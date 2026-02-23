# Agentic Engineering for California State Government

> From Vibe Coding to Disciplined AI-Assisted Development

**Core Thesis:** AI can write code now. The question isn't whether to use it — it's whether to use it responsibly. Agentic engineering is the disciplined approach that makes AI-assisted development safe, auditable, and production-ready for government.

California Department of Technology | February 2026

---

## The Shift

Software development is being transformed by AI — faster than any technology shift in decades.

- **AI coding assistants** now write production-quality code across every major language
- **AI agents** can plan, execute, test, and refine entire features autonomously
- **Private sector adoption** is accelerating: 97% of developers use AI tools ([GitHub 2024 Survey](https://github.blog/news-insights/research/survey-ai-wave-grows/))
- **Government is behind** — most agencies are still in "pilot" or "experimentation" phase

Two distinct approaches have emerged for working with AI in development:

1. **Vibe coding** — informal, unstructured, prompt-and-pray
2. **Agentic engineering** — disciplined, governed, production-grade

The difference between them is the difference between a hobby project and a government system.

---

## What Is Vibe Coding?

The term was coined by **Andrej Karpathy** (former Tesla AI Director, OpenAI co-founder) in February 2025:

> "You just give in to the vibes, embrace exponentials, and forget that the code even exists."

### How It Works

- Prompt an AI model with a vague description
- Accept the generated code without thorough review
- Run it, see if it works
- If it breaks, prompt again
- No tests, no architecture, no documentation

### Where It's Useful

- Personal prototypes and experiments
- Learning and exploration
- Quick one-off scripts
- Hackathons and proof-of-concepts

### Where It's Dangerous

- **Any system handling PII or sensitive data**
- **Any system connected to production infrastructure**
- **Any system subject to audit, compliance, or legal requirements**
- **Any system that other people depend on**

Vibe coding produces code that *works* — until it doesn't. And in government, "until it doesn't" means data breaches, compliance violations, and systems that fail when people need them most.

---

## What Is Agentic Engineering?

Karpathy coined this term in February 2026 as the mature successor to vibe coding:

> "You are not writing the code directly 99% of the time. You are orchestrating agents who do, and acting as oversight. 'Engineering' to emphasize that there is an art & science and expertise to it."

### How It Works

- **Start with a plan** — define architecture, requirements, and constraints before prompting anything
- **Decompose into tasks** — break work into well-defined, testable units
- **AI executes, human reviews** — agents write code, humans validate correctness
- **Test relentlessly** — automated test suites let agents iterate until tests pass
- **Version control everything** — full audit trail of every change
- **Quality gates before production** — security scanning, code review, deployment approval

### The Key Distinction

| | Vibe Coding | Agentic Engineering |
|---|---|---|
| **Planning** | None | Design doc / spec first |
| **Testing** | Manual, ad hoc | Automated test suites |
| **Review** | Glance and ship | Structured code review |
| **Audit Trail** | None | Full version control history |
| **Security** | Hope for the best | Security scanning, human review |
| **Quality** | "It works on my machine" | CI/CD, quality gates |
| **Governance** | None | Risk-tiered oversight |

Sources: [Karpathy's X post (Feb 2026)](https://x.com/karpathy/status/2019137879310836075), [Addy Osmani deep-dive](https://addyosmani.com/blog/agentic-engineering/)

---

## Vibe Coding in Government Is a Liability

This is not a theoretical concern. Unstructured AI-generated code in government systems creates real risks:

### Security Risk
AI models can generate code with **injection vulnerabilities, hardcoded credentials, and insecure data handling**. Without security review, these ship to production. In government, that means potential exposure of PII, financial data, and critical infrastructure.

### Compliance Risk
State systems must comply with **SIMM 5305-F, SAM 4986.1, NIST frameworks**, and department-specific regulations. Vibe-coded systems have no documentation, no audit trail, and no evidence of compliance.

### Reliability Risk
NYC's MyCity chatbot cost **$600K** and was found giving **incorrect legal advice** on labor law, harassment, and tips. No domain validation. No human-in-the-loop. Classic vibe coding at city scale. ([AI Now Institute testimony, 2024](https://ainowinstitute.org/wp-content/uploads/2024/10/NYC-Council-Testimony_AI-Now_MyCity-Portal_September-2024.pdf))

### Accountability Risk
When AI-generated code fails, who owns it? Vibe coding has no answer. Agentic engineering does: **the human who reviewed, approved, and deployed it.**

**The position is clear: vibe coding has no place in production government systems.** Experimentation is healthy. Shipping unreviewed AI code to systems Californians depend on is not.

---

## Why California Needs Agentic Engineering

### The IT Cost Problem

:::columns

**The Numbers**

- **87%** of government IT projects over $6M fail or are challenged — only 13% succeed ([Standish Group](https://opencommons.org/CHAOS_Report_on_IT_Project_Outcomes))
- **3x** higher cost overruns in public sector vs. private sector ([McKinsey](https://www.mckinsey.com/industries/public-sector/our-insights/unlocking-the-potential-of-public-sector-it-projects))
- **3.9 years** average public sector project duration vs. 2.4 years private ([McKinsey](https://www.mckinsey.com/industries/public-sector/our-insights/unlocking-the-potential-of-public-sector-it-projects))
- **78%** of federal IT dollars spent maintaining legacy systems ([GAO-25-107795](https://www.gao.gov/products/gao-25-107795))

---

**California's Track Record**

| Project | Budget | Outcome |
|---------|--------|---------|
| **FI$Cal** (accounting) | $1.6B est. | 20 years, still incomplete |
| **MyCalPAYS** (payroll) | $373M spent | Terminated — never produced one clean paycheck |
| **CCMS** (courts) | $500M+ spent | Terminated — estimate grew from $260M to $1.9B |
| **BreEZe** (licensing) | $96M spent | Terminated — original budget was $28M |
| **EDD Systems** | $250M+ to Deloitte | Buckled during COVID — 40M calls/month unanswered |

Between 1994 and 2013, California **terminated or suspended 7 IT projects** after spending nearly **$1 billion**. ([CA State Auditor 2014-602](https://information.auditor.ca.gov/reports/summary/2014-602))

:::

---

## Why Projects Fail: The Structural Problem

The failures aren't random. **Waldo Jaquith** (former 18F, White House OSTP) identified the structural causes ([source](https://waldo.jaquith.org/blog/2025/01/government-software-millions/)):

1. **30-year cost spiral** — Each failed project becomes the cost benchmark for the next one. A $100M failure makes $200M seem reasonable.

2. **No defensible pricing** — Vendors provide ballpark figures, agencies average the responses, bids come back near that amount. No internal logic underlying the price tag.

3. **Mega-contracts bundle everything** — Build, host, help desk, documentation, maintenance — all crammed into single contracts that are too big to succeed.

4. **Outsourced control** — Agencies outsource so thoroughly they lose the ability to control outcomes. The contractor knows the system; the agency doesn't.

5. **Procurement-development disconnect** — Contracting says "specify everything upfront" (safest). Software development says "specifying everything upfront is dangerous."

### The Counterpoint

**Small projects work.** Projects under $1M succeed **90% of the time** (Standish Group). When 18F helped California apply modular contracting to the Child Welfare System, they reduced the **RFP from 1,500 pages to 10** and created a pool of 11 agile vendors. ([18F Blog](https://18f.gsa.gov/2016/03/22/helping-california-buy-a-new-child-welfare-system/))

**Agentic engineering naturally produces small, testable, modular deliverables** — the exact pattern that works in government.

---

## How Agentic Engineering Works

### The Workflow

```
1. PLAN        Human defines architecture, requirements, constraints
                ↓
2. DECOMPOSE   Break into well-defined tasks with acceptance criteria
                ↓
3. EXECUTE     AI agent writes code, runs tests, iterates
                ↓
4. REVIEW      Human reviews output against requirements
                ↓
5. TEST        Automated test suite validates correctness
                ↓
6. GOVERN      Security scan, code review, deployment approval
                ↓
7. DEPLOY      Production release through standard CI/CD
```

### Core Principles ([Addy Osmani](https://addyosmani.com/blog/agentic-engineering/))

- **Start with a plan** — Write a design doc before prompting anything. Decide on architecture. This is the step vibe coders skip.
- **Test relentlessly** — The single biggest differentiator. With tests, an AI agent can iterate until tests pass. Without tests, it declares "done" on broken code.
- **Own the codebase** — Documentation, version control, CI/CD, monitoring. The AI accelerates the work, but you're responsible for the system.
- **Structured oversight** — Quality gates, automated testing, and audit trails throughout. Agents generate artifacts, humans evaluate them.

### What This Looks Like in Practice

An IT Specialist building an internal tool:
1. Writes a 1-page spec: what the tool does, who uses it, what data it touches
2. Sets up a project with version control, test framework, and CI/CD
3. Describes each feature to the AI agent with clear acceptance criteria
4. Agent writes code and tests; specialist reviews each piece
5. Security scan runs automatically; specialist reviews flagged items
6. IT Supervisor approves deployment to production

**Total time:** Days to weeks, not months to years.

---

## Workstream 1: IT Staff — Force Multiplication

This is the primary workstream. **IT Specialists, developers, cybersecurity analysts, and system engineers** use agentic engineering to dramatically increase throughput — with the same headcount.

### Application Development

- IT Specialist who delivers 1 feature/week now ships **3-5**
- Development team of 4 that takes 6 months on a project delivers in **6 weeks**
- The backlog of internal tool requests that IT can't get to? **It shrinks**
- Legacy code that nobody wants to touch? AI agents can **analyze, document, and refactor it**

### Cybersecurity

- Security analysts orchestrate agents to **scan configurations, flag vulnerabilities, and draft remediation plans**
- Incident response: agents compile logs, identify indicators of compromise, and draft reports while analysts make judgment calls
- Compliance: automated checks against NIST, SIMM, and department-specific frameworks

### Infrastructure & Operations

- System engineers use agents to **automate deployment scripts, monitor configurations, and detect drift**
- Database administrators use agents for **query optimization, schema migration planning, and performance analysis**

### What Stays the Same

- **IT staff still own architecture** — the AI doesn't decide system design
- **IT staff still own security** — the AI doesn't approve deployments
- **IT staff still own production** — the AI doesn't operate critical systems unsupervised
- **Code still goes through CI/CD, testing, and human review**

### The Career Path

IT Specialists add agentic engineering as a **core competency** at every level — not a replacement for technical skill, but an amplifier of it:

| Level | Current Role | With Agentic Engineering |
|-------|-------------|--------------------------|
| **IT Specialist I** | Implements features, fixes bugs | Orchestrates agents for routine development; reviews AI output |
| **IT Specialist II** | Leads projects, advises management | Designs agent workflows; mentors team on agentic practices |
| **IT Specialist III** | Expert advisor, strategic leadership | Architects multi-agent systems; sets quality standards |
| **IT Supervisor I/II** | Manages IT staff, day-to-day ops | Governs agentic workflows; approves deployment of AI-generated code |
| **IT Manager I/II** | Strategic IT management | Sets department agentic engineering policy; manages risk framework |

---

## Workstream 2: Business Staff — AI-Powered Productivity

The line between "business" and "IT" is blurring. That's fine — we accommodate it with a **spectrum of capability**, not a binary.

### Tier A: AI-Assisted Work (All Staff)

**Any state employee** uses tools like [Poppy](https://www.genai.ca.gov/poppy/), Copilot, or domain-specific AI to accelerate their existing work.

- **Contracting officers**: Draft SOWs, analyze proposals, check compliance faster
- **HR analysts**: Process classifications, write duty statements, analyze workforce data
- **Policy staff**: Research regulations, draft policy memos, analyze legislative impacts
- **Program managers**: Generate reports, analyze program data, draft communications

**No code. No technical risk.** These are productivity tools, governed by existing CDT GenAI guidelines (TL 24-01, SAM 4986.1).

### Tier B: Technical Business Staff (Self-Service Tools)

**Some business staff have technical skills** — scientists, data analysts, engineers, researchers. They can and do build their own tools using AI-assisted development.

- Dashboards and data visualizations
- Workflow automations and process tools
- Analysis scripts and data pipelines
- Internal utilities for their team

**These are not enterprise systems.** They don't handle PII, don't connect to production databases, and don't serve the public. They're **team-level productivity tools** built by people who understand both the domain and the technology.

**Governance**: Department IT reviews for security and data handling. Standard acceptable-use policies apply.

### Tier C: Collaborative Development (Business + IT)

The highest-impact pattern: **domain experts partner with IT staff**. The domain expert brings irreplaceable knowledge of business rules, eligibility logic, and edge cases. The IT specialist brings architecture, security, and production engineering.

- Domain expert writes requirements and validates output
- IT specialist handles architecture, security review, and deployment
- Agentic tools accelerate both sides
- **Result**: Systems that actually reflect how the work gets done — built in weeks, not years

This is where the contractor cost reduction is most dramatic. The domain expert who used to brief a $200/hr contractor on policy rules now works directly with an IT specialist using AI agents. The contractor is no longer needed.

---

## The Governance Framework

Agentic engineering requires governance that **scales with risk** — not one-size-fits-all bureaucracy that kills adoption, and not zero oversight that creates liability.

### Risk Tiers

| Tier | Description | Examples | Governance |
|------|------------|----------|------------|
| **Tier 1** | Personal productivity | Poppy, AI-assisted drafting, data analysis | Existing CDT GenAI guidelines (TL 24-01, SAM 4986.1) |
| **Tier 2** | Internal team tools | Dashboards, automations, non-PII utilities | Department IT review; standard acceptable-use |
| **Tier 3** | Enterprise / production | Citizen-facing apps, PII systems, financial systems | Full CDT PAL process; security review; IT-owned deployment |

### Ownership Model

| Role | Tier 1 | Tier 2 | Tier 3 |
|------|--------|--------|--------|
| **Individual contributor** | Owns their use | Builds with IT review | Provides domain expertise |
| **IT Specialist** | N/A | Reviews and approves | Builds and deploys |
| **IT Supervisor/Manager** | N/A | Oversees governance | Approves production release |
| **CDT** | Sets GenAI policy | Sets standards | Oversees via PAL process |

### Non-Negotiables (All Tiers)

1. **Version control** — All AI-generated code is tracked in git
2. **Human review** — No AI-generated code ships without human approval
3. **Audit trail** — Every change is traceable to a person and a decision
4. **Security scanning** — Automated tools check for vulnerabilities before deployment
5. **Data classification** — Know what data your system touches; govern accordingly

This aligns with California's existing frameworks: **SIMM 5305-F** (GenAI risk assessment), **CDT Technology Letters** (TL 24-01, 24-03, 25-01), and **SAM 4986.1** (GenAI policy for responsible use).

---

## The Economics

### The Contractor Problem

Government pays a premium for outsourced development — and the knowledge leaves when the contract ends.

:::columns

**Contractor Costs**

- GSA-schedule software engineers: **$82-$196/hr** ([GSA CALC](https://info.winvale.com/blog/gsa-contract-awarded-labor-category-calc-tool))
- Systems integrators (Deloitte, Accenture) apply **2.0-2.5x wrap rates** — a developer paid $60/hr bills to government at $120-$150/hr ([Deltek](https://www.deltek.com/en/government-contracting/guide/federal-contracting/wrap-rate))
- Senior consultants at top firms: **$200-$400+/hr**
- Federal government pays contractors **1.83x** what equivalent employees cost ([POGO](https://www.pogo.org/reports/bad-business-billions-of-taxpayer-dollars-wasted-on-hiring-contractors))

---

**State Employee Costs**

- IT Specialist I: **$78K-$115K/yr** (~$37-$55/hr)
- IT Specialist II: **$95K-$130K/yr** (~$46-$63/hr)
- IT Specialist III: **$110K-$145K/yr** (~$53-$70/hr)
- Fully loaded (benefits, pension, overhead): add ~50%

Sources: [CalHR Pay Scales](https://eservices.calhr.ca.gov/EnterpriseHRPublic/payscales/payscalesearch), [CDT Career Paths (PDF)](https://cdt.ca.gov/wp-content/uploads/2023/11/State-IT-Class-Career-Path-Salary-Ranges.pdf)

:::

### The Math

An IT Specialist II with agentic engineering tools producing at **3-5x throughput** costs the state roughly **$63/hr fully loaded** — versus **$150-300/hr** for the contractor they replace.

That's not a marginal improvement. That's a **structural shift in the cost of building government technology.**

### What McKinsey Says

> "Outsourcing builds capacity, but insourcing builds capability." Nearly half of top-performing organizations plan to increase insourcing. ([McKinsey Global Tech Agenda 2026](https://www.mckinsey.com/capabilities/mckinsey-technology/our-insights/mckinsey-global-tech-agenda-2026))

### What Doesn't Change

Contractors are still needed for:
- Specialized expertise the state doesn't have
- Surge capacity for major initiatives
- Independent security assessments
- Legacy vendor systems during transition

The goal isn't zero contractors. It's **reducing dependency on contractors for routine development work that state staff can do better, faster, and cheaper with agentic tools.**

---

## Who's Already Doing This

### International Government

| Government | Initiative | Results |
|------------|-----------|---------|
| **UK Government** | AI coding assistant trial — 2,500 licenses across 50+ public sector orgs | **56 min/day saved per developer** (28 working days/year); 58% wouldn't go back ([GOV.UK Report](https://www.gov.uk/government/publications/ai-coding-assistant-trial/)) |
| **Singapore GovTech** | Pair chatbot + GitHub Copilot for public officers | **60,000+ users**, 46% admin time savings, 21-28% coding speed increase ([GovTech Pair](https://www.tech.gov.sg/products-and-services/for-government-agencies/productivity-and-marketing/pair/)) |
| **Australia DTA** | AI assistant across 60 agencies | **1 hr/day saved per employee** across 7,600 users ([Microsoft](https://www.microsoft.com/en-us/industry/blog/government/2025/04/16/)) |

### Federal Government

| Agency | Initiative | Results |
|--------|-----------|---------|
| **US Treasury** | AI fraud detection | **$4B prevented/recovered** in FY2024, up from $652.7M — 6x increase ([Treasury](https://home.treasury.gov/news/press-releases/jy2650)) |
| **GSA** | OneGov deal with Anthropic (Aug 2025) | Claude available to all 3 branches for **$1** — FedRAMP High ([GSA](https://www.gsa.gov/about-us/newsroom/news-releases/gsa-strikes-onegov-deal-with-anthropic-08122025)) |
| **GAO** | Federal AI use case tracking | Use cases **doubled** from 571 to 1,110 in one year; GenAI up 9x ([GAO-25-107653](https://www.gao.gov/products/gao-25-107653)) |
| **DoD** | GenAI.mil | Secure LLMs for **3 million** military, civil service, and contractor personnel ([Breaking Defense](https://breakingdefense.com/2026/01/pentagon-rolls-out-major-reforms-of-rd-ai/)) |

### California

California is already building the foundation:

- **Poppy**: State-built GenAI platform — 11 AI models, **58 departments, 2,348 employees** in pilot ([GenAI.ca.gov](https://www.genai.ca.gov/poppy/))
- **EO N-12-23**: First-in-nation state GenAI executive order — risk framework, procurement guidelines, training mandates ([Governor's Office](https://www.gov.ca.gov/2023/09/06/governor-newsom-signs-executive-order-to-prepare-california-for-the-progress-of-artificial-intelligence/))
- **20+ AI training programs**: Including GenAI certificate series, boot camps, partnerships with UC Davis, Sac State, and Cisco ([GenAI.ca.gov Training](https://www.genai.ca.gov/choose-your-journey/get-training/))
- **Innovation Fellows**: 21 state employees from 15 departments selected for creativity, not seniority ([ODI](https://innovation.ca.gov/our-work/governors-innovation-fellows-program/))
- **Innovation Council**: 30-member tech policy advisory council (Stanford HAI, UC Berkeley, Mozilla) ([Governor's Office](https://www.gov.ca.gov/2025/12/16/governor-newsom-launches-new-initiatives-to-partner-with-tech-policy-experts-and-accelerate-responsible-ai-in-state-government/))

**The foundation is laid. The next step is moving from AI-as-chatbot to AI-as-engineering-tool.**

---

## The Workforce Question

### AI Augments — It Doesn't Replace

This is not speculation. The data is in.

- **Radiology**: Geoffrey Hinton said "stop training radiologists" in 2016. By 2025, residency positions hit a **record 1,208** — a 4% increase. 75% of FDA-approved medical AI devices target radiology. Demand for radiologists has never been higher. ([TS2 Tech](https://ts2.tech/en/ai-was-supposed-to-replace-radiologists-by-2025-heres-why-it-didnt/))

- **UK coding trial**: Developers didn't lose jobs. They saved **28 working days per year** for higher-value work. 58% said they wouldn't go back. ([GOV.UK](https://www.gov.uk/government/publications/ai-coding-assistant-trial/))

- **Harvard Business School**: Study of 19,000 job tasks across 900 occupations found jobs requiring analytical/creative work saw **20% growth** in demand post-ChatGPT. ([HBS](https://www.library.hbs.edu/working-knowledge/enhance-or-eliminate-how-ai-will-likely-change-these-jobs))

- **Gartner**: By 2030, CIOs expect **0% of IT work** done by humans without AI, **75%** done by humans augmented with AI, 25% by AI alone. The augmented worker IS the future. ([Gartner](https://www.gartner.com/en/newsroom/press-releases/2025-11-10-gartner-survey-finds-artificial-intelligence-will-touch-all-information-technology-work-by-2030))

### What This Means for State Workers

- **IT staff** get more powerful tools, higher throughput, and a deeper skill set
- **Business staff** get faster workflows, better analysis tools, and — for those with technical skills — the ability to build their own solutions
- **Nobody loses their job because AI writes code.** People lose their jobs when their organization can't deliver and gets outsourced. Agentic engineering is the antidote to outsourcing.

### Union Alignment

Agentic engineering aligns with organized labor's AI principles:

- **AFSCME Resolution No. 7** (2024): Supports AI adoption with worker voice in design and implementation ([AFSCME](https://www.afscme.org/about/governance/conventions/resolutions-amendments/2024/resolutions/artificial-intelligence))
- **California Labor Federation**: Human oversight required, worker participation in technology design, no algorithmic management without guardrails ([CA Labor Federation](https://calaborfed.org/labors-principles-on-use-of-artificial-intelligence-automation-and-technology-in-the-workplace/))
- **The model fits**: Agentic engineering is human-orchestrated, not autonomous. Workers are in the design seat, not being designed around. It's insourcing, not outsourcing.

---

## What's Missing — And What to Build

California has the **policy foundation** (EO N-12-23, CDT Technology Letters) and the **awareness training** (Foundations of GenAI certificate, 20+ programs). What doesn't exist yet:

### Training Gap

| What Exists | What's Needed |
|-------------|---------------|
| GenAI awareness (Foundations certificate, ~42 hrs) | Agentic engineering for IT staff (structured development with AI agents) |
| Poppy chatbot training | AI-assisted productivity training for business staff by role |
| Ad hoc experimentation | Formalized training paths with certification |

### Governance Gap

| What Exists | What's Needed |
|-------------|---------------|
| SIMM 5305-F (GenAI risk assessment for procurement) | Risk-tiered governance for AI-generated code |
| CDT PAL process (for major projects) | Lightweight governance for Tier 2 internal tools |
| GenAI acceptable use policies | Code-specific policies: version control, testing, review requirements |

### Tooling Gap

| What Exists | What's Needed |
|-------------|---------------|
| Poppy (chatbot/assistant) | Development-grade AI tools (Claude Code, Copilot) with state security |
| Individual experimentation | Shared infrastructure: repos, CI/CD, testing frameworks for AI-assisted development |

---

## Recommended Next Steps

### Immediate (0-6 months)

1. **Pilot agentic engineering training** for CDT IT staff — start with the teams closest to the problem
2. **Establish the three-tier governance framework** for AI-generated code, aligned with existing SIMM/SAM/TL structures
3. **Identify 3-5 high-impact IT backlog items** for agentic engineering pilot projects
4. **Measure and report**: delivery time, cost, quality versus traditional development

### Near-term (6-18 months)

5. **Expand training** to department IT shops statewide
6. **Publish Tier 2 governance guidelines** for internal tool development by technical business staff
7. **Evaluate development-grade AI tools** (Claude Code, GitHub Copilot) for state network deployment
8. **Build the business case** from pilot data: contractor hours displaced, delivery acceleration, quality metrics

### Strategic (18+ months)

9. **Integrate agentic engineering competencies** into IT classification specifications (IT Specialist I/II/III)
10. **Scale collaborative development** (Workstream 2, Tier C) across departments
11. **Reduce contractor dependency** for routine AppDev based on demonstrated in-house capability
12. **Share findings** with other states and the federal government through existing channels (NASCIO, Code for America)

---

## The Bottom Line

- **Vibe coding is a toy.** Agentic engineering is a discipline.
- Government IT has a **$billion failure problem** driven by mega-contracts, outsourced control, and structural cost spirals
- Agentic engineering breaks the pattern: **small, testable, modular deliverables** — the exact approach that works
- **IT staff become 3-5x more productive** with the same headcount
- **Business staff at every level** get appropriate AI-powered productivity gains
- **Governance scales with risk** — not one-size-fits-all bureaucracy
- California already has the **policy foundation, training infrastructure, and executive support** to move

The question is no longer whether AI changes how government builds technology.

**The question is whether California leads or follows.**

---

## Sources & Further Reading

### Foundational
- [Karpathy — "Agentic Engineering" (Feb 2026)](https://x.com/karpathy/status/2019137879310836075)
- [Addy Osmani — Agentic Engineering Deep-Dive](https://addyosmani.com/blog/agentic-engineering/)
- [Anthropic — Building Effective Agents](https://www.anthropic.com/research/building-effective-agents)

### Government IT Costs & Failures
- [McKinsey — Public Sector IT Projects](https://www.mckinsey.com/industries/public-sector/our-insights/unlocking-the-potential-of-public-sector-it-projects)
- [GAO-25-107795 — Federal IT Legacy Systems](https://www.gao.gov/products/gao-25-107795)
- [CA State Auditor 2014-602 — IT Project Oversight](https://information.auditor.ca.gov/reports/summary/2014-602)
- [Waldo Jaquith — Why Government Software Costs So Much](https://waldo.jaquith.org/blog/2025/01/government-software-millions/)

### AI Adoption in Government
- [UK AI Coding Assistant Trial](https://www.gov.uk/government/publications/ai-coding-assistant-trial/)
- [Singapore GovTech Pair](https://www.tech.gov.sg/products-and-services/for-government-agencies/productivity-and-marketing/pair/)
- [GAO-25-107653 — Federal AI Use Cases](https://www.gao.gov/products/gao-25-107653)

### California Policy
- [EO N-12-23 — GenAI Executive Order](https://www.gov.ca.gov/2023/09/06/governor-newsom-signs-executive-order-to-prepare-california-for-the-progress-of-artificial-intelligence/)
- [GenAI.ca.gov — Poppy AI Assistant](https://www.genai.ca.gov/poppy/)
- [CDT Technology Letter 24-01](https://cdt.ca.gov/policy/technology-letters/technology-letter-24-01/)

### Workforce & Economics
- [Gartner — AI Will Touch All IT Work by 2030](https://www.gartner.com/en/newsroom/press-releases/2025-11-10-gartner-survey-finds-artificial-intelligence-will-touch-all-information-technology-work-by-2030)
- [McKinsey — Global Tech Agenda 2026](https://www.mckinsey.com/capabilities/mckinsey-technology/our-insights/mckinsey-global-tech-agenda-2026)
- [Deloitte — Human-AI Synergy in Government](https://www.deloitte.com/us/en/insights/industry/government-public-sector-services/ai-future-of-work-in-government/)
- [AFSCME Resolution No. 7 on AI](https://www.afscme.org/about/governance/conventions/resolutions-amendments/2024/resolutions/artificial-intelligence)
