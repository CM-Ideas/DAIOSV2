# Enterprise Engineering Constitution — MVP build sequence (Layer 0 → Layer 9)

This guide sequences the platform build in **dependency order**, not layer-number order.
Infrastructure and security must exist before anything else can run, so the actual
build order is: **9 → 8 → 5 → 0 → 2 → 1 → 3 → 4 → 6 → 7**, with a final integration
pass that proves the full governed flow end-to-end (per the DAIOS Implementation
Directive's "prove one complete flow before scaling" rule). Each phase below states
which constitutional layer(s) it satisfies. All tools are free and open-source —
no paid APIs anywhere.

Target: a working MVP in **16 weeks**, matching the cadence in your
`16-WEEK MVP EXECUTION PLAN`. Team can compress this for a proof-of-concept in
4–6 weeks by skipping the hardening steps marked **[hardening]**.

---

## Phase 0 — Local dev environment (Week 0, before Week 1)

**Purpose:** one shared baseline so every engineer runs the identical stack.

**Tools:** Docker, Docker Compose, Git, `make`

```bash
# install docker + compose plugin (Ubuntu/Debian)
sudo apt update && sudo apt install -y docker.io docker-compose-plugin git make

# verify
docker --version && docker compose version

# create the platform monorepo skeleton
mkdir eec-platform && cd eec-platform
git init
mkdir -p infra governance registries ai gateway product dashboards commerce docs
```

Create one `docker-compose.yml` at the repo root; every phase below appends
services to it rather than starting isolated stacks — this keeps networking
simple (all services share the `eec-net` bridge network).

```yaml
# docker-compose.yml (root — add services in each phase)
version: "3.9"
networks:
  eec-net:
    driver: bridge
```

**Checkpoint:** `docker compose config` parses with no errors.

---

## Phase 1 — Layer 9: CI/CD & infrastructure foundation (Weeks 1–2)

**Constitution operations covered:** deployment sequencing, environment matrix,
IaC, rollback strategy.

**Tools:** k3s (lightweight Kubernetes for MVP), Terraform, GitLab CE (or Gitea for a
lighter start), ArgoCD

```bash
# 1. stand up a single-node k3s cluster (MVP-sized; swap for full k8s later)
curl -sfL https://get.k3s.io | sh -
sudo k3s kubectl get nodes

# 2. install GitLab CE for source control + CI/CD (or Gitea if resources are limited)
docker run -d --name gitlab \
  --hostname gitlab.local \
  -p 8929:80 -p 2224:22 \
  -v gitlab_config:/etc/gitlab -v gitlab_data:/var/opt/gitlab \
  gitlab/gitlab-ce:latest

# 3. install Terraform and initialise the infra-as-code module
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
sudo apt install terraform
cd infra && terraform init

# 4. install ArgoCD into the cluster for GitOps deployment
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

**Checkpoint:** `kubectl get pods -n argocd` shows all pods `Running`; a "hello
world" deployment pushed to GitLab CE auto-syncs into the cluster via ArgoCD.

---

## Phase 2 — Layer 8: security, identity & compliance (Weeks 2–3)

**Constitution operations covered:** deployment prohibition until security/AI
sign-off exists; evidence register; IAM foundation for every later layer.

**Tools:** Keycloak (IAM/SSO), HashiCorp Vault OSS (secrets), OpenSearch (audit log)

```bash
# Keycloak — add to docker-compose.yml, then:
docker compose up -d keycloak
# create the enterprise realm + admin role
docker exec -it keycloak /opt/keycloak/bin/kcadm.sh config credentials \
  --server http://localhost:8080 --realm master --user admin --password admin
docker exec -it keycloak /opt/keycloak/bin/kcadm.sh create realms \
  -s realm=eec -s enabled=true

# Vault (dev mode for MVP; use raft storage + TLS before production)
docker run -d --name vault -p 8200:8200 \
  -e 'VAULT_DEV_ROOT_TOKEN_ID=root' hashicorp/vault:latest

export VAULT_ADDR=http://127.0.0.1:8200
export VAULT_TOKEN=root
vault secrets enable -path=eec kv-v2

# OpenSearch for audit logging
docker run -d --name opensearch -p 9200:9200 \
  -e "discovery.type=single-node" opensearchproject/opensearch:latest
```

**Checkpoint:** a test user can log in via Keycloak SSO; a secret written to
Vault (`vault kv put eec/test key=value`) is retrievable; an audit event lands
in OpenSearch.

---

## Phase 3 — Layer 5: data & integration backbone (Weeks 3–4)

**Constitution operations covered:** integration priority order (API → Event
Bus → Webhook → Plugin → SSO), ERD/data model standards, tenant boundary.

**Tools:** PostgreSQL, Kafka (or Redpanda — Kafka-compatible, lighter for MVP),
Kong Gateway (OSS)

```bash
# PostgreSQL
docker run -d --name postgres -e POSTGRES_PASSWORD=eec \
  -e POSTGRES_DB=eec_core -p 5432:5432 postgres:16

# Redpanda (Kafka API-compatible event bus — single binary, MVP-friendly)
docker run -d --name redpanda -p 9092:9092 \
  docker.redpanda.com/redpandadata/redpanda:latest \
  redpanda start --smp 1 --memory 1G --overprovisioned --node-id 0 \
  --kafka-addr PLAINTEXT://0.0.0.0:9092

# Kong Gateway (OSS) — API gateway in DB-less declarative mode for MVP
docker run -d --name kong --network eec-net \
  -e "KONG_DATABASE=off" -e "KONG_DECLARATIVE_CONFIG=/kong.yml" \
  -v $(pwd)/gateway/kong.yml:/kong.yml \
  -p 8000:8000 -p 8443:8443 kong:latest
```

**Checkpoint:** a topic created in Redpanda (`rpk topic create eec.events`)
receives and delivers a test message; Kong routes a test request to a stub
service.

---

## Phase 4 — Layer 0: governance & constitution as code (Weeks 4–5)

**Constitution operations covered:** master constitutional hierarchy, conflict
rule, DAIOS/DUDOS boundary rule, mandatory gate — encoded as enforceable policy,
not a PDF.

**Tools:** Open Policy Agent (OPA), Git repo (in GitLab CE from Phase 1)

```bash
# run OPA as a policy server
docker run -d --name opa -p 8181:8181 openpolicyagent/opa:latest \
  run --server --addr :8181

# write the first constitutional rule (example: no product without a DAD)
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

# push the policy to OPA
curl -X PUT --data-binary @governance/policies/gate.rego \
  http://localhost:8181/v1/policies/gate

# test it
curl -X POST http://localhost:8181/v1/data/eec/gate/allow \
  -d '{"input":{"has_product_registration":true,"has_dad":true,"has_mpif":true,"reuse_search_completed":true}}'
```

**Checkpoint:** any downstream service call to `/v1/data/eec/gate/allow`
returns `false` unless all constitutional preconditions are met — the gate is
now a live API, not a document.

---

## Phase 5 — Layer 2: knowledge, prompt, agent & decision registries (Weeks 5–7)

**Constitution operations covered:** enterprise knowledge lifecycle, prompt/
agent/decision constitutions, project digital twin.

**Tools:** Nextcloud (Drive replacement), Neo4j Community Edition (knowledge
graph), MinIO (object storage), PostgreSQL schemas for registries

```bash
# Nextcloud
docker run -d --name nextcloud -p 8081:80 nextcloud:latest

# Neo4j
docker run -d --name neo4j -p 7474:7474 -p 7687:7687 \
  -e NEO4J_AUTH=neo4j/eecgraph neo4j:community

# MinIO
docker run -d --name minio -p 9000:9000 -p 9001:9001 \
  -e MINIO_ROOT_USER=eec -e MINIO_ROOT_PASSWORD=eecsecret \
  minio/minio server /data --console-address ":9001"

# create registry schemas in Postgres
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

**Checkpoint:** a test prompt, agent, and decision record can be inserted and
queried; a document uploaded to Nextcloud gets a corresponding node created in
Neo4j linking it to a project.

---

## Phase 6 — Layer 1: intake & mandatory enterprise gate (Weeks 7–8)

**Constitution operations covered:** single front-door intake, reuse search,
gate sequence enforcement (calls the OPA policy from Phase 4).

**Tools:** n8n (workflow automation) or Camunda 8 Community (BPMN), Typesense
or OpenSearch (reuse search — reuse the OpenSearch instance from Phase 2)

```bash
# n8n — visual workflow builder for the intake form + gate sequence
docker run -d --name n8n -p 5678:5678 \
  -e N8N_BASIC_AUTH_ACTIVE=true \
  -e N8N_BASIC_AUTH_USER=admin -e N8N_BASIC_AUTH_PASSWORD=eecadmin \
  n8nio/n8n:latest

# Typesense for fast reuse/duplicate search over the registries
docker run -d --name typesense -p 8108:8108 \
  -v typesense-data:/data \
  typesense/typesense:latest \
  --data-dir /data --api-key=eecsearchkey --enable-cors
```

In n8n, build one workflow: **Webhook (intake form) → HTTP Request (Typesense
reuse search) → HTTP Request (OPA gate check) → If (allow=true) → Postgres
Insert (Product Registry) → else → Respond (rejected, reason).**

**Checkpoint:** submitting a test intake form via the n8n webhook either
creates a registered product (gate passed) or is rejected with a reason (gate
failed) — this is the first end-to-end governed flow.

---

## Phase 7 — Layer 3: AI & agentic engineering (Weeks 8–10)

**Constitution operations covered:** AI/model/agent/vector/RAG/evaluation/
safety registries — all self-hosted, zero paid inference.

**Tools:** Ollama, Qdrant (vector DB), LangChain + LlamaIndex, CrewAI or
LangGraph (agents), MLflow (model/eval registry)

```bash
# Ollama — serves open-weight models locally
curl -fsSL https://ollama.com/install.sh | sh
ollama pull llama3
ollama pull mistral
ollama serve &        # exposes http://localhost:11434

# Qdrant vector database
docker run -d --name qdrant -p 6333:6333 qdrant/qdrant:latest

# Python environment for orchestration and agents
python3 -m venv .venv && source .venv/bin/activate
pip install langchain langchain-community llama-index crewai mlflow qdrant-client

# quick smoke test — call the local model, no external API key needed
curl http://localhost:11434/api/generate -d '{
  "model": "llama3",
  "prompt": "Summarize the EEC mandatory gate in one sentence."
}'

# start MLflow to track prompt/agent evaluations
mlflow server --host 0.0.0.0 --port 5000
```

**Checkpoint:** a LangChain script embeds a test document into Qdrant, retrieves
it via a RAG query answered by the local Llama 3 model, and logs the evaluation
run to MLflow — with zero calls to any paid API.

---

## Phase 8 — Layer 4: product & enterprise factory (Weeks 9–11, overlaps Phase 7)

**Constitution operations covered:** enterprise product factory, DAIOS/DUDOS
module packaging, reusable module/plugin/SDK output.

**Tools:** Next.js (frontend), FastAPI (backend), Docker (packaging)

```bash
# scaffold the first product module frontend
npx create-next-app@latest product-shell --typescript --tailwind --app

# scaffold the backend service
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

# package as a reusable Docker image
cat > Dockerfile << 'EOF'
FROM python:3.12-slim
WORKDIR /app
COPY . .
RUN pip install fastapi uvicorn
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8001"]
EOF
docker build -t eec/product-module:0.1 .
```

**Checkpoint:** the packaged product image runs standalone, registers itself
in the Product Registry (Phase 5) via an API call on startup, and is reachable
through Kong Gateway (Phase 3).

---

## Phase 9 — Layer 6: dashboards & accountability engine (Weeks 11–13)

**Constitution operations covered:** enterprise dashboard constitution
(Executive/Chairman/Risk/AI dashboards), accountability engine, autonomous
governance overlay.

**Tools:** Prometheus, Grafana, Apache Superset, Grafana Loki

```bash
# Prometheus + Grafana
docker run -d --name prometheus -p 9090:9090 prom/prometheus:latest
docker run -d --name grafana -p 3000:3000 grafana/grafana:latest

# Superset for executive/BI dashboards
docker run -d --name superset -p 8088:8088 apache/superset:latest
docker exec -it superset superset fab create-admin \
  --username admin --firstname Chairman --lastname Office \
  --email admin@eec.local --password admin
docker exec -it superset superset db upgrade
docker exec -it superset superset init

# Loki for centralized logs (pairs with Grafana)
docker run -d --name loki -p 3100:3100 grafana/loki:latest
```

Connect Grafana to Prometheus (metrics) and Loki (logs); connect Superset
directly to the Postgres registries for the Chairman/Product/Risk dashboards.

**Checkpoint:** Grafana shows live container/service health; Superset shows a
live count of registered products, open decisions, and pending gate approvals
pulled directly from Postgres — with no manual data entry.

---

## Phase 10 — Layer 7: commercialization & marketplace (Weeks 13–14)

**Constitution operations covered:** commercialization constitution — pricing,
marketplace listing, revenue dashboard feed.

**Tools:** Medusa.js (open-source commerce engine), Metabase (revenue reporting)

```bash
npx create-medusa-app@latest eec-marketplace
cd eec-marketplace && npm run dev

docker run -d --name metabase -p 3001:3000 metabase/metabase:latest
```

**Checkpoint:** a test product from the Product Registry can be listed with a
price in Medusa; Metabase shows a revenue dashboard fed from the marketplace
database.

---

## Phase 11 — Autonomous governance overlay + full integration (Weeks 14–16)

**Constitution operations covered:** enterprise autonomous governance — the
cross-cutting supervisor that continuously checks every layer instead of
waiting for a human report; final proof of "one complete governed flow."

**Tools:** CrewAI (or LangGraph) supervisor agent, Kafka/Redpanda consumer,
Ollama

```bash
pip install crewai kafka-python
```

```python
# supervisor_agent.py — polls registries and Kafka events every N minutes
from kafka import KafkaConsumer
import psycopg2, json

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

Run this as a scheduled Kubernetes CronJob (Phase 1's k3s cluster) rather than
a manual script once it's stable.

**Final MVP checkpoint — end-to-end proof:**
1. A request enters through the n8n intake form (Phase 6).
2. Reuse search runs against Typesense (Phase 6).
3. The OPA gate (Phase 4) approves or rejects it.
4. On approval, it's registered in Postgres (Phase 5) and a Neo4j knowledge
   node is created.
5. An AI agent (Phase 7) assists drafting the BRD/SRS using the local Llama 3
   model — logged in MLflow.
6. The resulting product module (Phase 8) is packaged, deployed via ArgoCD
   (Phase 1), and secured behind Keycloak/Kong (Phases 2–3).
7. Its status appears automatically on the Grafana/Superset dashboards
   (Phase 9) — no manual report.
8. It can be listed for commercialization in Medusa (Phase 10).
9. The supervisor agent (Phase 11) flags it if any step stalls.

If all nine steps run without manual intervention, the MVP satisfies the
Implementation Directive's definition of done: **one complete, governed,
measurable flow — proven before scaling to further modules.**

---

## Summary table

| Phase | Weeks | Layer(s) | Core tools |
|---|---|---|---|
| 0 | 0 | — | Docker, Compose, Git |
| 1 | 1–2 | 9 | k3s, GitLab CE, Terraform, ArgoCD |
| 2 | 2–3 | 8 | Keycloak, Vault, OpenSearch |
| 3 | 3–4 | 5 | PostgreSQL, Redpanda, Kong |
| 4 | 4–5 | 0 | Open Policy Agent, Git |
| 5 | 5–7 | 2 | Nextcloud, Neo4j, MinIO, PostgreSQL |
| 6 | 7–8 | 1 | n8n, Typesense/OpenSearch |
| 7 | 8–10 | 3 | Ollama, Qdrant, LangChain, CrewAI, MLflow |
| 8 | 9–11 | 4 | Next.js, FastAPI, Docker |
| 9 | 11–13 | 6 | Prometheus, Grafana, Superset, Loki |
| 10 | 13–14 | 7 | Medusa.js, Metabase |
| 11 | 14–16 | overlay | CrewAI/LangGraph supervisor, Kafka |

**[hardening]** items to add after MVP proof, before scaling: TLS everywhere,
Vault raft storage (not dev mode), Keycloak production database, Kafka/Redpanda
multi-broker cluster, Postgres replication, GitLab CE HA, network policies in
Kubernetes, SBOM generation (Syft) and image signing (Cosign) in the CI pipeline.
