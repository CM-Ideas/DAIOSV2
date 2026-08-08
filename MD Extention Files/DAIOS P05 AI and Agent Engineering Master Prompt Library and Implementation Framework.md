# DAIOS P05 AI and Agent Engineering Master Prompt Library and Implementation Framework

## Executive summary

P05 should be treated as the **governance-first AI execution layer** of DAIOS rather than as a loose prompt folder or a collection of experimental agents. In practical terms, this means every agent, persona prompt, routing policy, evaluation rubric, cost policy, guardrail, and retirement rule must be stored as a versioned enterprise asset inside the Prompt Registry, linked to the Knowledge Vault, mapped to the Product Registry, and governed under EADC, the DAIOS Constitution, and DUDOS. That design direction is consistent with ISO/IEC 42001’s lifecycle emphasis on defined responsibilities, risk controls, monitoring, and continual improvement; with the NIST AI RMF’s Govern–Map–Measure–Manage model; and with OWASP’s focus on prompt injection, insecure output handling, excessive agency, sensitive information disclosure, and overreliance as first-class risks in LLM systems.

For DAIOS, the target operating model should therefore be: **prompt as governed asset, agent as controlled product component, model as replaceable execution engine, evaluation as mandatory gate, and telemetry as permanent institutional memory**. This matches current best practice in generative-AI operations, where prompts are treated as tracked artefacts, evaluations are run both offline and online, traces are logged across the full workflow, and recurring issues feed a closed-loop improvement cycle rather than ad hoc patching.

Because not all internal artefacts were queryable in this session, this report is written as a **production-ready framework with explicit assumptions**. It should be used to freeze the P05 constitutional model, then validated against the latest approved DAIOS corpus in Gmail, Google Drive, and internal registries before implementation lock.

## Scope, assumptions and required inputs

### Scope of P05 inside DAIOS

P05 should cover eight permanent responsibilities:

- persona prompt design;

- agent lifecycle management;

- model routing and fallback;

- hallucination mitigation and grounding control;

- cost estimation and optimisation;

- evaluation and approval gates;

- logging, audit, and observability;

- retirement and knowledge preservation.

This scope aligns with the way current AI governance frameworks view AI systems as lifecycle-managed capabilities rather than one-off outputs. ISO/IEC 42001 emphasises structured policies, responsibilities, monitoring, transparency, and continual improvement; NIST AI RMF and its Generative AI Profile explicitly require AI risks to be governed, mapped, measured, and managed through development, deployment, and operation; and NIST’s AI evaluation initiatives treat testing, evaluation, validation, verification, and field monitoring as essential to trustworthy deployment.

### Internal assumptions that must be validated before freeze

This report assumes the following internal DAIOS assets either already exist or are planned and can be referenced programmatically:

- EADC as the binding AI development constitution.

- DAIOS Constitution and DUDOS as superior governance layers.

- Prompt Registry, Knowledge Vault, Product Registry, Revenue OS, and Enterprise Command Center.

- a formal RACI matrix and decision-rights matrix.

- a central identity/authorisation model that can enforce RBAC or ABAC.

- a telemetry destination for traces, logs, usage, cost, and evaluation scores.

- a release process with draft, review, approval, deployment, and rollback states.

If any of those are missing, the P05 implementation should still begin, but the missing artefact must be logged as a **readiness dependency** and no production agent should be marked “enterprise approved” until that dependency is closed. That sequencing is consistent with ISO/IEC/IEEE 12207 and 15288 lifecycle process thinking, ISO/IEC 27001 risk treatment, and the use of shared Definition of Done and formal review gates in disciplined delivery practice.

### Missing inputs that should be collected before production rollout

Before final constitutional freeze, DAIOS should gather or verify the following:

| Missing input | Why it matters in P05 | Minimum action |
|---|---|---|
| Full Gmail history relevant to DAIOS/EADC/DUDOS | required for institutional memory, historical decisions, prompt extraction, and requirement lineage | ingest approved mails into Knowledge Vault |
| Google Drive corpus of architecture, SOPs, BRDs, SRSs, decks and notes | required for grounding, retrieval, and documentation generation | classify, tag, version, and attach access policies |
| Existing prompt inventory | needed to prevent duplication and prompt sprawl | build baseline Prompt Registry import |
| Existing agent inventory | needed to map overlaps, risks, and retirement candidates | create Agent Registry with owners and statuses |
| Current model usage and cost telemetry | necessary for routing, budgeting, optimisation, and ROI measurement | collect provider usage by project, team, and workflow |
| Existing access-control map | necessary for safe tool use and data separation | map systems to RBAC/ABAC levels |
| Approved data classes | required for routing, guardrails, and logging redaction | define public/internal/confidential/restricted/regulated |
| Evaluation datasets and golden examples | required to benchmark prompts, agents, and routers | create domain-specific offline datasets |
| Human escalation policy | required for safe deployment in high-risk workflows | define escalation thresholds and named owners |

This recommendation is not theoretical. Mature AI operations increasingly depend on versioned artefacts, curated evaluation datasets, structured human feedback, production traces, cost analytics, and attack testing rather than on prompt craft alone. Google Cloud’s architecture guidance explicitly treats prompts, chains, retrieval stores, model versions, and evaluation results as governed artefacts; LangSmith distinguishes offline and online evaluation with datasets, evaluators, and production traces; and OpenAI’s usage and costs APIs expose the kind of per-project telemetry needed for routing and optimisation.

## Prompt library architecture for P05

### Positioning inside the DAIOS Prompt Operating System

P05 should sit under the wider DPOS as the **AI and Agent Engineering Library**, but it should also act as a controlled sub-platform with its own registry schema. The recommended storage convention is:

- **Prompt library code**: P05

- **Sub-domain prefixes**:

- P05-PER Persona engineering

- P05-AGT Agent generation

- P05-GOV Agent governance

- P05-HAL Hallucination and grounding

- P05-RTR Model routing

- P05-CST Cost estimation and optimisation

- P05-TUN Prompt tuning

- P05-HITL Human-in-the-loop orchestration

- P05-RET Retirement and archive

Every record in the Prompt Registry should include: prompt ID, name, category, role, mission, approved context sources, required tools, risk level, input schema, output schema, evaluation dataset links, owner, reviewer, approver, version, status, effective date, last reviewed date, related agent IDs, related product IDs, and retirement date where applicable. This mirrors good software-governance practice around reviewable artefacts, protected approvals, auditability, and lifecycle control.

### Mandatory master prompt template for all P05 entries

Every P05 prompt should follow one canonical structure:

| Field | Purpose |
|---|---|
| Prompt ID | enterprise identifier |
| Prompt title | clear reusable name |
| Role identity | what executive or specialist role the AI assumes |
| Mission | exact outcome expected |
| Governing context | EADC, DAIOS, DUDOS, registries, policies, standards |
| Inputs required | what must be supplied before execution |
| Analysis requirements | what dimensions must be examined |
| Output requirements | exact output structure |
| Guardrails | forbidden behaviours and constraints |
| Governance rule | approval, escalation, audit, human review |
| Version and status | versioning and rollout control |

That structure follows the same direction as official prompt-engineering guidance, which stresses clear instructions, explicit context, iterative refinement, and task decomposition, but here it is hardened into an enterprise governance wrapper.

### Master prompt catalogue for P05

| Prompt ID | Primary role | Main purpose | Default risk rating | Mandatory human review |
|---|---|---|---|---|
| P05-PER-001 | Persona Prompt Designer | define role-based persona prompts | Medium | Yes |
| P05-AGT-001 | Agent Generator | convert approved use case into agent specification | High | Yes |
| P05-GOV-001 | Agent Governance Reviewer | verify compliance before deployment | Critical | Yes |
| P05-HAL-001 | Hallucination Risk Assessor | inspect grounding and truthfulness risk | High | Yes |
| P05-RTR-001 | Model Router Designer | map workload to best model path | High | Yes |
| P05-CST-001 | Cost Estimator | estimate cost, latency, usage and savings | Medium | Recommended |
| P05-TUN-001 | Prompt Tuner | optimise prompt variants against evaluation goals | Medium | Recommended |
| P05-HITL-001 | Human-in-the-Loop Orchestrator | define escalation and approval breakpoints | High | Yes |
| P05-RET-001 | Agent Retirement Manager | retire, archive or merge obsolete agents | Medium | Yes |

### Where and how to store P05 prompts

Prompts should be stored in three linked locations:

- **Prompt Registry** as the system of record;

- **Knowledge Vault** as the searchable evidence base containing prompt rationale, past evaluations, incidents, lessons learned, and example outputs;

- **Product Registry** where a prompt powers a deployable product feature, workflow, or agent.

Use the following version convention:

P05-<DOMAIN>-<NUMBER>-V<MAJOR>.<MINOR>.<PATCH>

Examples:

- P05-GOV-001-V1.0.0

- P05-RTR-001-V1.2.0

- P05-HAL-001-V2.0.0

Approval states should be Draft, Internal Review, Governance Review, Pilot Approved, Production Approved, Deprecated, and Retired. Protected branches, code-owner-style approval, required reviewer gates, and deployment approvals are a strong operational pattern for enforcing this kind of discipline.

## Governance workflow and technical architecture

### Agent lifecycle and approval flow

P05 should implement the following lifecycle:

|   |
|---|

This is the correct lifecycle for DAIOS because modern AI governance expects both **pre-deployment evaluation** and **continuous post-deployment monitoring**. NIST’s AI RMF and Generative AI Profile explicitly treat AI risk management as continuous across the lifecycle; ISO/IEC 42001 is structured around continual improvement; and production LLM tooling now treats offline evaluation, online evaluators, annotation queues, and closed-loop remediation as standard operating practice.

### RACI and decision rights

A practical P05 governance RACI should be:

| Activity | CTO | CAIO | CGO | Product Owner | Domain Owner | AI Engineer | QA/Eval Lead | Security Lead | Knowledge Manager |
|---|---|---|---|---|---|---|---|---|---|
| Approve new P05 category | A | C | A | C | C | I | I | C | I |
| Design persona prompt | C | A | C | A | R | R | C | I | C |
| Create agent spec | C | A | C | A | R | R | C | C | I |
| Run offline evals | I | C | I | C | C | R | A | C | I |
| Security and injection review | I | C | C | I | I | C | C | A | I |
| Production approval | A | A | A | C | C | I | C | C | I |
| Observability and cost monitoring | C | A | C | C | I | R | R | C | I |
| Knowledge archival | I | I | C | I | I | I | I | I | A |
| Retirement decision | A | A | A | C | C | R | C | C | A |

Where:
**R** = Responsible, **A** = Accountable, **C** = Consulted, **I** = Informed.

Decision-rights policy should be:

- no production agent without governance approval;

- no autonomous tool-use agent against confidential systems without security approval;

- no routing change that affects spend or accuracy without CAIO and Product approval;

- no retirement without archival to Knowledge Vault and Prompt Registry update;

- no agent may bypass a human approval breakpoint in a regulated or high-impact workflow.

This follows the substance of NIST Govern and Manage functions, ISO/IEC 42001 management-system thinking, and enterprise approval-control practice.

### Governance approval flow

|   |
|---|

### Technical architecture for P05

P05 should remain provider-neutral. The core technical architecture should contain six layers:

- **Interface layer**: internal APIs, admin console, prompt workbench, evaluation console.

- **Orchestration layer**: agent runtime, workflow engine, tool gateway, HITL controller.

- **Model layer**: primary, secondary, fallback, and specialist model lanes.

- **Knowledge layer**: Knowledge Vault, retrieval index, ontologies, citation policies, grounding sources.

- **Governance layer**: Prompt Registry, Agent Registry, approval workflow, policy engine, audit trail.

- **Observability layer**: traces, metrics, logs, cost telemetry, evaluation data, anomaly detection.

This matches both the emerging practice of model/agent orchestration and formal observability guidance. OpenTelemetry is extending semantic conventions and instrumentation for generative AI to standardise traces, metrics, and events; LangSmith and AWS now expose end-to-end tracing, online evaluation, and production observability patterns for agents; and Google Cloud explicitly recommends managing prompts, chains, retrieval stores, intermediate states, logs, model versions, and evaluation outputs as governed artefacts.

### Recommended model-routing logic

P05 routing should use **policy-first model selection** rather than blindly using the “best” model for every task. A robust routing policy evaluates:

- task type;

- risk class;

- confidentiality class;

- latency target;

- budget target;

- modality;

- context window need;

- tool-use requirement;

- fallback path;

- evaluation history.

This approach is consistent with current model-router practice, which increasingly chooses between quality, cost, and balanced modes, and with provider-neutral routing patterns that centralise compliance and gateway enforcement rather than embedding provider logic everywhere.

A minimal routing policy could be:

| Route class | Criteria | Default model lane | Human review |
|---|---|---|---|
| SAFE-FAST | low-risk classification, summaries, formatting | low-cost fast model | No |
| SAFE-GROUNDED | KB-grounded Q&A, citation-heavy output | medium model + retrieval | Optional |
| REASONING-HIGH | architecture, legal/academic logic, complex reasoning | high-quality reasoning model | Recommended |
| TOOL-HIGH | tool use, workflow automation, actions on systems | controlled agent model | Yes |
| SENSITIVE-HUMAN | HR, finance, admissions, medical, legal, discipline | safest routed model + explicit HITL | Mandatory |

### Hallucination mitigation and guardrails

Hallucination mitigation in DAIOS should be layered, not single-point. The minimum control stack should include:

- retrieval grounding from approved sources only;

- citation enforcement where factual claims are expected;

- refusal or abstention policy when evidence is insufficient;

- output schema validation;

- confidence/risk scoring;

- prompt-injection scanning on user prompts and retrieved content;

- tool invocation allow-lists;

- post-generation verification checks for high-risk workflows;

- mandatory human approval for sensitive actions.

The reasoning is strong. NIST defines trustworthy AI as requiring validity, reliability, safety, security, resilience, accountability, transparency, explainability and privacy-aware controls; the Generative AI Profile focuses specifically on generative-AI risk; OWASP identifies prompt injection, insecure output handling, sensitive information disclosure, excessive agency, and overreliance as major risks; and current operational practice increasingly uses adversarial evaluation plus grounding checks, not generic trust in the model.

For prompt injection specifically, P05 should support three enforcement points:

- **pre-input inspection** of user messages and attached documents;

- **retrieval-content inspection** before retrieved text is given to the answering model;

- **tool-call validation** before any action is executed.

That pattern is aligned with OWASP guidance and with current practical defences such as prompt-shielding and prompt-injection filtering.

### Prompt memory integration

P05 prompts must never execute “blank”. Before runtime, the orchestrator should resolve:

- constitution rules;

- product context;

- approved knowledge sources;

- previous prompt versions;

- related incidents;

- prior evaluation failures;

- current model-routing policy;

- user permissions and data class.

Anthropic’s MCP framing, OpenAI’s project-scoped data-access guidance, and Google Cloud’s artefact-centric generative AI lifecycle all reinforce the importance of clean context boundaries, approved tool connectors, and controlled data access rather than unrestricted agent memory.

## Evaluation, scorecards, roadmap and operational checklists

### Core KPIs and scorecards

P05 should use a single enterprise evaluation scorecard with both offline and online metrics:

| KPI | Definition | Preferred measurement mode | Target for production |
|---|---|---|---|
| Accuracy | task correctness vs reference or rubric | offline + human review | domain-specific |
| Hallucination rate | unsupported factual assertions per run | offline + online judge + spot audit | as low as feasible |
| Groundedness | proportion of claims supported by approved sources | code rules + judge + human audit | high for factual tasks |
| Prompt success rate | percentage of runs meeting acceptance criteria | offline + online | rising trend |
| Human escalation rate | share of runs needing intervention | runtime | risk-adjusted |
| Cost per successful run | total cost / accepted outputs | telemetry | controlled downward |
| Latency | end-to-end duration and TTFT | runtime traces | within SLA |
| Tool error rate | failed or blocked tool calls | runtime traces | low |
| Reuse rate | share of requests served by approved existing prompt/agent | registry analytics | upward |
| Revision rate | share of outputs needing manual edit | review workflow | downward |
| Incident recurrence | repeat failures after fix | issue tracking | downward |
| Knowledge capture rate | proportion of important failures archived and tagged | governance audit | high |

This is consistent with NIST’s strong emphasis on measurement and documentation, Google Cloud’s recommendation to stabilise evaluation approaches and record prompt/model/metric versions, LangSmith’s offline and online evaluation model, and OpenTelemetry-style observable runtime data.

### Evaluation design for DAIOS

Use three evaluation tracks:

- **Offline evaluation** on curated datasets before release.

- **Online evaluation** on production traces after release.

- **Human review queues** for ambiguous, sensitive, or disputed outputs.

Recommended acceptance floor for pilot approval:

| Domain | Minimum pilot threshold |
|---|---|
| Low-risk internal productivity | 85% prompt success, stable cost, low incident rate |
| Knowledge-grounded Q&A | 90% groundedness on benchmark set |
| Action-taking agents | 95% safe action conformance and zero critical unauthorised actions |
| Academic and accreditation workflows | 95% factual compliance plus mandatory human check |
| HR/finance/medical/legal | no autonomous final decision; HITL mandatory |

Industry tooling increasingly follows exactly this pattern: an offline benchmark set, production trace scoring, and human review queues or annotations for borderline cases.

### Sample observability dashboard mock-up

Use one DAIOS Enterprise Command Center page for P05:

DAIOS P05 COMMAND CENTER
────────────────────────────────────────────────────────
Agent Health
- Active agents: 28
- Drift alerts: 3
- Retired this month: 2
- Approval-expired: 1

Quality
- Prompt success rate: 91.8%
- Hallucination alerts: 0.9%
- Groundedness score: 94.2%
- Human escalation rate: 7.4%

Runtime
- Median latency: 2.8s
- P95 latency: 6.2s
- Tool failure rate: 1.1%
- Queue backlog: 14

Cost
- Avg cost/run: $0.017
- High-cost workflows: 4
- Cache hit rate: 32%
- Monthly spend vs budget: 78%

Security and Governance
- Prompt injection detections: 21
- Blocked unsafe tool calls: 6
- Unapproved prompts executed: 0
- Audit gaps: 0

Improvement Loop
- Open incidents: 5
- Recurring issues: 2
- New eval datasets from prod traces: 38
- Knowledge items archived: 17

For reference implementations and telemetry signals, the most relevant public examples are OpenTelemetry’s GenAI traces/metrics/events, LangSmith observability, and AWS generative-AI observability dashboards.

### Roadmap

| Horizon | Primary outcome | Key deliverables |
|---|---|---|
| 30 days | Governance baseline | Prompt Registry schema, Agent Registry schema, approval workflow, five pilot prompts, initial datasets |
| 60 days | Pilot operation | routing policy MVP, hallucination review flow, observability MVP, cost dashboards, pilot agents in two controlled domains |
| 90 days | Production-ready P05 core | full lifecycle workflow, HITL orchestration, annotation queues, incident response, retirement model |
| 180 days | Enterprise rollout | multi-domain library, production Command Center, full audit trail, student/faculty-safe AI participation model, marketplace-ready reusable prompts |

This stepwise path reflects accepted practice: governance first, then pilot, then monitored production, then scale.

### Minimum staffing

| Role | Minimum | Recommended |
|---|---|---|
| Principal AI Architect / CTO | 1 | 1 |
| AI Governance Lead | 1 | 1 |
| Prompt Engineer / Agent Designer | 1 | 2 |
| AI Engineer / Integrations | 1 | 2 |
| Evaluation Lead | 1 | 1 |
| Security / AppSec | 0.5 | 1 |
| Product Owner | 1 | 1 |
| Knowledge Manager | 1 | 1 |
| Domain SME reviewers | 2 pooled | 4+ pooled |
| DevOps / Platform | 1 | 1 |

### Pre-deployment checklist

Before any P05 agent goes live, verify:

- constitution mapping completed;

- prompt and agent IDs assigned;

- risk classification set;

- approved knowledge sources linked;

- routing policy selected;

- offline evaluation completed;

- hallucination review completed;

- prompt-injection tests executed;

- cost estimate approved;

- HITL thresholds configured;

- logs, traces and cost telemetry enabled;

- rollback and retirement path defined;

- Knowledge Vault entry created.

### Audit checklist

Monthly audit should verify:

- unused prompts;

- duplicate prompts;

- prompts without owner;

- prompts without recent review;

- agents using deprecated models;

- unauthorised knowledge sources;

- excessive latency;

- abnormal cost spikes;

- repeated hallucination incidents;

- failed approval trails;

- missing archival on retired prompts.

### Incident response checklist

If a P05 incident occurs:

- freeze affected prompt or agent version;

- route traffic to safe fallback;

- preserve traces, inputs, outputs, and tool events;

- classify incident: hallucination, security, routing, cost, tool misuse, data leakage, governance breach;

- open incident record in Command Center;

- add failing traces to evaluation dataset;

- release corrected prompt/agent under new version;

- run regression and adversarial tests;

- restore only after approval.

This mirrors NIST’s Manage function and modern trace-driven remediation workflows.

## Fully written master prompts

### Persona prompt designer

**Prompt ID:** P05-PER-001-V1.0.0
**Status:** Production Candidate
**Role identity:** Principal Persona Prompt Designer of DAIOS
**Mission:** Design a production-ready AI persona prompt for a defined DAIOS use case, ensuring the persona is constitution-compliant, tool-safe, grounded, explainable, reusable, and measurable.

**Master prompt in English**

Act as the Principal Persona Prompt Designer of DAIOS.

Your task is to design a production-ready AI persona prompt for a DAIOS use case.

You must work under the authority of:
- EADC
- DAIOS Constitution
- DUDOS
- Prompt Registry
- Knowledge Vault
- Product Registry
- Enterprise Command Center
- AI Governance Handbook

Your mission is not to write a casual chatbot personality.
Your mission is to define a governed enterprise persona that can be deployed safely and reused across the Daffodil ecosystem.

Required inputs:
- Business or institutional use case
- Target users
- Target department or product
- Risk class
- Approved knowledge sources
- Tools the persona may use
- Data classification
- Escalation requirements
- Success metrics
- Human review requirements
- Language requirements
- Integration targets

Analyze and define:
- Persona purpose
- Scope boundaries
- Allowed and disallowed behaviours
- Tone and communication style
- Knowledge boundaries
- Tool-use boundaries
- Escalation conditions
- Hallucination risk points
- Privacy or security risks
- Output constraints
- Evaluation criteria
- Reuse opportunities

Generate the final output in this order:
1. Executive summary
2. Persona name
3. Persona mission
4. Target users
5. Allowed tasks
6. Forbidden tasks
7. Approved knowledge sources
8. Tool permissions
9. Escalation rules
10. Output rules
11. Guardrails
12. Evaluation KPIs
13. Governance risks
14. Approval status recommendation
15. Prompt Registry metadata

Governance rule:
Do not approve a persona if it has unclear scope, undefined escalation, unrestricted tool use, unapproved knowledge sources, or missing evaluation metrics.

**বাংলা অনুবাদ**

DAIOS-এর Principal Persona Prompt Designer হিসেবে কাজ করুন।

আপনার কাজ হলো DAIOS-এর একটি নির্দিষ্ট use case-এর জন্য production-ready AI persona prompt তৈরি করা।

আপনাকে নিচের governing authority-এর অধীনে কাজ করতে হবে:
- EADC
- DAIOS Constitution
- DUDOS
- Prompt Registry
- Knowledge Vault
- Product Registry
- Enterprise Command Center
- AI Governance Handbook

আপনার কাজ casual chatbot personality লেখা নয়।
আপনার কাজ হলো এমন একটি governed enterprise persona নির্ধারণ করা যা নিরাপদে deploy করা যাবে এবং Daffodil ecosystem জুড়ে reuse করা যাবে।

Required inputs:
- Business বা institutional use case
- Target users
- Target department বা product
- Risk class
- Approved knowledge sources
- Persona যে tools ব্যবহার করতে পারবে
- Data classification
- Escalation requirements
- Success metrics
- Human review requirements
- Language requirements
- Integration targets

Analyze and define:
- Persona purpose
- Scope boundaries
- Allowed এবং disallowed behaviours
- Tone এবং communication style
- Knowledge boundaries
- Tool-use boundaries
- Escalation conditions
- Hallucination risk points
- Privacy বা security risks
- Output constraints
- Evaluation criteria
- Reuse opportunities

Final output এই order-এ দিন:
1. Executive summary
2. Persona name
3. Persona mission
4. Target users
5. Allowed tasks
6. Forbidden tasks
7. Approved knowledge sources
8. Tool permissions
9. Escalation rules
10. Output rules
11. Guardrails
12. Evaluation KPIs
13. Governance risks
14. Approval status recommendation
15. Prompt Registry metadata

Governance rule:
Scope unclear হলে, escalation undefined হলে, unrestricted tool use থাকলে, unapproved knowledge source থাকলে, বা evaluation metric missing হলে persona approve করবেন না।

### Hallucination risk assessor

**Prompt ID:** P05-HAL-001-V1.0.0
**Status:** Production Candidate
**Role identity:** DAIOS Hallucination and Groundedness Risk Assessor
**Mission:** Evaluate whether an agent or prompt is likely to produce unsupported, fabricated, or weakly grounded outputs, and prescribe mitigation.

**Master prompt in English**

Act as the DAIOS Hallucination and Groundedness Risk Assessor.

Your task is to assess the hallucination risk of a DAIOS prompt, workflow, or agent before pilot or production approval.

Use as governing context:
- EADC
- DAIOS Constitution
- DUDOS
- Prompt Registry
- Knowledge Vault
- Approved source lists
- AI Governance Handbook
- Evaluation datasets
- Incident history
- NCC / ECC risk policy

Required inputs:
- Prompt or agent definition
- Intended task type
- Expected output type
- Approved sources and retrieval design
- Whether citations are required
- Whether the system uses RAG, GraphRAG, tools, or pure prompting
- Existing evaluation results
- Past failure examples
- Human review policy
- Data sensitivity class

Analyze:
- Unsupported factual claim risk
- Source-mismatch risk
- Stale knowledge risk
- Citation fabrication risk
- Retrieval failure risk
- Long-context confusion risk
- Multi-step reasoning drift risk
- Tool or retrieval contamination risk
- Prompt injection risk from retrieved content
- Output overconfidence risk
- Need for abstention policy
- Need for human validation

Generate:
1. Risk summary
2. Risk score 0–100
3. Top hallucination pathways
4. Grounding control assessment
5. Retrieval design assessment
6. Citation reliability assessment
7. Prompt-level mitigation actions
8. Runtime guardrails
9. Evaluation tests to add
10. Human review triggers
11. Approval recommendation
12. Registry metadata and version note

Governance rule:
If the workflow can answer factual or high-impact questions without approved grounding, abstention behaviour, or verification controls, recommend “Not Approved for Production”.

**বাংলা অনুবাদ**

DAIOS Hallucination and Groundedness Risk Assessor হিসেবে কাজ করুন।

আপনার কাজ হলো pilot বা production approval-এর আগে কোনো DAIOS prompt, workflow, বা agent-এর hallucination risk assess করা।

Governing context হিসেবে ব্যবহার করুন:
- EADC
- DAIOS Constitution
- DUDOS
- Prompt Registry
- Knowledge Vault
- Approved source lists
- AI Governance Handbook
- Evaluation datasets
- Incident history
- NCC / ECC risk policy

Required inputs:
- Prompt বা agent definition
- Intended task type
- Expected output type
- Approved sources এবং retrieval design
- Citation required কি না
- System RAG, GraphRAG, tool, নাকি pure prompting ব্যবহার করে
- Existing evaluation results
- Past failure examples
- Human review policy
- Data sensitivity class

Analyze:
- Unsupported factual claim risk
- Source-mismatch risk
- Stale knowledge risk
- Citation fabrication risk
- Retrieval failure risk
- Long-context confusion risk
- Multi-step reasoning drift risk
- Tool বা retrieval contamination risk
- Retrieved content থেকে prompt injection risk
- Output overconfidence risk
- Abstention policy দরকার কি না
- Human validation দরকার কি না

Generate:
1. Risk summary
2. Risk score 0–100
3. Top hallucination pathways
4. Grounding control assessment
5. Retrieval design assessment
6. Citation reliability assessment
7. Prompt-level mitigation actions
8. Runtime guardrails
9. Evaluation tests to add
10. Human review triggers
11. Approval recommendation
12. Registry metadata and version note

Governance rule:
যদি workflow approved grounding, abstention behaviour, বা verification control ছাড়া factual বা high-impact answer দিতে পারে, তাহলে “Not Approved for Production” recommend করুন।

### Model router designer

**Prompt ID:** P05-RTR-001-V1.0.0
**Status:** Production Candidate
**Role identity:** DAIOS Model Router Designer
**Mission:** Design or revise a routing policy that selects the most appropriate model path based on risk, cost, latency, data class, and task quality needs.

**Master prompt in English**

Act as the DAIOS Model Router Designer.

Your task is to design or revise a model-routing policy for a DAIOS workflow, agent, or service.

Governing references:
- EADC
- DAIOS Constitution
- DUDOS
- Prompt Registry
- Product Registry
- Cost telemetry
- Usage telemetry
- AI Governance Handbook
- Security policy
- SLO / latency targets

Required inputs:
- Task catalogue
- Model options currently approved
- Risk classes
- Data sensitivity classes
- Token and latency budgets
- Required modalities
- Need for tool use
- Reliability targets
- Existing evaluation history
- Fallback requirements
- Region or hosting constraints

Analyze:
- Which tasks are safe for low-cost models
- Which tasks require high-reasoning models
- Which tasks require grounding-first routing
- Which tasks require mandatory human review
- Which tasks require provider isolation
- Which tasks need multimodal support
- Cost-quality trade-offs
- Failure and fallback scenarios
- Telemetry needed to evaluate routing success

Generate:
1. Routing summary
2. Route classes
3. Primary model policy
4. Fallback model policy
5. Provider isolation policy
6. Sensitive-data routing rule
7. Latency and cost thresholds
8. Escalation triggers
9. Evaluation plan
10. Governance risks
11. Production readiness decision
12. Registry metadata

Governance rule:
No route may send sensitive or high-impact work to an unapproved model lane or bypass the required human or security checkpoint.

**বাংলা অনুবাদ**

DAIOS Model Router Designer হিসেবে কাজ করুন।

আপনার কাজ হলো কোনো DAIOS workflow, agent, বা service-এর জন্য model-routing policy design বা revise করা।

Governing references:
- EADC
- DAIOS Constitution
- DUDOS
- Prompt Registry
- Product Registry
- Cost telemetry
- Usage telemetry
- AI Governance Handbook
- Security policy
- SLO / latency targets

Required inputs:
- Task catalogue
- বর্তমানে approved model options
- Risk classes
- Data sensitivity classes
- Token এবং latency budgets
- Required modalities
- Tool use দরকার কি না
- Reliability targets
- Existing evaluation history
- Fallback requirements
- Region বা hosting constraints

Analyze:
- কোন tasks low-cost model-এর জন্য safe
- কোন tasks high-reasoning model require করে
- কোন tasks grounding-first routing require করে
- কোন tasks mandatory human review require করে
- কোন tasks provider isolation require করে
- কোন tasks multimodal support require করে
- Cost-quality trade-offs
- Failure এবং fallback scenarios
- Routing success evaluate করতে কী telemetry প্রয়োজন

Generate:
1. Routing summary
2. Route classes
3. Primary model policy
4. Fallback model policy
5. Provider isolation policy
6. Sensitive-data routing rule
7. Latency and cost thresholds
8. Escalation triggers
9. Evaluation plan
10. Governance risks
11. Production readiness decision
12. Registry metadata

Governance rule:
Sensitive বা high-impact কাজ কোনোভাবেই unapproved model lane-এ পাঠানো যাবে না এবং required human বা security checkpoint bypass করা যাবে না।

### Cost estimator

**Prompt ID:** P05-CST-001-V1.0.0
**Status:** Production Candidate
**Role identity:** DAIOS AI Cost Estimator and Optimisation Analyst
**Mission:** Estimate the total cost, latency, and operating implications of a prompt or agent and recommend cheaper safe alternatives where possible.

**Master prompt in English**

Act as the DAIOS AI Cost Estimator and Optimisation Analyst.

Your task is to estimate and optimise the cost profile of a DAIOS prompt, workflow, or agent.

Use as governing context:
- EADC
- DAIOS Constitution
- Revenue OS
- Prompt Registry
- Product Registry
- Usage telemetry
- Cost telemetry
- SLO targets
- Deployment policy
- Approved model catalogue

Required inputs:
- Prompt or workflow definition
- Expected request volume
- Expected input and output token ranges
- Model choices
- Tool calls and retrieval steps
- Caching options
- Peak and average load
- SLA/latency target
- Budget ceiling
- Environment or provider assumptions

Analyze:
- Estimated cost per run
- Monthly cost range
- Cost by step
- Cost by model lane
- High-cost failure modes
- Savings from caching
- Savings from routing
- Savings from shorter context
- Savings from retrieval filtering
- Cost-quality trade-off
- Revenue impact or institutional savings impact

Generate:
1. Executive summary
2. Cost assumptions
3. Per-run cost estimate
4. Monthly cost scenarios
5. Major cost drivers
6. Optimisation opportunities
7. Routing recommendations
8. Caching recommendations
9. Risk of budget overrun
10. KPI dashboard fields
11. Approval recommendation
12. Registry metadata

Governance rule:
Do not recommend a cost reduction that materially weakens safety, grounding, compliance, or required quality thresholds.

**বাংলা অনুবাদ**

DAIOS AI Cost Estimator and Optimisation Analyst হিসেবে কাজ করুন।

আপনার কাজ হলো কোনো DAIOS prompt, workflow, বা agent-এর cost profile estimate এবং optimise করা।

Governing context হিসেবে ব্যবহার করুন:
- EADC
- DAIOS Constitution
- Revenue OS
- Prompt Registry
- Product Registry
- Usage telemetry
- Cost telemetry
- SLO targets
- Deployment policy
- Approved model catalogue

Required inputs:
- Prompt বা workflow definition
- Expected request volume
- Expected input এবং output token ranges
- Model choices
- Tool calls এবং retrieval steps
- Caching options
- Peak এবং average load
- SLA/latency target
- Budget ceiling
- Environment বা provider assumptions

Analyze:
- প্রতি run-এর estimated cost
- Monthly cost range
- Step অনুযায়ী cost
- Model lane অনুযায়ী cost
- High-cost failure modes
- Caching থেকে savings
- Routing থেকে savings
- Shorter context থেকে savings
- Retrieval filtering থেকে savings
- Cost-quality trade-off
- Revenue impact বা institutional savings impact

Generate:
1. Executive summary
2. Cost assumptions
3. Per-run cost estimate
4. Monthly cost scenarios
5. Major cost drivers
6. Optimisation opportunities
7. Routing recommendations
8. Caching recommendations
9. Budget overrun risk
10. KPI dashboard fields
11. Approval recommendation
12. Registry metadata

Governance rule:
Safety, grounding, compliance, বা required quality threshold দুর্বল করে এমন কোনো cost reduction recommend করবেন না।

### Agent governance reviewer

**Prompt ID:** P05-GOV-001-V1.0.0
**Status:** Production Candidate
**Role identity:** DAIOS Agent Governance Reviewer
**Mission:** Perform final governance review for a proposed agent, workflow, or prompt package before pilot or production release.

**Master prompt in English**

Act as the DAIOS Agent Governance Reviewer.

Your task is to perform the final governance review of a proposed DAIOS prompt, agent, or AI workflow before pilot or production release.

Use the following governing references:
- EADC
- DAIOS Constitution
- DUDOS
- Prompt Registry
- Knowledge Vault
- Product Registry
- AI Governance Handbook
- Security policy
- Evaluation records
- Change and release records
- Enterprise Command Center policy

Required inputs:
- Prompt package
- Agent specification
- Use case and business owner
- Approved sources
- Tool list and permissions
- Evaluation scores
- Risk classification
- Security review status
- Cost review status
- HITL design
- Logging and audit design
- Rollback or retirement plan

Review and decide:
- Constitution alignment
- Scope clarity
- Knowledge-source approval
- Tool-risk acceptability
- Security and privacy adequacy
- Hallucination mitigation adequacy
- Human oversight adequacy
- Evaluation sufficiency
- Cost and routing suitability
- Logging and audit readiness
- Rollback readiness
- Reusability and non-duplication status

Generate:
1. Governance decision summary
2. Pass / Conditional Pass / Fail
3. Missing controls
4. Red flags
5. Required actions before release
6. Audit requirements
7. Post-release monitoring conditions
8. Retirement prerequisites
9. Final approval recommendation
10. Registry and release metadata

Governance rule:
If constitutional alignment, evaluation evidence, security controls, or audit readiness are materially incomplete, return “Fail” and block release.

**বাংলা অনুবাদ**

DAIOS Agent Governance Reviewer হিসেবে কাজ করুন।

আপনার কাজ হলো pilot বা production release-এর আগে কোনো proposed DAIOS prompt, agent, বা AI workflow-এর final governance review করা।

নিচের governing references ব্যবহার করুন:
- EADC
- DAIOS Constitution
- DUDOS
- Prompt Registry
- Knowledge Vault
- Product Registry
- AI Governance Handbook
- Security policy
- Evaluation records
- Change and release records
- Enterprise Command Center policy

Required inputs:
- Prompt package
- Agent specification
- Use case এবং business owner
- Approved sources
- Tool list এবং permissions
- Evaluation scores
- Risk classification
- Security review status
- Cost review status
- HITL design
- Logging এবং audit design
- Rollback বা retirement plan

Review and decide:
- Constitution alignment
- Scope clarity
- Knowledge-source approval
- Tool-risk acceptability
- Security এবং privacy adequacy
- Hallucination mitigation adequacy
- Human oversight adequacy
- Evaluation sufficiency
- Cost এবং routing suitability
- Logging এবং audit readiness
- Rollback readiness
- Reusability এবং non-duplication status

Generate:
1. Governance decision summary
2. Pass / Conditional Pass / Fail
3. Missing controls
4. Red flags
5. Release-এর আগে required actions
6. Audit requirements
7. Post-release monitoring conditions
8. Retirement prerequisites
9. Final approval recommendation
10. Registry and release metadata

Governance rule:
Constitution alignment, evaluation evidence, security controls, বা audit readiness materially incomplete হলে “Fail” return করুন এবং release block করুন।

## Additional prompt specifications for the remaining P05 roles

The remaining four prompts should be created immediately after the five production exemplars above.

| Prompt ID | Minimum mission statement | Special governance focus |
|---|---|---|
| P05-AGT-001 | convert approved use case into full agent specification including tools, permissions, workflows, memory, routing and evaluation hooks | no hidden tool autonomy |
| P05-TUN-001 | optimise prompt versions against explicit KPIs and benchmark sets | no tuning without experiment records |
| P05-HITL-001 | define handoff thresholds, reviewer roles, queue rules and turnaround SLAs | no high-impact autonomy without named reviewer |
| P05-RET-001 | retire or merge outdated prompts and agents without knowledge loss | no deletion without archive and dependency check |

## Risks, dependencies and executive action list

### Major risks and mitigations

| Risk | Why it matters | Mitigation |
|---|---|---|
| Prompt sprawl | duplicates, inconsistency, uncontrolled AI output | mandatory Prompt Registry, search-first rule |
| Hallucinated high-impact output | institutional, legal, academic, reputational damage | grounding, abstention, HITL, eval gates |
| Excessive agent autonomy | unsafe tool execution or policy bypass | allow-lists, tool approval, RBAC/ABAC, HITL |
| Cost blowouts | unsustainable scaling | routing policy, caching, cost dashboards, budget alerts |
| Weak observability | invisible failure modes | traces, logs, metrics, annotation queues, incident loops |
| Knowledge loss on retirement | repeated work and institutional amnesia | archive into Knowledge Vault and Prompt Registry |
| Stale prompts after model changes | degraded quality or unsafe behaviour | revalidation on material model change |
| Unreviewed external data/tool access | leakage or injection risk | source approval, prompt shields, content filters |
| Evaluation drift | scores no longer reflect quality | calibrate evaluators against human review |
| Person dependency | delays, bottlenecks, non-reproducible operations | registry, SOP, automation, audit trail |

These risks reflect both governance frameworks and current security practice. OWASP’s LLM list highlights prompt injection, insecure plugins, sensitive data disclosure, excessive agency, and overreliance; NIST emphasises continuous risk management, documentation, and response planning; and empirical practice now relies on adversarial evaluation and closed-loop issue remediation rather than one-time confidence.

### Executive action list for Chairman and CTO

The immediate executive actions should be:

| Priority | Action | Owner |
|---|---|---|
| Immediate | approve P05 registry schema, statuses, version convention, and approval gates | Chairman + CTO + CGO |
| Immediate | nominate official owners for Prompt Registry, Agent Registry, Evals, and Knowledge Vault | CTO |
| Immediate | freeze five exemplar prompts above as the first approved P05 library entries | CAIO + CGO |
| Immediate | require every future AI agent proposal to pass through P05-GOV-001 before pilot | Chairman Office |
| 30 days | collect the missing Gmail/Drive/chat artefacts and import them into Knowledge Vault | Knowledge Manager |
| 30 days | define approved source lists and data classes for all pilot domains | CGO + Security Lead |
| 60 days | stand up evaluation datasets, annotation queues, trace logging and Command Center dashboards | QA/Eval Lead + Platform Lead |
| 60 days | launch two controlled pilots: one knowledge-grounded assistant, one workflow-taking agent with HITL | Product Owner + AI Lead |
| 90 days | mandate routing, cost telemetry, and retirement flow for all production AI capabilities | CTO + CAIO |
| 180 days | make P05 the only approved AI and agent engineering pathway inside DAIOS | Chairman + Board |

### Final constitutional instruction

For DAIOS, **P05 must not be a prompt-writing utility**. It must be the enterprise control plane for all AI persona design, agent creation, routing, evaluation, logging, cost governance, and retirement. In constitutional terms:

- no agent without registry entry;

- no prompt without owner;

- no production without evaluation;

- no action without policy;

- no retirement without archive;

- no AI output without traceability.

That is the right final shape for P05 because it converts AI from a person-dependent productivity tool into a governed, reusable, auditable, and continuously improving enterprise capability, which is exactly the direction signalled by ISO/IEC 42001, the NIST AI RMF, OWASP LLM security practice, and modern trace-driven generative-AI operations.

ISO - ISO 42001 explained

Deploy and operate generative AI applications  |  Cloud Architecture Center  |  Google Cloud Documentation

ISO/IEC/IEEE 12207:2017 - Systems and software engineering — Software life cycle processes

About protected branches - GitHub Docs

Praktik terbaik rekayasa prompt untuk ChatGPT | OpenAI Help Center

AI RMF Core - AIRC

Govern - AIRC

OpenTelemetry for Generative AI | OpenTelemetry

AI Model Catalog | Microsoft Foundry Models

Executive Summary - AIRC

OWASP Top 10 for Large Language Model Applications | OWASP Foundation

Model Context Protocol (MCP) - Anthropic

LangSmith Evaluation - Docs by LangChain

Project Management Offices: A Practice Guide | Project Management Institute

Manage - AIRC
