# AIG2-FI #03 — Connected Finance Data Architecture & Integration Data Model — STAR Interview

## Focus
**SAP Finance | Connected Finance | Data Architecture | Integration Data Model | SAP S/4HANA | SAP Integration Suite**

## 20 Scenario-Based Questions + STAR Answers

### 01. Connected Finance data architecture
**Question:** How would you design the data architecture for Connected Finance?
**Situation:** Finance data moves across SAP S/4HANA, banks, tax platforms, suppliers, customers and analytics.
**Task:** Establish trusted, governed financial data exchange.
**Action:** Identify systems of record, master/transaction/reference/event data, canonical Finance semantics, data contracts, ownership, quality rules, security, lineage and integration patterns.
**Result:** A coherent Finance data architecture supporting operational and analytical outcomes.
**SME Probe:** What is the first architectural decision?
**Reflection:** Establish authoritative ownership and meaning before moving data.

### 02. Universal Journal integration model
**Question:** How would you protect Finance semantics when integrating with SAP S/4HANA Universal Journal?
**Situation:** External applications need accounting information.
**Task:** Expose financial information without creating conflicting representations.
**Action:** Define S/4HANA as the authoritative source for applicable accounting state, expose governed business services, map dimensions such as company code, ledger, fiscal year, document, currency and account, and preserve document lineage.
**Result:** Consumers use consistent Finance semantics.
**SME Probe:** Why avoid direct database integration?
**Reflection:** Financial meaning should be exposed through governed capabilities rather than internal persistence structures.

### 03. Finance canonical data model
**Question:** When would you create a canonical Finance data model?
**Situation:** Many systems exchange similar but differently structured financial data.
**Task:** Reduce semantic duplication.
**Action:** Identify stable enterprise concepts such as Customer, Supplier, Invoice, Payment, Journal Entry, Account, Cost Center and Financial Document; define shared semantics and mappings.
**Result:** Reduced transformation complexity where common semantics genuinely exist.
**SME Probe:** Should every field be canonicalized?
**Reflection:** Canonical models should solve meaningful reuse problems, not become another translation burden.

### 04. Customer financial data model
**Question:** How would you model customer data for Connected Finance?
**Situation:** CRM, billing, AR and banking systems use different customer identifiers.
**Task:** Establish trusted customer financial identity.
**Action:** Define enterprise customer key, source identifiers, legal entity context, account relationships, payment attributes, credit context, lifecycle and effective dates; govern cross-reference mapping.
**Result:** Customer financial transactions can be traced consistently across systems.
**SME Probe:** How do you handle duplicate customers?
**Reflection:** Identity resolution is a Finance architecture concern because it directly affects receivables and cash.

### 05. Supplier financial data model
**Question:** How would you design supplier data integration?
**Situation:** Procurement, AP and banks hold different supplier attributes.
**Task:** Establish authoritative supplier information.
**Action:** Define supplier identity, legal entity, payment attributes, bank details, tax attributes, procurement relationships, status and effective dating with appropriate security.
**Result:** Consistent supplier processing and controlled payment data.
**SME Probe:** Which supplier fields require stronger controls?
**Reflection:** Payment and banking data require heightened protection and change controls.

### 06. Financial document integration model
**Question:** How would you design an integration model for financial documents?
**Situation:** External billing and payment platforms send information into Finance.
**Task:** Preserve accounting traceability.
**Action:** Define business document ID, accounting document ID, source system, company code, fiscal period, currency, amount, accounting dimensions, status, timestamps and correlation ID.
**Result:** End-to-end financial lineage.
**SME Probe:** Why distinguish business document and accounting document IDs?
**Reflection:** One business event can produce multiple technical and accounting representations.

### 07. Currency and amount semantics
**Question:** How would you prevent currency-related integration errors?
**Situation:** Global Finance processes transactions in multiple currencies.
**Task:** Preserve financial accuracy.
**Action:** Explicitly model transaction currency, company-code/local currency, group/reporting currency where applicable, exchange-rate type/date and amount semantics; validate decimal precision and conversion rules.
**Result:** Consistent multi-currency processing.
**SME Probe:** Why is exchange-rate date important?
**Reflection:** Currency is business context, not merely a field beside an amount.

### 08. Time and effective dating
**Question:** How would you model time in Finance integration?
**Situation:** Systems use different time zones and effective dates.
**Task:** Avoid period and status inconsistencies.
**Action:** Distinguish event timestamp, business date, posting date, document date, value date and effective-from/effective-to dates; standardize timezone handling and period logic.
**Result:** Reliable temporal Finance processing.
**SME Probe:** Why can timestamp and business date differ?
**Reflection:** Financial time is governed by business semantics, not system clocks alone.

### 09. Master-data governance
**Question:** How would you govern Finance master data across connected systems?
**Situation:** Customer, supplier, account and cost-object data are replicated widely.
**Task:** Prevent inconsistent master data.
**Action:** Define source of truth, ownership, create/change processes, validation, synchronization, exception handling and lifecycle governance.
**Result:** Better master-data consistency and fewer downstream failures.
**SME Probe:** Is one global master system always necessary?
**Reflection:** Ownership and authoritative semantics matter more than forcing every domain into one physical repository.

### 10. Event data model
**Question:** How would you design a Finance event schema?
**Situation:** Payment events must be consumed by AR, Treasury, Analytics and AI.
**Task:** Create reusable event semantics.
**Action:** Include event type, event ID, version, timestamp, source, business context, correlation ID, financial identifiers, relevant payload and security classification.
**Result:** Multiple consumers can react consistently.
**SME Probe:** Should events contain the entire transaction?
**Reflection:** Events should carry enough trusted context for the intended use without creating unnecessary coupling or sensitive-data exposure.

### 11. Data contract ownership
**Question:** How would you establish ownership for a Finance integration data contract?
**Situation:** Producer and consumer teams disagree about field meaning.
**Task:** Resolve semantic ambiguity.
**Action:** Assign business/data owner, technical owner, source of truth, schema version, quality rules, SLA, security classification and change process.
**Result:** Contract governance becomes explicit.
**SME Probe:** Who owns business meaning?
**Reflection:** Technical teams implement contracts; accountable business/data owners govern semantics.

### 12. Data quality architecture
**Question:** How would you design data-quality controls for Connected Finance?
**Situation:** Integration succeeds technically but Finance detects incorrect values.
**Task:** Detect and prevent financially significant data errors.
**Action:** Define completeness, validity, accuracy, consistency, uniqueness and timeliness rules; validate at appropriate boundaries and reconcile source-to-target outcomes.
**Result:** Data quality becomes measurable and operational.
**SME Probe:** Where should validation happen?
**Reflection:** Validate as close as practical to the point where bad data can be prevented.

### 13. Data lineage
**Question:** How would you establish lineage for a financial amount?
**Situation:** An executive asks where a reported amount originated.
**Task:** Trace it to source evidence.
**Action:** Link source transaction, transformation, integration message, target accounting document, analytical representation and reporting output through IDs and metadata.
**Result:** Explainable financial reporting.
**SME Probe:** Why is lineage important for AI?
**Reflection:** AI recommendations require trustworthy provenance.

### 14. Integration data security
**Question:** How would you protect sensitive Finance data during integration?
**Situation:** APIs and events carry financial and personal information.
**Task:** Maintain confidentiality and controlled access.
**Action:** Classify data, minimize payloads, enforce identity and authorization, encrypt transport, secure secrets, apply masking where appropriate and monitor access.
**Result:** Data moves securely according to business sensitivity.
**SME Probe:** Why classify before securing?
**Reflection:** Security controls should reflect the data's actual risk.

### 15. Data retention and lifecycle
**Question:** How would you design the lifecycle of Finance integration data?
**Situation:** Integration platforms retain messages and logs for operational purposes.
**Task:** Balance auditability, troubleshooting, cost and data minimization.
**Action:** Define retention by data type and purpose, distinguish financial evidence from technical logs, apply legal/regulatory requirements and automate lifecycle controls.
**Result:** Appropriate retention without uncontrolled data accumulation.
**SME Probe:** Should all integration messages be retained equally?
**Reflection:** Retention should be purpose- and risk-driven.

### 16. Reconciliation data model
**Question:** How would you model data for financial reconciliation?
**Situation:** Source and target systems report different transaction counts and amounts.
**Task:** Identify and resolve differences.
**Action:** Capture source ID, target ID, business date, amount, currency, status, processing timestamp, rejection reason, correlation ID and reconciliation status.
**Result:** Differences become traceable and actionable.
**SME Probe:** What is more important than record count?
**Reflection:** Financial reconciliation must compare business meaning, not merely technical messages.

### 17. Data model for agentic Finance
**Question:** How would you prepare Finance data for AI agents?
**Situation:** Agents need trusted information to make or support Finance decisions.
**Task:** Provide semantically clear and controlled data access.
**Action:** Expose governed business capabilities and data services with machine-readable schemas, provenance, freshness, authorization, confidence/context where appropriate, and auditability.
**Result:** Agents consume Finance information safely and consistently.
**SME Probe:** Why is provenance essential?
**Reflection:** An agent needs to know not only what a value is, but where and when it came from.

### 18. Data model evolution
**Question:** How would you evolve a Finance integration schema without breaking consumers?
**Situation:** A new field or semantic change is required.
**Task:** Maintain compatibility.
**Action:** Version contracts, classify backward-compatible versus breaking changes, communicate deprecation, test consumers and manage controlled rollout.
**Result:** Data-model evolution becomes predictable.
**SME Probe:** When is a new version preferable?
**Reflection:** Financial integrations should favor controlled change over surprise breakage.

### 19. Global/local Finance data architecture
**Question:** How would you balance global data standards with local Finance requirements?
**Situation:** Countries require local tax, banking and statutory attributes.
**Task:** Preserve enterprise consistency.
**Action:** Define global core entities and semantics, then support governed local extensions with ownership, effective dates and regulatory justification.
**Result:** A scalable global data model.
**SME Probe:** What prevents local extensions from fragmenting the model?
**Reflection:** Extensions should be governed exceptions, not uncontrolled alternatives.

### 20. Executive Finance data architecture
**Question:** How would you explain Connected Finance data architecture to a CFO?
**Situation:** Leadership sees multiple reports with inconsistent numbers.
**Task:** Explain how architecture restores trust.
**Action:** Show source-of-truth ownership, common Finance semantics, data contracts, lineage, quality, reconciliation and governed consumption across operational and analytical systems.
**Result:** Leadership understands that trusted Finance decisions depend on trusted connected data.
**SME Probe:** What is the executive message?
**Reflection:** The goal is not one giant database; it is one trusted interpretation of financial reality.

## Rapid-Fire Questions
1. What is a Finance system of record?
2. What is a data contract?
3. Why are Finance semantics important?
4. What is a canonical data model?
5. Why is idempotency related to data architecture?
6. What is data lineage?
7. How should currency be modeled?
8. Why distinguish business date from timestamp?
9. What makes data agent-ready?
10. How should Finance schemas evolve?

## BAISI PAHACHA™ 22-Step Mastery

1. **Domain Foundation** — Finance data and accounting semantics.
2. **Product/Technology Knowledge** — S/4HANA, Integration Suite and Finance data services.
3. **Process & Business Context** — P2P, O2C, R2R, Treasury and Tax data flows.
4. **Data & Information Model** — authoritative Finance entities and semantics.
5. **Requirement Analysis** — business data requirements and quality expectations.
6. **Solution Design** — target Connected Finance data architecture.
7. **Configuration/Development** — integration mappings and implementation implications.
8. **Integration & Architecture** — APIs, events and data contracts.
9. **Testing & Quality Assurance** — data validation and reconciliation.
10. **Deployment & Release** — controlled contract rollout.
11. **Migration & Cutover** — legacy data and interface transition.
12. **Operations & Support** — data monitoring and exception management.
13. **Troubleshooting & Root Cause Analysis** — trace data failures to source.
14. **Scenario-Based Problem Solving** — resolve semantic and integration conflicts.
15. **Risk, Controls & Security** — protect financial information.
16. **Performance & Optimization** — efficient data movement and reuse.
17. **Stakeholder Management** — business, data, IT and integration owners.
18. **Communication & Consulting** — translate data architecture into business trust.
19. **Presales / Leadership / Decision Making** — shape enterprise data decisions.
20. **Transformation & Roadmap** — evolve Finance toward connected data.
21. **Innovation & Emerging Technology** — event data, semantic services and agentic Finance.
22. **Enterprise Architecture & Business Value** — connect trusted data to Finance decisions.

## Anti-Patterns
- Treating integration data as merely technical payloads.
- Directly exposing Finance database structures.
- No source-of-truth ownership.
- Different definitions of the same Finance metric.
- Ignoring currency and time semantics.
- Replicating sensitive data unnecessarily.
- No lineage.
- No reconciliation model.
- Breaking schemas without versioning.
- Allowing AI agents to consume ungoverned Finance data.

## Interview Evidence Bank
Prepare STAR evidence for:
- Finance canonical data modeling.
- S/4HANA Finance data integration.
- Customer/supplier identity.
- Financial document lineage.
- Data-quality remediation.
- Reconciliation architecture.
- Data-security design.
- Global/local data models.
- Schema evolution.
- Agent-ready Finance data services.

## Success Criteria
You can move from **Finance data requirement → source-of-truth model → Finance semantic model → data contract → integration mapping → quality/security/lineage → reconciliation → trusted connected Finance data**.

## Final BAISI PAHACHA™ Reflection
**“Can I ensure that financial data does not merely move correctly, but retains its meaning, ownership, lineage, security and business trust across every connected system?”**

## Final Mantra
**“Move the data carefully. Preserve the meaning. Prove the lineage. Protect the trust.”**

## Progress
**AIG2-FI Connected Finance — 03/22**

**Transformation:** Finance Integration Practitioner → Finance Data Architect → Connected Finance Architect → Integration Transformation Leader.

**Next:** #04 Connected Finance API Architecture & Business Capability Services
