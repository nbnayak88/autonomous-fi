# BAISI PAHACHA 05 — Requirement Analysis

**Course:** Applied SAP S/4HANA Finance  
**Stream:** AFR1 — Record to Report  
**Lab:** Scale — School of Career Acceleration Lab for Excellence  
**Interview Mastery Series:** 05 of 22  
**Theme:** DESIGN  
**Pahacha:** Requirement Analysis

---

## Purpose

Build the ability to transform vague Finance business needs into **clear, testable, prioritized, traceable requirements** that can drive SAP configuration, integration, data, controls, analytics and architecture.

The architect's journey is:

**Business Problem → Stakeholder Need → Requirement → Business Rule → Acceptance Criteria → Solution Capability → Architecture Impact → Value**

Every scenario uses **STAR-SME+**:

- **S — Situation:** Context, pain point, stakeholders, scale and constraints.
- **T — Task:** What you personally owned.
- **A — Action:** What you analyzed, challenged, documented, prioritized or validated — and why.
- **R — Result:** Observable or measurable outcome.
- **SME Probe:** Expert follow-up.
- **Reflection:** Learning and improvement.

---

# 20 Scenario-Based Interview Questions

## Scenario 01 — “We Need a Faster Close”

**Question:** A CFO says, “I need Finance to close faster.” How do you convert this into requirements?

**STAR Answer**

**S — Situation:** The CFO expressed a business outcome but had not defined which parts of the close caused the delay.

**T — Task:** My responsibility was to convert the broad request into actionable requirements.

**A — Action:** I decomposed the outcome into close duration, task dependencies, reconciliation delays, manual journals, late inputs, approval waits and reporting readiness. I interviewed Finance users, mapped the current process and established measurable baseline and target metrics.

**R — Result:** “Faster close” became a structured set of measurable requirements rather than an ambiguous technology request.

**SME Probe:** How would you avoid designing a solution before understanding the problem?

**Reflection:** I always convert outcome statements into measurable business requirements before discussing SAP features.

---

## Scenario 02 — Stakeholders Give Conflicting Requirements

**Question:** The CFO wants standardization while country Finance teams demand local variations. What do you do?

**STAR Answer**

**S — Situation:** Global leadership wanted a common R2R process, while local teams identified statutory and operational differences.

**T — Task:** My responsibility was to distinguish genuine requirements from preferences and historical habits.

**A — Action:** I documented each requirement, source, business rationale, regulatory basis, frequency, impact and affected entities. I classified requirements into global, localized, regulatory, differentiating and legacy-only categories.

**R — Result:** Stakeholders could discuss requirements based on evidence rather than organizational preference.

**SME Probe:** Who makes the final decision when requirements conflict?

**Reflection:** Requirement governance needs explicit decision rights; architecture should make trade-offs visible rather than silently choosing sides.

---

## Scenario 03 — Requirement vs Solution

**Question:** A Finance user says, “We need a custom SAP report.” Is that a requirement?

**STAR Answer**

**S — Situation:** A user requested a specific report because existing reporting did not answer a management question.

**T — Task:** My responsibility was to identify the underlying business need.

**A — Action:** I asked what decision the report supported, who used it, which measures and dimensions were required, frequency, latency, security and expected action. I then evaluated standard analytics, embedded reporting, governed semantic models and custom development.

**R — Result:** The requirement was reframed as a business-information need rather than prematurely locking into a custom report.

**SME Probe:** Why is “build a report” usually a solution statement?

**Reflection:** Requirements should describe the needed outcome or capability; implementation choices belong to solution design.

---

## Scenario 04 — Requirement Elicitation from a CFO

**Question:** How would you conduct a requirements workshop with a CFO who has only 30 minutes?

**STAR Answer**

**S — Situation:** Executive time was limited, but the program needed clarity on Finance transformation priorities.

**T — Task:** My responsibility was to extract high-value requirements quickly.

**A — Action:** I prepared hypotheses and baseline metrics in advance, then focused the session on business outcomes, decisions, pain points, risks, regulatory constraints, KPIs and desired future capabilities. I used targeted questions instead of asking the CFO to describe system functionality.

**R — Result:** The workshop produced strategic requirements and decision criteria that could be decomposed with Finance SMEs afterward.

**SME Probe:** What would you not ask the CFO?

**Reflection:** I would not ask the CFO to design SAP configuration; I would capture the business outcomes and decision context.

---

## Scenario 05 — Hidden Requirement

**Question:** A stakeholder says, “The process works today, so just migrate it.” How would you uncover hidden requirements?

**STAR Answer**

**S — Situation:** A legacy Finance process had many manual steps that users considered normal.

**T — Task:** My responsibility was to determine whether the existing process contained implicit requirements or simply workarounds.

**A — Action:** I observed the process, asked why each manual step existed, identified regulatory dependencies, controls, exceptions, spreadsheets, approvals and downstream consumers, and compared the process against business outcomes.

**R — Result:** Several hidden requirements and obsolete workarounds were identified before solution design.

**SME Probe:** How do you distinguish a real requirement from a legacy habit?

**Reflection:** Ask what risk or business outcome would be affected if the step disappeared.

---

## Scenario 06 — Non-Functional Requirements for Finance

**Question:** What non-functional requirements matter in R2R?

**STAR Answer**

**S — Situation:** A program captured detailed functional requirements but ignored performance, availability and security expectations.

**T — Task:** My responsibility was to make the requirement set architecture-ready.

**A — Action:** I captured requirements for performance, availability, security, auditability, data retention, scalability, integration latency, recovery, usability, regulatory compliance and observability. I attached measurable thresholds where possible.

**R — Result:** Solution design could address quality attributes before implementation rather than discovering them during testing.

**SME Probe:** Give an example of a Finance-specific non-functional requirement.

**Reflection:** Auditability and data traceability are often as important as response time in Finance.

---

## Scenario 07 — Prioritize Requirements

**Question:** Finance has 200 requirements and only six months for the first release. How do you prioritize?

**STAR Answer**

**S — Situation:** The backlog contained more requirements than the program could safely deliver in its first release.

**T — Task:** My responsibility was to create a transparent prioritization approach.

**A — Action:** I assessed regulatory necessity, business value, financial risk, dependency, user impact, implementation effort, architecture enablement and time sensitivity. I separated mandatory requirements from valuable enhancements and documented trade-offs.

**R — Result:** The program had an evidence-based release backlog rather than prioritization by stakeholder seniority.

**SME Probe:** Can a low-effort requirement outrank a high-value requirement?

**Reflection:** Effort matters, but risk, regulatory need and business value determine priority in context.

---

## Scenario 08 — Requirement Traceability

**Question:** How would you maintain traceability from CFO requirements to SAP implementation?

**STAR Answer**

**S — Situation:** Previous projects had requirements that could not be traced to configuration, testing or business outcomes.

**T — Task:** My responsibility was to establish end-to-end traceability.

**A — Action:** I linked business requirements to process requirements, solution capabilities, design decisions, configuration/development objects, test scenarios, acceptance criteria and measurable outcomes.

**R — Result:** Stakeholders could see why a solution component existed and whether the original requirement had actually been satisfied.

**SME Probe:** What is lost without traceability?

**Reflection:** Without traceability, scope, testing, change control and value measurement become disconnected.

---

## Scenario 09 — Acceptance Criteria

**Question:** A requirement says, “Financial reconciliation must be automated.” Is that testable?

**STAR Answer**

**S — Situation:** The requirement described an aspiration but gave no measurable definition of success.

**T — Task:** My responsibility was to make it testable.

**A — Action:** I defined what transactions were in scope, matching rules, tolerance thresholds, exception handling, processing frequency, reconciliation completeness, audit evidence and target automation rate.

**R — Result:** The requirement could be validated objectively through functional and business acceptance testing.

**SME Probe:** What is the relationship between acceptance criteria and test cases?

**Reflection:** Acceptance criteria define what must be true; test cases provide evidence that those conditions are satisfied.

---

## Scenario 10 — Regulatory Requirement

**Question:** A new statutory reporting regulation affects Finance. How would you analyze the requirement?

**STAR Answer**

**S — Situation:** A regulatory change introduced new reporting and data requirements for selected entities.

**T — Task:** My responsibility was to translate the regulation into actionable business and system requirements.

**A — Action:** I identified affected entities, reporting obligations, data elements, deadlines, controls, evidence requirements, interfaces and process changes. I then mapped the regulatory requirement to current capabilities and gaps.

**R — Result:** The program obtained a traceable regulatory requirement set and implementation impact assessment.

**SME Probe:** How would you prove regulatory compliance?

**Reflection:** Compliance needs both the implemented capability and evidence that the required process operates consistently.

---

## Scenario 11 — Requirements for Automation

**Question:** Finance wants to automate manual journal processing. What requirements would you gather?

**STAR Answer**

**S — Situation:** High-volume recurring journals consumed Finance capacity and created manual-error risk.

**T — Task:** My responsibility was to determine whether the process was suitable for automation.

**A — Action:** I documented journal types, volume, frequency, source data, calculation rules, materiality, approval requirements, exception conditions, reversals, audit evidence and segregation-of-duties constraints.

**R — Result:** The organization could identify which journals were suitable for straight-through automation and which required human judgment.

**SME Probe:** What requirement determines whether automation is safe?

**Reflection:** A clear decision rule and control boundary are prerequisites for safe automation.

---

## Scenario 12 — Requirements for AI

**Question:** Leadership says, “Use AI to improve financial close.” What requirements do you define?

**STAR Answer**

**S — Situation:** Leadership had an AI ambition but no specific use case or success definition.

**T — Task:** My responsibility was to turn the ambition into a controlled business requirement.

**A — Action:** I defined candidate decisions such as anomaly detection, variance explanation, reconciliation assistance and close-risk prediction. I captured data requirements, accuracy expectations, explainability, human approval, auditability, access control, model monitoring and measurable benefit.

**R — Result:** AI became a governed business capability requirement rather than a generic technology experiment.

**SME Probe:** What should be a mandatory AI requirement in Finance?

**Reflection:** Human accountability, traceability and controlled failure behavior should be explicit.

---

## Scenario 13 — Requirement Conflict with Standard SAP

**Question:** A business requirement does not fit standard SAP exactly. What do you do?

**STAR Answer**

**S — Situation:** A Finance process contained a requirement that differed from the standard SAP process.

**T — Task:** My responsibility was to determine whether the requirement was essential and how it should be satisfied.

**A — Action:** I challenged the requirement, identified its business rationale, tested standard process alternatives, evaluated configuration and extensibility options, and assessed process redesign before recommending customization.

**R — Result:** The decision was based on business necessity and lifecycle value rather than assuming every difference required customization.

**SME Probe:** When should an architect reject a requirement?

**Reflection:** I would challenge a requirement when it is unsupported by business value, regulation, risk or a genuine differentiating capability.

---

## Scenario 14 — Requirement for Real-Time Finance

**Question:** “We need real-time financial reporting.” What questions do you ask?

**STAR Answer**

**S — Situation:** Executives requested real-time Finance information without defining what “real-time” meant.

**T — Task:** My responsibility was to clarify the actual requirement.

**A — Action:** I asked which decisions required real-time information, acceptable latency, data scope, provisional-versus-final status, user groups, frequency, security and business impact of stale data.

**R — Result:** “Real-time” was converted into specific latency and information requirements for different use cases.

**SME Probe:** Is one-second latency always a valid Finance requirement?

**Reflection:** Latency should be derived from the business decision, not from technology enthusiasm.

---

## Scenario 15 — Stakeholder Says “Everything Is Critical”

**Question:** Every Finance stakeholder marks their requirement as critical. How do you respond?

**STAR Answer**

**S — Situation:** Requirement prioritization became impossible because every business unit classified its needs as critical.

**T — Task:** My responsibility was to create an objective prioritization mechanism.

**A — Action:** I required stakeholders to identify regulatory consequence, financial risk, business impact, affected population, dependency and deadline. I then used agreed scoring criteria and governance to distinguish mandatory from desirable requirements.

**R — Result:** The backlog became more transparent and trade-offs could be discussed objectively.

**SME Probe:** Who should own prioritization?

**Reflection:** Prioritization should be governed by accountable business owners with architecture and delivery input.

---

## Scenario 16 — Requirements Across Multiple Countries

**Question:** How do you collect requirements across 30 countries without creating 30 different solutions?

**STAR Answer**

**S — Situation:** A global Finance program had country teams with different processes and reporting needs.

**T — Task:** My responsibility was to identify common requirements and legitimate localization.

**A — Action:** I used a common requirement taxonomy and captured country-specific requirements separately. I compared them for semantic similarity, regulatory basis, process impact and business value, then created global requirements with explicit local variants.

**R — Result:** The program could distinguish genuine country requirements from duplicated preferences.

**SME Probe:** What is a good requirement taxonomy?

**Reflection:** Organize by capability, process, data, controls, integration, reporting, security and non-functional needs.

---

## Scenario 17 — Requirement Change During Implementation

**Question:** A CFO introduces a major new requirement halfway through implementation. What do you do?

**STAR Answer**

**S — Situation:** A significant new reporting requirement emerged after solution design had already progressed.

**T — Task:** My responsibility was to assess impact without allowing uncontrolled scope expansion.

**A — Action:** I documented the new requirement, assessed business value and urgency, traced affected processes, data, integrations, configuration, testing, timeline, cost and architecture, and presented options through formal change governance.

**R — Result:** Leadership could make an informed decision based on impact rather than simply accepting or rejecting the request.

**SME Probe:** What makes a change urgent enough to disrupt the current release?

**Reflection:** Regulatory deadlines, material risk and critical business outcomes can justify reprioritization, but the impact must remain explicit.

---

## Scenario 18 — Requirements from Process Mining

**Question:** Process mining reveals that users bypass the designed R2R process. How does that become a requirement?

**STAR Answer**

**S — Situation:** Observed process data showed frequent deviations from the documented process.

**T — Task:** My responsibility was to determine whether the deviation indicated a missing capability, poor design or non-compliance.

**A — Action:** I analyzed the variants, user behavior, business context, exception reasons and control implications. I converted recurring legitimate variants into requirements where appropriate and treated unauthorized workarounds as process/control issues.

**R — Result:** Requirements reflected actual business behavior while preserving governance.

**SME Probe:** Should every observed process variant become a requirement?

**Reflection:** No. Observation is evidence, not automatic approval.

---

## Scenario 19 — Requirements for Business Value

**Question:** How do you connect Finance requirements to measurable business value?

**STAR Answer**

**S — Situation:** The project had a large requirement backlog but weak linkage to business outcomes.

**T — Task:** My responsibility was to make value visible.

**A — Action:** I linked major requirements to metrics such as close duration, reconciliation effort, reporting latency, manual effort, control risk, audit findings, working capital visibility and decision speed.

**R — Result:** Business leaders could evaluate requirements based on expected outcomes rather than feature volume.

**SME Probe:** What if a requirement has no obvious financial benefit?

**Reflection:** Regulatory, risk-reduction, compliance and control requirements can create value through avoided exposure rather than direct savings.

---

## Scenario 20 — Architect Requirements for Future-State R2R

**Question:** You are leading requirements for a global R2R transformation. What is your approach?

**STAR Answer**

**S — Situation:** The enterprise had fragmented processes, legacy technology, inconsistent data and a mandate for intelligent Finance.

**T — Task:** My responsibility was to establish a complete, prioritized and architecture-ready requirement baseline.

**A — Action:** I would begin with business outcomes and stakeholder journeys, establish the current-state baseline, map capabilities and value streams, capture functional and non-functional requirements, define data and integration needs, identify controls, analytics and AI requirements, establish acceptance criteria, prioritize the backlog and maintain end-to-end traceability into solution design and testing.

**R — Result:** The transformation would have a defensible requirement baseline connecting business objectives to architecture, implementation and measurable value.

**SME Probe:** What is the biggest risk in requirements for a transformation program?

**Reflection:** The biggest risk is treating stakeholder statements as requirements without understanding the underlying business problem, constraints and desired outcome.

---

# Rapid-Fire Questions

1. What is a business requirement?
2. What is a functional requirement?
3. What is a non-functional requirement?
4. What is a business rule?
5. What is an acceptance criterion?
6. What is requirement traceability?
7. What is requirements prioritization?
8. How do you identify hidden requirements?
9. How do you challenge a requirement?
10. What is scope creep?
11. How do regulatory requirements affect Finance?
12. How do you gather executive requirements?
13. How do you resolve conflicting requirements?
14. How do you define requirements for automation?
15. How do you define requirements for AI?
16. What is a requirement baseline?
17. What is a requirement change request?
18. What makes a requirement testable?
19. How do you connect requirements to business value?
20. What makes a Finance requirement architecture-ready?

---

# Mastery Framework — Requirement-to-Outcome Chain

For every requirement question, move through:

**Problem → Stakeholder → Outcome → Requirement → Rule → Acceptance Criteria → Priority → Dependency → Solution Capability → Architecture Impact → Value**

Then test:

**Is it necessary? Is it measurable? Is it testable? Is it traceable? Is it owned?**

A strong architect does not simply capture what stakeholders ask for.

The architect discovers **what they actually need to achieve**.

---

# Common Anti-Patterns

Avoid:

- Treating stakeholder solution ideas as requirements.
- Starting requirements workshops with SAP screens.
- Accepting “real-time,” “automated,” or “user-friendly” without measurable definitions.
- Treating every stakeholder preference as mandatory.
- Ignoring non-functional requirements.
- Ignoring regulatory requirements.
- Failing to establish acceptance criteria.
- Losing traceability between requirements and testing.
- Allowing uncontrolled scope changes.
- Customizing SAP before challenging the requirement.
- Treating AI as a requirement without defining the decision and control boundary.

---

# Interview Evidence Bank

Prepare one real or simulated example for:

- Executive requirement elicitation
- Conflicting requirements
- Hidden requirements
- Functional requirements
- Non-functional requirements
- Requirement prioritization
- Traceability
- Acceptance criteria
- Regulatory requirements
- Automation requirements
- AI requirements
- Standard SAP vs custom requirement
- Real-time requirement
- Global/local requirements
- Requirement change control
- Process-mining-derived requirements
- Business-value mapping
- Requirement governance
- Finance transformation backlog
- Future-state R2R requirements

For each example document:

**Situation → Stakeholder → Business Problem → Requirement → Decision → Action → Acceptance Criteria → Result → Metric → Lesson**

---

# Success Criteria

You have mastered Pahacha 05 when you can:

- Convert vague business statements into precise requirements.
- Separate requirements from solution ideas.
- Elicit requirements from executives and SMEs.
- Identify hidden requirements.
- Capture functional and non-functional requirements.
- Prioritize competing Finance requirements.
- Define measurable acceptance criteria.
- Establish end-to-end traceability.
- Translate regulatory requirements into system requirements.
- Define automation and AI requirements responsibly.
- Challenge unnecessary customization.
- Clarify ambiguous terms such as “real-time.”
- Manage global versus local requirements.
- Handle requirement changes without losing governance.
- Connect every major requirement to business value.

---

## Final Interview Mantra

> **Do not ask only “What do you want the system to do?”  
> Ask “What business problem are you solving, what outcome must change, what constraint must be respected, and how will we prove that the requirement has been satisfied?”**

**BAISI PAHACHA 05 complete → proceed to Pahacha 06: Solution Design.**
