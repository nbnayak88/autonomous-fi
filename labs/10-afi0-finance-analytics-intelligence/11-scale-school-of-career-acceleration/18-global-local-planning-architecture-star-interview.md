# AFI0 #18 — Global / Local Planning Architecture — STAR Interview Mastery

**Lab:** Finance Analytics & Intelligence (AFI0)  
**Track:** Scale — School of Career Acceleration  
**Domain:** SAP Finance / SAP S/4HANA Finance / SAP Analytics Cloud Planning  
**Mastery:** **GLOBAL-INSIGHT-FI = Standardize → Localize → Govern → Integrate → Compare → Control → Scale → Evolve**

## Interview Objective

Demonstrate how to architect a global financial planning capability that provides enterprise standards while accommodating legitimate local requirements across countries, currencies, fiscal calendars, statutory needs, organizational structures and business practices.

> **STAR discipline:** Every scenario uses **Situation → Task → Action → Result**, followed by **SME Probe → Reflection**.

---

# 20 Scenario-Based Questions + STAR Answers

## 01. Global Planning Architecture
**Question:** How would you design a global financial planning architecture?

**Situation:** A multinational enterprise operated separate planning models by region with inconsistent definitions and reporting structures.  
**Task:** Create an enterprise planning architecture without eliminating legitimate local requirements.  
**Action:** I defined global financial dimensions, planning principles, KPI definitions, version governance, security boundaries and integration standards, while identifying controlled localization points.  
**Result:** Corporate Finance gained comparable planning information while regions retained necessary local flexibility.  
**SME Probe:** What should be globally standardized?  
**Reflection:** Financial semantics, core dimensions and governance should be standardized; local execution can vary where justified.

## 02. Global Chart of Accounts Alignment
**Question:** How would you handle different local account structures in a global planning model?

**Situation:** Countries used different local accounts for similar economic activities.  
**Task:** Enable enterprise comparison without losing local detail.  
**Action:** I mapped local accounts to a governed corporate financial structure, retained required local attributes and documented mapping ownership and change governance.  
**Result:** Corporate reporting became comparable while local accounting detail remained available.  
**SME Probe:** Should local accounts always be eliminated?  
**Reflection:** Local accounting structures can coexist with enterprise reporting mappings where statutory or operational requirements demand them.

## 03. Multi-Currency Planning
**Question:** How would you design multi-currency planning?

**Situation:** Regions planned in local currencies while corporate Finance required consolidated planning in a group currency.  
**Task:** Preserve local planning accuracy and enterprise comparability.  
**Action:** I defined transaction/local, planning and group-currency views, exchange-rate governance and translation rules, with clear ownership for rate assumptions.  
**Result:** Regional planners could work in local currency while corporate Finance obtained consistent consolidated views.  
**SME Probe:** Why govern planning exchange rates?  
**Reflection:** Exchange-rate assumptions materially affect consolidated plans and must be version-controlled.

## 04. Fiscal Calendar Differences
**Question:** How would you support different fiscal calendars?

**Situation:** Some entities followed the corporate fiscal calendar while others had different fiscal-year structures.  
**Task:** Support local planning without corrupting enterprise comparison.  
**Action:** I separated local planning periods from the enterprise reporting calendar and defined controlled mappings and aggregation rules.  
**Result:** Local entities could plan according to their required calendar while corporate Finance retained a consistent reporting framework.  
**SME Probe:** What is the risk of simple period renaming?  
**Reflection:** Fiscal-period mapping is a financial-semantic issue, not merely a display change.

## 05. Global Planning Dimensions
**Question:** How would you establish a common planning dimensional model?

**Situation:** Regions used different organizational and management dimensions.  
**Task:** Build an enterprise planning model.  
**Action:** I identified mandatory global dimensions such as account, entity, cost center, profit center, time, currency and version, then defined optional regional dimensions under controlled governance.  
**Result:** Enterprise analytics became comparable without forcing every region into identical detail.  
**SME Probe:** How do you avoid excessive dimensions?  
**Reflection:** Every dimension should have a clear planning or decision purpose.

## 06. Local Statutory Requirements
**Question:** How would local statutory requirements affect planning architecture?

**Situation:** A country required planning views aligned to local statutory reporting classifications.  
**Task:** Accommodate the requirement without creating an isolated planning model.  
**Action:** I created controlled local mappings and reporting structures while preserving the enterprise planning model as the common foundation.  
**Result:** The local requirement was satisfied without fragmenting the enterprise architecture.  
**SME Probe:** Where should localization live?  
**Reflection:** Prefer controlled mappings and extension points over duplicate enterprise planning models.

## 07. Global Security Model
**Question:** How would you design security for global planning?

**Situation:** Corporate Finance needed global visibility while regional planners required restricted write access.  
**Task:** Protect sensitive planning data and responsibilities.  
**Action:** I separated corporate read/analysis access from regional write permissions using organizational and planning dimensions, supported by role governance and periodic access review.  
**Result:** Users could perform their planning responsibilities without unnecessary cross-region edit access.  
**SME Probe:** Why distinguish read and write access?  
**Reflection:** Planning collaboration does not require unrestricted modification rights.

## 08. Global Planning Version Governance
**Question:** How would you govern budget and forecast versions globally?

**Situation:** Regions created their own versions using inconsistent naming and status conventions.  
**Task:** Establish enterprise version governance.  
**Action:** I defined standard version taxonomy, lifecycle states, ownership, lock rules and approval checkpoints while allowing controlled local scenarios.  
**Result:** Corporate Finance could distinguish approved enterprise versions from local working scenarios.  
**SME Probe:** Why standardize version status?  
**Reflection:** Version semantics are essential for reliable cross-region comparison.

## 09. Global / Local Driver Management
**Question:** How would you manage global and local planning drivers?

**Situation:** Corporate Finance wanted common assumptions for inflation and FX, while regions required local operational drivers.  
**Task:** Build a governed driver hierarchy.  
**Action:** I separated enterprise drivers from local drivers, defined ownership and precedence rules and ensured driver changes were traceable by planning version.  
**Result:** Enterprise assumptions remained consistent while local business drivers could be modeled appropriately.  
**SME Probe:** What happens when local and global assumptions conflict?  
**Reflection:** The architecture should define explicit precedence and exception governance rather than allowing silent overrides.

## 10. Global Planning Integration with S/4HANA
**Question:** How would you integrate global planning with SAP S/4HANA Finance?

**Situation:** Actuals came from multiple S/4HANA entities and local configurations.  
**Task:** Create a consistent actual-to-plan foundation.  
**Action:** I standardized integration mappings for company code, account, cost center, profit center, currency and fiscal period while validating local exceptions.  
**Result:** Planning received consistent actuals for enterprise analysis.  
**SME Probe:** What should be reconciled?  
**Reflection:** Actuals should reconcile to the relevant S/4HANA Finance source totals and dimensions.

## 11. Global Planning Data Quality
**Question:** How would you manage data-quality differences between countries?

**Situation:** One region had incomplete master-data mappings while others were clean.  
**Task:** Prevent local data issues from contaminating enterprise planning.  
**Action:** I introduced country-level validation, exception queues, mapping ownership and enterprise reconciliation before consolidation.  
**Result:** Poor-quality local data was isolated and corrected before affecting corporate analysis.  
**SME Probe:** Should consolidation hide local data problems?  
**Reflection:** Consolidation should expose data-quality exceptions, not mask them.

## 12. Local Planning Flexibility
**Question:** How much local flexibility should a global planning architecture allow?

**Situation:** Regions requested custom planning dimensions, workflows and reports.  
**Task:** Prevent uncontrolled customization while respecting business needs.  
**Action:** I classified requests into global standard, approved localization and exception categories, using architecture governance for deviations.  
**Result:** Local flexibility became deliberate rather than uncontrolled.  
**SME Probe:** What is the danger of excessive localization?  
**Reflection:** Excessive localization increases maintenance complexity and weakens enterprise comparability.

## 13. Global Planning Workflow
**Question:** How would you design global planning approvals?

**Situation:** Corporate and regional Finance teams required different review stages.  
**Task:** Establish consistent governance with local approval flexibility.  
**Action:** I defined enterprise approval gates and minimum control requirements, then allowed additional local review stages where business or regulatory needs justified them.  
**Result:** Every region met core governance standards while retaining appropriate local review.  
**SME Probe:** Should all countries have identical workflows?  
**Reflection:** Control objectives should be consistent even when workflow implementation differs.

## 14. Global Planning Performance
**Question:** How would you handle performance differences across regions?

**Situation:** A global planning model performed well for smaller regions but slowed significantly for high-volume entities.  
**Task:** Maintain acceptable performance without fragmenting the model unnecessarily.  
**Action:** I analyzed data volume, dimensionality, calculations, concurrency and query patterns, then optimized model design and processing while preserving common semantics.  
**Result:** Performance improved without creating uncontrolled regional copies.  
**SME Probe:** When might a separate model be justified?  
**Reflection:** Separation should be based on material architectural constraints, not convenience or local preference.

## 15. Global Planning Testing
**Question:** How would you test a global planning solution?

**Situation:** A global planning release included common functionality and country-specific extensions.  
**Task:** Validate both enterprise consistency and local correctness.  
**Action:** I created global regression scenarios plus country-specific tests for currencies, calendars, mappings, security, workflows and localized calculations.  
**Result:** The release could be validated without treating local variations as defects.  
**SME Probe:** What should every country inherit from global testing?  
**Reflection:** Core financial calculations, controls and integration behavior require common regression coverage.

## 16. Global Planning Migration
**Question:** How would you migrate multiple regional planning models into a global architecture?

**Situation:** Regions maintained legacy planning structures with inconsistent dimensions and historical versions.  
**Task:** Consolidate planning without losing important historical context.  
**Action:** I profiled regional structures, mapped common dimensions, classified obsolete versus required local attributes, cleansed data and reconciled migrated balances and versions.  
**Result:** The enterprise model gained a consistent foundation while preserving necessary planning history.  
**SME Probe:** Should every historical field be migrated?  
**Reflection:** Migration should preserve information needed for continuity, auditability and meaningful comparison rather than blindly copying legacy complexity.

## 17. Global Planning Support Model
**Question:** How would you structure support for a global planning platform?

**Situation:** Regional teams escalated every issue independently to the central Finance technology team.  
**Task:** Create a scalable support model.  
**Action:** I defined global platform ownership, regional super users, standard runbooks, incident categories, escalation paths and knowledge management.  
**Result:** Common issues could be resolved locally while enterprise defects received centralized governance.  
**SME Probe:** Why use regional super users?  
**Reflection:** Local capability improves responsiveness while global ownership protects architectural consistency.

## 18. Global Planning Analytics
**Question:** How would you provide comparable analytics across regions?

**Situation:** Executive dashboards used different KPI definitions by country.  
**Task:** Establish enterprise financial intelligence.  
**Action:** I standardized KPI definitions, calculation logic, dimensions and enterprise reporting semantics while providing localized drill-down where required.  
**Result:** Executives could compare regions using consistent financial measures.  
**SME Probe:** What is more important than dashboard design?  
**Reflection:** KPI semantic consistency is more important than visual consistency.

## 19. Global Planning Automation and AI
**Question:** How would you use automation and AI in a global planning architecture?

**Situation:** Finance manually consolidated planning submissions and investigated recurring exceptions across regions.  
**Task:** Reduce operational effort while preserving governance.  
**Action:** I automated validation, consolidation, exception alerts and status reporting, then used AI-assisted anomaly detection and narrative analysis with controlled human validation.  
**Result:** Finance gained faster enterprise insight without removing accountability from regional and corporate owners.  
**SME Probe:** Where should AI governance apply?  
**Reflection:** AI outputs affecting financial decisions require traceability, validation and appropriate access controls.

## 20. Global / Local Enterprise Architecture
**Question:** How would you explain your global/local planning architecture to a CFO?

**Situation:** A multinational CFO wanted one enterprise planning capability but local Finance leaders needed flexibility.  
**Task:** Establish an architecture balancing standardization and localization.  
**Action:** I proposed a common enterprise planning core covering financial semantics, dimensions, versions, controls, integration and KPI definitions, surrounded by governed local extensions for calendars, statutory needs, local drivers and workflows.  
**Result:** The architecture provided one enterprise planning language without requiring identical local execution.  
**SME Probe:** What is the central architecture principle?  
**Reflection:** **Standardize the financial language; localize only where there is a legitimate business, statutory or operational reason.**

---

# Rapid-Fire SAP Finance Questions

1. What is global/local planning architecture?
2. Which planning dimensions should be standardized?
3. How do you map local accounts to corporate accounts?
4. How do you handle multiple currencies?
5. How do fiscal-calendar differences affect planning?
6. How do you manage local statutory requirements?
7. How do you design global planning security?
8. How do you govern versions?
9. How do you govern global and local drivers?
10. How do you integrate multiple S/4HANA entities?
11. How do you manage country-specific data quality?
12. What is controlled localization?
13. How do you design global planning workflow?
14. How do you optimize global planning performance?
15. How do you test local extensions?
16. How do you migrate regional planning models?
17. How do you structure global support?
18. How do you standardize enterprise KPIs?
19. How can automation and AI support global planning?
20. What is the core global/local architecture principle?

---

# BAISI PAHACHA™ 22-Step Mastery Framework

## KNOW — 1–4
1. **Domain Foundation** — Global planning, local requirements, consolidation, versions, currencies and fiscal calendars.
2. **Product/Technology Knowledge** — SAP S/4HANA Finance and SAP Analytics Cloud Planning.
3. **Process & Business Context** — Enterprise planning with regional execution and governance.
4. **Data & Information Model** — Accounts, entities, cost centers, profit centers, periods, currencies, drivers, versions and scenarios.

## DESIGN — 5–8
5. **Requirement Analysis** — Separate enterprise requirements from legitimate local requirements.
6. **Solution Design** — Define the global planning core and localization boundaries.
7. **Configuration/Development** — Implement common models, workflows, mappings and approved extensions.
8. **Integration & Architecture** — Connect regional S/4HANA Finance data to an enterprise planning architecture.

## DELIVER — 9–12
9. **Testing & Quality Assurance** — Validate global standards and local variations.
10. **Deployment & Release** — Govern global releases and local extensions.
11. **Migration & Cutover** — Consolidate legacy regional planning structures.
12. **Operations & Support** — Establish global ownership with regional execution capability.

## SOLVE — 13–16
13. **Troubleshooting & Root Cause Analysis** — Diagnose country-specific data, mapping, workflow and performance issues.
14. **Scenario-Based Problem Solving** — Balance enterprise consistency with local requirements.
15. **Risk, Controls & Security** — Protect financial information and enforce planning governance.
16. **Performance & Optimization** — Scale planning without unnecessary model fragmentation.

## INFLUENCE — 17–19
17. **Stakeholder Management** — Align Corporate Finance, regional Finance, IT and business stakeholders.
18. **Communication & Consulting** — Explain standardization/localization trade-offs.
19. **Presales / Leadership / Decision Making** — Lead global planning architecture decisions.

## TRANSFORM — 20–22
20. **Transformation & Roadmap** — Move fragmented regional planning toward an integrated enterprise capability.
21. **Innovation & Emerging Technology** — Apply automation and AI within governed global/local architecture.
22. **Enterprise Architecture & Business Value** — Establish one financial planning language with controlled local flexibility.

---

# Anti-Patterns

- Creating separate planning models for every country by default.
- Forcing identical local processes where statutory or operational differences are legitimate.
- Allowing uncontrolled local dimensions.
- Using different KPI definitions across regions.
- Ignoring currency translation governance.
- Treating fiscal-calendar mapping as a cosmetic issue.
- Duplicating global functionality for local requirements.
- Allowing local overrides without ownership or auditability.
- Mixing corporate and local planning versions.
- Giving regional planners unrestricted cross-country access.
- Consolidating poor-quality data without exception management.
- Migrating every legacy field without assessing value.
- Allowing every country to customize the core model.
- Optimizing regional performance by creating unnecessary model copies.
- Using AI outputs for financial decisions without validation.

---

# Interview Evidence Bank

Prepare STAR evidence for:

- Global planning architecture.
- Corporate/local account mapping.
- Multi-currency planning.
- Fiscal-calendar mapping.
- Common planning dimensions.
- Local statutory requirements.
- Global planning security.
- Version governance.
- Global/local driver management.
- S/4HANA integration.
- Country-level data quality.
- Controlled localization.
- Global workflow.
- Planning performance.
- Global testing.
- Regional model migration.
- Global support operating model.
- Enterprise KPI standardization.
- Global automation and AI.
- CFO-level global/local architecture decision.

Evidence chain:

**Enterprise Standard → Local Requirement → Architecture Boundary → Mapping/Extension → Governance → Integration → Reconciliation → Comparison → Scale**

---

# Success Criteria

You are interview-ready when you can:

- Design global/local financial planning architecture.
- Define enterprise planning standards.
- Map local financial structures to corporate structures.
- Architect multi-currency planning.
- Handle different fiscal calendars.
- Accommodate statutory requirements.
- Design global planning security.
- Govern versions and scenarios.
- Manage global and local drivers.
- Integrate regional S/4HANA Finance actuals.
- Govern country-level data quality.
- Define controlled localization.
- Design enterprise and local workflows.
- Scale planning performance.
- Test global and local functionality.
- Migrate regional planning models.
- Establish global/regional support.
- Standardize enterprise financial KPIs.
- Apply automation and AI responsibly.
- Explain global/local architecture to executive Finance stakeholders.

---

# Final BAISI PAHACHA™ Reflection

**Before:** I saw global planning as a choice between one standardized model and many local models.

**After:** I understand it as an **architecture problem: create a common enterprise financial language while deliberately designing where localization is permitted and governed.**

The maturity shift:

**Standardize → Localize → Govern → Integrate → Compare → Control → Scale → Evolve**

The deeper interview answer:

> **“I architect global planning around a common enterprise financial core—dimensions, KPI definitions, versions, controls, security and integration—while creating governed extension points for legitimate local requirements such as currencies, fiscal calendars, statutory structures, local drivers and workflows. This gives Corporate Finance comparability without forcing every region into identical execution.”**

## Final Mantra

> **One financial language. Controlled local flexibility. Governed differences. Comparable decisions.**

---

# AFI0 Progress

**AFI0 Finance Analytics & Intelligence — 18/22 complete**

**Next → #19 Planning Knowledge Architecture**
