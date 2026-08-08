# DAIOS P01 Intake and Diagnosis Master Framework

## Executive summary

This report defines the master prompt architecture and implementation plan for **P01 — Intake & Diagnosis**, the DAIOS entry point for any department, company, campus unit, business segment, academic wing, or student/faculty team requesting automation, software development, AI enablement, workflow improvement, dashboarding, CRM, analytics, or service redesign. The design assumes that **EADC** is the supreme control layer for AI development and responsible AI use, **DAIOS** is the governing constitution for software, SaaS, automation, AI, APIs, dashboards, agents, and commercialisable digital products, and **DUDOS** is the governing constitution for enterprise-wide institutional operations. By design, no initiative should move into design, coding, procurement, piloting, or deployment until it passes P01 intake, diagnosis, duplication review, constitutional mapping, and ownership confirmation. That mirrors the logic of software life cycle governance in ISO/IEC/IEEE 12207, service life cycle controls in ISO/IEC 20000-1, quality and continuous improvement in ISO quality guidance, product quality modelling in ISO/IEC 25010, AI management system controls in ISO/IEC 42001, and AI/cyber risk management in NIST AI RMF and NIST CSF 2.0.

The core operating decision is this: **P01 is not a form; it is a constitutional diagnostic engine**. A department does not merely “request software”. It declares its problem, pain points, current trackers, queues, complaints, evidence, ownership, data sources, policy constraints, accreditation needs, manual workarounds, and expected outcomes. DAIOS then performs a structured diagnosis: it searches for reuse, checks constitutional compliance, scores pain and urgency, inventories spreadsheets and trackers, detects duplicate efforts, identifies integration opportunities, classifies the initiative, and generates the next required documents and prompts. This implements your philosophy of **System Before People, Product Before Project, Revenue Before Activity, AI Before Manual Effort, Reuse Before Rebuild, Governance Before Scale, and Knowledge Capture Before Closure**.

The output of P01 is therefore not “a ticket”. It is a governed package consisting of: intake record, problem statement, current-state model, pain map, queue analysis, manual-tracker inventory, duplication/integration assessment, constitutional applicability, risk summary, recommended product classification, required documents, AI-versus-human work split, and approval path. Only after that package is accepted should the initiative enter BRD/SRS/ERD/DAD work, Product Registry, Student Product Factory, Faculty Innovation, DACJE, or the Product Factory pipeline. This is the cleanest way to stop repeated work, reduce informal pressure loops, and ensure every new need becomes a reusable organisational model rather than an isolated departmental fix.

**Assumptions used in this report**

- EADC, DAIOS Constitution, DUDOS, and accreditation requirements are the highest internal authorities, even where they were not directly queryable in this turn.

- Some earlier uploaded files were not queryable during this turn; this framework therefore consolidates your clearly stated DAIOS requirements from the conversation together with current public standards and implementation best practice.

- No specific tech stack, cloud, or budget currency constraint has been fixed.

- The target operating language for delivery artefacts is English, with Bengali labels where they improve usability for departmental users.

## Foundational alignment and operating doctrine

P01 must be designed as a **gated governance service** rather than an optional administrative form. In DAIOS terms, it sits after request initiation but before product design. In EADC terms, it ensures no AI-enabled or AI-assisted solution bypasses governance, data review, risk review, or explainability requirements. In DUDOS terms, it ensures the request is aligned with institutional operating policy, academic policy, service obligations, and department-level ownership. In accreditation-sensitive cases, P01 should also capture the applicable regulatory or standards basis upfront, because once a system is built wrongly, retrofitting compliance is far more expensive and weaker. This is consistent with ISO/IEC 42001’s requirement for an AI management system with responsible development and continuous improvement, together with NIST AI RMF’s emphasis on governing, mapping, measuring, and managing AI risks across the lifecycle.

P01 should also be treated as the **official system-of-record for problem discovery**. That is important because your core organisational issue is not a shortage of effort; it is a shortage of structured intake, consistent diagnosis, reuse discipline, and traceable follow-up. ISO/IEC/IEEE 12207 explicitly frames software life cycle work around defined processes, activities, and tasks across conception, development, operation, maintenance, and retirement, while ISO/IEC 20000-1 requires planning, design, transition, delivery, and improvement of services. P01 becomes the “conception and qualification” layer that feeds those downstream processes correctly.

The architectural principle is straightforward:

- **One intake taxonomy**

- **One diagnosis logic**

- **One duplication check**

- **One integration check**

- **One constitutional check**

- **One productisation path**

- **One knowledge archive**

- **Many departmental use cases**

This is aligned with the ISO quality process approach and continuous improvement model, which emphasises planned processes, performance review, and acting on findings, and with ISO/IEC 25010’s view that product quality characteristics should be specified and evaluated explicitly rather than assumed.

The mandatory policy statement for P01 should therefore be:

**No department automation, no system change, no workflow digitalisation, no AI assistant, no dashboard, no tracker replacement, and no new software build may proceed unless it is first registered and diagnosed through DAIOS P01 and cleared against EADC, DAIOS, DUDOS, security, ownership, and integration requirements.**

## Intake model, templates, and diagnostic logic

### P01 purpose and scope

P01 should accept the following request types:

- departmental automation request

- software development request

- AI assistant / chatbot / agent request

- dashboard / analytics request

- process redesign request

- complaint / queue overload remediation

- Excel/CSV tracker replacement

- approval workflow automation

- CRM / ticketing / service desk need

- student/faculty academic solution seeking institutional adoption

- capstone or competition solution seeking productisation

- mobile app or self-service need

- API / integration request

- compliance / accreditation system need

- duplicate solution merger request

- legacy tracker or shadow-system migration request

### Exact intake template

The intake form should be compact on screen but rich in structure. It should use progressive disclosure: a short first screen for registration, then contextual sections based on request type.

| Field Group | Field Name | Bengali label | Type | Required | Validation rule | Notes |
|---|---|---|---|---|---|---|
| Registration | Intake ID | আবেদন আইডি | Auto | Yes | system generated | immutable |
| Registration | Request title | অনুরোধের শিরোনাম | Text | Yes | 10–120 chars | should state problem, not solution |
| Registration | Request type | অনুরোধের ধরন | Dropdown | Yes | controlled list | drives dynamic sections |
| Ownership | Department / unit | বিভাগ / ইউনিট | Lookup | Yes | must exist in org master | links to DUDOS org tree |
| Ownership | Requestor name | আবেদনকারী | Text | Yes | employee/student/faculty/vendor | must map to identity |
| Ownership | Sponsor / approver | অনুমোদনকারী | Lookup | Yes | must have decision right | no orphan requests |
| Ownership | Process owner | প্রক্রিয়া মালিক | Lookup | Yes | named role mandatory | not optional |
| Problem | Problem statement | সমস্যার বিবরণ | Long text | Yes | 100–2,000 chars | must describe pain, not software wish |
| Problem | Why now | এখন কেন | Long text | Yes | evidence-based | urgency trigger |
| Problem | Current method | বর্তমান পদ্ধতি | Long text | Yes | describe step flow | includes manual/WhatsApp/Excel/email |
| Problem | Current tools | বর্তমান টুল | Multi-select | Yes | Excel/Google Sheets/email/paper/ERP/etc | inventory anchor |
| Volume | Cases per day/week/month | কাজের পরিমাণ | Numeric set | Yes | >0 | used in effort and ROI |
| Volume | Peak load period | ব্যস্ত সময় | Text | No | optional | admissions, registration, exams |
| Queue | Current queue length | অপেক্ষমাণ সংখ্যা | Number | No | >=0 | backlog estimate |
| Queue | SLA / target time | নির্ধারিত সময় | Text/Number | No | structured if exists | e.g. 24 hrs, 3 days |
| Complaints | Complaint types | অভিযোগের ধরন | Multi-select + text | Yes | at least one if complaint-based | mapped taxonomy |
| Complaints | Top 5 complaints | প্রধান ৫ অভিযোগ | Structured list | No | optional but recommended | for analytics |
| Trackers | Existing tracker files | বর্তমান ট্র্যাকার | File refs | Yes | CSV/XLS/XLSX accepted | scanned and catalogued |
| Trackers | Tracker owners | ট্র্যাকার মালিক | Text/list | Yes | at least one | shadow system detection |
| Data | Data sources | ডেটা উৎস | Multi-select | Yes | master list + custom | database, API, email, forms, file |
| Data | Personal/sensitive data | সংবেদনশীল ডেটা | Multi-select | Yes | category required | student, HR, finance, health |
| Integration | Systems touched | সংযুক্ত সিস্টেম | Multi-select | Yes | DAIOS integration list | Student360, DUDOS, CRM, etc |
| Integration | Desired integration method | সংযুক্তির ধরন | Multi-select | No | API/webhook/shared DB/etc | preliminary |
| Governance | Policy basis | নীতিগত ভিত্তি | Multi-select | Yes | institutional policy / academic regulation / accreditation | constitutional mapping |
| Governance | Accreditation relevance | অ্যাক্রেডিটেশন | Yes/No + detail | Yes | detail if yes | programme/department use |
| Outcome | Expected outcome | প্রত্যাশিত ফলাফল | Long text | Yes | measurable | time, cost, accuracy, staffing |
| Outcome | People reduction estimate | জনবল হ্রাস | Number + narrative | No | justify if entered | evidence required later |
| Outcome | Revenue / value potential | রাজস্ব / মূল্য | Structured | No | internal value or external revenue | mandatory for commercial requests |
| AI | AI requested | AI প্রয়োজন | Yes/No | Yes | if yes, open AI section | triggers EADC |
| AI | AI use case | AI ব্যবহার | Multi-select | Conditional | search, assistant, analytics, prediction | no free-form only |
| Risks | Known risks | ঝুঁকি | Long text | No | optional initial capture | enriches later |
| Attachments | SOP/process docs | এসওপি / নথি | File refs | No | PDF/DOC/XLS/IMG | OCR/parse if needed |
| Attachments | Screenshots/photos | ছবি / স্ক্রিনশট | File refs | No | image accepted | useful for shadow workflow |
| Declaration | Declaration of accuracy | ঘোষণা | Checkbox | Yes | must accept | auditable |
| Declaration | Reuse search done | পুনঃব্যবহার খোঁজা হয়েছে | Yes/No | Yes | if yes, capture results | search-first enforcement |

### UI/UX notes

The interface should use a five-stage wizard:

- **Registration**

- **Problem & Current State**

- **Data & Trackers**

- **Governance & Integration**

- **Outcome & Declaration**

Within the form, the user should see hints in both English and Bengali, for example:

- **Problem Statement / সমস্যার বিবরণ**

- **Current Tracker Files / বর্তমান Excel বা Tracking Sheet**

- **Known Queue or Complaint Type / অভিযোগ বা Queue-এর ধরন**

- **Expected Measurable Improvement / কী measurable উন্নতি হবে**

An intake request should never show “Build me a software system” as the starting mental model. Instead, each page should continuously reframe the request around process, data, pain, ownership, and measurable outcomes.

### Diagnostic checklist and automated rules

After the request is submitted, DAIOS should run a structured diagnostic checklist.

#### Process mapping rules

- Detect whether the requestor has described inputs, steps, approvals, exceptions, outputs, and hand-offs.

- If fewer than three explicit steps are described, ask for process clarification.

- Convert the current narrative into a draft BPM-style process map.

- Flag missing owner, missing SLA, missing exception handling, and missing closure state.

#### Pain-point scoring rules

Use a 100-point pain score.

| Dimension | Weight | Scoring rule |
|---|---|---|
| Volume pressure | 15 | higher transaction load, higher pain |
| Delay / backlog | 15 | queue length and target miss |
| Complaint severity | 15 | repeated complaints and escalation |
| Manual dependency | 15 | number of manual hand-offs, spreadsheet reliance |
| Compliance risk | 10 | policy/accreditation exposure |
| Data fragmentation | 10 | multiple trackers, duplicate entry |
| Leadership visibility gap | 5 | no dashboard / no reportability |
| Revenue / value leakage | 5 | missed sales, billing, collections, conversion |
| Customer/student experience risk | 5 | response inconsistency, confusion |
| Reuse opportunity gap | 5 | known solution exists but not reused |

Suggested thresholds:

- **0–24**: low-priority enhancement

- **25–49**: process improvement candidate

- **50–69**: automation-worthy case

- **70–84**: urgent transformation case

- **85–100**: executive priority / escalation

#### Manual-tracker inventory rules

For every uploaded spreadsheet, CSV, form, or sample tracker, DAIOS should extract:

- file name

- owner

- last updated date

- number of tabs / sheets

- core columns

- duplicated data fields

- contact or approval fields

- status fields

- personally identifiable or sensitive information

- whether the file appears authoritative or unofficial

- whether similar data already exists in a governed system

This matches DAMA guidance that data governance, metadata, security, architecture, integration, and quality are foundational for enterprise-scale data use and trustworthy AI.

#### Queue and complaint analysis rules

For queue-based cases, require:

- entry source

- queue owner

- queue item type

- queue ageing buckets

- re-open rate

- escalation count

- abandonment or drop-off count

- average handling time

- peak-hour or peak-day pattern

- breach count against target time

For complaint-based cases, classify complaints by:

- delay

- wrong information

- no response

- duplicate follow-up

- payment/billing issue

- document issue

- access issue

- system failure

- service attitude issue

- policy ambiguity

- workflow confusion

#### Excel/CSV ingestion rules

- Accept .csv, .xls, .xlsx, .ods.

- Auto-profile columns and infer types.

- Detect probable primary keys and duplicate rows.

- Identify date columns, status columns, person identifiers, monetary fields, SLA timestamps.

- Reject password-protected files unless authorised workflow is provided.

- Flag files containing sensitive categories without an approved basis.

- Store the file fingerprint/hash and metadata; never silently overwrite prior versions.

- Link every ingested file to the Knowledge Vault and the intake record.

### Automated pre-compliance checks

Before any recommendation is issued, P01 should run mandatory checks.

| Check | What DAIOS should do | Output |
|---|---|---|
| Duplication check | Search Product Registry, Knowledge Vault, Prompt Registry, student archive, faculty archive | duplicate / similar / reusable candidate |
| Integration feasibility | Compare requested process with known systems | high / medium / low feasibility |
| Ownership check | Verify process owner, data owner, product sponsor | owner complete / missing |
| Security & privacy | Detect personal/financial/health/student/HR data classes | risk tier |
| Policy & accreditation | Match request against declared policy categories | required controls |
| AI governance | If AI requested, activate EADC checklist | allowed / limited / review required |
| Data quality risk | Assess fragmented sources and tracker trustworthiness | low / medium / high |
| Revenue/value relevance | Detect recurring revenue or measurable institutional value potential | none / internal value / commercial |
| Student360/enterprise impact | Detect likely cross-campus or cross-stakeholder use | local / multi-unit / enterprise |
| Shadow system risk | Detect unofficial trackers doing official work | contained / active risk |

Any request failing ownership, privacy, or duplication review should not move forward automatically.

## Prompt library and master prompts for P01

### Prompt library structure for P01

P01 should sit under the DPOS library as:

- **P01-A** Intake Summary

- **P01-B** Current-State Diagnostic

- **P01-C** Process Pain & Queue Analysis

- **P01-D** Manual-Tracker Inventory and Data Profiling

- **P01-E** Duplication and Reuse Review

- **P01-F** Integration Feasibility Review

- **P01-G** AI-vs-Human Work Split

- **P01-H** MVP and Product Classification

- **P01-I** Commercialisation and Value Potential

- **P01-J** Required Documents Generator

- **P01-K** Pre-Approval Decision Note

- **P01-L** Knowledge Vault Tagger

### Master prompt design principle

Every prompt should follow the same skeleton:

- **Identity**

- **Mission**

- **Authoritative references**

- **Input schema**

- **Analysis instructions**

- **Decision rules**

- **Output schema**

- **Governance stop rules**

- **Knowledge capture instructions**

- **Future anchors**

### Universal P01 orchestrator prompt

PROMPT-ID: P01-ORCH-001-V1.0
TITLE: DAIOS P01 Intake and Diagnosis Orchestrator

Act as the Principal AI Architect, Product Officer, Governance Lead, Enterprise Business Analyst, Data Governance Analyst, Solution Architect, Service Designer, and Intake Review Board for DAIOS.

Authoritative Internal References:
- EADC
- DAIOS Constitution
- DUDOS
- DAIOS Operating Model
- Product Registry
- Knowledge Vault
- Prompt Registry
- Student360 integration rules
- Accreditation and institutional policy overlays
- AI Governance Handbook
- Enterprise RACI and Decision Rights Matrix

Mission:
Analyse one department automation or system-development request and produce a constitution-compliant, evidence-based intake diagnosis package. Do not generate software design or code unless the request passes intake and pre-compliance rules.

Mandatory Evaluation Logic:
1. Understand the real problem, not only the requested solution.
2. Map the current process, manual steps, queues, complaints, and trackers.
3. Profile uploaded files and identify shadow systems.
4. Search for duplicate or reusable solutions across DAIOS.
5. Assess integration opportunities and enterprise fit.
6. Check ownership, data sensitivity, privacy, AI applicability, and accreditation impact.
7. Score pain, urgency, reuse potential, and implementation readiness.
8. Recommend whether to archive, clarify, improve, integrate, productise, or reject.

Hard Stop Rules:
- Missing process owner
- Missing sponsor/approver
- High-risk sensitive data without basis
- Duplicate solution with no justification
- AI requested without EADC applicability check
- No measurable outcome defined
- Attempt to bypass constitutional review

Input Schema:
{
  "intake_id": "",
  "request_type": "",
  "department": "",
  "problem_statement": "",
  "current_process": "",
  "current_tools": [],
  "queue_metrics": {},
  "complaint_summary": [],
  "uploaded_files": [],
  "data_sources": [],
  "systems_touched": [],
  "policy_basis": [],
  "accreditation_relevance": "",
  "expected_outcomes": [],
  "ai_requested": false,
  "attachments_text": ""
}

Required Output Sections:
- Executive intake summary
- Current-state process map summary
- Pain score and explanation
- Queue and complaint findings
- Manual-tracker inventory findings
- Duplication and reuse candidates
- Integration feasibility
- Data/privacy/security observations
- AI applicability and EADC trigger rating
- Product classification
- MVP readiness
- Required documents before design/coding
- Decision recommendation
- Approval path
- Knowledge Vault tags
- Placeholder anchors for future updates

Output Format:
Return a structured report in clear enterprise English with explicit pass/fail flags.

### Prompt catalogue with schemas and example prompts

| Prompt ID | Purpose | Minimum inputs | Key outputs | Example invocation |
|---|---|---|---|---|
| P01-A | Intake summary | title, dept, problem, current method | executive summary, missing info list | “Summarise this Registrar automation intake and list missing facts before review.” |
| P01-B | Current-state diagnostic | process narrative, volumes, owners | process map summary, bottlenecks | “Diagnose the current admissions complaint-handling workflow from this intake and file set.” |
| P01-C | Pain & queue analysis | queue, SLA, complaints | pain score, SLA gaps, ageing insight | “Analyse queue pressure and complaint risk for this medical service request.” |
| P01-D | Manual-tracker inventory | files, descriptions | tracker catalogue, data fields, shadow-system risk | “Inventory all Excel-based trackers uploaded by HR and identify overlaps.” |
| P01-E | Duplication review | request summary, integration list | existing products, reuse options, duplicate score | “Check whether this dashboard request duplicates Central Dashboard capabilities.” |
| P01-F | Integration review | systems touched, desired outcomes | integration map, dependency and feasibility level | “Assess integration feasibility with Student360, CRM and Revenue OS.” |
| P01-G | AI-human split | tasks, data, controls | AI candidate tasks, human-required tasks, risk flags | “Decide which intake workflow tasks can be AI-assisted under EADC.” |
| P01-H | MVP readiness | features, target users, reuse data | maturity classification, MVP boundary | “Classify whether this request is a workflow fix, MVP, or enterprise product.” |
| P01-I | Commercialisation/value | users, pricing/value assumptions | internal value score, revenue potential | “Estimate whether this registrar module has internal-only value or SaaS potential.” |
| P01-J | Required docs | request type, sensitivity, scale | document pack checklist | “Generate mandatory documents before BRD/SRS for this request.” |
| P01-K | Decision note | full diagnostic package | approval note, conditions, blockers | “Write the pre-approval note for Architecture Review Board.” |
| P01-L | Knowledge tagging | all findings | ontology tags, storage path, version labels | “Create Knowledge Vault tags and archival metadata for this intake.” |

### Example specialist prompts

**P01-E Duplication and Reuse Review**

Act as the DAIOS Non-Duplication and Reuse Review Engine.

Analyse this intake against Product Registry, Knowledge Vault, Prompt Registry, Central Dashboard, Student360, DUDOS, CRM, Revenue OS, and student/faculty solution archives.

Determine:
- direct duplication
- partial overlap
- reusable component opportunities
- required integration instead of rebuild
- exceptions where new development is justified

Return:
1. duplicate score (0–100)
2. reuse candidates
3. merge recommendations
4. justification for any new build
5. governance stop rule if duplication is unjustified

**P01-G AI vs Human Task Split**

Act as the EADC-compliant AI Task Allocation Board.

Inputs:
- process steps
- data sensitivity classes
- queue metrics
- target outcomes
- required approvals

For each step, decide:
- AI can do fully
- AI can assist human
- human must do
- forbidden for AI without additional control

Explain why using:
- risk
- explainability
- sensitivity
- legal/policy constraints
- quality requirements

Output a task allocation table with recommended controls.

**P01-J Required Documents Generator**

Act as the DAIOS Documentation Gatekeeper.

Based on this intake, generate the exact mandatory document sequence before any design or coding:
- Product Registration
- DAD
- MPIF
- BRD
- SRS
- ERD
- API Spec
- Security Review
- Test Strategy
- Integration Map
- AI Governance Checklist
- Commercialisation Note
- Accreditation Traceability Matrix

Return:
- mandatory
- conditional
- not required
- owner
- approval authority
- due stage

## Workflow, architecture, APIs, data model, and Knowledge Vault linkage

### System workflow

|   |
|---|

### Required screens

| Screen | Purpose | Key actions |
|---|---|---|
| P01 Dashboard | intake overview | filter by status, department, pain score |
| New Intake Wizard | request registration | create intake, upload files, save draft |
| Attachment Profiler | tracker review | preview columns, detect sensitive data |
| Diagnostic Results | current-state outputs | pain score, bottlenecks, duplicate matches |
| Pre-Compliance Review | governance checks | ownership, privacy, duplication, integration |
| Owner Review | business validation | confirm or amend findings |
| Governance Review | formal approval | approve, conditionally approve, reject |
| Productisation Handoff | move to next stage | create product record and document tasks |
| Knowledge Vault Linker | archive and reuse | tag, classify, save version |
| KPI Dashboard | operational metrics | volume, reuse, duplication, TTD, impact |

### API endpoints

| Method | Endpoint | Purpose |
|---|---|---|
| POST | /api/p01/intakes | create intake |
| GET | /api/p01/intakes/{id} | retrieve intake |
| PATCH | /api/p01/intakes/{id} | update intake |
| POST | /api/p01/intakes/{id}/attachments | upload files |
| POST | /api/p01/intakes/{id}/scan | trigger automated analysis |
| GET | /api/p01/intakes/{id}/diagnostic | fetch diagnostic report |
| GET | /api/p01/intakes/{id}/duplicates | fetch reuse/duplicate results |
| GET | /api/p01/intakes/{id}/integration | fetch integration review |
| POST | /api/p01/intakes/{id}/review/owner | owner review submission |
| POST | /api/p01/intakes/{id}/review/governance | governance decision |
| POST | /api/p01/intakes/{id}/handoff/product | create downstream product item |
| POST | /api/p01/intakes/{id}/knowledge/archive | archive knowledge item |
| GET | /api/p01/metrics | dashboard KPIs |

### Webhooks and event triggers

| Trigger | Event | Consumer |
|---|---|---|
| Intake created | p01.intake.created | dashboard, notifier |
| File uploaded | p01.file.uploaded | parser, profiler |
| Scan completed | p01.scan.completed | reviewer queues |
| Duplicate found | p01.duplicate.flagged | governance, product office |
| Sensitive data detected | p01.sensitive.flagged | security/privacy office |
| Approved | p01.approved | Product Registry, doc generator |
| Rejected | p01.rejected | archive, notifier |
| Archived | p01.archived | Knowledge Vault |
| Handoff completed | p01.handoff.done | PMO / build queue |

### Integration methods

P01 should support all six integration patterns you specified:

- **API** for governed, structured system-to-system exchange

- **Webhook** for event-driven notifications and downstream task creation

- **Shared DB** only for tightly governed internal read models, not the default

- **Event bus** for enterprise-wide workflow and dashboard updates

- **Plugin** for installable departmental modules within DAIOS

- **SSO** for identity and role inheritance

- **File exchange** only as a controlled bridge for legacy departments and student/project uploads

### Core database entities

|   |
|---|

### Metadata taxonomy for Knowledge Vault

P01 should not archive free text only. It should create governed metadata.

| Taxonomy dimension | Example values |
|---|---|
| Domain | admission, registrar, HR, finance, medical, library, CRM |
| Request type | automation, dashboard, AI assistant, tracker replacement |
| Stakeholder | student, faculty, staff, parent, customer, vendor |
| Problem class | delay, queue overload, complaint, duplication, visibility gap |
| Process area | intake, approval, billing, document issue, reporting |
| Data sensitivity | public, internal, confidential, student, HR, finance, health |
| Product class | local utility, academic prototype, MVP, institutional product |
| Reuse status | none, reusable, merge candidate, duplicate, archived |
| Integration target | Student360, DUDOS, CRM, KCX, Revenue OS, Central Dashboard |
| Compliance basis | EADC, DAIOS, DUDOS, accreditation, ISO security overlay |
| Lifecycle status | draft, diagnosed, under review, approved, handed off, archived |
| Version | v1.0, v1.1, v2.0 |
| Confidence | low, medium, high |
| Future anchor | ANCHOR-POLICY, ANCHOR-AI, ANCHOR-ACCREDITATION, ANCHOR-DATA |

### ASCII wireframe mockups

**New intake wizard**

+----------------------------------------------------------------------------------+
| DAIOS P01 - New Intake / নতুন আবেদন                                              |
+----------------------------------------------------------------------------------+
| Step 1 of 5: Registration                                                        |
|----------------------------------------------------------------------------------|
| Request Title *                 [______________________________________________] |
| Request Type *                  [Department Automation v]                        |
| Department / Unit *             [Registrar Office v]                            |
| Requestor *                     [______________________________________________] |
| Sponsor / Approver *            [______________________________________________] |
| Process Owner *                 [______________________________________________] |
|----------------------------------------------------------------------------------|
| [Save Draft]                                                  [Next >]          |
+----------------------------------------------------------------------------------+

**Diagnostic review screen**

+------------------------------------------------------------------------------------------------+
| DAIOS P01 Diagnostic Result                                                                     |
+------------------------------------------------------------------------------------------------+
| Intake ID: P01-2026-00124     Department: Registrar     Status: Governance Review              |
|------------------------------------------------------------------------------------------------|
| Pain Score: 78/100   | Duplicate Score: 62/100 | Integration Feasibility: High                |
|------------------------------------------------------------------------------------------------|
| Executive Summary                                                                            |
| - Manual tracker dependency across 4 Excel files                                              |
| - Average processing time 3.8 days against 1-day target                                       |
| - Frequent complaints: delay, status visibility, duplicate document requests                  |
|                                                                                                |
| Duplicate / Reuse Candidates                                                                   |
| [x] Central Dashboard widgets                                                                  |
| [x] Existing Student360 identity & profile service                                             |
| [ ] New local file repository                                                                  |
|                                                                                                |
| Mandatory Stop Flags                                                                           |
| [!] No approved data owner                                                                     |
| [!] Financial data classification not confirmed                                                 |
|                                                                                                |
| Recommended Next Step                                                                          |
| [Approve with Conditions] [Return for Clarification] [Reject] [Archive]                        |
+------------------------------------------------------------------------------------------------+

## Governance, KPIs, roadmap, pilot, and security controls

### Governance and approval rules

P01 should be governed by a lightweight but binding chain:

- **Requestor** submits the need

- **Process Owner** confirms the current state and problem reality

- **Department Head / Sponsor** confirms priority and budget intent

- **P01 Diagnostic Engine** runs its automated analysis

- **Security/Privacy reviewer** reviews risk if sensitive data is involved

- **Product / Architecture reviewer** checks reuse, fit, and classification

- **Governance approver** decides: clarify, reject, merge, pilot, productise

Every change to the intake, uploaded evidence, reviewer decision, and generated prompt should be audit logged. That aligns with ISO/IEC 42001 traceability expectations, NIST AI RMF governance expectations, and NIST CSF 2.0’s inclusion of **Govern** as a first-class cybersecurity function.

### Audit trail and versioning

Every intake record should store:

- who created it

- who edited it

- which files were uploaded

- what rules were triggered

- which duplicate matches were found

- which prompt versions were used

- which reviewer made which decision

- what changed between versions

- which downstream module was created

Versioning should follow:

- **INTAKE-P01-YYYY-NNNN-V1.0**

- **PROMPT-P01-X-XXX-V1.0**

- **DIAG-P01-YYYY-NNNN-V1.0**

### Placeholder anchors for future updates

To avoid rewriting the root design, every P01 output and prompt should carry reserved anchors:

- ANCHOR-POLICY-01 for new institutional policies

- ANCHOR-ACCREDITATION-01 for new accreditation or regulatory rules

- ANCHOR-AI-01 for new AI/EADC controls

- ANCHOR-DATA-01 for new privacy/security categories

- ANCHOR-INTEGRATION-01 for new DAIOS systems

- ANCHOR-COMMERCIAL-01 for new revenue/commercialisation requirements

That operationalises your “zero-maintenance continuous self-correction” principle. The architecture remains stable; only the controlled knowledge, rules, and prompts evolve.

### KPI set and dashboards

| KPI | Definition | Dashboard |
|---|---|---|
| Intake volume | new requests by period | P01 operations dashboard |
| Reuse rate | % of requests satisfied by reuse/integration | product office dashboard |
| Duplication rate | % of requests found to duplicate existing assets | governance dashboard |
| Time to decision | average days from submission to formal decision | leadership dashboard |
| Clarification rate | % returned due to missing data | intake quality dashboard |
| Sensitive-data hit rate | % involving protected data classes | security dashboard |
| Estimated vs actual effort variance | post-handoff variance | PMO dashboard |
| Automation impact | measured reduction in time/manual steps/roles | value dashboard |
| Productisation rate | % of approved intakes entering formal product pipeline | product dashboard |
| Archive and knowledge coverage | % of intakes fully tagged and archived | Knowledge Vault dashboard |
| Student contribution conversion | student projects moved into institutional use | academic innovation dashboard |
| Commercial potential identification rate | requests tagged with external/internal value potential | revenue dashboard |

### Team roles and RACI

| Role | Minimum team | Recommended team | Ideal team |
|---|---|---|---|
| Product owner | 1 shared | 1 dedicated | 1 dedicated |
| Business analyst / service designer | 1 | 2 | 3 |
| Solution architect | 0.5 FTE | 1 | 2 |
| AI/governance analyst | 0.5 FTE | 1 | 2 |
| Data engineer / parser engineer | 0.5 FTE | 1 | 2 |
| Backend engineer | 1 | 2 | 3 |
| Frontend engineer | 1 | 2 | 2 |
| QA / test engineer | 0.5 FTE | 1 | 2 |
| Security/privacy reviewer | shared | 0.5–1 | 1 |
| Knowledge manager | shared | 1 | 1 |
| PMO / implementation coordinator | shared | 1 | 1 |
| Student assistants | optional | 2–4 | 5–10 |

**High-level RACI**

| Activity | Requestor | Process Owner | Product Owner | Architect | Security | Governance Approver | Knowledge Manager |
|---|---|---|---|---|---|---|---|
| Submit intake | R | C | I | I | I | I | I |
| Confirm current process | C | R | I | C | I | I | I |
| Run diagnostic | I | C | A | R | C | I | C |
| Duplication review | I | I | A | R | I | C | C |
| Privacy/security review | I | I | C | C | R | C | I |
| Approval decision | I | C | C | C | C | A | I |
| Archive and tagging | I | I | I | I | I | I | R |

### Implementation roadmap

| Phase | Timeline | Primary deliverables |
|---|---|---|
| Phase A | Days 1–30 | policy freeze, P01 taxonomy, intake form, governance rules, prompt drafts |
| Phase B | Days 31–60 | file ingestion, diagnostic engine MVP, duplication search, dashboard prototype |
| Phase C | Days 61–90 | review workflows, API layer, Knowledge Vault linkage, pilot run |
| Phase D | Days 91–180 | enterprise rollout, dashboard hardening, student archive linkage, analytics and optimisation |

#### Detailed phase view

**30-day phase**

- freeze P01 policy

- create requested fields and validation rules

- create initial ontology and metadata

- define stop rules

- publish prompts P01-A to P01-L

- create first dashboard

**60-day phase**

- implement upload and profiling

- implement duplication search across known registries

- implement pain score engine

- implement owner review and governance decision flow

- connect Knowledge Vault

**90-day phase**

- run pilot on 145 student projects and 2–3 real departmental cases

- calibrate scoring, duplicate thresholds, and clarity rules

- implement basic analytics

**180-day phase**

- make P01 mandatory

- integrate with Product Registry, DACJE, Student Product Factory, Faculty Innovation

- establish ARB/PMO/Chairman reporting

- shift shadow requests away from email/WhatsApp into P01

### Budget model

Because no specific currency was fixed, the most robust estimate is in **Budget Units (BU)** where **1 BU = one fully loaded average professional team-month in your environment**.

| Delivery model | Estimated range |
|---|---|
| Lean MVP | 18–24 BU |
| Recommended enterprise-ready MVP | 32–45 BU |
| Ideal enterprise rollout with analytics, student archive linkage, and advanced security | 55–75 BU |

Suggested cost distribution:

- product, BA, governance: **20–25%**

- engineering: **35–45%**

- data parsing / ingestion / AI logic: **10–15%**

- QA/security/compliance: **10–15%**

- PMO/change management/training: **8–12%**

- contingency: **10%**

### Pilot plan using 145 student projects

The 145 student projects should be treated as a retrospective stress test for P01 and DACJE.

**Pilot steps**

- Collect available title, department, mentor, presentation, code, docs, and category.

- Create a simplified P01 intake record for each project.

- Run duplication and reuse review.

- Classify each project into:

- idea

- academic project

- prototype

- MVP

- institutional product

- marketplace candidate

- Identify:

- which projects solved real operational pain

- which projects duplicated existing work

- which could integrate into DAIOS

- which lacked documentation

- which had revenue or institutional value potential

- Push top candidates into Student Product Factory/Product Registry.

- Archive the rest with reusable knowledge tags.

**Expected outputs**

- top 20 reuse candidates

- top 10 institutional product candidates

- top 5 marketplace or startup candidates

- duplication map

- documentation gap report

- student capability heatmap

- prompt tuning feedback for P01 and DACJE

### Security, privacy, and compliance checklist

P01 should adopt a layered control approach.

**Software/service lifecycle controls**

- lifecycle stage traceability

- service transition and improvement controls

- defined acceptance and closure states

- quality characteristics for usability, reliability, security, maintainability, and portability

These align with ISO/IEC/IEEE 12207, ISO/IEC 20000-1, and ISO/IEC 25010.

**AI governance controls**

- AI purpose declaration

- model/provider declaration

- prompt version control

- human oversight requirement

- explainability note

- misuse/hallucination risk assessment

- output logging and review

- continuous improvement and incident learning

These align with ISO/IEC 42001 and NIST AI RMF.

**Cybersecurity controls**

- identity and access control

- least privilege and role-based permissions

- audit logs

- cryptography / secure transport

- secure configuration

- secure-by-design review

- logging and monitoring

- vulnerability management

- privacy-aware retention

- incident response handoff

NIST CSF 2.0 frames cyber risk around Govern, Identify, Protect, Detect, Respond, and Recover, while OWASP recommends ASVS as the verifiable standard for application security and positions the Top 10 as awareness baseline rather than a complete security programme.

**Academic and accreditation overlay**

Where a request touches academic processes, P01 should require:

- programme/department context

- learning or service objective

- accreditation relevance

- explainability requirement

- evidence retention requirement

- faculty/departmental validation

- student data classification

- assessment and audit readiness

## Recommended constitutional freeze language and next-step prompts

The cleanest way to freeze P01 constitutionally is to add one binding clause to the DAIOS implementation manual:

**Every department automation, software development, AI solution, dashboard, workflow digitisation, tracker replacement, student project seeking institutional adoption, and faculty solution seeking implementation must begin with DAIOS P01 Intake & Diagnosis. P01 is the sole authorised gateway for problem discovery, duplication review, integration review, constitutional mapping, and pre-approval diagnosis. No downstream build, procurement, pilot, or deployment activity may commence until P01 issues an approval outcome or an approval-with-conditions outcome.**

### Chairman-grade master execution prompt for P01 implementation

Act as the Principal AI Architect, Chief Product Officer, Chief Governance Officer, Service Transformation Lead, Data Governance Lead, Security and Privacy Control Officer, Academic Innovation Integrator, and Knowledge Vault Designer for DAIOS.

Your task is to design and implement DAIOS P01 — Intake & Diagnosis as the mandatory gateway for any department automation request, software development request, AI request, dashboard request, tracker replacement, workflow redesign, academic solution adoption, or service transformation initiative.

Authoritative references:
- EADC
- DAIOS Constitution
- DUDOS
- DAIOS Operating Model
- Enterprise RACI Matrix
- Decision Rights Matrix
- Product Registry
- Knowledge Vault
- Prompt Registry
- AI Governance Handbook
- DACJE
- Student Product Factory
- Faculty Innovation Framework
- Central Dashboard
- Student360 and enterprise integration catalogue

Mission:
Replace unstructured departmental requests and repeated work with one governed, searchable, diagnosable intake engine that automatically identifies pain points, queues, complaints, trackers, duplicate work, integration opportunities, constitutional obligations, and required next documents.

Generate in exact order:
1. P01 governance policy
2. exact intake form fields and validation rules
3. dynamic UI sections by request type
4. diagnostic engine logic and scoring model
5. file ingestion and tracker inventory rules
6. duplication and integration review logic
7. AI-vs-human task allocation logic under EADC
8. required document generation rules
9. outputs, statuses, and approval decisions
10. API list, screens, DB entities, events, and dashboard metrics
11. Knowledge Vault taxonomy and archival rules
12. 30/60/90/180-day roadmap
13. RACI and staffing model
14. pilot plan using 145 student projects
15. placeholder anchors for future policy and technology updates

Hard rules:
- No request proceeds without process owner
- No AI request proceeds without EADC check
- No development proceeds without duplication review
- No sensitive-data workflow proceeds without privacy and security review
- No local build is approved when enterprise reuse is sufficient
- No output may ignore knowledge archiving and version control

Output format:
- Executive summary
- Policy
- Intake template
- Diagnostic rules
- Prompt library
- Workflow
- APIs and data model
- Governance and audit rules
- Dashboards and KPIs
- Roadmap
- Chairman action note

### Operational prompt for live department requests

Act as DAIOS P01 Intake and Diagnosis Engine.

Analyse this department request and produce a constitution-compliant intake diagnosis package.

You must:
- restate the real business or academic problem
- map the current manual process
- identify the trackers, spreadsheets, forms, queues and complaints
- score the pain and urgency
- identify data sources and sensitivity categories
- search for existing DAIOS solutions that can be reused
- check integration feasibility with DUDOS, Student360, Central Dashboard, CRM, Revenue OS and other declared systems
- determine whether AI is appropriate under EADC
- classify the request as local utility, academic project, prototype, MVP, institutional product or marketplace candidate
- generate the mandatory next documents and approvals
- recommend approve / conditional approve / clarify / reject / archive

Return clear tables for:
1. key facts
2. missing facts
3. duplicate and reuse candidates
4. integration targets
5. risks
6. required documents
7. approval path
8. Knowledge Vault tags

### Prompt for future updates without root redesign

Act as the DAIOS P01 Update Integrator.

Review this new policy, new accreditation rule, new AI governance control, new integration target, or new departmental requirement.

Do not redesign P01.

Instead:
- identify the correct placeholder anchor
- state whether the change affects intake fields, validation, scoring, stop rules, outputs, dashboards, or archival metadata
- generate only the incremental update package
- preserve prior version history
- recommend whether this is a minor update, major update, or experimental rule
- update affected prompts and field dictionaries only where necessary

Return:
- change summary
- impacted components
- version recommendation
- migration note
- rollback note

The net result is a P01 framework that does exactly what your leadership theme requires: it turns DAIOS into a **dynamic, self-correcting blueprint engine** rather than a static form library; it lets departments submit reality instead of slogans; it automatically finds gaps, sorts context, and routes the right prompts; it gives developers a closed-loop correction mechanism instead of ad hoc rewrites; and it ensures every future addition can be plugged into a controlled anchor without breaking the root system design. The standards base strongly supports this direction: lifecycle governance, service management, quality modelling, AI management, and cyber risk management all favour defined intake, traceable decisions, continuous improvement, and verifiable controls over improvised development.

ISO/IEC/IEEE 12207:2026 - Systems and software engineering — Software life cycle processes

ISO/IEC 42001:2023 - AI management systems

ISO - Quality management: The path to continuous improvement

What is Data Management? - DAMA International®

The NIST Cybersecurity Framework (CSF) 2.0 | NIST
