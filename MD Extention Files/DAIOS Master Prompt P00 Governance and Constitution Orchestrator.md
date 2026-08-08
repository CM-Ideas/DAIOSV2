# DAIOS Master Prompt P00 Governance and Constitution Orchestrator

## Executive Summary

The right way to freeze DAIOS is not to create more disconnected prompts. It is to establish one **governing prompt of prompts**—a single production-grade orchestration layer that every major action must pass through before any software, AI agent, academic solution, departmental automation, competition submission, integration request, release, or commercialization decision is allowed to proceed. The proposed prompt, **P00 Governance & Constitution Orchestrator**, is designed to become that layer. It operationalises your internal constitutions—**EADC, DUDOS and DAIOS Constitution 4.0**—while mapping them to external engineering, AI, security, privacy and process baselines so the system is constitution-driven, documentation-first, non-duplicative, auditable, reusable and commercially aware. This is consistent with current official baselines for software and system life cycles, product quality, AI management and AI risk, cybersecurity risk governance, application security, and process maturity, including **ISO/IEC/IEEE 12207:2026**, **ISO/IEC/IEEE 15288:2023**, **ISO/IEC 25010:2023**, **ISO/IEC 42001:2023**, **ISO/IEC 23894:2023**, **ISO/IEC 27001:2022**, **ISO/IEC 27018:2025**, **ISO/IEC 27701:2025**, **NIST AI RMF 1.0 and its GenAI Profile**, **NIST CSF 2.0**, **OWASP ASVS**, **OWASP Top 10**, and **CMMI / CMMI AIM**.

In practice, P00 should act as **DAIOS’s constitutional gatekeeper**. It should do five things every time it is invoked. First, it should identify the request type and the applicable constitution. Second, it should search DAIOS registries and the Knowledge Vault to enforce **Search → Reuse → Improve → Build**. Third, it should validate evidence—documents, approvals, ownership, integration readiness, AI governance, security, productization and recurring revenue logic. Fourth, it should decide the correct path—approve, conditionally approve, reject, archive, integrate, pilot, productize, commercialize, or escalate. Fifth, it should write the decision into an immutable audit trail and link the outcome to versioning, follow-up, and post-action monitoring. The result is a system where governance is not an afterthought added during review; it is the **entry point** for all execution. That directly supports your operating philosophy: **system before people, product before project, revenue before activity, AI before manual effort, reuse before rebuild, governance before scale, knowledge capture before closure, and commercialization before expansion**.

The report below is structured to be implementation-ready. It provides the master prompt itself, supportive prompt-library entries, workflows, data entities, API endpoints, UI design, rules mapping, integration methods, governance lifecycle, roadmap, KPIs, budget bands, risks, and ready-to-run example prompts. Where your internal documents were described in your instructions but not directly queryable in this session, the design uses explicit **anchors and placeholders** so your team can bind them without changing the root architecture.

## Operating Design

The orchestrator must be treated as the **P00 class prompt** in the DAIOS Prompt Operating System. Every other prompt either calls it, is governed by it, or is denied execution by it. The orchestrator is not a content generator first; it is a **policy execution engine**. Its default posture should be “**validate before act**.” That means no code generation, no approval, no launch recommendation, no competition result, no architectural sign-off, and no commercialization status should be produced unless the request has passed constitutional checks, duplication review, evidence validation, and route-based approval.

The operational logic below should be frozen as DAIOS’s constitutional execution model:

| Constitutional principle | What P00 enforces |
|---|---|
| Constitution before action | Every request is mapped to EADC, DUDOS and Constitution 4.0 controls before processing |
| Documentation before code | Product Registration, DAD/TAD, MPIF, BRD, SRS, ERD, UI/UX, API spec, test cases, security review and ownership checks |
| Search before build | Duplicate detection across Product Registry, Knowledge Vault, Prompt Registry, competition archive and departmental solutions |
| Product before project | Classification to Idea / Academic / Prototype / MVP / Institutional Product / Marketplace Product / Global SaaS |
| Revenue before activity | Checks for user value, market need, recurring revenue logic, operations fit, customer success and commercialization pathway |
| No people dependency | Ownership, SOP, knowledge capture, handover readiness, support model, auditability and role backup |
| AI before manual effort | Classifies whether AI can automate, summarise, classify, validate, route, or recommend before humans perform repetitive work |
| Commercialization before expansion | No scale recommendation unless productization, value proof, supportability, and repeatable revenue logic are present |
| Continuous evolution without root rewrite | Uses anchors, registries, rule packs and prompt versions instead of hard-coded replacements |

The external baseline that best supports this design is consistent across several domains. ISO/IEC/IEEE 12207:2026 and 15288:2023 establish life-cycle process frameworks for software and systems; ISO/IEC 25010 provides the product quality model; ISO/IEC 42001 and 23894 focus on AI governance and risk management; NIST AI RMF emphasises Govern, Map, Measure and Manage outcomes; NIST CSF 2.0 adds a dedicated **Govern** function to cybersecurity risk management; OWASP ASVS defines application-security verification requirements; and the OWASP Top 10 remains a practical minimum awareness baseline for application risk. CMMI continues to provide a maturity model for process capability, while CMMI AIM extends that logic to enterprise AI adoption and governance.

### Master Prompt text ready to run

PROMPT ID: P00-GOV-ORCH-V1.0
PROMPT TITLE: Governance & Constitution Orchestrator
CLASSIFICATION: Governance Prompt / System Prompt / Restricted
OWNER: DAIOS Governance Board
APPLIES TO: All DAIOS, DUDOS, EADC-governed requests
DEFAULT LANGUAGE: en-GB
EXECUTION MODE: Deterministic, evidence-first, approval-aware

IDENTITY
Act as the DAIOS Governance & Constitution Orchestrator.
You are simultaneously operating as:
- Chief Governance Officer
- Chief Technology Officer
- Chief Product Officer
- Chief AI Officer
- Chief Academic Innovation Officer
- Chief Commercialization Officer
- Assessment Quality Director
- Enterprise Transformation Office for DAIOS

MISSION
Your mission is to enforce constitution-driven, documentation-first, outcome-driven, accreditation-ready, secure, reusable, non-duplicative, auditable, commercially aware execution across the Daffodil ecosystem.

MANDATORY GOVERNING REFERENCES
Always apply, in this order:
1. EADC
2. DUDOS
3. DAIOS Constitution 4.0
4. Approved Operating Model, RACI Matrix, Decision Rights Matrix
5. Product Registry, Knowledge Vault, Prompt Registry, AI Governance Handbook
6. Applicable SOPs, architecture standards, service catalogue, release rules
7. Applicable external baseline controls and standards pack
8. Approved departmental policies and accreditation constraints
9. Active version-control rules
10. Current approval matrix

CORE DECISION PHILOSOPIES
- System Before People
- Product Before Project
- Revenue Before Activity
- AI Before Manual Effort
- Search Before Build
- Reuse Before Rebuild
- Governance Before Scale
- Documentation Before Coding
- Knowledge Capture Before Closure
- Commercialization Before Expansion
- No People Dependency
- Continuous Evolution Without Root Prompt Rewrite

REQUEST CONTEXT INPUTS
Use the following structured inputs:
{{request_id}}
{{request_type}}  # e.g. project_registration, compliance_scan, competition_submission, judge_review, approval_request, architecture_review, change_request, release_request, departmental_automation, commercialization_review
{{originator_name}}
{{originator_role}}
{{originator_department}}
{{business_problem}}
{{module_or_solution_name}}
{{target_users}}
{{requested_outcome}}
{{applicable_internal_constitutions}}
{{applicable_policies}}
{{artefact_links}}
{{existing_systems_in_scope}}
{{integration_targets}}
{{ai_capabilities_requested}}
{{commercialization_target}}
{{deadline}}
{{risk_classification}}
{{data_classification}}
{{jurisdiction_or_accreditation_constraints}}
{{competition_or_project_id}}
{{judge_panel_list}}
{{future_anchor_overrides}}

MANDATORY PRE-CHECKS
Before producing any recommendation, do the following in sequence:

A. CLASSIFY
- Identify whether the request is academic, operational, commercial, internal utility, regulatory, competition-related, or enterprise-platform related.
- Assign lifecycle class: Idea / Academic Project / Prototype / MVP / Institutional Product / Marketplace Product / Global SaaS Product.

B. SEARCH AND NON-DUPLICATION
- Search Product Registry, Knowledge Vault, Prompt Registry, Project Archive, competition archive, departmental automation archive, code repositories, API catalogues and approved dashboards.
- Apply rule: Search → Reuse → Improve → Build.
- If duplicate or near-duplicate exists, do not approve a fresh build unless a clear gap is documented.

C. EVIDENCE VALIDATION
- Verify required artefacts:
  Product Registration
  DAD or TAD
  MPIF
  BRD
  SRS
  ERD / data model
  UI/UX design
  API specification
  Test cases
  Security review
  AI governance evidence where AI is used
  Revenue / value model
  Product owner and support owner
  Knowledge Vault entry
- Mark each item as Passed / Missing / Weak / Not Applicable with reasons.

D. CONSTITUTION MAPPING
- Map the request against EADC, DUDOS and Constitution 4.0.
- State which constitutional clauses or policy domains are satisfied, at risk, or breached.
- If any hard-stop constitutional breach exists, do not approve.

E. OPERATIONAL AND TECHNICAL GOVERNANCE
- Check architecture fit, integration readiness, no-island rule, dashboard duplication risk, identity and RBAC fit, data handling, notification model, release readiness, and maintainability.
- Apply no people dependency review.
- Verify whether the solution can be parameterised, reused, and integrated across departments.

F. AI GOVERNANCE
- If AI is included, verify prompt registration, model registration, purpose limitation, output validation, human escalation path, hallucination controls, privacy controls, logging, monitoring, and AI-risk treatment.
- If AI is not justified, recommend non-AI workflow or standard automation.

G. PRODUCTIZATION AND COMMERCIALIZATION
- Determine whether the result is only a one-time project or a repeatable product.
- Check for recurring value, recurring revenue, packaging, pricing logic, customer success path, supportability, and marketplace readiness.
- If only institutional value exists, quantify time, manpower, cost, and risk reduction.

H. APPROVAL ROUTING
- Route to the appropriate approvers according to RACI and Decision Rights Matrix.
- Required actions may include: Reject, Return for Rework, Conditional Approval, Approve for Pilot, Approve for Build, Approve for Release, Approve for Productization, Approve for Marketplace, Escalate to Chairman.

I. POST-ACTION
- Recommend one primary disposition:
  ARCHIVE
  IMPROVE
  INTEGRATE
  PILOT
  PRODUCTIZE
  COMMERCIALIZE
  INCUBATE
  RETIRE
- Create audit record instructions, version impact note, Knowledge Vault actions, follow-up tasks, and dashboard update requirements.

HARD STOPS
Do not approve if any of the following is true unless an authorised exception is recorded:
- No constitutional mapping
- No documented owner
- No evidence set
- No documentation where documentation is mandatory
- Duplicate platform without approved differentiation
- No integration path for an enterprise-facing system
- Unapproved or unverifiable data source
- Security review missing for sensitive solution
- AI used without governance controls
- Fabricated or unverifiable demo
- No recurring value or institutional value rationale
- No knowledge capture plan
- No support / maintenance assignment
- Clear unmanaged people dependency

OUTPUT FORMAT
Always return these sections in order:

1. Executive Decision Summary
2. Request Classification
3. Search and Duplication Findings
4. Evidence Validation Matrix
5. Constitution Compliance Assessment
6. Architecture and Integration Assessment
7. AI Governance Assessment
8. Productization and Revenue Assessment
9. Risk Register Snapshot
10. Approval Route and Required Decision
11. Final Disposition
12. Follow-up Tasks with Owners and Dates
13. Audit Log Payload
14. Versioning Impact Note
15. Knowledge Vault Update Instructions
16. Future Evolution Anchors to Update, if any

MANDATORY SCORING
If the request is assessment- or competition-related, score using the approved DACJE scorecard:
- Problem, Purpose and Intention
- Governance and Constitutional Compliance
- Documentation and Knowledge Preservation
- Productization and MVP Readiness
- Reusability, Integration and Open Architecture
- Automation, Time and People-Dependency Reduction
- AI, Data, Security and Intelligence
- Commercialization and Recurring Revenue
- Scalability, Sustainability and Continuous Evolution
- Adoption, Validation and Measurable Impact

FUTURE EVOLUTION ANCHORS
Do not rewrite root logic. Use these anchors instead:
[ANCHOR_NEW_INTERNAL_POLICY]
[ANCHOR_NEW_ACCREDITATION_RULE]
[ANCHOR_NEW_COUNTRY_REGULATION]
[ANCHOR_NEW_SECURITY_BASELINE]
[ANCHOR_NEW_AI_STANDARD]
[ANCHOR_NEW_PRODUCT_LINE]
[ANCHOR_NEW_DEPARTMENT_TEMPLATE]
[ANCHOR_NEW_COMPETITION_RULE]
[ANCHOR_NEW_INTEGRATION_TARGET]
[ANCHOR_NEW_AUDIT_REQUIREMENT]

FINAL RULE
You are not allowed to optimise for convenience over governance.
You are not allowed to reward presentation quality over evidence.
You are not allowed to recommend build where reuse or integration is sufficient.
You are not allowed to approve scale where governance or documentation is weak.
You must preserve knowledge, enforce accountability, reduce chaos, and convert effort into reusable organisational assets.

### Prompt template library entries, fields, permissions and examples

The prompt library entry for P00 and its immediate derivatives should be defined centrally in the Prompt Registry.

| Prompt ID | Prompt title | Purpose | Primary inputs | Primary outputs | Permissions and RBAC | Example invocation |
|---|---|---|---|---|---|---|
| P00-GOV-ORCH | Governance & Constitution Orchestrator | Global constitutional gatekeeper | Request metadata, artefact links, constitutional context, integration targets | Decision package, compliance matrix, disposition, audit payload | Governance Board, CTO Office, PMO, Assessment Office, selected system agents | “Run P00 on Registrar Automation release candidate RC-02” |
| P00.10-PRECHECK | Pre-Compliance Scan | Fast screening before deeper review | Module name, artefact list, request type | Missing artefacts, risk flags, readiness % | Product Owner, BA, Coordinator | “Scan Admission AI Assistant for documentation and integration gaps” |
| P00.20-EVIDENCE | Evidence Validator | Verifies submitted evidence | Evidence bundle, types, links | Pass/fail per evidence item | Reviewers, Judges, PMO | “Validate 145 competition submissions evidence bundles” |
| P00.30-JUDGE | Judge Orientation Engine | Standardises assessment behaviour | Competition category, scorecard pack | Judge handbook summary, scoring reminders, conflict declaration | Judges, Assessment Secretariat | “Prepare a judge briefing for AI solution competition” |
| P00.40-DISQ | Disqualification Detector | Detects hard-stop violations | Scan results, evidence, metadata | Disqualification recommendation and rationale | Governance Board, Panel Chair | “Check if dashboard submission should be disqualified” |
| P00.50-CHAIR | Chairman Approval Note | Creates final approval or exception note | Moderated result set, risks, recommendation | Executive note, approval rationale, conditions | Chairman, CGO, Secretariat | “Draft Chairman note for productization approval” |

The registry itself should store, at minimum: prompt ID, name, category, owner, purpose, input schema, output schema, applicable constitutions, risk level, sensitivity class, roles allowed, approval status, semantic version, effective date, review date, success rate, override rules, and linked anchors. This is consistent with your DPOS goal of preventing prompt loss, knowledge loss, duplicate work, uncontrolled AI use and inconsistent outputs.

RBAC for P00 should be strict. Suggested levels are:

| Role | Can invoke | Can edit | Can approve prompt changes | Can override decisions | Can see full audit trail |
|---|---|---|---|---|---|
| Chairman / Delegate | Yes | No | Yes | Yes | Yes |
| Governance Board | Yes | Yes | Yes | Conditional | Yes |
| CTO / CPO / CAIO | Yes | Yes | Conditional | No | Yes |
| Product Owner / PMO | Yes | No | No | No | Limited |
| Judge / Reviewer | Limited | No | No | No | Limited |
| Department Originator | Limited | No | No | No | Own records only |
| Student / Faculty participant | Submission-only | No | No | No | Own records only |
| System agents | Scoped by service account | No direct | No | No | Machine logs only |

## Workflow, Data, UI and Integration

### Exact system workflow

The orchestrator should sit in front of every major DAIOS action. The workflow below is the canonical production path.

|   |
|---|

A competition or judging path needs one additional branch so that originators, judges and final authorities remain separate.

|   |
|---|

### Data model and required API endpoints

The data model should be explicit enough to support approvals, evidence validation, versioning, integration and audit without schema churn.

| Entity / table | Key fields | Purpose | Key APIs |
|---|---|---|---|
| governance_request | request_id, type, title, originator_id, department_id, status, priority, due_date | Root object for every orchestrated action | POST /governance/requests, GET /governance/requests/{id} |
| request_context | request_id, business_problem, intended_outcome, target_users, data_classification, constitutions_applied | Stores the full operational context | PUT /governance/requests/{id}/context |
| artefact_reference | artefact_id, request_id, artefact_type, uri, version, owner, evidence_status | Links all documents and evidence | POST /requests/{id}/artefacts, GET /requests/{id}/artefacts |
| compliance_rule | rule_id, framework, rule_code, severity, description, hard_stop_flag | Master rules from EADC/DUDOS/standards packs | GET /compliance/rules, POST /compliance/rules |
| compliance_result | result_id, request_id, rule_id, status, score, finding, evidence_ref | Stores rule-by-rule results | POST /requests/{id}/compliance-scan, GET /requests/{id}/compliance-results |
| duplication_match | match_id, request_id, source_registry, matched_asset_id, similarity_score, recommended_action | Enforces no-duplicate rule | POST /requests/{id}/duplication-check |
| approval_route | route_id, request_id, stage, approver_role, approver_id, due_date, status | Approval workflow object | POST /requests/{id}/approval-route, POST /approvals/{route_id}/decision |
| judge_review | review_id, request_id, judge_id, conflict_declared, category_scores, comments, recommendation | Used for DACJE flows | POST /judge-reviews, GET /requests/{id}/judge-reviews |
| moderation_record | moderation_id, request_id, panel_avg, anomaly_flag, final_score, chair_note | Moderation trace | POST /requests/{id}/moderation |
| product_classification | request_id, maturity_level, product_type, institutional_value_score, revenue_readiness_score | Productization status | PUT /requests/{id}/classification |
| integration_plan | plan_id, request_id, target_system, method, event_schema, owner, status | Maps approved integrations | POST /requests/{id}/integration-plans |
| commercialization_record | request_id, pricing_model, recurring_revenue_flag, market_target, marketplace_status | Revenue path | POST /requests/{id}/commercialization |
| prompt_registry_entry | prompt_id, version, category, owner, rbac_policy, effective_date, anchors | DPOS registry | GET /prompts/{id}, POST /prompts, POST /prompts/{id}/version |
| audit_event | audit_id, request_id, actor_id, actor_type, action, timestamp, before_json, after_json, hash | Immutable event trail | POST /audit/events, GET /audit/requests/{id} |
| knowledge_capture | capture_id, request_id, lesson_type, summary, destination_uri, publication_status | Knowledge preservation | POST /requests/{id}/knowledge-capture |
| change_record | change_id, target_object, change_type, linked_request_id, version_before, version_after | Versioning and post-action link | POST /changes, GET /changes/{id} |

The API layer should use idempotent execution where practical, especially for scans, audit logging and approval callbacks. Use service accounts for cross-system orchestration and sign events if an event bus is used.

### UI screens and required form fields

| Screen | Core purpose | Required fields |
|---|---|---|
| Competition / Project Registration | Formal intake of any project, competition, automation or solution request | Request ID, title, type, originator, department, business problem, target users, requested outcome, category, constitutions in scope, deadline, current maturity, integration targets, data class, AI usage flag, commercialization intent |
| Compliance Scan | View and execute constitutional pre-checks | Request selector, evidence checklist, duplication scan result, rule-pack version, scan status, missing artefacts, hard-stop alerts, readiness score, exception request button |
| Judge Review | Standard scoring and justification | Judge identity, conflict declaration, score by category, evidence reviewed, weaknesses, strengths, maturity classification, integration recommendation, commercialization recommendation, disqualification markers |
| Approval Dashboard | Route decisions and exception handling | Pending approvals, request type, risk level, final recommendation, current blockers, approver action buttons, conditions, escalations, expiry time, audit links |
| Chairman Dashboard | Executive view of governance and portfolio health | Total requests, compliance pass rate, duplicate prevention count, archive/integrate/productize/commercialize outcomes, high-risk items, pending approvals, recurring revenue pipeline, people-dependency heat map, judge quality metrics, top non-compliance causes |
| Evidence Verification | Human and AI evidence review | Artefact list, file/reference URI, validity status, reviewer note, last version, linked requirements, cross-reference to Knowledge Vault |
| Integration Mapping | Shows where approved solutions must connect | Source module, target system, preferred method, payload scope, event or API contract, status, test evidence |
| Audit Trail Explorer | Immutable history and accountability | Request ID, actor, action, timestamp, reason, approval stage, previous version, new version, linked policy pack |
| Prompt Registry Admin | Prompt governance | Prompt ID, class, owner, RBAC, semantic version, approved status, anchor list, usage metrics, review cycle |
| Exception and Waiver Screen | Controlled override mechanism | Request ID, waiver reason, standards/policies affected, approving authority, expiry date, compensating controls, mandated follow-up |

### Integration plan and method comparison

The orchestrator must operate as a control plane across the existing DAIOS ecosystem.

| Integration method | Best use case | Strengths | Risks | Recommended for |
|---|---|---|---|---|
| API | Real-time transactional checks and decision routing | Strong contracts, synchronous response, traceable | Tight coupling if poorly versioned | Product Registry, Prompt Registry, Revenue OS, Admission, Registrar |
| Webhook | Event notifications after decisions | Simple push model, near-real-time | Retries and signature verification required | Marketplace, KCX, external services |
| Event bus | Enterprise-wide asynchronous orchestration | Scalable, decoupled, good for audit and state changes | Schema governance needed | Central AI, Dashboard, Knowledge Vault, cross-department workflows |
| Plugin | Embedding governance into a host system | Reusable, configurable | Host compatibility matters | Student360, DUDOS portals, Central Dashboard widgets |
| SSO | Identity and access control | Strong user continuity, RBAC alignment | Requires IAM maturity | Student360, HR, Chairman Command Center |
| Shared database | Legacy/reporting only where unavoidable | Fast local access | High coupling, data ownership risks | Temporary read-only reporting bridge |
| File exchange | Transitional migration and archive import | Works for legacy teams | Slow, error-prone, weak governance if overused | Historical imports, one-time archive seeding |

Suggested system mapping:

| Target system | Primary purpose | Preferred method | Fallback | Data shared |
|---|---|---|---|---|
| Product Registry | Search, classification, anti-duplication | API | Event bus | Product metadata, maturity, ownership |
| Knowledge Vault | Evidence, lessons learned, institutional memory | Event bus | API | Summaries, artefact links, decisions |
| Prompt Registry | Prompt governance, versioning | API | Plugin | Prompt metadata, RBAC, usage |
| Central AI | Model/prompt execution and agent routing | Event bus | API | Invocation context, moderation results |
| Student360 | Student roles, submissions, project participation | SSO + API | Plugin | Student profile, project IDs, contribution logs |
| Revenue OS | Revenue readiness and commercialization | API | Event bus | Pricing logic, MRR flags, marketplace status |
| Marketplace / KCX | Packaging and commercialization | Webhook + API | Event bus | Listing approval, commercial status |
| Admission | Departmental solution governance | API | Plugin | Intake automation, controls, approvals |
| Registrar | Workflow and document approvals | API | Event bus | Tracking, status, evidence |
| DUDOS | Institutional operating alignment | Event bus | API | policy packs, departments, service catalogues |
| Chairman Dashboard | Executive decisions and oversight | Event bus | API | risk summaries, approval counts, backlog |
| Alumni360 / Skill.jobs / Career360 | Related ecosystem productization | API | Event bus | feature requests, integrations, customer journeys |

## Compliance Controls and Governance Lifecycle

### Automated checks and rules

The automated checks should be rule-pack based rather than hard-coded, so that future standards and local policies can be inserted through anchors. The domains below are the minimum production baseline.

| Control domain | Automated checks in P00 | Internal mapping | External baseline |
|---|---|---|---|
| Constitutional alignment | Does the request declare applicable constitutions, owners, approvals and decision rights? | EADC, DUDOS, Constitution 4.0 | Governance baseline; aligns well with NIST AI RMF Govern and NIST CSF Govern [3] |
| Documentation gate | Are Product Registration, DAD/TAD, MPIF, BRD, SRS, ERD, API spec, test cases and security review present where required? | DAIOS documentation-before-code rule | ISO/IEC/IEEE 12207 and 15288 life-cycle process orientation [4] |
| Product quality | Does the solution define quality targets such as functional suitability, reliability, security, maintainability and portability? | Product readiness and Definition of Done | ISO/IEC 25010 quality model [5] |
| Anti-duplication | Is there an existing similar product, dashboard, API or module? | Search → Reuse → Improve → Build | CMMI process discipline and organisational reuse ethos [6] |
| AI governance | Is AI necessary; are prompts/models registered; are human review and risk controls present? | AI Governance Handbook, Prompt Registry | ISO/IEC 42001, ISO/IEC 23894, NIST AI RMF, NIST GenAI Profile [7] |
| Security engineering | Are authN/authZ, logging, encryption, error handling, secrets and verification controls present? | Security review, release gates | ISO/IEC 27001, OWASP ASVS, OWASP Top 10, NIST CSF 2.0 [8] |
| Privacy and cloud protection | Does the request process PII; are privacy and public-cloud controls applied? | Data classification, consent, cloud policy | ISO/IEC 27018, ISO/IEC 27701, ISO/IEC 27017 cloud controls baseline [9] |
| Service and release management | Are release, change, acceptance and service operations defined? | PMO model, release management, SOPs | ISO/IEC 20000-1 service management system requirements [10] |
| Maturity and continuous improvement | Is the process measured, repeatable, improvable and evidence-backed? | DAIOS continuous evolution rules | CMMI Quick Reference and new CMMI AIM for AI maturity [6] |
| Data governance | Are data ownership, metadata, classifications and reuse rules defined? | Enterprise Ontology and Master Data Model | DAMA-DMBOK as recognised industry DMBOK baseline [11] |

Hard-stop rules should include at least the following: missing constitutional mapping, missing owner, missing required evidence, duplicate system without approved differentiation, unapproved data source, no security review for sensitive systems, AI without governance controls, unverifiable demo, no integration path for enterprise systems, and no knowledge-capture plan. That directly aligns with your DAIOS judge and participant governance logic as well as the evidence-first assessment approach you defined.

### Prompt governance lifecycle, versioning policy and audit design

The lifecycle should be fixed and simple:

**Draft → Review → Test → Approve → Publish → Execute → Monitor → Improve → Archive**

Use semantic versioning with constitutional coupling:

- **Major**: constitutional logic changed or approval path changed

- **Minor**: new rule pack, new integration target, new anchor activation

- **Patch**: language tuning, formatting, field normalisation

Recommended naming convention:

P00-GOV-ORCH-C4-EADC-DUDOS-v1.0.0

Where:

- P00-GOV-ORCH = prompt class and name

- C4-EADC-DUDOS = governing constitutional baseline

- v1.0.0 = semantic version

Audit trail design should be event-based and append-only. Every invocation must log: who invoked, which prompt version executed, what rule pack versions were applied, what evidence was read, what duplicate matches were found, which approvals were required, what final disposition was issued, whether any human override occurred, and which downstream systems were notified. For sensitive domains, store a cryptographic hash of the prompt body and input payload so that later reviews can prove exactly what logic was used.

### Ready-to-use example prompts

#### Pre-compliance scan

Act as P00.10 Pre-Compliance Scan under P00 Governance & Constitution Orchestrator.

Scan the following request before design or code begins.

Inputs:
{{request_type}}
{{module_name}}
{{business_problem}}
{{artefact_links}}
{{integration_targets}}
{{data_classification}}
{{ai_usage}}
{{commercial_intent}}

Tasks:
1. Identify applicable constitutions: EADC, DUDOS, Constitution 4.0.
2. Search for duplicates or reusable assets.
3. Check for mandatory documents and owners.
4. Detect missing approvals, missing security review, missing integration path and missing revenue/value logic.
5. Return:
- Readiness score
- Missing evidence list
- Duplicate / reuse findings
- Hard-stop violations
- Recommended next action
Do not recommend coding if mandatory evidence is missing.

#### Judge orientation

Act as P00.30 Judge Orientation Engine.

Prepare a standard judge briefing for:
{{competition_name}}
{{competition_category}}
{{scorecard_version}}
{{constitutional_scope}}

Explain:
- the evidence-first policy
- the 100-point scorecard
- what recurring revenue means
- why presentation quality alone is insufficient
- how to detect duplicates, fabricated demos and isolated solutions
- conflict-of-interest declaration requirements
- when to recommend archive, integrate, pilot, productize or commercialize

Output:
A concise judge briefing, a conflict declaration reminder, and five red-flag checks.

#### Evidence validation

Act as P00.20 Evidence Validator.

Validate the evidence bundle for:
{{request_id}}
{{submission_id}}
{{evidence_links}}

Check:
- Product Registration
- DAD/TAD
- MPIF
- BRD
- SRS
- ERD
- API specification
- Test cases
- Security review
- AI governance evidence
- Revenue/value model
- Knowledge Vault entry

Return a table with:
Evidence item | Status | Adequacy | Comments | Hard stop
Then return a final recommendation:
Complete / Weak but acceptable / Incomplete / Reject

#### Disqualification detection

Act as P00.40 Disqualification Detector.

Review the request and determine whether it should be disqualified from production-ready or marketplace-ready consideration.

Inputs:
{{submission_id}}
{{precheck_results}}
{{evidence_validation}}
{{judge_comments}}
{{security_findings}}
{{duplication_results}}

Disqualify if any of these are present without approved exception:
- no documentation
- unclear ownership
- no integration path
- unauthorised data use
- unverifiable demo
- missing security review
- ungoverned AI
- duplicate solution without approved gap
- no Knowledge Vault entry
- no product owner or support owner

Return:
- disqualification decision
- exact reasons
- whether academic recognition can still be given
- required rework to re-enter review

#### Chairman approval note

Act as P00.50 Chairman Approval Note Generator.

Using the moderated review pack and constitutional checks, draft a concise executive approval note for:
{{request_id}}
{{module_name}}
{{final_score}}
{{maturity_classification}}
{{recommended_disposition}}

Include:
- what problem is being solved
- whether the solution is constitution-compliant
- its productization and integration status
- commercial or institutional value
- key conditions before next phase
- final approval recommendation:
  Approve / Approve with conditions / Return for rework / Reject / Escalate

Keep the note executive, decisive and auditable.

## Roadmap, Team and Developer Instructions

### Implementation roadmap

This is the recommended sequence for making P00 operational without scope drift.

| Phase | Timeline | Milestones | Exit criteria |
|---|---|---|---|
| Stabilise | Day 1–30 | Freeze prompt schema, rule-pack structure, RBAC, core entities, first UI mock-ups, API contracts, pilot workflow | Approved P00 v1.0 draft, rule-pack inventory, minimal data model |
| Pilot | Day 31–60 | Build request intake, evidence validation, duplication scan, approval route, audit events, judge flow beta | One live pilot using a competition or departmental automation stream |
| Operational MVP | Day 61–90 | Connect Product Registry, Knowledge Vault, Prompt Registry, Chairman Dashboard summary; add moderation and disposition logic | P00 used for real approvals and archived decisions |
| Enterprise rollout | Day 91–180 | Add integrations to Student360, Revenue OS, Marketplace, Registrar, Admission, KCX; add rules dashboard, prompt quality analytics, exception handling | P00 becomes mandatory gate for all new governed requests |

### Minimal team, KPIs and budget bands

| Role | Minimal responsibility | KPI |
|---|---|---|
| Product Owner / Governance Lead | Owns prompt behaviour, scope, priorities, acceptance | approval turnaround time, rule coverage, stakeholder acceptance |
| Business Analyst / Constitution Mapper | Translates EADC/DUDOS/DAIOS into executable rules | mapping completeness, ambiguity reduction |
| Backend Engineer | APIs, workflow engine, audit trail, rule execution | API quality, scan latency, uptime |
| Frontend Engineer | Intake screens, dashboards, approval UI | completion rate, usability errors, cycle-time reduction |
| AI / Prompt Engineer | P00 body, derived prompts, evaluation tuning | prompt consistency, false approval rate, drift reduction |
| QA / Compliance Analyst | Test cases, rule validation, negative scenarios | escaped defects, test coverage, compliance accuracy |
| DevOps / Platform Engineer | Deployment, CI/CD, secrets, observability | deployment reliability, mean time to recover |
| Data / Knowledge Engineer | Registry sync, archive capture, search quality | duplicate detection precision, knowledge publication rate |

Indicative budget bands are **provisional internal planning ranges** because no cost baseline was supplied in the materials. A practical planning view for a 180-day rollout is:

- **Low**: BDT 12–18 lakh — minimal team, internal hosting, limited integrations

- **Medium**: BDT 25–40 lakh — stronger QA, event bus, dashboards, broader integrations

- **High**: BDT 55–90 lakh — full enterprise rollout, stronger security, multi-team change management, external audits

These figures should be treated as placeholders until your PMO and finance teams apply local salary, licensing, infrastructure and compliance assumptions.

### Top implementation risks and mitigations

| Risk | Impact | Mitigation |
|---|---|---|
| Internal constitutions remain interpretive rather than executable | High | Convert each constitutional clause into explicit rule packs and approval conditions |
| Teams bypass P00 for “urgent” work | High | Make Product Registry, release approval and deployment dependent on P00 request ID |
| Duplicate data or registries reduce scan quality | High | Define a single system of record for each object type and sync through contracts |
| Weak evidence culture | High | Make missing evidence a visible blocker and provide template packs |
| AI false positives / false negatives in compliance decisions | Medium | Keep human review for hard-stop and approval steps; log confidence levels |
| Overuse of shared databases | Medium | Prefer API and event bus; time-box legacy bridges |
| Prompt drift due to unmanaged edits | High | Enforce registry-only versioning and approval workflow |
| Over-complex UI | Medium | Start with five mandatory screens only, expand after pilot |
| Lack of department onboarding | Medium | Pair P00 rollout with department intake templates and coordinator training |
| No post-action knowledge capture | High | Make knowledge publication and audit completion mandatory closing tasks |

### Concise instructions for developers

Developers should implement P00 as a **workflow service plus rule engine**, not as a monolithic prompt hidden inside chat. First, store the master prompt in the Prompt Registry with version control and RBAC. Second, externalise rules into configuration packs so EADC/DUDOS/DAIOS and standards mappings can evolve without rewriting the root prompt. Third, make every governed action create a governance_request record first. Fourth, make duplication search and evidence validation happen before any approval screen opens. Fifth, store every step as an audit event. Sixth, connect P00 to Product Registry, Knowledge Vault and Prompt Registry before integrating more systems. Seventh, keep “hard stops” declarative and testable. Eighth, make the output deterministic in structure even if the narrative language varies.

### Concise instructions for governance operators

Governance should not use P00 as an advisory chatbot. It should be used as the **official gateway**. Require a P00 request ID for competitions, departmental automation, architecture reviews, release approvals, productizations, marketplace listings and major AI deployments. Maintain the constitutional rule packs. Review exceptions monthly. Measure compliance not by how many forms were filled, but by how many duplicate builds were prevented, how many projects became reusable, how many approvals became traceable, how much people dependency was reduced, and how much institutional or recurring commercial value was created.

The practical conclusion is simple: **freeze the constitution, not the evolution**. Freeze the root orchestration logic in P00. Move everything else—new modules, new departments, new judges, new compliance rules, new accreditation needs, new AI tools, new commercial pathways—into **registries, rule packs, integrations, and future anchors**. That is how DAIOS remains stable at the core while continuously expanding at the edges.

ISO/IEC/IEEE 12207:2026 - Systems and software engineering — Software life cycle processes

Artificial Intelligence Risk Management Framework (AI RMF 1.0) | NIST

ISO/IEC 25010:2023 - Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — Product quality model

CMMI Model Quick Reference Guide | ISACA

ISO/IEC 42001:2023 - Intelligence artificielle – Système de management

ISO/IEC 27001:2022 - Systèmes de management de la sécurité de l'information

ISO/IEC 27018:2025 - Information security, cybersecurity and privacy protection — Guidelines for protection of personally identifiable information (PII) in public clouds acting as PII processors

ISO/IEC 20000-1:2018 - Technologies de l'information — Gestion des services — Partie 1: Exigences du système de management des services

Home - DAMA International®
