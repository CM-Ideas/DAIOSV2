# DAIOS Master Prompt Templates for P00, P01 and P03

## Executive summary

This report turns your DAIOS vision into an executable prompt-governance design for three foundational DPOS modules: **P00 Governance & Constitution**, **P01 Intake & Diagnosis**, and **P03 Documentation Generation**. The design assumes DAIOS will treat prompts as governed enterprise assets rather than ad hoc text, and that no software, AI workflow, competition solution, departmental automation, or academic system may proceed outside the control of the EADC, DUDOS, and DAIOS constitutional layers. That direction aligns well with current global practice: ISO/IEC 42001 requires an Artificial Intelligence Management System with policies, controls, monitoring and continual improvement; NIST AI RMF structures AI risk management around **Govern, Map, Measure, Manage**; ISO 9001, ISO/IEC 27001 and ISO/IEC 20000-1 all emphasise process control, documented systems, risk-based governance and continual improvement; and CMMI’s current model increasingly integrates data, people, virtual work and AI maturity into organisational capability improvement.

The practical implication for DAIOS is clear. **P00** must become the constitutional gatekeeper that checks EADC, DUDOS, approval rights, risk posture, duplication risk, academic/commercial classification and deployment readiness before anything else happens. **P01** must become the standardised departmental intake and diagnostic engine that converts informal complaints, Excel trackers, queues, bottlenecks, pressure points and scattered requirements into a structured automation brief. **P03** must then convert approved and validated inputs into controlled artefacts such as Product Registration, DAD, MPIF, BRD, SRS, ERD, API specifications, acceptance criteria and release evidence, in line with requirements-engineering and lifecycle-process standards.

The recommended operating pattern is: **P01 first for business discovery, P00 second for constitutional clearance, P03 third for controlled documentation generation**, followed by architecture review, backlog formation, build, QA, release and knowledge archival. That sequence matches ISO/IEC/IEEE 29148 requirements engineering, ISO/IEC/IEEE 12207 software lifecycle control, ISO/IEC/IEEE 15288 system lifecycle governance, and NIST CSF 2.0’s newer emphasis on governance as a first-class function rather than an afterthought.

Because some earlier uploaded files in this session were no longer retrievable through the file tools, and a Google Drive connector was not active in this run, the DAIOS-specific content below is grounded in the requirements you supplied in the conversation and cross-mapped to official standards and current reference practices. That means the model is implementation-ready, while a final document-by-document reconciliation against any re-uploaded source artefacts should be treated as the last constitutional freeze step.

## Source position, assumptions and design principles

The framework below is written on six assumptions that should be treated as governance defaults unless your team explicitly revises them in Constitution Freeze v1. First, **Prompts are controlled assets** and therefore need IDs, versions, owners, review status, risk level and deployment status. Second, **no prompt may bypass P00** if the output affects architecture, development, approvals, external communication, academic judging, data collection, or automation decisions. Third, **every departmental request must pass through P01** before any solutioning conversation begins. Fourth, **P03 may generate documents, but may not invent business facts**: it can only draft from approved inputs, existing DAIOS knowledge and traceable assumptions. Fifth, **every prompt execution must be logged and recoverable**. Sixth, **future changes should be added through governed placeholders** and not by rewriting the root operating philosophy. This design direction is consistent with NIST AI RMF’s stress on governance, lifecycle controls and documentation; ISO/IEC 42001’s requirement for policies, monitoring and continual improvement; and ISO/IEC 27001’s risk-based control model.

For DAIOS, the permanent prompt-operating philosophy should remain:

- System before people

- Product before project

- Revenue before activity

- AI before manual effort

- Reuse before rebuild

- Governance before scale

- Commercialisation before expansion

- Knowledge capture before closure

Those are not only leadership slogans; they have direct design consequences. “System before people” means prompt execution must not depend on any one developer’s memory. “Reuse before rebuild” means every prompt execution must search Product Registry, Knowledge Vault and Prompt Registry before generating new outputs. “Governance before scale” means no prompt can become production-grade unless it passes review, testing and approval. Vendor and framework implementation guidance now converges on the same point: production AI requires prompt version control, audit trails, deployment governance and rollback discipline rather than free-form chat usage.

## Standards mapping and control framework

The control baseline for DAIOS should be intentionally layered rather than fragmented. **ISO 9001** governs quality management, customer focus, corrective action and continual improvement. **ISO/IEC 27001** governs the information security management system. **ISO/IEC 27017** and **ISO/IEC 27018** add cloud-security and cloud-privacy controls that are directly relevant if DAIOS hosts prompts, logs, student records or departmental data in cloud environments. **ISO/IEC 20000-1** governs service management for support, change, incident, release and improvement. **ISO/IEC 42001** governs AI management. **ISO/IEC/IEEE 12207**, **15288** and **29148** govern software lifecycles, system lifecycles and requirements engineering. **ISO/IEC 25010** defines the product quality model used to evaluate quality characteristics across the lifecycle.

For cybersecurity and AI assurance, **NIST CSF 2.0** is especially important because it added an explicit **Govern** function and now positions itself for use by organisations of any size, not just critical infrastructure. That is helpful for DAIOS because prompts affect not only engineering but approvals, risk communications and role accountability. **NIST AI RMF** remains the best high-level operational model for prompt-governance design because it treats AI risk management as continuous and lifecycle-wide, and its companion Playbook provides action-oriented implementation suggestions. NIST’s AI resource stack also now emphasises TEVV, which is directly relevant to prompt testing, validation and anomaly detection inside DPOS.

For secure application development, **OWASP ASVS** should be the minimum baseline for web-facing modules, **OWASP MASVS** for mobile applications, and **OWASP LLMSVS** for LLM-backed features, prompt execution, agent behaviour, model lifecycle and integration safety. OWASP continues to present ASVS as a basis for testing web-application technical security controls and to give developers a requirement list for secure development; MASVS is the flagship mobile-security standard; and LLMSVS now provides a dedicated verification standard for LLM-based systems.

For organisational maturity, your CMMI direction should not be limited to legacy “development maturity” language. ISACA’s current CMMI material emphasises that the modern model covers additional domains including **data management, people management and virtual work**, and on 15 July 2026 ISACA announced **CMMI AIM**, which extends maturity management into AI capability and adoption. That is a strong fit for DAIOS because DAIOS is not only building products; it is building a governed AI-native enterprise operating environment.

The shortest practical standard-to-module map is this:

| DPOS Module | Primary Standard Mapping | Secondary Mapping | DAIOS Purpose |
|---|---|---|---|
| P00 Governance & Constitution | ISO/IEC 42001, NIST AI RMF, NIST CSF 2.0, ISO 9001 | ISO/IEC 27001, CMMI, TOGAF | Approval, policy, traceability, constitutional alignment |
| P01 Intake & Diagnosis | ISO/IEC/IEEE 29148, ISO 9001, CMMI | ISO/IEC/IEEE 12207/15288, NIST CSF Govern | Requirement discovery, pain analysis, current-state evidence |
| P03 Documentation Generation | ISO/IEC/IEEE 29148, 12207, 15288, ISO/IEC 25010 | ISO/IEC 42001, OWASP ASVS/MASVS/LLMSVS | Controlled artefact generation, quality-gated delivery |

## P00, P01 and P03 master prompt templates

### P00 Governance and Constitution

#### Purpose and scope

P00 is the constitutional orchestrator. It is the first authoritative check that decides whether a request is academically valid, commercially viable, policy-compliant, structurally non-duplicative and safe to proceed. It must be used for every new product, departmental automation request, AI solution, competition submission, academic project moving toward institutional use, dashboard request, workflow automation, prompt-library proposal and release approval. It should also be callable by other prompts as a dependency-checking service. This control pattern reflects the governance-first model in ISO/IEC 42001, NIST AI RMF’s Govern function and NIST CSF 2.0’s new Govern function.

#### Required inputs

| Input | Mandatory | Description |
|---|---|---|
| Request title | Yes | Name of project, module, automation or system |
| Request type | Yes | Commercial / Academic / Internal Utility / Competition / Faculty / Student / Research |
| Requesting unit | Yes | Department, company, wing or project team |
| Problem statement | Yes | Practical issue being addressed |
| Requested outcome | Yes | Time saved, complaints reduced, revenue, service quality, accreditation, etc. |
| Applicable policies | Yes | EADC, DUDOS, departmental regulations, accreditation constraints |
| Initial evidence pack | Yes | Tracker sheets, complaint logs, queue samples, minutes, screenshots, forms |
| Proposed integrations | Yes | Student360, DUDOS, Product Registry, Central Dashboard, Revenue OS etc. |
| Data classification | Yes | Public / Internal / Confidential / Sensitive / Student / HR / Financial / Health |
| Approval path | Yes | Who owns, who approves, who reviews security, AI and architecture |
| Prior-solution search reference | Yes | What was searched in DAIOS and what already exists |
| Deployment intent | Yes | Prototype only / Academic demonstration / Pilot / Production / Marketplace |

#### Mandatory evidence

P00 should reject or place on hold any request that lacks minimum evidence. At minimum it should require a request description, current-state process note, evidence of pain or value, initial integration intent, and confirmation that a duplication search was performed. For higher-risk requests, it should additionally require data sensitivity classification, ownership details, approval route and technical context. This aligns with requirements engineering and AI governance expectations for traceability and documented decision-making.

#### Ready-to-run prompt text

PROMPT ID: P00-CONSTITUTION-ORCHESTRATOR-V1.0
CATEGORY: Governance and Constitution
RISK LEVEL: Restricted / Governance Prompt

Act as the Global Chief Governance Officer, Chief Technology Officer, Chief Product Officer, Chief AI Officer, Chief Academic Innovation Officer, Chief Commercialization Officer, Architecture Review Board Lead, and Assessment Quality Director of DAIOS.

Mission:
You are the constitutional gatekeeper for DAIOS. Your task is to evaluate whether a proposed request may proceed under the DAIOS Constitution, EADC, DUDOS, AI Governance Handbook, Product Registry rules, Knowledge Vault reuse rules, and enterprise approval controls.

Core Operating Rules:
1. Governance before scale.
2. Search first, reuse second, build third.
3. No development without constitutional evidence.
4. No AI use without traceability and risk controls.
5. No duplicate solution without a justified exception.
6. No project proceeds without identifying whether it is academic, institutional, commercial, marketplace, or global SaaS in potential.

Inputs:
- Request Title / অনুরোধের শিরোনাম:
- Request ID:
- Request Type:
- Requesting Unit / বিভাগ:
- Business or Academic Problem:
- Current Pain or Complaint Summary:
- Desired Outcome:
- Existing DAIOS Search Evidence:
- Known Existing Systems or Modules:
- Proposed Integrations:
- Data Classification:
- Stakeholders:
- Approver(s):
- Initial Evidence Pack Summary:
- Accreditation or Policy Requirements:
- Commercialization Intent:
- Academic Use Intent:
- Risk Notes:
- Assumptions:
- Requested Next Step:

Your mandatory evaluation dimensions:
A. EADC compliance
B. DUDOS institutional alignment
C. DAIOS constitutional alignment
D. Duplication and reuse analysis
E. Governance readiness
F. Documentation readiness
G. Data and AI risk
H. Integration readiness
I. Commercialization and revenue readiness
J. Academic suitability and knowledge-preservation readiness
K. Approval-path completeness
L. Recommendation on whether the request should proceed, pause, merge, be archived, or be redirected

Validation rules:
- If no evidence of current pain, mark “Insufficient Diagnostic Basis”.
- If no duplication search was performed, mark “Search Non-Compliance”.
- If no approving authority is identified, mark “Approval Path Missing”.
- If student/faculty/HR/financial/health data is involved without classification, mark “Data Governance Gap”.
- If request is isolated and ignores central systems, mark “Integration Non-Compliance”.
- If academic idea is presented as production-ready without documents, mark “Maturity Misclassification”.
- If commercialization is claimed without recurring model or measurable institutional value, mark “Commercialization Gap”.

Output format:
Return the result in the following exact structure:

1. Executive Decision
2. Request Classification
3. Constitutional Alignment Summary
4. Missing Inputs and Missing Evidence
5. Duplication and Reuse Findings
6. Integration Findings
7. Risk Findings
8. Approval and Governance Findings
9. Academic/Commercial Readiness Findings
10. Required Documents Before Next Stage
11. Recommended Next Workflow:
   - Reject
   - Hold
   - Intake Required
   - Documentation Generation Allowed
   - Architecture Review Required
   - Merge with Existing Product
   - Route to Student Product Factory
   - Route to Faculty Innovation
   - Route to Marketplace/Revenue OS
12. Storage Instructions:
   - Knowledge Vault location
   - Product Registry action
   - Prompt Registry linkage
13. Final Constitutional Status:
   - Approved to proceed
   - Approved with conditions
   - Not approved

Do not write generic advice.
Do not invent missing facts.
Do not approve any request that lacks constitutional evidence.

#### Expected structured output

P00 should return a machine-readable and human-readable package with at least these fields:

{
  "request_id": "REQ-2026-0001",
  "module": "P00",
  "classification": "Department Automation Request",
  "constitutional_status": "Approved with conditions",
  "eadc_status": "Partial",
  "dudos_alignment": "Yes",
  "duplication_status": "Potential overlap with Central Dashboard",
  "required_next_prompt": ["P01-INTAKE-DIAGNOSIS", "P03-DOCUMENTATION-GENERATION"],
  "missing_evidence": ["queue sample", "approval note", "data classification"],
  "risks": [
    {"code": "RISK-DATA-01", "level": "High", "description": "Student data present without classification"}
  ],
  "storage_actions": {
    "knowledge_vault": "KV/Governance/Requests/REQ-2026-0001",
    "product_registry": "Create candidate entry",
    "prompt_registry": "Log execution trace"
  }
}

#### Validation rules and automated pre-checks

P00 pre-checks should include: duplicate-title search; similarity search against Product Registry and Knowledge Vault; check for missing required fields; cross-check of risky data words such as “student”, “salary”, “medical”, “ID”, “finance”; approval-path completeness; request-type gating; and environmental intent check to decide whether academic-only or production intent is being claimed. These checks are fully consistent with the risk-based governance model in ISO/IEC 42001 and ISO/IEC 27001, and with NIST AI RMF’s requirement that governance, documentation and measurement be continuous rather than one-time.

#### Storage destinations

- **Knowledge Vault**: Governance dossier, constitutional decision note, missing-evidence list

- **Product Registry**: Candidate entry or merge recommendation

- **Prompt Registry**: Prompt version used, variables submitted, reviewer, execution metadata

### P01 Intake and Diagnosis

#### Purpose and scope

P01 is the departmental discovery and pain-analysis engine. It standardises how departments, companies, wings, offices, medical units, academic units, registrar processes, student services and business teams describe their operational pain. It is the antidote to “everyone is working hard, but no one is following one system.” It converts scattered narratives, spreadsheets, complaint stories and pressure-driven escalations into a reusable diagnostic structure that DAIOS can analyse consistently. This is fundamentally a requirements-engineering and current-state assessment prompt, and maps strongly to ISO/IEC/IEEE 29148 and ISO 9001’s focus on customer/process evidence.

#### Required inputs

| Input | Mandatory | Description |
|---|---|---|
| Department name | Yes | The unit requesting automation |
| Contact owner | Yes | Responsible focal point |
| Service/process name | Yes | Process to be analysed |
| Current workflow | Yes | Narrative of how work happens now |
| Forms/trackers used | Yes | Excel sheets, logbooks, emails, WhatsApp, paper forms |
| Queue/backlog evidence | Yes | Pending requests, complaints, average delay |
| Pain points | Yes | Where confusion, pressure, follow-up or complaints happen |
| Requirement sources | Yes | Who asks for work and through what channel |
| SLA or expectation | No but recommended | Time expectation and escalation threshold |
| Existing systems | Yes | Any software, MIS, dashboard or manual tool already in use |
| Cross-department dependency | Yes | Which other units are involved |
| Data fields handled | Yes | What data is touched |
| Peak-load pattern | No but recommended | When pressure increases |
| Desired automation outcome | Yes | What success should look like |
| Reuse expectation | Yes | Whether the model should be reusable by other units |

#### Mandatory evidence

At least one real document or artefact should be attached conceptually to every P01 intake: a tracker screenshot, sheet structure, queue log, complaint summary, service form, e-mail format, approval path, or process narrative. Without evidence, P01 should still allow a “Discovery Draft” but mark the output as low confidence.

#### Ready-to-run prompt text

PROMPT ID: P01-INTAKE-DIAGNOSIS-V1.0
CATEGORY: Intake and Diagnosis
RISK LEVEL: Internal

Act as the Enterprise Intake Analyst, Process Transformation Architect, Business Analyst, Service Designer, Governance Reviewer, and Pain-Point Diagnostic Lead of DAIOS.

Mission:
Your task is to analyse a department, office, company, wing or service unit that is requesting automation, system improvement, AI support, dashboarding, workflow design, or process standardisation. Convert scattered operational narratives into a structured automation intake diagnosis that DAIOS can use without repeating discovery work.

Context Rules:
1. Diagnose the current state before recommending solution design.
2. Do not jump into software features before understanding the process.
3. Capture evidence of complaints, queues, pressure points, manual dependency and tracker sprawl.
4. Identify which parts are reusable across other departments.
5. Preserve knowledge so future teams do not repeat discovery work.

Inputs:
- Department Name / বিভাগ:
- Request Owner / দায়িত্বপ্রাপ্ত ব্যক্তি:
- Service or Process Name:
- Process Objective:
- Current Workflow Description:
- Forms Used:
- Excel Sheets or Tracker Inventory:
- Communication Channels Used:
- Complaint Types:
- Queue Types:
- Follow-up Pressure Points:
- Approval Bottlenecks:
- Manual Handoffs:
- Average Processing Time:
- Peak Load Periods:
- Existing Systems:
- Existing Dashboards:
- Existing Reports:
- Current Data Fields:
- Upstream Requirement Sources:
- Downstream Users:
- Cross-Department Dependencies:
- Pain Severity:
- Desired Future Outcome:
- Reuse / Replication Potential:
- Evidence Provided:
- Known Risks:
- Assumptions:

Analyse and produce:
A. Current-state diagnostic
B. Manual tracker inventory
C. Queue and complaint analysis
D. People-dependency analysis
E. Follow-up pressure analysis
F. Duplicate-system risk
G. Integration opportunities with DAIOS assets
H. Automation opportunities
I. Reuse potential across departments
J. Documentation requirements for next stage
K. Recommended classification:
   - Local department problem
   - Shared institutional workflow
   - Central reusable model
   - Academic/student project candidate
   - Commercial product candidate

Validation rules:
- If the department cannot describe current workflow, mark “Process Discovery Incomplete”.
- If trackers exist but fields are not defined, mark “Unstructured Data Capture”.
- If complaints are noted without counts/examples, mark “Complaint Evidence Weak”.
- If the same function already exists elsewhere, mark “Potential Duplication”.
- If a request is department-specific but could be parameterised for all departments, flag “Model Candidate”.

Output format:
1. Executive Diagnostic Summary
2. Department Profile
3. Current-State Workflow Summary
4. Forms, Trackers and Evidence Inventory
5. Queue and Complaint Analysis
6. Pressure, Follow-Up and Escalation Analysis
7. Manual Dependency and Role-Dependency Analysis
8. Duplicate-System and Existing-Solution Review
9. Integration Opportunities
10. Parameterisation and Reuse Potential
11. Priority Problems to Solve First
12. Required Documents for P03
13. Recommended Next Action
14. Storage Instructions
15. Confidence Level

Do not design the full solution.
Do not invent KPIs that were not supplied.
Do not hide missing data.

#### Expected structured output

{
  "intake_id": "INT-2026-0042",
  "module": "P01",
  "department": "Registrar Office",
  "process": "Application Tracking",
  "classification": "Central reusable model",
  "current_tools": ["Excel tracker", "Email", "Phone follow-up"],
  "pain_points": [
    "No single status view",
    "Repeated follow-up calls",
    "Approval bottleneck with paper signature"
  ],
  "queue_profile": {
    "avg_pending": 126,
    "peak_period": "Semester end",
    "major_complaints": ["status unknown", "delay", "lost application"]
  },
  "duplication_findings": [
    "Executive dashboard overlaps with Central Dashboard candidate widgets"
  ],
  "recommended_next_prompt": ["P00-CONSTITUTION-ORCHESTRATOR", "P03-DOCUMENTATION-GENERATION"],
  "required_docs": ["Process map", "field dictionary", "approval matrix", "sample tracker"],
  "storage_actions": {
    "knowledge_vault": "KV/Intake/Registrar/ApplicationTracking/INT-2026-0042",
    "product_registry": "Check central dashboard reuse",
    "prompt_registry": "Log diagnostic execution"
  }
}

#### Validation rules and automated pre-checks

P01 should automatically check whether the process name resembles an existing known model such as admission, billing, registrar, dashboard, HR, medical, CRM or ticketing. It should detect references to Excel, sheets, forms, approvals, queues, complaints, escalations and manual follow-up. It should also compare tracker field names and complaint language to central reusable modules. This reflects both requirements-engineering discipline and CMMI’s emphasis on standardisation, data management and organisational capability.

#### Storage destinations

- **Knowledge Vault**: Current-state diagnostic, evidence summary, tracker inventory, queue analysis

- **Product Registry**: Central-model candidacy or duplication notes

- **Prompt Registry**: Execution log and parameter set

### P03 Documentation Generation

#### Purpose and scope

P03 is the controlled document-generation engine. It should only run after P00 and/or P01 have produced sufficient validated inputs. Its role is not to “guess documents”; its role is to turn approved inputs into governed artefacts so that no development begins without documentation. This directly supports the “Documentation Before Development” principle and aligns with ISO/IEC/IEEE 29148, ISO/IEC/IEEE 12207, ISO/IEC/IEEE 15288 and ISO/IEC 25010.

#### Required inputs

| Input | Mandatory | Description |
|---|---|---|
| Source intake ID | Yes | P01 or equivalent source |
| Governance decision ID | Yes | P00 decision or approval note |
| Document type | Yes | Product Registration / DAD / MPIF / BRD / SRS / ERD / API Spec / UAT etc. |
| Scope statement | Yes | Approved scope |
| Stakeholder list | Yes | Users, approvers, owners |
| Process summary | Yes | Approved current-state and target-state understanding |
| Field inventory | For ERD/API/SRS | Data fields and structures |
| Integration map | For architecture/API docs | Systems and methods |
| Security and AI constraints | Yes | Risk controls and governance notes |
| Academic/commercial classification | Yes | Guides language and outputs |
| Assumption log | Yes | Explicit unresolved assumptions |
| Evidence links | Yes | References to intake and supporting materials |

#### Mandatory evidence

P03 should refuse “production-grade” output if there is no P00 governance status, no source intake or no evidence pack. It may generate a **Draft for Review** but must label it clearly.

#### Ready-to-run prompt text

PROMPT ID: P03-DOCUMENTATION-GENERATION-V1.0
CATEGORY: Documentation Generation
RISK LEVEL: Controlled

Act as the Chief Documentation Architect, Senior Business Analyst, Systems Analyst, Enterprise Architect, AI Governance Writer, QA Documentation Lead, and Product Office Documentation Controller of DAIOS.

Mission:
Generate governed project and product documentation from validated DAIOS inputs. You may draft controlled artefacts only from approved intake, governance findings, known DAIOS knowledge, and clearly marked assumptions. You must not fabricate business facts.

Operating rules:
1. No document may contradict P00 constitutional decisions.
2. No document may ignore P01 diagnostic findings.
3. Every assumption must be labelled.
4. Every generated document must show missing inputs and review requirements.
5. Outputs must remain reusable, auditable and ready for Knowledge Vault archival.

Inputs:
- Source Intake ID:
- Governance Decision ID:
- Document Type Requested:
- Project or Product Title:
- Classification:
- Business/Academic Objective:
- Stakeholders:
- Source Process Summary:
- Target Outcome Summary:
- Integration Scope:
- Data Fields / Entities:
- Security Constraints:
- AI Constraints:
- Required Standards:
- Acceptance Expectations:
- Evidence References:
- Known Gaps:
- Assumptions:
- Required Output Format:

Available document types:
- Product Registration
- DAD
- MPIF
- BRD
- SRS
- ERD
- API Specification
- Test Case Draft
- UAT Draft
- Release Readiness Checklist
- Knowledge Capture Summary

Generation instructions:
For each requested document:
A. Use only validated input.
B. If any mandatory section is unsupported, mark “Input Missing”.
C. Structure the document according to enterprise standards.
D. Include a traceability section.
E. Include a review-and-approval section.
F. Include a change-history stub.
G. Include constitutional and compliance references.

Output format:
1. Document Header
2. Document Status
3. Source Traceability
4. Generated Content
5. Missing Inputs
6. Open Questions
7. Required Reviews
8. Storage Instructions
9. Next Workflow Step

Do not produce one-page shallow summaries if the requested artefact requires full structure.
Do not hide unresolved ambiguities.
Do not mark any document final unless all mandatory sections are evidenced.

#### Expected structured output

{
  "document_request_id": "DOC-2026-0131",
  "module": "P03",
  "document_type": "BRD",
  "status": "Draft for Review",
  "traceability": {
    "intake_id": "INT-2026-0042",
    "governance_id": "REQ-2026-0001"
  },
  "missing_inputs": ["Formal SLA target", "Approved field dictionary"],
  "required_reviews": ["Business owner", "Architecture", "AI governance", "Security"],
  "storage_actions": {
    "knowledge_vault": "KV/Documents/Registrar/BRD/DOC-2026-0131",
    "product_registry": "Attach BRD reference",
    "prompt_registry": "Record document-generation run"
  }
}

#### Validation rules and automated pre-checks

P03 should first check whether the requested document type is allowed at the current maturity stage. For example, ERD generation without field inventory should be blocked; SRS generation without functional scope should be flagged; release readiness without test evidence should be refused. That is exactly the kind of quality gating expected in lifecycle standards and quality models.

#### Storage destinations

- **Knowledge Vault**: Final draft, review notes, assumptions, traceability map

- **Product Registry**: Attach approved artefact references

- **Prompt Registry**: Prompt version, template variant, generation metadata

## DPOS integration procedure, architecture and data model

### End-to-end workflow

The simplest correct workflow for DAIOS is below.

|   |
|---|

This sequence ensures that DAIOS does not start from code, but from discovery, governance and documentation. That supports both your constitutional philosophy and recognised engineering process control.

### Roles, permissions and RACI

#### Role and permission model

| Role | Can Execute | Can Review | Can Approve | Can Publish | Notes |
|---|---|---|---|---|---|
| Department Requestor | P01 | No | No | No | Submits operational facts only |
| Business Analyst | P01, P03 | Yes | No | No | Curates intake and draft documents |
| Governance Officer | P00 | Yes | Conditional | No | Reviews EADC/DUDOS/constitutional fit |
| Product Owner | P00, P03 | Yes | Conditional | No | Owns product outcome |
| AI Governance Reviewer | P00, P03 | Yes | Conditional | No | Reviews AI risk and prompt use |
| Architecture Review Board | P00, P03 | Yes | Yes | No | Architecture, reuse and integration gate |
| Security Reviewer | P00, P03 | Yes | Conditional | No | Data and control review |
| Prompt Librarian / Knowledge Manager | All | Yes | No | Yes | Registry, metadata, archival |
| PMO / Release Manager | P03 | Yes | Conditional | Yes | Release governance |
| Chairman Dashboard Reader | None | No | No | No | Read-only oversight |

#### RACI by module

| Activity | Department | BA | Governance | Product Owner | AI Gov | ARB | Security | Knowledge Manager | PMO |
|---|---|---|---|---|---|---|---|---|---|
| Submit intake | R | A | C | C | I | I | I | I | I |
| Diagnose current state | C | R/A | I | C | I | I | I | C | I |
| Constitutional review | I | C | R/A | C | C | C | C | I | I |
| Generate documents | I | R | C | A | C | C | C | C | I |
| Approve architecture readiness | I | C | C | C | C | R/A | C | I | I |
| Publish prompt version | I | I | C | C | C | I | I | R/A | I |
| Release to operational use | I | I | C | A | C | C | C | I | R |

### Core entities and data model

The minimum DPOS data model should include the following entities:

| Entity | Key fields |
|---|---|
| PromptDefinition | prompt_id, module, category, owner, version, status, language, risk_level |
| PromptExecution | execution_id, prompt_id, input_hash, output_hash, executed_by, timestamp, status |
| GovernanceDecision | decision_id, request_id, constitutional_status, approvals, conditions |
| IntakeCase | intake_id, department, process_name, evidence_count, diagnostic_status |
| DocumentArtifact | doc_id, type, source_intake_id, governance_id, version, review_status |
| EvidenceItem | evidence_id, case_id, type, file_ref, source, sensitivity |
| IntegrationLink | link_id, source_module, target_system, method, status |
| RegistryAction | action_id, target_registry, operation, ref_id, status |
| AnomalyFlag | flag_id, execution_id, severity, reason, reviewer, disposition |
| ReviewRecord | review_id, artefact_ref, reviewer_role, outcome, notes |

### UI screens

The minimum viable DPOS UI for these modules should include:

| Screen | Purpose |
|---|---|
| Prompt Registry | Browse governed prompts by module/category/version |
| Intake Submission | Department fills P01 input template |
| Intake Diagnostic Workspace | BA reviews and enriches P01 output |
| Governance Review Workspace | P00 constitutional panel and decision screen |
| Documentation Request Screen | Trigger P03 with governed source references |
| Evidence Vault Uploader | Add screenshots, trackers, forms, minutes |
| Execution Audit Log | View prompt runs, status, anomalies, reviewers |
| Registry Linkage Screen | Attach outputs to Product Registry / Knowledge Vault |
| Prompt Version Control | Draft, review, approve, retire, rollback |

### API and webhook integration points

DAIOS should expose these internal service endpoints. The endpoint names are assumptions and should be finalised during architecture design.

| Endpoint | Method | Purpose |
|---|---|---|
| /api/dpos/prompts/execute | POST | Execute a governed prompt |
| /api/dpos/prompts/register | POST | Register or update prompt metadata |
| /api/intake/cases | POST | Create P01 intake case |
| /api/governance/review | POST | Run P00 governance decision |
| /api/documents/generate | POST | Run P03 controlled generation |
| /api/evidence/upload | POST | Attach evidence artefacts |
| /api/registries/link | POST | Save output into Knowledge Vault / Product Registry |
| /api/anomalies/flag | POST | Open exception or anomaly case |
| /api/dashboards/events | POST | Send execution metrics to Central/Chairman Dashboard |

### Sample payloads

#### P01 intake submission

{
  "prompt_id": "P01-INTAKE-DIAGNOSIS-V1.0",
  "department_name": "Registrar Office",
  "request_owner": "Deputy Registrar",
  "process_name": "Application Tracking",
  "current_workflow": "Applications are received by email and manually entered into Excel...",
  "forms_used": ["Email template", "Excel tracker", "Paper approval form"],
  "complaint_types": ["Status unknown", "Delayed approval", "Lost supporting file"],
  "queue_types": ["Pending applications", "Awaiting signature"],
  "existing_systems": ["Basic spreadsheet", "Email inbox"],
  "desired_future_outcome": "Track every application with self-service status and department dashboard",
  "reuse_expectation": "Should be usable by multiple offices",
  "evidence_refs": ["EV-001", "EV-002"]
}

#### P00 governance review

{
  "prompt_id": "P00-CONSTITUTION-ORCHESTRATOR-V1.0",
  "request_id": "REQ-2026-0001",
  "request_type": "Department Automation",
  "requesting_unit": "Registrar Office",
  "problem_statement": "No traceable application lifecycle",
  "desired_outcome": "Reduce complaints and repeated follow-up",
  "existing_search_evidence": ["PR-MATCH-002", "KV-MATCH-019"],
  "proposed_integrations": ["Central Dashboard", "Student360", "DUDOS"],
  "data_classification": ["Student Data", "Internal"],
  "approvers": ["Registrar", "Governance Office", "Architecture Review Board"],
  "evidence_pack": ["INT-2026-0042", "EV-001", "EV-002"]
}

#### P03 documentation generation

{
  "prompt_id": "P03-DOCUMENTATION-GENERATION-V1.0",
  "source_intake_id": "INT-2026-0042",
  "governance_decision_id": "REQ-2026-0001",
  "document_type": "BRD",
  "project_title": "Registrar Application Tracking Model",
  "classification": "Institutional Product Candidate",
  "stakeholders": ["Students", "Registrar Office", "Approvers", "Service Desk"],
  "source_process_summary": "Current system uses email, manual Excel, paper signatures",
  "integration_scope": ["Central Dashboard", "Student360"],
  "security_constraints": ["Student data confidentiality", "Audit logging"],
  "required_standards": ["EADC", "DUDOS", "ISO 27001", "ISO 25010"]
}

## Governance workflow, exceptions, versioning and future evolution

### Governance approval flow

|   |
|---|

This governance sequence corresponds closely to ISO/IEC 42001’s continual-improvement logic and to AI RMF guidance that governance should be infused throughout the lifecycle rather than applied only at deployment.

### Error and exception handling

DPOS should not merely return “something went wrong”. It should classify exceptions. The minimum anomaly library should include:

| Code | Meaning | Trigger |
|---|---|---|
| ANOM-MISSING-INPUT | Required fields absent | Prompt called without mandatory inputs |
| ANOM-CONFLICT-FACTS | Inputs clash | Intake says “no system”, registry says “existing module” |
| ANOM-DUPLICATION | Existing model likely | Similarity threshold exceeded |
| ANOM-SENSITIVE-DATA | Sensitive info without classification | Student/HR/health terms detected |
| ANOM-LOW-CONFIDENCE | Evidence too weak | P01 received narrative but no artefacts |
| ANOM-OUTPUT-DRIFT | Output format shifted materially | Prompt no longer returning expected schema |
| ANOM-REVIEW-BYPASS | Execution attempted without approval | Restricted prompt called by wrong role |
| ANOM-STANDARDS-GAP | Required controls missing | Security/AI checklist incompletely satisfied |

Every anomaly should create a record, route to an owner, and carry a disposition such as “accepted”, “reworked”, “merged”, “retired”, or “escalated”. NIST’s TEVV emphasis and AI RMF governance approach both support this kind of ongoing, measurement-based control.

### Versioning rules

Use semantic-style prompt versioning:

- **V1.0**: first approved production version

- **V1.1**: minor wording or output-format improvement

- **V1.2**: new validation rule, no major mission change

- **V2.0**: structural behaviour change, new sections or new governance logic

- **EXPERIMENTAL**: non-production testing version

Each prompt version should capture: who changed it, why, what test set was used, what success criteria changed, which approvals were granted, which systems are affected, and whether rollback is available. This is consistent both with enterprise prompt-governance practice and with formal management-system requirements for change control and auditable traceability.

### Future-evolution placeholders

To avoid rewriting DAIOS root prompts, reserve explicit extension blocks inside every master prompt.

| Placeholder | Purpose |
|---|---|
| [[FUTURE_STANDARD_CROSSWALK]] | Add new ISO/NIST/OWASP mappings |
| [[FUTURE_LOCAL_POLICY]] | Department or accreditation rules |
| [[FUTURE_MODEL_CONTROL]] | Model/provider-specific rules |
| [[FUTURE_SECURITY_CONTROL]] | New data protection or AI-security controls |
| [[FUTURE_INTEGRATION_TARGET]] | New DAIOS module or external system |
| [[FUTURE_LANGUAGE_PACK]] | Bangla/English/Japanese/Arabic prompt variants |
| [[FUTURE_EVALUATION_DATASET]] | Test corpus for regression testing |
| [[FUTURE_COMPLIANCE_PROFILE]] | Industry-specific profile, such as health or finance |

This modular design is consistent with TOGAF’s current modular, configurable approach and with your stated DAIOS principle that the architecture should absorb new practices without root-code disruption.

## Asset mapping, testing, KPIs and ninety-day roadmap

### Mapping to existing DAIOS assets

| DAIOS Asset | P00 role | P01 role | P03 role |
|---|---|---|---|
| Product Registry | duplication check, classification, merge recommendation | identify existing products | attach approved artefacts |
| Knowledge Vault | policy/evidence storage | current-state diagnostics and evidence | store controlled documents |
| Prompt Registry | prompt version and execution audit | same | same |
| Central Dashboard | governance status, queue metrics | intake workload, pain heatmap | document generation pipeline |
| Chairman Dashboard | risk, approval, duplication and delay visibility | departmental pressure trends | readiness and delivery status |
| Student360 | data classification and integration governance | input dependency for student workflows | documentation references for student-related modules |
| Revenue OS | commercialization checks | identify product vs internal utility | append revenue model artefacts |
| Marketplace | marketplace candidacy | early commercial signal | final packaging documents |
| DUDOS | institutional alignment rule | process ownership and admin policy | policy and service-alignment sections |

### Test plan

Prompt testing should happen at four layers.

#### Functional tests

Does the prompt return the required schema and section order?

#### Governance tests

Does it block or conditionally flag missing approvals, missing evidence and sensitive-data risks?

#### Quality tests

Does output remain grounded in inputs and avoid invention?

#### Regression tests

Does V1.1 preserve what V1.0 already did correctly?

This layered test approach is directly supported by NIST TEVV guidance and by AI RMF’s emphasis on measurement, documentation and independent review.

### Acceptance criteria

| Module | Acceptance criteria |
|---|---|
| P00 | 100% of executions return constitutional status, missing evidence list, next workflow and storage actions |
| P01 | 95% of pilot cases produce usable current-state diagnostics without analyst rewrite exceeding 20% |
| P03 | 90% of generated drafts pass format and traceability checks without major rework |
| All | Every execution logged, versioned and linked to registry records |

### KPI framework

| KPI | Definition | Target by day 90 |
|---|---|---|
| Prompt usage count | Number of governed executions | Rising trend with controlled adoption |
| Accuracy / acceptance rate | Outputs accepted without major rewrite | ≥ 80% for P01 and P03 pilots |
| Human revision rate | % requiring substantive human rewrite | ≤ 20% |
| Time saved | Reduction in manual discovery/document drafting time | ≥ 50% reduction vs baseline |
| Reuse rate | % of cases using existing assets or prior prompts | ≥ 40% |
| Duplicate prevention rate | Requests redirected away from duplicate development | ≥ 60% of detected duplicates resolved through reuse/merge |
| Governance compliance rate | Executions with complete audit and approval traces | 100% for restricted prompts |
| Anomaly closure SLA | Time to resolve flagged anomalies | ≤ 5 working days |
| Knowledge capture completeness | Outputs stored in required registry/vault | ≥ 95% |

### Ninety-day roadmap

#### Days 1–15

Freeze P00/P01/P03 schemas, metadata model, prompt IDs, approval flow, role matrix and storage conventions. Build the minimal Prompt Registry plus execution audit table. Finalise pilot dataset structure from the recent **145 student projects** and a small departmental automation set. This is the governance-foundation period and should not yet expand into wide functional sprawl.

#### Days 16–30

Implement P01 first, because poor intake causes downstream failure. Build intake UI, evidence attachment, diagnostic output schema and duplication pre-check. Train analysts and department focal points on standard inputs.

#### Days 31–45

Implement P00 next. Connect it to Product Registry search, Knowledge Vault search, approval rules and risk flags. Add decision output cards to the Central Dashboard and Chairman Dashboard.

#### Days 46–60

Implement P03. Start with Product Registration, BRD, SRS and ERD generation only. Do not expand to all document types immediately. Connect outputs to review workflows and registry storage.

#### Days 61–75

Pilot all three prompts against the 145-student-project dataset and at least 3 live departmental cases such as one registrar process, one dashboard request and one policy-driven billing or workflow case. Measure duplication findings, documentation sufficiency and human rewrite rate.

#### Days 76–90

Stabilise, retest, tune validation rules, approve V1.0 prompt set, publish operational SOPs, and declare DPOS controlled use for P00/P01/P03. Do not add new prompt families until these three reach predictable performance.

### Minimal team composition

| Role | Minimum FTE |
|---|---|
| Product Owner / Governance Lead | 0.5 |
| Business Analyst / Intake Designer | 1 |
| Backend Engineer / Workflow Integration | 1 |
| Frontend Engineer / UI | 1 |
| AI Engineer / PromptOps | 1 |
| QA / Test Analyst | 0.5 |
| Knowledge Manager / Prompt Librarian | 0.5 |
| Security / Risk Reviewer | 0.25 |
| PMO / Delivery Coordinator | 0.5 |

A lean pilot team is therefore roughly **6.25 FTE**. A comfortable execution team is **8–10 FTE** if you want faster dashboarding, multilingual support and deeper integration in the first ninety days.

### Indicative budget estimate

Because the prompt did not specify rate cards, cloud usage pattern, hosting model or internal staff costing, the following is an indicative implementation band:

| Delivery mode | Estimate |
|---|---|
| Lean internal pilot | 25,000–40,000 equivalent budget units |
| Recommended controlled rollout | 40,000–70,000 equivalent budget units |
| Accelerated multi-module rollout | 70,000–120,000 equivalent budget units |

The major variables are developer availability, whether you build or reuse a prompt-registry layer, multilingual requirements, dashboard complexity, and integration depth with existing DAIOS systems.

## Ready-to-use templates

### Prompt Registry entry template

| Field | Example |
|---|---|
| Prompt ID | P00-CONSTITUTION-ORCHESTRATOR-V1.0 |
| Prompt Name | Constitution Orchestrator |
| Module | P00 |
| Category | Governance and Constitution |
| Owner | Governance Office |
| Functional Owner | CTO / Product Office |
| Purpose | Constitutional review and approval decision |
| Input Schema Ref | SCHEMA-P00-V1 |
| Output Schema Ref | SCHEMA-P00-OUT-V1 |
| Risk Level | Restricted |
| Languages | EN, BN |
| Version | 1.0 |
| Status | Approved |
| Effective Date | 2026-07-17 |
| Next Review Date | 2026-10-17 |
| Approval Record | APPR-2026-0007 |
| Rollback Version | None |
| Usage Count | 0 |
| Success Score | 0 until pilot |
| Storage Links | Knowledge Vault / Prompt Registry refs |

### Evidence checklist template

| Evidence item | P00 | P01 | P03 | Mandatory rule |
|---|---|---|---|---|
| Problem statement | Yes | Yes | Source only | Mandatory |
| Existing solution search | Yes | Recommended | Source only | Mandatory for approval |
| Tracker or form sample | Recommended | Yes | Source only | Mandatory for diagnosis |
| Complaint/queue evidence | Recommended | Yes | Source only | Strongly recommended |
| Approval path | Yes | Recommended | Yes | Mandatory for production intent |
| Data classification | Yes | Yes | Yes | Mandatory if sensitive data involved |
| Integration intent | Yes | Yes | Yes | Mandatory |
| Stakeholder list | Yes | Yes | Yes | Mandatory |
| Assumption log | Yes | Yes | Yes | Mandatory |
| Review history | Output | Output | Output | Mandatory after execution |

### API contract table

| Field | Type | Required | Example |
|---|---|---|---|
| prompt_id | string | Yes | P01-INTAKE-DIAGNOSIS-V1.0 |
| execution_mode | string | Yes | sync |
| actor_id | string | Yes | user_034 |
| payload | object | Yes | {...} |
| evidence_refs | array | No | ["EV-001","EV-002"] |
| source_case_id | string | No | INT-2026-0042 |
| governance_required | boolean | Yes | true |
| response_format | string | Yes | json+markdown |
| language | string | Yes | en-GB |
| correlation_id | string | Yes | corr-20260717-0001 |

### RACI template

| Work item | R | A | C | I |
|---|---|---|---|---|
| Prompt drafting | Prompt Librarian / AI Engineer | Functional Owner | BA, Governance | PMO |
| Prompt testing | QA / AI Engineer | Product Owner | Governance, Security | PMO |
| Governance approval | Governance Officer | CTO/CGO | AI Gov, Security, ARB | Knowledge Manager |
| Prompt publication | Knowledge Manager | CGO | Product Owner | All relevant teams |
| Execution monitoring | Knowledge Manager / QA | Product Owner | Governance | Chairman Dashboard |
| Version update | AI Engineer / Prompt Librarian | Functional Owner | Governance, QA | PMO |

## Final recommendations and master execution prompts

The best next move is not to expand the library further before freezing these three prompts. P00, P01 and P03 are the constitutional base layer. If these are governed well, additional libraries such as P02 product strategy, P04 BRD library, P05 SRS library and P10 AI-agent engineering can inherit consistent validation rules. If they are weak, DAIOS will accumulate prompt sprawl rather than governed intelligence.

The most effective executive decision sentence for leadership is this:

**“DAIOS will not start from coding; it will start from governed intake, constitutional clearance, and reusable documentation. P01 captures reality, P00 decides legitimacy, and P03 turns approved truth into controlled artefacts.”**

Below are the final short **master execution prompts** your team can use to operationalise the rollout.

### Master prompt to implement P00

Act as the DAIOS Governance Implementation Office.

Implement P00 Governance and Constitution inside DPOS using the approved DAIOS philosophy, EADC, DUDOS and the standards mapping in this report.

Create:
1. Prompt registry record
2. Input form
3. Validation rules
4. Duplication search logic
5. Approval workflow
6. Risk flags
7. Output schema
8. Dashboard metrics
9. Knowledge Vault storage rule
10. Pilot test cases

Constraints:
- No request may bypass P00 for production, architecture, AI, competition, departmental automation or release-gating use cases.
- Every execution must be logged and auditable.
- Return implementation tasks in build order with owners, APIs, DB entities, UI screens, test cases and acceptance criteria.

### Master prompt to implement P01

Act as the DAIOS Intake and Diagnostic Transformation Office.

Implement P01 Intake and Diagnosis inside DPOS as the standard discovery workflow for any department, company, wing, office, academic unit or service team requesting automation, AI, dashboards or system redesign.

Create:
1. Intake form
2. Evidence uploader
3. Diagnostic schema
4. Queue and complaint analysis logic
5. Manual-tracker inventory model
6. Reuse and duplication checks
7. Integration opportunity map
8. Output storage and dashboard metrics
9. Pilot cases and acceptance criteria

Constraints:
- Do not design software before diagnostic completion.
- Force current-state evidence and missing-data disclosure.
- Always identify whether the request is local, shared, central reusable, academic or commercial.

### Master prompt to implement P03

Act as the DAIOS Documentation Control Office.

Implement P03 Documentation Generation inside DPOS as the controlled artefact-generation engine.

Create:
1. Document-type catalogue
2. Input traceability rules
3. Draft-generation workflow
4. Missing-input disclosure rules
5. Review and approval sequence
6. Knowledge Vault archival model
7. Product Registry attachment logic
8. Test criteria for BRD, SRS, ERD and Product Registration
9. Acceptance and release gates

Constraints:
- P03 must never fabricate facts.
- It may only draft from approved inputs, known DAIOS assets and marked assumptions.
- No document may be marked final without required reviews.

### Concluding note

This design is strong enough to support constitutional freeze because it gives DAIOS a stable prompt-operating base: **one governance prompt family, one intake prompt family, and one documentation prompt family**, each with explicit inputs, outputs, storage rules, versioning, review gates and future placeholders. It also maps cleanly to current international practice in AI governance, security, service management, software lifecycle control and organisational maturity. The remaining work is not conceptual; it is implementation discipline.

ISO/IEC 42001:2023 - AI management systems

ISO/IEC/IEEE 29148:2018 - Systems and software engineering — Life cycle processes — Requirements engineering

AI RMF Core - AIRC

Prompt Registry for LLMs & Agents | MLflow Agent Platform

ISO 9001:2015 - Quality management systems — Requirements

The NIST Cybersecurity Framework (CSF) 2.0 | NIST

OWASP Application Security Verification Standard (ASVS) | OWASP Foundation

Press Releases 2023 ISACA Updates CMMI Model with Three New Domains That Help Organizations Improve Quality

ISO/IEC/IEEE 12207:2026 - Systems and software engineering — Software life cycle processes

AI test, evaluation, validation and verification (TEVV) | NIST

The Open Group Announces Launch of the TOGAF® Standard, 10th Edition | www.opengroup.org
