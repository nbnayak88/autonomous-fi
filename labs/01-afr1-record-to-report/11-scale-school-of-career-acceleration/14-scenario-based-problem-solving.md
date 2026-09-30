# 14 — Scenario-Based Problem Solving

## Course
**Applied SAP S/4HANA Finance — AFR1 Record to Report**

- **Stream:** Enterprise Architect
- **Lab:** 11 — Scale | School of Career Acceleration
- **Theme:** SOLVE
- **Pahacha:** @baisi pahacha — Step 14: Scenario-Based Problem Solving
- **Purpose:** Move from knowing Finance concepts to solving ambiguous, cross-functional business problems with structured architectural reasoning.

## Mastery Objective

Senior Finance architecture interviews rarely ask only, “What does SAP do?”

They ask:

> **“Here is a business problem. What would you do?”**

A strong answer connects:

**Business problem → assumptions → diagnosis → options → trade-offs → decision → execution → measurable outcome.**

The architect must solve under uncertainty without jumping prematurely to configuration.

---

# 20 Scenario-Based Interview Questions

## 1. CFO wants a 50% faster close

**Question:** The CFO wants month-end close reduced from 10 days to 5. What would you do?

**S — Situation:** Finance had a long close cycle with substantial manual reconciliation and dependency on upstream processes.

**T — Task:** I needed to determine whether the target was achievable and identify the highest-value interventions.

**A — Action:** I mapped the close value stream, measured cycle time by activity, identified manual touchpoints and waiting states, assessed upstream P2P/O2C/asset/payroll dependencies, and separated process, data, control, and technology constraints. I then prioritized automation, standardization, continuous accounting, exception management, and close orchestration.

**R — Result:** The target became a measurable transformation roadmap rather than an arbitrary technology request.

**SME Probe:** Which metric would you improve first?

**Reflection:** A close problem should be solved as a value-stream problem, not simply an ERP-performance problem.

---

## 2. Business wants a custom process SAP does not support

**Question:** A business unit requests heavy customization. How do you respond?

**S:** A business stakeholder believed a highly customized process was essential.

**T:** I needed to preserve the business outcome while protecting maintainability.

**A:** I clarified the underlying requirement, distinguished mandatory business capability from preferred user behavior, evaluated standard SAP, configuration, extensibility, integration, and process redesign options, and documented trade-offs.

**R:** The discussion moved from “build exactly this” to “achieve this outcome sustainably.”

**SME Probe:** When would customization actually be justified?

**Reflection:** Architecture begins by solving the problem, not implementing the requested mechanism.

---

## 3. Global template versus local requirement

**Question:** One country says the global Finance template cannot meet its statutory needs.

**S:** A local team requested significant deviation from the global design.

**T:** I needed to determine what must be localized and what should remain standardized.

**A:** I classified the requirement into statutory, regulatory, business differentiation, operational preference, and historical practice. I assessed the impact on process, data, integration, controls, reporting, and support.

**R:** Mandatory local capability could be preserved while unnecessary divergence was challenged.

**SME Probe:** What makes a good localization decision?

**Reflection:** Local variation should have an explicit business or regulatory reason.

---

## 4. Acquisition introduces a second ERP

**Question:** Your company acquires an organization running another ERP. How would you solve the Finance integration problem?

**S:** The enterprise now had two accounting landscapes and needed consolidated visibility.

**T:** I needed to create a pragmatic integration and convergence strategy.

**A:** I mapped capabilities, data ownership, chart-of-accounts structures, accounting calendars, currencies, interfaces, controls, and reporting requirements. I defined transitional integration and a target-state architecture with clear migration decision points.

**R:** The organization could operate safely during transition while progressing toward a coherent Finance architecture.

**SME Probe:** Why should integration not automatically mean immediate ERP migration?

**Reflection:** Transformation should be staged according to business value and risk.

---

## 5. Finance and HR numbers disagree

**Question:** Payroll expense in Finance does not match HR payroll results.

**S:** Finance identified a recurring discrepancy between payroll and accounting.

**T:** I needed to locate the first divergence.

**A:** I established common definitions, period boundaries, employee populations, accounting mappings, posting dates, interfaces, adjustments, and reconciliation rules. I traced the data from payroll calculation through accounting and reporting.

**R:** The discrepancy could be classified as timing, mapping, data, processing, or reporting rather than treated as a generic “SAP issue.”

**SME Probe:** Why are definitions important before reconciliation?

**Reflection:** Two systems cannot reconcile if they are measuring different things.

---

## 6. Treasury wants real-time cash visibility

**Question:** Treasury wants real-time global cash visibility. What architecture would you propose?

**S:** Cash data was distributed across banks, ERP systems, and business units.

**T:** I needed to create a trusted and timely liquidity view.

**A:** I mapped bank connectivity, account data, transaction feeds, cash positions, currencies, business entities, reconciliation, security, integration patterns, analytics, and latency requirements. I separated operational cash visibility from forecasting and decision intelligence.

**R:** The architecture became an end-to-end liquidity capability rather than a dashboard-only solution.

**SME Probe:** What is the difference between real-time data and real-time decision-making?

**Reflection:** Fresh data does not automatically produce better decisions.

---

## 7. Finance wants AI but cannot define the use case

**Question:** Leadership says, “We need AI in Finance.” How do you respond?

**S:** Leadership had strong interest in AI but no prioritized business problem.

**T:** I needed to convert enthusiasm into measurable use cases.

**A:** I mapped Finance pain points and identified opportunities such as close exception detection, reconciliation assistance, cash forecasting, anomaly detection, collections prioritization, document processing, and decision support. I assessed value, data readiness, risk, explainability, controls, and human oversight.

**R:** AI became a portfolio of governed business use cases instead of a generic technology initiative.

**SME Probe:** What makes a Finance AI use case production-ready?

**Reflection:** Start with a business decision or workflow, not the model.

---

## 8. Audit identifies excessive manual journals

**Question:** Audit reports excessive manual journal entries. What would you do?

**S:** Audit identified a high volume of manual postings.

**T:** I needed to determine why they existed and reduce unnecessary risk.

**A:** I classified journals by source, reason, frequency, value, approval, recurrence, and upstream cause. I identified candidates for process correction, automation, recurring entries, integration, and stronger controls.

**R:** The organization could reduce manual activity while addressing the underlying process causes.

**SME Probe:** Why is simply banning manual journals inappropriate?

**Reflection:** Some manual adjustments are legitimate; the objective is controlled necessity.

---

## 9. Financial reporting definitions conflict

**Question:** CFO, business units, and analytics teams use different definitions for EBITDA and revenue.

**S:** Executive reports showed conflicting values for apparently identical metrics.

**T:** I needed to establish semantic consistency.

**A:** I documented metric definitions, calculation rules, data ownership, source systems, grain, hierarchies, exceptions, and governance. I created a controlled semantic model and aligned reporting products to it.

**R:** Reporting disagreements became governed data-definition issues instead of repeated reconciliation debates.

**SME Probe:** Who should own a Finance KPI definition?

**Reflection:** A dashboard cannot solve an undefined metric.

---

## 10. Close is dependent on multiple upstream systems

**Question:** Close cannot finish until P2P, O2C, payroll, and assets complete.

**S:** Finance close was repeatedly delayed by upstream process completion.

**T:** I needed to solve the dependency problem without destabilizing source processes.

**A:** I mapped cross-process dependencies, defined readiness criteria, introduced dependency monitoring, exception-based escalation, automated status visibility, and evaluated continuous accounting opportunities.

**R:** Finance gained transparency into close readiness and could address blockers earlier.

**SME Probe:** Why is the close team not always the right place to solve the delay?

**Reflection:** The bottleneck may exist upstream of the visible symptom.

---

## 11. Company wants to standardize 30 countries

**Question:** How would you approach global Finance standardization?

**S:** Thirty countries had different processes and varying levels of SAP standardization.

**T:** I needed to balance global consistency with legitimate local requirements.

**A:** I created a capability and process baseline, identified common patterns, classified local deviations, defined global design principles, established template governance, and sequenced rollout according to readiness and risk.

**R:** Standardization became a governed transformation program rather than a forced one-size-fits-all implementation.

**SME Probe:** What should never be standardized blindly?

**Reflection:** Regulatory and legally required differences need evidence-based treatment.

---

## 12. Finance data quality is poor

**Question:** Reports cannot be trusted because Finance master data is inconsistent.

**S:** Analytics teams repeatedly found missing, duplicate, and inconsistent Finance data.

**T:** I needed to solve the systemic data problem.

**A:** I established data ownership, quality dimensions, critical data elements, validation rules, lineage, stewardship, monitoring, remediation workflows, and upstream prevention.

**R:** Data quality moved from periodic cleanup to continuous governance.

**SME Probe:** What is more important: cleansing or prevention?

**Reflection:** Cleansing repairs history; prevention protects the future.

---

## 13. Finance transformation has a limited budget

**Question:** You have 20 requested initiatives but funding for five.

**S:** Leadership had more transformation requests than available capacity.

**T:** I needed a transparent prioritization method.

**A:** I assessed each initiative using business value, risk reduction, regulatory necessity, dependency, feasibility, data readiness, architectural impact, and time-to-value. I created a dependency-aware roadmap rather than selecting projects independently.

**R:** Investment decisions became traceable and connected to enterprise outcomes.

**SME Probe:** Why is “highest ROI” alone insufficient?

**Reflection:** Regulatory, risk, dependency, and architecture considerations can change sequencing.

---

## 14. A critical Finance interface fails during close

**Question:** A bank or subledger interface fails during month-end close. What do you do?

**S:** A close-critical integration failed during a time-sensitive period.

**T:** I needed to protect financial integrity and restore processing quickly.

**A:** I established impact and scope, contained further processing, checked monitoring and correlation IDs, identified failed messages, assessed duplicate risk, restored the service or used a governed contingency path, and reconciled after recovery.

**R:** Processing resumed without sacrificing control or creating duplicate financial outcomes.

**SME Probe:** Why is “just rerun it” unsafe?

**Reflection:** Recovery must preserve transaction integrity.

---

## 15. Business requests real-time reporting on historical Finance data

**Question:** Why is the existing report too slow, and what would you do?

**S:** A management report over large historical data volumes had unacceptable response time.

**T:** I needed to improve user experience without compromising analytical accuracy.

**A:** I examined query patterns, data volume, grain, semantic models, extraction, aggregation, workload separation, and architecture. I determined whether embedded analytics, a dedicated analytical model, or broader data architecture was appropriate.

**R:** The solution addressed the workload architecture rather than merely increasing resources.

**SME Probe:** What architectural question should be asked before tuning a query?

**Reflection:** Ask whether the workload belongs on the platform where it is currently running.

---

## 16. Merger requires chart-of-accounts harmonization

**Question:** Two organizations use incompatible charts of accounts.

**S:** Consolidated reporting required common financial semantics.

**T:** I needed to harmonize without losing statutory and historical traceability.

**A:** I mapped accounts semantically, identified one-to-many and many-to-one relationships, preserved historical lineage, defined target hierarchies, established mapping governance, and validated consolidated reporting.

**R:** The enterprise gained common reporting semantics while retaining necessary historical context.

**SME Probe:** Why is simple account renaming insufficient?

**Reflection:** A chart of accounts is an information architecture, not merely a list.

---

## 17. A business process is compliant but inefficient

**Question:** Audit is satisfied, but Finance says the process is too slow.

**S:** Controls worked but required excessive manual effort.

**T:** I needed to improve efficiency without weakening control.

**A:** I mapped control objectives, manual activities, evidence requirements, approval points, exception rates, and automation opportunities. I redesigned the process so controls were embedded rather than duplicated.

**R:** Efficiency improvement could be pursued while preserving the required control objective.

**SME Probe:** What is the difference between removing a control and automating a control?

**Reflection:** Good architecture makes controls easier to execute correctly.

---

## 18. Leadership wants autonomous Finance

**Question:** What does “autonomous Finance” mean architecturally?

**S:** Leadership wanted Finance operations to become increasingly autonomous.

**T:** I needed to translate the vision into an actionable architecture.

**A:** I defined a maturity path from transaction automation to exception management, predictive insight, AI-assisted decisions, governed agentic actions, and autonomous outcomes. I included identity, authorization, policies, observability, human escalation, auditability, and measurable business outcomes.

**R:** Autonomy became a controlled progression rather than unrestricted automation.

**SME Probe:** Which Finance decisions should remain human-governed?

**Reflection:** Autonomy must be bounded by risk and control.

---

## 19. Transformation program is technically successful but business adoption is low

**Question:** SAP went live successfully, but users still use spreadsheets.

**S:** The implementation met technical go-live criteria but business adoption remained weak.

**T:** I needed to identify why the designed solution was not becoming the operating model.

**A:** I assessed user journeys, process friction, training, role design, reporting gaps, data trust, change readiness, and workarounds. I used usage evidence to prioritize improvements.

**R:** The transformation shifted from “system delivered” to “capability adopted.”

**SME Probe:** What does adoption tell an architect?

**Reflection:** Architecture is successful only when the intended capability works in real organizational behavior.

---

## 20. Architect a Finance problem-solving operating model

**Question:** How would you institutionalize scenario-based problem solving across Finance?

**S:** Complex Finance issues were repeatedly escalated to a small group of experts.

**T:** I needed to create scalable problem-solving capability.

**A:** I established a structured diagnostic and decision framework, reusable scenario playbooks, architecture decision records, evidence standards, root-cause reviews, knowledge assets, simulation exercises, and metrics for resolution and recurrence.

**R:** Problem-solving became a learning system that improved with every scenario.

**SME Probe:** How would you know the model is working?

**Reflection:** The strongest capability converts incidents into organizational learning.

---

# Rapid-Fire Questions

1. What is the difference between a problem and a symptom?
2. How do you structure an ambiguous Finance problem?
3. What assumptions should you state?
4. How do you identify missing information?
5. What makes a hypothesis useful?
6. How do you compare solution options?
7. What is a trade-off?
8. How do you prioritize under constraints?
9. How do you handle conflicting stakeholders?
10. How do you distinguish a process problem from a technology problem?
11. Why map the value stream?
12. When should standard SAP be challenged?
13. When should customization be considered?
14. What is an architecture decision record?
15. Why are dependencies important?
16. How do you design for reversibility?
17. What makes a Finance solution scalable?
18. How do you measure business outcome?
19. How do you convert a problem into a roadmap?
20. What separates an architect's answer from a consultant's answer?

---

# Mastery Framework — SOLVE

Use this 7-step method for ambiguous scenario questions:

### 1. STATE
Restate the business problem and desired outcome.

### 2. OUTLINE
Define scope, stakeholders, constraints, assumptions, and missing information.

### 3. LOCATE
Map the problem across process, application, data, integration, people, controls, and technology.

### 4. VERIFY
Test hypotheses using evidence, scenarios, metrics, and comparisons.

### 5. EVALUATE
Generate options and compare value, risk, complexity, cost, dependencies, and reversibility.

### 6. EXECUTE
Define the implementation sequence, ownership, controls, validation, and change approach.

### 7. LEARN
Measure results, capture decisions, and feed lessons back into architecture and operating models.

**Memory line:**

> **State → Outline → Locate → Verify → Evaluate → Execute → Learn**

---

# Common Anti-Patterns

- Jumping directly to SAP configuration.
- Solving the requested solution instead of the underlying problem.
- Ignoring assumptions.
- Treating every stakeholder request as a requirement.
- Giving a single option without trade-offs.
- Ignoring organizational readiness.
- Ignoring data and integration dependencies.
- Optimizing local processes at enterprise expense.
- Treating standardization as absolute.
- Treating customization as automatically wrong.
- Designing AI without a business decision or control model.
- Measuring project completion instead of business outcomes.
- Ignoring adoption.
- Producing architecture without an execution path.
- Confusing technical success with transformation success.

---

# Interview Evidence Bank

Prepare STAR stories demonstrating:

1. Ambiguous Finance problem.
2. Conflicting stakeholder requirements.
3. Global/local design trade-off.
4. SAP standard versus customization.
5. Cross-system reconciliation.
6. Finance-HR integration issue.
7. Real-time cash visibility.
8. AI use-case discovery.
9. Manual journal reduction.
10. KPI semantic harmonization.
11. Cross-process close dependency.
12. Global Finance template.
13. Finance data-quality transformation.
14. Prioritization under budget constraints.
15. Critical interface failure.
16. Finance analytics performance.
17. Chart-of-accounts harmonization.
18. Control automation.
19. Autonomous Finance design.
20. Adoption/transformation challenge.

For each story, articulate:

**Problem → Context → Constraints → Hypotheses → Options → Trade-offs → Decision → Execution → Outcome → Learning.**

---

# Success Criteria

You have mastered Step 14 when you can:

- Solve ambiguous Finance scenarios without premature configuration.
- State assumptions clearly.
- Separate symptoms, causes, constraints, and outcomes.
- Map problems across architecture layers.
- Develop multiple solution options.
- Explain trade-offs objectively.
- Make decisions under uncertainty.
- Connect technical choices to business outcomes.
- Handle global versus local requirements.
- Prioritize transformation investments.
- Design AI and autonomous Finance use cases responsibly.
- Account for data, integration, security, controls, and adoption.
- Convert a problem into an executable roadmap.
- Demonstrate learning from previous scenarios.

---

# Final Interview Mantra

> **“When I face an ambiguous Finance problem, I first clarify the outcome and constraints. I map the problem across business, process, data, application, integration, controls, and technology. I test hypotheses, compare options and trade-offs, make a transparent architecture decision, define execution and measurement, and use the result to improve the enterprise.”**

## Architecture Lens

A scenario is never only a technical question.

Think across:

**Business → Process → Data → Application → Integration → Security → Technology → UX → Operations → AI → Industry → Enterprise.**

The architect's superpower is not having every answer immediately.

**It is having a repeatable way to discover the right answer.**
