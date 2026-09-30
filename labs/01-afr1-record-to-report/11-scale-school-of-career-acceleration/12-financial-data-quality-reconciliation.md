# BAISI PAHACHA™ — Financial Data Quality & Reconciliation

## Purpose
Master SAP S/4HANA Finance interview scenarios where the consultant must prove that financial data is complete, accurate, consistent, timely, valid, traceable, and reconcilable across the Universal Journal, subledgers, interfaces, migration loads, and reporting.

## Interview Mastery Objective
Move from **“I can reconcile data”** to **“I can architect financial data quality as a continuous control.”**

---

## 20 Scenario-Based Interview Questions

### 1. Universal Journal data does not reconcile to a Finance report
**Question:** A business user says the SAC report does not match the S/4HANA Finance balance. How would you investigate?

**Situation:** Reported balances differ between the source system and analytics layer.
**Task:** Identify whether the issue is source data, transformation, filtering, timing, or reporting logic.
**Action:** Establish the source-of-truth population; reconcile ACDOCA totals by company code, ledger, fiscal period, currency, account, and document; compare extraction timestamps and transformation logic; trace a sample document end-to-end into the analytical model; check delta loads and filters.
**Result:** The reconciliation identifies the exact variance category and restores an auditable, repeatable reconciliation process.
**SME Probe:** Which dimensions would you reconcile first?
**Reflection:** Never start by changing the report. First prove where the data diverges.

### 2. AP subledger does not reconcile to the General Ledger
**Question:** AP balance differs from the corresponding G/L reconciliation account at month-end. What do you do?

**Situation:** AP subledger and G/L balances are inconsistent.
**Task:** Determine the population and timing causing the difference.
**Action:** Compare vendor open items and G/L totals by company code, reconciliation account, currency, and posting date; isolate recent postings; inspect parked/held documents, clearing, interface postings, and period status; validate that postings use the correct reconciliation account.
**Result:** The variance is classified as timing, configuration, master-data, or transaction error and corrected with evidence.
**SME Probe:** Why should direct postings to a reconciliation account normally be controlled?
**Reflection:** Reconciliation is a control, not merely a month-end spreadsheet.

### 3. AR reconciliation shows unexplained differences
**Question:** Customer balances in AR do not agree with the G/L. How would you troubleshoot?

**Situation:** AR and G/L balances differ.
**Task:** Establish the precise document population behind the difference.
**Action:** Reconcile customer line items to the reconciliation account; analyze posting dates, document types, clearing documents, special G/L transactions, currency, and period; trace integration sources and identify invalid account determination or manual adjustments.
**Result:** The variance is isolated to specific documents or configuration and the control is strengthened.
**SME Probe:** How would you distinguish a timing difference from a genuine accounting defect?
**Reflection:** Segment first; aggregate reconciliation alone hides root causes.

### 4. Bank reconciliation has a persistent difference
**Question:** The bank statement balance does not reconcile with the SAP bank G/L. What approach would you take?

**Situation:** Bank statement and book balance differ.
**Task:** Identify outstanding, duplicated, missing, or incorrectly posted transactions.
**Action:** Compare statement items, electronic bank statement processing, clearing status, bank G/L postings, value dates, and transaction references; investigate unapplied items and duplicate imports; reconcile opening balance, movement, and closing balance.
**Result:** Outstanding items are categorized and the reconciliation becomes explainable and auditable.
**SME Probe:** What controls help prevent duplicate bank-statement postings?
**Reflection:** Reconciliation should explain every difference, not merely produce a difference number.

### 5. Intercompany balances do not match
**Question:** Two company codes report different intercompany balances at close. How do you resolve it?

**Situation:** Sending and receiving entities have mismatched intercompany positions.
**Task:** Identify the transaction-level source of asymmetry.
**Action:** Match counterparties, document numbers, currencies, posting dates, exchange rates, and clearing status; trace FI-SD/MM/interface postings; check cut-off and late postings; classify timing versus substantive mismatch.
**Result:** The unmatched population is resolved and an intercompany matching control is defined.
**SME Probe:** What dimensions are essential for automated intercompany matching?
**Reflection:** Intercompany reconciliation is a shared-data problem, not just an accounting problem.

### 6. Profit-center reporting does not balance
**Question:** The balance sheet is correct, but profit-center reporting is inconsistent. What would you check?

**Situation:** Enterprise totals reconcile but management dimensions do not.
**Task:** Find missing, invalid, or inconsistently derived dimensions.
**Action:** Review document splitting, account assignments, substitution/derivation logic, master-data validity, allocation postings, and source integration; reconcile total company code values to profit-center totals.
**Result:** Dimension-level completeness and derivation controls are restored without disturbing the statutory ledger.
**SME Probe:** Why can a company-level reconciliation pass while a profit-center reconciliation fails?
**Reflection:** Aggregation can hide dimensional data-quality defects.

### 7. Migration opening balances do not reconcile
**Question:** After ECC-to-S/4HANA migration, opening balances differ from the legacy system. What is your method?

**Situation:** Migration reconciliation shows unexplained variances.
**Task:** Prove whether the difference originates in mapping, extraction, transformation, loading, or legacy data.
**Action:** Freeze the reconciliation population; compare trial balances and subledgers; validate account, company code, currency, ledger, customer/vendor, asset, and open-item mappings; trace rejected records and rounding; perform mock-load reconciliation before cutover.
**Result:** Variances are categorized, corrected, and signed off with a documented reconciliation pack.
**SME Probe:** Why reconcile at multiple levels rather than only total balance?
**Reflection:** Migration quality is demonstrated through evidence, not confidence.

### 8. Duplicate FI postings appear in an interface
**Question:** An external interface has created duplicate accounting documents. How would you respond?

**Situation:** The same business event appears more than once in Finance.
**Task:** Stop further duplication and identify the failure mode.
**Action:** Identify idempotency keys/business references; compare timestamps, interface messages, document references, and source transactions; quarantine the interface if necessary; reverse/correct duplicates under controlled procedures; implement duplicate detection and replay controls.
**Result:** The duplicate population is contained and the integration becomes safely retryable.
**SME Probe:** What is idempotency and why is it important in Finance integration?
**Reflection:** A reliable financial interface must tolerate retries without creating financial duplication.

### 9. Master-data quality causes reconciliation failures
**Question:** Several Finance reconciliations fail because accounts or business partners are mapped inconsistently. What would you do?

**Situation:** Master-data defects propagate into multiple financial controls.
**Task:** Separate master-data root causes from transaction symptoms.
**Action:** Profile account and business-partner mappings; identify duplicates, inactive values, invalid mappings, and local exceptions; establish ownership and approval rules; validate downstream impact before remediation.
**Result:** Root master-data defects are corrected and preventive controls reduce recurrence.
**SME Probe:** Which Finance master-data objects are most important to reconciliation?
**Reflection:** Poor master data creates repeated transaction-level exceptions.

### 10. Currency reconciliation shows unexpected differences
**Question:** Local-currency balances reconcile but group-currency balances do not. How do you investigate?

**Situation:** Parallel currency values differ unexpectedly.
**Task:** Determine whether the variance is legitimate valuation or a data/configuration defect.
**Action:** Compare currency types, exchange-rate types, rate dates, valuation postings, ledger settings, document currency, local currency, and group currency; trace representative documents and period-end valuation.
**Result:** Legitimate FX effects are separated from configuration or posting errors.
**SME Probe:** Why is currency architecture a reconciliation dimension?
**Reflection:** Reconciliation without currency context can create false positives.

### 11. Period-end reconciliation is too slow
**Question:** Finance spends several days manually reconciling subledgers and G/L. How would you redesign the process?

**Situation:** Reconciliation is spreadsheet-heavy and delayed.
**Task:** Improve speed without weakening financial controls.
**Action:** Map reconciliation points; standardize tolerance rules; automate source-to-target comparisons; use exception-based workflows; create ownership and ageing metrics; expose status through a Finance control tower.
**Result:** Routine matched populations become automated while SMEs focus on exceptions.
**SME Probe:** What should remain human-controlled?
**Reflection:** Automation should remove repetitive comparison, not remove accountability.

### 12. Data-quality defects recur after every close
**Question:** The same reconciliation exceptions appear every month. How do you address the pattern?

**Situation:** Corrective fixes repeat without eliminating root causes.
**Task:** Convert recurring exceptions into permanent controls.
**Action:** Trend exception categories; perform root-cause analysis; classify defects into configuration, master data, process, integration, user, and timing causes; assign control owners; introduce preventive validation and monitoring.
**Result:** Recurring defects decline and control effectiveness becomes measurable.
**SME Probe:** What metric would prove improvement?
**Reflection:** Repeated reconciliation exceptions are transformation signals.

### 13. Finance data is complete but inaccurate
**Question:** Every transaction is present, but some values are wrong. How do you distinguish completeness from accuracy?

**Situation:** Record counts reconcile, but financial values do not.
**Task:** Test the correct data-quality dimension.
**Action:** Define quality rules for amount, currency, account, company code, tax, assignment, and reference fields; sample source-to-target records; compare business rules and derivations; quantify error rates.
**Result:** Accuracy defects are isolated without confusing them with missing records.
**SME Probe:** Name key Finance data-quality dimensions.
**Reflection:** A complete dataset can still be financially wrong.

### 14. Audit asks for evidence of reconciliation
**Question:** An auditor asks how you prove that a monthly reconciliation was performed and reviewed. What evidence would you provide?

**Situation:** Control execution must be independently evidenced.
**Task:** Demonstrate completeness, review, exceptions, and resolution.
**Action:** Provide reconciliation scope, source populations, timestamped results, tolerance rules, exception log, preparer/reviewer evidence, adjustments, approvals, and closure status.
**Result:** The reconciliation is demonstrable as a controlled process rather than an informal spreadsheet activity.
**SME Probe:** What makes reconciliation evidence auditable?
**Reflection:** A control without retained evidence is difficult to defend.

### 15. A reconciliation passes total balance but fails at document level
**Question:** Overall totals match, but individual documents are unmatched. What would you do?

**Situation:** Aggregate reconciliation passes while transaction-level matching fails.
**Task:** Determine whether offsets are legitimate or masking errors.
**Action:** Match by business reference, document number, amount, currency, date, and counterparty; identify compensating errors and duplicates; assess materiality and control impact.
**Result:** Genuine matches are distinguished from offsetting errors.
**SME Probe:** Why is document-level reconciliation sometimes necessary?
**Reflection:** Equal totals do not necessarily mean equal transactions.

### 16. Data quality across an integration pipeline is inconsistent
**Question:** Finance data passes through middleware and an analytical platform before reporting. Where would you place controls?

**Situation:** Data crosses multiple architectural boundaries.
**Task:** Ensure lineage and quality across the complete flow.
**Action:** Define controls at source, interface, transformation, target, and consumption layers; use record counts, control totals, schema validation, business-rule validation, duplicate checks, and reconciliation keys.
**Result:** Each layer has measurable quality gates and failures can be localized quickly.
**SME Probe:** Why are control totals useful?
**Reflection:** Data quality is an architecture concern, not only an application concern.

### 17. Business users dispute a Finance dashboard
**Question:** Executives challenge the numbers in a Finance dashboard. How do you establish trust?

**Situation:** Confidence in financial analytics is declining.
**Task:** Trace metrics to governed source data and business definitions.
**Action:** Define KPI ownership; document calculation logic; trace lineage from dashboard to analytical model to S/4HANA source; reconcile key metrics to approved Finance reports; establish certification and change governance.
**Result:** The dashboard gains a documented semantic and reconciliation foundation.
**SME Probe:** What is the difference between data lineage and reconciliation?
**Reflection:** Lineage explains where data comes from; reconciliation proves that populations and values agree.

### 18. AI is proposed for anomaly detection in Finance
**Question:** The CFO wants AI to detect unusual financial transactions. What controls would you design first?

**Situation:** AI is proposed to identify anomalies.
**Task:** Ensure AI complements rather than bypasses Finance controls.
**Action:** Establish trusted data, quality thresholds, explainable features, human review, false-positive handling, audit logging, and escalation workflows; pilot on defined transaction populations.
**Result:** AI produces prioritized exceptions with human-controlled financial decisions.
**SME Probe:** Why should data quality precede AI anomaly detection?
**Reflection:** AI amplifies patterns in data; poor data can amplify poor signals.

### 19. Global template versus local reconciliation requirements
**Question:** A global Finance template has standardized reconciliation rules, but a country requires additional statutory controls. How do you handle it?

**Situation:** Global standardization conflicts with legitimate local requirements.
**Task:** Preserve global consistency while satisfying local compliance.
**Action:** Separate global control objectives from local implementation; assess statutory requirements; document the exception; reuse common data and reconciliation logic where possible; govern deviations through architecture and Finance ownership.
**Result:** Local compliance is addressed without unnecessary fragmentation.
**SME Probe:** What makes a local exception architecturally acceptable?
**Reflection:** Standardize the control objective first; localize only where necessary.

### 20. Designing a Finance Reconciliation Control Tower
**Question:** You are asked to architect an enterprise Finance reconciliation control tower. What would you include?

**Situation:** A multinational enterprise wants continuous visibility into financial data quality.
**Task:** Design a scalable architecture for reconciliation and exception management.
**Action:** Define reconciliation domains across GL, AP, AR, AA, banks, intercompany, migration, interfaces, and analytics; establish control totals, quality dimensions, tolerance rules, lineage, exception workflows, ownership, SLA, audit evidence, dashboards, and AI-assisted anomaly detection; integrate S/4HANA, SAP Analytics Cloud/Datasphere where applicable, and integration platforms.
**Result:** Finance moves from periodic manual reconciliation to governed, exception-driven financial data quality management.
**SME Probe:** What would be the first five KPIs?
**Reflection:** The target state is not “zero differences”; it is controlled, explainable, timely resolution of differences.

---

## Rapid-Fire Questions

1. What is the purpose of reconciliation in Finance?
2. Name six dimensions of data quality.
3. What is the Universal Journal?
4. Why reconcile subledger to G/L?
5. What is a control total?
6. What is an exception threshold?
7. How would you detect duplicate postings?
8. What is data lineage?
9. Why is master-data quality important?
10. How do you reconcile parallel currencies?
11. What is intercompany reconciliation?
12. How do migration mock loads support reconciliation?
13. Why can aggregate totals hide defects?
14. What makes reconciliation auditable?
15. Where should reconciliation controls sit in an integration architecture?
16. How can SAC support Finance reconciliation visibility?
17. What should an exception workflow contain?
18. Why is idempotency important?
19. What is preventive versus detective control?
20. How can AI support financial data-quality monitoring?

---

## DQ-RECON-FI Mastery Framework

**1. DEFINE** — Define the reconciliation scope, source of truth, dimensions, business rules, and tolerances.  
**2. PROFILE** — Profile completeness, accuracy, validity, consistency, uniqueness, and timeliness.  
**3. VALIDATE** — Validate master data, transactions, interfaces, mappings, and business rules.  
**4. RECONCILE** — Compare source-to-target, subledger-to-G/L, entity-to-entity, and ledger/currency populations.  
**5. INVESTIGATE** — Trace exceptions to document, process, master data, configuration, interface, or timing root causes.  
**6. CONTROL** — Implement preventive, detective, automated, ownership, SLA, and audit controls.  
**7. CERTIFY** — Evidence, review, approve, monitor, and continuously improve reconciliation outcomes.

### BAISI PAHACHA™ Alignment

- **KNOW:** Understand Finance data models, reconciliation objects, and quality dimensions.
- **DESIGN:** Design reconciliation architecture, rules, lineage, and controls.
- **DELIVER:** Implement, test, migrate, and operationalize controls.
- **SOLVE:** Diagnose exceptions and eliminate root causes.
- **INFLUENCE:** Explain financial-data trust to Finance, audit, IT, and business stakeholders.
- **TRANSFORM:** Evolve reconciliation into a continuous Finance data-quality and intelligence capability.

---

## Anti-Patterns to Avoid

- Treating reconciliation as a spreadsheet-only activity.
- Reconciling only total balances and ignoring dimensions.
- Fixing reports before validating source data.
- Ignoring master-data root causes.
- Using AI before establishing trusted data.
- Allowing uncontrolled manual adjustments.
- Treating every difference as an error without considering timing and valuation.
- Automating reconciliation without ownership and audit evidence.
- Designing local exceptions without global governance.
- Measuring only “number of differences” rather than age, materiality, root cause, and resolution.

---

## Interview Evidence Bank

Prepare real examples demonstrating:

- A subledger-to-G/L reconciliation you designed or improved.
- A migration reconciliation and cutover sign-off.
- A duplicate posting or interface defect you diagnosed.
- An intercompany mismatch you resolved.
- A master-data issue that caused financial defects.
- A month-end reconciliation acceleration.
- A Finance dashboard/data-quality issue you traced through lineage.
- A control or audit-evidence improvement.
- A recurring exception converted into a preventive control.
- An automation or AI opportunity for Finance data quality.

---

## Success Criteria

You are interview-ready when you can:

- Explain reconciliation as a Finance control and architecture capability.
- Diagnose differences systematically rather than guessing.
- Reconcile ACDOCA and subledger populations using meaningful dimensions.
- Explain data quality across SAP Finance integration flows.
- Design migration and cutover reconciliation controls.
- Distinguish timing, configuration, master-data, interface, and transaction defects.
- Explain audit evidence and control ownership.
- Design exception-driven reconciliation rather than spreadsheet-driven reconciliation.
- Connect data quality to reporting, AI readiness, and Finance transformation.
- Defend your decisions with business impact, control effectiveness, and measurable outcomes.

---

## Final BAISI PAHACHA™ Mantra

> **Do not merely reconcile numbers. Architect trust in financial data.**

**Master the topic → prove the data → explain the exception → control the cause → create measurable Finance confidence.**
