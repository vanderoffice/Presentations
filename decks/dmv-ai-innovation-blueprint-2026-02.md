# DMV AI in Production: What Could Your Department Do With These Tools?

Governor's Innovation Fellows Program

**Core Thesis:** DMV has 6 AI systems in production saving thousands of staff hours annually. Every Fellowship department has problems these proven patterns already solve — the question is which ones fit your shop.

March 2026 | Based on DMV Innovation Tour, January 30, 2026

---

## Before You Read: How to Use This Deck

This deck is **prep material for the March 20 Fellows meeting.** Here's the plan:

1. **Now** — Read this deck. Find your department. Look at which DMV tools apply.
2. **Before March 20** — Have one conversation with someone in your shop. Ask: "If we had this, what would change?"
3. **March 20 meeting** — Bring your ideas. We'll discuss as a group.
4. **After the meeting** — A formal survey will capture everyone's ideas in writing.

This deck includes AI-generated suggestions for how DMV's tools might apply at each department. **Some will be on target; others will miss the mark entirely.** Only you and your department know where these patterns actually fit. That's the point — we need your expertise, not more AI guesswork.

**Skip to your department:** Use the left-hand navigation to jump to "Your Department at a Glance."

---

## Why This Matters

California DMV is running **six distinct AI/automation systems** in production — more than most state departments have even piloted.

The critical pattern: DMV uses AI as a **decision-support layer** (human stays in the loop), not full automation. This approach:

- Requires no new legislation
- Has survived legal challenge (Personalized Plates: zero lawsuits since GenAI implementation)
- Produces measurable, auditable results

The [Governor's Innovation Fellows Program](https://innovation.ca.gov/) puts 21 Fellows across **15 departments in 9 agencies** — every one of which has a direct opportunity to benefit from DMV's proven approach.

---

## 3 Focus Areas for March 20

For this meeting, we're focusing on the **three DMV systems with the broadest applicability** across Fellowship departments:

| Focus Area | What DMV Built | Why It Matters to You |
|-----------|---------------|----------------------|
| **Miles Chatbot** | Voice & chat AI handling **13.77M calls/year** — 49% now fully self-service | Every department has a call center or help desk. What would *your* Miles answer? |
| **RADV Document Verification** | OCR + ML auto-verifies **62% of documents** — saving **22,050 hours/year** (28 FTE) | Every department processes paper. Which forms eat the most staff time? |
| **MyDMV Identity Verification** | Multi-tier identity proofing at **90-95% success** (up from 35-40%) | Every department with online accounts needs identity verification. Where does proving identity create friction? |

DMV also has 3 additional systems covered later in this deck: Service Advisor (AI web search), Disaster Recovery App (mobile field ops), and GenAI for Personalized Plates (content review). Browse those for additional ideas.

---

## The Master Pattern: AI Assists, Humans Decide

Every one of DMV's 6 AI systems follows the same architecture:

1. **AI processes** — Extracts, classifies, recommends, routes
2. **Human decides** — Reviews flagged items, makes final call
3. **Automation executes** — Carries out the approved action

This isn't a coincidence. It's a deliberate design choice that:

- **Satisfies legal requirements** — Human accountability for decisions
- **Builds staff trust** — AI augments, doesn't replace
- **Survives scrutiny** — Personalized Plates has had zero lawsuits since implementation
- **Improves over time** — ML learns from human corrections

**This is the pattern other departments should look at.** Not "AI replaces workers" — but "AI handles the 60-90% that's routine so workers can focus on the cases that actually need judgment."

---

## The 6 AI Systems in Production

| # | System | AI Type | Launched | Key Metric |
|---|--------|---------|----------|------------|
| 1 | **Miles Chatbot** — Voice & Chat | NLP → GenAI | Ongoing | 13.77M calls/year handled |
| 2 | **RADV** — Document Verification | OCR/ICR + ML | 2020 | 5.4M docs/year, 62% automated |
| 3 | **MyDMV** — Identity Verification | Multi-tier Auth + Biometrics | Active | 90-95% verification success |
| 4 | **Service Advisor** — Web Search | Semantic Search | Active | 1M+ queries/year |
| 5 | **GenAI Plates** — Content Review | GenAI + RPA | Nov 2022 | 90% auto-processed, 0 lawsuits |
| 6 | **Disaster Recovery App** — Field Ops | GIS Mobile App | Active | 195 vehicles mapped (Sacramento region) |

Each system follows the same philosophy: **AI assists, humans decide.**

---

## Focus 1: Miles Chatbot — Voice & Chat AI

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

## Focus 2: RADV — Real ID Automated Document Verification

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

## Focus 3: MyDMV — Identity Management & Automation

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

## Your Department at a Glance — GovOps Agency

### CDT (Dept of Technology) — Jennifer Uyeda Issertell

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Miles-style Chatbot** | Statewide IT help desk bot — password resets, service tickets, system status. CDT's ServiceNow platform already has structured data; a bot layer on top could deflect 40%+ of routine calls. |
| **Identity Verification** | CDT could offer identity proofing as a **shared service** for all state departments. One implementation, every department benefits. Jennifer led the EDD Strike Team — she's seen firsthand what happens when identity verification fails at scale and call centers can't keep up. |

**Your question:** *From the EDD Strike Team experience — what were the top lessons about identity verification and call center overload? If CDT offered identity proofing as a shared service, which departments would benefit most immediately?*

### DGS (General Services) — Lorna Brisco

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Miles-style Chatbot** | DGS has 4 trainers for 4,000 employees. An internal knowledge bot handling policy questions, onboarding guidance, and procedure lookups could bridge the training gap that DGS can't staff for. Externally: vendors constantly call about bid status, contract questions, and Cal eProcure — a procurement status bot could deflect significant volume. |
| **Document Verification** | SB/DVBE certification processing and K-12 school construction plan reviews are high-volume document workflows where automated extraction could speed review cycles. |

**Your question:** *What are the top 5 questions DGS employees ask that training staff can't keep up with? For vendors — what do they call about most, and how much of that is simple status checks on Cal eProcure?*

### CDTFA (Tax & Fee Admin) — Jeremiah Oakden

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Miles-style Chatbot** | CDTFA collects $90B+ annually across 42 different programs — every retail business in California files with them. Taxpayer inquiries — "When is my return due?" "What's my balance?" — are the exact same query types Miles handles for DMV. Their Customer Service Center already publishes live wait times, signaling they know call volume is a problem. |
| **Document Verification** | Sales tax returns, exemption certificates, and cannabis compliance filings across hundreds of thousands of businesses. CDTFA already digitizes returns; adding ML validation could flag mismatches before they reach auditors. |

**Your question:** *Across CDTFA's 42 programs, which generate the most customer service contacts? What percentage of calls are simple status or deadline questions that could be self-service?*

---

## Your Department at a Glance — Health & Human Services

### DDS (Developmental Services) — Henri Aghaei Baradaran

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Document Verification** | DDS's 21 regional centers each process eligibility paperwork and Individual Program Plans for 491K+ consumers — but with no unified data system across centers. Automated verification of standardized eligibility forms could reduce the 120-day intake timeline. Henri's data analytics background positions him to identify which document types across centers have the most inconsistency. |

**Your question:** *Across DDS's 21 regional centers, which intake documents are most standardized — and which vary the most between centers? How long does eligibility determination actually take, and where in that process does paperwork create bottlenecks?*

### DCSS (Child Support) — Bryanna McAdams

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Miles-style Chatbot** | DCSS already has "Customer Connect 24/7" — but it's keyword-based. Bryanna's behavioral economics work focuses on reducing friction for specialized populations (military parents, formerly incarcerated parents, housing-insecure parents). A Miles-style chatbot that handles edge cases — not just "What's my balance?" but "I'm being released from custody, what happens to my child support order?" — would be a real differentiator. 1.04M+ open cases, $2.55B/year distributed. |
| **Document Verification** | Child support order verification — income declarations across 47 county agencies. Each county submits slightly different formats; ML normalization is the high-value target. |
| **Identity Verification** | Parent identity verification for the child support portal across 47 counties — reliable identity proofing reduces fraud and call center burden. |

**Your question:** *What are the top 5 reasons parents contact DCSS? For specialized populations (military, formerly incarcerated, housing-insecure) — where does the current Customer Connect 24/7 fall short?*

### OTSI/CalHHS — Kattya Trinh

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Miles-style Chatbot** | Kattya's All-Hazards Dashboard (NASCIO award winner) already aggregates data across CalHHS agencies for emergency response. The same coordination challenge exists for Californians navigating health and human services — they bounce between DHCS, DSS, DDS, and others. A benefit navigation chatbot that Kattya's OTSI team could coordinate across agencies is a natural extension of her cross-agency platform work. |
| **Identity Verification** | CalHHS agencies each verify identity independently — a shared identity layer (like DMV's model) serving DHCS, DSS, DDS from one platform would reduce duplication. Medi-Cal alone has 14M+ beneficiaries. |

**Your question:** *From your experience building the All-Hazards Dashboard — what are the biggest integration challenges when coordinating across CalHHS agencies? For Californians accessing health services, where does identity verification create the most friction?*

---

## Your Department at a Glance — Transportation Agency

### CHP (Highway Patrol) — Lt. Marc Peachey

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Document Verification** | CHP processes hundreds of thousands of collision reports (Form CHP 555) annually, plus commercial vehicle inspection reports and CAD records. Automated extraction from standardized collision report forms could speed data entry and improve the SWITRS collision database. |
| **Miles-style Chatbot** | CHP's primary call volume is 911 emergency dispatch (LA alone handles 2.7M calls/year) — that's fundamentally different from DMV's Miles model. But CHP's *non-emergency* public inquiries (collision report requests, commercial vehicle permit status, tow company licensing) could be deflected to self-service. |

**Your question:** *How many non-emergency public inquiries does CHP handle — collision report requests, permit questions, licensing status? What percentage of CHP's public-facing interactions are routine enough that a self-service tool could handle them?*

### Caltrans — Ben Bressette

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Miles-style Chatbot** | Encroachment permits went mandatory online in January 2025 — contractors and utilities now navigate CEPS digitally at $173/hr processing. A chatbot guiding applicants through the permitting process could reduce processing errors and call volume. Ben's Innovation Program is already focused on technology adoption across Caltrans's 12 districts. |

**Your question:** *Since CEPS went mandatory online in January, what are the most common questions applicants ask? How much staff time goes to helping contractors navigate the permitting process?*

---

## Your Department at a Glance — Natural Resources & Environment

### DWR (Water Resources) — Nikki Hatcher

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Miles-style Chatbot** | Nikki's procurement branch handles thousands of contracts with 3-18 month timelines across DWR's 29 State Water Project contractor agencies. Vendors and internal staff ask the same questions: "What's the status of my contract?" "What documents do I need for this solicitation?" A procurement chatbot could reduce the repetitive inquiries her team fields daily — and Nikki's 5% Contract Reduction Pilot is already measuring this kind of efficiency gain. |
| **Document Verification** | Contract compliance documents, dam safety inspection reports, and environmental impact reports are high-volume document types where automated extraction could flag errors before they stall the pipeline. |

**Your question:** *In your procurement branch, what are the most common questions staff and vendors ask repeatedly? Where in the contract lifecycle do document errors cause the most delays?*

### SWRCB (Water Board) — Brent Vanderburgh

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Document Verification** | Water rights division has 7M+ paper records dating to the 1800s. The $60M UPWARD initiative is already digitizing them; AI verification is the logical next step. Water quality lab data (chemistry samples across thousands of monitoring sites) needs anomaly detection — flagging outlier results before they hit compliance reports. |

**Your question:** *Which water rights document types have the highest error rates? In water quality monitoring, how much staff time goes to reviewing lab results that could be flagged automatically?*

### OEHHA — Kannan Krishnan

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **GenAI Content Review** | Kannan's core problem is that traditional chemical assessment methods are too slow. GenAI could triage incoming research papers, flag chemicals needing expedited Prop 65 listing review, and cross-reference new findings against the existing 900+ chemical list. This is the Personalized Plates pattern (AI reviews, human decides) applied to scientific literature screening. |
| **Service Advisor** | For businesses and attorneys querying the Prop 65 list: a semantic search tool that interprets plain-English queries ("Is BPA in baby bottles covered?") is more appropriate than a full chatbot for OEHHA's scale (~120 staff). |

**Your question:** *How many chemical assessments does OEHHA process annually, and what's the current timeline from "new research published" to "listing decision"? For Prop 65 queries from businesses — what are the most common questions, and how are they handled today?*

### CARB (Air Resources Board) — Christina Marin-Fitzhugh

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Miles-style Chatbot** | With 1,700+ employees, CARB's HR branch fields constant questions about hiring timelines, classification specs, leave policies, and health/safety protocols. An internal HR knowledge bot — "What's the process for an out-of-class assignment?" "How do I request a reasonable accommodation?" — could free Christina's team from repetitive inquiries. Department-wide: CARB's regulated entities (fleet operators, manufacturers, cap-and-trade participants) navigate fragmented compliance portals — a public-facing chatbot is a separate but large opportunity. |
| **Document Verification** | The new climate disclosure filings (SB 253/261, thousands of companies starting 2026) will create a surge of document processing on the regulatory side. |

**Your question:** *In CARB's HR branch, what are the most repetitive employee questions your team handles? On the regulatory side — what volume of new climate disclosure filings is CARB expecting in 2026, and how will they be processed?*

### CNRA (Natural Resources Agency) — Elizabeth Betancourt

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Document Verification** | Elizabeth's real initiative is ADA document remediation — AI-assisted accessibility compliance for ca.gov websites. This is the most broadly applicable project of any Fellow: a cross-cutting solution for all 170+ departments. For CNRA specifically: bond fund administration across 26+ entities involves massive document tracking and environmental review document summarization at the policy level. |

**Your question:** *Elizabeth — for the ADA remediation initiative, which document types across state government are the hardest to make accessible? At the agency level, where does document processing across CNRA's 26+ entities create the most coordination overhead?*

---

## Your Department at a Glance — Military, Corrections & Other

### CDCR (Corrections) — Samantha Kissane & Chris Siino

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Document Verification** | CDCR processes 20,000+ grievances/month, thousands of classification chronos (Form 128-B, many still handwritten), and workers' comp claims currently tracked in individual Excel spreadsheets with no centralized database. Employee files don't transfer between institutions — you can't even identify pattern claims (one employee with 6 claims on the same issue). Automated document extraction could tackle the grievance backlog alone. |
| **Identity Verification** | DMV's kiosk-based biometric approach could transform officer and inmate check-in/check-out across 31 institutions. |

**Your question:** *Which CDCR forms still rely on handwritten input? How many grievances does your institution process monthly, and how much staff time goes to data entry? For workers' comp — how are claims tracked today, and what happens when an employee transfers institutions?*

### CMD (Military Dept) — Jai London, SSgt Kelton Pisano & SMSgt Blake Carter

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Document Verification** | Military paperwork is highly standardized (DD-214s, SF-180s, deployment orders) — ideal for OCR with near-zero customization. Blake's A1 Connect platform already handles action item workflows across 5 Wings; AI document verification could extend it. Kelton's wildfire cost dashboards could integrate automated verification of reimbursement claims against historical norms. |
| **Miles-style Chatbot** | With dual state/federal pay systems and complex personnel rules, Guard members likely have repetitive questions about benefits, deployment status, and personnel actions. Jai's centralized procurement restructuring could also benefit from a vendor/internal FAQ bot. |

**Your question:** *Blake — what document types does A1 Connect handle, and where are the gaps? Kelton — for wildfire cost claims, how much review time goes to verifying completeness and flagging outliers? Jai — in centralized procurement, which document verification steps create the most bottlenecks?*

### LCI (Land Use & Climate Innovation) — Will Robinson

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **GenAI Content Review** | Will manages LCI's legislative portfolio across complex, overlapping policy domains (land use, climate, housing, tribal consultation). GenAI-assisted bill analysis — flagging conflicts with existing CEQA Guidelines, summarizing amendments, cross-referencing related bills — is something Will could use immediately. LCI is a small policy shop (~50-80 staff), not a service-delivery agency. |
| **Service Advisor** | LCI's Site Check mapping tool could integrate AI-driven search to help local governments and developers understand CEQA requirements for specific locations. |

**Your question:** *How many bills does LCI track per session, and how much staff time goes to cross-referencing new legislation against existing CEQA Guidelines? For local governments contacting LCI — what are the most common CEQA questions?*

### CA Volunteers — Molly Linares

| DMV Tool | What This Could Look Like |
|----------|--------------------------|
| **Miles-style Chatbot** | CaliforniaVolunteers runs the nation's largest statewide volunteer matching network — 68+ AmeriCorps programs, ~7,000 members at 1,000+ locations, initiatives targeting 10,000 mentors (Men's Service Challenge) and 55 campuses (College Corps). The "How do I find the right program?" question has real volume. Molly's digital delivery background (she built the ServiceForce database) means she's already thinking about platform UX. |
| **Document Verification** | Grant management across 68+ programs involves applications, renewals, performance reports, and financial reimbursements — a document processing pipeline. |

**Your question:** *How do volunteers currently find and match to opportunities — and where does that process break down at scale? For grant management across 68+ programs, which document types consume the most staff review time?*

---

## Questions to Bring to the March 20 Meeting

Before the meeting, try to find out:

1. **If your department had a Miles, what would people ask it?** Think about your call center, help desk, or front counter — what are the top 5 questions that come in over and over?

2. **What's your department's highest-volume paper form?** Roughly how many per month? Is it still partially handwritten or fully digital? How much staff time goes to processing it?

3. **Where does proving identity create friction?** For the public trying to access your services online — or for staff logging into systems. Where do people get stuck?

4. **If you could automate one repetitive review or intake task, what would it be?** The one where staff look at the same kind of document hundreds of times and make the same determination.

You don't need formal answers. A five-minute conversation with the right person in your shop will surface more than a week of desk research.

---

## What Happens Next

| Phase | What | When |
|-------|------|------|
| **Prep** | Read this deck, talk to your department | Now through March 20 |
| **Discuss** | Group discussion at monthly meeting | March 20 |
| **Capture** | Formal survey to memorialize ideas | After the meeting |
| **Discover** | Deep-dive session with DMV subject matter experts | TBD based on survey results |
| **Scope** | IT, security, costs, and implementation planning | After discovery — not before |

We're deliberately keeping the conversation at the **business-need level** for now. The technical details, security reviews, and cost estimates come later — once we know which patterns have the strongest fit across departments. First we figure out *what*, then we figure out *how*.

---

## Additional Reference: Service Advisor — AI-Driven Web Search

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

- **[mDL](https://www.dmv.ca.gov/portal/ca-dmv-wallet/) Q&A assistant** — Handles mobile driver's license questions with corrective actions when something goes wrong.

- **Adaptable** — Same interface handles procedural guidance (Notice of Transfer walkthrough) and real-time crisis response (scam alerts).

**This is the most universally transferable pattern.** Every department has a website. Every website has a "How do I...?" problem.

---

## Additional Reference: GenAI + Intelligent Automation for Personalized Plates

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

## Additional Reference: Disaster Recovery App — Mobile Field Investigation

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

4. **Start with the easiest win for your department.** Every department has a website, a call center, or a pile of paper forms. Pick the one that causes the most pain and look at how DMV addressed the same problem.

5. **Don't start from scratch.** That's the whole point. DMV has proven patterns in production — the opportunity is to adapt what works, not reinvent it.
