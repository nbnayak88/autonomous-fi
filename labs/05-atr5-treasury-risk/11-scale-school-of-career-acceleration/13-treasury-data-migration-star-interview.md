# ATR5 #13 — Treasury Data Migration — SAP Finance STAR Interview Mastery

## Purpose

Prepare for senior SAP Finance Treasury & Risk Management interviews with a strict SAP Finance focus. This module covers Treasury data migration into SAP S/4HANA, migration strategy, transaction and instrument data, master data, open items, positions, balances, valuation data, historical data, reconciliation, cleansing, mapping, mock loads, cutover, controls, testing, production support, analytics continuity, and post-go-live stabilization.

**Mastery Framework: MIGRATE-FI**  
**Model → Inspect → Govern → Integrate → Reconcile → Assure → Transition → Evolve**

---

# 20 Scenario-Based Interview Questions + STAR Framework Answers

## 01. Treasury Migration Strategy

**Scenario / Question:** How would you design a Treasury data migration strategy for an SAP S/4HANA transformation?

**Situation:** An organization was moving Treasury processes from a legacy platform into SAP S/4HANA.

**Task:** Define a controlled migration strategy covering data, finance integrity, and business continuity.

**Action:** Classified data into master data, transactions, instruments, positions, balances, valuations, reference data, and historical information. Defined migration scope, ownership, mapping, cleansing, mock loads, reconciliation, cutover, validation, and rollback principles.

**Result:** Established a migration approach that protected Treasury and Finance continuity.

**SME Probe:** Why should migration scope be defined by business purpose rather than by available legacy tables?

**Reflection:** Migration is a business transformation activity, not a database-copy exercise.

---

## 02. Treasury Data Object Classification

**Scenario / Question:** How would you determine which Treasury data objects must migrate?

**Situation:** Business stakeholders requested that all legacy Treasury data be moved.

**Task:** Define a defensible migration scope.

**Action:** Classified objects by operational necessity, accounting impact, regulatory need, reporting requirement, historical value, reconciliation dependency, and retention policy. Distinguished data required for day-one operations from archive/reference information.

**Result:** Reduced unnecessary migration while protecting required Finance and Treasury evidence.

**SME Probe:** What data should normally remain accessible even when it is not migrated into the target operational system?

**Reflection:** Not all historical information belongs in the transactional target system.

---

## 03. Treasury Master Data Migration

**Scenario / Question:** How would you migrate Treasury master data?

**Situation:** Counterparties, bank accounts, currencies, instruments, and organizational data used inconsistent legacy structures.

**Task:** Create trusted target master data.

**Action:** Defined target ownership and canonical values, mapped legacy attributes, cleansed duplicates, validated mandatory fields, controlled identifiers, established transformation rules, and reconciled counts before loading.

**Result:** Created a reliable master-data foundation for Treasury processing.

**SME Probe:** Why should master data be migrated before dependent transactions?

**Reflection:** Transaction migration is only as reliable as the master data supporting it.

---

## 04. Financial Instrument Migration

**Scenario / Question:** How would you migrate financial instruments into SAP Treasury?

**Situation:** Legacy instruments had different classifications, identifiers, and lifecycle attributes.

**Task:** Preserve instrument meaning and lifecycle status.

**Action:** Mapped instrument types, counterparties, currencies, nominal amounts, dates, rates, maturities, settlement details, valuation attributes, and status. Validated target configuration before migration.

**Result:** Preserved instrument integrity in the target Treasury process.

**SME Probe:** What happens if instrument classification is migrated incorrectly?

**Reflection:** Incorrect classification can affect lifecycle processing, valuation, risk, and accounting.

---

## 05. Treasury Transaction Migration

**Scenario / Question:** How would you migrate open Treasury transactions?

**Situation:** The legacy system contained transactions that remained economically active at cutover.

**Task:** Move required open transactions without changing their financial meaning.

**Action:** Defined transaction selection rules, extracted source records, mapped target structures, validated lifecycle status, loaded representative populations through mock cycles, and reconciled transaction counts and values.

**Result:** Established controlled migration of open Treasury transactions.

**SME Probe:** Why should closed historical transactions be treated differently from open transactions?

**Reflection:** Open transactions can affect future cash, risk, valuation, and accounting and therefore require operational continuity.

---

## 06. Treasury Position Migration

**Scenario / Question:** How would you migrate Treasury positions?

**Situation:** Risk and liquidity reporting depended on positions created from legacy transactions.

**Task:** Ensure target positions accurately represented the economic state at cutover.

**Action:** Defined position cutover rules, reconciled transaction populations, validated balances and maturities, checked currencies and counterparties, and compared target positions against the legacy baseline.

**Result:** Established confidence in post-migration Treasury positions.

**SME Probe:** Why should positions be reconciled back to transactions?

**Reflection:** Position balances are derived views; transaction lineage provides the evidence.

---

## 07. Treasury Balance Migration

**Scenario / Question:** How would you migrate Treasury-related balances into SAP Finance?

**Situation:** Legacy Treasury balances had to align with SAP Finance accounting at cutover.

**Task:** Preserve financial reporting integrity.

**Action:** Identified relevant G/L accounts, ledgers, currencies, company codes, valuation areas, and balances. Reconciled legacy balances to approved Finance baselines and validated target postings and balances.

**Result:** Established a controlled financial baseline.

**SME Probe:** Why must Treasury migration be reconciled with Finance rather than only with Treasury?

**Reflection:** Treasury data ultimately affects enterprise financial reporting.

---

## 08. Valuation Data Migration

**Scenario / Question:** How would you handle Treasury valuation data during migration?

**Situation:** The migration occurred close to a financial reporting period.

**Task:** Prevent valuation discontinuity.

**Action:** Established valuation-date rules, market-data assumptions, instrument status, prior valuation results, accounting treatment, and target recalculation requirements. Compared pre- and post-migration valuation outputs.

**Result:** Reduced valuation discontinuity risk.

**SME Probe:** When should valuation be recalculated instead of simply migrated?

**Reflection:** Target-system valuation logic may provide the authoritative result when the transaction state is correctly established.

---

## 09. Historical Treasury Data

**Scenario / Question:** How would you decide whether historical Treasury data should be migrated?

**Situation:** The organization had many years of legacy Treasury history.

**Task:** Balance historical accessibility, cost, compliance, and operational needs.

**Action:** Categorized historical data by reporting, audit, regulatory, tax, management, reconciliation, and operational value. Defined archive/access requirements separately from day-one transactional migration.

**Result:** Preserved necessary history without overloading the target operational system.

**SME Probe:** What is the difference between operational migration and historical retention?

**Reflection:** Accessibility and operational processing are separate architectural requirements.

---

## 10. Treasury Data Mapping

**Scenario / Question:** How would you create a Treasury migration mapping specification?

**Situation:** Legacy and SAP structures represented similar concepts differently.

**Task:** Build traceable source-to-target mappings.

**Action:** Documented source field, business definition, target field, transformation rule, default logic, validation rule, ownership, exception treatment, and reconciliation method.

**Result:** Created auditable mapping specifications.

**SME Probe:** Why should business definitions accompany technical field mappings?

**Reflection:** A field-to-field mapping can be technically valid while being financially wrong.

---

## 11. Treasury Data Cleansing

**Scenario / Question:** Legacy Treasury data contains duplicates and inconsistent attributes. How would you cleanse it?

**Situation:** Data profiling revealed duplicate counterparties, invalid bank details, inconsistent currencies, and incomplete instrument attributes.

**Task:** Improve data quality before migration.

**Action:** Profiled data, defined quality rules, identified authoritative sources, resolved duplicates, corrected invalid attributes, documented exceptions, and obtained business-owner approval.

**Result:** Increased migration quality and reduced downstream reconciliation issues.

**SME Probe:** Who should approve material Treasury data corrections?

**Reflection:** Data cleansing that changes financial meaning requires accountable business ownership.

---

## 12. Mock Migration Cycles

**Scenario / Question:** Why are multiple mock migrations important for Treasury?

**Situation:** The first migration rehearsal produced reconciliation differences.

**Task:** Improve migration quality before production cutover.

**Action:** Conducted repeated mock cycles covering extraction, transformation, loading, reconciliation, defect correction, performance, and business validation. Tracked defects to root cause.

**Result:** Increased migration predictability and reduced cutover risk.

**SME Probe:** What should improve between mock cycles?

**Reflection:** Each rehearsal should reduce uncertainty, not merely repeat the same process.

---

## 13. Treasury Migration Reconciliation

**Scenario / Question:** What reconciliation framework would you use for Treasury migration?

**Situation:** Business required proof that migrated Treasury information was complete and accurate.

**Task:** Establish objective migration sign-off.

**Action:** Reconciled master-data counts, transaction populations, nominal values, positions, balances, currencies, valuation outputs, and accounting impacts. Defined tolerance and evidence rules.

**Result:** Created an evidence-based migration sign-off framework.

**SME Probe:** Why are counts alone insufficient?

**Reflection:** Completeness and financial accuracy require both population and value reconciliation.

---

## 14. Treasury Migration Testing

**Scenario / Question:** What would you test during Treasury migration?

**Situation:** Treasury migration was approaching final validation.

**Task:** Prove the migrated solution works operationally.

**Action:** Tested master data, instruments, transactions, lifecycle events, valuation, accounting, cash flows, reconciliation, reporting, interfaces, security, negative cases, and volume.

**Result:** Improved confidence in target-system readiness.

**SME Probe:** Which migration test should receive special attention?

**Reflection:** End-to-end tests that connect migrated transactions to future Treasury and Finance outcomes reveal hidden defects.

---

## 15. Treasury Cutover

**Scenario / Question:** How would you plan Treasury cutover?

**Situation:** Treasury had active transactions and reporting obligations at go-live.

**Task:** Transition from legacy to SAP with minimal financial disruption.

**Action:** Defined freeze windows, final extraction, transformation, load sequence, validation gates, reconciliation, business sign-off, interface activation, contingency procedures, and command-center ownership.

**Result:** Created a controlled cutover path.

**SME Probe:** Why must Treasury cutover be synchronized with Finance close activities?

**Reflection:** Treasury and Finance have shared financial dependencies that cannot be cut over independently.

---

## 16. Treasury Migration Controls & Audit

**Scenario / Question:** What controls should govern Treasury data migration?

**Situation:** Audit and Finance leadership required evidence that migrated financial data was controlled.

**Task:** Establish migration governance.

**Action:** Implemented segregation of duties, approved mappings, controlled extracts, transformation logs, load logs, reconciliation evidence, exception approvals, access controls, and sign-offs.

**Result:** Created traceable migration evidence.

**SME Probe:** What is the purpose of transformation logs?

**Reflection:** Transformation logs establish what changed between source and target and why.

---

## 17. Treasury Migration Production Incident

**Scenario / Question:** A migrated Treasury transaction is missing after go-live. How would you investigate?

**Situation:** A business user reported that an active instrument could not be found in SAP.

**Task:** Restore operational continuity and identify the migration defect.

**Action:** Traced the transaction from source extract through transformation, staging, load, target record, and reconciliation evidence. Assessed related accounting and risk impacts and corrected the controlled population.

**Result:** Restored the transaction while identifying the migration control gap.

**SME Probe:** Why should the correction be traceable back to the source record?

**Reflection:** Post-go-live migration fixes must preserve lineage and auditability.

---

## 18. Treasury Analytics Continuity

**Scenario / Question:** How would you preserve Treasury analytics after migration?

**Situation:** Historical dashboards and new SAP analytics used different dimensions and definitions.

**Task:** Maintain management-reporting continuity.

**Action:** Mapped historical and target dimensions, KPI definitions, currencies, entities, instrument classifications, and reporting periods. Ran parallel reports and analyzed variances.

**Result:** Preserved decision continuity through the transformation.

**SME Probe:** Why can a technically successful migration still fail analytically?

**Reflection:** Analytical meaning must migrate along with the underlying records.

---

## 19. Treasury Migration Automation

**Scenario / Question:** Where would you automate Treasury migration?

**Situation:** Migration teams manually performed repetitive validation and reconciliation tasks.

**Task:** Improve migration efficiency without weakening control.

**Action:** Automated profiling, mapping validation, duplicate detection, load monitoring, count/value reconciliation, exception reporting, and evidence packaging. Retained human approval for financial exceptions.

**Result:** Reduced manual effort and improved migration consistency.

**SME Probe:** Which migration activities should remain human-controlled?

**Reflection:** Automation should remove repetitive work while preserving accountable financial decisions.

---

## 20. Enterprise Treasury Migration Architecture

**Scenario / Question:** How would you architect an enterprise Treasury migration into SAP S/4HANA?

**Situation:** Global Treasury needed to migrate multiple entities, instruments, banks, currencies, transactions, positions, and accounting dependencies.

**Task:** Define the complete migration architecture.

**Action:** Established migration scope, canonical data model, source-to-target mapping, cleansing, master-data governance, transaction migration, valuation, accounting reconciliation, mock cycles, testing, cutover, controls, analytics continuity, hypercare, and continuous improvement.

**Result:** Created a controlled migration architecture that preserved Treasury operations and Finance integrity.

**SME Probe:** What differentiates a Treasury migration architect from a migration execution analyst?

**Reflection:** The architect designs the business, data, Finance, integration, control, and cutover system that makes migration sustainable.

---

# Rapid-Fire Interview Questions

1. What is Treasury data migration?
2. How do you define migration scope?
3. Which Treasury data objects require migration?
4. How do you migrate Treasury master data?
5. How do you migrate financial instruments?
6. How do you migrate open Treasury transactions?
7. How do you validate migrated positions?
8. How do you reconcile Treasury balances with SAP Finance?
9. How do you handle valuation during migration?
10. What historical data should be migrated?
11. How do you build Treasury mapping specifications?
12. How do you cleanse legacy Treasury data?
13. Why are mock migrations necessary?
14. How do you design migration reconciliation?
15. What should Treasury migration testing cover?
16. How do you design Treasury cutover?
17. What migration controls are required?
18. How do you handle a post-go-live migration defect?
19. How do you preserve Treasury analytics continuity?
20. Where can automation and AI assist Treasury migration?

---

# @BAISI PAHACHA™ 22-Step Mastery Framework

## KNOW

1. **Domain Foundation** — Explain Treasury migration, master data, transactions, instruments, positions, valuation, balances, and reconciliation.
2. **Product/Technology Knowledge** — Explain SAP S/4HANA Finance and Treasury migration capabilities and relevant tooling.
3. **Process & Business Context** — Connect migration to liquidity, risk, accounting, reporting, close, and operational continuity.
4. **Data & Information Model** — Model source-to-target Treasury data lineage and dependencies.

## DESIGN

5. **Requirement Analysis** — Discover migration scope, data, regulatory, reporting, accounting, and operational requirements.
6. **Solution Design** — Design the end-to-end Treasury migration architecture.
7. **Configuration/Development** — Translate target Treasury requirements into SAP configuration and migration structures.
8. **Integration & Architecture** — Connect legacy sources, SAP Treasury, SAP Finance, banks, market data, and analytics.

## DELIVER

9. **Testing & Quality Assurance** — Validate migrated data, lifecycle processing, valuation, accounting, integration, and reporting.
10. **Deployment & Release** — Govern migration releases and production loads.
11. **Migration & Cutover** — Execute mock cycles, final migration, reconciliation, and cutover.
12. **Operations & Support** — Stabilize migrated Treasury processes during hypercare.

## SOLVE

13. **Troubleshooting & Root Cause Analysis** — Trace migration defects from target records back through transformation to source.
14. **Scenario-Based Problem Solving** — Resolve missing, duplicated, incorrectly mapped, or financially inconsistent Treasury data.
15. **Risk, Controls & Security** — Protect migration access, approvals, evidence, and financial integrity.
16. **Performance & Optimization** — Improve extraction, transformation, load, reconciliation, and cutover performance.

## INFLUENCE

17. **Stakeholder Management** — Align Treasury, Finance, Accounting, Risk, IT, Data, banks, and business owners.
18. **Communication & Consulting** — Explain migration status, financial differences, risks, and sign-off evidence.
19. **Presales / Leadership / Decision Making** — Shape migration strategy, scope, investment, and risk decisions.

## TRANSFORM

20. **Transformation & Roadmap** — Build a Treasury modernization and migration roadmap.
21. **Innovation & Emerging Technology** — Evaluate migration automation, intelligent profiling, anomaly detection, and AI-assisted validation.
22. **Enterprise Architecture & Business Value** — Connect migration architecture to Finance integrity, operational continuity, data quality, and transformation value.

---

# Common Anti-Patterns

- Treating migration as a technical database copy.
- Migrating every historical record without business justification.
- Loading transactions before establishing trusted master data.
- Ignoring open Treasury transactions and future lifecycle events.
- Reconciling only aggregate balances.
- Ignoring valuation and accounting continuity.
- Treating data cleansing as an IT-only responsibility.
- Running only one migration rehearsal.
- Starting cutover without explicit reconciliation gates.
- Correcting post-go-live migration defects without preserving lineage and evidence.
- Preserving technical data while losing analytical meaning.
- Automating financial exceptions without accountable human approval.

---

# Interview Evidence Bank

Prepare one concrete STAR example for each:

1. Treasury migration strategy.
2. Migration scope definition.
3. Treasury master-data migration.
4. Financial instrument migration.
5. Open transaction migration.
6. Position migration.
7. Treasury balance migration.
8. Valuation migration.
9. Historical data strategy.
10. Treasury mapping.
11. Data cleansing.
12. Mock migration.
13. Migration reconciliation.
14. Migration testing.
15. Treasury cutover.
16. Migration controls.
17. Post-go-live migration incident.
18. Analytics continuity.
19. Migration automation.
20. Enterprise Treasury migration architecture.

---

# Success Criteria

You are interview-ready when you can:

- Design an end-to-end SAP Treasury migration strategy.
- Define migration scope based on business and Finance needs.
- Migrate Treasury master data, instruments, transactions, positions, and balances.
- Design source-to-target mappings with financial meaning.
- Establish cleansing and governance rules.
- Execute multiple mock migration cycles.
- Design evidence-based reconciliation.
- Protect valuation and accounting continuity.
- Lead Treasury cutover and hypercare.
- Troubleshoot post-go-live migration defects using data lineage.
- Preserve analytics and reporting continuity.
- Identify controlled automation and AI opportunities.
- Explain every scenario using concise STAR evidence.

---

# Final BAISI PAHACHA Reflection

For every Treasury migration interview question, move beyond:

**“How will you load the data?”**

toward:

**“What business truth must survive the migration, what is the source of that truth, how is it transformed, how is it reconciled, how is it controlled, and how do we prove Treasury and Finance continuity after cutover?”**

### Final Mantra

> **“I do not migrate Treasury data. I architect the controlled transition of financial truth from legacy systems into SAP Finance.”**

---

**ATR5 Progress:** 13/22 complete  
**Next:** ATR5 #14 — Treasury Testing & Quality Assurance
