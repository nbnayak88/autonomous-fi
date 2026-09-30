# BAISI PAHACHA™ — APT2 #09 P2P Data Migration, Master Data & Cutover Architecture

## Topic
**P2P Data Migration, Master Data & Cutover Architecture**

**Domain:** SAP S/4HANA Procure-to-Pay  
**Interview Mastery:** 20 scenario-based questions  
**Answer Method:** Every scenario follows **STAR → SME Probe → Reflection**.

## Architecture Principle

P2P migration is not simply moving records from one system to another.

**Discover → Profile → Cleanse → Map → Transform → Load → Validate → Reconcile → Cut Over → Stabilize**

The objective is to establish a trusted P2P foundation in S/4HANA while preserving business continuity, financial integrity, traceability, and operational readiness.

---

# 20 STAR-Based SAP P2P Migration Scenarios

## 1. P2P Migration Strategy

**Question:** How would you define a P2P migration strategy for S/4HANA?

### Situation
A global enterprise was migrating several legacy ERP systems into S/4HANA, each with different procurement structures and data quality.

### Task
I needed to define a migration approach that balanced standardization, business continuity, and data integrity.

### Action
I classified data into supplier/business partner, material, purchasing information, contracts, open purchasing documents, historical data, and configuration-dependent data. I defined migration scope, ownership, cleansing, mapping, mock loads, reconciliation, cutover, and retention requirements.

### Result
The migration became a governed business transformation rather than a technical data-copy exercise.

**SME Probe:** How do you decide what historical P2P data should actually be migrated?

**Reflection:** Migration scope should be driven by business, regulatory, operational, and analytical needs.

---

## 2. Supplier Master Migration

**Question:** How would you migrate supplier master data to S/4HANA Business Partner?

### Situation
The legacy systems contained duplicate suppliers with inconsistent addresses, tax identifiers, and payment data.

### Task
I needed to establish trusted supplier identities in the target system.

### Action
I profiled the legacy population, identified duplicates, mapped supplier identities to Business Partners, cleansed organizational data, validated tax and bank attributes, and performed mock migrations before final loading.

### Result
The target supplier population was cleaner and better aligned with S/4HANA Business Partner architecture.

**SME Probe:** What happens when two legacy suppliers appear to represent the same legal entity?

**Reflection:** Identity resolution must precede technical loading.

---

## 3. Material Master Migration

**Question:** How would you migrate procurement-relevant material data?

### Situation
Legacy systems used different material numbers, units, descriptions, groups, and plant-level procurement attributes.

### Task
I needed a consistent target material model.

### Action
I mapped material identities, units, material groups, plants, purchasing data, valuation-related information, and relevant classifications. I identified obsolete materials and validated business ownership before migration.

### Result
The target material population supported consistent purchasing processes.

**SME Probe:** How would you handle duplicate material numbers across legacy systems?

**Reflection:** Material harmonization is a business classification problem as much as a technical mapping problem.

---

## 4. Purchasing Organization Mapping

**Question:** How would you map legacy purchasing organizations into S/4HANA?

### Situation
Several legacy ERP systems had different purchasing structures for similar business operations.

### Task
I needed to create a target structure aligned with the global P2P operating model.

### Action
I compared organizational responsibility, plants, company codes, purchasing categories, buyer ownership, reporting, and approval requirements. I eliminated unnecessary duplication and documented justified local structures.

### Result
The target organization became simpler and more consistent.

**SME Probe:** What evidence would justify retaining a legacy purchasing organization?

**Reflection:** Organizational migration should follow the target operating model, not legacy history.

---

## 5. Purchase Order Migration

**Question:** How would you handle open purchase orders during migration?

### Situation
Thousands of open POs existed at the planned cutover date.

### Task
I needed to determine which commitments should be recreated or migrated.

### Action
I classified POs by status, remaining quantity/value, delivery status, invoice status, supplier, contract relationship, and business relevance. I defined migration rules for open commitments and excluded obsolete transactions.

### Result
Only business-relevant commitments were carried into the target environment.

**SME Probe:** What risks arise from migrating every open PO?

**Reflection:** Open-document migration requires business-state analysis, not record-count maximization.

---

## 6. Open Purchase Requisitions

**Question:** How would you handle open purchase requisitions?

### Situation
Many requisitions were still pending at cutover.

### Task
I needed to determine whether they should continue in the new system.

### Action
I assessed age, approval status, sourcing status, business need, budget relevance, requester, and target-process compatibility. I created rules for migration, cancellation, or controlled recreation.

### Result
The target system avoided inheriting obsolete demand.

**SME Probe:** When is recreation preferable to migration?

**Reflection:** A transaction should migrate only when its business state can be represented reliably in the target process.

---

## 7. Contract & Source-of-Supply Migration

**Question:** How would you migrate purchasing contracts?

### Situation
Legacy contracts had different structures, validity dates, supplier identifiers, and category classifications.

### Task
I needed to preserve active commercial commitments.

### Action
I assessed contract validity, remaining value/quantity, supplier mapping, materials/services, pricing conditions, organizational applicability, and legal requirements. I migrated only active and usable contractual information.

### Result
The target procurement process retained relevant commercial commitments.

**SME Probe:** How do you validate that a migrated contract remains commercially usable?

**Reflection:** Contract migration must preserve business meaning, not merely contract metadata.

---

## 8. Data Cleansing

**Question:** How would you establish P2P data-cleansing rules?

### Situation
Legacy data contained incomplete, duplicated, obsolete, and incorrectly classified records.

### Task
I needed measurable data-quality criteria.

### Action
I defined completeness, uniqueness, validity, consistency, accuracy, and business-relevance rules. I assigned data owners and created exception queues for unresolved records.

### Result
Data cleansing became measurable and accountable.

**SME Probe:** Who should own data cleansing decisions?

**Reflection:** Business data owners must decide business truth; technical teams should enable the transformation.

---

## 9. Data Mapping

**Question:** How would you design P2P migration mapping?

### Situation
Legacy fields did not have direct equivalents in S/4HANA.

### Task
I needed to establish reliable source-to-target mappings.

### Action
I created mapping specifications for supplier, material, purchasing organization, document types, account assignment, payment terms, tax attributes, and other relevant data. I documented transformation rules, defaults, exclusions, and ownership.

### Result
Migration mapping became transparent and testable.

**SME Probe:** What should happen when there is no valid target value?

**Reflection:** A missing mapping should create an explicit decision, not an invisible default.

---

## 10. Mock Migration Cycles

**Question:** How would you use mock migrations?

### Situation
The first migration rehearsal exposed unexpected supplier and open-document issues.

### Task
I needed to improve migration readiness before cutover.

### Action
I ran repeated mock cycles with profiling, cleansing, extraction, transformation, loading, validation, reconciliation, defect correction, and timing measurement.

### Result
Migration defects were discovered earlier and cutover confidence improved.

**SME Probe:** What should be measured during a mock migration?

**Reflection:** A mock migration is both a data-quality test and a cutover rehearsal.

---

## 11. Migration Reconciliation

**Question:** How would you reconcile migrated P2P data?

### Situation
The target system showed different counts and values from the legacy system after a load.

### Task
I needed to determine whether differences were expected transformations or migration defects.

### Action
I reconciled supplier counts, material populations, open PO quantities/values, open requisitions, contract values, invoice-related positions, and relevant Finance balances. I documented accepted differences.

### Result
Migration sign-off became evidence-based.

**SME Probe:** Is record-count equality always the goal?

**Reflection:** Reconciliation proves business equivalence, not necessarily identical record counts.

---

## 12. Data Migration Testing

**Question:** How would you test migrated P2P data?

### Situation
Migration loads completed technically, but users found transaction-processing issues.

### Task
I needed to prove that migrated data was operationally usable.

### Action
I tested supplier creation/use, PO creation/change, goods receipt, service entry, invoice matching, approvals, payment-relevant data, reporting, authorization, and integrations using migrated records.

### Result
Migration testing validated both data correctness and business usability.

**SME Probe:** Why is transaction testing necessary after successful data validation?

**Reflection:** Correct-looking data is not necessarily executable business data.

---

## 13. Cutover Planning

**Question:** How would you design the P2P cutover?

### Situation
The enterprise had a narrow production cutover window and ongoing purchasing activity.

### Task
I needed to minimize business disruption.

### Action
I created a sequenced plan covering freeze, extraction, cleansing, transformation, loading, validation, reconciliation, configuration readiness, open-document handling, interface activation, business validation, and go/no-go criteria.

### Result
Cutover responsibilities and dependencies became explicit.

**SME Probe:** What P2P activities must be controlled during the freeze window?

**Reflection:** Cutover is a business-event synchronization problem.

---

## 14. Supplier Cutover

**Question:** How would you manage supplier readiness during cutover?

### Situation
The target system had migrated suppliers but external suppliers still had old system references.

### Task
I needed to ensure supplier transactions continued correctly.

### Action
I aligned supplier identifiers, communication channels, PO references, network mappings, contact information, payment details, and supplier communication. I established targeted validation with critical suppliers.

### Result
Supplier-facing disruption was reduced.

**SME Probe:** What supplier-facing changes should be communicated before go-live?

**Reflection:** External ecosystem readiness is part of internal cutover readiness.

---

## 15. Interface Cutover

**Question:** How would you manage P2P interface cutover?

### Situation
The enterprise had interfaces to suppliers, tax services, banks, legacy systems, and analytics platforms.

### Task
I needed to avoid duplicate or lost transactions during transition.

### Action
I defined interface freeze, message queues, reconciliation points, endpoint switching, sequencing, monitoring, replay rules, and idempotency controls. I validated inbound and outbound business events after activation.

### Result
Interfaces transitioned with controlled transaction continuity.

**SME Probe:** How would you prevent duplicate messages during cutover?

**Reflection:** Interface cutover requires transaction-state awareness, not just endpoint switching.

---

## 16. Historical Data & Retention

**Question:** How would you decide whether historical P2P data should be migrated?

### Situation
The business wanted all historical purchasing data available in S/4HANA.

### Task
I needed to balance usability, regulatory needs, cost, and system complexity.

### Action
I classified history by operational necessity, legal retention, audit, analytics, and reference requirements. I distinguished active transactional data from historical information that could remain in an approved archive or analytical platform.

### Result
The target system avoided unnecessary historical-data complexity while preserving required access.

**SME Probe:** What is the difference between migrating historical data and retaining historical data?

**Reflection:** Accessibility does not always require moving every historical record into the transactional system.

---

## 17. Cutover Reconciliation with Finance

**Question:** How would you reconcile P2P migration with Finance?

### Situation
Procurement data migration was complete, but Finance needed confidence that open commitments and liabilities remained consistent.

### Task
I needed to connect P2P reconciliation with Finance validation.

### Action
I reconciled open procurement commitments, goods receipts, invoices, GR/IR positions, supplier balances where applicable, and relevant accounting outcomes. I investigated differences and obtained joint sign-off.

### Result
P2P and Finance had a common migration baseline.

**SME Probe:** Why should Procurement and Finance sign off together?

**Reflection:** P2P migration crosses the operational-to-financial boundary.

---

## 18. Cutover Defect & Recovery

**Question:** What would you do if critical P2P migration defects were discovered during cutover?

### Situation
A critical supplier population failed validation shortly before business activation.

### Task
I needed to protect go-live integrity.

### Action
I assessed severity, business impact, transaction dependency, workaround availability, rollback implications, and recovery time. I stopped affected processing where necessary, corrected the data, revalidated it, and documented the decision.

### Result
The organization avoided uncontrolled activation of defective data.

**SME Probe:** What makes a migration defect a go/no-go issue?

**Reflection:** Go-live decisions should be based on business impact and recoverability, not defect counts alone.

---

## 19. Hypercare & Migration Stabilization

**Question:** How would you manage P2P migration hypercare?

### Situation
Users experienced unfamiliar master-data and transaction issues immediately after go-live.

### Task
I needed to stabilize P2P quickly while distinguishing migration defects from training or process issues.

### Action
I established issue classification, severity, ownership, monitoring, reconciliation, root-cause analysis, user support, and daily stabilization reviews. I tracked recurring defects back to migration rules.

### Result
The team could stabilize operations while feeding lessons into the migration and support model.

**SME Probe:** How do you distinguish a migration defect from a configuration defect?

**Reflection:** Hypercare should generate learning, not become permanent firefighting.

---

## 20. Migration to a Clean P2P Foundation

**Question:** How would you use migration to improve the future P2P architecture?

### Situation
The legacy landscape contained years of duplicated suppliers, inconsistent categories, redundant purchasing structures, and process variants.

### Task
I needed to use migration as an opportunity to simplify the target architecture.

### Action
I treated migration as a transformation workstream. I rationalized master data, purchasing structures, document variants, historical scope, integration patterns, and local exceptions before loading the target system. I aligned decisions with the global template and clean-core principles.

### Result
The S/4HANA environment started with a more coherent P2P foundation rather than reproducing legacy complexity.

**SME Probe:** What is the danger of “lift and shift” migration?

**Reflection:** Migration is an opportunity to decide what the enterprise should carry forward.

---

# Rapid-Fire Questions

1. What is a P2P migration strategy?
2. How do you migrate suppliers to Business Partner?
3. How do you harmonize materials?
4. How do you map purchasing organizations?
5. How do you handle open POs?
6. How do you handle open requisitions?
7. How do you migrate active contracts?
8. What are key data-quality dimensions?
9. What is source-to-target mapping?
10. Why are mock migrations important?
11. How do you reconcile migrated data?
12. How do you test migrated P2P data?
13. What belongs in a P2P cutover plan?
14. How do you manage supplier readiness?
15. How do you cut over interfaces safely?
16. Should all historical P2P data be migrated?
17. How do you reconcile P2P with Finance?
18. What makes a migration defect a go/no-go issue?
19. What should hypercare monitor?
20. How can migration simplify the target P2P architecture?

# Mastery Framework — MIGRATE-P2P

**M — Map the Landscape**  
Understand legacy data, processes, organizations, and dependencies.

**I — Improve the Data**  
Cleanse, deduplicate, classify, and establish ownership.

**G — Govern the Scope**  
Decide what migrates, what is archived, and what is retired.

**R — Reconcile**  
Prove business equivalence across source and target.

**A — Activate**  
Execute controlled cutover and interface transition.

**T — Test**  
Validate data through real P2P business transactions.

**E — Evolve**  
Use migration to simplify and improve the target architecture.

**P2P — Preserve Business Truth**  
Migrate what the business needs while deliberately leaving unnecessary legacy complexity behind.

# Anti-Patterns

- Treating migration as a technical extraction/load exercise.
- Migrating every legacy supplier.
- Carrying duplicate suppliers into S/4HANA.
- Migrating obsolete open POs.
- Loading data without business ownership.
- Assuming record-count equality means successful migration.
- Testing migration only at database/data level.
- Ignoring external supplier readiness.
- Switching interfaces without transaction-state controls.
- Migrating all historical data without a retention strategy.
- Allowing Procurement and Finance to reconcile separately.
- Treating cutover defects by count rather than business impact.
- Recreating legacy complexity in the target system.

# Interview Evidence Bank

Prepare STAR stories for:

- P2P migration strategy
- Supplier/BP migration
- Material migration
- Purchasing-organization harmonization
- Open PO migration
- Open requisitions
- Contract migration
- Data cleansing
- Source-to-target mapping
- Mock migration
- Reconciliation
- Migration testing
- Cutover planning
- Supplier readiness
- Interface cutover
- Historical-data strategy
- Finance reconciliation
- Critical migration defect
- Hypercare
- Target-architecture simplification

For every example explain:

**Legacy State → Business Decision → Data Transformation → Validation → Cutover → Business Result → Learning**

# Success Criteria

You have mastered this topic when you can:

- Define a P2P migration strategy.
- Migrate suppliers into Business Partner architecture.
- Harmonize material data.
- Rationalize purchasing organizations.
- Handle open POs and requisitions.
- Migrate relevant contracts.
- Establish data-quality rules.
- Build source-to-target mappings.
- Run effective mock migrations.
- Reconcile source and target.
- Test migrated data through transactions.
- Design P2P cutover.
- Prepare suppliers and interfaces.
- Define historical-data strategy.
- Reconcile P2P with Finance.
- Make evidence-based go/no-go decisions.
- Stabilize P2P during hypercare.
- Use migration to simplify the target architecture.

# Final BAISI PAHACHA™ Mantra

> **“I do not migrate legacy P2P simply because it exists. I migrate the business truth the enterprise needs, cleanse what is broken, retire what is obsolete, and use the transition to create a stronger architecture.”**

## Final Mastery Milestone

**KNOW → DESIGN → DELIVER → SOLVE → INFLUENCE → TRANSFORM**

**Know P2P Migration → Design the Target Data Foundation → Deliver Trusted Migration → Solve Cutover Risks → Influence Transformation Decisions → Transform Legacy P2P into a Clean S/4HANA Foundation.**
