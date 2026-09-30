# 07 — Configuration & Development

## Course
**Applied SAP S/4HANA Finance — AFR1 Record to Report**

- **Stream:** 01 — Enterprise Architect
- **Lab:** 11 — Scale | School of Career Acceleration
- **Theme:** DESIGN
- **Pahacha:** @baisi pahacha — Step 7: Configuration / Development
- **Mastery objective:** Move from “I can configure SAP” to “I can design governed configuration and development that realizes business outcomes without compromising clean core, controls, auditability, integration, or long-term operability.”

## Purpose

Configuration and development are not isolated technical activities. In an R2R transformation, every configuration choice changes business behavior, accounting outcomes, control points, data semantics, integration contracts, testing scope, and operational risk.

A strong Finance architect can explain:

**Business requirement → design decision → configuration/development → control → test → transport → release → measurable outcome.**

The goal is not transaction-code memorization. The goal is implementation judgment.

---

# 20 Scenario-Based Interview Questions

## 1. The business asks for a custom posting behavior

**Question:** Finance wants a posting behavior that standard SAP does not appear to provide. How would you approach it?

**S — Situation:** During an R2R design, Finance requested a specialized posting rule for a business scenario that was not available through the initially proposed standard configuration.

**T — Task:** I had to determine whether the requirement truly required custom development while protecting the global template and clean-core strategy.

**A — Action:** I first decomposed the requirement into business rule, trigger, accounting outcome, control requirement, and reporting impact. I checked whether standard configuration, workflow, validation/substitution, extensibility, or process redesign could satisfy it. Only after exhausting standard options would I propose custom development. I documented the decision, business value, lifecycle impact, test implications, and ownership.

**R — Result:** The decision became evidence-based rather than “customize because the user asked.” The architecture remained maintainable and the exception had explicit governance.

**SME Probe:** How would you decide when customization is justified?

**Reflection:** Never start with “How do I code this?” Start with “What business outcome must change?”

---

## 2. Global template versus local configuration

**Question:** A country team requests different Finance configuration from the global template. What do you do?

**S:** A global R2R rollout had standardized accounting processes, but a local team identified statutory and operational differences.

**T:** I needed to separate legitimate localization from avoidable divergence.

**A:** I classified the request as regulatory, statutory, business-specific, or preference-driven. Regulatory requirements were documented with evidence. Business differences were evaluated against global process principles. I designed controlled localization points rather than allowing uncontrolled forks of the template.

**R:** The organization retained a common global core while accommodating justified local requirements.

**SME Probe:** What evidence would you require before approving localization?

**Reflection:** Global standardization should be strong; localization should be explicit, justified, and governable.

---

## 3. Posting periods create operational problems

**Question:** Users report that postings are failing because the relevant period is closed.

**S:** During period close, business teams attempted legitimate postings after operational cut-off.

**T:** I had to solve the operational issue without weakening financial controls.

**A:** I mapped the period-control process, ownership, cut-off calendar, emergency-opening authority, and downstream reporting consequences. Instead of simply widening access, I proposed controlled exception handling with approval, audit logging, and reconciliation.

**R:** The organization gained a predictable close process without turning period control into an unrestricted operational override.

**SME Probe:** Why is opening a period a control decision rather than merely a configuration change?

**Reflection:** Configuration can enforce governance—or accidentally bypass it.

---

## 4. Document types and accounting behavior

**Question:** How would you design document-type governance?

**S:** A Finance landscape had many document types created over time with inconsistent ownership and usage.

**T:** I needed to simplify the accounting model without breaking reporting or controls.

**A:** I catalogued document types by business purpose, posting behavior, authorization, reporting need, and integration source. I removed duplicates where feasible and established naming, ownership, lifecycle, and change-control standards.

**R:** The document model became easier to understand, govern, test, and support.

**SME Probe:** What would make a document type architecturally meaningful?

**Reflection:** Configuration objects should communicate business intent, not historical accidents.

---

## 5. Ledgers and currencies

**Question:** A multinational needs multiple accounting principles and currencies. What configuration considerations matter?

**S:** The organization required group, local, and management reporting with different accounting and currency requirements.

**T:** I had to ensure the ledger and currency model supported statutory compliance and management insight.

**A:** I mapped accounting principles, ledgers, currencies, company-code requirements, reporting grains, consolidation needs, and integration dependencies. I evaluated whether each ledger represented a real accounting requirement rather than creating unnecessary complexity.

**R:** The ledger and currency architecture supported required reporting while limiting avoidable configuration proliferation.

**SME Probe:** What is the risk of designing ledgers independently from reporting architecture?

**Reflection:** Ledger design is simultaneously accounting architecture, data architecture, and reporting architecture.

---

## 6. Account determination is producing unexpected results

**Question:** How would you troubleshoot an incorrect account determination?

**S:** A transaction posted to an unexpected G/L account.

**T:** I had to identify the causal configuration path and prevent recurrence.

**A:** I traced the transaction from business event to account assignment, determination logic, master data, configuration, and posting result. I reproduced the scenario in a controlled environment, identified the actual decision point, corrected the governed configuration, and regression-tested related scenarios.

**R:** The root cause was fixed rather than masked with manual journal corrections.

**SME Probe:** What evidence would you collect before changing configuration?

**Reflection:** Diagnose the decision path before changing the destination.

---

## 7. Validation versus substitution

**Question:** When would you use validation or substitution?

**S:** Finance wanted stronger consistency in accounting entries.

**T:** I had to prevent invalid postings while avoiding unnecessary manual intervention.

**A:** I used validation when the goal was to reject or flag invalid combinations and substitution when a governed derivation could safely populate or replace a value. I documented the rule, precedence, ownership, exception path, and test cases.

**R:** Data quality improved while the rule remained transparent and auditable.

**SME Probe:** What happens when too many derivation rules accumulate?

**Reflection:** Automation without governance can create invisible complexity.

---

## 8. Workflow for accounting controls

**Question:** Finance wants approval workflow around sensitive accounting activities. How do you design it?

**S:** Manual approval existed through email and spreadsheets.

**T:** I needed to convert it into a controlled digital process.

**A:** I identified trigger, requester, approver, segregation-of-duties requirement, thresholds, evidence, escalation, rejection, delegation, and audit retention. I designed workflow around the business control rather than around a particular technical feature.

**R:** Approval became traceable, repeatable, and measurable.

**SME Probe:** How would you prevent workflow from becoming a bottleneck?

**Reflection:** Good workflow removes friction while preserving control.

---

## 9. Clean-core decision

**Question:** How do you explain clean core to a Finance stakeholder?

**S:** A business team believed every unique requirement justified modifying the core ERP.

**T:** I needed to establish a sustainable extension strategy.

**A:** I explained that the objective is to keep the core stable and upgradeable while using standard configuration and supported extension mechanisms where possible. I evaluated side-by-side extensibility, APIs, events, workflow, automation, and external services before considering intrusive modification.

**R:** The stakeholder could distinguish business uniqueness from technical modification.

**SME Probe:** Does clean core mean “never customize”?

**Reflection:** Clean core is a governance and lifecycle principle, not a slogan.

---

## 10. Development object governance

**Question:** What should an architect govern when developers create Finance extensions?

**S:** Multiple teams were creating enhancements independently.

**T:** I had to prevent duplicate logic and uncontrolled technical debt.

**A:** I established design review criteria covering business ownership, API/interface usage, data model impact, security, performance, upgrade compatibility, observability, testing, support ownership, and retirement strategy.

**R:** Development became architecture-led rather than team-local.

**SME Probe:** How would you identify duplicate extensions?

**Reflection:** Every extension should have a reason to exist, an owner, and an exit strategy.

---

## 11. Transport and release governance

**Question:** A critical configuration change must move quickly to production. What do you consider?

**S:** A production issue required an urgent configuration correction during a sensitive financial period.

**T:** I had to balance speed with release control.

**A:** I classified the change, confirmed authorization, assessed dependencies, performed focused testing, verified transport sequence, captured evidence, and established post-release validation and rollback/contingency steps.

**R:** The change was deployed quickly without bypassing essential control gates.

**SME Probe:** What is the difference between emergency change and uncontrolled change?

**Reflection:** Speed is a design capability; control is what makes speed safe.

---

## 12. Unit testing configuration

**Question:** How would you design unit tests for Finance configuration?

**S:** Configuration changes affected multiple accounting scenarios.

**T:** I needed to establish confidence before integration testing.

**A:** I created positive, negative, boundary, exception, authorization, and regression cases. Each case traced back to a requirement and expected accounting outcome.

**R:** Defects were discovered earlier and testing became repeatable.

**SME Probe:** What makes a configuration test architecturally useful?

**Reflection:** Test the business rule, not just whether the screen accepts the value.

---

## 13. Debugging without creating new risk

**Question:** How should an architect approach debugging a Finance defect?

**S:** A posting behaved differently between environments.

**T:** I needed to isolate the cause without changing production behavior blindly.

**A:** I compared configuration, master data, transports, interfaces, authorizations, timing, and environment-specific dependencies. I reproduced the defect in a controlled environment and involved the appropriate functional/development specialists.

**R:** Root cause was isolated with evidence and the fix could be regression-tested.

**SME Probe:** Why should architects avoid “quick fixes” directly in production?

**Reflection:** Debugging is investigation; production change is governance.

---

## 14. Performance-aware development

**Question:** A custom Finance process is technically correct but slow. What do you investigate?

**S:** A custom reporting or processing function created unacceptable runtime during close.

**T:** I had to improve performance without changing business semantics.

**A:** I examined data volume, query patterns, processing logic, unnecessary data retrieval, synchronous dependencies, batching, caching opportunities, and architectural placement. I measured before and after rather than optimizing based on assumption.

**R:** Performance improved while accounting correctness remained intact.

**SME Probe:** How do you distinguish application performance from data-model or integration bottlenecks?

**Reflection:** Performance is an architecture property, not merely a developer concern.

---

## 15. Configuration change impacts controls

**Question:** A configuration change improves usability but weakens a control. What do you do?

**S:** Users requested fewer restrictions on a Finance process.

**T:** I needed to determine whether the restriction was operational inconvenience or a genuine control.

**A:** I traced the control objective, risk, affected population, compensating controls, and audit evidence. I redesigned the process only if the control objective remained satisfied.

**R:** Usability improvements were evaluated against risk rather than approved purely on convenience.

**SME Probe:** How do you distinguish preventive and detective controls here?

**Reflection:** Better UX is valuable only when the control objective survives.

---

## 16. Automation of repetitive configuration-driven work

**Question:** Finance wants repetitive close tasks automated.

**S:** Teams manually performed recurring checks and follow-ups.

**T:** I had to identify what could safely be automated.

**A:** I mapped the task, decision rule, exception frequency, data dependency, control requirement, and human approval point. Deterministic tasks were automated first; exceptions remained visible for human action.

**R:** Automation reduced repetitive work while preserving exception accountability.

**SME Probe:** When should automation stop and human judgment begin?

**Reflection:** Automate predictable work; expose meaningful exceptions.

---

## 17. Configuration governance board

**Question:** How would you establish configuration governance for a large Finance program?

**S:** Multiple workstreams were making overlapping design decisions.

**T:** I needed consistency without slowing delivery.

**A:** I defined design authorities, decision thresholds, configuration standards, naming conventions, documentation requirements, reuse principles, exception management, testing evidence, and change approval paths.

**R:** The program gained a common decision system instead of relying on individual experts.

**SME Probe:** What decisions should be escalated to architecture governance?

**Reflection:** Governance should handle consequential decisions, not every keystroke.

---

## 18. Migration changes configuration assumptions

**Question:** During ECC-to-S/4HANA migration, how do you handle legacy configuration?

**S:** Legacy configuration contained years of accumulated exceptions.

**T:** I needed to avoid carrying technical debt into the target platform.

**A:** I classified legacy settings into retain, redesign, replace with standard, retire, or transform. I linked each decision to business value, process impact, controls, data migration, testing, and future-state architecture.

**R:** Migration became a transformation opportunity rather than a configuration-copy exercise.

**SME Probe:** Why is “replicate everything” dangerous?

**Reflection:** Migration should preserve required business capability, not historical complexity.

---

## 19. Architecting for auditability

**Question:** How do you ensure development and configuration remain auditable?

**S:** Auditors needed evidence of who changed critical Finance behavior and why.

**T:** I had to create traceability from requirement through production.

**A:** I ensured change records, approvals, configuration rationale, transport history, test evidence, access controls, and post-release validation were linked. Critical rules had identifiable owners.

**R:** Audit evidence became part of the delivery process instead of a retrospective document hunt.

**SME Probe:** What would you consider the minimum evidence chain?

**Reflection:** Auditability is designed into the lifecycle.

---

## 20. Architect the future configuration/development model

**Question:** What does a mature R2R configuration and development model look like?

**S:** The enterprise wanted to scale Finance transformation across countries and future SAP releases.

**T:** I needed to define a sustainable operating model.

**A:** I designed a model based on global standards, controlled localization, clean-core principles, reusable extensions, API/event-driven integration, automated testing, DevSecOps-style governance, observability, release discipline, and continuous architecture review.

**R:** Configuration and development became a strategic capability supporting continuous Finance transformation rather than project-only delivery.

**SME Probe:** What would you measure to know the model is working?

**Reflection:** Maturity is demonstrated by repeatability, upgradeability, control, speed, and business outcomes.

---

# Rapid-Fire Questions

1. Configuration vs customization?
2. Why does clean core matter?
3. What is a validation?
4. What is a substitution?
5. Why are document types important?
6. What makes a configuration change high risk?
7. Why should ledger design involve reporting architects?
8. What is configuration governance?
9. Why test negative scenarios?
10. What is an emergency change?
11. Why maintain transport discipline?
12. What makes an extension sustainable?
13. How does master data affect configuration?
14. Why is auditability a design concern?
15. What is exception-driven automation?
16. How do you assess performance?
17. Why should configuration have ownership?
18. What should be retired during migration?
19. How do you protect controls while improving UX?
20. What is the architect's role in development?

---

# Mastery Framework — CONFIGURE

Use this 7-part mental model for every configuration/development question:

### 1. CLARIFY
Define the business outcome and accounting/control requirement.

### 2. CLASSIFY
Determine whether the solution is standard configuration, extension, integration, automation, or redesign.

### 3. CONSTRAIN
Identify compliance, security, clean-core, performance, data, and lifecycle constraints.

### 4. CONFIGURE
Design the smallest governed change that realizes the requirement.

### 5. CONTROL
Define authorization, auditability, exception handling, ownership, and segregation of duties.

### 6. CONFIRM
Test positive, negative, boundary, integration, regression, and performance scenarios.

### 7. CONTINUE
Transport, release, monitor, measure, document, and continuously improve.

**Memory line:**
> **Clarify → Classify → Constrain → Configure → Control → Confirm → Continue**

---

# Common Anti-Patterns

- Starting with a transaction code instead of a business requirement.
- Treating every local preference as localization.
- Copying legacy configuration without challenge.
- Customizing before checking standard capabilities.
- Treating clean core as an absolute ban on extensions.
- Allowing developers to create duplicate business logic.
- Testing only the happy path.
- Changing production configuration without evidence.
- Optimizing performance without measurement.
- Treating audit documentation as an afterthought.
- Automating decisions that require human judgment.
- Allowing configuration objects to exist without ownership.
- Ignoring downstream integration impacts.
- Designing configuration independently from data and reporting architecture.
- Treating emergency change as permission to bypass governance.

---

# Interview Evidence Bank

Prepare concrete examples for:

1. A configuration decision you defended.
2. A customization you avoided.
3. A clean-core decision.
4. A difficult global/localization trade-off.
5. A posting/account-determination issue you resolved.
6. A workflow/control you designed.
7. A production change you governed.
8. A migration configuration you retired.
9. A performance problem you diagnosed.
10. An automation opportunity you identified.
11. A configuration defect caused by master data.
12. A testing strategy that prevented production defects.
13. An audit requirement you embedded into delivery.
14. A development governance decision.
15. A situation where you challenged a stakeholder requirement.

For each example, be able to explain:

**Business problem → architectural decision → implementation choice → evidence → outcome → lesson.**

---

# Success Criteria

You have mastered this step when you can:

- Explain configuration in business language.
- Distinguish standard configuration from extension and customization.
- Design configuration with controls and auditability.
- Explain clean-core implications.
- Govern global template and localization decisions.
- Reason about ledgers, currencies, posting behavior, and accounting configuration.
- Design validation, substitution, workflow, and automation appropriately.
- Establish development governance.
- Design configuration-focused testing.
- Handle transport and release decisions.
- Diagnose configuration defects systematically.
- Evaluate performance using evidence.
- Connect configuration to data, integration, security, and reporting architecture.
- Explain migration configuration decisions.
- Defend implementation choices before an Architecture Review Board.
- Connect implementation decisions to measurable Finance outcomes.

---

# Final Interview Mantra

> **“I do not configure SAP in isolation. I translate a business and accounting requirement into governed configuration or extension, protect controls and clean core, validate the end-to-end impact, and ensure the change can be operated, audited, upgraded, and continuously improved.”**

## Architecture Lens

Every configuration/development decision should be tested against:

**Business → Process → Application → Data → Integration → Security → Technology → Control → Experience → Operations → AI → Industry.**

The architect's job is not to make configuration complicated.

**The architect's job is to make the right business behavior repeatable, controlled, explainable, and scalable.**
