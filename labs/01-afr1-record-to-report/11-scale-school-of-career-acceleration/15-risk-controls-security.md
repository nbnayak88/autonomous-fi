# 15 — Risk, Controls & Security

## Course
**Applied SAP S/4HANA Finance — AFR1 Record to Report**

- **Stream:** Enterprise Architect
- **Lab:** 11 — Scale | School of Career Acceleration
- **Theme:** SOLVE
- **Pahacha:** @baisi pahacha — Step 15: Risk, Controls & Security
- **Purpose:** Design Finance solutions where risk, internal control, security, privacy, compliance, and business continuity are architectural capabilities rather than after-the-fact checks.

## Mastery Objective

A Finance architect must answer more than:

> “Can the process work?”

The deeper questions are:

- Can it work **safely**?
- Can it work **with appropriate segregation of duties**?
- Can the enterprise prove what happened?
- Can sensitive financial data be protected?
- Can controls operate without creating unnecessary friction?
- Can automated and AI-driven decisions be governed?
- Can the business continue when a dependency fails?

The architecture mindset is:

**Risk → Control Objective → Control Design → Enforcement → Evidence → Monitoring → Improvement.**

---

# 20 Scenario-Based Interview Questions

## 1. Audit identifies excessive access

**Question:** Finance users have broader access than their roles require. What would you do?

**S — Situation:** An access review identified excessive Finance privileges across several users.

**T — Task:** I needed to reduce access risk without disrupting legitimate business operations.

**A — Action:** I mapped business responsibilities to required capabilities, analyzed role and authorization assignments, identified toxic combinations and excessive privileges, validated access with business owners, and introduced least-privilege remediation with periodic review.

**R — Result:** Access became aligned with job responsibilities while critical Finance processes remained operational.

**SME Probe:** Why is least privilege a business control rather than only an IT control?

**Reflection:** Access determines which financial actions a person can initiate or influence.

---

## 2. Segregation of duties conflict

**Question:** A user needs two roles that create an SoD conflict. How do you handle it?

**S:** A Finance specialist required access to two activities that created a potential conflict.

**T:** I needed to support the business need without weakening the control environment.

**A:** I validated the actual business process, assessed the risk and compensating controls, explored alternative role design, and documented an approved exception only if unavoidable.

**R:** The business requirement could be addressed with explicit risk ownership and control evidence.

**SME Probe:** Why should an SoD conflict not automatically be treated as a technical defect?

**Reflection:** SoD is fundamentally about business risk.

---

## 3. Manual journal approval control

**Question:** How would you design controls around manual journals?

**S:** Audit highlighted the financial risk associated with manual journal entries.

**T:** I needed to preserve legitimate adjustments while reducing error and fraud exposure.

**A:** I classified journal types, thresholds, preparer/approver separation, supporting evidence, recurring patterns, unusual entries, posting windows, and monitoring requirements. I designed workflow and analytics around risk rather than applying identical controls to every journal.

**R:** Journal governance became risk-based and auditable.

**SME Probe:** Why are value thresholds useful but insufficient?

**Reflection:** A low-value unusual transaction can still be a high-risk event.

---

## 4. Finance data contains sensitive information

**Question:** How do you protect sensitive Finance data?

**S:** Financial reporting and operational data included commercially sensitive information.

**T:** I needed to protect confidentiality while preserving legitimate analytical access.

**A:** I classified data, defined ownership, applied least-privilege access, encryption, secure integration, retention controls, monitoring, masking where appropriate, and governed analytical copies.

**R:** Sensitive information could be used without unnecessary exposure.

**SME Probe:** Why is data classification an architectural activity?

**Reflection:** Protection requirements depend on what the data represents and how it is used.

---

## 5. Auditor asks, “Who changed this?”

**Question:** How would you design auditability for Finance?

**S:** An auditor needed to reconstruct the history of a financial change.

**T:** I needed to provide reliable evidence of who, what, when, why, and through which process the change occurred.

**A:** I identified critical transactions and master data, defined audit logging requirements, retained relevant timestamps and identities, protected logs from unauthorized modification, and connected evidence across systems.

**R:** The enterprise could reconstruct material financial events with traceable evidence.

**SME Probe:** What is the difference between logging and auditability?

**Reflection:** Auditability requires meaningful evidence, not simply more logs.

---

## 6. Privileged support access

**Question:** Production support needs emergency Finance access. What controls would you implement?

**S:** A critical incident required elevated access to production.

**T:** I needed to enable resolution while maintaining accountability.

**A:** I used controlled emergency access with approval, time limitation, activity logging, reason capture, post-use review, and separation between incident resolution and audit review.

**R:** The incident could be resolved without creating unmanaged privileged access.

**SME Probe:** Why is permanent administrator access inappropriate for support convenience?

**Reflection:** Emergency access should be exceptional, temporary, and observable.

---

## 7. Payment and journal duties overlap

**Question:** A user can prepare and approve a sensitive financial transaction. What would you do?

**S:** A role design allowed incompatible financial activities.

**T:** I needed to reduce fraud and error risk.

**A:** I mapped the end-to-end process, identified conflicting activities, separated responsibilities, reviewed workflow approvals, and introduced compensating controls where organizational constraints prevented complete separation.

**R:** Critical financial duties were separated or explicitly controlled.

**SME Probe:** How do you identify the highest-risk SoD conflicts?

**Reflection:** Focus first on combinations that can create unauthorized financial outcomes.

---

## 8. Control is slowing the business

**Question:** Business says controls are causing unacceptable delays. How do you respond?

**S:** A Finance approval control created significant processing delays.

**T:** I needed to preserve the control objective while improving process efficiency.

**A:** I clarified the control objective, analyzed risk and exception patterns, evaluated automation, risk-based thresholds, straight-through processing for low-risk transactions, and stronger controls for exceptions.

**R:** The control could become more efficient without simply being removed.

**SME Probe:** What is the difference between removing a control and redesigning it?

**Reflection:** Good control architecture manages risk with minimal unnecessary friction.

---

## 9. AI agent can initiate Finance actions

**Question:** How would you secure an AI agent capable of initiating Finance activities?

**S:** A Finance AI agent was proposed to execute selected operational actions.

**T:** I needed to establish safe autonomy.

**A:** I defined identity, authorization boundaries, action policies, approval thresholds, human escalation, explainability, audit logs, tool permissions, data access, monitoring, rollback, and exception handling.

**R:** AI autonomy became bounded and observable rather than unrestricted.

**SME Probe:** Should an AI agent inherit a human user's full permissions?

**Reflection:** Agent identity and authorization should be explicitly governed.

---

## 10. Fraud analytics identifies an anomaly

**Question:** An analytics model flags a potentially fraudulent transaction. What happens next?

**S:** An anomaly-detection system identified unusual Finance activity.

**T:** I needed to investigate without automatically accusing or blocking legitimate business activity.

**A:** I assessed confidence, transaction context, historical behavior, supporting evidence, risk thresholds, human review, and potential false positives. I ensured the investigation remained controlled and documented.

**R:** The anomaly became an evidence-based investigation rather than an automatic conclusion.

**SME Probe:** Why should anomaly detection not equal automatic fraud determination?

**Reflection:** Detection creates a signal; governance determines the response.

---

## 11. Regulatory requirement changes

**Question:** A new regulation changes Finance reporting requirements. How would you architect the response?

**S:** A regulatory change affected Finance data and reporting.

**T:** I needed to implement compliance without uncontrolled local modifications.

**A:** I translated the regulation into control and data requirements, identified affected processes and systems, assessed gaps, designed the required changes, established evidence requirements, and created a controlled release and validation plan.

**R:** Compliance became traceable from regulation to implementation and evidence.

**SME Probe:** Why should regulatory change management be treated as an architecture capability?

**Reflection:** Regulations change the enterprise operating model, not just a report.

---

## 12. Business continuity during ERP outage

**Question:** S/4HANA becomes unavailable during close. What is your approach?

**S:** A critical Finance platform outage occurred during a close window.

**T:** I needed to preserve business continuity and financial integrity.

**A:** I activated the appropriate continuity plan, established affected capabilities, prioritized critical processes, protected data consistency, coordinated recovery, communicated status, and performed reconciliation after restoration.

**R:** Business continuity was managed as a controlled recovery process rather than ad-hoc manual activity.

**SME Probe:** Why should business continuity include reconciliation?

**Reflection:** Recovery is incomplete until financial state is proven consistent.

---

## 13. Third-party integration introduces security risk

**Question:** A tax or banking provider requires integration with Finance. What security architecture would you apply?

**S:** A third-party service needed access to Finance data and transactions.

**T:** I needed to enable integration while limiting exposure.

**A:** I defined data minimization, authentication, authorization, encryption, API security, network controls, credential management, monitoring, error handling, and vendor responsibilities. I separated inbound and outbound trust boundaries.

**R:** The integration could operate with explicit security boundaries.

**SME Probe:** Why is “trusted vendor” not a sufficient security control?

**Reflection:** Trust must be implemented as verifiable technical and contractual controls.

---

## 14. Financial data leaves the ERP

**Question:** Finance data is replicated into an analytics platform. What risks do you assess?

**S:** Financial data was copied into an enterprise analytics environment.

**T:** I needed to ensure the analytical copy remained governed.

**A:** I assessed purpose, data classification, lineage, access, retention, masking, replication frequency, reconciliation, downstream sharing, and deletion requirements.

**R:** Analytical use could continue with controlled data exposure.

**SME Probe:** What happens to governance when data leaves the source system?

**Reflection:** Governance must follow the data.

---

## 15. Control failure is discovered after posting

**Question:** A key Finance control failed and transactions were already posted. What would you do?

**S:** A control exception was discovered after financial transactions had processed.

**T:** I needed to assess impact and restore control effectiveness.

**A:** I stopped or contained further exposure where appropriate, identified the affected population, preserved evidence, quantified financial impact, performed reconciliation, corrected the control, and established remediation and monitoring.

**R:** The organization could address both immediate impact and systemic control failure.

**SME Probe:** Why should the affected population be established before mass correction?

**Reflection:** Control remediation must be evidence-driven.

---

## 16. Security and performance conflict

**Question:** Strong encryption and monitoring are affecting Finance performance. What do you do?

**S:** Security controls introduced measurable latency into a critical process.

**T:** I needed to maintain the required security posture while meeting business performance requirements.

**A:** I quantified the performance impact, identified the specific security mechanisms involved, assessed risk requirements, optimized implementation, evaluated architecture alternatives, and validated both security and performance.

**R:** The organization could balance protection and operational performance based on evidence.

**SME Probe:** Why should security not simply be disabled to solve performance?

**Reflection:** Security is a design constraint, not a toggle.

---

## 17. Access review becomes a checkbox

**Question:** Quarterly access reviews are completed but risks remain. What would you change?

**S:** Managers approved access reviews without meaningful analysis.

**T:** I needed to make access governance effective rather than procedural.

**A:** I introduced risk-based review, high-risk privilege focus, automated evidence, exception tracking, ownership accountability, SoD analysis, and trend monitoring.

**R:** Access governance shifted from completion metrics toward actual risk reduction.

**SME Probe:** What metric would you use beyond “100% reviewed”?

**Reflection:** Control completion is not the same as control effectiveness.

---

## 18. AI model changes its behavior

**Question:** An AI model that supported Finance decisions begins producing different recommendations after an update. How do you manage the risk?

**S:** AI-assisted recommendations changed unexpectedly after a model or data update.

**T:** I needed to determine whether the change was acceptable and controlled.

**A:** I compared model/version metadata, input distributions, prompts or retrieval context, outputs, thresholds, business rules, validation datasets, and approval status. I established rollback or human-review controls if required.

**R:** Model change became governed as a production change rather than treated as an invisible technical event.

**SME Probe:** Why does model drift belong in Finance governance?

**Reflection:** A changing decision engine can change financial outcomes.

---

## 19. Security incident affects Finance

**Question:** A security incident may have exposed Finance data. What would you do?

**S:** Security monitoring identified possible unauthorized access to financial information.

**T:** I needed to contain exposure, preserve evidence, and support incident response.

**A:** I coordinated with security and incident-response teams, identified affected identities and data, preserved logs, restricted compromised access, assessed downstream impact, maintained required communications, and supported recovery and post-incident controls.

**R:** The incident was handled through a controlled response process rather than independent Finance actions.

**SME Probe:** Why should Finance not investigate a cyber incident alone?

**Reflection:** Security incidents cross technical, legal, operational, and governance boundaries.

---

## 20. Architect enterprise Finance risk

**Question:** How would you build a risk and control architecture for Finance?

**S:** The organization managed controls by individual applications with limited enterprise visibility.

**T:** I needed to create a coherent Finance risk and control model.

**A:** I mapped business objectives to risks, controls, systems, data, identities, processes, evidence, monitoring, and owners. I classified preventive, detective, corrective, and compensating controls and connected them to continuous monitoring.

**R:** Finance gained an enterprise control architecture with clearer accountability and measurable control effectiveness.

**SME Probe:** What makes a control architecture scalable?

**Reflection:** Risk should be modeled once and enforced consistently across the value stream.

---

# Rapid-Fire Questions

1. What is a risk?
2. What is a control objective?
3. Preventive versus detective control?
4. What is compensating control?
5. What is least privilege?
6. What is segregation of duties?
7. Why is SoD a business issue?
8. What is privileged access?
9. What makes audit evidence reliable?
10. Why is data classification important?
11. What is defense in depth?
12. Why should controls be risk-based?
13. What is continuous control monitoring?
14. How do you secure APIs?
15. How do you govern third-party access?
16. How do you secure AI agents?
17. What is human-in-the-loop governance?
18. Why should recovery include reconciliation?
19. How do you measure control effectiveness?
20. What is the architect's role in Finance security?

---

# Mastery Framework — SHIELD

Use this 7-step method for risk, controls, and security scenarios:

### 1. SCOPE
Identify business assets, processes, data, identities, systems, and affected populations.

### 2. HAZARD
Identify threats, vulnerabilities, failure modes, regulatory obligations, and business consequences.

### 3. IDENTIFY
Define the risk and the specific control objective.

### 4. ENGINEER
Design preventive, detective, corrective, and compensating controls.

### 5. LIMIT
Apply least privilege, segmentation, thresholds, approvals, resilience, and containment.

### 6. DEMONSTRATE
Create reliable evidence, monitoring, auditability, and control-effectiveness measures.

### 7. LEARN
Review incidents, exceptions, control failures, and changing threats to improve the architecture.

**Memory line:**

> **Scope → Hazard → Identify → Engineer → Limit → Demonstrate → Learn**

---

# Common Anti-Patterns

- Treating security as a post-implementation activity.
- Giving broad access because it is convenient.
- Treating SoD as an IT-only problem.
- Designing controls without understanding the business risk.
- Using approval as the default solution for every risk.
- Assuming logs automatically provide auditability.
- Ignoring data after it leaves the ERP.
- Giving AI agents human-equivalent privileges.
- Treating anomaly detection as proof of fraud.
- Disabling security controls to improve performance.
- Treating compliance as a reporting-only concern.
- Ignoring third-party trust boundaries.
- Using manual workarounds during outages without reconciliation.
- Measuring control completion instead of effectiveness.
- Failing to update controls when architecture changes.

---

# Interview Evidence Bank

Prepare STAR stories for:

1. Excessive Finance access.
2. SoD conflict.
3. Manual journal controls.
4. Sensitive Finance data protection.
5. Audit-trail design.
6. Emergency privileged access.
7. Separation of financial duties.
8. Control-efficiency redesign.
9. AI-agent security.
10. Fraud/anomaly investigation.
11. Regulatory change.
12. Finance business continuity.
13. Third-party integration security.
14. Analytics data governance.
15. Control failure after posting.
16. Security-performance trade-off.
17. Access-review transformation.
18. AI/model-change governance.
19. Finance security incident.
20. Enterprise Finance control architecture.

For each story, articulate:

**Asset → Risk → Control Objective → Control → Evidence → Monitoring → Exception → Outcome.**

---

# Success Criteria

You have mastered Step 15 when you can:

- Identify Finance risks across business and technology layers.
- Translate risks into control objectives.
- Design preventive, detective, corrective, and compensating controls.
- Apply least privilege and segregation of duties.
- Design secure Finance integrations.
- Protect sensitive financial information.
- Create meaningful audit evidence.
- Govern privileged access.
- Design business continuity and recovery controls.
- Secure AI-assisted and agentic Finance.
- Handle anomalies without premature conclusions.
- Translate regulatory requirements into architecture.
- Measure control effectiveness.
- Design continuous control monitoring.
- Convert incidents into stronger enterprise controls.

---

# Final Interview Mantra

> **“I design Finance architecture so that risk is understood before controls are selected. I translate business risks into explicit control objectives, enforce least privilege and segregation of duties, protect data and integrations, create reliable evidence, monitor control effectiveness, and continuously improve the control environment.”**

## Architecture Lens

Assess every Finance design across:

**Business Risk → Process Control → Identity → Data → Application → Integration → Infrastructure → Security → Compliance → Resilience → AI Governance → Auditability.**

The architect does not ask only:

**“Can we make this work?”**

The architect asks:

**“Can we make this work safely, prove that it worked correctly, recover when it does not, and continuously reduce the risk of failure?”**
