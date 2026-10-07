# FI132 — Common Google AI Studio Application Architecture

> Canonical template for building 12 stream-specific Google AI Studio applications across FI132.
> Principle: **Build the architecture once. Specialize the knowledge. Reuse the experience.**

## 1. Vision

FI132 becomes a federated Finance AI learning ecosystem: **one common application architecture + 12 specialized Finance applications + one shared learning ontology.**

**North Star:** Architecting Autonomous Financial Enterprises

**Learner journey:** Learn → Explore → Practice → Architect → Assess → Reflect → Transform

## 2. The 12 Applications

| # | Stream | Application identity |
|---:|---|---|
| 01 | AFR1 — Record to Report | R2R Architecture & Interview Coach |
| 02 | APT2 — Procure to Pay | P2P Architecture & Interview Coach |
| 03 | AOT3 — Order to Cash | O2C Architecture & Interview Coach |
| 04 | ATX4 — Tax & Compliance | Tax & Compliance Architecture Coach |
| 05 | ATR5 — Treasury & Risk | Treasury Architecture & Risk Coach |
| 06 | AFP6 — Financial Planning & Performance | Planning & Performance Coach |
| 07 | ACC7 — Controlling & Profitability | Controlling & Profitability Coach |
| 08 | AFA8 — Asset Accounting | Asset Finance Architecture Coach |
| 09 | AGR9 — Governance, Risk & Compliance | Finance Controls & GRC Coach |
| 10 | AFI0 — Finance Analytics & Intelligence | Finance Analytics & Decision Coach |
| 11 | AAI1-FI — AI-Powered Finance | AI Finance & Agent Architecture Coach |
| 12 | AIG2-FI — Connected Finance | Connected Finance & Integration Coach |

## 3. Common Architecture

```text
LEARNER EXPERIENCE
Learn | Scenario Catalog | Practice | Interview | Architect | Assess | Progress | Capstone | Ask AI
                              ↓
AI EXPERIENCE
Tutor | Scenario Coach | STAR Coach | Interviewer | Architect | Assessor | SME Challenger | Reflection Coach
                              ↓
FI132 KNOWLEDGE
Stream | 22 Scenario Categories | Scenarios | SAP Finance | Processes | Architecture | Controls | Industry
                              ↓
COMMON ONTOLOGY
12 Streams | 22 Categories | 20 Scenarios | 12 Architecture Streams | 20 Tracks | 11 GICS Sectors
                              ↓
ASSESSMENT
Knowledge | Process | SAP | Architecture | STAR | Problem Solving | Communication | Business Value
```

## 4. Learner-Facing Navigation

| Menu | Learner question |
|---|---|
| **Home** | Where am I and what should I do next? |
| **Learn** | What do I need to understand? |
| **Scenario Catalog** | What situations must I master? |
| **Practice** | Can I solve a scenario? |
| **Interview** | Can I explain it under pressure? |
| **Architect** | Can I design the solution? |
| **Assess** | How strong am I? |
| **Capstone** | Can I solve an end-to-end problem? |
| **Progress** | What have I mastered? |
| **Ask AI** | Where am I stuck? |

**Naming principle:** Do not expose BAISI PAHACHA™ as the primary navigation language. Use **Stream → Scenario Catalog → Scenario**. BAISI PAHACHA™ remains the proprietary mastery architecture behind the catalog.

## 5. Common Learning Model

```text
FINANCE → STREAM → SCENARIO CATALOG → SCENARIO → STAR ANSWER → EXPERT CHALLENGE → REFLECTION → ARCHITECTURE EVIDENCE → CAPABILITY
```

| Layer | Quantity |
|---|---:|
| Finance streams | 12 |
| Scenario categories per stream | 22 |
| Practice scenarios per category | 20 |
| Scenarios per stream | 440 |
| Total scenarios | **5,280** |
| GICS sectors | 11 |
| Architecture perspectives | 12 |
| SuccessLabs tracks | 20 |

## 6. Scenario Catalog

The **Scenario Catalog** is the learner-friendly representation of the 22 BAISI PAHACHA™ themes.

| # | Learner-facing category | BAISI PAHACHA™ |
|---:|---|---|
| 01 | Finance Foundation | Domain Foundation |
| 02 | SAP Finance Knowledge | Product / Technology Knowledge |
| 03 | Business Process | Process & Business Context |
| 04 | Finance Data | Data & Information Model |
| 05 | Requirements | Requirement Analysis |
| 06 | Solution Design | Solution Design |
| 07 | Configuration & Build | Configuration / Development |
| 08 | Integration & Architecture | Integration & Architecture |
| 09 | Testing & Quality | Testing & Quality Assurance |
| 10 | Deployment & Release | Deployment & Release |
| 11 | Migration & Cutover | Migration & Cutover |
| 12 | Operations & Support | Operations & Support |
| 13 | Troubleshooting | Troubleshooting & Root Cause Analysis |
| 14 | Problem Solving | Scenario-Based Problem Solving |
| 15 | Risk, Controls & Security | Risk, Controls & Security |
| 16 | Performance & Optimization | Performance & Optimization |
| 17 | Stakeholders | Stakeholder Management |
| 18 | Communication & Consulting | Communication & Consulting |
| 19 | Leadership & Decisions | Presales / Leadership / Decision Making |
| 20 | Transformation & Roadmap | Transformation & Roadmap |
| 21 | Innovation & Emerging Tech | Innovation & Emerging Technology |
| 22 | Enterprise Value | Enterprise Architecture & Business Value |

## 7. Scenario Object

Every scenario follows one common structure:

```text
Scenario
├── ID
├── Stream
├── Scenario Category
├── GICS Sector
├── Difficulty
├── Role
├── Business Context
├── Question
├── Situation
├── Task
├── Expected Action
├── Model Result
├── SAP Finance Concepts
├── Architecture Perspectives
├── SuccessLabs Tracks
├── SME Probe
├── Reflection
├── Evidence
└── Scoring
```

### Scenario difficulty

| Level | Meaning |
|---|---|
| Foundation | Can explain the concept |
| Applied | Can apply it to a normal situation |
| Complex | Can solve ambiguity and dependencies |
| Architecture | Can make design trade-offs |
| Leadership | Can influence decisions |
| Transformation | Can connect technology to enterprise value |

## 8. STAR Coach

Every interview scenario uses **Situation → Task → Action → Result**, followed by an SME Probe and Reflection.

| Dimension | Evaluation question |
|---|---|
| Situation | Did the learner establish meaningful business context? |
| Task | Was responsibility clearly defined? |
| Action | Did the learner explain what they personally did? |
| Result | Was the outcome measurable? |
| SAP depth | Was the technology explanation credible? |
| Architecture | Were trade-offs and dependencies considered? |
| Business value | Was the impact clear? |
| Communication | Was the answer structured and concise? |

## 9. AI Personas

| AI Mode | Role |
|---|---|
| Tutor | Explain concepts simply |
| Scenario Coach | Present realistic Finance situations |
| STAR Coach | Improve interview answers |
| Interviewer | Conduct adaptive interviews |
| SME Challenger | Ask expert-level follow-ups |
| Architect | Challenge solution design |
| Assessor | Score capability |
| Reflection Coach | Turn experience into evidence |
| Capstone Coach | Guide end-to-end transformation |
| Career Coach | Connect capability to interview readiness |

## 10. 12 Architecture Perspectives

| # | Architecture perspective | Core question |
|---:|---|---|
| 01 | Enterprise Architect | What enterprise value is being created? |
| 02 | Business Architect | What business capability changes? |
| 03 | Integration Architect | What must connect? |
| 04 | Domain Architect | What Finance capability and rules are required? |
| 05 | Cloud & Infrastructure Architect | Where does it operate? |
| 06 | Application & Process Architect | How should the SAP process/application work? |
| 07 | AI Architect | Where can AI/agents assist or act? |
| 08 | Security Architect | How are access and financial controls protected? |
| 09 | Industry Architect | What changes for the industry? |
| 10 | Data Architect | What data and governance are required? |
| 11 | UI/UX Architect | How does the user experience the process/decision? |
| 12 | Technology Architect | What technology standards enable scale? |

## 11. 11 GICS Sector Engine

Each application must support the 11 FI132 sectors. The AI adapts business drivers, regulations, operating model, process complexity, data, controls, risks, KPIs and architecture trade-offs.

| # | GICS sector | Architecture focus |
|---:|---|---|
| 01 | Energy | Clean Energy Transitions |
| 02 | Materials | Sustainable Material Solutions |
| 03 | Industrials | Ethical Production Systems |
| 04 | Consumer Discretionary | Mindful Consumption Patterns |
| 05 | Consumer Staples | Equitable Access to Essential Goods |
| 06 | Health Care | Universal Care Systems |
| 07 | Financials | Inclusive Financial Frameworks |
| 08 | Information Technology | Digital Solutions That Bridge Divides |
| 09 | Communication Services | Networks That Connect Humanity |
| 10 | Utilities | Sustainable Utility Networks |
| 11 | Real Estate | Sustainable Spaces That Nurture Human Potential |

## 12. 20 SuccessLabs Tracks

| # | Track |
|---:|---|
| 01 | Product |
| 02 | Process |
| 03 | Strategy & Architecture |
| 04 | Operation |
| 05 | Implementation |
| 06 | Migration |
| 07 | Integration |
| 08 | Quality Assurance |
| 09 | Application Maintenance Support |
| 10 | Certification Tracker |
| 11 | Interview Preparation |
| 12 | Presales Toolkit |
| 13 | Project Management |
| 14 | Product Management |
| 15 | Emerging Trends |
| 16 | Podcast / Videos |
| 17 | Assets |
| 18 | Ask Me Anything |
| 19 | Industry |
| 20 | Research |

## 13. Learner Profile

```text
Learner Profile
├── Current Role
├── Target Role
├── Experience
├── SAP Finance Experience
├── Architecture Experience
├── Industry
├── Target GICS Sector
├── Target Stream
├── Target Certification
├── Interview Date
├── Strengths
├── Gaps
├── STAR Evidence
└── Mastery Score
```

The AI adapts scenario difficulty and coaching to this profile.

## 14. Progress Model

Track capability, not just completion.

| Capability | Beginning | Developing | Applied | Advanced | Architect |
|---|---|---|---|---|---|
| Knowledge | ○ | ○ | ○ | ○ | ○ |
| Process | ○ | ○ | ○ | ○ | ○ |
| SAP | ○ | ○ | ○ | ○ | ○ |
| Data | ○ | ○ | ○ | ○ | ○ |
| Integration | ○ | ○ | ○ | ○ | ○ |
| Architecture | ○ | ○ | ○ | ○ | ○ |
| Problem Solving | ○ | ○ | ○ | ○ | ○ |
| STAR Interview | ○ | ○ | ○ | ○ | ○ |
| Leadership | ○ | ○ | ○ | ○ | ○ |
| Business Value | ○ | ○ | ○ | ○ | ○ |

## 15. Capstone Mode

Every stream application culminates in a stream-specific architecture challenge.

The learner should be able to: understand the business problem; define capabilities; model the process; define data; design SAP/application architecture; design integration; define security and controls; address migration; define testing and release; define operations; add analytics; identify automation and AI-agent opportunities; adapt to industry; create a transformation roadmap; and quantify business value.

## 16. Common AI System Instruction

```text
You are the SuccessLabs Academy Finance Architecture Coach.

Your specialization is [STREAM].

Your mission is to help the learner progress from:
Knowledge → Capability → Architecture → Transformation.

Use the FI132 learning ontology.

Always connect answers to:
1. Finance business value
2. Business process
3. SAP Finance capability
4. Data
5. Integration
6. Controls and security
7. Architecture
8. Industry context
9. AI/automation where relevant
10. Measurable outcome

For interview questions:
- use realistic scenarios
- require Situation, Task, Action and Result
- distinguish the learner's action from team activity
- ask SME-level follow-up questions
- challenge unsupported claims
- reward measurable outcomes
- never encourage memorized generic answers

For architecture questions:
- expose assumptions
- explain alternatives
- identify trade-offs
- identify risks
- connect decisions to business value

Adapt complexity to the learner profile.

Do not drift outside Finance unless the dependency is necessary to explain the Finance solution.
```

## 17. Common vs Stream-Specific

| Component | Common | Stream-specific |
|---|:---:|:---:|
| Navigation | ✓ | |
| AI personas | ✓ | |
| STAR engine | ✓ | |
| Assessment model | ✓ | |
| Scenario Catalog structure | ✓ | |
| 12 Architecture perspectives | ✓ | |
| 20 SuccessLabs tracks | ✓ | |
| 11 GICS sectors | ✓ | |
| Learner profile | ✓ | |
| Progress model | ✓ | |
| Finance knowledge | | ✓ |
| SAP capabilities | | ✓ |
| 22 scenario category content | | ✓ |
| 440 scenarios | | ✓ |
| Stream capstone | | ✓ |
| Stream architecture patterns | | ✓ |
| Stream terminology | | ✓ |

**Critical architecture rule:** Do not duplicate the application logic 12 times. Duplicate the knowledge specialization, not the design.

## 18. Build Strategy

### Phase 1 — Master Prototype

Build **AFR1 — Record to Report** as the FI132 Reference Application.

### Phase 2 — Validate

Validate onboarding, concept tutoring, Scenario Catalog, scenario generation, STAR evaluation, SME probing, architecture coaching, industry adaptation, assessment, progress and capstone.

### Phase 3 — Clone

Clone the validated architecture for APT2, AOT3, ATX4, ATR5, AFP6, ACC7, AFA8, AGR9, AFI0, AAI1-FI and AIG2-FI.

### Phase 4 — Specialize

Replace the knowledge layer and stream-specific prompts while keeping the common UX, assessment architecture and learning ontology.

## 19. Stream Configuration

Every cloned application should be driven by a stream configuration:

```text
STREAM_CONFIG
├── code
├── name
├── product
├── business_capabilities
├── SAP_capabilities
├── processes
├── data_objects
├── integrations
├── controls
├── architecture_patterns
├── 22_scenario_categories
├── 440_scenarios
├── 11_industry_variants
├── 20_track_mappings
├── capstone
└── AI_specialization_prompt
```

## 20. Success Criteria Before Cloning

| Test | Required outcome |
|---|---|
| Stream recognition | Correctly stays within the target Finance stream |
| Scenario Catalog | All 22 categories accessible |
| Scenario depth | 20 scenarios per category |
| STAR coaching | Actionable feedback |
| SME probing | Challenges shallow answers |
| SAP accuracy | Finance-specific and credible |
| Architecture | Uses relevant architecture perspectives |
| Industry | Adapts to GICS sector |
| Interview | Simulates realistic pressure |
| Assessment | Identifies capability gaps |
| Progress | Shows mastery, not just completion |
| Capstone | Produces end-to-end architecture outcome |
| AI behavior | Does not become a generic chatbot |

## 21. Product Experience

The learner should never feel that they are navigating a 5,280-question database.

They should feel:

> **I have my own Finance Architect Coach that knows my stream, my industry, my experience and the role I am preparing for.**

## 22. Final Design Principle

```text
FI132 = Learning Ecosystem
Scenario Catalog = learner-friendly name for the 22 BAISI PAHACHA™ categories
Scenario = actual practice/interview challenge
Google AI Studio App = intelligent coach

Stream → Scenario Catalog → Scenario → STAR → Expert Challenge → Reflection → Architecture → Capstone
```

> **Clone the shell. Specialize the brain.**

---

Repository: `nbnayak88/autonomous-fi`  
Document: `docs/google-ai-studio/fi132-common-application-architecture.md`  
Status: **Canonical template for the FI132 Google AI Studio application family.**