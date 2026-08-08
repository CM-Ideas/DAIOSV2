# Enterprise Engineering Constitution — complete MVP build guide (every tool, Layer 0 → Layer 9)

This is the full version of the build sequence — it includes **every tool** listed
in `EEC_Open_Source_Platform_Architecture.html` for each layer, not a trimmed
subset. Where the architecture doc listed two or three options for the same slot
(e.g. Kafka **or** NATS, Ollama **or** vLLM, GitLab CE **or** Gitea), both are
shown so your team can pick — or run both in a POC and compare.

**Build order is dependency-first, not numeric.** Layer 9 (infrastructure) and
Layer 8 (security) must exist before anything above them can run safely. The
sequence below is: **Layer 9 → 8 → 5 → 0 → 2 → 1 → 3 → 4 → 6 → 7**, plus a final
cross-cutting overlay phase. Every phase states which layer it satisfies and
which constitutional operations it fulfils, so you can still read this
layer-0-to-9 if that's how your steering committee wants it reported.

All tools are free, open-source, and self-hostable. No paid APIs or metered
model calls anywhere in this stack.

---

## Phase 1 — Layer 9: CI/CD & infrastructure (Weeks 1–2)

**Constitution operations:** deployment sequencing, environment matrix, IaC,
rollback strategy, supply-chain integrity (SBOM/attestation).

**Full tool list:** Kubernetes, Docker, GitLab CE (or Gitea), ArgoCD, Terraform,
Syft, CycloneDX

### 1.1 Docker (container runtime — required by every later layer)
```bash
sudo apt update && sudo apt install -y docker.io docker-compose-plugin
sudo systemctl enable --now docker
docker --version
```

### 1.2 Kubernetes
For an MVP, run **k3s** (single-binary, lightweight, fully conformant Kubernetes).
For a production-scale build, use full **kubeadm**.

```bash
# Option A — k3s (recommended for MVP)
curl -sfL https://get.k3s.io | sh -
sudo k3s kubectl get nodes
alias kubectl='sudo k3s kubectl'

# Option B — full kubeadm cluster (production scale)
sudo apt install -y kubeadm kubelet kubectl
sudo kubeadm init --pod-network-cidr=10.244.0.0/16
kubectl apply -f https://raw.githubusercontent.com/flannel-io/flannel/master/Documentation/kube-flannel.yml
```

### 1.3 Source control — GitLab CE or Gitea
```bash
# Option A — GitLab CE (full DevOps platform, heavier)
docker run -d --name gitlab --hostname gitlab.local \
  -p 8929:80 -p 2224:22 \
  -v gitlab_config:/etc/gitlab -v gitlab_data:/var/opt/gitlab \
  gitlab/gitlab-ce:latest

# Option B — Gitea (lightweight Git server, faster MVP start)
docker run -d --name gitea -p 3050:3000 -p 2225:22 \
  -v gitea_data:/data gitea/gitea:latest
```

### 1.4 ArgoCD (GitOps continuous delivery)
```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# get the initial admin password
kubectl -n argocd get secret argocd-initial-admin-secret \
  -o jsonpath="{.data.password}" | base64 -d

# access the UI
kubectl port-forward svc/argocd-server -n argocd 8090:443
```

### 1.5 Terraform (infrastructure as code)
```bash
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
sudo apt-add-repository "deb [arch=$(dpkg --print-architecture)] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
sudo apt update && sudo apt install terraform

mkdir -p infra && cd infra
cat > main.tf << 'EOF'
terraform {
  required_providers {
    docker = { source = "kreuzwerker/docker" }
  }
}
provider "docker" {}
EOF
terraform init
terraform plan
terraform apply -auto-approve
```

### 1.6 Syft (SBOM generation)
```bash
curl -sSfL https://raw.githubusercontent.com/anchore/syft/main/install.sh \
  | sh -s -- -b /usr/local/bin

# generate an SBOM for a built image
syft eec/product-module:0.1 -o table
```

### 1.7 CycloneDX (standard SBOM format, feeds into CI evidence pack)
```bash
# generate a CycloneDX-format SBOM directly with Syft
syft eec/product-module:0.1 -o cyclonedx-json > sbom-cyclonedx.json

# or use the dedicated CycloneDX CLI for merging/validating SBOMs
npm install -g @cyclonedx/cyclonedx-cli
cyclonedx-cli validate --input-file sbom-cyclonedx.json
```

**Checkpoint:** cluster is reachable via `kubectl get nodes`; a test commit to
GitLab CE/Gitea triggers an ArgoCD sync; `terraform apply` provisions a test
resource cleanly; a built image produces a valid CycloneDX SBOM.

---

## Phase 2 — Layer 8: security, identity & compliance (Weeks 2–3)

**Constitution operations:** deployment prohibition until security/AI sign-off,
evidence register, IAM foundation for every later layer.

**Full tool list:** Keycloak, HashiCorp Vault, OpenSearch, Trivy, OWASP ZAP

### 2.1 Keycloak (IAM / SSO / RBAC)
```bash
docker run -d --name keycloak -p 8080:8080 \
  -e KEYCLOAK_ADMIN=admin -e KEYCLOAK_ADMIN_PASSWORD=admin \
  quay.io/keycloak/keycloak:latest start-dev

# create the enterprise realm
docker exec -it keycloak /opt/keycloak/bin/kcadm.sh config credentials \
  --server http://localhost:8080 --realm master --user admin --password admin
docker exec -it keycloak /opt/keycloak/bin/kcadm.sh create realms \
  -s realm=eec -s enabled=true

# create governance roles (used by Layer 0's OPA policies later)
docker exec -it keycloak /opt/keycloak/bin/kcadm.sh create roles \
  -r eec -s name=governance-officer
docker exec -it keycloak /opt/keycloak/bin/kcadm.sh create roles \
  -r eec -s name=architecture-review-board
```

### 2.2 HashiCorp Vault (secrets management)
```bash
docker run -d --name vault -p 8200:8200 \
  -e 'VAULT_DEV_ROOT_TOKEN_ID=root' hashicorp/vault:latest

export VAULT_ADDR=http://127.0.0.1:8200
export VAULT_TOKEN=root
vault secrets enable -path=eec kv-v2
vault kv put eec/db password=eecsecret
vault kv get eec/db
```

### 2.3 OpenSearch (audit log / SIEM)
```bash
docker run -d --name opensearch -p 9200:9200 -p 9600:9600 \
  -e "discovery.type=single-node" \
  -e "OPENSEARCH_INITIAL_ADMIN_PASSWORD=Eec-Admin1!" \
  opensearchproject/opensearch:latest

curl -k -u admin:Eec-Admin1! https://localhost:9200
```

### 2.4 Trivy (vulnerability scanning — container images and IaC)
```bash
sudo apt install -y wget apt-transport-https gnupg
wget -qO - https://aquasecurity.github.io/trivy-repo/deb/public.key | sudo apt-key add -
echo "deb https://aquasecurity.github.io/trivy-repo/deb generic main" \
  | sudo tee -a /etc/apt/sources.list.d/trivy.list
sudo apt update && sudo apt install trivy

# scan a built product image before it's allowed through the gate
trivy image eec/product-module:0.1

# scan Terraform/Kubernetes manifests
trivy config ./infra
```

### 2.5 OWASP ZAP (dynamic application security testing)
```bash
docker run -t owasp/zap2docker-stable zap-baseline.py \
  -t http://host.docker.internal:8001 -r zap-report.html
```

**Checkpoint:** a test user logs in via Keycloak SSO; a secret round-trips
through Vault; a test event lands in OpenSearch; Trivy blocks a deliberately
vulnerable test image; ZAP produces a baseline report against the Layer 4
product module stub.

---

## Phase 3 — Layer 5: data & integration backbone (Weeks 3–4)

**Constitution operations:** integration priority order (API → Event Bus →
Webhook → Plugin → SSO), ERD/data model standards, tenant boundary.

**Full tool list:** PostgreSQL, TimescaleDB, Apache Kafka, NATS, Kong Gateway,
Keycloak SSO (integration, not re-install)

### 3.1 PostgreSQL + TimescaleDB
```bash
docker run -d --name postgres -e POSTGRES_PASSWORD=eec \
  -e POSTGRES_DB=eec_core -p 5432:5432 timescale/timescaledb:latest-pg16

psql "postgresql://postgres:eec@localhost:5432/eec_core" \
  -c "CREATE EXTENSION IF NOT EXISTS timescaledb;"
```

### 3.2 Apache Kafka (full, via Bitnami images)
```bash
docker run -d --name zookeeper -p 2181:2181 bitnami/zookeeper:latest \
  -e ALLOW_ANONYMOUS_LOGIN=yes
docker run -d --name kafka -p 9092:9092 \
  -e KAFKA_BROKER_ID=1 \
  -e KAFKA_ZOOKEEPER_CONNECT=zookeeper:2181 \
  -e ALLOW_PLAINTEXT_LISTENER=yes \
  --link zookeeper bitnami/kafka:latest

# create a topic
docker exec -it kafka kafka-topics.sh --create \
  --topic eec.events --bootstrap-server localhost:9092 --partitions 3
```

### 3.3 NATS (lightweight alternative event bus)
```bash
docker run -d --name nats -p 4222:4222 -p 8222:8222 nats:latest -js

# publish/subscribe smoke test using the NATS CLI
nats pub eec.events "test message"
nats sub eec.events
```

### 3.4 Kong Gateway (API gateway, DB-less mode for MVP)
```bash
mkdir -p gateway
cat > gateway/kong.yml << 'EOF'
_format_version: "3.0"
services:
  - name: product-module
    url: http://product-module:8001
    routes:
      - name: product-module-route
        paths: ["/api/products"]
EOF

docker run -d --name kong \
  -e "KONG_DATABASE=off" -e "KONG_DECLARATIVE_CONFIG=/kong.yml" \
  -v $(pwd)/gateway/kong.yml:/kong.yml \
  -p 8000:8000 -p 8443:8443 -p 8001:8001 kong:latest

curl http://localhost:8000/api/products
```

### 3.5 Keycloak SSO client registration (integrating Layer 8 into Layer 5)
```bash
docker exec -it keycloak /opt/keycloak/bin/kcadm.sh create clients -r eec \
  -s clientId=eec-gateway -s publicClient=false -s secret=eecgatewaysecret \
  -s 'redirectUris=["http://localhost:8000/*"]'
```

**Checkpoint:** a Kafka topic and a NATS subject both accept and deliver test
messages; Kong routes a request through to a stub service; TimescaleDB
extension is active on the core database; the gateway client authenticates
against Keycloak.

---

## Phase 4 — Layer 0: governance & constitution as code (Weeks 4–5)

**Constitution operations:** master constitutional hierarchy, conflict rule,
DAIOS/DUDOS boundary rule, mandatory gate — enforced as policy, not a PDF.

**Full tool list:** Open Policy Agent, Gitea/GitLab CE (repo, already installed
in Phase 1), Keycloak (governance RBAC, already installed in Phase 2)

### 4.1 Open Policy Agent (OPA)
```bash
docker run -d --name opa -p 8181:8181 openpolicyagent/opa:latest \
  run --server --addr :8181

mkdir -p governance/policies
cat > governance/policies/gate.rego << 'EOF'
package eec.gate

default allow = false

allow {
  input.has_product_registration == true
  input.has_dad == true
  input.has_mpif == true
  input.reuse_search_completed == true
}
EOF

curl -X PUT --data-binary @governance/policies/gate.rego \
  http://localhost:8181/v1/policies/gate

curl -X POST http://localhost:8181/v1/data/eec/gate/allow \
  -d '{"input":{"has_product_registration":true,"has_dad":true,"has_mpif":true,"reuse_search_completed":true}}'
```

### 4.2 Constitution version control (Gitea or GitLab CE from Phase 1)
```bash
git clone http://localhost:3050/eec/constitution.git   # Gitea
# or
git clone http://localhost:8929/eec/constitution.git   # GitLab CE

git add governance/policies/gate.rego
git commit -m "Add mandatory enterprise gate policy v1.0"
git push origin main
```

### 4.3 Keycloak governance RBAC enforcement (from Phase 2)
```bash
# assign the governance-officer role to a test user so only they can approve gate overrides
docker exec -it keycloak /opt/keycloak/bin/kcadm.sh add-roles -r eec \
  --uusername governance.lead --rolename governance-officer
```

**Checkpoint:** the OPA policy is version-controlled in Git, deployed via CI,
and returns `false` for any request missing a precondition; only users with
the `governance-officer` Keycloak role can push policy changes to the protected
branch (enforce via Git branch protection rules).

---

## Phase 5 — Layer 2: knowledge, prompt, agent & decision registries (Weeks 5–7)

**Constitution operations:** enterprise knowledge lifecycle, prompt/agent/
decision constitutions, project digital twin.

**Full tool list:** Nextcloud, Neo4j Community Edition, MinIO, PostgreSQL

### 5.1 Nextcloud (Google Drive replacement)
```bash
docker run -d --name nextcloud -p 8081:80 \
  -e POSTGRES_HOST=postgres -e POSTGRES_DB=nextcloud \
  -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=eec \
  nextcloud:latest
```

### 5.2 Neo4j Community Edition (enterprise knowledge graph)
```bash
docker run -d --name neo4j -p 7474:7474 -p 7687:7687 \
  -e NEO4J_AUTH=neo4j/eecgraph neo4j:community

# create the first linkage: a document connected to a project
cypher-shell -a bolt://localhost:7687 -u neo4j -p eecgraph << 'EOF'
CREATE (p:Project {name: "Pilot Module"})
CREATE (d:Document {name: "BRD v1"})
CREATE (d)-[:BELONGS_TO]->(p);
EOF
```

### 5.3 MinIO (object storage)
```bash
docker run -d --name minio -p 9000:9000 -p 9001:9001 \
  -e MINIO_ROOT_USER=eec -e MINIO_ROOT_PASSWORD=eecsecret \
  minio/minio server /data --console-address ":9001"

# create the first bucket for the Knowledge Vault
docker run --rm --network host minio/mc \
  alias set eec http://localhost:9000 eec eecsecret
docker run --rm --network host minio/mc mb eec/knowledge-vault
```

### 5.4 PostgreSQL registries (Prompt / Agent / Decision)
```bash
psql "postgresql://postgres:eec@localhost:5432/eec_core" << 'EOF'
CREATE SCHEMA registry;
CREATE TABLE registry.prompt (
  id UUID PRIMARY KEY, owner TEXT, purpose TEXT, version TEXT,
  risk TEXT, status TEXT, created_at TIMESTAMPTZ DEFAULT now());
CREATE TABLE registry.agent (
  id UUID PRIMARY KEY, owner TEXT, permissions JSONB, budget NUMERIC,
  status TEXT, created_at TIMESTAMPTZ DEFAULT now());
CREATE TABLE registry.decision (
  id UUID PRIMARY KEY, evidence TEXT, owner TEXT, impact TEXT,
  rollback_plan TEXT, approved BOOLEAN DEFAULT false);
EOF
```

**Checkpoint:** a document uploaded to Nextcloud has a corresponding node in
Neo4j; a file lands in the MinIO `knowledge-vault` bucket; test rows insert
cleanly into all three registry tables.

---

## Phase 6 — Layer 1: intake & mandatory enterprise gate (Weeks 7–8)

**Constitution operations:** single front-door intake, reuse search, gate
sequence enforcement (calls the OPA policy from Phase 4).

**Full tool list:** Camunda 8 Community, n8n, Typesense, OpenSearch (already
installed in Phase 2)

### 6.1 Camunda 8 Community (BPMN-based gate workflow — heavier, more formal)
```bash
git clone https://github.com/camunda/camunda-platform.git
cd camunda-platform
docker compose -f docker-compose.yaml up -d
# Operate UI at http://localhost:8081, Zeebe gateway at localhost:26500
```

### 6.2 n8n (lightweight visual workflow builder — faster MVP start)
```bash
docker run -d --name n8n -p 5678:5678 \
  -e N8N_BASIC_AUTH_ACTIVE=true \
  -e N8N_BASIC_AUTH_USER=admin -e N8N_BASIC_AUTH_PASSWORD=eecadmin \
  n8nio/n8n:latest
```
In n8n, build: **Webhook (intake form) → HTTP Request (Typesense reuse search)
→ HTTP Request (OPA gate check) → If (allow=true) → Postgres Insert (Product
Registry) → else → Respond (rejected, reason).**

### 6.3 Typesense (fast reuse/duplicate search)
```bash
docker run -d --name typesense -p 8108:8108 \
  -v typesense-data:/data \
  typesense/typesense:latest \
  --data-dir /data --api-key=eecsearchkey --enable-cors

# index a product for reuse search
curl -X POST http://localhost:8108/collections \
  -H "X-TYPESENSE-API-KEY: eecsearchkey" \
  -H "Content-Type: application/json" \
  -d '{"name":"products","fields":[{"name":"title","type":"string"}]}'
```

### 6.4 OpenSearch (alternative/complementary reuse search — reuse Phase 2 instance)
```bash
curl -X PUT "https://localhost:9200/products" -k -u admin:Eec-Admin1! \
  -H "Content-Type: application/json" \
  -d '{"mappings":{"properties":{"title":{"type":"text"}}}}'
```

**Checkpoint:** submitting a test intake via n8n (or triggering a Camunda
process instance) runs the reuse search, calls the OPA gate, and either
registers a product or returns a rejection reason — this is the first
end-to-end governed flow.

---

## Phase 7 — Layer 3: AI & agentic engineering (Weeks 8–10)

**Constitution operations:** AI/model/agent/vector/RAG/evaluation/safety
registries — all self-hosted, zero paid inference.

**Full tool list:** Ollama, vLLM, LangChain, LlamaIndex, Qdrant, Milvus,
CrewAI, AutoGen, LangGraph, MLflow

### 7.1 Ollama (simplest local model server)
```bash
curl -fsSL https://ollama.com/install.sh | sh
ollama pull llama3
ollama pull mistral
ollama pull qwen2
ollama serve &
curl http://localhost:11434/api/generate -d '{"model":"llama3","prompt":"test"}'
```

### 7.2 vLLM (high-throughput inference server — production-grade alternative)
```bash
python3 -m venv .venv-vllm && source .venv-vllm/bin/activate
pip install vllm

python3 -m vllm.entrypoints.openai.api_server \
  --model mistralai/Mistral-7B-Instruct-v0.2 --port 8002

curl http://localhost:8002/v1/completions \
  -H "Content-Type: application/json" \
  -d '{"model":"mistralai/Mistral-7B-Instruct-v0.2","prompt":"test","max_tokens":50}'
```

### 7.3 LangChain + LlamaIndex (RAG orchestration)
```bash
python3 -m venv .venv && source .venv/bin/activate
pip install langchain langchain-community llama-index

python3 << 'EOF'
from langchain_community.llms import Ollama
llm = Ollama(model="llama3")
print(llm.invoke("Summarize the EEC mandatory gate in one sentence."))
EOF
```

### 7.4 Qdrant (vector database)
```bash
docker run -d --name qdrant -p 6333:6333 qdrant/qdrant:latest
curl http://localhost:6333/collections
```

### 7.5 Milvus (alternative vector database — larger scale)
```bash
curl -sfL https://raw.githubusercontent.com/milvus-io/milvus/master/scripts/standalone_embed.sh -o standalone_embed.sh
bash standalone_embed.sh start
# Milvus is now available at localhost:19530
```

### 7.6 CrewAI (role-based agent framework)
```bash
pip install crewai crewai-tools
python3 << 'EOF'
from crewai import Agent, Task, Crew
researcher = Agent(role="Researcher", goal="Summarize EEC gate rules",
                    backstory="Governance analyst", llm="ollama/llama3")
task = Task(description="Summarize the mandatory gate", agent=researcher)
crew = Crew(agents=[researcher], tasks=[task])
print(crew.kickoff())
EOF
```

### 7.7 AutoGen (multi-agent conversation framework — alternative to CrewAI)
```bash
pip install pyautogen
python3 << 'EOF'
import autogen
config_list = [{"model": "llama3", "base_url": "http://localhost:11434/v1", "api_key": "ollama"}]
assistant = autogen.AssistantAgent("assistant", llm_config={"config_list": config_list})
user = autogen.UserProxyAgent("user", code_execution_config=False)
user.initiate_chat(assistant, message="Summarize the EEC mandatory gate.")
EOF
```

### 7.8 LangGraph (stateful agent graphs — alternative orchestration)
```bash
pip install langgraph
```

### 7.9 MLflow (model/prompt/agent evaluation registry)
```bash
pip install mlflow
mlflow server --host 0.0.0.0 --port 5000 &

python3 << 'EOF'
import mlflow
mlflow.set_tracking_uri("http://localhost:5000")
with mlflow.start_run():
    mlflow.log_param("model", "llama3")
    mlflow.log_metric("eval_score", 0.87)
EOF
```

**Checkpoint:** Ollama and vLLM both respond to a test prompt; a document
embedded and stored in both Qdrant and Milvus is retrievable; CrewAI, AutoGen,
and LangGraph each complete a trivial multi-step task using the local model;
the run is logged in MLflow — with zero calls to any paid API.

---

## Phase 8 — Layer 4: product & enterprise factory (Weeks 9–11)

**Constitution operations:** enterprise product factory, DAIOS/DUDOS module
packaging, reusable module/plugin/SDK output.

**Full tool list:** React, Next.js, FastAPI, NestJS, Docker

### 8.1 React + Next.js (frontend)
```bash
npx create-next-app@latest product-shell --typescript --tailwind --app
cd product-shell && npm run dev
```

### 8.2 FastAPI (Python backend — lightweight, AI-friendly)
```bash
python3 -m venv product-api && source product-api/bin/activate
pip install fastapi uvicorn
mkdir product-api-src && cd product-api-src
cat > main.py << 'EOF'
from fastapi import FastAPI
app = FastAPI(title="EEC Product Module")

@app.get("/health")
def health():
    return {"status": "ok"}
EOF
uvicorn main:app --reload --port 8001
```

### 8.3 NestJS (Node.js backend — alternative for teams standardizing on TypeScript end-to-end)
```bash
npm install -g @nestjs/cli
nest new product-api-nest
cd product-api-nest
npm run start:dev
```

### 8.4 Docker packaging (reusable module output)
```bash
cat > Dockerfile << 'EOF'
FROM python:3.12-slim
WORKDIR /app
COPY . .
RUN pip install fastapi uvicorn
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8001"]
EOF
docker build -t eec/product-module:0.1 .
docker run -d -p 8001:8001 eec/product-module:0.1
```

**Checkpoint:** both the FastAPI and NestJS backend stubs respond on
`/health`; the packaged Docker image runs standalone and registers itself in
the Product Registry (Phase 5) on startup; the Next.js frontend calls it
successfully through Kong (Phase 3).

---

## Phase 9 — Layer 6: dashboards & accountability engine (Weeks 11–13)

**Constitution operations:** enterprise dashboard constitution (Executive/
Chairman/Risk/AI dashboards), accountability engine.

**Full tool list:** Grafana, Prometheus, Apache Superset, Loki

### 9.1 Prometheus (metrics collection)
```bash
docker run -d --name prometheus -p 9090:9090 prom/prometheus:latest
```

### 9.2 Grafana (dashboards)
```bash
docker run -d --name grafana -p 3000:3000 grafana/grafana:latest
# add Prometheus as a data source at http://localhost:3000
```

### 9.3 Apache Superset (executive/BI dashboards)
```bash
docker run -d --name superset -p 8088:8088 apache/superset:latest
docker exec -it superset superset fab create-admin \
  --username admin --firstname Chairman --lastname Office \
  --email admin@eec.local --password admin
docker exec -it superset superset db upgrade
docker exec -it superset superset init
# connect Superset to the eec_core Postgres database via the UI
```

### 9.4 Grafana Loki (centralized logs)
```bash
docker run -d --name loki -p 3100:3100 grafana/loki:latest
# add Loki as a data source in Grafana for log correlation with metrics
```

**Checkpoint:** Grafana shows live container/service health from Prometheus
and correlated logs from Loki; Superset shows a live count of registered
products, open decisions, and pending gate approvals pulled directly from
Postgres — no manual data entry.

---

## Phase 10 — Layer 7: commercialization & marketplace (Weeks 13–14)

**Constitution operations:** commercialization constitution — pricing,
marketplace listing, revenue dashboard feed.

**Full tool list:** Medusa.js, Saleor, Metabase

### 10.1 Medusa.js (headless commerce engine)
```bash
npx create-medusa-app@latest eec-marketplace
cd eec-marketplace && npm run dev
```

### 10.2 Saleor (alternative — GraphQL-first commerce platform)
```bash
git clone https://github.com/saleor/saleor-platform.git
cd saleor-platform
docker compose up -d
# GraphQL API at http://localhost:8000/graphql/
```

### 10.3 Metabase (revenue reporting)
```bash
docker run -d --name metabase -p 3001:3000 metabase/metabase:latest
# connect to the marketplace database via the setup wizard
```

**Checkpoint:** a test product from the Product Registry can be listed with a
price in both Medusa and Saleor; Metabase shows a revenue dashboard fed live
from the marketplace database.

---

## Phase 11 — Autonomous governance overlay + full integration (Weeks 14–16)

**Constitution operations:** enterprise autonomous governance — the
cross-cutting supervisor that continuously checks every layer; final proof of
"one complete governed flow."

**Tools used:** CrewAI or LangGraph (Phase 7), Kafka or NATS (Phase 3), Ollama
(Phase 7)

```bash
pip install crewai kafka-python
```

```python
# supervisor_agent.py — polls registries and the event bus continuously
from kafka import KafkaConsumer
import psycopg2

consumer = KafkaConsumer('eec.events', bootstrap_servers='localhost:9092')

def check_delays():
    conn = psycopg2.connect("postgresql://postgres:eec@localhost:5432/eec_core")
    cur = conn.cursor()
    cur.execute("SELECT id FROM registry.decision WHERE approved = false")
    open_items = cur.fetchall()
    if open_items:
        print(f"[Autonomous Governance] {len(open_items)} decisions pending approval")

for message in consumer:
    check_delays()
```

Run this as a Kubernetes CronJob (Phase 1's cluster) once stable:
```bash
kubectl create cronjob eec-supervisor --image=eec/supervisor:0.1 \
  --schedule="*/5 * * * *" -- python supervisor_agent.py
```

**Final MVP checkpoint — end-to-end proof, every tool exercised:**
1. Request enters through n8n or Camunda (Phase 6).
2. Reuse search runs against Typesense and/or OpenSearch (Phase 6, Phase 2).
3. The OPA gate (Phase 4) approves or rejects it, backed by Keycloak roles (Phase 2).
4. On approval, it's registered in PostgreSQL (Phase 5), files land in
   Nextcloud/MinIO, and a Neo4j knowledge-graph node is created.
5. An AI agent (CrewAI/AutoGen/LangGraph on Ollama or vLLM, Phase 7) drafts the
   BRD/SRS using retrieval from Qdrant/Milvus — logged in MLflow.
6. The resulting product module (Next.js + FastAPI/NestJS, Phase 8) is
   packaged with Docker, scanned by Trivy and OWASP ZAP (Phase 2), given an
   SBOM by Syft/CycloneDX (Phase 1), and deployed via ArgoCD (Phase 1) behind
   Kong and Keycloak SSO (Phase 3).
7. Status appears automatically on Grafana/Superset/Loki dashboards (Phase 9).
8. It can be listed for commercialization in Medusa or Saleor, with revenue
   visible in Metabase (Phase 10).
9. The supervisor agent (Phase 11) flags it if any step stalls, publishing to
   Kafka/NATS (Phase 3).

If all nine steps run without manual intervention, the MVP satisfies the
Implementation Directive's definition of done.

---

## Complete tool inventory by layer

| Layer | Tools (all included, no omissions) |
|---|---|
| 9 — Infra/CI-CD | Docker, Kubernetes (k3s or kubeadm), GitLab CE, Gitea, ArgoCD, Terraform, Syft, CycloneDX |
| 8 — Security | Keycloak, HashiCorp Vault, OpenSearch, Trivy, OWASP ZAP |
| 5 — Data/Integration | PostgreSQL, TimescaleDB, Apache Kafka, NATS, Kong Gateway, Keycloak (SSO) |
| 0 — Governance | Open Policy Agent, Gitea/GitLab CE (repo), Keycloak (RBAC) |
| 2 — Knowledge | Nextcloud, Neo4j Community Edition, MinIO, PostgreSQL |
| 1 — Intake/Gate | Camunda 8 Community, n8n, Typesense, OpenSearch |
| 3 — AI/Agentic | Ollama, vLLM, LangChain, LlamaIndex, Qdrant, Milvus, CrewAI, AutoGen, LangGraph, MLflow |
| 4 — Product Factory | React, Next.js, FastAPI, NestJS, Docker |
| 6 — Dashboards | Grafana, Prometheus, Apache Superset, Loki |
| 7 — Commercialization | Medusa.js, Saleor, Metabase |
| Overlay — Autonomous governance | CrewAI/LangGraph, Kafka/NATS, Ollama |

**[hardening — post-MVP]:** TLS everywhere, Vault raft storage (not dev mode),
Keycloak with a production database, Kafka/NATS multi-broker clustering,
PostgreSQL replication, GitLab CE HA, Kubernetes network policies, image
signing with Cosign alongside Syft/CycloneDX SBOMs.
