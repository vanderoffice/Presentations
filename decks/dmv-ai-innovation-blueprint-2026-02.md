# DMV AI Innovation: A Blueprint for California State Government

Governor's Innovation Fellows Program

**Core Thesis:** DMV has 6 AI systems in production — with RADV alone saving 22,000+ staff hours/year. Every Fellowship department can adopt at least one of these patterns without starting from scratch.

February 2026 | Based on DMV Innovation Tour, January 30, 2026

---

## Why This Matters

California DMV is running **six distinct AI/automation systems** in production — more than most state departments have even piloted.

The critical pattern: DMV uses AI as a **decision-support layer** (human stays in the loop), not full automation. This approach:

- Requires no new legislation
- Has survived legal challenge (Personalized Plates: zero lawsuits since GenAI implementation)
- Produces measurable, auditable results

The [Governor's Innovation Fellows Program](https://innovation.ca.gov/) puts 21 Fellows across **15 departments in 9 agencies** — every one of which has a direct transfer opportunity from DMV's playbook.

---

## The 6 AI Systems in Production

| # | System | AI Type | Launched | Key Metric |
|---|--------|---------|----------|------------|
| 1 | **RADV** — Document Verification | OCR/ICR + ML | 2020 | 5.4M docs/year, 62% automated |
| 2 | **Miles Chatbot** — Voice & Chat | NLP → GenAI | Ongoing | 13.77M calls/year handled |
| 3 | **Service Advisor** — Web Search | Semantic Search | Active | 1M+ queries/year |
| 4 | **MyDMV** — Identity Verification | Multi-tier Auth + Biometrics | Active | 90-95% verification success |
| 5 | **Disaster Recovery App** — Field Ops | GIS Mobile App | Active | 195 vehicles mapped (Sacramento region) |
| 6 | **GenAI Plates** — Content Review | GenAI + RPA | Nov 2022 | 90% auto-processed, 0 lawsuits |

Each system follows the same philosophy: **AI assists, humans decide.**

---

## System 1: RADV — Real ID Automated Document Verification

**Presenter:** Adrian Monteon | **Technology:** [ABBYY](https://www.abbyy.com/) OCR/ICR + Machine Learning

### How It Works

Citizens upload identity documents (birth certificates, passports, EAD cards, I-94s) through the [online portal](https://www.dmv.ca.gov/portal/). The ABBYY engine:

1. **Extracts** printed text and handwritten entries via OCR/ICR
2. **Validates** extracted data against DMV's database
3. **Auto-approves** documents that pass (~62%)
4. **Routes failures** to a human technician for manual review

### Five-Year Average Savings

- **Time saved:** 22,050 hours/year
- **Staff equivalent:** 28 FTE/year
- **Documents processed:** Millions monthly

---

## RADV: Automation Rate Climbing Year Over Year

:::chart bar
| Year | Automated | Human Touch |
|------|-----------|-------------|
| 2021 | 2.9 | 2.5 |
| 2022 | 2.6 | 2.1 |
| 2023 | 3.1 | 2.2 |
| 2024 | 2.8 | 1.7 |
| 2025 | 3.3 | 2.1 |
:::

Automation rate rose from **53% in 2021 to 62% in 2025** — driven by machine learning improvements, not just volume growth. The Digital Imaging and Archiving extension reached **75% automation** for internal form processing (309K docs in 2025).

---

## System 2: Miles Chatbot — Voice & Chat AI

**Presenter:** Sonia Huestis | **Technology:** NLP chatbot evolving toward GenAI conversational bot

### Scale: 13.77 Million Calls in 2025

:::chart doughnut
| Channel | Calls (M) |
|---------|-----------|
| Self-Service | 6.8 |
| Requested Agent | 5.6 |
| Full Message | 1.4 |
:::

The bot deflected **6.8M calls** to self-service in 2025 (up from 6.0M in 2024) — a 13% increase in automation without adding staff.

Top call reasons: VR Renewal (13%), Title Transfer (5%), DL Renewal (5%), Drive Test Appointments (4%).

---

## Miles Chatbot: Evolution Roadmap

The roadmap shows a clear pattern from **rule-based → semantic → generative → predictive:**

| Date | Milestone | What Changes |
|------|-----------|-------------|
| March '25 | **Content Cleanup** | Reduce QnA utterance noise — fewer dead-end responses |
| April '25 | **VR Status** | Customers check vehicle registration status via bot |
| Sept '25 | **Semantic Search** | Bot understands *meaning and context*, not just keywords |
| Nov '25 | **DL Status** | Customers check driver's license renewal status via bot |
| Dec '25 | **GenAI Convo Bot** | New knowledge base + content safety guardrails |
| Q1-Q2 '26 | **Predictive Caller** | Bot determines caller intent *before* connecting |
| Q1-Q2 '26 | **Title Transfer** | Full self-service title transfer via bot |

**Key takeaway for other departments:** You don't have to start at GenAI. Enter the roadmap at whatever stage matches your current maturity — even a keyword QnA bot that handles the top 5 call reasons creates immediate value.

---

## System 3: Service Advisor — AI-Driven Web Search

**Presenter:** Randolph L. Fernandez-Gonzalez | **Technology:** Semantic search + guided form-filling assistant

Integrated into [dmv.ca.gov](https://www.dmv.ca.gov/) at the **three highest-traffic touchpoints:** homepage search, site-wide search, and the [appointments page](https://www.dmv.ca.gov/portal/appointments/).

:::chart bar
| Query Category | Queries (K) |
|---------------|-------------|
| Real ID | 258 |
| Driver Permits | 209 |
| Release of Liability | 155 |
| Change of Address | 143 |
| Title Transfers | 121 |
| Registration | 109 |
| Appointments | 102 |
:::

---

## Service Advisor: Key Capabilities

### Not Just Search — It's an AI Assistant

- **Contextual answers** — Returns structured guidance, not just links. Searching "statement of facts" identifies the exact form (REG 256), explains all 6 uses, and offers a guided Form Filler.

- **Form Filler integration** — Walks users step-by-step through DMV forms. Enter your license plate, answer questions, and it generates a completed PDF.

- **Scam detection** — Recognizes known scam reference numbers and *immediately* surfaces fraud alerts: "The DMV will never ask for personal or financial information by text."

- **[mDL](https://www.dmv.ca.gov/portal/ca-dmv-wallet/) Q&A assistant** — Handles mobile driver's license questions with corrective actions when something goes wrong (e.g., "What do I do if my mDL request is rejected?").

- **Adaptable** — Same interface handles procedural guidance (Notice of Transfer walkthrough) and real-time crisis response (scam alerts).

**This is the most universally transferable pattern.** Every department has a website. Every website has a "How do I...?" problem.

---

## System 4: MyDMV — Identity Management & Automation

**Presenter:** Stefan Schoy | **Technology:** Multi-tier automated identity verification via [MyDMV](https://mydmv.dmv.ca.gov/) + biometric exploration

### The Problem → The Fix

| | Before | After |
|---|--------|-------|
| **Approach** | Single verification attempt | Two-tier (Level 1 → Level 2 fallback) |
| **Success Rate** | 35-40% | **90-95%** |
| **Failure Routing** | All failures → call center | Only double-failures → agent |
| **Document Flexibility** | Rigid single pathway | Multiple verification pathways |

### High-Risk Application Protections

For sensitive operations (phone number reset, replacement DL), the system adds external identity verification services — validating against third-party databases *in addition to* DMV records.

### Future: Biometric Verification

DMV is exploring selfie + camera comparison against the DL photo on file — for both [MyDMV](https://mydmv.dmv.ca.gov/) account creation and [CA DMV Wallet](https://www.dmv.ca.gov/portal/ca-dmv-wallet/) (mDL) issuance. Same face = verified identity = credential issued.

---

## System 5: Disaster Recovery App — Mobile Field Investigation

**Presenter:** Amy Burks | **Technology:** GIS-based mobile application for field data collection

### Real-World Application

Used by DMV investigators to locate and document vehicles destroyed in wildfires and other natural disasters. The mobile app:

- Maps investigation clusters using GIS (195 vehicles in Sacramento region alone)
- Enables on-site data collection via iPad
- Tracks investigation status in real-time
- Syncs field data with central databases

### Field Operations

Investigators physically locate burned vehicles at disaster sites — crawling under wreckage to read VINs, photographing damage, recording GPS coordinates — all feeding back through the app.

Less "AI" in the traditional sense, more **intelligent field data collection** — but the GIS clustering, mobile-first workflow, and real-time sync represent a model for any department with field operations.

---

## System 6: GenAI + Intelligent Automation for Personalized Plates

**Presenter:** Angela Marbray | **Technology:** Generative AI (content review) + RPA (plate assignment)

### The Origin Story

A 2020 lawsuit ([*Ogilvie v. Steve Gordon*](https://casetext.com/case/ogilvie-v-gordon-3)) exposed that plate configuration decisions were **subjective and inconsistent** across reviewers. The numbers told the story:

- **167,000** orders/year (~668/day)
- Only **4 reviewers** + 5 assignment staff
- **36,000 plate backlog**
- Up to **9 months** wait time
- **Inconsistent** approve/deny decisions

---

## Personalized Plates: The AI Solution

### Two-Part Fix

1. **Generative AI (Nov 2022):** Reviews plate configurations for offensive/inappropriate content. Makes approve/deny recommendations. Eliminated human bias and created consistency.

2. **Intelligent Automation (July 2023):** Assigns approved plates to vehicles automatically. Runs 24/7 — no breaks, no sick days, works beyond business hours.

### End-to-End Flow

**Intake** → **GenAI Assist** → **Staff Review** → **IA Assist** → **Fulfillment**

Online, Mail, Field Office, AAA → Machine review, flags & routing → **Final human decision** → Assigns plates to vehicles → [CALPIA](https://www.calpia.ca.gov/) Manufacturing

### Results

| Metric | Result |
|--------|--------|
| **IA processing rate** | 90% of all plate assignments |
| **AI approval rate** | 90% of AI recommendations confirmed by staff |
| **Wait time** | 2-4 months (was 9 months) — **50% reduction** |
| **Lawsuits** | **0** since implementation |

The human-in-the-loop design is why there are zero lawsuits. GenAI *recommends*, staff *decides*.

---

## The Master Pattern: Human in the Loop

Every one of DMV's 6 AI systems follows the same architecture:

1. **AI processes** — Extracts, classifies, recommends, routes
2. **Human decides** — Reviews flagged items, makes final call
3. **Automation executes** — Carries out the approved action

This isn't a coincidence. It's a deliberate design choice that:

- **Satisfies legal requirements** — Human accountability for decisions
- **Builds staff trust** — AI augments, doesn't replace
- **Survives scrutiny** — Personalized Plates has had zero lawsuits since implementation
- **Improves over time** — ML learns from human corrections

**This is the pattern other departments should adopt.** Not "AI replaces workers" — but "AI handles the 60-90% that's routine so workers can focus on the cases that actually need judgment."

---

## 6 Transferable Patterns for State Government

Each DMV system maps to a **reusable pattern** any department can adopt:

| Pattern | DMV System | What It Does | Universality |
|---------|-----------|-------------|-------------|
| **A** — Document Verification | RADV | OCR + ML validates documents against database | Any dept with paper intake |
| **B** — AI Chatbot | Miles | Voice/chat handles status checks + FAQs | Any dept with a call center |
| **C** — AI-Driven Search | Service Advisor | Semantic search + form filling on website | **Every department** |
| **D** — GenAI Content Review | Personalized Plates | AI reviews content, human decides | Any dept with subjective review |
| **E** — Mobile Field App | Disaster Recovery | GIS-based field data collection | Any dept with inspectors |
| **F** — Identity Verification | MyDMV | Multi-tier automated identity proofing | Any dept with online accounts |

---

## Pattern A: Document Verification (RADV Model)

**DMV capability:** ABBYY OCR/ICR + ML validation against database

### Fellowship Department Opportunities

| Fellow | Department | Transfer Opportunity |
|--------|-----------|---------------------|
| Henri Aghaei Baradaran | **DDS** | Regional center intake — ~460K clients served through 21 regional centers. OCR could auto-validate Lanterman Act applications and reduce 90-day processing backlogs. |
| Jeremiah Oakden | **CDTFA** | Tax return processing — sales tax returns, exemption certificates. CDTFA already digitizes returns; adding ML validation could flag mismatches before they reach auditors. |
| Nikki Hatcher / Brent Vanderburgh | **DWR / SWRCB** | Water right applications — records dating back to 1902 across thousands of active permits. Start with new applications (standardized forms), then tackle backfile conversion. |
| Bryanna McAdams | **DCSS** | Child support orders — income declarations across 47 county agencies. Each county submits slightly different paperwork; ML normalization across county formats is the high-value target. |
| Samantha Kissane / Chris Siino | **CDCR** | Inmate records, transfer paperwork, parole documentation. CDCR processes thousands of Form 128-Bs (classification chrono) monthly — many still handwritten. |
| SMSgt Blake Carter | **CA Air National Guard** | Personnel action forms, deployment orders. Military paperwork is highly standardized (DD-214s, SF-180s) — ideal for OCR with near-zero customization. |

:::collapse Why this transfers well
Document verification is the most **structurally similar** use case across departments. Every agency receives paper forms, validates them against a database, and routes failures for manual review. DMV proved the [ABBYY](https://www.abbyy.com/) platform scales from 37K to 309K documents with minimal additional configuration. The licensing model (per-page pricing) means departments can start small and scale.
:::

:::callout tip
**Pilot sizing:** Identify your top 3 highest-volume paper forms and run a 30-day submission count. That number × ABBYY's per-page rate gives you a pilot budget. DMV's data shows ~50% automation in year one — a reasonable baseline for any business case.
:::

---

## Pattern B: AI Chatbot (Miles Model)

**DMV capability:** Voice + chat bot handling 13.77M calls/year, evolving toward GenAI

### Fellowship Department Opportunities

| Fellow | Department | Transfer Opportunity |
|--------|-----------|---------------------|
| Lorna Brisco | **DGS** | Procurement support — vendor bid status, contract questions. DGS handles thousands of "Where's my PO?" calls; a status-check bot could deflect 40%+ of that volume. |
| Jennifer Uyeda Issertell | **CDT** | Statewide IT help desk — password resets, service tickets, system status. CDT's ServiceNow platform already has structured data; a bot layer on top is straightforward. |
| Jeremiah Oakden | **CDTFA** | Taxpayer inquiries — "When is my return due?" "What's my balance?" These are the exact same query types Miles handles for DMV, just with tax data. |
| Bryanna McAdams | **DCSS** | Already has Customer Connect 24/7 — but it's keyword-based. DMV's semantic search roadmap shows the upgrade path to context-aware responses. |
| Lt. Marc Peachey | **CHP** | Accident report status, permit questions, commercial vehicle requirements. CHP's call center handles 2M+ calls/year — strong deflection potential. |
| Molly Linares | **CA Volunteers** | Volunteer matching + program questions. Lower call volume makes this a natural low-risk pilot environment. |
| Kattya Trinh | **OTSI/CalHHS** | Medi-Cal questions, benefit status, provider lookup. CalHHS already has structured eligibility data; a chatbot reduces the burden on county eligibility workers. |

:::collapse The chatbot maturity ladder
DMV's roadmap shows 5 stages that departments can enter at any point:
1. **Keyword QnA** — Match questions to canned answers (cheapest, simplest)
2. **Status Lookup** — Authenticate caller, query database, return status
3. **Semantic Search** — Understand *meaning*, not just keywords
4. **GenAI Conversational** — Generate answers from knowledge base with guardrails
5. **Predictive** — Determine caller intent before they ask
:::

:::callout tip
**Where to enter:** A department's top 10 call reasons usually reveal the right starting stage. If 3+ are simple status checks or FAQ lookups, Stage 1 (keyword QnA) delivers value with minimal investment.
:::

---

## Pattern C: AI-Driven Search (Service Advisor Model)

**DMV capability:** Semantic search on website with form-filling assistance

### The Most Universally Transferable Pattern

**Every single department represented in the Fellowship** has a public-facing website with a search function. DMV proved that an AI-driven search overlay handles 1M+ queries/year and directly reduces call center volume.

### Specific High-Value Targets

| Fellow | Department | Use Case |
|--------|-----------|----------|
| Kannan Krishnan | **OEHHA** | [Proposition 65](https://oehha.ca.gov/proposition-65) chemical hazard lookup — businesses search the Prop 65 list thousands of times daily. An AI search overlay could interpret plain-English queries ("Is BPA in baby bottles covered?") instead of requiring exact chemical names. |
| Will Robinson | **LCI** | [CEQA](https://opr.ca.gov/ceqa/) guidance — notoriously complex regulations that generate constant "How do I comply?" questions. A semantic search advisor could cut the learning curve for new project applicants. |
| Christina Marin-Fitzhugh | **CARB** | ZEV compliance, emission regulations, Cap-and-Invest. Fleet operators need to understand complex compliance pathways — a guided advisor replaces the current "call us" experience. |
| Ben Bressette | **Caltrans** | Project status, encroachment permits, traffic data. Caltrans.ca.gov is one of the state's highest-traffic sites; an AI search layer would serve millions of visitors. |
| *All Fellows* | *All Departments* | Form-filling assistance for any publicly available government form |

The **Form Filler** capability alone is worth the investment. DMV walks users through REG 256 (Statement of Facts) step by step — imagine that for tax forms (CDTFA), water right applications (DWR/SWRCB), or child support forms (DCSS).

:::callout tip
**The simplest business case:** Monthly "How do I...?" call volume × average handling time = the hours an AI search overlay could reclaim. DMV deployed theirs on an existing website without rebuilding anything.
:::

---

## Pattern D: GenAI Content Review (Plates Model)

**DMV capability:** GenAI reviews content, makes recommendations, human makes final decision

### Fellowship Department Opportunities

| Fellow | Department | Transfer Opportunity |
|--------|-----------|---------------------|
| Samantha Kissane | **CDCR** | Inmate correspondence screening — flag threats/contraband language, staff makes the call. CDCR screens tens of thousands of pieces of mail monthly; GenAI pre-screening could cut reviewer workload by 60%+. |
| Christina Marin-Fitzhugh | **CARB** | Emission test result review — flag anomalous readings for inspectors. The pattern is identical: AI scans structured data, flags outliers, human investigates. |
| Kannan Krishnan | **OEHHA** | Chemical assessment triage — scan incoming papers for chemicals that need expedited Prop 65 listing review. Prioritization, not decision-making. |
| Jai London | **CMD** | Procurement bid screening — flag non-compliant submissions before they reach evaluators. Saves evaluator time on bids missing required sections. |
| SSgt Kelton Pisano | **CMD** | Wildfire cost claim review — flag outlier reimbursement requests against historical norms. The same "flag and route" architecture DMV uses for plates. |
| Elizabeth Betancourt | **Natural Resources** | EIR screening — summarize 500+ page environmental impact reports and flag key findings for reviewers. GenAI excels at structured summarization. |

:::collapse Why the Plates model is the gold standard
The Personalized Plates system is the purest example of "GenAI assist, human decide" in California government. It faced a real legal challenge ([Ogilvie v. Steve Gordon](https://casetext.com/case/ogilvie-v-gordon-3)), implemented GenAI as the fix, and has had **zero lawsuits since**. The 90% staff approval rate of AI recommendations proves the model is accurate. The 50% wait time reduction proves it's efficient. And the zero-lawsuit record proves it's legally sound.
:::

:::callout tip
**Good fit indicator:** Any review process where two staff members might reach different conclusions on the same item is a candidate for GenAI-assisted consistency. DMV's legal track record provides strong precedent for a business case.
:::

---

## Pattern E: Mobile Field App (Disaster Recovery Model)

**DMV capability:** GIS-based mobile app for field investigations

### Fellowship Department Opportunities

| Fellow | Department | Transfer Opportunity |
|--------|-----------|---------------------|
| Kattya Trinh | **OTSI/CalHHS** | Integrate with [All-Hazards Dashboard](https://www.nascio.org/awards/) (NASCIO award winner). CalHHS already has the data platform; a field collection app feeds it directly. |
| Lt. Marc Peachey | **CHP** | Accident investigation, MAIT teams. CHP investigators photograph scenes, measure skid marks, catalog debris — all currently on paper or ad-hoc tablets. A purpose-built GIS app standardizes the workflow. |
| SSgt Kelton Pisano | **CMD** | Wildfire deployment tracking — field app connected to cost dashboards. CMD deploys personnel across dozens of fire zones simultaneously; real-time location + status data replaces radio check-ins. |
| Elizabeth Betancourt | **Natural Resources** | Working lands assessments, post-fire landscape surveys. Field biologists currently carry paper checklists + GPS units + cameras separately; one app replaces three tools. |
| Brent Vanderburgh | **SWRCB** | Water rights field inspections — replace paper forms with GIS-enabled mobile. Inspectors visit remote sites with no cell coverage; offline-first design (sync when connected) is critical. |

The pattern: **mobile-first, GIS-enabled, offline-capable, syncs when connected.** Any department that sends people into the field with clipboards is leaving efficiency on the table.

:::callout tip
**Smallest viable pilot:** One inspection workflow, one data entry form with GPS auto-tagging, deployed on iPads. DMV's disaster recovery app started exactly this small.
:::

---

## Pattern F: Identity Verification (MyDMV Model)

**DMV capability:** Multi-tier identity proofing with external verification services

### The Biggest Strategic Multiplier

| Fellow | Department | Transfer Opportunity |
|--------|-----------|---------------------|
| Jennifer Uyeda Issertell | **CDT** | Offer identity verification as a **shared service** for all state departments. CDT is the natural platform owner — one implementation, every department benefits. |
| Bryanna McAdams | **DCSS** | Parent identity verification for child support portal. DCSS serves 1.2M cases across 47 counties; custodial parents logging in to check case status need reliable identity proofing. |
| Kattya Trinh | **OTSI/CalHHS** | Medi-Cal eligibility verification for 14M+ beneficiaries. CalHHS already partners with Login.gov; DMV's two-tier model would add a state-specific fallback layer. |

### Why This Is the Biggest Win

DMV solved the hardest problem in government digital services: **proving you are who you say you are** — at 90-95% success. If CDT offered this as a platform service, every department could skip years of development.

The [EDD fraud crisis](https://www.edd.ca.gov/about_edd/fraud.htm) proved what happens when identity verification fails — an estimated $10.4B to $32.6B in fraudulent claims during the pandemic. DMV's two-tier model (validate against internal records → fallback to external identity services) is the architecture the entire state should be using.

:::callout info
**Why this matters for every department:** Every agency offering online services needs identity verification. Today, each builds or buys its own. A shared service based on DMV's proven architecture would eliminate that duplication and raise the security floor statewide.
:::

---

## DMV Contacts & Your Internal Bridge

### DMV Innovation Team

| Name | Area | Email |
|------|------|-------|
| Adrian Monteon | Document Processing (RADV) | adrian.monteon@dmv.ca.gov |
| Sonia Huestis | Miles Chatbot | sonia.huestis@dmv.ca.gov |
| Randolph L. Fernandez-Gonzalez | Service Advisor | randolph.gonzalez@dmv.ca.gov |
| Stefan Schoy | MyDMV Identity | stefan.schoy@dmv.ca.gov |
| Amy Burks | Disaster Recovery App | amy.burks@dmv.ca.gov |
| Angela Marbray | GenAI Personalized Plates | angela.marbray@dmv.ca.gov |

### Your Internal Bridge

**Liyuan Guo** — DMV's own Innovation Fellow (EEO Officer) — is already in Cohort 1. She can serve as the liaison between DMV's innovation teams and Fellows from other departments.

---

## Key Takeaways

1. **Human in the loop is non-negotiable.** Every DMV AI system keeps a human making the final decision. The Personalized Plates flow (GenAI recommends → Staff decides → IA executes) survived legal challenge with zero lawsuits. That's your template.

2. **Identity verification is the biggest multiplier.** DMV proved 90-95% success at scale. If CDT offers this as a shared service, every department skips years of work.

3. **The chatbot roadmap is a replicable playbook.** Keyword QnA → Semantic Search → GenAI → Predictive. Enter at whatever stage matches your maturity.

4. **Start with the Service Advisor pattern.** Every department has a website. Every website has a search function. An AI-driven search overlay with form-filling assistance is the lowest-friction, highest-visibility win available.

5. **Don't start from scratch.** That's the whole point. DMV built the playbook — now use it.
