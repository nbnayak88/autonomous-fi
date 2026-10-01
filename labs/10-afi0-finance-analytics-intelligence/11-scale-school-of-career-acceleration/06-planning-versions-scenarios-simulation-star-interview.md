# AFI0 #06 — Planning Versions, Scenarios & Simulation — STAR Interview Mastery

**Lab:** Finance Analytics & Intelligence (AFI0)  
**Track:** Scale — School of Career Acceleration  
**Domain:** SAP Finance / SAP Analytics Cloud Planning / SAP S/4HANA / FP&A  
**Mastery:** **VERSION-INSIGHT-FI = Define → Separate → Model → Simulate → Compare → Govern → Approve → Decide**

## Interview Objective

Demonstrate how to design and govern SAP Finance planning versions, scenarios and simulations so that Finance can explore alternatives without compromising the integrity of approved budgets, forecasts and financial actuals.

> **STAR discipline:** Every scenario uses **Situation → Task → Action → Result**, followed by **SME Probe → Reflection**.

---

# 20 Scenario-Based Questions + STAR Answers

## 01. Planning Version Architecture
**Question:** How would you design planning versions for a Finance organization?

**Situation:** Finance had budget, forecast and simulation values stored with inconsistent naming and unclear status.  
**Task:** Establish a controlled planning-version architecture.  
**Action:** I defined version purpose, type, owner, status, fiscal horizon, scenario relationship, approval state, security and lifecycle rules.  
**Result:** Finance could distinguish approved plans, working forecasts and simulations reliably.  
**SME Probe:** Why is version identity important?  
**Reflection:** A planning number has meaning only when its version context is known.

## 02. Budget vs Forecast vs Simulation
**Question:** How would you distinguish an approved budget, rolling forecast and simulation?

**Situation:** Business users treated all planning values as interchangeable.  
**Task:** Establish clear semantic boundaries.  
**Action:** I defined each version's purpose, authority, update rules, approval status, permitted use and relationship to actuals.  
**Result:** Management reporting and decision-making used the correct planning context.  
**SME Probe:** Why should simulations not be treated as approved forecasts?  
**Reflection:** Planning semantics protect decision integrity.

## 03. Version Naming Standards
**Question:** How would you establish a naming convention for Finance planning versions?

**Situation:** Users created versions such as “Final,” “Final2” and “Latest Forecast.”  
**Task:** Create unambiguous version identification.  
**Action:** I standardized naming around planning type, fiscal year, cycle, scenario and status, with ownership and lifecycle metadata.  
**Result:** Users could identify versions consistently across planning and analytics.  
**SME Probe:** What information should a version name communicate?  
**Reflection:** Naming is a small control that prevents significant analytical confusion.

## 04. Version Lifecycle
**Question:** How would you manage the lifecycle of a planning version?

**Situation:** Old working versions remained editable long after the planning cycle ended.  
**Task:** Prevent obsolete versions from affecting decisions.  
**Action:** I defined creation, working, review, approval, lock, archive and retirement states with responsible owners and access rules.  
**Result:** Version lifecycle became controlled and auditable.  
**SME Probe:** Why lock an approved version?  
**Reflection:** Approval has little meaning if approved numbers remain silently editable.

## 05. Baseline Version
**Question:** How would you establish a baseline for Finance planning?

**Situation:** Leadership wanted to measure how the latest forecast changed from the originally approved plan.  
**Task:** Preserve an immutable baseline.  
**Action:** I identified the approved budget or strategic plan as the baseline, locked it after approval and established controlled comparison measures.  
**Result:** Finance could measure plan-to-current-outlook movement consistently.  
**SME Probe:** What makes a baseline trustworthy?  
**Reflection:** A baseline must be stable and governed.

## 06. Scenario Design
**Question:** How would you design base, upside and downside Finance scenarios?

**Situation:** Executives wanted to evaluate uncertain market and cost conditions.  
**Task:** Create useful scenarios without excessive complexity.  
**Action:** I identified material uncertainty drivers, defined scenario assumptions, established calculation rules and separated scenarios from the approved forecast.  
**Result:** Leadership could compare meaningful alternatives and understand their assumptions.  
**SME Probe:** How do you decide which scenarios are worth modeling?  
**Reflection:** Scenario design should focus on material uncertainty and actionable decisions.

## 07. What-If Simulation
**Question:** How would you build a what-if simulation for Finance?

**Situation:** Management wanted to understand the impact of a major price and volume change.  
**Task:** Quantify the financial impact without changing the approved plan.  
**Action:** I copied relevant planning inputs into a controlled simulation context, changed the selected drivers, recalculated financial measures and compared results against the baseline.  
**Result:** Management could evaluate the alternative without contaminating official planning values.  
**SME Probe:** What control prevents simulation data from becoming official data?  
**Reflection:** Simulation requires technical and governance separation.

## 08. Scenario Driver Governance
**Question:** How would you govern assumptions across multiple scenarios?

**Situation:** Different scenario models used inconsistent FX, volume and cost assumptions.  
**Task:** Make scenario comparison meaningful.  
**Action:** I defined shared driver semantics, scenario-specific values, ownership, effective periods, versioning and documentation of assumptions.  
**Result:** Scenario outputs became comparable and explainable.  
**SME Probe:** Can every scenario have completely different dimensions?  
**Reflection:** Scenarios should vary assumptions intentionally while preserving analytical comparability.

## 09. Scenario Comparison
**Question:** How would you compare multiple Finance scenarios?

**Situation:** Leadership received separate spreadsheets for base, downside and upside cases.  
**Task:** Provide structured scenario comparison.  
**Action:** I aligned measures, dimensions, periods, currencies and driver assumptions, then calculated absolute and percentage differences and identified material drivers.  
**Result:** Leaders could understand both outcome differences and their causes.  
**SME Probe:** Why compare drivers as well as financial totals?  
**Reflection:** Scenario comparison should explain why outcomes differ.

## 10. Scenario Approval
**Question:** Should every Finance scenario require formal approval?

**Situation:** Users created dozens of simulations during planning.  
**Task:** Establish proportional governance.  
**Action:** I distinguished exploratory simulations from management scenarios used for formal decisions. I applied stronger approval, ownership and evidence requirements to scenarios that influenced official decisions.  
**Result:** Governance effort matched decision impact.  
**SME Probe:** What makes a scenario decision-significant?  
**Reflection:** Governance should be proportional to risk and consequence.

## 11. Forecast Version Comparison
**Question:** How would you compare two rolling forecast versions?

**Situation:** Management wanted to know why the latest forecast differed from the previous cycle.  
**Task:** Explain forecast movement.  
**Action:** I aligned both versions at the same dimensional grain, calculated changes and decomposed material movement into driver, timing, volume, rate and other relevant effects.  
**Result:** Management could see how the outlook changed and why.  
**SME Probe:** What if dimensional structures changed between versions?  
**Reflection:** Version comparison requires controlled semantic consistency.

## 12. Version Security
**Question:** How would you secure Finance planning versions?

**Situation:** Business users should edit working forecasts but only selected Finance users should modify approved versions.  
**Task:** Protect planning integrity.  
**Action:** I mapped roles to version status and organizational scope, restricted write access to working versions and enforced controlled approval and locking.  
**Result:** Planning ownership and approved values remained protected.  
**SME Probe:** Why should security depend on version status?  
**Reflection:** Access should reflect the business meaning of the data.

## 13. Simulation and Actuals Separation
**Question:** How would you prevent simulated values from being confused with SAP Finance actuals?

**Situation:** Users wanted simulations in the same analytical environment as actuals.  
**Task:** Preserve financial truth.  
**Action:** I clearly separated actual and planning data semantics, labeled scenario status, applied distinct versions and designed analytics that explicitly identified actual versus simulated values.  
**Result:** Users could analyze alternatives without mistaking them for posted Finance results.  
**SME Probe:** Why should actuals remain immutable in planning analytics?  
**Reflection:** Actual accounting results are a governed historical record.

## 14. Scenario Sensitivity
**Question:** How would you identify which scenario assumptions have the greatest financial impact?

**Situation:** Leadership had many possible assumptions but limited time for analysis.  
**Task:** Focus scenario discussion on material uncertainties.  
**Action:** I performed sensitivity analysis across key drivers, measured financial response and prioritized assumptions based on impact, uncertainty and management controllability.  
**Result:** Scenario discussions focused on the assumptions most relevant to decisions.  
**SME Probe:** What makes a sensitivity result actionable?  
**Reflection:** Sensitivity becomes valuable when it changes management attention or action.

## 15. Planning Version Data Quality
**Question:** What would you do if one planning version contained inconsistent data?

**Situation:** A forecast version showed unexpected values for a regional cost center.  
**Task:** Determine whether the issue was source data, mapping, calculation or version-specific logic.  
**Action:** I traced the data lineage, compared versions, validated dimensions and calculations, reconciled affected records and corrected the responsible layer.  
**Result:** The affected version was restored without changing unrelated planning data.  
**SME Probe:** Why compare versions during root-cause analysis?  
**Reflection:** Version comparison helps isolate changes that introduced an anomaly.

## 16. Planning Version Migration
**Question:** How would you migrate planning versions during an SAP Finance transformation?

**Situation:** A company was moving planning capabilities while historical budget and forecast versions were needed for comparison.  
**Task:** Preserve relevant planning history.  
**Action:** I classified versions by business value, mapped dimensions and master data, validated historical calculations, reconciled totals and preserved critical baseline and forecast versions with appropriate metadata.  
**Result:** Finance retained meaningful historical comparisons after transformation.  
**SME Probe:** Should every historical version be migrated?  
**Reflection:** Migration should preserve decision-relevant history rather than indiscriminately copying everything.

## 17. Scenario Workflow
**Question:** How would you design a workflow for scenario creation and approval?

**Situation:** Scenario models were created informally and sometimes presented as management recommendations without review.  
**Task:** Establish decision governance.  
**Action:** I defined scenario creation, assumption documentation, analytical review, business challenge, approval and publication states, with clear ownership and audit history.  
**Result:** Decision-significant scenarios became traceable and governed.  
**SME Probe:** Why document scenario assumptions?  
**Reflection:** Decision-makers need to understand the conditions behind a scenario.

## 18. Scenario Automation
**Question:** How would you automate recurring scenario analysis?

**Situation:** Finance repeatedly rebuilt base, downside and upside models manually.  
**Task:** Reduce repetitive effort.  
**Action:** I standardized driver inputs, version structures and calculation logic, then automated scenario generation, comparison and exception reporting while preserving approval controls.  
**Result:** Scenario analysis became faster and more repeatable.  
**SME Probe:** What should remain manually reviewed?  
**Reflection:** Automation should accelerate analysis without removing decision accountability.

## 19. AI-Assisted Scenario Analysis
**Question:** How would you use AI to support Finance scenario analysis?

**Situation:** Leadership wanted to explore many possible business conditions more quickly.  
**Task:** Use AI to accelerate scenario exploration responsibly.  
**Action:** I used AI to identify candidate driver combinations and summarize scenario differences, while enforcing governed data, clear assumptions, validation, human review and separation from approved Finance versions.  
**Result:** Finance could explore alternatives faster without allowing AI-generated scenarios to become uncontrolled official plans.  
**SME Probe:** Should AI create an approved Finance plan autonomously?  
**Reflection:** AI can accelerate exploration; governance determines what becomes an official financial decision.

## 20. Enterprise Planning Version Architecture
**Question:** How would you architect enterprise-wide planning versions, scenarios and simulations?

**Situation:** A multinational Finance organization used different planning conventions across regions.  
**Task:** Establish a common architecture while supporting legitimate local needs.  
**Action:** I designed a version taxonomy, lifecycle, scenario framework, driver model, security model, approval process, comparison logic, audit trail, integration approach and governance standards.  
**Result:** Finance gained a consistent planning architecture supporting budgeting, forecasting, simulations and executive decision-making.  
**SME Probe:** What makes a version architecture scalable?  
**Reflection:** Scalability comes from common semantics, controlled variation and clear lifecycle governance.

---

# Rapid-Fire SAP Finance Planning Questions

1. What is a planning version?
2. How do budget and forecast versions differ?
3. Why are version names important?
4. What is a version lifecycle?
5. Why preserve an immutable baseline?
6. How should scenarios be designed?
7. What is what-if simulation?
8. How do you govern scenario drivers?
9. How should scenarios be compared?
10. Which scenarios need formal approval?
11. How do you compare forecast versions?
12. How should version security work?
13. How do you separate simulations from actuals?
14. How do you perform scenario sensitivity analysis?
15. How do you troubleshoot version-specific data issues?
16. What planning history should be migrated?
17. How should scenario workflows operate?
18. What can be automated in scenario analysis?
19. How should AI support simulations?
20. What makes enterprise version architecture scalable?

---

# BAISI PAHACHA™ 22-Step Mastery Framework — AFI0 #06

## KNOW — 1–4
1. **Domain Foundation** — Planning versions, scenarios, simulations, budgets and forecasts.
2. **Product/Technology Knowledge** — SAP S/4HANA Finance, SAP Analytics Cloud Planning and Finance analytics.
3. **Process & Business Context** — Budget cycles, rolling forecasts, scenario planning and management decisions.
4. **Data & Information Model** — Versions, scenarios, drivers, dimensions, measures, periods and metadata.

## DESIGN — 5–8
5. **Requirement Analysis** — Identify decisions requiring alternative planning views.
6. **Solution Design** — Design version, scenario and simulation architecture.
7. **Configuration/Development** — Implement governed planning models and workflows.
8. **Integration & Architecture** — Connect planning versions to SAP Finance actuals and enterprise data.

## DELIVER — 9–12
9. **Testing & Quality Assurance** — Validate calculations, version integrity, reconciliation and security.
10. **Deployment & Release** — Govern changes to planning models and scenarios.
11. **Migration & Cutover** — Preserve decision-relevant planning history.
12. **Operations & Support** — Manage version lifecycle, approvals and exceptions.

## SOLVE — 13–16
13. **Troubleshooting & Root Cause Analysis** — Diagnose version and scenario anomalies.
14. **Scenario-Based Problem Solving** — Analyze alternative financial outcomes.
15. **Risk, Controls & Security** — Protect approved plans and financial truth.
16. **Performance & Optimization** — Improve scenario generation and comparison efficiency.

## INFLUENCE — 17–19
17. **Stakeholder Management** — Align FP&A, Controllers, Finance leadership and business units.
18. **Communication & Consulting** — Explain scenarios, assumptions and trade-offs.
19. **Presales / Leadership / Decision Making** — Lead planning architecture decisions.

## TRANSFORM — 20–22
20. **Transformation & Roadmap** — Establish enterprise planning-version capability.
21. **Innovation & Emerging Technology** — Apply automation and AI to scenario analysis.
22. **Enterprise Architecture & Business Value** — Connect planning scenarios to enterprise decisions and value.

---

# Planning Version Anti-Patterns

- Calling every planning number “forecast.”
- Allowing approved versions to remain freely editable.
- Using “Final,” “Final2” and “Latest” as version identifiers.
- Overwriting prior forecasts.
- Mixing simulations with approved plans.
- Creating scenarios without material decision questions.
- Allowing every scenario to use different semantics.
- Comparing versions at inconsistent dimensional grain.
- Giving broad write access to approved versions.
- Migrating every historical version without business-value assessment.
- Treating scenario output as financial fact.
- Automating scenario creation without approval governance.
- Allowing AI-generated scenarios to enter official planning without validation.
- Ignoring version metadata and assumption lineage.

---

# Interview Evidence Bank

Prepare STAR evidence for:

- Planning-version architecture.
- Budget/forecast/simulation separation.
- Version naming standards.
- Version lifecycle governance.
- Baseline creation.
- Scenario design.
- What-if simulation.
- Scenario-driver governance.
- Scenario comparison.
- Scenario approval.
- Forecast-version comparison.
- Version security.
- Actual-versus-simulation separation.
- Sensitivity analysis.
- Version-specific data-quality remediation.
- Planning-version migration.
- Scenario workflow.
- Scenario automation.
- AI-assisted scenario analysis.
- Enterprise planning-version architecture.

For every evidence item capture:

**Decision → Version/Scenario → Assumptions → SAP Finance/SAC Model → Governance → Comparison → Result → Management Action → Learning.**

---

# Success Criteria

You are interview-ready when you can:

- Design a governed planning-version taxonomy.
- Explain budget, forecast and simulation semantics.
- Establish naming and lifecycle standards.
- Preserve approved baselines.
- Design meaningful scenarios.
- Build controlled what-if simulations.
- Govern scenario drivers.
- Compare versions and explain movements.
- Apply proportional scenario approval.
- Secure planning versions.
- Keep simulations separate from SAP Finance actuals.
- Perform sensitivity analysis.
- Troubleshoot version-specific data issues.
- Migrate decision-relevant planning history.
- Design scenario workflows.
- Automate recurring scenario analysis.
- Apply AI responsibly to scenario exploration.
- Architect enterprise planning-version governance.
- Explain every decision in SAP Finance context.
- Answer all 20 scenarios using concise STAR evidence.

---

# Final BAISI PAHACHA™ Reflection

**Before:** I viewed planning versions as technical containers for different Finance numbers.

**After:** I can architect versions and scenarios as **governed decision contexts that preserve financial truth while allowing Finance to explore uncertainty**.

The maturity shift is:

**Version → Scenario → Simulation → Comparison → Decision → Learning**

The deeper interview answer is:

> **“I design planning versions so Finance can distinguish what is approved, what is forecast, what is hypothetical and what is under review. This creates the freedom to simulate alternatives without compromising the integrity of official financial information.”**

## Final Mantra

> **Define the context. Separate the truth. Model the scenario. Simulate safely. Compare intelligently. Govern the decision. Approve deliberately. Learn continuously.**

---

# AFI0 Progress

**AFI0 Finance Analytics & Intelligence — 06/22 modules complete**

Completed: **#01 Requirement & Solution Design → #02 Process & Business Architecture → #03 Financial Planning, Budgeting & Performance Analytics → #04 Financial Forecasting & Rolling Forecast Analytics → #05 Financial Planning Drivers & Assumptions → #06 Planning Versions, Scenarios & Simulation**

**Next:** #07 Financial Planning Data Model & Master Data

**Transformation path:**  
Finance Reporting Practitioner → SAP Finance Analytics SME → Finance Analytics Architect → Finance Intelligence Leader → Trusted Finance Data & Decision Advisor
