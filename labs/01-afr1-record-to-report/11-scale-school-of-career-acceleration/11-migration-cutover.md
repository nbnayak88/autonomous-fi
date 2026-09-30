# 11 — Migration & Cutover

## Course
**Applied SAP S/4HANA Finance — AFR1 Record to Report**

- **Stream:** 01 — Enterprise Architect
- **Lab:** 11 — Scale | School of Career Acceleration
- **Theme:** DELIVER
- **Pahacha:** @baisi pahacha — Step 11: Migration & Cutover
- **Mastery objective:** Move financial processes, data, controls, and business operations from legacy to S/4HANA with measurable integrity and controlled business continuity.

## Purpose

Finance migration is not simply moving data from one database to another.

A Finance migration changes the enterprise's financial system of record. It affects balances, open items, master data, historical information, accounting dimensions, integrations, controls, reporting, reconciliation, users, and the close calendar.

A strong Finance architect can explain:

**Legacy state → migration strategy → data scope → transformation → reconciliation → cutover → validation → business acceptance → stabilization.**

The goal is not to memorize migration tools.

The goal is to prove that **financial meaning survives the transition.**

---

# 20 Scenario-Based Interview Questions

## 1. Choosing the migration approach

**Question:** How would you choose a Finance migration approach for ECC to S/4HANA?

**S — Situation:** An enterprise needed to move from a legacy SAP Finance landscape to S/4HANA.

**T — Task:** I had to determine the migration approach while considering business continuity, data history, transformation objectives, and technical constraints.

**A — Action:** I assessed system condition, business-process redesign requirements, historical-data needs, custom-code footprint, integrations, organizational changes, regulatory requirements, timeline, and risk. I compared system conversion, new implementation, and selective-transition considerations rather than choosing based only on technical preference.

**R — Result:** The migration approach was tied to business and architecture outcomes.

**SME Probe:** What factors would make a transformation-oriented approach preferable to simple technical conversion?

**Reflection:** Migration strategy is a business transformation decision.

---

## 2. Defining Finance migration scope

**Question:** What data would you migrate for R2R?

**S:** Stakeholders initially requested that all historical Finance data be moved.

**T:** I needed to define a defensible scope.

**A:** I classified data into master data, open items, balances, transactional history, reference data, audit evidence, reporting history, and information that could remain in an accessible legacy archive. I considered legal retention, business reporting, reconciliation, audit, performance, and cost.

**R:** Migration scope became purposeful instead of “move everything.”

**SME Probe:** Why is historical data not automatically the same as active transactional data?

**Reflection:** Migration should preserve required business capability and evidence, not unnecessary technical volume.

---

## 3. Financial reconciliation

**Question:** How would you prove that migrated Finance data is correct?

**S:** Legacy balances and open items were migrated into S/4HANA.

**T:** I needed to demonstrate financial integrity.

**A:** I established control totals, account-level reconciliation, company-code reconciliation, subledger-to-GL checks, open-item reconciliation, currency checks, document counts, and exception investigation. I compared legacy and target results at defined control points.

**R:** Migration acceptance was based on measurable reconciliation.

**SME Probe:** What would you do if total balance matches but individual accounts do not?

**Reflection:** Aggregate equality can hide structural errors.

---

## 4. Master-data migration

**Question:** How would you migrate Finance master data?

**S:** Customer, supplier, G/L, cost-center, profit-center, and organizational data existed across legacy systems.

**T:** I needed to migrate usable and governed master data.

**A:** I defined ownership, cleansing, duplicate handling, mapping, hierarchy transformation, mandatory attributes, effective dates, validation, and approval. I distinguished active records from obsolete or historical records.

**R:** Target master data supported both accounting and future-state processes.

**SME Probe:** Who should own master-data quality?

**Reflection:** Migration exposes data-governance weaknesses that already existed.

---

## 5. Legacy chart of accounts

**Question:** The legacy chart of accounts is overly complex. Would you migrate it unchanged?

**S:** Finance had accumulated duplicate and obsolete accounts.

**T:** I needed to support reporting continuity without carrying unnecessary complexity into S/4HANA.

**A:** I classified accounts as retain, consolidate, map, replace, or retire. I validated statutory and management-reporting requirements and created a controlled mapping for historical comparability.

**R:** The target account model was simpler while preserving required financial meaning.

**SME Probe:** What risks arise from aggressive chart-of-accounts simplification?

**Reflection:** Simplification must preserve reporting and accounting semantics.

---

## 6. Open-item migration

**Question:** How would you handle open receivables and payables?

**S:** Thousands of customer and supplier open items existed at cutover.

**T:** I needed to migrate them without breaking collection, payment, clearing, or reporting processes.

**A:** I defined open-item selection criteria, document attributes, due dates, currencies, references, clearing status, business partner mapping, and reconciliation controls. I tested downstream collections, payments, and clearing.

**R:** Open items remained operationally usable after migration.

**SME Probe:** Why is open-item migration different from migrating historical closed transactions?

**Reflection:** Open items are active business obligations.

---

## 7. Asset accounting migration

**Question:** What would you consider when migrating asset accounting?

**S:** Asset master data and depreciation information had to move to the target system.

**T:** I needed to preserve asset values and future depreciation behavior.

**A:** I mapped asset classes, master data, acquisition values, accumulated depreciation, useful lives, depreciation areas, currencies, and historical information. I reconciled asset subledger totals to the GL.

**R:** Asset accounting remained financially consistent after migration.

**SME Probe:** What is the risk of reconciling only asset counts?

**Reflection:** Financial value matters more than record volume alone.

---

## 8. Migration transformation rules

**Question:** How should Finance migration transformation rules be governed?

**S:** Legacy and target models represented organizational and accounting information differently.

**T:** I needed consistent transformation.

**A:** I documented source field, target field, transformation logic, business rule, owner, exception handling, and effective date. I required business validation for rules affecting financial meaning.

**R:** Transformation became traceable and testable.

**SME Probe:** Which transformations require Finance business ownership?

**Reflection:** A transformation rule that changes accounting meaning is a business decision.

---

## 9. Migration mock cycles

**Question:** Why perform multiple migration mock cycles?

**S:** The first migration rehearsal produced reconciliation differences.

**T:** I needed to improve both the migration process and the quality of the source data.

**A:** I used mock cycles to validate extraction, transformation, loading, reconciliation, timing, defect resolution, and cutover procedures. I tracked recurring errors and improved the process after each cycle.

**R:** Migration confidence increased through repeated evidence rather than a single rehearsal.

**SME Probe:** What should improve between mock cycles?

**Reflection:** A mock migration is an experiment, not a dress rehearsal to repeat unchanged.

---

## 10. Data cleansing

**Question:** Who should decide what legacy Finance data gets cleansed?

**S:** The migration team found duplicate and obsolete records.

**T:** I needed to prevent technical teams from making business decisions about data meaning.

**A:** I established business data owners, cleansing rules, approval criteria, exception handling, and measurable quality thresholds. Technical teams executed approved rules but did not invent business semantics.

**R:** Data cleansing became accountable and auditable.

**SME Probe:** What happens when business ownership is missing?

**Reflection:** Data quality cannot be outsourced to the migration tool.

---

## 11. Migration and integrations

**Question:** How do you manage integrations during Finance cutover?

**S:** Multiple upstream and downstream systems continued operating while Finance was being migrated.

**T:** I needed to prevent transaction loss or duplication.

**A:** I mapped interface freeze points, queues, transaction timing, reconciliation, replay/reprocessing procedures, source-system behavior, and target activation. I defined ownership for every critical integration.

**R:** Cutover protected the continuity of financial business events.

**SME Probe:** How would you handle transactions arriving during the migration window?

**Reflection:** Cutover must account for business events that do not stop simply because technology is changing.

---

## 12. Cutover command center

**Question:** How would you run Finance cutover?

**S:** A global Finance go-live required coordinated activities across multiple teams.

**T:** I needed a single operating model for decisions and escalation.

**A:** I established a command center with workstream leads, clear roles, time-based checkpoints, entry/exit criteria, issue severity, escalation paths, communication protocols, and decision authority.

**R:** The organization could make coordinated decisions under time pressure.

**SME Probe:** What information should be visible to the cutover command center?

**Reflection:** Cutover needs a shared operational picture.

---

## 13. Cutover timing and financial calendar

**Question:** How does the financial calendar affect migration cutover?

**S:** The migration was initially planned near a financial reporting boundary.

**T:** I needed to minimize accounting and reporting risk.

**A:** I mapped fiscal periods, close activities, reporting deadlines, statutory requirements, payroll, billing, procurement, treasury, and bank schedules. I selected cutover timing based on business dependency and risk.

**R:** Cutover timing aligned with enterprise financial operations.

**SME Probe:** Is year-end always the best migration point?

**Reflection:** Calendar boundaries can simplify some activities while increasing risk elsewhere.

---

## 14. Historical reporting

**Question:** How would you preserve historical Finance reporting after migration?

**S:** Leadership required multi-year comparisons after moving to S/4HANA.

**T:** I needed to preserve analytical continuity without necessarily migrating every historical transaction.

**A:** I evaluated historical migration scope, data-warehouse/analytics retention, legacy archive access, semantic mapping, chart-of-accounts changes, fiscal dimensions, and reporting reconciliation.

**R:** Historical reporting remained usable and explainable.

**SME Probe:** What if the target chart of accounts differs from the legacy model?

**Reflection:** Historical continuity requires semantic mapping, not just data storage.

---

## 15. Migration controls

**Question:** What controls should exist during Finance migration?

**S:** Migration involved elevated access, bulk data movement, and high-impact financial changes.

**T:** I needed to prevent unauthorized or incomplete migration.

**A:** I established role segregation, migration approvals, source/target control totals, reconciliation, logging, access monitoring, data validation, exception approval, and sign-off.

**R:** Migration became a controlled financial process.

**SME Probe:** Which migration activities require independent verification?

**Reflection:** The higher the financial impact, the stronger the independent evidence should be.

---

## 16. Cutover rollback

**Question:** What does rollback mean during Finance migration?

**S:** A critical reconciliation issue appeared after cutover.

**T:** I needed to determine whether to revert or recover.

**A:** I assessed whether financial transactions had already been processed, data integrity, source-system state, interface state, recovery points, and business impact. I considered controlled recovery or correction rather than assuming a technical rollback was safe.

**R:** The response protected financial integrity.

**SME Probe:** Why is rollback especially complex after financial activity begins?

**Reflection:** A migrated system becomes part of the accounting chain as soon as business events occur.

---

## 17. Migration performance

**Question:** How do you ensure migration completes within the cutover window?

**S:** Data volume and transformation complexity threatened the available downtime window.

**T:** I needed to prove migration feasibility.

**A:** I measured extraction, transformation, loading, reconciliation, and validation times across mock cycles. I optimized data scope, parallelism, sequencing, transformation logic, and operational handoffs where appropriate.

**R:** Cutover duration became measurable and predictable.

**SME Probe:** Why should migration performance be tested early?

**Reflection:** A migration that cannot finish in the business window is not a viable architecture.

---

## 18. Migration defects

**Question:** How would you triage migration defects?

**S:** Mock migration generated differences in master data and financial balances.

**T:** I needed to prioritize defects by business risk.

**A:** I classified issues by financial impact, data integrity, regulatory significance, process criticality, volume, recurrence, and workaround. I separated source-data defects from transformation and target-system defects.

**R:** Teams focused on systemic causes instead of treating every mismatch as an isolated issue.

**SME Probe:** Why is defect classification important during migration?

**Reflection:** Migration defects often reveal architecture or data-governance problems.

---

## 19. Business acceptance of migration

**Question:** Who signs off on Finance migration?

**S:** Technical teams completed migration and reconciliation reports.

**T:** I needed accountable business acceptance.

**A:** I defined sign-off responsibilities across Finance process owners, data owners, controls, business units, integration owners, and technology. Acceptance criteria were agreed before final cutover.

**R:** Sign-off represented business accountability rather than technical completion.

**SME Probe:** What should business owners actually verify?

**Reflection:** The people accountable for financial outcomes must own acceptance.

---

## 20. Architect the future migration model

**Question:** What would a mature Finance migration capability look like?

**S:** The enterprise expected future acquisitions, country rollouts, ERP modernization, and continuous transformation.

**T:** I needed a reusable migration architecture.

**A:** I designed standardized data models, cleansing rules, mapping templates, reconciliation frameworks, mock-cycle patterns, migration automation, cutover playbooks, controls, monitoring, and reusable governance. I connected migration architecture to enterprise data and integration architecture.

**R:** Migration became a repeatable enterprise capability rather than a one-time project.

**SME Probe:** What would you measure to assess migration maturity?

**Reflection:** Mature migration reduces uncertainty through repeatable evidence.

---

# Rapid-Fire Questions

1. System conversion versus new implementation?
2. What is Finance migration scope?
3. How do you validate migrated balances?
4. Why are open items special?
5. What is master-data cleansing?
6. Who owns migration transformation rules?
7. Why perform mock migrations?
8. What is a cutover command center?
9. How does the financial calendar affect cutover?
10. How do you preserve historical reporting?
11. What migration controls are essential?
12. Why can rollback be dangerous?
13. How do you measure migration performance?
14. How do you classify migration defects?
15. Who owns business sign-off?
16. How do integrations behave during cutover?
17. What is a control total?
18. How do you reconcile subledger and GL after migration?
19. What makes migration business-ready?
20. How do you make migration repeatable?

---

# Mastery Framework — MOVE

Use this 7-part model for every migration question:

### 1. MAP
Understand legacy and target business, process, data, integration, and control landscapes.

### 2. MINIMIZE
Define what truly needs to move and what can be archived, retired, or redesigned.

### 3. MODEL
Define target data semantics, mappings, transformations, ownership, and quality rules.

### 4. MIGRATE
Execute controlled extraction, transformation, loading, reconciliation, and validation.

### 5. MEASURE
Prove completeness, accuracy, performance, controls, and business readiness.

### 6. MOVE
Execute cutover using controlled sequencing, command-center governance, and contingency paths.

### 7. MASTER
Capture lessons, stabilize operations, and turn migration assets into reusable enterprise capability.

**Memory line:**

> **Map → Minimize → Model → Migrate → Measure → Move → Master**

---

# Common Anti-Patterns

- Moving all legacy data without business justification.
- Treating migration as a technical ETL exercise.
- Allowing technical teams to decide business data meaning.
- Migrating obsolete configuration and master data.
- Reconciling only aggregate balances.
- Ignoring open-item behavior.
- Performing only one mock migration.
- Ignoring interfaces during cutover.
- Choosing cutover timing without the Finance calendar.
- Assuming rollback is always possible.
- Measuring migration only by record counts.
- Leaving historical reporting undefined.
- Allowing uncontrolled privileged migration access.
- Accepting technical completion as business sign-off.
- Treating recurring migration defects as isolated incidents.

---

# Interview Evidence Bank

Prepare concrete STAR examples for:

1. Selecting a Finance migration approach.
2. Defining migration scope.
3. Financial reconciliation.
4. Master-data migration.
5. Chart-of-accounts transformation.
6. Open-item migration.
7. Asset accounting migration.
8. Transformation-rule governance.
9. Mock migration cycles.
10. Data-cleansing governance.
11. Integration cutover.
12. Cutover command center.
13. Financial-calendar planning.
14. Historical reporting continuity.
15. Migration controls.
16. Rollback/recovery.
17. Migration performance.
18. Migration-defect triage.
19. Business sign-off.
20. Designing a reusable migration capability.

For every story, explain:

**Legacy problem → migration decision → transformation → reconciliation → cutover → business outcome → lesson.**

---

# Success Criteria

You have mastered this step when you can:

- Explain Finance migration as a business transformation.
- Evaluate migration approaches.
- Define migration scope.
- Design financial reconciliation.
- Govern master-data migration.
- Transform legacy accounting structures responsibly.
- Handle open items and asset accounting.
- Govern migration transformation rules.
- Design mock migration cycles.
- Coordinate integrations during cutover.
- Run a cutover command center.
- Align migration with the financial calendar.
- Preserve historical reporting continuity.
- Design migration controls.
- Evaluate rollback and recovery.
- Validate migration performance.
- Triage migration defects by business risk.
- Establish accountable business sign-off.
- Build a reusable migration architecture.

---

# Final Interview Mantra

> **“I do not define Finance migration as moving records from one system to another. I preserve financial meaning, data integrity, controls, business continuity, reconciliation, and reporting continuity while using migration as an opportunity to simplify and modernize the enterprise.”**

## Architecture Lens

Every migration decision should be tested across:

**Business → Process → Application → Data → Integration → Security → Technology → Control → Experience → Operations → AI → Industry.**

The architect's responsibility is not simply to move data.

**It is to move the enterprise from one trusted financial operating state to another without losing the meaning, control, or continuity of the business.**
