# BAISI PAHACHA 04 — Data & Information Model

**Course:** Applied SAP S/4HANA Finance  
**Stream:** AFR1 — Record to Report  
**Lab:** Scale — School of Career Acceleration Lab for Excellence  
**Interview Mastery Series:** 04 of 22  
**Theme:** KNOW  
**Pahacha:** Data & Information Model

---

## Purpose

Build the ability to reason about **Finance data as an enterprise information architecture** rather than as tables, fields, or reports.

A strong Finance architect can connect:

**Business Event → Master Data → Transaction Data → Accounting Document → Financial Dimensions → Controls → Reconciliation → Semantic Model → Insight → Decision**

Use **STAR-SME+** for every scenario:

- **S — Situation:** Business context, pain point, stakeholders and constraints.
- **T — Task:** What you personally owned.
- **A — Action:** What you analyzed, designed, governed, validated or changed — and why.
- **R — Result:** Observable or measurable outcome.
- **SME Probe:** Expert follow-up.
- **Reflection:** Learning and improvement.

---

# 20 Scenario-Based Interview Questions

## Scenario 01 — Design the Finance Information Model

**Question:** A CFO asks, “What information architecture should Finance have?” How would you answer?

**STAR Answer**

**S — Situation:** Finance had accounting data, master data, reporting data and external information distributed across several systems with inconsistent definitions.

**T — Task:** My responsibility was to establish a common Finance information model.

**A — Action:** I classified information into business master data, reference data, transactional data, accounting documents, financial dimensions, hierarchies, controls, analytical measures and reporting semantics. I mapped each object to its owner, source, lifecycle, quality rules and consumers.

**R — Result:** Finance gained a structured view of what data exists, where it originates, who governs it and how it supports reporting and decisions.

**SME Probe:** Why is an information model different from a database model?

**Reflection:** An information model explains business meaning and relationships; a database model primarily explains technical storage.

---

## Scenario 02 — Master Data vs Transaction Data

**Question:** Explain the difference between master data and transactional data using Finance examples.

**STAR Answer**

**S — Situation:** Teams were repeatedly debating whether Finance data-quality problems originated from transactions or master data.

**T — Task:** My responsibility was to establish a clear distinction.

**A — Action:** I explained master data as relatively stable business entities such as G/L accounts, cost centers, profit centers, customers and suppliers, while transaction data represents events such as invoices, payments, journals and settlements. I then mapped dependencies between them.

**R — Result:** Teams could investigate errors by tracing transaction records back to the relevant master-data definition instead of correcting transactions blindly.

**SME Probe:** Can master data itself have transactions or history?

**Reflection:** Master data has lifecycle and historical states; “stable” does not mean “unchanging.”

---

## Scenario 03 — G/L Account Information Architecture

**Question:** A global enterprise has thousands of G/L accounts with inconsistent meanings. How would you redesign the information model?

**STAR Answer**

**S — Situation:** Different entities used accounts with similar names but different business meanings.

**T — Task:** My responsibility was to improve semantic consistency while preserving legitimate statutory requirements.

**A — Action:** I defined account semantics, hierarchy, type, ownership, lifecycle, reporting mappings, local/global relationships and governance rules. I identified duplicate or ambiguous accounts and established a controlled change process.

**R — Result:** Financial reporting could use consistent account meaning and controlled hierarchies across the enterprise.

**SME Probe:** How do you handle local accounts that cannot be eliminated?

**Reflection:** Preserve legitimate local requirements but map them to governed enterprise semantics.

---

## Scenario 04 — Financial Dimensions

**Question:** Management wants profitability by product, customer, region and business unit. How would you model the information?

**STAR Answer**

**S — Situation:** Management wanted multidimensional profitability analysis, but the required dimensions were not consistently captured.

**T — Task:** My responsibility was to define the dimensional information architecture.

**A — Action:** I identified each analytical dimension, its source, ownership, hierarchy, valid combinations, derivation logic and reporting use. I then validated whether the dimensions could be captured reliably at transaction or derivation time.

**R — Result:** Reporting requirements were translated into explicit data requirements rather than being left to dashboard developers.

**SME Probe:** What happens if a dimension is unavailable when the transaction is posted?

**Reflection:** The architecture must define whether it can be derived, enriched later, or requires a process change.

---

## Scenario 05 — Data Lineage from Source to Financial Statement

**Question:** An auditor asks, “Where did this number in the financial statement come from?” What should your architecture provide?

**STAR Answer**

**S — Situation:** Audit and Finance teams needed to trace reported amounts back to source transactions.

**T — Task:** My responsibility was to establish end-to-end financial data lineage.

**A — Action:** I mapped the lineage from business source and transaction through accounting document, journal, aggregation, adjustments, reporting semantic layer and final statement. I documented transformation rules, ownership and control points.

**R — Result:** The organization could explain the origin and transformation of reported numbers with evidence.

**SME Probe:** What is the difference between technical lineage and business lineage?

**Reflection:** Technical lineage shows system/data movement; business lineage explains meaning and business transformation.

---

## Scenario 06 — Finance Data Quality

**Question:** Finance reports have missing profit centers and inconsistent customer classifications. How would you approach the problem?

**STAR Answer**

**S — Situation:** Reporting quality was affected by incomplete and inconsistent dimensions.

**T — Task:** My responsibility was to identify root causes and establish measurable data-quality improvement.

**A — Action:** I profiled completeness, validity, consistency, uniqueness and timeliness. I traced defects to master-data creation, interfaces, derivation rules and user processes, then defined quality rules, owners, remediation and monitoring.

**R — Result:** Data-quality management shifted from manual report correction to measurable prevention and monitoring.

**SME Probe:** Which quality dimension would you prioritize first?

**Reflection:** Prioritize according to business materiality and decision impact, not simply the largest defect count.

---

## Scenario 07 — Reconciliation Data Model

**Question:** How would you design data to support automated reconciliation?

**STAR Answer**

**S — Situation:** Finance spent significant time manually matching records between operational systems and accounting.

**T — Task:** My responsibility was to identify the information needed for reliable matching.

**A — Action:** I defined stable transaction identifiers, source references, dates, amounts, currencies, business partners, document relationships, status, tolerance rules and exception attributes. I ensured the data was retained consistently across interfaces.

**R — Result:** The architecture created a foundation for automated matching and exception-based reconciliation.

**SME Probe:** Why are shared identifiers important?

**Reflection:** Without reliable correlation keys, reconciliation becomes probabilistic and expensive.

---

## Scenario 08 — Hierarchies and Aggregation

**Question:** A CFO wants to see P&L by enterprise, region, country and business unit. What data architecture issues arise?

**STAR Answer**

**S — Situation:** Different reports used different organizational hierarchies, causing conflicting management views.

**T — Task:** My responsibility was to establish governed aggregation structures.

**A — Action:** I identified hierarchy types, ownership, effective dates, parent-child relationships, versioning and reporting rules. I separated legal structures from management structures where necessary.

**R — Result:** Reports could use governed hierarchies and produce consistent rollups.

**SME Probe:** Why does hierarchy versioning matter?

**Reflection:** Organizations change; historical reporting should not be unintentionally rewritten by current organizational structures.

---

## Scenario 09 — Time-Dependent Finance Data

**Question:** Why does effective dating matter in Finance information architecture?

**STAR Answer**

**S — Situation:** A reporting team used today's organizational hierarchy to analyze historical transactions.

**T — Task:** My responsibility was to preserve historical context.

**A — Action:** I identified attributes that change over time, such as organizational assignments, hierarchies and master-data classifications. I introduced effective dates or historical versions where appropriate and defined reporting rules.

**R — Result:** Historical reporting could reflect the appropriate organizational context rather than blindly applying today's master data.

**SME Probe:** When should historical attributes be preserved?

**Reflection:** Preserve historical context whenever a change affects interpretation, control, auditability or comparative reporting.

---

## Scenario 10 — Semantic Layer and KPI Definitions

**Question:** Revenue is calculated differently in three dashboards. What is the data architecture problem?

**STAR Answer**

**S — Situation:** Multiple analytical teams created their own revenue calculations from the same source data.

**T — Task:** My responsibility was to establish a governed semantic definition.

**A — Action:** I documented the business definition, calculation logic, inclusion/exclusion rules, dimensions, grain, source, owner and refresh expectations. I established a governed semantic model for consumption.

**R — Result:** Consumers could use a common revenue definition and trace it to authoritative source information.

**SME Probe:** Is a KPI definition a data governance artifact?

**Reflection:** Yes. Business semantics are part of data architecture and should be governed accordingly.

---

## Scenario 11 — Data Grain

**Question:** Two Finance reports produce different totals because one uses journal-line data and the other uses aggregated monthly data. How would you diagnose it?

**STAR Answer**

**S — Situation:** Analysts were comparing reports built at different levels of data granularity.

**T — Task:** My responsibility was to identify whether the discrepancy was caused by aggregation, filtering or data logic.

**A — Action:** I documented the grain of each dataset, dimensions available at that grain, aggregation rules, duplicate risks and filtering logic. I traced both reports back to the underlying transaction population.

**R — Result:** Stakeholders understood why apparently similar reports could produce different results and how to establish controlled comparison rules.

**SME Probe:** Why must grain be documented?

**Reflection:** Without grain, aggregation and duplication behavior cannot be reasoned about reliably.

---

## Scenario 12 — Data Integration Across Finance Systems

**Question:** Finance receives data from banks, payroll, tax systems and operational applications. What information architecture controls would you establish?

**STAR Answer**

**S — Situation:** Multiple systems supplied finance-relevant information using different formats, identifiers and frequencies.

**T — Task:** My responsibility was to create consistent information exchange and control.

**A — Action:** I defined source ownership, canonical attributes, mappings, validation, interface identifiers, timestamps, reconciliation totals, error handling, lineage and retention requirements.

**R — Result:** Data movement became traceable and exceptions could be isolated by source, interface and business impact.

**SME Probe:** What is the difference between integration monitoring and data-quality monitoring?

**Reflection:** Integration monitoring asks whether data moved correctly; data-quality monitoring asks whether the data itself is fit for purpose.

---

## Scenario 13 — Data Retention and Auditability

**Question:** Finance wants to archive old data to reduce platform cost. What would you consider?

**STAR Answer**

**S — Situation:** The organization wanted to reduce the cost and performance impact of historical Finance data.

**T — Task:** My responsibility was to balance cost optimization with statutory, audit, reporting and business requirements.

**A — Action:** I classified data by retention requirement, legal/audit need, reporting value, access frequency and sensitivity. I designed an archive strategy with retrieval controls, lineage, integrity and documented ownership.

**R — Result:** The organization could reduce active-data volume without losing required financial evidence.

**SME Probe:** Is archived data still part of the information architecture?

**Reflection:** Yes. If the enterprise has a responsibility to retrieve or prove information, its archived state must be architected and governed.

---

## Scenario 14 — Sensitive Finance Data

**Question:** Finance wants broad analytics access, but some financial information is highly sensitive. How would you design access?

**STAR Answer**

**S — Situation:** Users wanted self-service Finance analytics while security teams required strict control over sensitive information.

**T — Task:** My responsibility was to balance analytical usefulness with confidentiality and segregation requirements.

**A — Action:** I classified data by sensitivity, defined role and attribute-based access where appropriate, restricted sensitive dimensions, established masking or aggregation requirements, and aligned access with business responsibilities and audit controls.

**R — Result:** Users could access the information necessary for their roles without creating uncontrolled visibility of sensitive financial data.

**SME Probe:** Why can row-level access be insufficient?

**Reflection:** Security can involve attributes, aggregation, derived measures, exports and downstream copies, not only individual records.

---

## Scenario 15 — Data Migration and Reconciliation

**Question:** During an S/4HANA migration, how would you prove that Finance data is complete and accurate?

**STAR Answer**

**S — Situation:** A legacy Finance system was being migrated and leadership required confidence in financial completeness.

**T — Task:** My responsibility was to define a data-validation and reconciliation approach.

**A — Action:** I established record counts, control totals, balances, key dimensions, master-data mappings and exception thresholds. I reconciled opening balances and material populations before and after migration and retained evidence for sign-off.

**R — Result:** Migration quality became measurable and auditable rather than being judged only by technical load success.

**SME Probe:** What would you reconcile besides total G/L balances?

**Reflection:** Reconcile at multiple meaningful levels: company, account, currency, subledger, material dimensions and key transaction populations.

---

## Scenario 16 — Finance Data for AI

**Question:** Leadership wants AI to detect anomalies in financial transactions. What data architecture must exist first?

**STAR Answer**

**S — Situation:** Finance wanted anomaly detection but transaction and master-data quality varied across entities.

**T — Task:** My responsibility was to determine whether the information foundation was ready for AI.

**A — Action:** I assessed data completeness, historical depth, labels or known outcomes, transaction grain, master-data consistency, lineage, access, feature stability and monitoring requirements. I defined an AI data pipeline with governed inputs and human validation.

**R — Result:** AI readiness became a measurable data-quality and governance problem rather than simply a model-selection exercise.

**SME Probe:** Why can poor master data damage anomaly detection?

**Reflection:** An AI model can learn normal-looking patterns from incorrect or inconsistent data and produce misleading alerts.

---

## Scenario 17 — Single Source of Truth

**Question:** The business asks for “one source of truth for Finance.” What does that actually mean?

**STAR Answer**

**S — Situation:** Different teams claimed that their ERP, data warehouse, spreadsheet and reporting platform was the source of truth.

**T — Task:** My responsibility was to clarify the requirement.

**A — Action:** I separated system of record, authoritative source for a specific data domain, analytical source, reporting semantic layer and presentation layer. I assigned ownership and lineage rather than assuming one physical database must contain everything.

**R — Result:** The organization gained a more precise information architecture and avoided an unrealistic “one database for everything” objective.

**SME Probe:** Can multiple systems legitimately be authoritative for different data domains?

**Reflection:** Yes. “Single source of truth” should describe governed authority and semantics, not necessarily one physical platform.

---

## Scenario 18 — Data Ownership and Stewardship

**Question:** Finance data-quality problems keep returning because nobody owns them. What would you establish?

**STAR Answer**

**S — Situation:** Data defects were repeatedly corrected by analysts without a clear accountable owner.

**T — Task:** My responsibility was to establish governance and accountability.

**A — Action:** I defined data owners, stewards, custodians, quality rules, issue-management workflows, escalation paths and KPIs. I linked critical data elements to business processes and control responsibilities.

**R — Result:** Data quality became an owned operational capability instead of an informal cleanup activity.

**SME Probe:** What is the difference between a data owner and data steward?

**Reflection:** Ownership is accountable for business meaning and decisions; stewardship is typically responsible for operational quality and governance execution.

---

## Scenario 19 — Data Architecture for Real-Time Finance

**Question:** Executives want near-real-time financial insight. What data architecture decisions matter?

**STAR Answer**

**S — Situation:** Leadership wanted financial information closer to operational time rather than waiting for periodic reporting.

**T — Task:** My responsibility was to define the information architecture without confusing operational data with finalized accounting results.

**A — Action:** I defined latency requirements, source systems, event or batch patterns, data freshness indicators, provisional-versus-final status, semantic rules, reconciliation and security. I designed the analytical flow around decision use cases.

**R — Result:** Leadership could consume timely information while understanding its accounting status and confidence level.

**SME Probe:** How should a dashboard communicate data freshness and financial finality?

**Reflection:** Users need both timestamp/freshness and accounting-status context to interpret real-time financial information correctly.

---

## Scenario 20 — Architect the Future-State Finance Information Model

**Question:** You are asked to create the target Finance information architecture for a global S/4HANA transformation. What would you do?

**STAR Answer**

**S — Situation:** The enterprise had fragmented master data, inconsistent financial dimensions, multiple reporting definitions, legacy integrations and limited lineage.

**T — Task:** My responsibility was to define a governed information architecture that could support reporting, analytics, automation and AI.

**A — Action:** I would establish the Finance information domain model, critical data elements, ownership, authoritative sources, master-data lifecycle, transaction grain, dimensions, hierarchies, semantic definitions, lineage, quality rules, integration contracts, retention, security and analytical consumption. I would then map these to the S/4HANA core, integration layer and analytical platform.

**R — Result:** The enterprise would have a governed Finance information foundation capable of supporting trusted reporting, reconciliation, automation, advanced analytics and AI.

**SME Probe:** What would you establish before building dashboards?

**Reflection:** I would establish business definitions, authoritative data, grain, lineage, quality and ownership before multiplying reports.

---

# Rapid-Fire Questions

1. What is a Finance information model?
2. What is master data?
3. What is transaction data?
4. What is reference data?
5. What is a critical data element?
6. What is data grain?
7. What is data lineage?
8. What is business lineage?
9. What is technical lineage?
10. What is a semantic layer?
11. What is a financial dimension?
12. Why do hierarchies need governance?
13. Why does effective dating matter?
14. What makes Finance data high quality?
15. What is reconciliation data?
16. What is a system of record?
17. What is an authoritative source?
18. What is data ownership?
19. What data is required for Finance AI?
20. What makes Finance information architecture trustworthy?

---

# Mastery Framework — Finance Information Architecture Lens

For every data question, move through:

**Business Meaning → Data Object → Source → Owner → Grain → Relationship → Quality → Lineage → Security → Lifecycle → Consumer → Outcome**

Then ask:

**Can this data support accounting, reporting, reconciliation, automation, analytics and AI reliably?**

A strong architect does not merely say:

> “This field exists in SAP.”

The stronger answer is:

> “This business concept is represented by this governed data object, sourced from this process, owned by this role, captured at this grain, validated through these controls, and consumed for this decision.”

---

# Common Anti-Patterns

Avoid:

- Treating data architecture as database design only.
- Calling every reporting platform a “source of truth.”
- Ignoring data grain.
- Ignoring effective dates and historical context.
- Building dashboards before defining KPI semantics.
- Treating master-data cleanup as a one-time migration activity.
- Ignoring lineage.
- Ignoring data ownership.
- Assuming technically complete data is automatically business-quality data.
- Feeding AI with uncontrolled financial data.
- Treating security as an analytics-only concern.

---

# Interview Evidence Bank

Prepare one real or simulated example for:

- Finance information model
- Master-data governance
- G/L account harmonization
- Financial dimensions
- Data lineage
- Data-quality improvement
- Automated reconciliation
- Hierarchy governance
- Effective-dated reporting
- KPI semantic governance
- Data-grain analysis
- Finance integration
- Data retention
- Sensitive-data security
- Migration reconciliation
- AI data readiness
- Source-of-truth architecture
- Data ownership
- Real-time finance analytics
- Target Finance information architecture

For each example document:

**Situation → Data Problem → Your Role → Information Model → Decision → Action → Result → Metric → Lesson**

---

# Success Criteria

You have mastered Pahacha 04 when you can:

- Explain Finance data as a business information architecture.
- Distinguish master, transaction, reference and analytical data.
- Explain data grain clearly.
- Design financial dimensions and hierarchies.
- Trace a financial number from source to report.
- Explain technical and business lineage.
- Diagnose Finance data-quality problems systematically.
- Design reconciliation-ready data.
- Govern KPI semantics.
- Explain effective dating and historical reporting.
- Design Finance data ownership and stewardship.
- Balance analytical access with security.
- Define migration reconciliation evidence.
- Assess Finance data readiness for AI.
- Explain “single source of truth” precisely.
- Design a target Finance information architecture.

---

## Final Interview Mantra

> **Do not answer “Where is the data?” first.  
> Answer “What does the data mean, who owns it, where does it originate, at what grain is it captured, how is it governed, and what decision does it enable?”**

**BAISI PAHACHA 04 complete → proceed to Pahacha 05: Requirement Analysis.**
