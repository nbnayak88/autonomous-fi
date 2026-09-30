# AOT3 #06 — O2C Credit Management, Collections & Receivables Controls
## STAR Interview Preparation | SAP Finance

> Finance focus: protecting cash flow, controlling receivables exposure, enforcing customer credit policy, and converting overdue AR into measurable collection outcomes.

## 1. Complex Credit Management Requirement
**Situation:** A business had inconsistent customer credit limits and frequent order blocks.
**Task:** Design a Finance-controlled credit management approach without disrupting legitimate sales.
**Action:** I mapped customer risk classes, credit segments, exposure categories, credit limits, automatic checks, release authorities, and escalation rules. I separated policy decisions from system enforcement and defined audit evidence.
**Result:** Credit decisions became consistent, traceable, and aligned with Finance policy.
**SME Probe:** How would you distinguish credit policy from SAP configuration?
**Reflection:** I learned that credit architecture must translate financial risk policy into enforceable controls.

## 2. Credit Exposure Architecture
**Situation:** Finance could not explain why customer exposure differed from the expected balance.
**Task:** Establish a reliable exposure model.
**Action:** I mapped open receivables, sales commitments, relevant billing documents, and credit exposure categories, then reconciled them against Finance reporting.
**Result:** Finance gained a common view of customer exposure and exceptions.
**SME Probe:** What documents contribute to credit exposure?
**Reflection:** Credit exposure is a controlled financial data model, not simply an AR balance.

## 3. Credit Limit and Risk Classification
**Situation:** High-risk customers received limits similar to low-risk customers.
**Task:** Introduce differentiated credit governance.
**Action:** I defined risk categories, credit limits, review frequency, approval thresholds, and ownership. Changes above thresholds required documented Finance approval.
**Result:** Credit decisions became risk-based and auditable.
**SME Probe:** What evidence should support a credit-limit change?
**Reflection:** Credit limits should be governed by policy, evidence, and accountability.

## 4. Automatic Credit Check
**Situation:** Orders for financially risky customers were progressing too far before Finance intervention.
**Task:** Move credit control earlier in O2C.
**Action:** I identified appropriate control points and configured checks against credit exposure and customer risk. I designed clear block reasons and release responsibilities.
**Result:** Exceptions were detected earlier and manual intervention became more focused.
**SME Probe:** Where can credit checks be enforced in O2C?
**Reflection:** Preventive controls are generally more valuable than discovering exposure after billing.

## 5. Credit Block and Release Governance
**Situation:** Sales users frequently requested Finance to release blocked documents without sufficient evidence.
**Task:** Create controlled release governance.
**Action:** I established release roles, approval thresholds, reason codes, evidence requirements, escalation paths, and audit logging.
**Result:** Releases became consistent and defensible.
**SME Probe:** How would you prevent unauthorized release?
**Reflection:** A control is only effective when authorization and evidence are designed together.

## 6. Overdue Receivables and Aging
**Situation:** Management saw rising overdue AR but lacked prioritization.
**Task:** Create a Finance-led collections view.
**Action:** I segmented receivables by aging bucket, customer risk, amount, payment behavior, dispute status, and promise-to-pay status.
**Result:** Collectors could focus effort on material and high-risk exposures.
**SME Probe:** Which metrics would you monitor?
**Reflection:** Aging becomes actionable when combined with risk and collection context.

## 7. Dunning Strategy
**Situation:** Customers received inconsistent overdue-payment communications.
**Task:** Standardize dunning while preserving customer segmentation.
**Action:** I defined dunning levels, grace periods, correspondence rules, escalation paths, and exception handling in accordance with Finance policy.
**Result:** Collection activity became repeatable and measurable.
**SME Probe:** What should determine a dunning level?
**Reflection:** Dunning is a receivables control process, not merely automated correspondence.

## 8. Collection Work Prioritization
**Situation:** Collectors spent similar effort on low-value and high-risk accounts.
**Task:** Improve collection productivity.
**Action:** I designed worklists using overdue amount, risk, aging, payment behavior, dispute status, and strategic customer rules.
**Result:** Collector effort became more targeted.
**SME Probe:** How would you avoid optimizing only for amount?
**Reflection:** Collection prioritization must balance value, probability, risk, and customer context.

## 9. Dispute-Aware Collections
**Situation:** Collection teams repeatedly chased invoices already under legitimate dispute.
**Task:** Prevent inefficient collection activity.
**Action:** I connected dispute status with receivables worklists and defined ownership between Collections, AR, and the responsible business function.
**Result:** Unnecessary collection contacts decreased and unresolved disputes became more visible.
**SME Probe:** How do disputes affect collection prioritization?
**Reflection:** A receivable should be interpreted in business context before collection action.

## 10. Promise-to-Pay Control
**Situation:** Customers repeatedly missed promised payment dates.
**Task:** Improve visibility of collection commitments.
**Action:** I captured promise dates, amounts, ownership, follow-up status, and exception reasons and linked them to receivables monitoring.
**Result:** Broken promises became measurable collection exceptions.
**SME Probe:** What would you do with repeated broken promises?
**Reflection:** A promise-to-pay is useful only when it creates an accountable follow-up mechanism.

## 11. Customer Payment Behavior
**Situation:** Credit decisions relied heavily on static customer classifications.
**Task:** Incorporate actual payment behavior.
**Action:** I analyzed historical payment patterns, overdue frequency, average delay, disputes, and broken promises and proposed governed use of those signals in credit review.
**Result:** Credit review became more evidence-based.
**SME Probe:** How would you prevent historical data from creating unfair decisions?
**Reflection:** Behavioral data should inform governed decisions, not replace human accountability.

## 12. Receivables Controls and Reconciliation
**Situation:** Credit exposure and AR reporting showed unexplained differences.
**Task:** Establish control points between operational O2C and Finance.
**Action:** I defined reconciliation checks across customer master data, billing, AR postings, open items, credits, payments, and credit exposure.
**Result:** Exceptions became identifiable and traceable.
**SME Probe:** What is the difference between reconciliation and credit control?
**Reflection:** Credit control manages risk; reconciliation proves financial consistency.

## 13. Collections KPI Architecture
**Situation:** Leadership received collections reports but could not connect them to cash outcomes.
**Task:** Define Finance-relevant KPIs.
**Action:** I structured metrics such as DSO, overdue percentage, aging distribution, collection effectiveness, promise-to-pay adherence, dispute aging, and concentration risk.
**Result:** Collections discussions shifted toward measurable financial outcomes.
**SME Probe:** Why is DSO insufficient by itself?
**Reflection:** A KPI becomes useful when it explains both outcome and operational driver.

## 14. Credit Master Data Governance
**Situation:** Credit limits and customer risk data were changed without consistent governance.
**Task:** Strengthen master-data controls.
**Action:** I defined ownership, approval workflow, change reasons, segregation of duties, validity controls, and periodic review.
**Result:** Credit master changes became traceable and controlled.
**SME Probe:** What SoD risks exist?
**Reflection:** Master-data governance is part of financial control architecture.

## 15. Credit Migration
**Situation:** A Finance transformation required migration of customer credit data.
**Task:** Move credit limits, risk classifications, exposure-related data, and open receivables without compromising control.
**Action:** I defined mapping, cleansing, reconciliation, mock migration, approval, cutover validation, and rollback criteria.
**Result:** Credit data was migrated with measurable control evidence.
**SME Probe:** How would you validate migrated credit limits?
**Reflection:** Migration success means business control continuity, not merely technical load completion.

## 16. Credit Management Testing
**Situation:** Credit checks worked in normal scenarios but failed for edge cases.
**Task:** Build Finance-focused test coverage.
**Action:** I tested credit-limit breaches, partial payments, overdue items, blocked documents, releases, risk changes, currency scenarios, reversals, and authorization boundaries.
**Result:** High-risk credit-control defects were found before production.
**SME Probe:** What negative tests are essential?
**Reflection:** Financial controls require deliberate negative testing.

## 17. Collections Incident
**Situation:** A production change caused collection worklists to omit material overdue items.
**Task:** Restore reliable collections visibility.
**Action:** I assessed scope, reconciled worklists to AR, identified the control failure, applied a governed correction, and established monitoring.
**Result:** Collection visibility was restored with an evidence trail.
**SME Probe:** What would you check first?
**Reflection:** Production support must protect financial outcomes, not just system availability.

## 18. AI-Assisted Collections
**Situation:** Finance wanted to prioritize collection actions using AI.
**Task:** Introduce AI without weakening financial governance.
**Action:** I defined explainable signals, human approval points, data-quality requirements, privacy controls, monitoring, and exception handling. AI recommendations remained subject to Finance policy.
**Result:** AI could support prioritization while accountability remained with authorized Finance users.
**SME Probe:** What should never be delegated blindly to an AI agent?
**Reflection:** AI can augment collection decisions, but financial accountability and control ownership must remain explicit.

## 19. Finance Transformation
**Situation:** Collections were highly manual and reactive.
**Task:** Define a target-state receivables operating model.
**Action:** I connected credit policy, exposure monitoring, automated controls, dunning, collections worklists, dispute visibility, analytics, and governed AI assistance.
**Result:** The roadmap linked process improvement to measurable working-capital outcomes.
**SME Probe:** How would you sequence transformation?
**Reflection:** Transformation should progress from control visibility to automation and then intelligent decision support.

## 20. Trusted Finance Advisor Scenario
**Situation:** Business leaders wanted higher sales velocity while Finance wanted tighter credit controls.
**Task:** Facilitate a decision balancing growth and receivables risk.
**Action:** I quantified exposure scenarios, defined risk thresholds, proposed differentiated controls, clarified exception authority, and presented trade-offs using Finance KPIs.
**Result:** Stakeholders could make an evidence-based decision with explicit risk ownership.
**SME Probe:** How do you handle a stakeholder who rejects Finance controls?
**Reflection:** A Finance architect creates decision transparency rather than simply saying yes or no.

# Rapid-Fire Finance Questions

1. What is credit exposure?
2. What is the purpose of a credit limit?
3. What is a risk class?
4. Why perform automatic credit checks?
5. What is a credit block?
6. Who should release a credit block?
7. What is AR aging?
8. What is dunning?
9. What is DSO?
10. What is a promise to pay?
11. How do disputes affect collections?
12. Why reconcile AR?
13. What is credit master-data governance?
14. What SoD risk exists in credit-limit maintenance?
15. What should be tested after a credit-control change?
16. How would you migrate credit data?
17. How can payment behavior support credit decisions?
18. What KPIs measure collections?
19. How can AI support collections?
20. What makes credit architecture Finance-led?

# Mastery Framework — CREDIT-FI

**C — Classify Risk** → **R — Review Exposure** → **E — Enforce Credit Controls** → **D — Drive Collections** → **I — Investigate Exceptions** → **T — Track Cash Outcomes** → **F — Finance Governance** → **I — Improve Continuously**

Use it in interviews to structure answers from customer risk through receivables outcome and transformation.

# Anti-Patterns to Avoid

- Treating credit limits as static master data with no governance.
- Explaining credit only from a Sales perspective.
- Confusing AR balance with total credit exposure.
- Releasing blocks without evidence and authorization.
- Treating dunning as only a correspondence function.
- Measuring collections only by invoice count.
- Ignoring disputes when prioritizing collections.
- Migrating credit data without reconciliation.
- Testing only happy paths.
- Introducing AI without explainability, human oversight, and Finance controls.

# Interview Evidence Bank

Prepare one real example for each:
- Complex credit requirement
- Credit exposure reconciliation
- Credit-limit governance
- Automated credit check
- Credit-block release
- Dunning improvement
- Collections prioritization
- Dispute-aware collections
- Payment-behavior analysis
- Credit-data migration
- Production credit incident
- Finance AI use case

For every example, quantify at least one outcome: overdue reduction, DSO movement, collection productivity, exception reduction, control coverage, reconciliation accuracy, or cycle-time improvement.

# Success Criteria

You are interview-ready when you can:
- Explain credit architecture from Finance policy to SAP execution.
- Design preventive and detective receivables controls.
- Explain credit exposure and reconciliation logically.
- Handle credit, collections, disputes, and dunning scenarios.
- Design migration and testing for credit controls.
- Discuss AI in collections without weakening governance.
- Connect O2C credit management to cash, working capital, risk, and business value.

## Final BAISI PAHACHA Mantra

**Know the Finance risk → Design the control → Configure the decision point → Integrate the evidence → Test the exception → Operate the receivable → Explain the trade-off → Transform cash outcomes.**
