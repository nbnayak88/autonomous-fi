# AFP6 #11 — Planning Data Migration — STAR Interview Mastery

## Purpose

This module prepares SAP Finance professionals to plan, execute, reconcile and govern migration of financial planning data into SAP Analytics Cloud Planning and connected SAP Finance landscapes.

**Mastery mnemonic:** MIGRATE-FI = **Model → Inspect → Govern → Integrate → Reconcile → Assure → Transition → Evolve**

---

# 20 SAP Finance Scenario-Based Interview Questions + STAR Answers

## Question 01 — How would you design a migration strategy for historical planning data?

**Situation:** Finance was moving from a legacy planning platform to SAP Analytics Cloud Planning and needed several years of budget and forecast history.

**Task:** Define a controlled migration strategy.

**Action:** I classified data into historical actuals, approved budgets, forecast snapshots, scenarios, assumptions and master data. I defined the required retention period, target planning grain, mappings, reconciliation rules, migration waves and cutover criteria.

**Result:** Finance obtained a controlled path to the new planning platform without losing decision-relevant planning history.

**SME Probe:** Would you migrate every historical planning version?

**Reflection:** Migration should preserve information that has business, analytical, control or audit value—not every obsolete data object.

---

## Question 02 — How would you map a legacy chart of accounts to SAP Finance planning structures?

**Situation:** The legacy planning solution used a different account hierarchy from SAP S/4HANA Finance.

**Task:** Create a reliable account mapping.

**Action:** I established a source-to-target crosswalk, identified one-to-one, many-to-one and exception mappings, validated totals and obtained Finance SME approval for ambiguous accounts.

**Result:** Historical planning values could be interpreted consistently in the target structure.

**SME Probe:** What would you do with an unmapped legacy account?

**Reflection:** An unmapped financial value should become an explicit exception, never an invisible aggregation.

---

## Question 03 — How would you migrate historical budgets and forecasts?

**Situation:** Finance wanted historical budgets and forecast snapshots available for performance analysis.

**Task:** Preserve the meaning of historical planning states.

**Action:** I migrated values with their fiscal period, organizational dimensions, currency, version identity and scenario context. I preserved the distinction between approved budget and forecast snapshots.

**Result:** Finance could compare historical expectations with subsequent actual performance.

**SME Probe:** Why is version context important?

**Reflection:** A planning number without its version context can lose its business meaning.

---

## Question 04 — How would you handle historical master-data changes during migration?

**Situation:** Cost centers and profit-center hierarchies changed over several years.

**Task:** Migrate historical planning without incorrectly rewriting organizational history.

**Action:** I created effective-dated mappings and retained historical hierarchy context. Where management needed current-structure reporting, I created controlled analytical mappings rather than changing the source history.

**Result:** Historical planning remained explainable across organizational changes.

**SME Probe:** Why not simply map every historical record to today's hierarchy?

**Reflection:** Reconstructing history under today's organization can distort past management decisions.

---

## Question 05 — How would you migrate multi-currency planning data?

**Situation:** The legacy system contained local-currency plans and group-currency reporting.

**Task:** Preserve currency meaning during migration.

**Action:** I identified source currency, planning currency, reporting currency, exchange-rate assumptions and translation rules. I reconciled both local and translated values where required.

**Result:** Historical planning remained financially interpretable across currencies.

**SME Probe:** Would you recalculate every historical amount using today's exchange rate?

**Reflection:** Historical planning should preserve the financial context under which it was created unless a governed restatement is explicitly required.

---

## Question 06 — How would you migrate planning data at different granularities?

**Situation:** Legacy plans were monthly by cost center, while the target model required additional product and profitability dimensions.

**Task:** Transform the data without creating false precision.

**Action:** I assessed the available source grain, defined aggregation and allocation rules and clearly distinguished migrated source-level values from newly derived planning attributes.

**Result:** The target model received usable data without pretending that unavailable historical detail actually existed.

**SME Probe:** Can you safely allocate historical totals to a new dimension?

**Reflection:** Derived detail must be clearly identified as an allocation or estimate.

---

## Question 07 — How would you perform migration data profiling?

**Situation:** Legacy planning data contained duplicate records, missing dimensions and inconsistent account mappings.

**Task:** Determine migration readiness.

**Action:** I profiled completeness, uniqueness, validity, referential integrity, dimensional coverage, financial totals and version consistency. I categorized exceptions by materiality and remediation priority.

**Result:** Migration defects were identified before transformation and loading.

**SME Probe:** Which data-quality dimension would you investigate first?

**Reflection:** Start with defects capable of materially changing financial meaning.

---

## Question 08 — How would you design a migration reconciliation strategy?

**Situation:** Finance required evidence that migrated planning values matched the legacy source.

**Task:** Prove migration completeness and accuracy.

**Action:** I reconciled record counts and financial values by fiscal period, account, organization, currency, version and scenario. I established tolerances and documented all approved differences.

**Result:** Finance could demonstrate controlled migration accuracy.

**SME Probe:** Why is record-count matching insufficient?

**Reflection:** Equal record counts can still contain materially different financial values.

---

## Question 09 — How would you migrate planning data into SAP Analytics Cloud?

**Situation:** A legacy planning application was being replaced by SAP Analytics Cloud Planning.

**Task:** Load historical planning data into the target model.

**Action:** I mapped source dimensions to target dimensions, transformed values, validated planning grain, loaded controlled migration batches and reconciled each batch before proceeding.

**Result:** Migration progressed in controlled waves rather than one high-risk bulk load.

**SME Probe:** Why use migration waves?

**Reflection:** Smaller controlled waves reduce diagnostic scope and migration risk.

---

## Question 10 — How would you migrate scenario and simulation history?

**Situation:** Leadership wanted historical downside and investment scenarios retained for strategic analysis.

**Task:** Preserve scenario context.

**Action:** I classified scenarios by business relevance, migrated selected scenarios with assumptions and metadata, and archived low-value scenarios outside the active planning model where appropriate.

**Result:** Valuable decision history remained available without creating an uncontrolled scenario landscape.

**SME Probe:** What makes a historical scenario worth migrating?

**Reflection:** Decision relevance, audit value and analytical usefulness should determine retention.

---

## Question 11 — How would you migrate planning assumptions and drivers?

**Situation:** Historical forecasts depended on driver assumptions such as volume, price, headcount and inflation.

**Task:** Preserve the assumptions behind historical forecasts.

**Action:** I migrated material driver values with period, version, scenario and ownership context. I distinguished actual historical assumptions from current planning assumptions.

**Result:** Finance could understand why historical forecasts differed from actual outcomes.

**SME Probe:** Why migrate assumptions rather than only financial results?

**Reflection:** Assumptions explain the causal story behind planning outcomes.

---

## Question 12 — How would you manage migration security?

**Situation:** Historical planning data contained sensitive executive forecasts and business-unit financial information.

**Task:** Protect data during extraction, transformation and loading.

**Action:** I applied least-privilege access, controlled migration identities, restricted source extracts, secured transfer locations and validated target access after loading.

**Result:** Migration preserved financial confidentiality and access control.

**SME Probe:** Who should have access to migration extracts?

**Reflection:** Migration access should be limited to the people and technical identities required for the migration.

---

## Question 13 — How would you test migration before cutover?

**Situation:** A first migration rehearsal produced several mapping exceptions.

**Task:** Prove readiness before production cutover.

**Action:** I performed mock migrations, reconciliation, functional validation, workflow checks, security testing and performance testing. I converted defects into exit criteria and repeated the rehearsal.

**Result:** The final migration became predictable and evidence-based.

**SME Probe:** What is the purpose of a mock migration?

**Reflection:** Rehearsal converts theoretical migration design into measurable execution capability.

---

## Question 14 — How would you design migration cutover?

**Situation:** Finance needed to switch from the legacy planning system to SAP Analytics Cloud without disrupting an active forecast cycle.

**Task:** Execute a controlled cutover.

**Action:** I defined freeze windows, final source extraction, transformation, load sequence, reconciliation, business validation, sign-off, system switch and rollback criteria.

**Result:** The transition occurred with a controlled financial handover.

**SME Probe:** Why is a freeze window important?

**Reflection:** Source changes during extraction and reconciliation can create competing financial states.

---

## Question 15 — How would you handle migration differences discovered after cutover?

**Situation:** Finance identified a small difference between a migrated historical forecast and the legacy report.

**Task:** Determine whether it was an error or an approved transformation difference.

**Action:** I traced the difference through source, mapping, transformation and target values. I assessed materiality and documented the explanation or correction.

**Result:** The difference became an evidence-backed exception rather than an unresolved concern.

**SME Probe:** Should every difference be corrected?

**Reflection:** A difference should be corrected when it is erroneous or materially misleading; legitimate transformation differences should be documented.

---

## Question 16 — How would you migrate planning data after an organizational restructuring?

**Situation:** The target planning model used a new organizational hierarchy.

**Task:** Preserve both historical accountability and current planning responsibility.

**Action:** I maintained source historical structures, created legacy-to-target mappings and applied current structures to future planning. I provided controlled crosswalks for management reporting.

**Result:** Finance could analyze historical and current organizational performance without losing context.

**SME Probe:** How would you handle a dissolved cost center?

**Reflection:** Historical records should remain attributable to the structure that existed when the financial decision was made.

---

## Question 17 — How would you migrate planning data while preserving workflow and approval evidence?

**Situation:** Historical budgets had approval records in the legacy system.

**Task:** Preserve relevant governance evidence.

**Action:** I classified approval metadata by audit and business value, retained required approver, status and timestamp information, and linked migrated planning versions to the available historical evidence.

**Result:** Finance retained traceability around important historical planning decisions.

**SME Probe:** Should the new system recreate every historical workflow step?

**Reflection:** Preserve evidence and meaning; do not recreate obsolete process mechanics unnecessarily.

---

## Question 18 — How would you use automation or AI during planning migration?

**Situation:** The migration contained thousands of legacy-to-target mapping candidates.

**Task:** Accelerate mapping analysis without compromising Finance control.

**Action:** I used automated profiling and candidate-mapping techniques to identify likely matches, duplicates and anomalies. Finance SMEs validated material mappings before they became governed transformations.

**Result:** Migration analysis became faster while financial accountability remained with authorized SMEs.

**SME Probe:** Should AI automatically approve account mappings?

**Reflection:** AI can accelerate discovery; material Finance mappings require governed validation.

---

## Question 19 — How would you design rollback for a planning migration?

**Situation:** A production migration could potentially introduce incorrect historical planning values.

**Task:** Ensure the organization could recover safely.

**Action:** I preserved source backups, maintained migration batches and reconciliation evidence, defined rollback triggers and documented the procedure for restoring the previous planning state.

**Result:** Migration risk became bounded by a tested recovery strategy.

**SME Probe:** What would trigger rollback?

**Reflection:** Rollback criteria should be based on predefined financial, technical and control thresholds.

---

## Question 20 — How would you architect an enterprise planning-data migration?

**Situation:** The organization wanted to move from fragmented legacy planning systems to SAP Analytics Cloud Planning integrated with SAP S/4HANA Finance.

**Task:** Design the target migration architecture and roadmap.

**Action:** I established: source discovery → profiling → data classification → semantic mapping → transformation → mock migration → reconciliation → business validation → cutover → hypercare → legacy archival. I included master data, versions, scenarios, assumptions, security, audit evidence and rollback.

**Result:** Finance gained a repeatable migration framework rather than a one-time technical conversion.

**SME Probe:** What makes Finance planning migration successful?

**Reflection:** Success means preserving financial meaning, control evidence and decision usefulness—not merely loading records.

---

# Rapid-Fire SAP Finance Questions

1. What is planning-data migration?
2. What planning data should be migrated?
3. How do you map legacy accounts?
4. How do you preserve historical organizational structures?
5. How do you migrate multi-currency planning?
6. How do you handle different data granularities?
7. How do you profile legacy planning data?
8. How do you reconcile migration?
9. Why use migration waves?
10. How do you migrate scenarios?
11. How do you migrate planning drivers?
12. How do you secure migration?
13. Why perform mock migrations?
14. How do you design cutover?
15. How do you handle post-cutover differences?
16. How do restructurings affect migration?
17. How do you preserve approval evidence?
18. How can AI support migration?
19. How do you design rollback?
20. What makes planning migration successful?

---

# @BAISI PAHACHA™ 22-Step Mastery Framework

## KNOW

1. **Domain Foundation** — Understand planning data, budgets, forecasts, scenarios, drivers and migration.
2. **Product/Technology Knowledge** — Understand SAP Analytics Cloud Planning and SAP S/4HANA Finance data structures.
3. **Process & Business Context** — Understand planning cycles, historical analysis, close and management reporting.
4. **Data & Information Model** — Understand accounts, dimensions, hierarchies, versions, currencies and planning grain.

## DESIGN

5. **Requirement Analysis** — Define retention, scope, mappings, history and business outcomes.
6. **Solution Design** — Design profiling, transformation, reconciliation and cutover.
7. **Configuration/Development** — Build migration mappings, transformations and loading processes.
8. **Integration & Architecture** — Connect legacy planning, target planning and SAP Finance.

## DELIVER

9. **Testing & Quality Assurance** — Execute mock migration, reconciliation, security and performance testing.
10. **Deployment & Release** — Control production cutover and release.
11. **Migration & Cutover** — Execute the migration and validate financial integrity.
12. **Operations & Support** — Provide hypercare, exception management and legacy archival.

## SOLVE

13. **Troubleshooting & Root Cause Analysis** — Diagnose mapping, transformation and reconciliation differences.
14. **Scenario-Based Problem Solving** — Handle organizational changes, missing data and post-cutover exceptions.
15. **Risk, Controls & Security** — Protect financial data and preserve governance evidence.
16. **Performance & Optimization** — Optimize migration waves, load speed and reconciliation.

## INFLUENCE

17. **Stakeholder Management** — Align Finance, FP&A, IT, data owners and business SMEs.
18. **Communication & Consulting** — Explain migration decisions, differences and risks.
19. **Presales / Leadership / Decision Making** — Shape migration roadmap and cutover decisions.

## TRANSFORM

20. **Transformation & Roadmap** — Move from fragmented planning platforms to a governed enterprise planning foundation.
21. **Innovation & Emerging Technology** — Use automation and AI-assisted profiling and mapping responsibly.
22. **Enterprise Architecture & Business Value** — Connect migration to trusted financial history and future planning capability.

---

# Anti-Patterns

- Migrating everything without business classification.
- Treating record counts as proof of migration success.
- Ignoring historical version and scenario context.
- Rewriting historical organizations without preserving source context.
- Recalculating historical currencies without governance.
- Creating false granularity during migration.
- Loading without profiling source data.
- Skipping mock migrations.
- Migrating without reconciliation tolerances.
- Cutting over without a freeze window.
- Correcting every difference without investigating its cause.
- Exposing sensitive planning extracts broadly.
- Allowing AI to approve material Finance mappings.
- Migrating data without rollback criteria.
- Retaining obsolete scenarios indefinitely in the active model.

---

# Interview Evidence Bank

Prepare STAR stories for:

- Historical planning migration.
- Legacy-to-SAP account mapping.
- Budget and forecast migration.
- Historical hierarchy mapping.
- Multi-currency migration.
- Grain transformation.
- Data profiling.
- Migration reconciliation.
- SAP Analytics Cloud migration.
- Scenario migration.
- Driver and assumption migration.
- Migration security.
- Mock migration.
- Cutover planning.
- Post-cutover discrepancy management.
- Organizational restructuring migration.
- Approval-evidence preservation.
- AI-assisted migration.
- Rollback design.
- Enterprise planning migration architecture.

Quantify:

**Migration accuracy | reconciliation variance | mapping coverage | exception rate | migration duration | manual mapping effort | mock-migration defects | cutover downtime | rollback readiness | historical-data adoption**

---

# Success Criteria

You are interview-ready when you can:

1. Define the correct planning-data migration scope.
2. Map legacy Finance structures to SAP planning.
3. Preserve budget, forecast and scenario context.
4. Handle historical hierarchy and currency changes.
5. Profile and cleanse migration data.
6. Design financial reconciliation.
7. Execute migration waves and mock migrations.
8. Design controlled cutover and rollback.
9. Preserve security and governance evidence.
10. Handle post-cutover differences systematically.
11. Explain responsible AI-assisted migration.
12. Present an enterprise planning migration architecture using BAISI PAHACHA™.

---

# Final BAISI PAHACHA™ Reflection

**KNOW:** I understand what financial planning history means.

**DESIGN:** I can map legacy planning structures into a governed target model.

**DELIVER:** I can execute migration with reconciliation and controlled cutover.

**SOLVE:** I can diagnose migration differences without jumping to conclusions.

**INFLUENCE:** I can explain migration trade-offs to Finance leadership.

**TRANSFORM:** I can preserve the organization's financial memory while creating a stronger planning foundation for the future.

## Final Mantra

> **“I do not merely migrate planning data. I preserve the financial memory of the enterprise while architecting its next planning capability.”**

---

## Progress

**AFP6 — Financial Planning & Performance: 11/22 modules complete**

**Completed:** #01 Financial Planning & Performance Finance Requirement & Solution Design; #02 Financial Planning Process & Business Architecture; #03 Financial Planning & Budgeting; #04 Financial Forecasting & Rolling Forecasts; #05 Financial Planning Drivers & Assumptions; #06 Planning Versions, Scenarios & Simulation; #07 Financial Planning Data Model & Master Data; #08 Planning Workflow, Approvals & Governance; #09 Financial Planning Integration with SAP S/4HANA Finance; #10 Planning Testing & Quality Assurance; #11 Planning Data Migration

**Next:** **AFP6 #12 — Planning Security & Controls**
