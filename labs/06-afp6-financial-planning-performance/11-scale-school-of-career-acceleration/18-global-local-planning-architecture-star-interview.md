# AFP6 #18 — Global/Local Planning Architecture — STAR Interview Mastery

## Purpose

This module prepares SAP Finance professionals to architect global planning models that balance enterprise standardization with legitimate local financial, regulatory, operational and market requirements using SAP S/4HANA Finance and SAP Analytics Cloud Planning.

**Mastery mnemonic:** GLOBAL-FI = **Govern → Organize → Balance → Align → Localize**

---

# 20 SAP Finance Scenario-Based Interview Questions + STAR Answers

## Question 01 — How would you design a global planning architecture?

**Situation:** A multinational organization operated separate planning models across regions with inconsistent definitions and reporting structures.

**Task:** Create an enterprise planning architecture without eliminating legitimate local requirements.

**Action:** I established a global planning model for common financial definitions, dimensions, versions, workflows and governance, while allowing governed local extensions for currency, regulatory requirements, local drivers and operating practices.

**Result:** Corporate Finance gained comparable planning information while regions retained necessary local flexibility.

**SME Probe:** What should be standardized globally?

**Reflection:** Standardize financial meaning and core governance; localize only where a genuine business or regulatory requirement exists.

---

## Question 02 — How would you decide what belongs in the global template?

**Situation:** Regions requested different planning calculations and dimensions.

**Task:** Determine which capabilities should become global standards.

**Action:** I evaluated each requirement for enterprise relevance, financial-control impact, reuse, regulatory necessity and maintenance cost. Common requirements became global capabilities; valid exceptions became governed extensions.

**Result:** The global template remained manageable without ignoring legitimate regional needs.

**SME Probe:** Should every regional request become part of the global template?

**Reflection:** A global template should represent reusable enterprise capability, not a collection of every local exception.

---

## Question 03 — How would you handle local statutory planning requirements?

**Situation:** A country required additional planning information because of local tax and regulatory reporting.

**Task:** Support the requirement without fragmenting the enterprise model.

**Action:** I retained the global financial model and introduced controlled local dimensions or planning attributes only where required, with clear ownership and mapping to enterprise reporting.

**Result:** Local compliance needs were supported without creating a completely separate planning architecture.

**SME Probe:** When would a separate local model be justified?

**Reflection:** Separation should be considered when regulatory, data-residency, operational or process constraints make shared modeling impractical.

---

## Question 04 — How would you manage multiple currencies in global planning?

**Situation:** Regional Finance teams planned in local currencies while corporate Finance required group-currency consolidation.

**Task:** Create a consistent multi-currency planning approach.

**Action:** I defined local planning currency, group reporting currency, translation methodology, exchange-rate assumptions and version governance.

**Result:** Local planning remained meaningful while corporate consolidation remained comparable.

**SME Probe:** Should every region plan directly in group currency?

**Reflection:** Local operational planning often requires local currency; enterprise reporting can use governed translation.

---

## Question 05 — How would you design global versus local planning calendars?

**Situation:** Regions had different fiscal calendars and local close timelines.

**Task:** Coordinate enterprise planning without forcing identical operating schedules.

**Action:** I defined global milestones and dependencies while allowing governed regional submission windows aligned to local close requirements.

**Result:** Corporate planning remained synchronized while local teams operated within realistic timelines.

**SME Probe:** What should never be allowed to drift?

**Reflection:** Enterprise reporting deadlines, control gates and final consolidation milestones should remain governed.

---

## Question 06 — How would you manage local chart-of-account differences?

**Situation:** Countries used local accounts that did not directly match the corporate chart of accounts.

**Task:** Enable local planning while maintaining enterprise comparability.

**Action:** I created governed local-to-global account mappings, identified one-to-one and many-to-one relationships and established exception ownership.

**Result:** Local planning could operate naturally while corporate reporting used consistent financial semantics.

**SME Probe:** What should happen to unmapped local accounts?

**Reflection:** Unmapped financial structures should be explicit exceptions rather than silently disappearing into generic categories.

---

## Question 07 — How would you design global planning dimensions?

**Situation:** Regions used different organizational and profitability dimensions.

**Task:** Establish a common planning data model.

**Action:** I defined mandatory global dimensions such as account, time, organization, currency, version and scenario, then governed additional dimensions such as product, customer or market where enterprise value justified them.

**Result:** Planning models became comparable without forcing every region to use irrelevant dimensions.

**SME Probe:** Why not make every possible dimension globally mandatory?

**Reflection:** Excessive dimensionality increases complexity and performance cost without necessarily increasing decision value.

---

## Question 08 — How would you handle local business drivers?

**Situation:** A regional business used market-specific drivers that did not apply globally.

**Task:** Include the driver without compromising enterprise model consistency.

**Action:** I classified the driver as local, documented its financial relationship, established ownership and mapped its output to the global financial model.

**Result:** Local business economics could influence planning while enterprise financial reporting remained standardized.

**SME Probe:** When should a local driver become global?

**Reflection:** When it becomes materially relevant across multiple markets and has a defensible reusable definition.

---

## Question 09 — How would you govern local planning exceptions?

**Situation:** Every region had accumulated custom planning rules over several years.

**Task:** Reduce uncontrolled customization.

**Action:** I established an exception register with business justification, owner, impact, lifecycle, approval and review date. I assessed whether each exception should be standardized, retained or retired.

**Result:** Local variation became governed rather than accidental.

**SME Probe:** Why should exceptions have expiry or review dates?

**Reflection:** An exception that is never reviewed eventually becomes invisible technical debt.

---

## Question 10 — How would you integrate global planning with SAP S/4HANA Finance?

**Situation:** Global planning was maintained in SAC while actual financial data originated from multiple SAP S/4HANA Finance entities.

**Task:** Create a consistent actual-to-plan architecture.

**Action:** I aligned company codes, ledgers, accounts, cost centers, profit centers, fiscal periods, currencies and organizational mappings. I established governed integration and reconciliation.

**Result:** Global planning and Finance actuals could be compared using consistent enterprise semantics.

**SME Probe:** What happens when local Finance structures differ from the global planning model?

**Reflection:** Controlled semantic mapping is preferable to forcing incompatible source structures into an artificial common structure.

---

## Question 11 — How would you design global and local versions?

**Situation:** Corporate Finance needed a consolidated forecast while regions required local working versions.

**Task:** Prevent version proliferation while preserving regional planning flexibility.

**Action:** I established enterprise baseline versions and governed local working versions with clear lifecycle, ownership and promotion rules.

**Result:** Corporate and local planning remained connected without uncontrolled version creation.

**SME Probe:** When should a local version become an enterprise version?

**Reflection:** Promotion should occur only when the version represents an approved enterprise planning state.

---

## Question 12 — How would you manage global planning security?

**Situation:** Regional planners needed access to local data but should not automatically see sensitive data from other regions.

**Task:** Design scalable security.

**Action:** I used role-based access combined with organizational and dimensional restrictions, separated local write authority from corporate oversight and periodically reviewed access.

**Result:** Global planning remained collaborative while maintaining financial confidentiality.

**SME Probe:** How would you prevent role proliferation?

**Reflection:** Use reusable global roles and governed dimensional access rather than creating a unique role for every local variation.

---

## Question 13 — How would you handle local taxation and regulatory assumptions?

**Situation:** Country planning required different tax, statutory and regulatory assumptions.

**Task:** Preserve local accuracy without creating inconsistent enterprise financial definitions.

**Action:** I separated enterprise financial measures from local assumptions and governed country-specific parameters, ownership and effective dates.

**Result:** Local requirements could be represented while corporate planning remained comparable.

**SME Probe:** Should local tax logic change the global financial model?

**Reflection:** Only where the local requirement materially affects an enterprise financial measure and the change is governed.

---

## Question 14 — How would you design global profitability planning?

**Situation:** Corporate Finance wanted global profitability analysis while regions had different products, customers and cost structures.

**Task:** Establish comparable profitability planning.

**Action:** I standardized core revenue, cost, margin and contribution definitions while allowing local product, customer and market dimensions where required.

**Result:** Corporate Finance gained comparable profitability information without eliminating local economic context.

**SME Probe:** What is the most important global profitability control?

**Reflection:** Consistent financial definitions are more important than identical local operating assumptions.

---

## Question 15 — How would you manage mergers or acquisitions in a global planning architecture?

**Situation:** A newly acquired company used a separate planning platform and financial hierarchy.

**Task:** Integrate the acquired organization without disrupting the existing planning cycle.

**Action:** I mapped accounts, organizations, currencies, planning versions and drivers, preserved pre-acquisition history and established a phased integration roadmap.

**Result:** The acquisition could enter enterprise planning while historical context remained intact.

**SME Probe:** Why use phased integration?

**Reflection:** Controlled integration reduces business disruption and allows mapping and reconciliation to mature progressively.

---

## Question 16 — How would you handle a regional request to duplicate the global planning model?

**Situation:** A region argued that its business was unique and requested a completely separate planning model.

**Task:** Assess whether separation was justified.

**Action:** I examined regulatory, data, process, performance and business requirements and compared them against the cost and control impact of duplication.

**Result:** The decision was based on evidence rather than preference.

**SME Probe:** What is the main risk of unnecessary model duplication?

**Reflection:** Duplication creates divergent definitions, reconciliation effort, maintenance cost and governance complexity.

---

## Question 17 — How would you design global planning analytics?

**Situation:** Corporate Finance wanted consolidated planning analytics while local teams needed detailed operational views.

**Task:** Support both perspectives.

**Action:** I created a common enterprise semantic layer with corporate KPIs and governed drill-downs into regional dimensions and local drivers.

**Result:** Executives received comparable enterprise insight while local teams retained operational detail.

**SME Probe:** How do you prevent local dashboards from redefining enterprise KPIs?

**Reflection:** KPI definitions should be centrally governed even when local analytical views vary.

---

## Question 18 — How would you use AI in global/local planning?

**Situation:** Corporate Finance wanted AI-assisted forecasting across regions with different data quality and planning practices.

**Task:** Introduce AI without creating inconsistent or uncontrolled forecasts.

**Action:** I standardized the input definitions and governance first, assessed data quality by region, applied AI where appropriate and required human validation for material financial outputs.

**Result:** AI-assisted planning could scale without hiding differences in data quality or business context.

**SME Probe:** Should the same AI model be used identically in every country?

**Reflection:** Enterprise governance can be common while model configuration may need to reflect material local differences.

---

## Question 19 — How would you measure the effectiveness of a global/local planning architecture?

**Situation:** Leadership wanted evidence that standardization was producing business value.

**Task:** Establish architecture KPIs.

**Action:** I measured template adoption, exception volume, reconciliation effort, planning-cycle time, forecast consistency, model performance, security findings and local customization trends.

**Result:** Architecture decisions could be evaluated using operational and financial evidence.

**SME Probe:** What does a rising exception count indicate?

**Reflection:** It may indicate legitimate business diversity—or that the global model is failing to meet real requirements. It requires investigation.

---

## Question 20 — How would you architect the target global/local planning operating model?

**Situation:** A multinational enterprise wanted one connected planning capability across corporate and regional Finance.

**Task:** Define the target architecture and governance model.

**Action:** I established a global core for financial definitions, master-data semantics, versions, security principles, workflows, KPIs and enterprise reporting. I allowed governed local extensions for currency, statutory requirements, local drivers, calendars and operational dimensions. I added exception governance, integration with SAP S/4HANA Finance, SAC planning, reconciliation and continuous improvement.

**Result:** The enterprise gained a federated planning architecture: standardized where financial meaning must be common, flexible where local business reality requires variation.

**SME Probe:** What is the ultimate principle of global/local planning architecture?

**Reflection:** The goal is not maximum standardization. It is the right balance between enterprise comparability and local financial truth.

---

# Rapid-Fire SAP Finance Questions

1. What is global/local planning architecture?
2. What belongs in a global planning template?
3. When is local customization justified?
4. How do you manage statutory planning requirements?
5. How do you handle multiple currencies?
6. How do you align global and local planning calendars?
7. How do you map local charts of accounts?
8. What dimensions should be globally standardized?
9. How do you govern local drivers?
10. How do you manage planning exceptions?
11. How do you integrate global planning with S/4HANA Finance?
12. How do you govern global and local versions?
13. How do you secure global planning?
14. How do you handle local tax assumptions?
15. How do you design global profitability planning?
16. How do you integrate acquisitions?
17. When should a region have a separate planning model?
18. How do you design global planning analytics?
19. How can AI support global/local planning?
20. What is the ultimate principle of global/local planning architecture?

---

# @BAISI PAHACHA™ 22-Step Mastery Framework

## KNOW

1. **Domain Foundation** — Understand global planning, local requirements, standardization, exceptions and financial governance.
2. **Product/Technology Knowledge** — Understand SAP S/4HANA Finance and SAP Analytics Cloud Planning in multinational landscapes.
3. **Process & Business Context** — Understand corporate, regional and local planning cycles.
4. **Data & Information Model** — Understand global dimensions, local mappings, currencies, accounts, hierarchies, versions and scenarios.

## DESIGN

5. **Requirement Analysis** — Identify enterprise commonality and genuine local requirements.
6. **Solution Design** — Design global core, local extensions and exception governance.
7. **Configuration/Development** — Build reusable planning structures, workflows, mappings and controlled extensions.
8. **Integration & Architecture** — Connect local Finance structures to the enterprise planning model.

## DELIVER

9. **Testing & Quality Assurance** — Validate global standards, local variations, security and reconciliation.
10. **Deployment & Release** — Govern global releases and local changes.
11. **Migration & Cutover** — Integrate countries, acquisitions and reorganizations safely.
12. **Operations & Support** — Manage local exceptions, support and continuous governance.

## SOLVE

13. **Troubleshooting & Root Cause Analysis** — Diagnose differences caused by local mappings, currencies, periods or structures.
14. **Scenario-Based Problem Solving** — Handle regulatory, organizational and business-specific exceptions.
15. **Risk, Controls & Security** — Protect global financial data and maintain controlled local access.
16. **Performance & Optimization** — Avoid unnecessary dimensionality, customization and model duplication.

## INFLUENCE

17. **Stakeholder Management** — Align corporate Finance, regional CFOs, local Finance, IT and audit.
18. **Communication & Consulting** — Explain why a requirement should be global, local or an exception.
19. **Presales / Leadership / Decision Making** — Lead template and localization decisions.

## TRANSFORM

20. **Transformation & Roadmap** — Move fragmented regional planning toward a federated enterprise architecture.
21. **Innovation & Emerging Technology** — Scale AI-assisted planning while respecting local data quality and context.
22. **Enterprise Architecture & Business Value** — Balance standardization, agility, control and local financial truth.

---

# Anti-Patterns

- Making every local requirement global.
- Treating every local requirement as an exception.
- Duplicating planning models unnecessarily.
- Forcing local structures into artificial global dimensions.
- Ignoring local regulatory requirements.
- Allowing local chart-of-account mappings to remain undocumented.
- Creating excessive local roles.
- Allowing local versions to proliferate.
- Letting local dashboards redefine enterprise KPIs.
- Ignoring currency and fiscal-calendar differences.
- Applying identical assumptions to materially different markets.
- Using AI before establishing data-quality and governance foundations.
- Allowing exceptions to exist indefinitely without review.
- Measuring standardization only by percentage of global adoption.
- Confusing standardization with business value.

---

# Interview Evidence Bank

Prepare STAR stories for:

- Global planning architecture.
- Global-template design.
- Local statutory planning.
- Multi-currency architecture.
- Global/local planning calendars.
- Chart-of-account mapping.
- Global planning dimensions.
- Local business drivers.
- Exception governance.
- S/4HANA Finance integration.
- Global/local versions.
- Planning security.
- Local tax assumptions.
- Global profitability planning.
- Acquisition integration.
- Separate-model decision.
- Global planning analytics.
- AI-assisted global planning.
- Architecture KPI design.
- Federated global/local planning architecture.

Quantify:

**Countries covered | template adoption | local exceptions reduced | reconciliation effort | planning-cycle time | model count | role count | forecast consistency | support effort | acquisition integration time**

---

# Success Criteria

You are interview-ready when you can:

1. Design a global/local planning architecture.
2. Decide what belongs in the global template.
3. Govern legitimate local extensions.
4. Handle local statutory and currency requirements.
5. Align global and local planning calendars.
6. Map local financial structures to enterprise semantics.
7. Govern dimensions, versions and exceptions.
8. Integrate global planning with S/4HANA Finance.
9. Design scalable global planning security.
10. Support acquisitions and organizational changes.
11. Create global planning analytics.
12. Govern AI across different regional data contexts.
13. Measure architecture effectiveness.
14. Explain the trade-off between standardization and local financial truth.

---

# Final BAISI PAHACHA™ Reflection

**KNOW:** I understand why global Finance needs both common standards and local context.

**DESIGN:** I can architect a global core with governed local extensions.

**DELIVER:** I can implement planning structures that work across countries.

**SOLVE:** I can resolve differences caused by currencies, calendars, accounts, regulations and local processes.

**INFLUENCE:** I can help corporate and regional Finance leaders reach architecture decisions based on evidence.

**TRANSFORM:** I can create a federated planning ecosystem that combines enterprise comparability with local financial truth.

## Final Mantra

> **“I do not architect global planning for uniformity. I architect it for shared financial meaning, controlled flexibility and enterprise-wide decision clarity.”**

---

## Progress

**AFP6 — Financial Planning & Performance: 18/22 modules complete**

**Completed:** #01 Financial Planning & Performance Finance Requirement & Solution Design; #02 Financial Planning Process & Business Architecture; #03 Financial Planning & Budgeting; #04 Financial Forecasting & Rolling Forecasts; #05 Financial Planning Drivers & Assumptions; #06 Planning Versions, Scenarios & Simulation; #07 Financial Planning Data Model & Master Data; #08 Planning Workflow, Approvals & Governance; #09 Financial Planning Integration with SAP S/4HANA Finance; #10 Planning Testing & Quality Assurance; #11 Planning Data Migration; #12 Planning Security & Controls; #13 Financial Planning Analytics & Variance Analysis; #14 Profitability Planning & Performance Management; #15 Workforce & OPEX Planning; #16 CapEx & Investment Planning; #17 Planning Production Support & Close/Planning Cycle Management; #18 Global/Local Planning Architecture

**Next:** **AFP6 #19 — Planning Knowledge Architecture**
