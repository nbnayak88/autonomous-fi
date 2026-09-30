# BAISI PAHACHA™ — Stakeholder Requirement Conflict

## Purpose
Master SAP S/4HANA Finance interview scenarios where Finance, business, IT, audit, security, tax, operations, and transformation stakeholders disagree on requirements, priorities, scope, design, controls, or delivery decisions.

## Interview Mastery Objective
Move from **“I resolve stakeholder disagreements”** to **“I turn conflicting requirements into governed Finance decisions.”**

---

## 20 Scenario-Based Interview Questions

### 1. Business Wants a Custom Finance Process; Architecture Wants Standard SAP
**Question:** A business leader insists on a custom Finance process while the architecture team wants standard S/4HANA. How do you handle the conflict?

**Situation:** Business preference and clean-core architecture are misaligned.
**Task:** Reach a decision that satisfies the business outcome without unnecessary technical debt.
**Action:** Clarify the underlying business requirement; separate outcome from requested solution; assess standard SAP capability, configuration, extensibility, integration, control, cost, lifecycle, and regulatory implications; present options with trade-offs and obtain governed decision approval.
**Result:** The organization selects an evidence-based solution aligned to business value and architectural principles.
**SME Probe:** When is an extension justified?
**Reflection:** Stakeholder conflict often disappears when the conversation moves from solutions to outcomes.

### 2. Finance Wants Speed; Internal Audit Wants More Controls
**Question:** Finance wants a faster journal process, while audit demands additional approval controls. What would you do?

**Situation:** Operational efficiency and control requirements conflict.
**Task:** Design a process that improves speed without weakening financial governance.
**Action:** Identify control objectives; map approval risk; segment low-risk and high-risk journals; consider workflow, thresholds, segregation of duties, automated validations, exception routing, and audit evidence.
**Result:** Routine journals can move faster while material or risky transactions retain stronger controls.
**SME Probe:** How would you avoid applying the same control intensity to every journal?
**Reflection:** Good architecture applies controls proportionately to risk.

### 3. Global Template Versus Local Finance Requirement
**Question:** A country Finance team rejects the global template because of local requirements. How do you resolve it?

**Situation:** Global standardization conflicts with a legitimate local requirement.
**Task:** Determine whether the local deviation is necessary and architecturally sustainable.
**Action:** Clarify statutory/business need; distinguish mandatory local requirement from preference; assess standard functionality, configuration, localization, extension, data, reporting, and support impact; document the exception through governance.
**Result:** A justified local variation is either incorporated or rejected with evidence.
**SME Probe:** What makes a local exception legitimate?
**Reflection:** “Local requirement” should be demonstrated, not assumed.

### 4. CFO Wants a Dashboard Immediately; Data Is Not Trusted
**Question:** The CFO demands a Finance dashboard, but Finance data quality is poor. What do you recommend?

**Situation:** Executive demand for visibility conflicts with unreliable source data.
**Task:** Provide useful insight without creating false confidence.
**Action:** Identify critical KPIs and data-quality gaps; establish trusted metrics and reconciliation controls; deliver a controlled minimum viable dashboard while building the underlying data-quality capability.
**Result:** Leadership receives transparent insight with documented limitations and a path to stronger data trust.
**SME Probe:** Would you ever publish a dashboard with known data limitations?
**Reflection:** Transparency about data confidence is better than false precision.

### 5. Business Wants a Manual Workaround
**Question:** A business stakeholder asks for a manual workaround instead of fixing the SAP process. How do you respond?

**Situation:** A manual solution appears faster than system remediation.
**Task:** Protect continuity without creating permanent operational risk.
**Action:** Quantify frequency, effort, financial risk, control implications, auditability, and lifecycle cost; allow a controlled temporary workaround where justified; define owner, reconciliation, expiry, and permanent remediation.
**Result:** Continuity is protected while technical debt remains visible and governed.
**SME Probe:** When is a workaround acceptable?
**Reflection:** Temporary solutions need an exit strategy.

### 6. Finance and Tax Disagree on Transaction Design
**Question:** Finance wants a simple posting model, while Tax requires more detailed transaction attributes. What do you do?

**Situation:** Accounting simplicity conflicts with tax reporting requirements.
**Task:** Preserve both financial integrity and tax compliance.
**Action:** Identify tax data requirements; assess whether required attributes can be derived or captured upstream; design master-data and transaction rules; validate tax accounting, statutory reporting, and reconciliation.
**Result:** Tax requirements are embedded without unnecessary manual Finance effort.
**SME Probe:** Where should tax-specific data ideally originate?
**Reflection:** Capture information at the earliest reliable point in the value stream.

### 7. Treasury Wants Real-Time Integration; Security Restricts Connectivity
**Question:** Treasury demands real-time bank connectivity, but security rejects the proposed integration. How do you resolve the issue?

**Situation:** Business responsiveness conflicts with security requirements.
**Task:** Find an integration pattern that satisfies both objectives.
**Action:** Clarify required data and latency; identify security constraints; evaluate approved connectivity, encryption, authentication, API gateways, network controls, monitoring, and least privilege; compare architecture options.
**Result:** A secure integration pattern meets the required business service level.
**SME Probe:** How do you avoid treating security as a late-stage approval?
**Reflection:** Security constraints belong in architecture from the beginning.

### 8. Business Wants a Report; Architect Wants a Data Product
**Question:** A Finance team requests a one-off report, while the data team proposes a governed semantic model. How do you decide?

**Situation:** Immediate reporting need conflicts with reusable data architecture.
**Task:** Meet the immediate need while avoiding uncontrolled reporting duplication.
**Action:** Understand the business question; assess recurrence, criticality, data lineage, KPI reuse, governance, and lifecycle; provide a tactical report where appropriate while designing a reusable governed model for strategic needs.
**Result:** Immediate business value is delivered without losing architectural direction.
**SME Probe:** When should a report become a governed data product?
**Reflection:** Reuse and governance should follow business value, not architecture for its own sake.

### 9. Finance Wants More Fields; Users Want Simplicity
**Question:** Finance asks for many additional mandatory fields, but business users complain about transaction complexity. What would you do?

**Situation:** Data completeness conflicts with user experience.
**Task:** Capture required information with minimum operational friction.
**Action:** Classify fields by statutory, control, reporting, and optional needs; use derivation/defaulting where reliable; apply conditional mandatory logic; eliminate unnecessary fields; validate user experience.
**Result:** Required financial data is captured while transaction effort is reduced.
**SME Probe:** Which fields should never be made mandatory without a clear reason?
**Reflection:** Good UX is a control-enabler, not the opposite of control.

### 10. Two Business Units Demand Different Chart-of-Accounts Structures
**Question:** Two business units insist on separate account structures. How would you handle the conflict?

**Situation:** Local reporting preferences conflict with enterprise financial harmonization.
**Task:** Determine the minimum common structure required for enterprise reporting.
**Action:** Identify statutory, management, consolidation, and operational requirements; evaluate common chart-of-accounts design, local mapping, account groups, reporting dimensions, and governance; quantify impact of fragmentation.
**Result:** Enterprise consistency is achieved where necessary while legitimate local reporting needs remain supported.
**SME Probe:** Why is account harmonization strategically important?
**Reflection:** Standardization should serve reporting and control outcomes.

### 11. Finance Wants an Immediate Production Fix; Change Management Says Wait
**Question:** A Finance defect is blocking operations, but normal change management cannot deliver quickly enough. What do you do?

**Situation:** Operational urgency conflicts with controlled release governance.
**Task:** Restore service without bypassing change controls.
**Action:** Assess severity and financial impact; invoke the approved emergency-change process if criteria are met; define approvals, testing, implementation, rollback, monitoring, and post-implementation review.
**Result:** Business continuity is restored through controlled emergency change.
**SME Probe:** What distinguishes a true emergency from poor planning?
**Reflection:** Emergency governance is a controlled path, not an absence of governance.

### 12. Finance Wants AI Automation; Audit Wants Human Review
**Question:** Finance proposes AI-generated journal recommendations, but audit requires human approval. How do you design the solution?

**Situation:** Automation ambition conflicts with control requirements.
**Task:** Capture AI productivity while maintaining accountability.
**Action:** Define eligible transaction classes; establish confidence thresholds, explainability, approval workflow, segregation of duties, audit logging, exception handling, and human-in-the-loop controls.
**Result:** AI assists Finance without making uncontrolled accounting decisions.
**SME Probe:** Which AI decisions would you keep human-approved?
**Reflection:** Automation maturity should increase with control maturity.

### 13. Project Manager Wants to Remove Testing to Meet the Date
**Question:** The project is late and proposes reducing Finance testing. How do you respond?

**Situation:** Schedule pressure threatens assurance.
**Task:** Protect critical financial and control coverage while managing the timeline.
**Action:** Perform risk-based test prioritization; identify mandatory regulatory, financial, integration, migration, and control tests; remove only demonstrably low-risk duplication; document residual risk and obtain accountable acceptance.
**Result:** The schedule is optimized without silently removing critical assurance.
**SME Probe:** Who should accept residual Finance risk?
**Reflection:** Schedule compression should be risk-based, not arbitrary.

### 14. Business and IT Disagree on Root Cause
**Question:** Finance says a process is broken, while IT says the system is working as designed. How do you mediate?

**Situation:** Business outcome and technical behavior appear contradictory.
**Task:** Establish objective evidence and identify the real gap.
**Action:** Reproduce the scenario; compare requirement, expected behavior, configuration, master data, transaction, and accounting result; determine whether the issue is defect, design gap, data problem, training, or expectation mismatch.
**Result:** The disagreement becomes an evidence-based decision rather than an ownership dispute.
**SME Probe:** What is your first artifact in such a conflict?
**Reflection:** Reproduction and evidence turn opinion into analysis.

### 15. Shared Services Wants Standardization; Business Units Want Autonomy
**Question:** How would you resolve a conflict between centralized Finance operations and business-unit autonomy?

**Situation:** Shared services seeks standard processes while business units resist centralized control.
**Task:** Define which capabilities should be standardized and where variation is justified.
**Action:** Classify processes into global standards, configurable local variants, and genuinely local capabilities; define service levels, governance, decision rights, exception processes, and KPIs.
**Result:** Operating-model boundaries become explicit.
**SME Probe:** What should determine whether a process is centralized?
**Reflection:** Operating-model design should follow capability and value, not organizational politics.

### 16. Finance Wants Scope Added Mid-Project
**Question:** A senior stakeholder introduces a major Finance requirement late in the program. How do you handle it?

**Situation:** A late requirement threatens scope, cost, and timeline.
**Task:** Evaluate it objectively without dismissing business needs.
**Action:** Clarify requirement and business value; assess regulatory urgency, dependency, architecture impact, effort, testing, migration, controls, and timeline; present options such as include, defer, phase, or workaround through formal governance.
**Result:** The decision is transparent and consequences are understood.
**SME Probe:** What makes a late requirement mandatory?
**Reflection:** Scope decisions should be evidence-driven.

### 17. Vendor Recommendation Conflicts with Enterprise Architecture
**Question:** A software vendor recommends an approach that conflicts with the enterprise integration strategy. What would you do?

**Situation:** Vendor optimization and enterprise architecture principles differ.
**Task:** Determine whether the vendor approach creates unacceptable long-term dependency.
**Action:** Assess standards, APIs, integration patterns, data ownership, security, extensibility, operational model, exit implications, total cost, and business value; require evidence rather than accepting vendor preference.
**Result:** The organization selects an architecture based on enterprise requirements.
**SME Probe:** How do you avoid vendor bias?
**Reflection:** Vendors provide options; architecture governance protects enterprise interests.

### 18. Finance, Security and UX Have Conflicting Priorities
**Question:** A new Finance application must be highly secure but also easy for users. How do you balance the requirements?

**Situation:** Security, control, and user experience appear to compete.
**Task:** Design a secure and usable process.
**Action:** Apply risk-based authentication and authorization; simplify screens and workflows; use role-based access, conditional controls, defaults, workflow, and automation; test both usability and security outcomes.
**Result:** Security controls are integrated into an efficient user experience.
**SME Probe:** What is “secure by design” in a Finance application?
**Reflection:** Strong controls should be experienced as safe workflows, not unnecessary friction.

### 19. Executive Stakeholders Disagree on Finance Transformation Priorities
**Question:** CFO, CIO, and business leaders each want different Finance transformation outcomes. How do you facilitate alignment?

**Situation:** Leadership has competing priorities around cost, control, speed, data, and experience.
**Task:** Establish a common transformation decision framework.
**Action:** Translate each priority into measurable business outcomes; map capabilities, value streams, dependencies, risks, investment, and sequencing; facilitate trade-off discussion using agreed criteria and architecture principles.
**Result:** Leadership can make explicit choices with understood consequences.
**SME Probe:** What should be common across competing executive priorities?
**Reflection:** Architects create decision clarity; executives own the final business trade-offs.

### 20. Architecting a Finance Decision Governance Model
**Question:** How would you design governance for recurring Finance requirement conflicts?

**Situation:** The organization repeatedly faces disagreements across Finance, business, IT, security, tax, audit, and architecture.
**Task:** Create a repeatable decision mechanism.
**Action:** Establish decision rights, requirement taxonomy, architecture principles, risk criteria, value assessment, control objectives, exception governance, decision records, escalation paths, and review cadence; maintain an evidence-based decision log.
**Result:** Conflicts become structured architecture decisions rather than recurring stakeholder friction.
**SME Probe:** What should a Finance architecture decision record contain?
**Reflection:** Mature governance does not eliminate disagreement; it makes disagreement productive and traceable.

---

## Rapid-Fire Questions

1. How do you handle conflicting Finance requirements?
2. What is the difference between a requirement and a proposed solution?
3. How do you resolve global versus local requirements?
4. When is a custom extension justified?
5. How do you balance speed and control?
6. What is risk-based decision making?
7. How do you handle late scope?
8. Who should accept residual risk?
9. How do you mediate business versus IT disagreement?
10. How do you evaluate vendor recommendations?
11. What is a decision record?
12. Why are architecture principles useful?
13. How do you balance UX and security?
14. How do you govern exceptions?
15. What makes a requirement regulatory?
16. How do you handle emergency changes?
17. What is stakeholder alignment?
18. How do you prioritize executive demands?
19. Why should trade-offs be explicit?
20. What makes Finance governance effective?

---

## ALIGN-FI Mastery Framework

**1. LISTEN** — Listen for the business outcome behind every stakeholder position.  
**2. FRAME** — Frame the requirement, constraints, risks, dependencies, and decision context.  
**3. EVIDENCE** — Establish facts through process, data, architecture, financial, control, and regulatory evidence.  
**4. OPTIONS** — Develop viable options with clear trade-offs, assumptions, and consequences.  
**5. ALIGN** — Facilitate stakeholder alignment around outcomes, principles, and risk.  
**6. DECIDE** — Record the accountable decision, rationale, exceptions, and residual risk.  
**7. GOVERN** — Monitor the decision and revisit it when assumptions or business conditions change.

### BAISI PAHACHA™ Alignment

- **KNOW:** Understand stakeholder objectives, Finance processes, constraints, and governance.
- **DESIGN:** Convert competing requirements into solution options.
- **DELIVER:** Implement decisions with traceability.
- **SOLVE:** Resolve conflicts through evidence and root-cause analysis.
- **INFLUENCE:** Facilitate decision-making without taking ownership away from accountable stakeholders.
- **TRANSFORM:** Build a culture of explicit, repeatable, architecture-led decisions.

---

## Anti-Patterns to Avoid

- Treating the loudest stakeholder as the decision maker.
- Confusing a stakeholder's requested solution with the actual requirement.
- Saying “SAP cannot do it” without evidence.
- Saying “business requires it” without validating the requirement.
- Using architecture principles as a reason to ignore business outcomes.
- Removing controls simply to accelerate delivery.
- Rejecting local requirements without regulatory analysis.
- Accepting customizations without lifecycle and total-cost analysis.
- Allowing unresolved conflicts to remain undocumented.
- Making decisions without recording assumptions and residual risk.
- Escalating every disagreement instead of facilitating structured resolution.

---

## Interview Evidence Bank

Prepare real examples demonstrating:

- Global versus local Finance requirement conflict.
- Standard SAP versus customization decision.
- Finance versus audit/control conflict.
- Finance versus security conflict.
- Tax versus Finance requirement conflict.
- Late-scope Finance requirement.
- Emergency production decision.
- AI automation versus human-control discussion.
- Business versus IT root-cause disagreement.
- Executive-level transformation prioritization.
- Vendor recommendation versus enterprise architecture.
- A governance mechanism you created or improved.

---

## Success Criteria

You are interview-ready when you can:

- Separate business outcomes from proposed technical solutions.
- Facilitate Finance stakeholder conflicts objectively.
- Translate competing requirements into architecture options.
- Quantify trade-offs across value, risk, cost, control, and time.
- Handle global/local Finance requirements.
- Balance standardization and justified exceptions.
- Protect financial controls under schedule pressure.
- Explain how security, UX, tax, audit, and Finance requirements interact.
- Create traceable architecture decisions.
- Establish governance that turns recurring conflict into structured decision-making.

---

## Final BAISI PAHACHA™ Mantra

> **Do not try to win the stakeholder conflict. Architect a decision that everyone can understand, govern, and own.**

**Listen to the outcome → frame the conflict → establish evidence → create options → align the stakeholders → record the decision → govern the consequence.**
