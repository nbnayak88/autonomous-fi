# 11 — Finance Data Migration & Open Items

## SAP Finance Interview Mastery — BAISI PAHACHA™

### Purpose

Master SAP S/4HANA Finance interview scenarios involving **legacy-to-S/4HANA Finance migration, master and transactional data, open items, balances, historical data, mapping, cleansing, reconciliation, migration tooling, cutover, mock loads, migration defects, data quality and auditability**.

### Interview North Star

> **Migration scope → Data model → Extract → Cleanse → Map → Load → Reconcile → Cut over**

---

# 20 Scenario-Based Interview Questions

## 01. ECC to S/4HANA Finance Migration Scope

### Question
A client is migrating ECC Finance to S/4HANA. How do you determine what Finance data should be migrated?

### STAR Answer

**Situation:**  
The client wanted to move to S/4HANA while avoiding unnecessary historical-data complexity.

**Task:**  
I needed to define the Finance migration scope based on business, statutory and operational requirements.

**Action:**  
I classified data into master data, open transactional items, balances, required historical information and data that could remain in an archive or legacy reporting solution. I considered legal retention, audit requirements, reconciliation needs, operational continuity and target S/4HANA data structures. I documented inclusion/exclusion criteria and obtained Finance ownership approval.

**Result:**  
The migration scope became controlled, auditable and aligned with business requirements rather than simply copying the legacy database.

**SME Probe:**  
Should all historical FI documents always be migrated?

**Reflection:**  
Migration scope should be driven by business and regulatory need, not by the assumption that every historical record belongs in the target ERP.

---

## 02. Open Items vs Historical Balances

### Question
Why would you migrate open items rather than every historical transaction?

### STAR Answer

**Situation:**  
The organization wanted operational continuity after S/4HANA go-live without unnecessarily loading large historical datasets.

**Task:**  
I needed to determine the minimum transactional data required for business operations.

**Action:**  
I distinguished open operational obligations from closed historical transactions. Vendor and customer open items required migration when users needed to continue collection, payment, clearing and reporting processes in S/4HANA. Closed historical transactions could often be retained through appropriate legacy access or reporting arrangements, subject to retention requirements.

**Result:**  
The target system contained the data required to operate while historical data remained accessible through governed means.

**SME Probe:**  
What is the risk of migrating too much historical data?

**Reflection:**  
Excessive historical migration increases complexity, validation effort and conversion risk without necessarily improving operational value.

---

## 03. Finance Master Data Cleansing

### Question
During migration, you discover thousands of duplicate G/L accounts. What do you do?

### STAR Answer

**Situation:**  
The legacy Chart of Accounts contained duplicate or redundant accounts.

**Task:**  
I needed to improve data quality before loading the target Finance structure.

**Action:**  
I analyzed account purpose, usage, balances, mappings, statutory requirements and reporting dependencies. I worked with Finance to define the target account structure and mapping rules. I identified accounts that could be consolidated and documented exceptions requiring separate treatment.

**Result:**  
The target Chart of Accounts became more standardized and fit for S/4HANA reporting.

**SME Probe:**  
Who should decide whether two accounts can be merged?

**Reflection:**  
Account harmonization is a Finance business decision supported by architecture and data analysis.

---

## 04. Customer Open Items Migration

### Question
How would you migrate customer open items into S/4HANA?

### STAR Answer

**Situation:**  
Open customer receivables had to remain operational after cutover.

**Task:**  
I needed to migrate them with correct customer, amount, currency, due date and accounting attributes.

**Action:**  
I defined the source-to-target mapping, cleansed customer and open-item data, validated document and posting-date requirements, and prepared migration files/processes. I performed mock migrations and reconciled customer-level totals to the legacy source. I also tested clearing and collection processes after load.

**Result:**  
Receivables remained operational and traceable after go-live.

**SME Probe:**  
What is more important than simply loading the open-item count?

**Reflection:**  
Financial amount, currency, aging, customer assignment and reconciliation are essential.

---

## 05. Vendor Open Items Migration

### Question
Vendor open items are loaded, but payment proposals do not select some invoices. How do you troubleshoot?

### STAR Answer

**Situation:**  
Migrated vendor liabilities appeared in S/4HANA but did not behave like normal operational open items.

**Task:**  
I needed to identify the missing or incorrect attributes.

**Action:**  
I checked vendor master data, company-code data, payment terms, baseline dates, payment methods, payment blocks, currencies and open-item attributes. I compared migrated invoices with native S/4HANA invoices and validated payment-process eligibility.

**Result:**  
The migration defects were corrected and vendor open items became usable in the standard payment process.

**SME Probe:**  
Why is migration testing beyond balance reconciliation necessary?

**Reflection:**  
Migrated data must behave correctly in downstream business processes, not merely equal a source total.

---

## 06. Legacy Chart of Accounts Mapping

### Question
A global company has different Charts of Accounts in five countries. How would you design the migration mapping?

### STAR Answer

**Situation:**  
The legacy landscape contained country-specific account structures.

**Task:**  
I needed to map them into a controlled target Finance account model.

**Action:**  
I analyzed account semantics, financial-statement presentation, statutory requirements, controlling dependencies and reporting needs. I created source-to-target mappings with one-to-one, many-to-one and exception mappings where justified. I validated opening balances and historical reporting impacts.

**Result:**  
The target Chart of Accounts supported global standardization while preserving required local reporting.

**SME Probe:**  
What is dangerous about a simple account-number mapping?

**Reflection:**  
Account numbers alone do not establish equivalent accounting meaning.

---

## 07. Migration of Assets

### Question
How would you migrate fixed assets into S/4HANA?

### STAR Answer

**Situation:**  
The client needed asset continuity after migration.

**Task:**  
I needed to migrate asset masters and financial values without breaking depreciation or reporting.

**Action:**  
I mapped asset classes, master attributes, capitalization dates, acquisition values, accumulated depreciation, depreciation areas, useful lives and remaining values. I performed mock loads and reconciled asset subledger values to the legacy system and GL.

**Result:**  
The asset population was transferred with controlled values and operational continuity.

**SME Probe:**  
Why should asset subledger and GL be reconciled separately?

**Reflection:**  
Asset migration must preserve both individual asset integrity and financial statement integrity.

---

## 08. Opening Balance Migration

### Question
The business wants to migrate opening balances into S/4HANA. What controls do you establish?

### STAR Answer

**Situation:**  
Opening balances represented the financial starting point for the new system.

**Task:**  
I needed to ensure that the opening balance was complete, accurate and reconcilable.

**Action:**  
I defined source balances, mapping rules, currencies, ledgers, profit centers and other required dimensions. I established trial-balance reconciliation, subledger reconciliation, intercompany reconciliation and retained-earnings/opening-balance controls as applicable. I required Finance sign-off before cutover.

**Result:**  
The S/4HANA opening position could be demonstrated as equivalent to the approved migration baseline.

**SME Probe:**  
What is the strongest evidence of a successful opening-balance migration?

**Reflection:**  
A signed, multidimensional reconciliation from approved source balances to target balances.

---

## 09. Migration Creates Document-Splitting Problems

### Question
Migrated Finance balances lack characteristics required by the target document-splitting design. How would you handle it?

### STAR Answer

**Situation:**  
Legacy balances did not contain all dimensions required by the target reporting architecture.

**Task:**  
I needed to preserve accounting integrity while handling missing characteristics.

**Action:**  
I identified which characteristics were mandatory for new postings versus historical balances and determined whether reliable derivation was possible. I avoided inventing unsupported historical dimensions and designed controlled migration treatment, balancing and reporting exceptions where necessary.

**Result:**  
The migration supported the target architecture without creating fabricated accounting history.

**SME Probe:**  
Why is historical derivation risky?

**Reflection:**  
A derived financial attribute must have a defensible source and audit trail.

---

## 10. Migration Mock Load Fails

### Question
The first mock migration has a 30% failure rate. How would you respond?

### STAR Answer

**Situation:**  
The first mock load exposed substantial migration defects.

**Task:**  
I needed to determine whether the problems were mapping, data quality, transformation, configuration or tooling issues.

**Action:**  
I categorized failures, quantified each defect type, identified high-volume root causes and prioritized systemic fixes. I established a defect dashboard and reran targeted mock loads after corrections rather than repeatedly executing full loads without learning from the failures.

**Result:**  
The migration team moved from individual defect fixing toward systematic conversion-quality improvement.

**SME Probe:**  
What is more valuable than fixing 10,000 individual records?

**Reflection:**  
Removing the common root cause can resolve thousands of records simultaneously.

---

## 11. Migration Reconciliation Shows Difference

### Question
Legacy AR total is ₹500 million, but the S/4HANA migrated total is ₹497 million. What do you do?

### STAR Answer

**Situation:**  
The target balance did not reconcile with the approved source balance.

**Task:**  
I needed to isolate the ₹3 million difference before approving the migration.

**Action:**  
I segmented the reconciliation by company code, customer, currency, document type, aging and migration batch. I checked exclusions, duplicate records, rejected items, currency conversion and timing differences. I traced the difference to individual records and documented the correction.

**Result:**  
The reconciliation difference was either resolved or formally explained and approved before cutover.

**SME Probe:**  
Would you accept a small unexplained difference?

**Reflection:**  
Materiality thresholds may govern exceptions, but unexplained financial differences must never be casually ignored.

---

## 12. Migration Cutover Planning

### Question
How would you design the Finance migration cutover?

### STAR Answer

**Situation:**  
The organization needed to move from legacy Finance to S/4HANA with minimal business disruption.

**Task:**  
I needed to coordinate transaction freeze, extraction, transformation, load, reconciliation and go-live.

**Action:**  
I created a cutover sequence covering source-system freeze, final extraction, data cleansing, migration execution, validation, opening balances, open-item verification, integration readiness, business reconciliation and sign-off. I defined rollback/contingency procedures and clear ownership for every activity.

**Result:**  
The Finance cutover became a controlled sequence rather than an unstructured data-loading event.

**SME Probe:**  
What is the most important cutover dependency?

**Reflection:**  
Source-system transaction completeness and the agreed cut-off point must be controlled.

---

## 13. Migration Data Quality Dashboard

### Question
What KPIs would you use to measure Finance migration quality?

### STAR Answer

**Situation:**  
The program needed objective evidence that Finance data was ready for migration.

**Task:**  
I needed to define measurable data-quality indicators.

**Action:**  
I tracked record completeness, mapping coverage, duplicate rate, rejected records, transformation exceptions, balance reconciliation, open-item reconciliation, master-data quality, mock-load success rate and unresolved defects by severity.

**Result:**  
The program could make migration decisions using measurable evidence rather than subjective confidence.

**SME Probe:**  
Which KPI is most important?

**Reflection:**  
No single KPI proves migration readiness; quality must be assessed across completeness, correctness, reconciliation and operational behavior.

---

## 14. Historical Data Is Required for Audit

### Question
The business says all 10 years of historical FI documents must be available in S/4HANA because auditors may request them. How would you challenge the requirement?

### STAR Answer

**Situation:**  
The business requested full historical migration primarily because of audit concerns.

**Task:**  
I needed to separate audit-access requirements from operational migration requirements.

**Action:**  
I clarified retention obligations, audit access needs, reporting requirements and document retrieval expectations. I evaluated whether governed legacy access, archival solutions or historical reporting could satisfy the requirement without physically migrating every closed document into the target ERP.

**Result:**  
The organization could meet evidence and retention needs while avoiding unnecessary migration scope.

**SME Probe:**  
What question should you ask auditors?

**Reflection:**  
Ask what evidence must be retained and retrievable, not simply whether every record must exist in the new ERP.

---

## 15. Migration of Open Items With Different Currencies

### Question
Open items exist in transaction currency and local currency. What should you validate during migration?

### STAR Answer

**Situation:**  
The legacy system contained open items across multiple currencies.

**Task:**  
I needed to preserve both operational and accounting currency integrity.

**Action:**  
I validated transaction currency, local/company-code currency, exchange-rate treatment, amounts, dates, due dates and open-item status. I compared migrated documents with legacy records and tested clearing and valuation after migration.

**Result:**  
The migrated open items behaved correctly under multi-currency Finance processes.

**SME Probe:**  
Why test clearing after currency migration?

**Reflection:**  
A technically loaded amount may still be operationally unusable if currency attributes are incorrect.

---

## 16. Migration Defect After Go-Live

### Question
After go-live, Finance discovers that a population of vendor open items was migrated incorrectly. What do you do?

### STAR Answer

**Situation:**  
A post-go-live data-quality defect affected vendor open items.

**Task:**  
I needed to assess the accounting and operational impact and correct it safely.

**Action:**  
I identified the affected population, quantified the financial impact and stopped further propagation where necessary. I traced the defect to the migration mapping or transformation rule, defined a controlled correction, reconciled before and after balances and documented the incident.

**Result:**  
The affected data was corrected with an auditable trail and the migration rule was fixed to prevent recurrence.

**SME Probe:**  
Why should you fix the mapping rule as well as the records?

**Reflection:**  
Correcting records without eliminating the source defect leaves the system vulnerable to repeated errors.

---

## 17. Migration and Parallel Ledgers

### Question
A client uses IFRS and local GAAP ledgers. How do you validate migrated opening balances?

### STAR Answer

**Situation:**  
The target system contained multiple accounting perspectives.

**Task:**  
I needed to prove that opening balances were correct for each ledger.

**Action:**  
I reconciled source balances by accounting principle, ledger, company code, currency and relevant dimensions. I validated legitimate differences between local and group accounting and ensured ledger-specific adjustments were represented correctly.

**Result:**  
Each accounting view had an independently reconciled opening position.

**SME Probe:**  
Why is one trial balance insufficient?

**Reflection:**  
Parallel accounting requires reconciliation at the ledger/accounting-principle level.

---

## 18. Migration Testing Beyond Data Validation

### Question
What is the difference between migration validation and migration testing?

### STAR Answer

**Situation:**  
The project team believed that matching source and target totals was enough to prove migration success.

**Task:**  
I needed to establish a broader testing approach.

**Action:**  
I separated data validation from business-process testing. Validation checks completeness, mappings and reconciliations. Testing additionally proves that migrated data behaves correctly in payment, collection, clearing, reporting, valuation, close and other downstream processes.

**Result:**  
The migration acceptance criteria covered both data correctness and operational usability.

**SME Probe:**  
Give one example of an operational migration test.

**Reflection:**  
A migrated vendor open item should be tested through the payment/clearing process, not merely counted.

---

## 19. Migration Governance and Sign-Off

### Question
Who should sign off Finance migration readiness?

### STAR Answer

**Situation:**  
The program needed formal approval before Finance cutover.

**Task:**  
I needed to define accountable ownership.

**Action:**  
I established sign-off across Finance process owners, data owners, migration leads, reconciliation/control owners and relevant business stakeholders. Each sign-off was tied to measurable evidence such as reconciliation, defect status, mock-load results and operational test completion.

**Result:**  
Go-live approval became evidence-based and clearly owned.

**SME Probe:**  
Should the technical migration team alone approve the Finance data?

**Reflection:**  
Technical teams can prove technical load success; Finance business owners must approve financial correctness.

---

## 20. Finance Architect Designs Migration Factory

### Question
As a Finance Architect, how would you design a repeatable Finance migration factory for multiple countries?

### STAR Answer

**Situation:**  
A global enterprise needed to migrate many countries into a common S/4HANA Finance platform.

**Task:**  
I needed to create a scalable migration approach without reinventing the process for every country.

**Action:**  
I established reusable global migration templates for data objects, mapping, cleansing, validation, reconciliation, mock loads, cutover and sign-off. I defined local extension points for statutory requirements and controlled country-specific mappings. I created migration KPIs, defect taxonomy, reusable test scenarios and governance checkpoints.

**Result:**  
Country migrations could follow a standardized factory model while still accommodating legitimate local requirements.

**SME Probe:**  
What should be standardized globally?

**Reflection:**  
Methodology, controls, evidence and quality gates should be standardized; legitimate local accounting requirements should be explicitly governed as variations.

---

# Rapid-Fire Interview Questions

1. What is Finance data migration?
2. What are open items?
3. Why migrate open items?
4. What are opening balances?
5. What is a migration mock load?
6. Why is data cleansing important?
7. What is source-to-target mapping?
8. What is reconciliation?
9. Why are G/L mappings difficult?
10. How do you migrate customer open items?
11. How do you migrate vendor open items?
12. What should be validated for asset migration?
13. Why test migrated data operationally?
14. What is a cutover freeze?
15. Why are migration defects categorized?
16. What is a migration factory?
17. What is a migration sign-off?
18. Why should Finance own financial validation?
19. What is historical-data strategy?
20. What makes migration successful?

---

# MIG-FI Mastery Framework

Use this 7-step framework for Finance migration interview scenarios:

### 1. MAP
Define scope, data objects, source systems and target structures.

### 2. IMPROVE
Cleanse, deduplicate and enrich source data.

### 3. GOVERN
Establish ownership, mapping rules, controls and quality gates.

### 4. LOAD
Execute transformation and controlled migration cycles.

### 5. INSPECT
Validate completeness, correctness, rejected records and data behavior.

### 6. RECONCILE
Prove balances, open items, ledgers, currencies and subledgers against approved sources.

### 7. CUTOVER
Execute the final migration with freeze, sign-off, contingency and operational readiness.

---

# Anti-Patterns to Avoid in Interviews

- Migrating every historical record without a business requirement.
- Treating migration as a technical ETL exercise only.
- Loading dirty master data into S/4HANA.
- Validating only record counts.
- Ignoring financial reconciliation.
- Assuming source and target account numbers have identical meaning.
- Testing migrated data only as static records.
- Ignoring open-item behavior.
- Ignoring currency and ledger differences.
- Fixing individual records without fixing mapping rules.
- Allowing technical teams to approve financial correctness alone.
- Treating country-specific requirements as uncontrolled exceptions.

---

# Interview Evidence Bank

Prepare STAR stories for:

- An ECC-to-S/4HANA Finance migration.
- Finance master-data cleansing.
- G/L mapping and Chart of Accounts harmonization.
- Customer open-item migration.
- Vendor open-item migration.
- Asset migration.
- Opening-balance reconciliation.
- Migration mock-load failures.
- Cutover planning.
- Post-go-live migration defects.
- Parallel-ledger migration.
- Migration-factory design.

For every example, explain:

**Scope → Mapping → Cleansing → Load → Validation → Reconciliation → Cutover → Outcome**

---

# Success Criteria

You have mastered this topic when you can:

- Define Finance migration scope.
- Explain open-item migration.
- Design source-to-target mappings.
- Lead Finance data cleansing.
- Plan mock migrations.
- Reconcile opening balances.
- Validate customer/vendor open items.
- Handle currencies and parallel ledgers.
- Design Finance cutover.
- Define migration-quality KPIs.
- Distinguish validation from operational testing.
- Manage post-go-live migration defects.
- Design a scalable global migration factory.

---

# Final Interview Mantra

> **Do not start with the migration tool.**
>
> **Start with the data and business requirement.**
>
> **Clean it.**
>
> **Map it.**
>
> **Load it.**
>
> **Reconcile it.**
>
> **Prove that the business can operate on it.**

**BAISI PAHACHA™ principle:**

**Know the source → Design the target → Clean the data → Map the accounting → Load with control → Reconcile the numbers → Transform Finance.**
