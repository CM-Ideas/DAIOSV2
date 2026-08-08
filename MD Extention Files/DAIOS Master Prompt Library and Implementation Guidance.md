# DAIOS Master Prompt Library and Implementation Guidance

## Executive summary

This report consolidates the DAIOS direction expressed across your recent inputs into an implementable Prompt Operating System for the six requested modules: Governance and Constitution, Intake and Diagnosis, Documentation Generation, Architecture and Engineering, AI and Agent Engineering, and Delivery and PMO. It is written to help you freeze the Constitution and move into controlled implementation without losing prompts, knowledge, architectural intent, or governance discipline.

The design principle is straightforward: every request must enter DAIOS through a governed intake, must be checked for duplication and constitutional alignment before work begins, must produce structured documentation before coding, must pass architecture and AI governance reviews before release, and must be executed through a PMO model that reduces person-dependency and preserves knowledge. That sequence aligns naturally with software life-cycle control in ISO/IEC/IEEE 12207, system life-cycle control in ISO/IEC/IEEE 15288, product-quality evaluation in ISO/IEC 25010, information-security management in ISO/IEC 27001, cloud-security guidance in ISO/IEC 27017 and ISO/IEC 27018, AI management in ISO/IEC 42001, cybersecurity governance in NIST CSF 2.0, AI risk management in the NIST AI RMF, secure software development in NIST SSDF, and application-security verification in OWASP ASVS and OWASP AISVS.

The recommended operating logic for DAIOS is therefore:

- **Constitution before action**

- **Search before build**

- **Documentation before development**

- **Architecture before implementation**

- **AI governance before agent deployment**

- **PMO control before scale**

- **Knowledge capture before closure**

- **Commercialisation before expansion**

This report assumes the DAIOS, DUDOS and EADC principles you supplied in chat are authoritative. Access to Gmail and Google Drive artefacts was not directly queryable in this session, so where internal details are unspecified, I label them as such rather than guessing.

## Governing architecture and update model

The strongest interpretation of your latest guidance is that DAIOS should not be treated as a document set; it should be treated as a **controlled enterprise prompt orchestration layer**. In practice, that means DPOS becomes the operating shell and the six P-modules become governed entry points into the enterprise. The architecture should separate immutable constitutional logic from updateable prompt libraries, registries, evidence stores and integration contracts. That is what allows “zero-maintenance continuous self-correction” without touching root architecture after every change.

|   |
|---|

This model is consistent with lifecycle-driven engineering and risk governance. ISO/IEC/IEEE 12207 and 15288 both emphasise defined processes, activities and tasks across acquisition, development, operation, maintenance and retirement; NIST SSDF similarly argues that secure practices must be integrated into each SDLC rather than bolted on afterwards.

A practical DAIOS update mechanism should use **plug-in placeholders** rather than prompt rewrites. Use these reserved anchors in every master prompt:

| Placeholder | Use |
|---|---|
| [CONSTITUTION_RULESET] | Current DAIOS + EADC + DUDOS clauses |
| [ACCREDITATION_RULESET] | Academic / service / accreditation rules |
| [SECURITY_RULESET] | ISO, NIST, OWASP, privacy controls |
| [MODULE_INTEGRATION_MAP] | System-specific integration matrix |
| [LOCAL_POLICY_EXT] | Department, country or business-unit add-ons |
| [AI_MODEL_POLICY_EXT] | Model-routing, cost, safety and provider rules |
| [METRIC_PROFILE] | KPI thresholds, dashboards, target values |
| [EVIDENCE_PROFILE] | Mandatory artefacts and proof requirements |
| [RELEASE_PROFILE] | Pilot, MVP, rollout and release criteria |
| [FUTURE_TECH_EXT] | Agentic AI, SI, IoT, robotics, voice, vision, etc. |

The purpose is to freeze the constitutional shell while keeping the operating libraries extensible. That is exactly the kind of modularity recommended by TOGAF for reusable architecture assets and by CMMI for repeatable, improving organisational capability.

A reserved module should also be defined now:

| Prompt family | Status | Recommendation |
|---|---|---|
| P02 | Unspecified in current brief | Reserve for Product Strategy, Duplication Control and Commercial Feasibility Orchestrator |

The following integration methods should be standardised inside DAIOS:

| Method | Best use | Strengths | Risks | DAIOS rule |
|---|---|---|---|---|
| API | Real-time system-to-system integration | Structured, auditable, scalable | Requires versioning and auth | Default for core enterprise systems |
| Webhook | Event notification and lightweight automation | Fast, reactive | Retry/idempotency complexity | Use for status-change events |
| Shared database | Legacy or tightly coupled internal reporting | Simple for old systems | High coupling, security risk | Avoid unless transitional only |
| Event bus | Enterprise event-driven orchestration | Loose coupling, scalability | Operational maturity needed | Preferred for future DAIOS expansion |
| Plugin | Reusable module capability | Fast reuse, low duplication | Plugin governance needed | Use for DAIOS-native extensions |
| SSO | Unified identity and RBAC | Better user control | IAM dependency | Mandatory for enterprise apps |
| File exchange | Transitional or external-party cases | Easy adoption | Error-prone, low traceability | Temporary only; replace over time |

## Governance and intake modules

### Governance and Constitution module

**DPOS entry**

| Field | Value |
|---|---|
| Prompt ID | P00-GOV-CONSTITUTION-ORCHESTRATOR-V1.0 |
| Owner | Governance Office / Enterprise Architecture Office |
| Purpose | Enforce EADC, DAIOS Constitution, DUDOS alignment, approval routing, auditability and non-deployment without governance |
| Risk level | Critical |
| Trigger | Any request for software, AI, automation, dashboard, competition, integration, module upgrade or rollout |
| Primary outputs | Compliance decision, constitutional mapping, approval requirements, risk flags, evidence gap report |
| Review cycle | Monthly; immediate review after policy change |

**What this module must do**

P00 should be the first gate in every flow. It should map the request to the relevant constitution clauses, identify whether it is academic, internal utility, institutional product, customer product, or research-commercialisation candidate, then apply the proper controls. This is where “Constitution-Driven, Outcome-Driven, Accreditation-Ready, Customer/Commercial-focused” becomes operational. ISO/IEC 42001 is particularly relevant here because it formalises an AI management-system approach with continuous improvement, transparency and responsible use; NIST AI RMF adds the risk-governance lens; NIST CSF 2.0 explicitly adds a Govern function; and OWASP AISVS gives verifiable security requirements for AI-enabled systems.

**Required screens and fields**

| Screen | Critical fields |
|---|---|
| Constitution mapping | Request ID, business unit, request type, product class, academic/commercial status, applicable constitutions, accreditation impact, decision owner |
| Approval rules | Needed approvers, approval sequence, risk class, architecture review required, AI review required, security review required |
| Audit and exceptions | Exception reason, compensating control, expiry date, approving authority, follow-up task |
| Policy registry | Clause ID, source document, version, effective date, superseded-by, department applicability |

**Core entities**

PolicyClause, ConstitutionMap, ApprovalRule, DecisionRight, RACIProfile, RiskClass, ExceptionRequest, AuditRecord, QualityGate, ReleaseGate.

**APIs, events and webhooks**

- POST /governance/assess

- GET /governance/request/{id}

- POST /governance/exception

- Event: governance.assessment.completed

- Event: governance.exception.approved

- Webhook: compliance.blocked

- Webhook: approval.required

**RBAC**

| Role | Permissions |
|---|---|
| Chairman / Executive authority | Final override, exception approval |
| Governance lead | Full create/review/approve |
| Product owner | Submit request, respond to gaps |
| Department requester | Submit and track |
| Architect | Review mapped architecture obligations |
| AI governance reviewer | Review AI obligations |
| Auditor | Read-only, audit export |
| Student / participant | No direct approval access |

**Automated pre-checks**

- Duplicate request detection against Product Registry and Prompt Registry

- Mandatory constitutional mapping completed

- DUDOS alignment status present for institutional flows

- EADC compliance checklist completed for AI-enabled flows

- Required approvers assigned

- Conflict-of-interest flag for competition / judge scenarios

**Evidence requirements**

- Request justification

- Current-state document or reference

- Intended business or academic outcome

- Risk statement

- Ownership assignment

- Previous solution search result

**Validation rules**

- No development pathway if constitutional mapping is blank

- No AI deployment pathway if AI governance profile is missing

- No release if exception is active without expiry and owner

- No competition approval without participant and judge templates attached

**KPIs**

- Governance-first compliance rate

- Requests blocked before unmanaged development starts

- Exception volume and ageing

- Average approval lead time

- Duplicate requests prevented

- Audit completeness rate

**Master prompt**

Act as the Global Chief Governance Officer, Chief Technology Officer, Chief AI Officer, Chief Product Officer, Chief Academic Innovation Officer and Enterprise Audit Director of DAIOS.

Identity
You are the DAIOS Governance and Constitution Orchestrator.

Mission
Your mission is to evaluate every incoming software, AI, automation, dashboard, competition, research, student project, faculty innovation, integration and rollout request against the DAIOS Constitution, EADC, DUDOS, institutional policies, accreditation rules and enterprise governance controls before any work proceeds.

Context
Use these governing references in priority order:
1. [CONSTITUTION_RULESET]
2. EADC
3. DUDOS
4. DAIOS Operating Model
5. Enterprise RACI Matrix
6. Decision Rights Matrix
7. AI Governance Handbook
8. Product Registry
9. Knowledge Vault
10. Prompt Registry
11. [ACCREDITATION_RULESET]
12. [SECURITY_RULESET]

Analysis Requirements
For the submitted request:
- classify the request type
- determine whether it is academic, internal, institutional, commercial or hybrid
- map all applicable constitutional clauses and policies
- identify missing approvals, missing owners and missing evidence
- detect duplication, overlap and non-standard requests
- determine architecture review, AI review, security review, PMO review and release review requirements
- assess whether the request is blocked, conditionally approved, approved for analysis only, or approved for controlled development

Output Requirements
Generate:
- executive summary
- constitutional mapping table
- approval matrix
- risk and exception table
- missing inputs list
- decision: Reject / Hold / Approve for Analysis / Approve for Documentation / Approve for Controlled Development
- next mandatory actions
- audit log entry text
- dashboard status update

Governance Rule
Do not allow any request to proceed to documentation, development, pilot or deployment if constitutional mapping, ownership, evidence, approvals and required reviews are incomplete.
Apply the principle: Governance Before Scale.

**Execution example**

Input package:
Request type: Department automation
Department: Registrar
Problem: Complaint backlog, manual Excel tracking, duplicate approvals
AI capability requested: AI assistant + queue triage
Data class: Student + confidential
Target outcome: Reduce response time from 5 days to 1 day

### Intake and Diagnosis module

**DPOS entry**

| Field | Value |
|---|---|
| Prompt ID | P01-INTAKE-DIAGNOSIS-ANALYSER-V1.0 |
| Owner | Business Analysis Office / Process Excellence Office |
| Purpose | Capture departmental pain points, current workflows, backlog, complaint sources, tracker artefacts, manual dependencies and automation opportunities |
| Risk level | High |
| Trigger | Any department requesting automation, diagnostics, re-engineering or system enhancement |
| Primary outputs | Current-state map, pain analysis, queue and complaint analysis, automation opportunity map, duplication report |
| Review cycle | Monthly by default; weekly for active pilots |

**What this module must do**

P01 is the translation engine between messy operational reality and structured automation planning. It should ask departments what they do today, what sheets they maintain, what approvals cause delay, what complaints recur, what queues accumulate, where follow-up pressure comes from, and where person-dependency creates chaos. This is the module that turns devotion without system into diagnosable process architecture. It also operationalises your instruction that the same intake model should work for students, faculty, departments and business units so repeated work is avoided.

This approach aligns with PMI’s emphasis on structured business analysis and value delivery, and with ISO/IEC/IEEE 12207 and 15288, which both regard requirements identification, stakeholder involvement and process control as foundational rather than optional.

**Sample intake screen fields**

| Group | Fields |
|---|---|
| Request identity | Department, business unit, contact person, process owner, escalation owner |
| Problem statement | Main problem, symptoms, when pressure appears, who complains, business impact, academic impact |
| Current workflow | Step list, approval path, service SLA, queue source, exceptions, rework points |
| Artefact inventory | Excel files, Google Sheets, forms, email threads, WhatsApp groups, physical registers, PDFs |
| Complaint diagnostics | Complaint types, complaint volume, peak times, unresolved ratios, root causes |
| Manual dependency | Key people, single points of failure, unavailable knowledge, undocumented handoffs |
| Data profile | Data types, sensitivity, sources, downstream systems |
| Desired future state | Target turnaround, automation goals, integration needs, dashboard needs, AI expectations |
| Evidence uploads | Existing forms, tracker sheets, SOPs, screenshots, reports, complaints log |

**Core entities**

IntakeRequest, DepartmentProfile, ProcessStep, PainPoint, ComplaintCategory, QueueMetric, TrackerArtifact, ManualDependency, CurrentStateReport, FutureStateIntent, AutomationCandidate.

**APIs, events and webhooks**

- POST /intake/submit

- POST /intake/artifact/upload

- GET /intake/{id}/diagnosis

- Event: intake.submitted

- Event: diagnosis.completed

- Webhook: documentation.requested

- Webhook: duplicate.solution.found

**RBAC**

| Role | Permissions |
|---|---|
| Department submitter | Create, edit own request |
| Business analyst | Review, interview, enrich |
| Governance lead | View and block if incomplete |
| Architect | View technical implications |
| Data steward | Review source data and sensitivity |
| Student intern | Restricted analyst support only |
| Chairman dashboard viewer | Read summary only |

**Automated pre-checks**

- Search existing DAIOS modules for similar process

- Search Knowledge Vault for prior SOPs, student projects, faculty work, dashboards

- Flag missing baseline metrics

- Flag missing issue evidence

- Flag contradictory goals

- Flag non-automation problem masquerading as software requirement

**Validation rules**

- At least one current artefact must be uploaded or described

- At least one measurable pain point must be quantified

- At least one process owner must be assigned

- Queue/complaint fields mandatory if backlog claimed

- “Need AI” cannot be selected without use-case description

**Evidence requirements**

- Current form / register / tracker

- Complaint samples or queue logs

- Existing SOP or policy

- Escalation examples

- Volume, time, or service-delay evidence

**KPIs**

- Intake completeness score

- Diagnostic turnaround time

- Duplicate solution discovery rate

- Artefact coverage rate

- Measurable pain-point capture rate

- Automation-opportunity quality score

**Master prompt**

Act as the Chief Business Analyst, Chief Process Architect, Chief Governance Officer, Chief AI Opportunity Analyst and Department Automation Intake Director of DAIOS.

Identity
You are the DAIOS Intake and Diagnosis Analyser.

Mission
Your mission is to convert any departmental, academic or business-unit automation request into a structured and evidence-backed current-state diagnosis that reveals pain points, queues, complaints, manual trackers, hidden dependencies, duplication and automation opportunities.

Context
Use:
- [CONSTITUTION_RULESET]
- DAIOS Operating Model
- DUDOS process map
- Product Registry
- Knowledge Vault
- Prompt Registry
- Department service catalog
- [MODULE_INTEGRATION_MAP]

Analysis Requirements
For the submitted department or unit:
- map the current workflow step by step
- identify all manual trackers, Excel sheets, forms, email or chat dependencies
- classify complaints, bottlenecks, delays, queues and escalation triggers
- identify person dependencies and undocumented handoffs
- estimate volume, time loss, rework and risk
- detect whether an existing DAIOS product or module can already solve all or part of the problem
- recommend whether the next step is reuse, improvement, integration or new build
- identify what documentation is needed to move into P03

Output Requirements
Generate:
- executive diagnosis summary
- current-state workflow
- pain point table
- queue and complaint analysis
- manual tracker inventory
- people-dependency analysis
- duplicate-solution check
- future-state recommendation
- required evidence still missing
- exact documentation package needed for next phase

Governance Rule
Do not recommend new system development unless the request has passed duplication search and the current-state diagnostic has evidence, measurable pain points and identified ownership.
Apply the principle: Search First, Reuse Second, Build Third.

**Execution example**

Analyse the Registrar Office automation intake.
Inputs:
- 7 Excel trackers
- approvals through email and paper
- 120 weekly complaints
- average response time 4.8 days
- three staff members acting as knowledge bottlenecks
- request for dashboard and AI assistant
Return:
- current-state diagnosis
- duplication review against Central Dashboard and Registrar modules
- documentation pack required for P03

## Documentation and architecture modules

### Documentation generation module

**DPOS entry**

| Field | Value |
|---|---|
| Prompt ID | P03-DOCUMENTATION-GENERATOR-V1.0 |
| Owner | Product Office / Documentation Office |
| Purpose | Generate and complete governed artefacts before coding |
| Risk level | Critical |
| Trigger | Governance-approved and diagnosed request entering formal engineering |
| Primary outputs | Product Registration, DAD, MPIF, BRD, SRS, ERD, API spec, test cases, release notes, SOP pack |
| Review cycle | Every artefact version; mandatory on change request |

**What this module must do**

P03 is the practical embodiment of “No documentation = no demonstration”. It must generate and maintain the full evidence chain required before coding, integration, pilot or release. ISO/IEC/IEEE 12207 explicitly notes that software life-cycle processes need defined information items; ISO/IEC/IEEE 15288 treats information exchange as a core system-life-cycle need; ISO/IEC 25010 provides the quality lens that requirements and tests should map to. NIST SSDF reinforces that secure development requires structured artefacts and traceable practices, not only source code.

**Required screens and fields**

| Screen | Critical fields |
|---|---|
| Product registration | Product name, owner, business value, user class, maturity level, internal/external use, revenue intent |
| DAD / MPIF | architecture pattern, module boundaries, integrations, MVP scope, exclusions, constraints |
| BRD / SRS | problem, business rules, non-functional requirements, user stories, acceptance criteria |
| ERD / API | entities, relationships, identifiers, retention, APIs, auth, payload examples |
| Test and release | test scenarios, UAT cases, release gates, cutover plan, rollback plan |
| SOP pack | operational steps, roles, escalation, dashboards, backup procedures |

**Core entities**

ProductRecord, DADDocument, MPIFRecord, BRDDocument, SRSDocument, ERDModel, APISpec, TestCase, ReleaseNote, SOPPack, DocumentVersion, EvidenceLink.

**APIs, events and webhooks**

- POST /docs/generate

- GET /docs/package/{requestId}

- POST /docs/version

- Event: document.generated

- Event: document.approved

- Webhook: coding.blocked.missing_docs

- Webhook: architecture.review.ready

**RBAC**

| Role | Permissions |
|---|---|
| Product owner | Edit business artefacts |
| Business analyst | Draft BRD/SRS |
| Architect | Edit DAD/API/ERD |
| QA lead | Edit tests and DoD |
| Governance lead | Approval |
| Developer | Read-only until approval |
| Student documentation role | Draft support only, no final approval |

**Automated pre-checks**

- Product Registration exists

- DAD exists

- MPIF exists

- BRD and SRS not empty

- ERD and API spec aligned

- Security classification linked

- Test skeleton created

- Version control metadata present

**Validation rules**

- No coding task if Product Registration, DAD, MPIF, BRD or SRS is missing

- No API build if API spec missing

- No schema implementation if ERD missing

- No release if test cases or release notes missing

- No operational rollout if SOP pack missing

**Evidence requirements**

- Approved document package

- Traceability matrix from requirement to test

- Integration inventory

- Security and privacy notes

- Knowledge Vault archival link

**KPIs**

- Documentation completeness score

- Pre-code document compliance rate

- Change traceability coverage

- Requirement-to-test traceability rate

- Release-note completeness rate

**Master prompt**

Act as the Global Chief Product Officer, Chief Business Analyst, Chief Systems Architect, Chief Documentation Officer, Chief QA Officer and Governance Controller of DAIOS.

Identity
You are the DAIOS Documentation Generation Orchestrator.

Mission
Your mission is to generate the full governed documentation package required before any coding, integration, testing, pilot or release work begins.

Context
Use:
- [CONSTITUTION_RULESET]
- EADC
- DAIOS Operating Model
- Product Registry
- Knowledge Vault
- Prompt Registry
- AI Governance Handbook
- [EVIDENCE_PROFILE]
- [MODULE_INTEGRATION_MAP]

Analysis Requirements
Based on the approved intake and governance outputs:
- generate Product Registration
- generate DAD and MPIF
- generate BRD and SRS
- generate ERD and API specification
- generate test cases and Definition of Done
- generate release note structure and SOP pack
- identify missing source inputs and contradictions
- map requirements to quality, security, AI and integration obligations

Output Requirements
Generate:
- complete documentation pack
- missing information matrix
- assumptions register
- traceability matrix
- reviewer checklist
- approval workflow
- final readiness decision for coding

Governance Rule
Do not mark the module ready for coding unless Product Registration, DAD, MPIF, BRD, SRS, ERD, API specification, test skeleton and document version metadata all exist and pass validation.
Apply the principle: Documentation Before Development.

**Execution example**

Generate the full documentation pack for:
Product: Registrar Service Automation
Use case: complaint resolution, status tracking, AI queue triage
Integrations: Student360, Central Dashboard, Notification Service, DUDOS
Need outputs: Product Registration, DAD, MPIF, BRD, SRS, ERD, API spec, UAT cases, SOP pack

### Architecture and engineering module

**DPOS entry**

| Field | Value |
|---|---|
| Prompt ID | P04-ARCHITECTURE-ENGINEERING-REVIEW-V1.0 |
| Owner | CTO Office / Architecture Review Board |
| Purpose | Review enterprise architecture, SaaS readiness, API design, multi-tenancy, DevOps, observability and environment planning |
| Risk level | Critical |
| Trigger | Approved documentation pack ready for technical design |
| Primary outputs | Architecture review decision, integration pattern, environment plan, operational readiness plan |
| Review cycle | Before build, before pilot, before major release |

**What this module must do**

P04 ensures that no isolated, hard-coded, one-department software enters DAIOS. It should force architecture patterns consistent with your open-architecture principle, reusable APIs, tenant-aware design, integration contracts, security by design, and operational observability. ISO/IEC 25010 gives the quality model; ISO/IEC 27001 and cloud-security standards shape security expectations; NIST SSDF and OWASP ASVS give software-security verification discipline; TOGAF gives the reusable EA framing for architecture assets and governance.

**Architecture review controls**

| Review area | Required decision |
|---|---|
| Deployment model | shared service / single tenant / multi-tenant / hybrid |
| Integration model | API / event bus / plugin / SSO / transitional |
| Data model | master entities, ownership, data lineage, retention |
| Security model | authN/authZ, secrets, encryption, logs, backup |
| Environment plan | dev, test, staging, prod, DR |
| Observability | metrics, logs, traces, alerts |
| Performance | target load, concurrency, scale policy |
| Reuse | existing components, shared UI, shared services, shared agents |

**Core entities**

ArchitectureReview, IntegrationContract, TenantModel, EnvironmentPlan, DevOpsPlan, ObservabilitySpec, SecurityControlSet, PerformanceProfile, ReuseDecision, ARBDecision.

**APIs, events and webhooks**

- POST /architecture/review

- GET /architecture/{productId}/readiness

- Event: architecture.approved

- Event: architecture.rework.required

- Webhook: devops.plan.required

- Webhook: shared.component.reuse.required

**RBAC**

| Role | Permissions |
|---|---|
| CTO / ARB chair | Final architecture approval |
| Enterprise architect | Full technical review |
| Security architect | Security approval |
| DevOps lead | Environment and delivery-plan approval |
| Data architect | Data-model approval |
| Product owner | Respond to findings |
| Developer | Read/comment only |

**Automated pre-checks**

- Existing component reuse scan

- Multi-tenant readiness check if commercial or cross-unit product

- API naming/versioning conventions check

- Security baseline check

- Environment segmentation check

- Logging/monitoring presence check

- Central Dashboard compatibility check

**Validation rules**

- No production approval without environment plan

- No integration approval without contract or spec

- No external deployment without auth and audit model

- No SaaS label without tenancy and lifecycle controls

- No mobile release without MASVS-aligned review if mobile app involved

**Evidence requirements**

- Approved DAD, ERD, API spec

- Reuse map

- Infra diagram

- Security control mapping

- Non-functional targets

- Runbook draft

**KPIs**

- Architecture-first compliance rate

- Reuse ratio

- Shared component adoption rate

- API governance compliance

- Observability readiness score

- Production incident reduction

**Master prompt**

Act as the Global CTO, Chief Enterprise Architect, Chief Security Architect, Chief DevOps Architect and Architecture Review Board Chair of DAIOS.

Identity
You are the DAIOS Architecture and Engineering Review Orchestrator.

Mission
Your mission is to determine whether a proposed DAIOS module is enterprise-ready, reusable, secure, scalable, SaaS-capable where required, and properly prepared for delivery and operations.

Context
Use:
- [CONSTITUTION_RULESET]
- DAIOS Master Blueprint
- approved DAD, MPIF, BRD, SRS, ERD and API spec
- Product Registry
- Knowledge Vault
- [SECURITY_RULESET]
- [MODULE_INTEGRATION_MAP]
- [RELEASE_PROFILE]

Analysis Requirements
Analyse:
- enterprise architecture fit
- reuse and non-duplication opportunities
- API quality and integration model
- data model and master-data impact
- single-tenant vs multi-tenant strategy
- security and privacy controls
- DevOps and environment readiness
- observability and support readiness
- scalability, resilience and rollback readiness

Output Requirements
Generate:
- architecture decision summary
- approved target architecture
- integration recommendations
- reuse obligations
- environment plan
- observability plan
- security findings
- rework items
- build readiness decision

Governance Rule
Do not approve build or deployment if the architecture is isolated, duplicated, hard-coded for one department, missing integration contracts, or missing security and observability controls.
Apply the principle: Open Architecture, Governed Reuse, No Isolated Systems.

**Execution example**

Review architecture for:
Module: Admission Test Portal
Scope: multi-campus, multi-university capable, payment, question engine, dashboard, reporting
Need verdict on:
- multi-tenant readiness
- API integration with Admission, Payment, Central Dashboard, Product Registry
- security and observability requirements

## AI engineering and delivery modules

### AI and agent engineering module

**DPOS entry**

| Field | Value |
|---|---|
| Prompt ID | P05-AI-AGENT-ENGINEERING-ORCHESTRATOR-V1.0 |
| Owner | Chief AI Office |
| Purpose | Design personas, prompts, agents, model routing, guardrails, evaluation, hallucination review and cost governance |
| Risk level | Critical |
| Trigger | Any AI assistant, agent, recommendation engine, conversational layer, automation or model-enabled workflow |
| Primary outputs | Persona spec, prompt spec, guardrail plan, eval plan, cost model, model-routing decision |
| Review cycle | Before pilot, monthly after release, immediate after incident |

**What this module must do**

P05 is the control room for all AI usage inside DAIOS. It should maintain persona libraries, approved prompt variants, routing rules, escalation-to-human rules, cost and latency policies, hallucination logging, safety testing, and agent-to-agent orchestration controls. This is where DCIP, central AI, domain assistants and virtual executive roles can safely live.

ISO/IEC 42001 is central because it is an AI management-system standard. NIST AI RMF adds trustworthy-AI governance. NIST SP 800-218A extends secure development practices specifically to AI model development. OWASP AISVS gives testable security requirements for AI-enabled systems, while ASVS remains important for the application layer and MASVS matters if mobile AI apps are involved.

**Required screens and fields**

| Screen | Critical fields |
|---|---|
| Persona registry | Persona name, audience, goal, knowledge sources, permissions, escalation rules |
| Prompt registry | Prompt ID, owner, purpose, inputs, outputs, model route, temperature, guardrails |
| Evaluation console | Test set, expected result, risk category, hallucination score, human pass/fail |
| Cost and routing | Provider, model, max token cost, latency target, fallback chain |
| Incident and audit | unsafe output, hallucination case, policy breach, rollback, fix version |

**Core entities**

AIPersona, PromptAsset, AgentDefinition, GuardrailPolicy, ModelRoute, EvalSuite, EvalRun, HallucinationIncident, CostProfile, SafetyCase, HumanEscalationRule, AIApprovalRecord.

**APIs, events and webhooks**

- POST /ai/persona

- POST /ai/prompt/publish

- POST /ai/evaluate

- POST /ai/route/decision

- Event: ai.eval.failed

- Event: ai.cost.threshold.exceeded

- Webhook: human.review.required

- Webhook: prompt.duplicate.detected

**RBAC**

| Role | Permissions |
|---|---|
| Chief AI Officer | Final publish / block |
| Prompt engineer | Draft and update prompts |
| Security reviewer | Evaluate AI safety and data usage |
| Domain owner | Approve persona knowledge and business intent |
| Data steward | Approve knowledge sources |
| Developer | Integrate approved prompts only |
| Student contributor | Draft in sandbox only |

**Automated pre-checks**

- Prompt duplication check

- Restricted data source check

- Missing evaluation suite check

- Missing human escalation rule

- Missing cost ceiling

- Missing audit metadata

- High-risk use-case flag

**Validation rules**

- No production AI persona without owner, knowledge list, permissions and eval results

- No AI prompt publication without version and approval state

- No high-risk AI use without human-in-the-loop rule

- No external-facing assistant without content-source verification and safety review

- No model routing change without recorded reason and rollback path

**Evidence requirements**

- Persona specification

- Prompt text and version metadata

- Evaluation results

- Safety and hallucination review

- Cost profile

- Human escalation rule

- Audit trail and approval record

**KPIs**

- Prompt reuse rate

- Hallucination incident rate

- Human escalation rate

- AI answer accuracy

- Cost per resolved interaction

- Prompt approval lead time

- Persona adoption rate

**Master prompt**

Act as the Chief AI Officer, Principal Prompt Architect, Enterprise Agent Engineer, AI Governance Lead, Security Reviewer and Cost Optimisation Director of DAIOS.

Identity
You are the DAIOS AI and Agent Engineering Orchestrator.

Mission
Your mission is to design, review, govern and approve every AI persona, prompt, agent and model-routing rule used across DAIOS so that outputs are safe, traceable, explainable, reusable, cost-aware and aligned with governance.

Context
Use:
- [CONSTITUTION_RULESET]
- AI Governance Handbook
- Prompt Registry
- Knowledge Vault
- Product Registry
- [AI_MODEL_POLICY_EXT]
- [SECURITY_RULESET]
- [MODULE_INTEGRATION_MAP]

Analysis Requirements
For the proposed AI capability:
- define the persona, users, permissions and knowledge sources
- draft the prompt and required structured inputs
- propose model routing, fallback and cost thresholds
- define guardrails and prohibited behaviours
- define evaluation tests, hallucination checks and human escalation rules
- classify risk and data sensitivity
- determine whether the request should be sandboxed, piloted, approved or blocked

Output Requirements
Generate:
- persona specification
- prompt specification
- model routing table
- evaluation plan
- guardrail policy
- cost and latency profile
- approval status
- monitoring requirements
- dashboard metrics

Governance Rule
Do not approve any AI prompt, persona or agent for production without evaluation evidence, ownership, approved knowledge sources, guardrails, cost policy, auditability and human-escalation rules where applicable.
Apply the principle: Controlled AI, Measurable AI, Reusable AI.

**Execution example**

Design and review an Admission Assistant persona.
Knowledge sources: Admission policy, FAQs, fee rules, intake calendar
Channels: Web chat, WhatsApp, Central AI
Languages: English and Bangla
Need:
- approved prompt
- routing plan
- hallucination controls
- escalation to admission officers
- cost thresholds

### Delivery and PMO module

**DPOS entry**

| Field | Value |
|---|---|
| Prompt ID | P06-DELIVERY-PMO-EXECUTION-ORCHESTRATOR-V1.0 |
| Owner | PMO / Transformation Office |
| Purpose | Translate approved architecture into governed execution, release control, reporting, risk management, change management and no-people-dependency delivery |
| Risk level | Critical |
| Trigger | Build-ready module with architecture and AI approvals in place |
| Primary outputs | Delivery plan, sprint structure, weekly reporting, risk register, release plan, acceptance evidence |
| Review cycle | Daily stand-up, weekly governance, sprint review, release review, monthly executive review |

**What this module must do**

P06 is the execution spine. It is where your “ruthless execution-focused transformation office” operates. Its job is not to redesign DAIOS; it is to get governed modules delivered in the right order with minimum confusion, minimum person dependency and maximum reuse. PMI’s current PMBOK guidance is now explicitly value-delivery oriented and includes expanded coverage of AI and PMOs; organisational project management guidance is directly relevant where multiple departments and platforms must align. CMMI’s maturity framing is useful here because it provides the logic for moving from fragmented execution to quantitatively managed and optimising delivery capability.

**Required screens and fields**

| Screen | Critical fields |
|---|---|
| Execution plan | module, dependency order, owner, duration, deliverables, governance gates |
| Sprint / tasking | epic, feature, user story, task, acceptance criteria, DoD, evidence link |
| Weekly governance | planned vs actual, blockers, risk, decisions needed, approvals pending |
| Release control | release candidate, change set, rollback plan, migration notes, training status |
| Risk and dependency | risk ID, probability, impact, mitigation, owner, due date |
| People-dependency review | undocumented knowledge points, shadow owner, SOP coverage, automation gap |

**Core entities**

Epic, Feature, UserStory, Task, AcceptanceCriterion, DefinitionOfDone, Release, ChangeRequest, RiskItem, Dependency, StatusReport, TrainingRecord, OperationalHandover, PeopleDependencyFinding.

**APIs, events and webhooks**

- POST /delivery/plan

- POST /delivery/task

- POST /release/candidate

- POST /risk/register

- Event: quality.gate.failed

- Event: release.approved

- Event: scope.change.requested

- Webhook: chairman.review.required

**RBAC**

| Role | Permissions |
|---|---|
| PMO lead | Full plan and release control |
| Product owner | Scope and acceptance control |
| Engineering lead | Delivery execution updates |
| QA lead | Quality-gate control |
| DevOps lead | Release and deployment control |
| Governance lead | Compliance gate review |
| Student contributor | Assigned work only |
| Executive viewer | Read dashboards and decision packs |

**Automated pre-checks**

- Dependency order consistency

- Required documentation links present

- Architecture approval present

- AI approval present where relevant

- Test evidence present before release

- Change request created for scope modification

- Shadow owner assigned for key deliverables

**Validation rules**

- No sprint start without approved backlog and documentation links

- No release candidate without test and rollback evidence

- No scope change without change request and impact analysis

- No closure without knowledge-archive and SOP update

- No critical feature with a single undocumented owner

**Evidence requirements**

- Task acceptance evidence

- Test results

- Review minutes

- Release notes

- Change control decision

- Training and handover proof

- Knowledge Vault update

**KPIs**

- Planned vs actual delivery accuracy

- Governance gate pass rate

- Scope-change rate

- Lead time to MVP

- Release rollback rate

- Knowledge capture completion rate

- People-dependency reduction score

**Master prompt**

Act as the Global Chief Program Manager, PMO Director, Chief Product Delivery Officer, Chief Governance Controller, Chief QA Officer and Release Management Director of DAIOS.

Identity
You are the DAIOS Delivery and PMO Execution Orchestrator.

Mission
Your mission is to convert approved DAIOS designs into a controlled delivery plan with the correct build order, task structure, reporting cadence, release gates, risk controls, knowledge preservation and minimum people dependency.

Context
Use:
- [CONSTITUTION_RULESET]
- DAIOS Operating Model
- Enterprise Service Catalog
- Enterprise RACI Matrix
- Decision Rights Matrix
- approved Product Registration, DAD, MPIF, BRD, SRS, ERD, API spec and architecture decision
- Prompt Registry
- Knowledge Vault
- [RELEASE_PROFILE]
- [METRIC_PROFILE]

Analysis Requirements
Generate:
- dependency-aware implementation sequence
- epic and feature breakdown
- user stories, tasks and acceptance criteria
- Definition of Done
- weekly reporting model
- risk register
- release and change management plan
- people-dependency analysis
- student participation model where allowed
- dashboard reporting requirements

Output Requirements
Produce:
- executive delivery summary
- exact implementation order
- MVP roadmap
- weekly governance cadence
- risk and mitigation table
- release gates
- immediate next actions
- chairman review points

Governance Rule
Do not allow execution to proceed in parallel where dependencies exist. Do not allow release without evidence, quality-gate clearance, rollback plan, knowledge-archive update and handover readiness.
Apply the principle: System Before People, Delivery With Governance.

**Execution example**

Create the execution plan for DAIOS Phase 1 MVP.
Included modules:
P00, P01, P03, P04, P05, P06 foundations plus Product Registry, Knowledge Vault, Prompt Registry and Central Dashboard integration.
Need:
- exact build order
- team structure
- weekly reporting
- 16-week roadmap
- quality gates
- people-dependency review

## Cross-cutting controls, teams and roadmaps

A single consolidated DPOS registry should exist for the six modules from day one.

| Module | Registry ID | Primary owner | Highest-risk gate |
|---|---|---|---|
| Governance and Constitution | P00 | Governance Office | Approval and exception control |
| Intake and Diagnosis | P01 | Business Analysis Office | Bad requirements and duplicate work |
| Documentation Generation | P03 | Product Office | Coding without artefacts |
| Architecture and Engineering | P04 | CTO / ARB | Isolated or non-scalable architecture |
| AI and Agent Engineering | P05 | Chief AI Office | Unsafe or uncontrolled AI use |
| Delivery and PMO | P06 | PMO | Execution chaos and people dependency |

A minimal but viable team should look like this:

| Role | Minimal | Ideal | Main responsibility |
|---|---|---|---|
| Product owner | 1 | 2 | Business scope and acceptance |
| Governance lead | 1 | 1 | P00 control and compliance |
| Business analyst | 1 | 2–3 | P01 diagnostics and requirements |
| Documentation lead | 1 | 2 | P03 artefacts and traceability |
| Enterprise architect | 1 | 1–2 | P04 architecture and reuse |
| AI lead / prompt architect | 1 | 2 | P05 prompts, agents and evaluations |
| Backend engineers | 2 | 4–6 | Services, APIs, integrations |
| Frontend engineers | 1 | 2–3 | UI and workflow screens |
| QA / test lead | 1 | 2 | Quality gates and evidence |
| DevOps / platform | 1 | 2 | Environments, observability, release |
| Knowledge manager | 1 | 1 | Knowledge Vault, archival discipline |
| PMO lead | 1 | 1 | P06 execution control |
| Student contributors | 2–4 | 8–15 | Controlled documentation, testing, research |

A working RACI summary should be fixed now:

| Deliverable | Product owner | Governance | BA | Architect | AI lead | QA | DevOps | PMO | Knowledge mgr |
|---|---|---|---|---|---|---|---|---|---|
| P00 assessment | C | A/R | C | C | C | I | I | I | I |
| P01 diagnosis | A | C | R | C | C | I | I | I | C |
| P03 documentation pack | A | C | R | R | C | C | I | I | C |
| P04 architecture decision | C | C | C | A/R | C | C | C | I | I |
| P05 AI approval | C | C | I | C | A/R | C | I | I | C |
| P06 delivery plan | A | C | C | C | C | C | C | R | I |
| Knowledge archival | I | I | C | C | C | I | I | I | A/R |

**Pilot recommendation**

Run one integrated pilot, not six disconnected pilots. Use one real departmental request with measurable pain, plus one academic/competition flow to test DACJE alignment.

**Suggested pilot**

- Core business pilot: Registrar or Admission automation request

- Academic pilot: competition/capstone submission pathway with participant and judge templates

- AI pilot: one single approved persona such as Admission Assistant or Registrar Queue Assistant

- Dashboard pilot: one cross-module governance dashboard into the Chairman Command Center

**Pilot checklist**

| Check | Pass criterion |
|---|---|
| P00 live | Governance decision generated before any work item is opened |
| P01 live | Intake form completed with artefacts and diagnostics |
| P03 live | Full documentation pack produced and approved |
| P04 live | ARB decision created with integration and reuse obligations |
| P05 live | Persona/prompt approved with evaluation results |
| P06 live | Delivery plan, risk register and release gates active |
| Integrations live | Product Registry, Knowledge Vault, Prompt Registry, Central Dashboard connected |
| Auditability | Each step has timestamp, owner and evidence |
| Non-duplication | System flags existing related artefacts and modules |
| Knowledge capture | Closure updates pushed into Knowledge Vault |

**Acceptance criteria for constitutional freeze**

DAIOS is ready to freeze for implementation only when all of the following are true:

- Every requested P-module has an approved master prompt and registry entry

- One canonical DPOS taxonomy exists and prompt IDs are versioned

- No prompt can be executed without owner, version, scope and approval state

- P00 is technically enforced as the first gate

- P03 blocks coding when artefacts are missing

- P04 blocks deployment when architecture and security are incomplete

- P05 blocks AI release when evaluations and guardrails are missing

- P06 blocks closure when knowledge archival is incomplete

- Product Registry, Knowledge Vault, Prompt Registry and Central Dashboard are integrated

- A pilot has produced evidence that prompts are reusable and not person-dependent

**Ninety-day roadmap**

| Period | Outcome |
|---|---|
| Days 1–15 | Finalise DPOS taxonomy, prompt IDs, registry schema, P00–P06 prompt approval |
| Days 16–30 | Build P00 and P01 screens, entities and workflow; connect Product Registry and Knowledge Vault |
| Days 31–45 | Build P03 document engine and approval states; enforce no-code-without-docs rule |
| Days 46–60 | Build P04 architecture review workspace, integration checklist and ARB dashboard |
| Days 61–75 | Build P05 persona/prompt registry, evaluation console and guardrail workflow |
| Days 76–90 | Build P06 execution dashboard, release gates and chairman view; run integrated pilot |

**One-hundred-and-eighty-day roadmap**

| Period | Outcome |
|---|---|
| Months 4–5 | Expand integrations to Student360, Registrar, Admission, Revenue OS, Marketplace, Central AI |
| Month 5 | Roll out participant and judge templates into DACJE-linked competition workflow |
| Month 6 | Enable multi-channel execution telemetry, prompt-performance dashboards and department onboarding packs |

**Top risks and mitigations**

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Departments bypass P00 | High | High | Make P00 mandatory for ticket creation and funding approval |
| Over-designed prompts with poor usability | Medium | High | Pilot with two real departments before full rollout |
| Duplicate modules continue outside registry | High | High | Block development requests without Product Registry ID |
| AI prompts drift over time | Medium | High | Versioning, evaluation suites and monthly prompt audit |
| Documentation becomes a paper exercise | Medium | High | Tie P03 outputs directly to build, test and release gates |
| Architecture approvals slow delivery | Medium | Medium | Use standard patterns and pre-approved archetypes |
| Students create unmanaged artefacts | Medium | Medium | Sandbox role, mentor approval and registry-first participation |
| Cost explosion from AI usage | Medium | High | Model-routing policy, budget ceilings and per-prompt cost telemetry |
| Dashboard data becomes inconsistent | Medium | High | Master data ownership and event-driven updates |
| People dependency persists | High | High | Shadow owners, SOP coverage, Knowledge Vault closure requirement |

A final note on security and verification: for web applications use OWASP ASVS as the minimum verification yardstick; for AI-enabled systems include OWASP AISVS controls; for mobile applications include OWASP MASVS and related test guidance; for cloud-hosted modules align controls with ISO/IEC 27017 and privacy handling with ISO/IEC 27018. For AI governance and development, combine ISO/IEC 42001, NIST AI RMF and NIST SP 800-218A rather than relying on general application controls alone.

The practical conclusion is simple: if you freeze DAIOS now around this module sequence and these master prompts, future additions will not require rewriting the root logic. They will plug into the registries, integration maps, evidence profiles and policy extensions. That gives you the operating discipline you asked for: **no prompt lost, no knowledge lost, no duplicate work, no uncontrolled AI usage, and no product development without governance**.

ISO/IEC/IEEE 12207:2026 - Systems and software engineering — Software life cycle processes

The TOGAF® Standard, a Standard of The Open Group

ISO/IEC 42001:2023 - Intelligence artificielle – Système de management

The PMI Guide to Business Analysis | Project Management Institutue

ISO/IEC 25010:2023 - Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — Product quality model

PMBOK Guide | Project Management Institute

OWASP Application Security Verification Standard (ASVS) | OWASP Foundation
