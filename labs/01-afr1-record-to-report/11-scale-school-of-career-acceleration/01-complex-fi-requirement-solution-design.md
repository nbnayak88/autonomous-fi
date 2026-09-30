# BAISI PAHACHA 01 — Complex FI Requirement & Solution Design

**Course:** Applied SAP S/4HANA Finance  
**Stream:** AFR1 — Record to Report  
**Lab:** Scale — School of Career Acceleration Lab for Excellence  
**Interview Mastery Series:** 01 of 22  
**Theme:** KNOW → DESIGN  
**Pahacha:** Complex FI Requirement & Solution Design

---

## Purpose

Master the ability to take an ambiguous **SAP S/4HANA Finance / FI business requirement**, discover the real accounting and business need, and convert it into a defensible solution design.

This is not a generic requirements-analysis exercise.

The candidate must demonstrate how they work with:

- General Ledger
- Universal Journal
- Company Code
- Chart of Accounts
- Ledgers
- Currencies
- Posting periods
- Document types
- Account assignments
- Document splitting
- Validations and substitutions
- Financial closing
- Intercompany accounting
- Integration with MM, SD, AA, CO, HCM/Payroll, Treasury and Tax
- Fiori and analytics
- Workflow and automation
- Security and controls
- Clean-core principles
- SAP Integration Suite
- SAP Business AI / Joule
- Migration and reporting implications

The design sequence is:

**Business Requirement → Accounting Requirement → Process → SAP Standard Capability → Gap → Solution Option → Configuration/Extension → Integration → Data → Controls → Testing → Business Outcome**

---

# How to Answer These Scenarios

Use **STAR-SME+** for every scenario.

- **S — Situation:** Business context, accounting problem, scope, scale and constraints.
- **T — Task:** Your personal responsibility.
- **A — Action:** Discovery, accounting analysis, SAP design, decisions, configuration/extension, integration and validation.
- **R — Result:** Measurable outcome.
- **SME Probe:** The deeper SAP Finance question an expert interviewer may ask.
- **Reflection:** What you learned and what you would improve.

A strong answer must show:

1. **Business ownership**
2. **Accounting understanding**
3. **SAP S/4HANA knowledge**
4. **Solution-design reasoning**
5. **Integration and data awareness**
6. **Controls and security**
7. **Testing and validation**
8. **Measurable outcome**

---

# 20 SAP Finance-Specific Interview Scenarios

## Scenario 01 — CFO Wants a Five-Day Financial Close

**Question:** The CFO says, “Our close takes 12 days. I need it reduced to five.” How would you approach the requirement?

### STAR Answer

**S — Situation:** I was working with a Finance organization whose month-end close depended heavily on manual journals, spreadsheet reconciliations, intercompany corrections and delayed upstream postings.

**T — Task:** My responsibility was to convert the executive request for a five-day close into an actionable SAP Finance solution requirement.

**A — Action:** I first avoided treating “five days” as a configuration requirement. I mapped the close activities and dependencies across FI, MM, SD, Asset Accounting, CO, Treasury and Payroll. I identified waiting time, manual journals, reconciliation bottlenecks, interface failures, late master data and approval delays. I then classified activities into standard SAP capability, configuration, automation, integration and organizational/process changes. For S/4HANA, I evaluated Universal Journal reporting, close orchestration, automated reconciliations, workflow and exception-based monitoring.

**R — Result:** The requirement became a measurable transformation backlog rather than a vague speed request, with cycle-time, manual-effort, exception and late-posting KPIs.

**SME Probe:** Which close activities would you automate first?

**Reflection:** I learned that “faster close” is an outcome; the architect must discover the constraints that actually determine close duration.

---

## Scenario 02 — Business Requests a New Posting Rule

**Question:** A business unit says, “Whenever this transaction occurs, post it automatically to a specific G/L.” What do you do before configuring it?

### STAR Answer

**S — Situation:** Finance requested automatic account determination for a recurring business transaction.

**T — Task:** I needed to establish the accounting rule and determine the safest standard SAP design.

**A — Action:** I clarified the business event, company codes, chart of accounts, document type, account assignment, material/customer/vendor context, valuation and legal requirements. I determined whether standard account determination could satisfy the requirement before considering validation, substitution, configuration or extension. I documented the rule and its exceptions and designed positive and negative test cases.

**R — Result:** The requirement became an explicit accounting rule with traceability from business event to G/L posting.

**SME Probe:** When would you use standard configuration versus substitution or custom development?

**Reflection:** I should never translate a business statement directly into customization without first identifying the standard accounting capability.

---

## Scenario 03 — Global Template with Local Statutory Requirements

**Question:** A global Finance template must support multiple countries with different statutory requirements. How would you design the requirement?

### STAR Answer

**S — Situation:** A multinational organization wanted a common S/4HANA Finance template while retaining country-specific statutory accounting requirements.

**T — Task:** My responsibility was to separate global requirements from legitimate local variations.

**A — Action:** I classified requirements into global accounting principles, group reporting needs, configurable country requirements, statutory reporting, tax requirements, local currencies, ledgers and regulatory controls. I designed the global template around common processes and data semantics while using controlled localization where legally necessary.

**R — Result:** The organization obtained a reusable global design without incorrectly forcing statutory differences into a single model.

**SME Probe:** How do you prevent localization from destroying the global template?

**Reflection:** Standardization should focus on common business meaning and governance; localization should be evidence-based.

---

## Scenario 04 — Business Wants a Custom Field in Every Finance Document

**Question:** Users request a custom field on financial documents for reporting. What would you investigate?

### STAR Answer

**S — Situation:** Finance users wanted an additional attribute on accounting transactions for management reporting.

**T — Task:** I needed to determine whether the field represented a genuine business requirement and how it should be implemented.

**A — Action:** I identified the business meaning, data owner, population rules, reporting use, lifecycle and downstream integrations. I checked whether an existing standard field, account assignment, coding block or extensibility option could meet the need. I considered clean-core impact, Fiori behavior, analytics consumption and migration implications before recommending an extension.

**R — Result:** The requirement was either satisfied through standard capability or implemented through a governed extensibility approach.

**SME Probe:** Why should reporting requirements influence transaction-data design?

**Reflection:** A field should exist because it has governed business meaning, not because a report developer wants another column.

---

## Scenario 05 — Requirement Conflicts with Clean Core

**Question:** A business-critical Finance requirement appears to require modification of standard SAP behavior. How do you respond?

### STAR Answer

**S — Situation:** A business team requested a modification to standard Finance behavior because it matched an existing legacy process.

**T — Task:** I needed to preserve the business outcome without unnecessarily increasing core complexity.

**A — Action:** I challenged the legacy assumption, clarified the required outcome, and assessed configuration, standard extensibility, APIs, events, side-by-side extensions and workflow alternatives. I documented the business value, technical debt, upgrade impact and operational consequences of each option.

**R — Result:** The decision was based on business value and lifecycle impact rather than automatically reproducing the legacy customization.

**SME Probe:** When can a non-standard approach still be justified?

**Reflection:** Clean core is a design principle, not an excuse to ignore legitimate business requirements.

---

## Scenario 06 — Finance Wants Different Posting Logic by Profit Center

**Question:** How would you analyze this requirement?

### STAR Answer

**S — Situation:** Finance wanted accounting treatment to vary according to organizational or profitability dimensions.

**T — Task:** I needed to determine whether the distinction was an accounting requirement, reporting requirement, or both.

**A — Action:** I clarified the required G/L treatment, account assignments, controlling dimensions, legal entity, valuation and reporting outcome. I checked standard account determination, substitutions, validations and document-splitting capabilities before considering extensions. I also assessed downstream CO and analytics implications.

**R — Result:** The solution addressed the actual accounting rule rather than using profit center as an arbitrary technical trigger.

**SME Probe:** How can FI and CO requirements interact here?

**Reflection:** I must distinguish financial-accounting semantics from management-reporting dimensions.

---

## Scenario 07 — Requirement for Parallel Ledgers

**Question:** The organization needs different accounting principles for group and local reporting. What would you design?

### STAR Answer

**S — Situation:** A multinational needed to report under group accounting principles while maintaining local statutory accounting.

**T — Task:** I needed to determine the ledger and accounting architecture.

**A — Action:** I analyzed accounting principles, company codes, currencies, fiscal calendars, reporting requirements and valuation differences. I evaluated leading and non-leading ledger requirements, parallel accounting, posting behavior, reporting and close impacts.

**R — Result:** The design provided a controlled basis for parallel accounting without duplicating the entire Finance process.

**SME Probe:** What factors determine whether separate ledgers are appropriate?

**Reflection:** Ledger design must follow accounting principles and reporting requirements, not merely organizational preference.

---

## Scenario 08 — Finance Wants a New Currency

**Question:** A business requests an additional currency for management reporting. How would you handle it?

### STAR Answer

**S — Situation:** Management required an additional currency for consolidated and analytical reporting.

**T — Task:** I needed to understand whether the requirement affected accounting, reporting or both.

**A — Action:** I identified company-code, transaction, local, group and reporting currency requirements, exchange-rate sources, valuation implications, historical data, performance impact and downstream analytics. I then assessed the appropriate S/4HANA currency design.

**R — Result:** The requirement was translated into a controlled currency architecture rather than simply adding a reporting field.

**SME Probe:** What happens to historical reporting when currency architecture changes?

**Reflection:** Currency decisions have long-term data and reporting consequences and should be made early.

---

## Scenario 09 — Business Requests Document Splitting

**Question:** A business wants complete financial statements by segment or business unit. How would you approach the requirement?

### STAR Answer

**S — Situation:** Management required balanced financial reporting at a defined organizational dimension.

**T — Task:** I needed to determine whether document splitting could satisfy the accounting requirement and what data would be required.

**A — Action:** I identified the reporting dimension, posting scenarios, document types, account assignments, inheritance rules, clearing behavior and edge cases. I evaluated how document splitting would affect posting, clearing, migration and reporting.

**R — Result:** The requirement became a defined document-splitting design with explicit dependencies and test cases.

**SME Probe:** What are common risks when introducing document splitting into an existing Finance landscape?

**Reflection:** Document splitting is not simply a reporting feature; it affects accounting-document behavior and must be tested end to end.

---

## Scenario 10 — Manual Journals Need Approval

**Question:** Finance wants every manual journal above a threshold approved before posting. How would you design it?

### STAR Answer

**S — Situation:** Audit identified inconsistent approval and supporting evidence for higher-value manual journals.

**T — Task:** I needed to translate the control requirement into a practical S/4HANA workflow design.

**A — Action:** I defined journal categories, materiality thresholds, preparer/approver segregation, evidence requirements, exception paths and audit trails. I evaluated workflow and authorization design and ensured the process did not block low-risk journals unnecessarily.

**R — Result:** The design created risk-based approval with clear accountability and evidence.

**SME Probe:** How would you prevent segregation-of-duties conflicts?

**Reflection:** A workflow is only a control if identity, authorization, evidence and monitoring are designed together.

---

## Scenario 11 — Finance Wants Real-Time P&L

**Question:** The CFO asks for “real-time P&L.” What questions do you ask?

### STAR Answer

**S — Situation:** Executives wanted faster profitability insight during the month.

**T — Task:** I needed to clarify what “real-time” actually meant.

**A — Action:** I asked which decisions required the information, required latency, accounting basis, treatment of unposted transactions, accruals, valuation, currency, data completeness and reconciliation expectations. I separated operational/provisional insight from finalized financial reporting and designed the appropriate S/4HANA analytics architecture.

**R — Result:** The requirement became a measurable information-latency requirement rather than an ambiguous real-time request.

**SME Probe:** Can a real-time P&L be considered the final statutory number?

**Reflection:** Information freshness and accounting finality are different concepts.

---

## Scenario 12 — Finance Wants SAP Fiori Instead of GUI-Centric Processing

**Question:** Users say, “We want a modern Finance experience.” How do you convert that into requirements?

### STAR Answer

**S — Situation:** Finance users wanted simpler role-based experiences and fewer transaction-code-driven workflows.

**T — Task:** I needed to convert a UX statement into actionable solution requirements.

**A — Action:** I mapped personas and tasks such as journal posting, approvals, reconciliation, close monitoring and exception handling. I identified required Fiori apps, role design, embedded analytics, workflow and mobile/desktop usage patterns. I prioritized high-frequency and high-friction activities.

**R — Result:** The requirement became an experience architecture rather than a generic request for “Fiori.”

**SME Probe:** What should determine which Finance activities receive redesigned UX first?

**Reflection:** UX priority should follow user frequency, business criticality, error reduction and decision value.

---

## Scenario 13 — Requirement Crosses FI and CO

**Question:** A business wants profitability reporting with both legal-accounting and management-accounting dimensions. How do you analyze it?

### STAR Answer

**S — Situation:** Finance wanted a profitability view combining financial accounting and controlling dimensions.

**T — Task:** I needed to define the information and process requirement across FI and CO.

**A — Action:** I clarified the required dimensions, source transactions, account assignments, derivations, reporting grain, reconciliation expectations and business ownership. I used the S/4HANA Universal Journal as the architectural foundation and validated how FI and CO information would be represented and consumed.

**R — Result:** The solution created a consistent financial and management-reporting model.

**SME Probe:** Why is the Universal Journal important for this requirement?

**Reflection:** Integrated accounting information reduces unnecessary reconciliation between financial and management views.

---

## Scenario 14 — New Acquisition Must Join the Finance Template

**Question:** A company acquires another business and wants it onboarded rapidly. What do you discover before designing the solution?

### STAR Answer

**S — Situation:** An acquired business had different ERP processes, master data, chart of accounts and reporting structures.

**T — Task:** My responsibility was to determine the minimum required transformation to integrate the business into the Finance landscape.

**A — Action:** I assessed legal entities, company codes, charts of accounts, ledgers, currencies, fiscal calendars, master data, open items, historical reporting, interfaces, controls and local statutory requirements. I created a transition architecture separating Day-1 requirements from later harmonization.

**R — Result:** The acquisition could be integrated through a controlled sequence rather than attempting full harmonization immediately.

**SME Probe:** What belongs in Day-1 versus the target state?

**Reflection:** Acquisition architecture needs both continuity and a deliberate path toward standardization.

---

## Scenario 15 — Tax Requirement Changes Finance Posting

**Question:** A new tax rule changes the accounting treatment of certain transactions. What is your role as an FI architect?

### STAR Answer

**S — Situation:** A regulatory change required new tax treatment and reporting for Finance transactions.

**T — Task:** I needed to assess the impact across accounting, tax determination, reporting and integration.

**A — Action:** I mapped the affected business transactions, tax determination, G/L postings, tax codes, statutory reporting, e-invoicing/DRC dependencies, interfaces and test scenarios. I coordinated with tax specialists rather than treating the change as an isolated FI configuration.

**R — Result:** The Finance solution incorporated the regulatory change with traceable accounting and reporting impacts.

**SME Probe:** Why should FI and DRC requirements be analyzed together?

**Reflection:** Tax correctness is an end-to-end business and regulatory capability, not just a posting configuration.

---

## Scenario 16 — Integration Requirement with SAP MM

**Question:** Procurement says GR/IR balances are wrong and asks Finance to “fix FI.” How would you handle it?

### STAR Answer

**S — Situation:** Finance reported GR/IR reconciliation issues while Procurement believed the problem belonged entirely to FI.

**T — Task:** I needed to identify the end-to-end accounting cause.

**A — Action:** I traced purchase order, goods receipt, invoice receipt and accounting-document flows. I checked quantity/value differences, timing, account determination, master data, blocked invoices and clearing behavior. I brought MM and Finance stakeholders together around the common process rather than assigning ownership prematurely.

**R — Result:** The root cause could be addressed across the MM–FI process, reducing repeated reconciliation effort.

**SME Probe:** What is the significance of GR/IR from an R2R perspective?

**Reflection:** Cross-module Finance issues should be diagnosed through the business transaction flow, not by module boundaries.

---

## Scenario 17 — Integration Requirement with SAP SD

**Question:** Revenue accounting is inconsistent between billing and Finance. What would you investigate?

### STAR Answer

**S — Situation:** Sales reported completed billing transactions, but Finance identified differences in accounting and revenue reporting.

**T — Task:** I needed to determine whether the issue originated in SD, FI account determination, timing, master data or reporting.

**A — Action:** I traced sales order, delivery, billing and accounting events, then checked revenue account determination, customer/material master data, posting dates, cancellations, credit memos and reporting definitions.

**R — Result:** The requirement was reframed as an end-to-end O2C-to-FI accounting problem rather than a Finance-only defect.

**SME Probe:** What evidence would you use to reconcile billing and accounting?

**Reflection:** Revenue architecture requires transaction-level traceability from commercial event to accounting document.

---

## Scenario 18 — Requirement Cannot Be Met Through Standard Configuration

**Question:** You conclude that standard S/4HANA configuration does not fully satisfy a business requirement. What happens next?

### STAR Answer

**S — Situation:** A legitimate business requirement had a gap against standard SAP functionality.

**T — Task:** I needed to recommend a sustainable solution without jumping directly to custom code.

**A — Action:** I documented the gap, challenged the requirement for unnecessary legacy behavior, evaluated configuration and standard extensibility, then considered released APIs, events, workflow, side-by-side extension and only then custom development where justified. I documented lifecycle, security, testing and upgrade implications.

**R — Result:** The organization received a transparent solution decision with explicit trade-offs.

**SME Probe:** What should an architecture decision record contain?

**Reflection:** A gap is not automatically a customization requirement; it is a trigger for structured solution evaluation.

---

## Scenario 19 — AI/Joule Requirement for Finance

**Question:** Finance asks for an AI assistant that can explain unusual journal entries. How would you design the requirement?

### STAR Answer

**S — Situation:** Finance wanted faster investigation of unusual journals and variances.

**T — Task:** I needed to determine whether an AI capability could safely augment analysts.

**A — Action:** I defined the user, decision, trusted data sources, explanation requirements, authorization boundaries, audit needs, confidence expectations and escalation path. I considered SAP Business AI/Joule capabilities, governed Finance data, human review and read-only investigation before any transactional autonomy.

**R — Result:** The requirement became a controlled AI-assisted investigation use case with measurable accuracy and productivity criteria.

**SME Probe:** What should prevent an AI assistant from becoming an uncontrolled posting agent?

**Reflection:** AI architecture must define authority boundaries explicitly.

---

## Scenario 20 — Architect a Complete R2R Requirement

**Question:** You receive the statement: “We need a world-class autonomous Finance close.” What do you do?

### STAR Answer

**S — Situation:** Executive leadership expressed a strategic ambition for autonomous Finance without defining the detailed business or technology requirements.

**T — Task:** My responsibility was to convert the ambition into an executable SAP Finance architecture and transformation backlog.

**A — Action:** I decomposed the ambition into capabilities: close orchestration, automated reconciliations, journal automation, intercompany matching, accrual automation, anomaly detection, real-time visibility, workflow, AI assistance and controlled autonomy. I mapped each capability to business processes, S/4HANA Finance functions, data, integration, security, controls, UX and measurable KPIs. I then classified requirements into standard SAP, configuration, extension, integration, automation and innovation.

**R — Result:** The executive vision became a traceable R2R transformation architecture with measurable outcomes and clear implementation priorities.

**SME Probe:** What would you refuse to automate initially?

**Reflection:** I would not automate high-risk financial decisions merely because technology can technically perform them; materiality, explainability, controls and reversibility must determine the autonomy boundary.

---

# Rapid-Fire SAP Finance Questions

1. What is the difference between a business requirement and an SAP configuration requirement?
2. How do you identify the real requirement behind “make it like the legacy system”?
3. When do you use standard SAP?
4. When do you consider extensibility?
5. What is clean core?
6. What is the Universal Journal?
7. What is a company code?
8. What is a chart of accounts?
9. What are leading and non-leading ledgers?
10. Why are currencies important during requirement analysis?
11. When would document splitting be relevant?
12. What are validations and substitutions?
13. How do FI and CO requirements interact?
14. Why must MM and SD be included in R2R requirement analysis?
15. What makes a Finance requirement testable?
16. How do you handle global versus local requirements?
17. How do you handle conflicting Finance stakeholder requirements?
18. What is an architecture decision record?
19. How do you assess an AI requirement for Finance?
20. What makes a Finance solution scalable?

---

# Mastery Framework — DESIGN-FI

Use this 7-step method for complex SAP Finance requirement and solution-design interviews.

### 1. DISCOVER
Understand the business event, accounting problem, users, entities, volume and regulatory context.

### 2. INTERPRET
Translate the business statement into accounting rules, process requirements, data requirements and measurable outcomes.

### 3. STANDARDIZE
Identify relevant standard S/4HANA Finance capabilities before considering customization.

### 4. EXPLORE
Evaluate configuration, extensibility, integration, workflow, analytics, automation and AI options.

### 5. INTEGRATE
Assess MM, SD, AA, CO, HCM/Payroll, Treasury, Tax, banking, data and reporting dependencies.

### 6. GOVERN
Validate security, controls, clean-core principles, auditability, testing, migration and lifecycle impact.

### 7. PROVE
Define acceptance criteria, KPIs, reconciliation evidence and measurable business value.

**Memory line:**

> **Discover → Interpret → Standardize → Explore → Integrate → Govern → Prove**

---

# Common Anti-Patterns

Avoid:

- Jumping directly to SAP configuration.
- Starting with transaction codes.
- Reproducing legacy customization without challenging the requirement.
- Treating FI as an isolated module.
- Ignoring accounting principles.
- Ignoring company code, ledger and currency implications.
- Ignoring MM/SD/AA/CO dependencies.
- Treating every requirement as a customization.
- Designing fields without business ownership.
- Ignoring clean-core principles.
- Ignoring security and SoD.
- Ignoring data migration.
- Ignoring testing and reconciliation.
- Treating AI as an uncontrolled automation mechanism.
- Giving an answer without measurable acceptance criteria.

---

# Interview Evidence Bank

Prepare one real or simulated STAR story for each:

- Global Finance template
- New company code
- Chart-of-accounts redesign
- Ledger/accounting-principle requirement
- Currency requirement
- Document splitting
- Validation/substitution
- Manual journal workflow
- Close acceleration
- FI-MM integration
- FI-SD integration
- FI-AA integration
- FI-CO requirement
- Tax/DRC impact
- Finance analytics
- Fiori/UX redesign
- Clean-core decision
- Finance extension
- Finance AI/Joule use case
- Autonomous Finance roadmap

For each story capture:

**Business Problem → Accounting Rule → SAP Standard → Gap → Design Decision → Integration → Controls → Testing → Result**

---

# Success Criteria

You have mastered Pahacha 01 when you can:

- Take an ambiguous CFO/Finance requirement and turn it into a precise SAP Finance requirement.
- Explain the accounting principle behind the requirement.
- Identify the relevant S/4HANA Finance capability.
- Distinguish configuration from extension and customization.
- Defend standard-versus-custom decisions.
- Analyze FI integration with MM, SD, AA, CO, HCM, Treasury and Tax.
- Identify data, security and control implications.
- Design requirements that can actually be tested.
- Explain clean-core implications.
- Incorporate Fiori, analytics, automation and AI where relevant.
- Quantify the expected business outcome.
- Defend the design in front of a senior Finance SME or architect.

---

# Final Interview Mantra

> **“I do not translate a business statement directly into SAP configuration. I first understand the accounting and business outcome, identify the standard S/4HANA Finance capability, expose the true gap, evaluate solution options, consider integration, data, controls and clean core, and then prove the design through measurable acceptance criteria.”**

## BAISI PAHACHA 01

**Complex FI Requirement & Solution Design**

**Business Requirement → Accounting Requirement → SAP Standard → Design Decision → Integrated Solution → Controlled Outcome**
