# APT2 — Procure to Pay

> **Finance Architecture Stream 02 | Applied SAP FI-AP | Autonomous Finance**

## 1. Purpose

Procure to Pay (P2P) is the financial architecture of external spend: from identifying a business requirement through purchasing, receiving, invoice verification, accounts payable, payment, and financial reconciliation.

The architect's job is not to memorize purchasing transactions. It is to design an **integrated spend-to-cash architecture** in which:

- business demand becomes an authorized commitment,
- the commitment becomes a purchase order,
- the receipt becomes financial evidence,
- the supplier invoice becomes a validated liability,
- the payment becomes a controlled cash movement,
- and every event produces trustworthy financial data.

### North Star

> **Design P2P so that every unit of external spend is visible, authorized, matched, controlled, payable, auditable, and increasingly autonomous.**

---

## 2. Learning Outcomes

By completing this stream, the learner can:

1. Explain the end-to-end Procure-to-Pay value stream and its finance impact.
2. Architect the relationship between procurement, inventory/services, Accounts Payable, General Ledger, tax, treasury, and supplier collaboration.
3. Design purchase-to-payment controls including approval, segregation of duties, tolerance, duplicate-invoice, and payment controls.
4. Understand the financial consequences of requisitions, purchase orders, goods receipts, service entry, invoices, credit memos, and payments.
5. Diagnose P2P failures using document flow, accounting impact, master data, and integration evidence.
6. Design automation using workflow, invoice capture, matching, evaluated receipt settlement, payment automation, and exception management.
7. Evaluate how SAP S/4HANA, SAP Business Network, SAP Ariba, SAP Integration Suite, and adjacent services can participate in a P2P architecture.
8. Define measurable P2P outcomes such as cycle time, first-pass match rate, exception rate, overdue liabilities, duplicate-payment exposure, and working-capital impact.

---

# 3. The P2P Mental Model

A useful architecture model is:

**Demand → Requisition → Approval → Purchase Order → Confirmation → Receipt → Invoice → Match → Liability → Payment → Clearing → Reconciliation → Insight**

The critical insight is that P2P has **two simultaneous flows**:

### Operational flow

```text
Need
→ Purchase Requisition
→ Purchase Order
→ Supplier Fulfillment
→ Goods Receipt / Service Entry
→ Supplier Invoice
→ Payment
```

### Financial flow

```text
Commitment
→ Receipt / Accrual Evidence
→ Accounts Payable Liability
→ Tax / Withholding
→ Cash Disbursement
→ Clearing
→ General Ledger / Reporting
```

An enterprise architect connects these flows instead of treating Procurement and Finance as separate applications.

---

# 4. End-to-End P2P Architecture

| Stage | Business question | Primary evidence | Architecture concern |
|---|---|---|---|
| Demand | What does the business need? | Requisition | Demand governance |
| Approval | Is the spend authorized? | Workflow decision | Delegation / SoD |
| Sourcing | Who should supply it? | Source / contract | Supplier strategy |
| Ordering | What have we committed to buy? | Purchase Order | Commitment control |
| Fulfillment | Did we receive it? | GR / SES | Receipt evidence |
| Invoicing | What is the supplier claiming? | Supplier invoice | Invoice integrity |
| Matching | Does invoice agree with evidence? | PO + GR/SES + invoice | Match / tolerance |
| AP | What do we owe? | Accounting document | Liability accuracy |
| Tax | What tax applies? | Tax determination | Compliance |
| Payment | When and how should we pay? | Payment proposal / run | Cash + controls |
| Clearing | Has the liability been settled? | Clearing document | Reconciliation |
| Analytics | What is happening? | P2P data | Performance / insight |

SAP describes P2P as integrating materials management with Accounts Payable, with core steps including demand determination, purchase order creation, goods receipt, invoice verification, and payment. SAP also provides process-flow capabilities to relate purchasing documents, goods movements, invoices, journal entries, and clearing entries. citeturn0search11turn0search12

---

# 5. Core Capability Model

## 5.1 Spend and Demand

- Demand identification
- Purchase requisition
- Budget / availability awareness
- Catalog and guided buying
- Approval routing
- Preferred supplier selection

## 5.2 Procurement

- Source determination
- Purchase order creation
- Purchase order approval
- Supplier confirmation
- Delivery monitoring
- Contract / source-of-supply compliance

## 5.3 Receipt

- Goods receipt
- Service entry sheet
- Quantity validation
- Quality / acceptance evidence
- Accrual awareness

## 5.4 Accounts Payable

- Invoice intake
- Invoice validation
- PO / receipt matching
- Exception handling
- Credit memo processing
- Liability posting
- Open-item management

## 5.5 Payment

- Due-date analysis
- Payment proposal
- Approval
- Payment execution
- Payment media
- Remittance
- Clearing

SAP's automatic payment program can select due open invoices, prepare payment processing, post payment documents, and support payment media such as DME or EDI. citeturn0search14

## 5.6 Controls

- Supplier master governance
- Segregation of duties
- Approval limits
- Duplicate invoice detection
- Tolerance rules
- Payment controls
- Bank-account controls
- Audit trail
- Tax controls

---

# 6. SAP S/4HANA Finance Architecture View

A simplified architecture is:

```text
                    BUSINESS USERS
                         │
                 Fiori / Guided Buying
                         │
                         ▼
              ┌──────────────────────┐
              │ Procurement Process  │
              │ PR → PO → Receipt    │
              └──────────┬───────────┘
                         │
                         ▼
              ┌──────────────────────┐
              │ Invoice Processing   │
              │ Match / Validate     │
              └──────────┬───────────┘
                         │
                         ▼
              ┌──────────────────────┐
              │ Accounts Payable     │
              │ Liability / Tax      │
              └──────────┬───────────┘
                         │
             ┌───────────┴───────────┐
             ▼                       ▼
       General Ledger             Treasury
             │                       │
             └───────────┬───────────┘
                         ▼
                Financial Insight
```

The architecture should preserve a traceable relationship between the procurement document flow and the accounting document flow.

SAP documentation describes supplier invoice processing as generating both an invoice document and an accounting document, with the invoice information also updating procurement document history and Financial Accounting. citeturn0search1

---

# 7. The Three-Way Match as an Architecture Pattern

The classic P2P control is:

```text
Purchase Order
      +
Goods Receipt / Service Entry
      +
Supplier Invoice
      ↓
   MATCHING
      ↓
 ┌────┴────┐
 │         │
MATCH     EXCEPTION
 │         │
 ▼         ▼
POST      RESOLVE
```

The architect should ask:

- What constitutes the source of truth for price?
- What constitutes the source of truth for quantity?
- Is receipt mandatory?
- Are services validated differently from materials?
- Which variances are acceptable?
- Who owns an exception?
- When is a liability created?
- What prevents payment before evidence is complete?

For services, the evidence chain may use a Service Entry Sheet rather than a physical goods receipt. SAP's current best-practice scenarios explicitly support supplier invoices with PO/GR and PO/SES relationships. citeturn0search8turn0search15

---

# 8. Financial Posting Mental Model

A learner should understand the accounting logic, not only the user interface.

A simplified goods procurement pattern can be understood as:

```text
Goods Receipt
→ Inventory / Expense
→ GR/IR

Supplier Invoice
→ GR/IR / Tax / Expense adjustments
→ Accounts Payable

Payment
→ Accounts Payable
→ Bank
```

The exact posting logic depends on valuation, account determination, tax, material/service characteristics, and configuration.

The important architectural principle is:

> **Every operational P2P event must have a predictable financial interpretation.**

SAP documentation shows supplier-invoice accounting can involve GR/IR, tax, and Accounts Payable, with automatic offsetting-account determination supporting balanced accounting documents. citeturn0search9

---

# 9. Master Data Architecture

P2P quality is heavily constrained by master data.

### Supplier / Business Partner

Key concerns:

- legal identity
- tax registration
- payment terms
- purchasing organization data
- bank details
- payment methods
- withholding-tax relevance
- duplicate supplier prevention
- supplier lifecycle status

### Material / Service

Key concerns:

- material or service classification
- valuation
- purchasing data
- units of measure
- tax relevance
- account determination

### Organizational Data

- company code
- purchasing organization
- purchasing group
- plant
- storage location
- cost center
- profit center
- controlling objects

### Architecture rule

> **Do not automate a broken master-data model.**

---

# 10. Business Architecture

Map P2P to business capabilities:

```text
Enterprise Spend
├── Demand Management
├── Supplier Management
├── Procurement
├── Receiving
├── Invoice Management
├── Accounts Payable
├── Payments
├── Financial Control
└── Spend Intelligence
```

### Key stakeholders

| Stakeholder | Primary concern |
|---|---|
| Requester | Speed and usability |
| Procurement | Compliance and sourcing |
| Supplier | Clear orders and fast payment |
| Warehouse / Operations | Correct receipt |
| Service Owner | Acceptance of services |
| AP Accountant | Accurate liabilities |
| Treasury | Cash timing |
| Tax | Correct tax treatment |
| Controller | Financial integrity |
| Auditor | Evidence and controls |
| CIO / EA | Integration and architecture |
| CFO | Working capital and financial risk |

---

# 11. Application Architecture

A modern P2P landscape may include:

- SAP S/4HANA
- SAP S/4HANA Cloud
- SAP Ariba / SAP Business Network
- SAP Business Partner
- SAP Fiori
- SAP Integration Suite
- SAP Analytics Cloud
- SAP Build Process Automation / workflow capabilities
- Tax and compliance services
- Banks / payment providers
- External supplier systems
- OCR / intelligent document processing
- Enterprise data platform

The architect should decide which capability belongs where instead of creating point-to-point integrations for every business event.

SAP Business Network supports native Source-to-Pay collaboration with documents such as purchase orders, goods-receipt notices, invoice status updates, payment remittances, purchase-order confirmations, advanced shipping notices, invoices, and service-entry sheets. citeturn0search18

---

# 12. Integration Architecture

A conceptual integration landscape:

```text
Supplier
   │
   ▼
SAP Business Network / Supplier Channel
   │
   ▼
Integration Layer
   │
   ├──────────────► Procurement
   │
   ├──────────────► Invoice Processing
   │
   ├──────────────► Accounts Payable
   │
   ├──────────────► Tax
   │
   └──────────────► Payment / Bank
                         │
                         ▼
                      Treasury
```

For multi-system enterprises, Central Procurement can act as a hub across connected SAP and third-party systems, with SAP Cloud Integration participating in integration scenarios. citeturn0search0turn0search5

### Integration design questions

1. Which system owns the supplier?
2. Which system owns the purchase order?
3. Where is the invoice received?
4. Where is matching performed?
5. Where is the liability posted?
6. Which system owns payment execution?
7. How are status events propagated?
8. How are retries handled?
9. How are duplicate messages detected?
10. How is end-to-end observability implemented?

---

# 13. Data Architecture

The P2P data chain is:

```text
Supplier
→ Requisition
→ Purchase Order
→ PO Item
→ Confirmation
→ Receipt / SES
→ Invoice
→ Accounting Document
→ Payment
→ Clearing
```

### Critical identifiers

- Supplier / Business Partner ID
- Purchase Requisition ID
- Purchase Order ID
- PO Item
- Material / Service ID
- Goods Receipt ID
- Service Entry Sheet ID
- Supplier Invoice ID
- Accounting Document
- Payment Document
- Clearing Document

### Data principle

> **Every financial liability should be traceable back to the business evidence that created it.**

---

# 14. Control Architecture

A mature P2P control model operates across four layers.

## Preventive

- supplier onboarding controls
- approval workflows
- spending limits
- preferred suppliers
- PO requirements
- segregation of duties

## Detective

- duplicate invoice analysis
- unmatched invoice reporting
- overdue items
- unusual supplier activity
- payment exception analysis

## Corrective

- invoice blocking / release
- master-data remediation
- payment reversal
- dispute resolution
- reconciliation

## Predictive

- supplier risk signals
- duplicate-payment prediction
- abnormal invoice behavior
- cash-flow forecasting
- exception prioritization

---

# 15. Exception Architecture

The goal is not to eliminate every exception.

The goal is to **route the right exception to the right person with enough evidence to resolve it quickly**.

### Common exception classes

| Exception | Typical cause | Architectural response |
|---|---|---|
| Price variance | Invoice price differs from PO | Tolerance + workflow |
| Quantity variance | Invoice quantity differs from receipt | Receipt validation |
| Missing receipt | Invoice arrives before evidence | Exception queue |
| Duplicate invoice | Same invoice submitted twice | Duplicate detection |
| Tax variance | Tax mismatch | Tax determination / review |
| Supplier mismatch | Incorrect supplier identity | Master-data validation |
| Bank issue | Invalid payment data | Bank validation |
| Blocked invoice | Control failure | Workflow ownership |
| Unapproved spend | Policy breach | Approval escalation |

---

# 16. Autonomous P2P Architecture

Progression:

```text
Manual
  ↓
Digitized
  ↓
Workflow-Driven
  ↓
Exception-Aware
  ↓
Predictive
  ↓
AI-Assisted
  ↓
Autonomous
```

### Automation opportunities

1. Invoice ingestion
2. Invoice data extraction
3. Supplier matching
4. PO matching
5. Receipt matching
6. Duplicate detection
7. Exception classification
8. Approval routing
9. Payment proposal
10. Remittance notification

### ERS — a powerful automation pattern

In Evaluated Receipt Settlement, the buyer and supplier agree that the supplier does not send the invoice; the system creates the settlement based on purchase-order and goods-receipt information. SAP documents ERS as an automation mechanism when its required master-data and purchasing conditions are met. citeturn0search6turn0search7

The architecture lesson is:

> **The best invoice is sometimes the invoice the enterprise never has to receive.**

---

# 17. AI Architecture for P2P

AI should augment controlled business processes rather than bypass them.

### AI use cases

- invoice classification
- invoice data extraction
- duplicate-risk detection
- supplier anomaly detection
- payment-risk prioritization
- exception summarization
- root-cause analysis
- cash-disbursement forecasting
- supplier communication assistance
- procurement recommendations

### AI control pattern

```text
AI Detects
    ↓
AI Explains
    ↓
Human / Policy Validates
    ↓
Workflow Acts
    ↓
Transaction Executes
    ↓
Audit Evidence Captured
```

### AI architecture questions

- What data can the model access?
- What decisions can it recommend?
- What decisions can it execute?
- What thresholds require human approval?
- How is model confidence represented?
- How is the decision logged?
- How can the decision be reversed?

---

# 18. P2P Scenario Architecture

## Scenario A — Standard Material Purchase

```text
Requisition
→ Approval
→ PO
→ Goods Receipt
→ Invoice
→ 3-Way Match
→ AP
→ Payment
→ Clearing
```

## Scenario B — Service Procurement

```text
Requisition
→ PO
→ Service Delivery
→ Service Entry Sheet
→ Approval
→ Invoice
→ Match
→ AP
→ Payment
```

## Scenario C — Invoice Without PO

Architecture question:

> Should the enterprise permit non-PO invoices, and if so, under which controlled exceptions?

## Scenario D — Evaluated Receipt Settlement

```text
PO
→ Goods Receipt
→ ERS
→ Automated Settlement
→ AP
```

## Scenario E — Global P2P

```text
Global Procurement Policy
        │
        ├── Country A
        ├── Country B
        ├── Country C
        └── Country D
              │
              ▼
     Local Tax / Payment / Legal
```

The architecture challenge is balancing global standardization with local statutory requirements.

---

# 19. 20 Architecture Questions

1. What is the enterprise's P2P value proposition?
2. Which business capabilities belong to Procurement versus Finance?
3. Where is supplier master data governed?
4. What is the authoritative source for purchase orders?
5. What evidence is required before a liability can be recognized?
6. Where is the three-way match performed?
7. What are the tolerance policies?
8. Which purchases require a receipt?
9. How are service purchases controlled?
10. Which non-PO invoices are allowed?
11. How are duplicate invoices detected?
12. How are supplier bank-account changes controlled?
13. Which payment activities require dual control?
14. Where does tax determination occur?
15. How are exceptions routed?
16. How does P2P integrate with the General Ledger?
17. How does P2P integrate with Treasury?
18. What P2P data should feed analytics?
19. Which P2P activities can be automated safely?
20. What would make the process genuinely autonomous?

---

# 20. Hands-On Architecture Challenge

## Challenge: Design a Global P2P Control Tower

### Business situation

A multinational enterprise has:

- 8 countries
- 5 ERP instances
- 40,000 suppliers
- 250,000 invoices per month
- multiple procurement channels
- high invoice-exception volumes
- decentralized supplier onboarding
- multiple banking partners

### Your mission

Design the target P2P architecture.

### Deliverables

1. Business capability map
2. Current-state value stream
3. Target-state architecture
4. Supplier master architecture
5. PO / receipt / invoice data model
6. Integration architecture
7. Three-way-match control model
8. Payment-control model
9. Exception-management architecture
10. P2P KPI dashboard
11. AI opportunity map
12. 12-month transformation roadmap

### Success criteria

The solution must improve:

- traceability
- control
- exception resolution
- supplier experience
- payment visibility
- working-capital insight
- auditability
- automation readiness

---

# 21. KPI Architecture

| KPI | What it tells the architect |
|---|---|
| P2P cycle time | Process speed |
| PR-to-PO time | Procurement responsiveness |
| Invoice processing time | AP efficiency |
| First-pass match rate | Process quality |
| Exception rate | Process stability |
| Touchless invoice rate | Automation maturity |
| PO compliance | Spend governance |
| On-time payment rate | Supplier / cash discipline |
| Duplicate invoice rate | Control effectiveness |
| Blocked invoice aging | Exception health |
| Cost per invoice | Operating efficiency |
| Early-payment discount capture | Working-capital opportunity |
| Days Payable Outstanding | Cash strategy |
| Supplier dispute cycle time | Supplier experience |
| Manual intervention rate | Automation opportunity |

---

# 22. P2P Maturity Model

| Level | Architecture characteristic |
|---|---|
| **Bronze — Foundations** | Understand P2P process, documents, roles, and accounting impact |
| **Silver — Essentials** | Configure / analyze core procurement, AP, matching, and payment scenarios |
| **Gold — Advanced** | Design controls, integrations, analytics, exceptions, and global scenarios |
| **Diamond — Ultimate** | Architect enterprise-scale P2P transformation and optimization |
| **Quantum — Autonomous** | Design AI-enabled, exception-driven, continuously learning P2P ecosystems |

---

# 23. SuccessLabs Learning Architecture

## KNOW

Understand:

- P2P concepts
- procurement and AP terminology
- financial postings
- supplier lifecycle
- invoice matching
- payment lifecycle

## DESIGN

Design:

- P2P capabilities
- operating model
- control architecture
- integration architecture
- data architecture

## DELIVER

Apply:

- SAP S/4HANA scenarios
- invoice processing
- matching
- payment runs
- exception workflows

## SOLVE

Diagnose:

- unmatched invoices
- GR/IR issues
- supplier-data problems
- payment failures
- integration errors

## INFLUENCE

Communicate:

- business value
- control improvements
- architecture decisions
- transformation roadmap

## TRANSFORM

Create:

- intelligent P2P
- touchless processing
- AI-assisted exception management
- autonomous finance capabilities

---

# 24. Mapping to the 12 Architecture Streams

| Architecture Stream | P2P application |
|---|---|
| Enterprise Architect | Global P2P target architecture |
| Business Architect | Spend and AP capability model |
| Integration Architect | Procurement-to-Finance and supplier integrations |
| Domain Architect | Finance / Procurement domain boundaries |
| Cloud & Infrastructure Architect | SAP cloud, connectivity, resilience |
| Application & Process Architect | P2P workflow and application landscape |
| AI Architect | Invoice intelligence and exception automation |
| Security Architect | SoD, supplier, bank and payment security |
| Industry Architect | Industry-specific procurement patterns |
| Data Architect | Supplier, PO, invoice, payment data lineage |
| UI/UX Architect | Guided buying, AP worklists, exception experience |
| Technology Architect | APIs, events, integration and automation platform |

---

# 25. Mapping to the 20 SuccessLabs Tracks

| Track | P2P application |
|---|---|
| Product | P2P product / capability design |
| Process | End-to-end P2P process architecture |
| Strategy & Architecture | Global P2P target state |
| Operation | AP and procurement operating model |
| Implementation | SAP S/4HANA P2P implementation |
| Migration | Legacy procurement / AP migration |
| Integration | Supplier, network, bank and ERP integration |
| Quality Assurance | P2P testing and controls |
| AMS | P2P production support |
| Certification Tracker | SAP Finance / Procurement learning path |
| Interview Preparation | P2P architecture and SAP FI-AP scenarios |
| Presales Toolkit | P2P discovery and solutioning |
| Project Management | P2P transformation delivery |
| Product Management | Finance automation products |
| Emerging Trends | AI, autonomous AP, digital networks |
| Podcast/Videos | P2P architecture stories |
| Assets | Process maps, checklists, templates |
| AMA | P2P architect problem-solving |
| Industry | Industry-specific spend patterns |
| Research | Autonomous P2P and finance transformation |

---

# 26. Anti-Patterns

Avoid:

- treating P2P as only an FI-AP configuration exercise
- designing Procurement and Finance independently
- automating bad supplier master data
- allowing uncontrolled non-PO invoices
- creating point-to-point integrations everywhere
- measuring only invoice-processing speed
- ignoring GR/IR reconciliation
- designing payment without Treasury alignment
- allowing AI to bypass financial controls
- optimizing local process while damaging the global value stream
- treating exceptions as an AP-only problem
- designing without audit evidence

---

# 27. Architect's Master Loop

Use this loop for every P2P problem:

```text
1. OBSERVE
   Understand the business event.

2. MODEL
   Map capability, process, data, application and control.

3. CONNECT
   Identify upstream and downstream dependencies.

4. CONTROL
   Define policy, authorization and evidence.

5. AUTOMATE
   Remove repetitive manual work.

6. INTELLIGENTLY ASSIST
   Apply AI where prediction, classification or explanation helps.

7. MEASURE
   Track business and financial outcomes.

8. LEARN
   Feed exceptions and outcomes back into the architecture.
```

---

# 28. Final Master Answer

If someone asks:

> **“What does a Finance Architect need to understand about Procure to Pay?”**

The answer is:

> **A Finance Architect must understand P2P as an integrated business, financial, data, control, application, and integration value stream.**
>
> The architect connects business demand to procurement commitment, commitment to receipt evidence, receipt to supplier liability, liability to controlled payment, and payment to reconciliation and financial insight.
>
> The real mastery is not knowing every transaction code. It is being able to explain **why each business event exists, what data it creates, what accounting consequence it produces, what control protects it, which application owns it, how systems communicate it, how exceptions are resolved, and how the process can progressively become automated and intelligent.**
>
> The ultimate architecture objective is a P2P ecosystem where spend is visible, supplier interactions are connected, invoices are processed with minimal manual intervention, exceptions are intelligently prioritized, payments are controlled, and every financial outcome remains explainable and auditable.

---

# 29. SAP Source Alignment

This learning stream is aligned to current SAP learning and documentation themes around:

- Procure-to-Pay and the integration of procurement with Accounts Payable
- supplier invoice processing and accounting-document creation
- PO / goods-receipt / invoice relationships
- Service Entry Sheet-based invoice scenarios
- Evaluated Receipt Settlement
- automatic payment processing
- SAP Business Network Source-to-Pay collaboration
- Central Procurement and multi-system integration
- supplier-invoice integration APIs

The SAP documentation used for this architecture stream should be treated as the product-reference layer; customer-specific configuration, localization, release level, activated scope items, and integration choices must be validated during solution design. citeturn0search11turn0search1turn0search6turn0search14turn0search18

---

## 30. One-Line Mastery Statement

> **Architect P2P so that every rupee, dollar, euro, or riyal of external spend can be traced from business need to authorized commitment, verified receipt, validated liability, controlled payment, and measurable business value.**
