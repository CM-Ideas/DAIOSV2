# DAIOS Master Prompt Framework and Prompt Operating System

## Executive Summary

The most defensible way to freeze DAIOS and move from concept to implementation is to treat prompts as governed enterprise assets rather than ad hoc instructions. That means every prompt must have an owner, purpose, evidence requirements, constitutional alignment, security posture, version history, usage telemetry, and a defined route into the Knowledge Vault, Product Registry, and release/change-management flow. This is fully consistent with the DAIOS materials you have already developed, which position DAIOS as a single AI-native, reusable, knowledge-preserving, commercially oriented operating platform rather than a loose collection of tools, projects, and departmental systems.

The recommended operating model is a **DAIOS Prompt Operating System** with twelve governed modules for the current constitutional freeze: **P00 Governance; P01 Intake; P03 Documentation; P04 Architecture; P05 AI Engineering; P06 Delivery and PMO; P07 Competition and Academic Innovation; P08 Knowledge and Learning; P09 Revenue and Commercialization; P10 Communication and Conversational Intelligence; P11 Chairman and Executive Intelligence; P12 Change Detection and Constitutional Evolution**. **P02 should remain reserved** for future Business Analysis, Process Mining, or Enterprise Analytics so the numbering model stays stable. This gives DAIOS a durable library structure without forcing future renumbering.

This report recommends that DAIOS adopt five non-negotiable design rules. First, **documentation-before-code**: no software, prompt, or AI workflow enters build status without registration, ownership, scope, architecture, data classification, and acceptance criteria. Second, **search first, reuse second, build third**: prompt execution must query the Prompt Registry, Knowledge Vault, and Product Registry before generating fresh work. Third, **risk-tiered AI execution**: not every task should use the same model, context window, or permission set. Fourth, **closed-loop learning**: every output, ticket, complaint, competition result, and executive decision must feed a structured archive and improvement cycle. Fifth, **governance before scale**: no prompt can bypass EADC, DUDOS, DAIOS constitutional rules, security controls, or explicit decision rights. Those recommendations align well with ISO/IEC 27001’s emphasis on risk-managed information security, NIST’s AI RMF and Privacy Framework, NIST’s Secure Software Development Framework, OWASP’s software-assurance and AI security guidance, and the continuous-improvement expectations reflected in UNESCO, ENQA ESG, and ABET accreditation criteria.

The implementation recommendation is therefore not to redesign DAIOS, but to operationalise it through a governed DPOS stack backed by a registry, policy engine, architecture review board, PMO cadence, AI guardrails, release/change controls, and a weekly executive reporting model. Your own DAIOS artefacts already point in that direction: development is expected to be architecture-led, product-oriented, marketplace-aware, and commercially reusable, while documentation, governance, and knowledge preservation are treated as structural requirements rather than administrative afterthoughts.

## Research Basis and Operating Principles

This framework is grounded in two source layers. The first layer is your internal DAIOS direction: one operating system, one knowledge base, one product logic, one commercialization discipline, and no loss of institutional memory. The DAIOS artefacts already indicate that every development should be reusable, documented, integrated, and capable of entering a broader commercialization and governance pipeline, while DAIOS itself is expected to function as a unifying analytical, technical, managerial, and executive system.

The second layer is the external baseline that makes the constitutional freeze implementation-ready rather than merely visionary. For information security governance, ISO/IEC 27001 requires a risk-based information security management system and emphasises confidentiality, integrity, and availability across people, process, and technology. For AI governance, NIST’s AI RMF frames trustworthy AI around governance, mapping context, measuring risk, and managing controls, while the Generative AI Profile operationalises that for GenAI systems. For secure software delivery, NIST SSDF and OWASP SAMM both emphasise integrating security into the lifecycle rather than treating it as a post-build check, and OWASP AISVS extends testable security requirements to AI-enabled systems. For academic quality assurance, UNESCO, ENQA ESG, and ABET all emphasise documented processes, measurable outcomes, evidence, and continuous improvement.

From those layers, the operational philosophy for DPOS should be fixed as follows:

| Principle | Operational meaning inside DPOS |
|---|---|
| System before people | A task must be executable by traceable workflow, not by memory or heroics |
| Product before project | Outputs are treated as reusable assets, not one-off delivery artefacts |
| Revenue before activity | Work is prioritised by institutional value, monetisation potential, or measurable efficiency |
| AI before manual effort | AI is used first where risk permits, with human review where risk requires |
| Reuse before rebuild | Prompt Registry, Knowledge Vault, Product Registry, and prior artefacts are searched before new generation |
| Governance before scale | No prompt or module may scale without ownership, approval, controls, and auditability |
| Knowledge capture before closure | No task, ticket, competition, or release is closed until key learning is archived |
| Constitution before deployment | EADC, DAIOS, DUDOS, and decision-rights alignment are mandatory gating rules |

The architectural consequence is that DPOS is not just a prompt library. It is a policy-and-execution layer that sits between user intent and enterprise action. It decides which prompt to use, which model may be used, which knowledge can be retrieved, what evidence is required, whether the request is allowed, which system is updated, and what is archived afterwards. That design also fits your stated aim of dynamic form/prompt architecture, zero root-code rewrites, contextual gap identification, and closed-loop correction. Those functions are most safely implemented as policy-driven orchestration rather than prompt sprawl.

## DPOS Architecture and Governance

The target-state design is a registry-centred orchestration pattern. User intent flows into an intake layer, which invokes a module prompt only after governance, search/reuse, knowledge retrieval, and model-routing logic are applied. The output then updates the relevant enterprise systems and archives evidence. This is the simplest way to preserve consistency, traceability, and reuse at scale.

|   |
|---|

That architecture should be implemented with standards-based interfaces. OpenAPI provides a machine-readable, language-agnostic way to describe HTTP APIs; the latest published specification is 3.2.0, while 3.1.2 remains a stable current branch. OAuth 2.0 security best current practice is codified in RFC 9700. For observability, OpenTelemetry provides vendor-neutral traces, metrics, and logs with context propagation, which is particularly useful for tracing prompt execution, retrieval, escalation, and human-review steps across distributed systems. For multi-tenant isolation, Kubernetes documentation explicitly recommends namespace isolation, least-privilege RBAC, and default-deny network controls in multi-tenant clusters.

The governance structure should be lightweight enough to execute weekly, but strict enough to prevent bypass. The recommended bodies are:

| Body | Purpose | Cadence |
|---|---|---|
| Constitutional Review Office | EADC, DAIOS, DUDOS alignment; amendments; red flags | Monthly and on exception |
| Prompt Review Board | Review/approve new or materially changed prompts | Weekly |
| Architecture Review Board | DAD, API, tenancy, security, observability, integration design | Weekly |
| AI Governance Board | Model routing, guardrails, AI risk, data exposure, evaluations | Fortnightly |
| PMO & Change Board | Implementation sequencing, release decisions, scope/risk control | Weekly |
| Executive Steering Group | Chairman brief, strategic blockers, capex/opex, commercialization | Monthly |

The prompt lifecycle should be frozen now so that every future update plugs into the same model.

|   |
|---|

The core registry schemas should be defined at constitutional level.

**Prompt Registry schema**

| Field | Required | Notes |
|---|---|---|
| Prompt ID | Yes | Format DPOS-Pxx-###-vM.m |
| Prompt Name | Yes | Human-readable |
| Module | Yes | P00–P12 |
| Category | Yes | Master / Functional / Workflow / Task / Governance |
| Owner | Yes | Named accountable owner |
| Backup Owner | Yes | Removes people dependency |
| Purpose | Yes | One-sentence mission |
| Risk Tier | Yes | T0 low, T1 moderate, T2 high, T3 restricted |
| Data Sensitivity | Yes | Public / Internal / Confidential / Restricted |
| Inputs | Yes | Required artefacts, systems, IDs |
| Outputs | Yes | Deliverables and destination systems |
| Constitutional References | Yes | EADC / DAIOS / DUDOS / DACJE / etc. |
| Approval Status | Yes | Draft / Review / Approved / Restricted / Retired |
| Version | Yes | Semantic versioning |
| Effective Date | Yes | Start date |
| Review Date | Yes | Next mandatory review |
| Success Metrics | Yes | Accuracy, usage, review rate, time saved |
| Model Policy | Yes | Approved models, banned models, fallback |
| Extension Anchors | Yes | Placeholder keys for future updates |
| Audit Log URI | Yes | Link to change and execution history |

**Product Registry minimum fields**

| Field | Required | Notes |
|---|---|---|
| Product ID | Yes | Enterprise-unique |
| Product Name | Yes | Stable canonical name |
| Classification | Yes | Academic / MVP / Institutional / Marketplace / SaaS |
| Product Owner | Yes | Named accountable owner |
| Customer / User Type | Yes | Student, faculty, staff, market, partner |
| Problem Solved | Yes | Explicit use case |
| Reuse Status | Yes | Existing / Adapted / New |
| Linked Prompt IDs | Yes | Which prompts generated or govern it |
| Linked Docs | Yes | DAD, MPIP, BRD, SRS, ERD, API spec |
| Commercial Status | Yes | Internal only / Pilot / Revenue / White-label |
| Integration Map | Yes | APIs, events, SSO, data exchanges |
| Data Classification | Yes | Security/privacy tier |
| ROI / Value Model | Yes | Cost saved, revenue, adoption, quality improvement |
| Lifecycle Status | Yes | Idea / Active / Released / Retired |

**Documentation-before-code gate**

| Gate | Must exist before build starts |
|---|---|
| Registration gate | Product ID, prompt ID, owner, purpose, linked unit |
| Constitutional gate | EADC/DAIOS/DUDOS mapping and decision rights |
| Documentation gate | DAD, MPIP, BRD, SRS, ERD, API scope, UI scope |
| Security gate | Data classification, auth model, secrets plan, logging plan |
| AI gate | Model policy, prompt risk tier, hallucination controls, eval plan |
| Integration gate | Source/target systems, interface contract, event design |
| Delivery gate | backlog, Definition of Done, acceptance criteria, release owner |
| Knowledge gate | archive path, naming rules, metadata, lessons-learned template |

A pre-compliance engine should reject or pause execution if any of these checks fail: missing owner; missing constitutional mapping; missing evidence; unapproved model; request attempts to bypass a restricted prompt; duplicate prompt candidate above threshold; prompt points to a retired system; missing destination archive path; privileged output requested without role or justification; or changes proposed directly to a constitutional prompt without amendment workflow. This mirrors the security and lifecycle emphasis found in ISO 27001, NIST SSDF, OWASP SAMM, and OWASP AISVS.

## Module Library P00–P12

The table below defines the frozen module structure. “Mandatory inputs” are the minimum inputs required for compliant execution. “Anchors” are extension points where future updates are inserted without rewriting the root prompt.

| Module | Purpose | Mandatory inputs | Key integrations | Evidence checklist | Version & anchors | Sample invocation |
|---|---|---|---|---|---|---|
| P00 Governance and Constitution | Constitutional orchestration, approvals, audit prompts, EADC/DUDOS alignment | policy refs, unit, owner, request, risk tier | Decision Rights, RACI, Prompt Registry, audit log | policy mapping, approval path, red-flag screen | DPOS-P00-*; anchors [P00-POLICY] [P00-APPROVAL] [P00-AUDIT] | “Run P00 to validate whether this automation request can proceed under EADC and DUDOS.” |
| P01 Intake and Diagnosis | Department automation intake, pain analysis, queue/complaint diagnostics, tracker inventory | department profile, current process, queue logs, trackers, pain points | CRM, ticketing, PMO, Knowledge Vault | current-state map, manual steps, SLA pain, duplicate tools | DPOS-P01-*; anchors [P01-FORMS] [P01-TAXONOMY] [P01-CHANNELS] | “Run P01 for Registrar complaints and identify automation priority.” |
| P03 Documentation | Generate and validate Product Registration, DAD, MPIP, BRD, SRS, ERD, API spec, tests, SOP pack | product idea, actors, inputs/outputs, scope, rules, integrations | Product Registry, Architecture Board, QA, release pack | completed docs, traceability matrix, acceptance criteria | DPOS-P03-*; anchors [P03-DOCS] [P03-TEMPLATES] [P03-TRACEABILITY] | “Run P03 to produce DAD, BRD and API spec for Alumni 360 payment module.” |
| P04 Architecture and Engineering | Architecture review, SaaS readiness, API design, tenancy, DevOps, observability | DAD, NFRs, data model, integration map, target scale | ARB, DevOps, security, OpenTelemetry stack | architecture diagrams, tenancy choice, resiliency, observability | DPOS-P04-*; anchors [P04-STACK] [P04-TENANCY] [P04-OBSERVE] | “Run P04 to review multi-tenant design for Student360 partner deployment.” |
| P05 AI and Agent Engineering | Persona prompt design, agent governance, guardrails, evaluation, cost and hallucination review | persona, tasks, approved knowledge, risk tier, model options | AI Registry, Prompt Registry, eval store, security | eval metrics, prompt tests, fallback, red-team notes | DPOS-P05-*; anchors [P05-MODELS] [P05-GUARDRAILS] [P05-EVALS] | “Run P05 to design an Admission AI persona with quota and risk controls.” |
| P06 Delivery and PMO | Execution command, sprint/governance pack, risk review, decision note, RACI validation, change control | scope, backlog, owners, milestones, risks, approvals | PMO, dashboards, change board, ARB | plan, dependencies, RAID log, DoD, release notes | DPOS-P06-*; anchors [P06-CADENCE] [P06-REPORTS] [P06-CHANGE] | “Run P06 for a 12-week MVP plan for PerfectHR leave automation.” |
| P07 Competition and Academic Innovation | Participant generator, judge package, capstone classifier, maturity scorer, post-competition integration | submission data, evidence, mentor, demo, docs, commercialization note | DACJE, Student Product Factory, Faculty Innovation, Product Registry | scorecard, documentation, classification, recommendation | DPOS-P07-*; anchors [P07-SCORE] [P07-CLASSIFY] [P07-POSTPIPELINE] | “Run P07 to classify this capstone as Prototype, MVP or Institutional Product.” |
| P08 Knowledge and Learning | Knowledge extraction, lessons learned, archive classifier, forum intelligence, research productization | source artefacts, outcomes, owners, tags, audience | Knowledge Vault, Prompt Registry, Faculty Innovation | summary, taxonomy, reusable assets, learning actions | DPOS-P08-*; anchors [P08-TAXONOMY] [P08-ARCHIVE] [P08-RESEARCH] | “Run P08 on project closure documents and generate lessons learned plus learning assets.” |
| P09 Revenue and Commercialization | Pricing, MRR/ARR, white-label, packaging, customer success automation, revenue readiness | product profile, market, costs, segment, support model | Revenue OS, Marketplace, CRM, Product Registry | pricing logic, margin, packaging, retention plan | DPOS-P09-*; anchors [P09-PRICING] [P09-PACKAGE] [P09-CSM] | “Run P09 for a white-label pricing plan for AI Proctor.” |
| P10 Communication and Conversational Intelligence | DCIP channel prompts, CRM enrichment, complaint/ticket classification, recommendations, escalation | channel, actor, message, context, identity, SLA rules | CRM, ticketing, WhatsApp, email, dashboards | classification, sentiment, ticket, escalation, archive | DPOS-P10-*; anchors [P10-CHANNELS] [P10-PERSONAS] [P10-TAXONOMY] | “Run P10 on WhatsApp complaints from parents and suggest governed response plus escalation.” |
| P11 Chairman and Executive Intelligence | Morning brief, weekly brief, risk note, opportunity scan, delay note, commercialization summary | KPIs, unresolved items, risks, opportunities, approvals, dependencies | Chairman Command Center, PMO, Revenue OS, dashboards | decision memo, brief pack, escalation logic, action owners | DPOS-P11-*; anchors [P11-BRIEF] [P11-RISK] [P11-OPSUM] | “Run P11 to create Monday executive brief from weekly dashboards.” |
| P12 Change Detection and Constitutional Evolution | Policy delta detection, standard impact, anomaly detection, prompt update need, amendment proposal | existing policy, new source, changed requirement, owner, affected modules | P00, Prompt Registry, audit log, ARB, AI Governance | delta report, impacted prompts, amendment note, migration plan | DPOS-P12-*; anchors [P12-SOURCES] [P12-DELTAS] [P12-AMENDMENT] | “Run P12 against new academic QA requirements and show required constitutional updates.” |

The following are the implementation-ready master prompt texts. Each is written so your team can run it directly, while the extension anchors tell future teams exactly where updates should be inserted.

[DPOS-P00-Governance-Constitution-Orchestrator-v1.0]
Act as the Chief Governance Officer, Chief AI Officer, Chief Product Officer, and Constitutional Orchestrator of DAIOS.
Mission: decide whether a requested task, product, automation, AI workflow, or prompt may proceed under EADC, DAIOS, DUDOS, decision-rights rules, and approval policy.
Context: use Prompt Registry, Product Registry, Knowledge Vault, RACI Matrix, Decision Rights Matrix, DACJE, and applicable institutional policy.
Analyse: requester authority, business purpose, constitutional alignment, risk tier, data sensitivity, approval path, duplication risk, audit requirements, and whether build, pilot, release, or rejection is appropriate.
Output: executive decision, policy mapping, missing approvals, required evidence, risk flags, allowed next step, mandatory reviewers, and audit-trail entry.
Governance rules: never approve execution without owner, purpose, evidence path, archive path, and decision authority.
Update anchors: [P00-POLICY] [P00-APPROVAL] [P00-AUDIT] [P00-EXCEPTIONS]

[DPOS-P01-Intake-Diagnosis-Orchestrator-v1.0]
Act as the Enterprise Systems Analyst and Process Diagnostic Director of DAIOS.
Mission: convert departmental confusion, manual pain, queue pressure, complaint load, and tracker sprawl into a structured automation diagnosis.
Context: review current forms, Excel files, queues, complaints, approvals, emails, existing systems, and service expectations.
Analyse: current-state workflow, bottlenecks, repeated work, people dependency, missing data, lost knowledge, duplicated tools, demand volume, risk, and likely automation value.
Output: current-state map, pain-point inventory, complaint classification, tracker inventory, duplicate-system warning, quick wins, required documents, and recommended intake score.
Governance rules: do not recommend new system build until existing systems, prompts, and reusable modules have been checked.
Update anchors: [P01-FORMS] [P01-CHANNELS] [P01-TAXONOMY] [P01-SCORING]

[DPOS-P03-Documentation-Generation-Orchestrator-v1.0]
Act as the Enterprise Documentation Architect of DAIOS.
Mission: generate and validate the full documentation pack required before coding, procurement, deployment, pilot, or competition submission.
Context: use Product Registry conventions, DAD rules, MPIP, BRD, SRS, ERD, API contracts, test packs, release templates, and SOP libraries.
Analyse: business problem, actors, process rules, data objects, integrations, non-functional requirements, risks, AI scope, success metrics, and acceptance criteria.
Output: Product Registration, DAD, MPIP, BRD, SRS, ERD outline, API spec outline, test case pack, release-note skeleton, SOP pack, and traceability matrix.
Governance rules: no code, no procurement, no release, and no competition qualification without required documentation completeness.
Update anchors: [P03-DOCS] [P03-TEMPLATES] [P03-TRACEABILITY] [P03-SOPS]

[DPOS-P04-Architecture-Engineering-Orchestrator-v1.0]
Act as the Principal Enterprise Architect and Global SaaS Systems Engineer of DAIOS.
Mission: assess whether the proposed design is reusable, scalable, secure, observable, интегrated, and fit for institutional or commercial growth.
Context: review DAD, ERD, NFRs, API boundaries, tenancy model, CI/CD, infrastructure, observability, and disaster recovery assumptions.
Analyse: architecture fit, tenant isolation, interface contracts, failure modes, performance, logging, tracing, portability, vendor lock-in, environment readiness, and release topology.
Output: architecture decision, required corrections, SaaS readiness score, API review, tenancy recommendation, DevOps plan, observability plan, and environment matrix.
Governance rules: reject isolated, duplicate, hard-coded, or non-observable architectures.
Update anchors: [P04-STACK] [P04-TENANCY] [P04-OBSERVE] [P04-PLATFORM]

[DPOS-P05-AI-Agent-Engineering-Orchestrator-v1.0]
Act as the Chief AI Engineer and Agent Governance Director of DAIOS.
Mission: design safe, effective, cost-aware, and measurable AI personas, prompts, agents, and model-routing rules.
Context: use AI Governance Handbook, approved knowledge sources, Prompt Registry, evaluation rules, security policy, and model policy.
Analyse: role, allowed actions, retrieval needs, hallucination risk, sensitive data exposure, evaluation criteria, fallback logic, cost per task, and human-review thresholds.
Output: persona definition, system prompt, guardrails, tool permissions, eval plan, hallucination controls, cost band, routing policy, and go/no-go recommendation.
Governance rules: no unrestricted agent deployment, no unapproved knowledge source, and no high-risk autonomy without explicit approval.
Update anchors: [P05-MODELS] [P05-GUARDRAILS] [P05-EVALS] [P05-COST]

[DPOS-P06-Delivery-PMO-Orchestrator-v1.0]
Act as the Enterprise PMO Director and Delivery Governance Lead of DAIOS.
Mission: convert approved scope into governed execution with zero scope drift and minimum people dependency.
Context: use backlog, dependencies, team capacity, RACI, decision rights, RAID log, release plan, and KPI pack.
Analyse: sequence, blockers, work packages, approval gates, sprint goals, resource risk, documentation readiness, and reporting needs.
Output: implementation order, sprint plan, weekly governance pack, risk review, decision note, change-control note, and Definition-of-Done checklist.
Governance rules: no build begins without gated readiness and no release occurs without evidence, sign-off, and archive completion.
Update anchors: [P06-CADENCE] [P06-REPORTS] [P06-CHANGE] [P06-DOD]

[DPOS-P07-Competition-Academic-Innovation-Orchestrator-v1.0]
Act as the Chief Academic Innovation Officer, Assessment Quality Director, and Product Transformation Lead of DAIOS.
Mission: transform competitions, capstones, faculty innovation, and demos into classified, governed, reusable product and knowledge outcomes.
Context: use DACJE, Student Product Factory, Faculty Innovation Framework, Product Registry, Knowledge Vault, and commercialization rules.
Analyse: evidence quality, governance compliance, originality, documentation, integration potential, scalability, security, maturity, and commercialization value.
Output: participant pack, judge pack, maturity score, capstone classification, integration recommendation, commercialization note, and post-competition pipeline decision.
Governance rules: no submission is ranked by presentation alone and no winning solution bypasses compliance checks.
Update anchors: [P07-SCORE] [P07-CLASSIFY] [P07-POSTPIPELINE] [P07-COMMERCIAL]

[DPOS-P08-Knowledge-Learning-Orchestrator-v1.0]
Act as the Knowledge Architect and Learning Intelligence Director of DAIOS.
Mission: convert project outputs, tickets, discussions, research, and releases into searchable, reusable institutional learning assets.
Context: use Knowledge Vault taxonomy, Prompt Registry, archive rules, faculty research pipeline, and student-product enrichment logic.
Analyse: what was created, what was learned, what should be reused, what should become policy, prompt, SOP, training material, or product feature.
Output: structured summary, archive classification, lessons learned, reusable assets, competency gaps, learning actions, and enrichment metadata.
Governance rules: no closure without archive quality check, metadata, source link, owner, and reuse recommendation.
Update anchors: [P08-TAXONOMY] [P08-ARCHIVE] [P08-RESEARCH] [P08-LEARNING]

[DPOS-P09-Revenue-Commercialization-Orchestrator-v1.0]
Act as the Chief Commercialization Officer and Revenue Systems Director of DAIOS.
Mission: determine how an approved product becomes financially viable, supportable, packageable, and repeatably sellable.
Context: use Revenue OS, Marketplace rules, CRM, pricing policies, support model, and product-cost assumptions.
Analyse: customer segment, pricing basis, MRR/ARR potential, margin, onboarding effort, white-label potential, support cost, retention risk, and packaging readiness.
Output: pricing model, revenue forecast, packaging plan, white-label plan, customer success automation, marketplace readiness, and revenue readiness score.
Governance rules: do not label a product commercial without pricing logic, owner, support model, and measurable revenue pathway.
Update anchors: [P09-PRICING] [P09-PACKAGE] [P09-CSM] [P09-MARKETS]

[DPOS-P10-Communication-Conversational-Intelligence-Orchestrator-v1.0]
Act as the Communication Intelligence Director and Omnichannel Automation Lead of DAIOS.
Mission: turn every governed conversation into customer intelligence, workflow execution, organizational memory, and product insight.
Context: use DCIP policies, CRM, ticketing, Knowledge Vault, persona definitions, escalation rules, and response libraries.
Analyse: channel, identity, intent, urgency, sentiment, duplication, ticket requirement, escalation rule, recommendation, and knowledge value.
Output: classified response, CRM update, ticket status, escalation path, knowledge capture entry, next-best action, and dashboard event.
Governance rules: no uncontrolled responses, no off-registry persona use, and no sensitive-experience handling without authorised policy.
Update anchors: [P10-CHANNELS] [P10-PERSONAS] [P10-TAXONOMY] [P10-ESCALATION]

[DPOS-P11-Chairman-Executive-Intelligence-Orchestrator-v1.0]
Act as the Chairman Intelligence Officer and Enterprise Strategy Briefing Director of DAIOS.
Mission: provide decision-ready executive intelligence on performance, delay, risk, opportunity, commercialization, and system dependency.
Context: use KPI dashboards, PMO logs, risk registers, approval queues, commercialization pipeline, and operational telemetry.
Analyse: overdue items, blocked decisions, concentration of dependency, revenue signals, product progress, complaint trends, and escalation quality.
Output: morning brief, weekly brief, risk note, opportunity scan, delayed-approval note, commercialization summary, dependency score, and action memo.
Governance rules: every statement must be evidence-backed, dated, owner-tagged, and decision-oriented.
Update anchors: [P11-BRIEF] [P11-RISK] [P11-OPSUM] [P11-DEPENDENCY]

[DPOS-P12-Change-Detection-Constitutional-Evolution-Orchestrator-v1.0]
Act as the Constitutional Evolution Director and Policy Delta Analyst of DAIOS.
Mission: detect policy, standards, risk, architecture, and operational changes that require updates in prompts, controls, or constitutional text.
Context: compare current constitutional baseline against new internal directives, standards, audit findings, incidents, or accreditation changes.
Analyse: delta type, affected modules, urgency, impacted prompts, transition effort, backward compatibility, retraining need, and approval path.
Output: delta report, impact map, proposed amendment text, affected prompt list, migration steps, temporary controls, and review agenda.
Governance rules: no root-prompt rewrite without amendment proposal, versioning, compatibility note, and approving authority.
Update anchors: [P12-SOURCES] [P12-DELTAS] [P12-AMENDMENT] [P12-MIGRATION]

These module prompts should be executed through a common shell rather than pasted as standalone text each time. The shell should always prepend request metadata, role permissions, linked system IDs, approved knowledge sources, model policy, and destination archive path. That is the key mechanism that prevents prompt drift and uncontrolled usage.

## Implementation and Delivery Model

The constitutional freeze should be implemented in four waves over sixteen weeks, starting with governance and registries, then documentation and architecture, then AI/commercial/communication modules, then optimization and executive intelligence. Trying to build all prompt families in parallel before the registries, gates, and audit flow exist will reintroduce exactly the chaos DAIOS is attempting to eliminate.

A reasonable initial readiness view, based on your internal artefacts and the maturity now implied by the design, is that constitutional direction is strong but execution control layers need finishing. This is an inferred readiness profile rather than a formal audited score.

|   |
|---|

The sequencing should be frozen as follows:

| Wave | Weeks | Outcome |
|---|---|---|
| Foundation | 1–4 | P00, registry schemas, gates, RACI, approval flow, naming/versioning |
| Design control | 5–8 | P01, P03, P04, ARB, documentation gates, tenancy/API/observability standards |
| Intelligence and execution | 9–12 | P05, P06, P10, model routing, PMO packs, dashboards, ticket/CRM linkage |
| Scale and feedback | 13–16 | P07, P08, P09, P11, P12, KPI automation, change detection, executive brief flows |

The team model should separate accountability from implementation so that no single technical person becomes the system.

| Role | Minimum staffing | Ideal staffing | Key accountabilities |
|---|---|---|---|
| Executive Sponsor / Chairman Delegate | 1 | 1 | strategic prioritisation, escalation decisions |
| CPO / Product Governance Lead | 1 | 1 | prompt portfolio, product alignment |
| CGO / CAIO | 1 | 2 | constitutional and AI governance |
| PMO Lead | 1 | 1 | sequencing, cadence, reporting |
| Enterprise Architect | 1 | 2 | P04, integrations, ARB |
| AI Engineering Lead | 1 | 2 | P05, routing, evaluations |
| Backend / Platform Engineers | 2 | 4 | registries, APIs, eventing |
| Front-end / Workflow Engineers | 1 | 3 | forms, admin UI, dashboards |
| QA / Test Automation | 1 | 2 | prompt tests, regression, acceptance |
| Security / Compliance Engineer | 1 | 2 | auth, logging, risk, reviews |
| Knowledge Manager | 1 | 2 | taxonomy, archive, reuse metrics |
| Commercialisation Lead | 1 | 2 | P09, packaging, value models |
| Academic Innovation Lead | 1 | 2 | P07, faculty/student pipelines |
| Student contributors | 2 | 8 | documentation, testing, support, research under controlled scope |

The RACI and decision-rights model should be simple enough to execute.

| Activity | Sponsor | CPO/CGO | PMO | Architect | AI Lead | Security/QA | Knowledge | Dept Owner |
|---|---|---|---|---|---|---|---|---|
| Approve new module | A | R | C | C | C | C | C | I |
| Approve new prompt | I | A/R | C | C | C | C | C | I |
| Approve architecture | I | C | C | A/R | C | C | I | C |
| Approve model policy | I | A | I | C | R | C | I | I |
| Release to production | I | A | R | C | C | R | C | C |
| Constitutional amendment | A | R | C | C | C | C | C | I |
| Weekly reporting | I | C | A/R | C | C | C | C | R |
| Knowledge ingestion quality | I | I | C | I | I | I | A/R | C |

The weekly PMO pack should contain exactly these artefacts: readiness score; sprint status; decision log; RAID log; documentation completeness; outstanding approvals; security blockers; prompt performance; top reuse wins; revenue/commercialisation pipeline; student/faculty innovation pipeline; and Chairman action items. That pack should be generated via P06 and P11, not assembled manually.

The Definition of Done for prompt-enabled work should be frozen as follows: registered; owner assigned; traceable inputs defined; outputs tested; required approvals completed; archive entry created; monitoring configured; rollback or fallback path documented; prompt version tagged; and post-release KPI linked. Any work item lacking one of those conditions is not done.

The release and change-management flow should be:

|   |
|---|

The 16-week MVP roadmap can be represented as follows.

|   |
|---|

## Controls, Metrics, and Risk Register

Prompt performance must be measured, not assumed. The minimum metric family should include usage count, successful first-pass rate, human revision rate, constitutional-compliance pass rate, knowledge-reuse rate, time saved, ticket deflection rate where relevant, revenue impact where relevant, and hallucination/escalation rates for AI prompts. OpenTelemetry is well suited for capturing execution telemetry across traces, metrics, and logs, while OWASP and NIST guidance support explicit testing, monitoring, and controlled iteration on AI and software risks.

|   |
|---|

The KPI dashboard should contain at least these twelve indicators:

| KPI | Target by month 6 |
|---|---|
| Documentation completeness before build | 95% |
| Prompt reuse rate | 60% |
| First-pass prompt success | 80% |
| Human revision rate | <20% |
| Constitutional pass rate | 98% |
| Duplicate-prompt prevention hit rate | >70% of duplicates caught pre-approval |
| Knowledge Vault ingestion completeness | 90% |
| Mean time to approved prompt | <5 working days |
| Release on-time rate | 85% |
| AI evaluation pass rate | 85% |
| Competition-to-product conversion rate | 20% |
| Commercial-readiness pipeline conversion | 50% of selected candidates |

The anomaly and alert rules should be explicit.

| Alert | Trigger |
|---|---|
| Prompt drift | runtime output deviates materially from approved output schema |
| Hallucination risk | low evidence coverage or contradiction with approved sources |
| Uncontrolled AI use | model or prompt invoked outside approved registry |
| Knowledge loss | task closed without archive entry |
| Duplicate creation risk | similarity with existing prompt/product above threshold |
| Approval bypass | restricted task executed without signed workflow |
| Security regression | missing logs, auth, or secret-policy check |
| Stale prompt | review date exceeded or success rate degraded |
| Concentration risk | one owner responsible for too many critical prompts |
| Commercial blind spot | product marked deployable but no revenue/support model |
| Accreditation blind spot | academic workflow missing mapped outcomes/evidence |
| Delivery slippage | milestone variance beyond threshold |

The duplication-detection method should be layered: exact match on IDs and names; semantic similarity on prompt text and purpose; overlap on input/output schemas; overlap on system/API targets; overlap on product/problem taxonomy; overlap on UI/workflow labels; and historic usage clustering. That layered method is more robust than title matching alone, and it reflects your own preference to stop repetitive work before it starts.

The risk register below captures the fifty most likely failure modes for DPOS implementation.

| ID | Risk | Prob. | Impact | Mitigation | Owner |
|---|---|---|---|---|---|
| 1 | Constitution remains aspirational, not enforceable | H | H | hard gates in registry | CGO |
| 2 | Prompt sprawl without registry discipline | H | H | no execution outside registry | CPO |
| 3 | Missing owners for prompts | H | H | owner mandatory field | PMO |
| 4 | People dependency on one architect | H | H | backup owner and docs | Sponsor |
| 5 | Undocumented exceptions become norm | M | H | exception log and review | CGO |
| 6 | Duplicate prompts proliferate | H | M | similarity screening | Knowledge Lead |
| 7 | Duplicate systems built by departments | H | H | P01 and P00 pre-check | Architect |
| 8 | Documentation generated but not used | H | M | traceability and gates | PMO |
| 9 | Weak DAD quality | M | H | ARB checklist | Architect |
| 10 | No clear data classification | M | H | security gate | Security |
| 11 | Sensitive data sent to wrong model | M | H | risk-tiered model policy | AI Lead |
| 12 | AI hallucinations accepted as fact | H | H | evals and evidence thresholds | AI Lead |
| 13 | Persona scope too broad | M | H | restricted permissions | AI Lead |
| 14 | Prompt versions unmanaged | H | M | semantic version control | PMO |
| 15 | Review dates missed | M | M | stale-prompt alerts | PMO |
| 16 | ARB becomes bottleneck | M | M | standard patterns and SLAs | Architect |
| 17 | PMO reporting becomes manual burden | M | M | automation via P06/P11 | PMO |
| 18 | Weak test coverage for prompts | H | H | prompt regression suite | QA |
| 19 | No rollback path for prompt releases | M | H | release checklist | PMO |
| 20 | Missing audit logs | M | H | immutable logging | Security |
| 21 | Role creep in privileged prompts | M | H | least privilege enforcement | Security |
| 22 | Multi-tenant isolation gaps | M | H | namespace/RBAC/network policies | Architect |
| 23 | Lack of observability | M | H | OpenTelemetry baseline | Platform |
| 24 | API contracts drift from implementation | M | M | OpenAPI validation | Architect |
| 25 | Integration debt grows | M | M | interface review board | Architect |
| 26 | Competition outputs not archived | H | M | P07 to P08 pipeline | Academic Lead |
| 27 | Judge bias overrides evidence | M | H | DACJE moderation | Assessment Director |
| 28 | Faculty innovation not commercialised | M | M | P07/P09 linkage | Innovation Lead |
| 29 | Student outputs pose security risks | M | H | controlled sandbox and review | QA/Security |
| 30 | Commercial claims lack evidence | M | M | P09 readiness gates | Revenue Lead |
| 31 | White-label plans ignore support burden | M | M | support cost model | Revenue Lead |
| 32 | CRM not updated from conversations | H | M | P10 automation | CRM Lead |
| 33 | Ticketing and communication stay siloed | H | M | DCIP integration rules | Ops Lead |
| 34 | Escalations are inconsistent | M | M | policy-driven escalation matrix | PMO |
| 35 | Executive briefs contain unverified claims | M | H | evidence-linked P11 outputs | Chairman Office |
| 36 | Change detection not monitored | M | M | P12 scheduled runs | CGO |
| 37 | Standards change not reflected in prompts | M | H | delta alerts and amendments | CGO |
| 38 | Knowledge metadata quality weak | M | M | controlled taxonomy | Knowledge Lead |
| 39 | Search/reuse quality poor | M | M | ontology and tags | Knowledge Lead |
| 40 | Prompt costs escalate silently | M | M | model-cost monitoring | AI Lead |
| 41 | Vendor lock-in from tooling choices | M | M | open standards and exportability | Architect |
| 42 | No student/faculty onboarding | M | M | guided templates and training | Academic Lead |
| 43 | Staff resist new governance | H | M | phased rollout and wins | Sponsor |
| 44 | Department requests bypass intake | H | M | P00 approval prerequisite | PMO |
| 45 | Marketplace packaging incomplete | M | M | P09 mandatory pack | Revenue Lead |
| 46 | Privacy obligations overlooked | M | H | privacy impact and lawful basis | Security |
| 47 | Accreditation evidence not captured | M | H | outcome mapping in P07/P08 | Academic Lead |
| 48 | Prompt library becomes stale | M | M | monthly audit and retirement | CPO |
| 49 | Hotfixes bypass change control | M | H | emergency change path | PMO |
| 50 | DPOS success measured only by adoption, not value | M | H | KPI baseline with outcomes | Sponsor |

Finally, the DACJE mapping for the academic and competition engine should remain aligned to evidence and product maturity, not presentation quality.

| DACJE category | Suggested weight | Primary source in DPOS |
|---|---|---|
| Problem clarity and real need | 8 | P01, P07 |
| Governance and constitutional compliance | 10 | P00, P07 |
| Documentation and knowledge preservation | 10 | P03, P08 |
| Productisation and MVP readiness | 10 | P03, P04, P07 |
| Reuse, integration, architecture | 12 | P04, P07 |
| Automation and people-dependency reduction | 10 | P01, P06 |
| AI, data, security | 10 | P05, P07 |
| Commercialisation and recurring value | 12 | P09, P07 |
| Scalability and sustainability | 10 | P04, P09 |
| Validation and measurable impact | 8 | P07, P08 |

This score orientation matches your DAIOS position that governance, documentation, reuse, integration, adoption, recurring value, and measurable outcomes are the real evidence of product quality, while academic quality frameworks likewise require documented outcomes and continuous improvement rather than superficial showpieces.

## Immediate Constitutional Freeze Actions

The cleanest path to freeze and implement is to approve the following as constitutional clauses within DAIOS.

First, approve **DPOS as the only authorised prompt execution framework** for enterprise use. Second, approve **P00–P12 as the frozen master library structure**, with **P02 reserved**. Third, approve the **registry-first rule**: no production prompt, AI persona, or automation workflow exists outside the Prompt Registry. Fourth, approve **documentation-before-code** and **archive-before-closure** as hard gates. Fifth, approve the **weekly PMO and executive reporting cadence**. Sixth, approve **P12 as the only lawful route for constitutional amendments**. Seventh, approve **risk-tiered model routing** and ban unapproved external or consumer-grade AI execution for restricted work. Eighth, approve **competition-to-product** and **conversation-to-knowledge** as default enterprise pathways so that student work, faculty output, support interactions, and executive decisions all become reusable institutional capital. That final step is especially important because it operationalises the DAIOS ambition of turning separate systems, AI tools, products, and business units into a unified product-and-knowledge platform with commercialization discipline built in from the start.

If those eight actions are approved, DAIOS no longer depends on remembered instructions or scattered prompt files. It becomes a governed, auditable, evolve-without-rewrite operating system. That is the correct point at which to declare the constitutional freeze and begin implementation.

ISO/IEC 27001:2022 - Information security management systems

Artificial Intelligence Risk Management Framework (AI RMF 1.0) | NIST

OpenAPI Specification v3.2.0

OpenTelemetry

Quality assurance in higher education | UNESCO
