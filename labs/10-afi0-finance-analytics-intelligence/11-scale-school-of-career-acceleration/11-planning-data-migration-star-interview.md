# AFI0 #11 — Planning Data Migration — STAR Interview Mastery

**Lab:** Finance Analytics & Intelligence (AFI0)  
**Track:** Scale — School of Career Acceleration  
**Domain:** SAP Finance / SAP Analytics Cloud Planning / SAP S/4HANA Finance / FP&A  
**Mastery:** **MIGRATE-INSIGHT-FI = Discover → Profile → Map → Cleanse → Transform → Load → Reconcile → Certify**

## Interview Objective

Demonstrate how to migrate Finance planning data safely into an SAP planning environment while preserving financial meaning, historical comparability, master-data integrity, version context, reconciliation and auditability.

> **STAR discipline:** Every scenario uses **Situation → Task → Action → Result**, followed by **SME Probe → Reflection**.

---

# 20 Scenario-Based Questions + STAR Answers

## 01. Planning Data Migration Strategy
**Question:** How would you design a migration strategy for Financial Planning data?

**Situation:** A company was replacing a legacy planning solution with SAP Analytics Cloud Planning.  
**Task:** Move required planning history and active planning data without carrying forward unnecessary legacy complexity.  
**Action:** I classified data by business value, profiled source quality, defined target mappings, established cleansing rules, planned controlled loads and designed reconciliation and sign-off gates.  
**Result:** The organization retained decision-relevant planning history while establishing a cleaner target model.  
**SME Probe:** Would you migrate everything?  
**Reflection:** Migration should preserve financial meaning, not simply maximize record volume.

## 02. Migration Scope
**Question:** How would you determine which planning data should be migrated?

**Situation:** Finance had many years of budgets, forecasts, simulations and obsolete planning versions.  
**Task:** Define migration scope.  
**Action:** I categorized data into active planning, approved baselines, required historical comparisons, regulatory or audit needs and obsolete information, then obtained Finance ownership decisions.  
**Result:** Migration scope was focused and defensible.  
**SME Probe:** Who should decide historical retention?  
**Reflection:** Finance business ownership should drive retention decisions.

## 03. Source Data Profiling
**Question:** What would you examine during planning-data profiling?

**Situation:** Legacy planning data contained inconsistent dimensions and duplicate records.  
**Task:** Understand migration risk before transformation.  
**Action:** I profiled accounts, cost centers, profit centers, periods, currencies, versions, scenarios, data volumes, nulls, duplicates, invalid members and calculation dependencies.  
**Result:** Migration risks became visible before target loading.  
**SME Probe:** Why profile before mapping?  
**Reflection:** You cannot design a reliable transformation without understanding the source.

## 04. Master Data Mapping
**Question:** How would you map legacy planning master data to SAP Finance?

**Situation:** Legacy account and organizational structures differed from SAP S/4HANA Finance.  
**Task:** Establish governed target mappings.  
**Action:** I mapped legacy members to SAP Finance accounts and organizational dimensions, documented one-to-many and many-to-one relationships, resolved unmapped members and obtained Finance owner approval.  
**Result:** Historical planning values could be interpreted correctly in the target model.  
**SME Probe:** What do you do with an unmapped legacy member?  
**Reflection:** An unresolved mapping is a business decision, not merely a technical exception.

## 05. Planning Version Migration
**Question:** How would you migrate budget and forecast versions?

**Situation:** Finance needed the approved budget and recent forecast cycles for historical comparison.  
**Task:** Preserve version semantics.  
**Action:** I mapped source version types to governed target versions, retained status and fiscal context, validated ownership and reconciled values by relevant dimensions.  
**Result:** Historical and current planning comparisons remained meaningful.  
**SME Probe:** Should obsolete working versions be migrated?  
**Reflection:** Version migration should follow business relevance and governance.

## 06. Scenario Migration
**Question:** How would you migrate planning scenarios?

**Situation:** The legacy system contained base, downside and upside scenarios.  
**Task:** Preserve useful scenario history without confusing it with official plans.  
**Action:** I classified scenarios, mapped their assumptions and metadata, preserved scenario context and validated that simulations remained distinct from approved versions.  
**Result:** Historical scenario analysis remained usable and clearly labeled.  
**SME Probe:** What metadata is essential for a scenario?  
**Reflection:** Scenario values without assumptions and context lose much of their decision value.

## 07. Data Cleansing
**Question:** How would you cleanse planning data before migration?

**Situation:** Legacy planning data contained duplicates, invalid members and inconsistent signs.  
**Task:** Improve data quality before loading.  
**Action:** I defined cleansing rules with Finance, corrected structural defects, resolved duplicates, standardized dimensions and documented approved transformations.  
**Result:** Target data quality improved without silently changing business meaning.  
**SME Probe:** Who approves financial transformations?  
**Reflection:** Data cleansing that changes financial meaning requires Finance ownership.

## 08. Historical Fiscal Periods
**Question:** How would you migrate historical planning periods?

**Situation:** Legacy planning used a calendar-month structure while SAP Finance used fiscal periods.  
**Task:** Preserve historical comparability.  
**Action:** I mapped historical periods to the target fiscal calendar, validated period boundaries and reconciled totals across years and organizational dimensions.  
**Result:** Historical planning could be compared consistently with SAP Finance reporting periods.  
**SME Probe:** What if historical calendars cannot be mapped perfectly?  
**Reflection:** Any unavoidable limitation must be explicit and documented.

## 09. Currency Conversion
**Question:** How would you handle currencies during planning migration?

**Situation:** Historical plans existed in local, group and reporting currencies.  
**Task:** Preserve currency semantics.  
**Action:** I identified source currency types, exchange-rate assumptions and target currency requirements, then validated converted values and documented any historical conversion methodology.  
**Result:** Finance could interpret migrated values without confusing translation effects with business changes.  
**SME Probe:** Should historical values always be recalculated using current exchange rates?  
**Reflection:** Historical financial meaning should not be rewritten without an explicit business requirement.

## 10. Migration Reconciliation
**Question:** How would you reconcile migrated planning data?

**Situation:** Finance required evidence that approved historical budgets were preserved.  
**Task:** Prove source-to-target integrity.  
**Action:** I established control totals by version, company, account, period, currency and organizational dimensions, investigated variances and obtained Finance sign-off.  
**Result:** Migration accuracy became measurable rather than assumed.  
**SME Probe:** What is the first reconciliation level?  
**Reflection:** Start with controlled financial totals and progressively drill into differences.

## 11. Migration Trial Load
**Question:** Why would you perform multiple planning-data trial loads?

**Situation:** The first migration rehearsal exposed mapping and hierarchy issues.  
**Task:** Reduce cutover risk.  
**Action:** I used trial loads to validate transformations, mappings, performance, error handling and reconciliation, then incorporated lessons into subsequent cycles.  
**Result:** The final migration became more predictable and controlled.  
**SME Probe:** What should a rehearsal prove?  
**Reflection:** A rehearsal should test the migration process, not merely demonstrate that files can be uploaded.

## 12. Migration Error Handling
**Question:** What would you do with rejected planning records?

**Situation:** A target load rejected records because of invalid account and cost-center combinations.  
**Task:** Correct the issue without bypassing controls.  
**Action:** I categorized rejected records, traced the relevant mapping or master-data defect, corrected the approved transformation and reprocessed the controlled subset.  
**Result:** Errors were resolved without corrupting the target model.  
**SME Probe:** Should rejected records be force-loaded?  
**Reflection:** Rejection is often a control signal, not an obstacle to bypass.

## 13. Migration Cutover
**Question:** How would you plan the final planning-data migration cutover?

**Situation:** Finance needed the new planning environment ready before the next forecast cycle.  
**Task:** Execute cutover with minimal business disruption.  
**Action:** I defined freeze windows, final extraction, transformation, load sequence, reconciliation, business validation, rollback criteria and sign-off responsibilities.  
**Result:** The planning environment became operational with controlled financial continuity.  
**SME Probe:** What determines cutover success?  
**Reflection:** Cutover success is measured by business readiness and reconciled financial integrity.

## 14. Planning Migration Security
**Question:** How would you protect Finance data during migration?

**Situation:** Planning data contained sensitive financial and organizational information.  
**Task:** Maintain security throughout extraction, transformation and loading.  
**Action:** I applied least-privilege access, controlled migration identities, protected working files and environments, restricted target access and maintained evidence of migration activity.  
**Result:** Migration preserved Finance security controls.  
**SME Probe:** Should migration users have permanent elevated access?  
**Reflection:** Migration privileges should be temporary, controlled and auditable.

## 15. Migration Testing
**Question:** What testing is required for planning-data migration?

**Situation:** Finance wanted confidence that migrated budgets and forecasts behaved correctly in the new model.  
**Task:** Validate both data integrity and target behavior.  
**Action:** I tested record counts, financial totals, dimensions, versions, scenarios, calculations, reporting, security, reconciliation and representative historical comparisons.  
**Result:** Migration defects were identified before business acceptance.  
**SME Probe:** Is record-count matching enough?  
**Reflection:** Equal record counts do not prove equal financial meaning.

## 16. Migration Performance
**Question:** How would you manage migration performance for large Finance planning datasets?

**Situation:** Millions of planning records had to be migrated within a controlled cutover window.  
**Task:** Complete migration within the available business window.  
**Action:** I profiled volumes, optimized transformation and loading sequences, used appropriate batching or parallelization, monitored throughput and performed rehearsal-based timing validation.  
**Result:** Migration duration became predictable and compatible with cutover constraints.  
**SME Probe:** What should never be sacrificed for speed?  
**Reflection:** Financial integrity and reconciliation remain non-negotiable.

## 17. Post-Migration Validation
**Question:** What would you validate immediately after migration?

**Situation:** The final load completed successfully from a technical perspective.  
**Task:** Determine whether Finance could safely use the new planning data.  
**Action:** I validated control totals, key versions, master-data mappings, planning calculations, dashboards, security, workflow behavior and business-critical historical comparisons.  
**Result:** Technical completion was converted into Finance acceptance evidence.  
**SME Probe:** Why is technical success insufficient?  
**Reflection:** A successful load is not the same as a successful Finance migration.

## 18. Migration and Integration
**Question:** How would you validate migrated planning data against S/4HANA Finance?

**Situation:** Historical planning data had to be compared with current S/4HANA actuals.  
**Task:** Ensure dimensional and financial compatibility.  
**Action:** I reconciled accounts, organizations, periods and currencies, validated mappings and tested budget-versus-actual analytics using representative historical cases.  
**Result:** The migrated planning model supported connected Finance analysis.  
**SME Probe:** What if historical master data differs from current S/4HANA master data?  
**Reflection:** Historical context must be preserved rather than overwritten by today's structure.

## 19. Migration Automation and AI
**Question:** How could automation or AI improve planning-data migration?

**Situation:** Migration teams manually reviewed thousands of mapping exceptions.  
**Task:** Reduce effort while preserving Finance governance.  
**Action:** I used automation for profiling, validation, reconciliation and repeatable transformations, while AI-assisted analysis identified potential duplicate mappings and anomalies for Finance review.  
**Result:** Migration analysis became faster without transferring approval responsibility away from Finance.  
**SME Probe:** Should AI approve mappings automatically?  
**Reflection:** AI can accelerate candidate identification; governed Finance ownership should approve financial mappings.

## 20. Enterprise Planning Migration Architecture
**Question:** How would you architect a global planning-data migration?

**Situation:** A multinational organization was consolidating multiple planning platforms into a governed SAP Finance planning environment.  
**Task:** Establish a scalable migration architecture.  
**Action:** I designed source profiling, master-data mapping, transformation rules, version/scenario treatment, fiscal and currency conversion, security, trial loads, reconciliation, cutover, rollback and Finance sign-off.  
**Result:** The organization gained a repeatable migration factory for country and business-unit onboarding.  
**SME Probe:** What makes a migration factory scalable?  
**Reflection:** Standardized controls with controlled local mapping make migration repeatable without ignoring Finance differences.

---

# Rapid-Fire SAP Finance Migration Questions

1. What belongs in a planning-data migration strategy?
2. How do you define migration scope?
3. What do you profile first?
4. How do you map legacy master data?
5. How do you migrate planning versions?
6. How should scenarios be migrated?
7. What is financial data cleansing?
8. How do you map historical fiscal periods?
9. How should currencies be handled?
10. How do you reconcile source and target?
11. Why perform trial loads?
12. How should rejected records be handled?
13. What belongs in cutover planning?
14. How do you secure migration?
15. How do you test migrated planning data?
16. How do you manage migration performance?
17. What is post-migration validation?
18. How do you validate against S/4HANA Finance?
19. How can automation and AI assist migration?
20. What makes an enterprise planning migration scalable?

---

# BAISI PAHACHA™ 22-Step Mastery Framework — AFI0 #11

## KNOW — 1–4
1. **Domain Foundation** — Planning-data migration, historical budgets, forecasts, scenarios and master data.
2. **Product/Technology Knowledge** — SAP Analytics Cloud Planning and SAP S/4HANA Finance.
3. **Process & Business Context** — Planning cycles, historical analysis, forecast continuity and cutover.
4. **Data & Information Model** — Accounts, organizations, periods, currencies, versions, scenarios and measures.

## DESIGN — 5–8
5. **Requirement Analysis** — Determine retained history and target planning requirements.
6. **Solution Design** — Design mapping, cleansing, transformation and reconciliation architecture.
7. **Configuration/Development** — Implement controlled migration transformations and validations.
8. **Integration & Architecture** — Align migrated planning data with S/4HANA Finance.

## DELIVER — 9–12
9. **Testing & Quality Assurance** — Validate financial totals, mappings, versions and target behavior.
10. **Deployment & Release** — Govern migration releases and cutover readiness.
11. **Migration & Cutover** — Execute freeze, extract, transform, load, reconcile and sign-off.
12. **Operations & Support** — Resolve post-migration exceptions and stabilize planning.

## SOLVE — 13–16
13. **Troubleshooting & Root Cause Analysis** — Diagnose mapping, transformation and load defects.
14. **Scenario-Based Problem Solving** — Resolve historical data and migration exceptions.
15. **Risk, Controls & Security** — Protect financial data and migration integrity.
16. **Performance & Optimization** — Improve migration throughput without weakening controls.

## INFLUENCE — 17–19
17. **Stakeholder Management** — Align Finance, FP&A, data, ERP and migration teams.
18. **Communication & Consulting** — Explain migration decisions, exceptions and reconciliation evidence.
19. **Presales / Leadership / Decision Making** — Lead migration architecture and cutover decisions.

## TRANSFORM — 20–22
20. **Transformation & Roadmap** — Establish repeatable Finance planning migration capability.
21. **Innovation & Emerging Technology** — Apply automation and AI-assisted migration analysis.
22. **Enterprise Architecture & Business Value** — Preserve trusted Finance history while modernizing planning.

---

# Planning Migration Anti-Patterns

- Migrating everything without business-value assessment.
- Skipping source-data profiling.
- Treating unmapped members as technical rather than Finance decisions.
- Changing financial meaning silently during cleansing.
- Overwriting historical master-data context with today's hierarchy.
- Ignoring version and scenario semantics.
- Recalculating historical currency values without business approval.
- Treating record counts as proof of migration accuracy.
- Performing only one migration rehearsal.
- Force-loading rejected Finance records.
- Giving migration users permanent elevated access.
- Optimizing migration speed at the expense of reconciliation.
- Declaring success because the technical load completed.
- Allowing AI to approve financial mappings autonomously.

---

# Interview Evidence Bank

Prepare STAR evidence for:

- Planning-data migration strategy.
- Migration scope definition.
- Source-data profiling.
- SAP Finance master-data mapping.
- Version migration.
- Scenario migration.
- Financial data cleansing.
- Historical fiscal-period migration.
- Currency handling.
- Migration reconciliation.
- Trial-load execution.
- Rejected-record resolution.
- Cutover planning.
- Migration security.
- Migration testing.
- Migration performance.
- Post-migration validation.
- S/4HANA reconciliation.
- Migration automation and AI.
- Enterprise migration architecture.

For every evidence item capture:

**Source → Scope → Profile → Map → Cleanse → Transform → Load → Reconcile → Finance Sign-Off → Business Value.**

---

# Success Criteria

You are interview-ready when you can:

- Design a Finance planning-data migration strategy.
- Define migration scope based on business value.
- Profile legacy planning data.
- Map legacy dimensions to SAP Finance.
- Preserve version and scenario semantics.
- Cleanse data without changing meaning silently.
- Handle fiscal periods and currencies.
- Reconcile source and target financial values.
- Execute migration rehearsals.
- Handle rejected records correctly.
- Design controlled cutover.
- Protect Finance data during migration.
- Build migration test coverage.
- Manage large migration volumes.
- Perform post-migration validation.
- Reconcile migrated planning data with S/4HANA.
- Automate repeatable migration controls.
- Use AI responsibly for exception analysis.
- Architect a scalable Finance migration factory.
- Answer all 20 scenarios using concise SAP Finance STAR evidence.

---

# Final BAISI PAHACHA™ Reflection

**Before:** I viewed migration as moving historical planning records into a new system.

**After:** I understand migration as the **controlled transfer of financial meaning, context and decision history from one planning architecture to another**.

The maturity shift is:

**Source → Profile → Map → Transform → Load → Reconcile → Certify**

The deeper interview answer is:

> **“I treat Finance planning migration as a business-controlled transformation, not a file-loading exercise. I preserve the meaning of accounts, organizations, periods, currencies, versions and scenarios, reconcile financial totals, validate the target behavior and obtain Finance sign-off before declaring the migration successful.”**

## Final Mantra

> **Know the source. Map the meaning. Cleanse deliberately. Transform transparently. Reconcile completely. Certify financially.**

---

# AFI0 Progress

**AFI0 Finance Analytics & Intelligence — 11/22 modules complete**

Completed: **#01 Requirement & Solution Design → #02 Process & Business Architecture → #03 Financial Planning, Budgeting & Performance Analytics → #04 Financial Forecasting & Rolling Forecast Analytics → #05 Financial Planning Drivers & Assumptions → #06 Planning Versions, Scenarios & Simulation → #07 Financial Planning Data Model & Master Data → #08 Planning Workflow, Approvals & Governance → #09 Financial Planning Integration with SAP S/4HANA Finance → #10 Planning Testing & Quality Assurance → #11 Planning Data Migration**

**Next:** #12 Planning Security & Controls

**Transformation path:**  
Finance Reporting Practitioner → SAP Finance Analytics SME → Finance Analytics Architect → Finance Intelligence Leader → Trusted Finance Data & Decision Advisor
