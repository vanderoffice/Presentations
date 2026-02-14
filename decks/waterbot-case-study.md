# WaterBot: Building a Government AI Assistant

A RAG Chatbot Case Study for California Water Boards

<p class="thesis"><strong>Core Thesis:</strong> The AI model is the easy part. The knowledge base is what separates a hallucinating toy from a production system.</p>
<p class="meta">February 2026</p>

<style>
/* ── Annotated Screenshot System ── */
.annotated-ui {
  position: relative;
  display: inline-block;
  max-width: 100%;
  width: 100%;
  margin: 0.5rem 0;
}
.annotated-ui p { margin: 0; line-height: 0; }
.annotated-ui img { display: block; width: 100%; max-width: 100%; border-radius: 8px; }
.marker {
  position: absolute;
  width: 22px;
  height: 22px;
  border-radius: 50%;
  background: #d4a04a;
  color: #0f0f1a;
  font-weight: 700;
  font-size: 0.65rem;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 2px 8px rgba(0,0,0,0.6), 0 0 0 2px rgba(212,160,74,0.3);
  z-index: 10;
  transform: translate(-50%, -50%);
  pointer-events: none;
  font-family: system-ui, sans-serif;
}

/* ── Numbered Legend ── */
.legend {
  columns: 2;
  column-gap: 1.5rem;
  margin-top: 0.75rem;
  text-align: left;
}
.legend-item {
  display: flex;
  align-items: flex-start;
  gap: 0.5rem;
  font-size: 0.85rem;
  line-height: 1.3;
  break-inside: avoid;
  margin-bottom: 0.35rem;
}
.legend-num {
  flex-shrink: 0;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  background: #d4a04a;
  color: #0f0f1a;
  font-weight: 700;
  font-size: 0.65rem;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}

/* ── Stat Cards ── */
.stat-row {
  display: flex;
  gap: 1rem;
  margin: 1.5rem 0;
  flex-wrap: wrap;
}
.stat-card {
  flex: 1;
  min-width: 120px;
  background: rgba(255,255,255,0.04);
  border-radius: 10px;
  padding: 1rem 1.2rem;
  text-align: center;
  border-top: 3px solid #4a9eff;
}
.stat-card.gold { border-top-color: #d4a04a; }
.stat-card.green { border-top-color: #55f09a; }
.stat-card .stat-number {
  font-size: 2rem;
  font-weight: 700;
  color: #f2f2f8;
  line-height: 1.1;
}
.stat-card .stat-label {
  font-size: 0.9rem;
  color: #a5a5b8;
  margin-top: 0.25rem;
}

/* ── Comparison Grid ── */
.compare-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1rem;
  margin: 1rem 0;
  text-align: left;
}
.compare-card {
  background: rgba(255,255,255,0.04);
  border-radius: 10px;
  padding: 1rem;
  border-top: 3px solid #4a9eff;
}
.compare-card.gold { border-top-color: #d4a04a; }
.compare-card h4 { margin: 0 0 0.5rem 0; font-size: 1.05rem; }
.compare-card p, .compare-card li { font-size: 0.95rem; line-height: 1.5; }
.compare-card ul { padding-left: 1.2rem; margin: 0.5rem 0 0 0; }

/* ── Step Cards ── */
.step-card {
  background: rgba(255,255,255,0.04);
  border-radius: 10px;
  padding: 0.8rem 1rem;
  margin-bottom: 0.5rem;
  border-left: 3px solid #4a9eff;
  text-align: left;
}
.step-card .step-label {
  color: #4a9eff;
  font-weight: 600;
  font-size: 0.8rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-bottom: 0.15rem;
}
.step-card.gold { border-left-color: #d4a04a; }
.step-card.gold .step-label { color: #d4a04a; }
.step-card.green { border-left-color: #55f09a; }
.step-card.green .step-label { color: #55f09a; }
.step-card p { margin: 0; font-size: 0.95rem; }

/* ── Government Callout ── */
.gov-callout {
  background: rgba(212, 160, 74, 0.1);
  border-left: 3px solid #d4a04a;
  border-radius: 0 8px 8px 0;
  padding: 0.75rem 1rem;
  margin: 0.75rem 0;
  text-align: left;
  font-size: 0.95rem;
}
.gov-callout strong { color: #d4a04a; }
.gov-callout.blue {
  background: rgba(74, 158, 255, 0.1);
  border-left-color: #4a9eff;
}
.gov-callout.blue strong { color: #4a9eff; }
.gov-callout.red {
  background: rgba(255, 74, 74, 0.1);
  border-left-color: #ff6b6b;
}
.gov-callout.red strong { color: #ff6b6b; }

/* ── Tech Stack Grid ── */
.tech-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 0.75rem;
  margin: 1rem 0;
}
.tech-card {
  background: rgba(255,255,255,0.04);
  border-radius: 10px;
  padding: 0.8rem 1rem;
  text-align: center;
  border-bottom: 2px solid #4a9eff;
}
.tech-card.gold { border-bottom-color: #d4a04a; }
.tech-card .tech-icon { font-size: 1.5rem; margin-bottom: 0.3rem; }
.tech-card .tech-title { font-weight: 600; font-size: 1rem; color: #f2f2f8; margin-bottom: 0.2rem; }
.tech-card .tech-desc { font-size: 0.85rem; color: #a5a5b8; line-height: 1.3; }

/* ── Timeline ── */
.timeline {
  position: relative;
  padding-left: 2rem;
  margin: 1rem 0;
  text-align: left;
}
.timeline::before {
  content: '';
  position: absolute;
  left: 7px;
  top: 8px;
  bottom: 8px;
  width: 2px;
  background: rgba(74, 158, 255, 0.3);
}
.timeline-item {
  position: relative;
  margin-bottom: 0.75rem;
}
.timeline-item::before {
  content: '';
  position: absolute;
  left: -2rem;
  top: 6px;
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: #4a9eff;
  border: 2px solid rgba(74, 158, 255, 0.3);
  margin-left: 2px;
}
.timeline-item .tl-title {
  font-weight: 600;
  color: #4a9eff;
  font-size: 0.9rem;
}
.timeline-item .tl-desc {
  font-size: 0.85rem;
  color: #a5a5b8;
  margin-top: 0.1rem;
}

/* ── Feature Badge ── */
.feature-badge {
  display: inline-block;
  background: rgba(74, 158, 255, 0.15);
  color: #4a9eff;
  padding: 0.15rem 0.5rem;
  border-radius: 4px;
  font-size: 0.8rem;
  font-weight: 600;
}
.feature-badge.gold { background: rgba(212,160,74,0.15); color: #d4a04a; }
.feature-badge.green { background: rgba(85,240,154,0.15); color: #55f09a; }

/* ── Do/Don't Columns ── */
.do-dont {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.5rem;
  text-align: left;
}
.do-col, .dont-col {
  background: rgba(255,255,255,0.03);
  border-radius: 10px;
  padding: 1rem 1.2rem;
}
.do-col { border-top: 3px solid #55f09a; }
.dont-col { border-top: 3px solid #ff6b6b; }
.do-col h4 { color: #55f09a; margin: 0 0 0.75rem 0; }
.dont-col h4 { color: #ff6b6b; margin: 0 0 0.75rem 0; }
.do-col li, .dont-col li { font-size: 0.9rem; line-height: 1.5; margin-bottom: 0.3rem; }

/* ── Flow Diagram ── */
.flow-diagram {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.3rem;
  margin: 1.5rem 0;
  flex-wrap: wrap;
}
.flow-node {
  background: rgba(255,255,255,0.06);
  border-radius: 10px;
  padding: 0.6rem 0.8rem;
  text-align: center;
  border-bottom: 2px solid #4a9eff;
  min-width: 85px;
}
.flow-node.gold { border-bottom-color: #d4a04a; }
.flow-icon { font-size: 1.4rem; margin-bottom: 0.2rem; }
.flow-label { font-size: 0.8rem; font-weight: 600; color: #f2f2f8; }
.flow-sublabel { font-size: 0.7rem; color: #a5a5b8; margin-top: 0.1rem; }
.flow-arrow { font-size: 1.3rem; color: rgba(74, 158, 255, 0.5); }

/* ── Section Tag ── */
.section-tag {
  display: inline-block;
  background: rgba(212,160,74,0.15);
  color: #d4a04a;
  padding: 0.15rem 0.75rem;
  border-radius: 4px;
  font-size: 0.75rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  margin-bottom: 0.5rem;
}
</style>

---

## The Complexity Problem

California's water regulatory landscape: a maze of agencies, permits, and programs that overwhelms the people who need it most.

<div class="stat-row">
<div class="stat-card"><div class="stat-number">1</div><div class="stat-label">State Water Board</div></div>
<div class="stat-card"><div class="stat-number">9</div><div class="stat-label">Regional Boards</div></div>
<div class="stat-card gold"><div class="stat-number">100+</div><div class="stat-label">Permit Types</div></div>
<div class="stat-card gold"><div class="stat-number">58</div><div class="stat-label">Funding Programs</div></div>
</div>

**What if we could give every Californian access to the equivalent of a water regulation expert, 24/7, for free?**

---

## Meet WaterBot

A live, production AI assistant for California Water Boards — four ways to get help.

<div class="annotated-ui">

![WaterBot mode selector interface](../img/waterbot/chat-interface.png)

<span class="marker" style="top: 35%; left: 50%">1</span>
<span class="marker" style="top: 47%; left: 50%">2</span>
<span class="marker" style="top: 59%; left: 50%">3</span>
<span class="marker" style="top: 72%; left: 50%">4</span>
<span class="marker" style="top: 93%; left: 50%">5</span>
</div>

<div class="legend">
<div class="legend-item"><span class="legend-num">1</span><span><strong>Personalized Help</strong> — intake form gathers project context first</span></div>
<div class="legend-item"><span class="legend-num">2</span><span><strong>Just Chat</strong> — ask anything about CA water regulations</span></div>
<div class="legend-item"><span class="legend-num">3</span><span><strong>Permit Finder</strong> — interactive decision tree for permit types</span></div>
<div class="legend-item"><span class="legend-num">4</span><span><strong>Funding Navigator</strong> — eligibility checker for infrastructure funding</span></div>
<div class="legend-item"><span class="legend-num">5</span><span><strong>Disclaimer</strong> — always directs to official Regional Board sources</span></div>
</div>

---

## WaterBot in Action

A real conversation — user asks about NPDES permits, WaterBot responds with structured guidance and official links.

<div class="annotated-ui">

![WaterBot responding to NPDES permit question](../img/waterbot/chat-response-top.png)

<span class="marker" style="top: 7%; left: 62%">1</span>
<span class="marker" style="top: 17%; left: 30%">2</span>
<span class="marker" style="top: 55%; left: 38%">3</span>
<span class="marker" style="top: 90%; left: 30%">4</span>
</div>

<div class="legend">
<div class="legend-item"><span class="legend-num">1</span><span><strong>User question</strong> — plain English, no jargon required</span></div>
<div class="legend-item"><span class="legend-num">2</span><span><strong>Structured response</strong> — headings and bullets, not a wall of text</span></div>
<div class="legend-item"><span class="legend-num">3</span><span><strong>Inline link</strong> to SMARTS Portal — actionable, not just informational</span></div>
<div class="legend-item"><span class="legend-num">4</span><span><strong>Fee formula</strong> with current year — grounded in real regulatory data</span></div>
</div>

---

## The Full Experience

**Personalized Help** mode walks users through a 5-step intake so the AI knows their situation before answering.

<div class="step-card"><div class="step-label">Step 1 — Project Type</div><p>Construction, agricultural, municipal, industrial, or habitat restoration</p></div>
<div class="step-card"><div class="step-label">Step 2 — Location</div><p>County selection → maps to the correct Regional Water Board</p></div>
<div class="step-card"><div class="step-label">Step 3 — Discharge Details</div><p>Type and volume — determines which permits apply</p></div>
<div class="step-card"><div class="step-label">Step 4 — Water Rights & Federal Nexus</div><p>Existing rights? Federal permits? Changes the regulatory path.</p></div>
<div class="step-card gold"><div class="step-label">Step 5 — Applicant Profile</div><p>Business, individual, or municipality — plus DAC status for funding eligibility</p></div>

---

## The Permit Decision Tree

An interactive decision tree built from a 107KB JSON structure covering every permit pathway.

<div class="compare-grid">
<div class="compare-card">
<h4>How Most People Find Permits</h4>
<ul>
<li>Google "California water permit"</li>
<li>Land on the wrong Regional Board site</li>
<li>Still not sure which permit applies</li>
<li>Give up and call a consultant</li>
</ul>
</div>
<div class="compare-card gold">
<h4>How the Decision Tree Works</h4>
<ul>
<li>Answer 4-6 plain-language questions</li>
<li>Get the specific permit type you need</li>
<li>Direct link to the application portal</li>
<li>Total time: under 2 minutes</li>
</ul>
</div>
</div>

<div class="gov-callout">
<strong>Design principle:</strong> The tree doesn't replace the regulatory process — it helps people find the right starting point.
</div>

---

## The Funding Navigator

58 state and federal funding programs, matched by answering 5 plain-language questions — no AI hallucination risk.

<div class="compare-grid">
<div class="compare-card">
<h4>How Most People Find Funding</h4>
<ul>
<li>Google scattered agency sites</li>
<li>Read 200-page NOFAs</li>
<li>Miss programs they qualify for</li>
<li>Give up and hire a grant writer</li>
</ul>
</div>
<div class="compare-card gold">
<h4>How the Navigator Works</h4>
<ul>
<li>Answer 5 questions: org type, project, population, DAC status, matching funds</li>
<li>Get tiered results: <strong>Eligible</strong>, <strong>Likely</strong>, <strong>May Qualify</strong></li>
<li>Direct links to applications</li>
<li>AI enriches results with tips — but matching is deterministic</li>
</ul>
</div>
</div>

<div class="stat-row">
<div class="stat-card gold"><div class="stat-number">58</div><div class="stat-label">Programs Cataloged</div></div>
<div class="stat-card"><div class="stat-number">5</div><div class="stat-label">Questions Asked</div></div>
<div class="stat-card green"><div class="stat-number">3</div><div class="stat-label">Eligibility Tiers</div></div>
</div>

<div class="gov-callout">
<strong>Deterministic matching — no AI hallucination risk.</strong> Hard filters narrow the field; the AI only enriches results with application tips and deadline context.
</div>

---

## How It Actually Works: RAG

<span class="section-tag">How It Works</span>

**RAG — Retrieval-Augmented Generation.** Think of it as giving the AI a research assistant who pulls the right files before speaking.

<div class="compare-grid">
<div class="compare-card">
<h4>Without RAG</h4>
<ul>
<li>AI answers from memory (training data)</li>
<li>Can't cite specific sources</li>
<li>Hallucinates confidently</li>
<li>"I think the permit fee is around..."</li>
</ul>
</div>
<div class="compare-card gold">
<h4>With RAG</h4>
<ul>
<li>Searches a curated knowledge base first</li>
<li>Every claim cites a real source</li>
<li>Knowledge updates without retraining</li>
<li>"The CGP fee formula is $511 + ($54 × acres)"</li>
</ul>
</div>
</div>

---

## The Full Architecture

Six systems cooperate in about 2-3 seconds. None are exotic — React, PostgreSQL, and webhook APIs.

<div class="flow-diagram">
<div class="flow-node">
<div class="flow-icon">👤</div>
<div class="flow-label">User Asks</div>
<div class="flow-sublabel">React frontend</div>
</div>
<div class="flow-arrow">→</div>
<div class="flow-node">
<div class="flow-icon">🔗</div>
<div class="flow-label">Webhook</div>
<div class="flow-sublabel">n8n receives</div>
</div>
<div class="flow-arrow">→</div>
<div class="flow-node">
<div class="flow-icon">🔢</div>
<div class="flow-label">Embed</div>
<div class="flow-sublabel">OpenAI 1,536d</div>
</div>
<div class="flow-arrow">→</div>
<div class="flow-node">
<div class="flow-icon">🔍</div>
<div class="flow-label">Search</div>
<div class="flow-sublabel">pgvector top-8</div>
</div>
<div class="flow-arrow">→</div>
<div class="flow-node">
<div class="flow-icon">📋</div>
<div class="flow-label">Prompt</div>
<div class="flow-sublabel">Context + query</div>
</div>
<div class="flow-arrow">→</div>
<div class="flow-node gold">
<div class="flow-icon">🤖</div>
<div class="flow-label">Response</div>
<div class="flow-sublabel">Claude + citations</div>
</div>
</div>

<div class="gov-callout blue">
<strong>Key insight:</strong> The AI (steps 5-6) is the simplest piece. 80% of the effort is in curating, embedding, and tuning retrieval.
</div>

<div class="gov-callout">
<strong>n8n gotchas:</strong> <code>alwaysOutputData: true</code> prevents silent pipeline death on zero results. <code>escapeBraces()</code> in prompt templates avoids n8n expression collisions. Top-K = 8 chunks.
</div>

---

## The Stack

Every component is open-source or free-tier.

<div class="tech-grid">
<div class="tech-card"><div class="tech-icon">⚛️</div><div class="tech-title">React + Tailwind</div><div class="tech-desc">Frontend UI</div></div>
<div class="tech-card gold"><div class="tech-icon">🔄</div><div class="tech-title">n8n</div><div class="tech-desc">Workflow automation</div></div>
<div class="tech-card"><div class="tech-icon">🧠</div><div class="tech-title">OpenAI Embeddings</div><div class="tech-desc">text-embedding-3-small</div></div>
<div class="tech-card gold"><div class="tech-icon">🗄️</div><div class="tech-title">PostgreSQL + pgvector</div><div class="tech-desc">Vector database</div></div>
<div class="tech-card"><div class="tech-icon">🤖</div><div class="tech-title">Claude (Anthropic)</div><div class="tech-desc">Response generation</div></div>
<div class="tech-card gold"><div class="tech-icon">🐳</div><div class="tech-title">Docker on VPS</div><div class="tech-desc">Tailscale mesh networking</div></div>
</div>

---

## The Knowledge Base

<span class="section-tag">Knowledge Engineering</span>

The knowledge base is the product. The LLM is a commodity.

<div class="stat-row">
<div class="stat-card"><div class="stat-number">130</div><div class="stat-label">Markdown Files</div></div>
<div class="stat-card gold"><div class="stat-number">179</div><div class="stat-label">Database Chunks</div></div>
<div class="stat-card"><div class="stat-number">10</div><div class="stat-label">Categories</div></div>
<div class="stat-card gold"><div class="stat-number">313</div><div class="stat-label">Verified URLs</div></div>
</div>

Every fact is sourced from official California Water Boards publications with direct URLs.

---

## Inside the Knowledge Base

| Category | Coverage |
|----------|---------|
| **Permits & Compliance** | NPDES, WDR, 401 Cert, MS4, enforcement |
| **Funding Programs** | CWSRF, DWSRF, SAFER, Prop 4, federal grants |
| **Regional Boards** | All 9 regions — jurisdictions, contacts, priorities |
| **Water Quality** | TMDLs, impaired waters, beneficial uses |
| **Pollutants** | PFAS, lead, arsenic, nitrate, chromium-6 |
| **Consumer FAQ** | Tap safety, CCR reports, billing, hard water |
| **Conservation** | Usage targets, drought rules, Save Our Water |

---

## Why Chunking Strategy Matters

If you chunk badly, your retrieval will be bad — and no LLM can fix bad retrieval.

<div class="compare-grid">
<div class="compare-card">
<h4>Wrong: Arbitrary Splitting</h4>
<p>Split every 500 characters regardless of content:</p>
<pre style="font-size:0.75rem;background:rgba(0,0,0,0.3);padding:0.5rem;border-radius:6px;margin-top:0.5rem;overflow:hidden;">...discharge requirements for car
washes. The permit fee</pre>
<pre style="font-size:0.75rem;background:rgba(0,0,0,0.3);padding:0.5rem;border-radius:6px;margin-top:0.3rem;overflow:hidden;">schedule is as follows: $500 for
minor facilities...</pre>
<p style="font-size:0.85rem;color:#ff6b6b;margin-top:0.5rem;">Information split mid-sentence. Related content scattered.</p>
</div>
<div class="compare-card gold">
<h4>Right: Semantic Splitting</h4>
<p>Split on H2 headers — each chunk is a complete thought:</p>
<pre style="font-size:0.75rem;background:rgba(0,0,0,0.3);padding:0.5rem;border-radius:6px;margin-top:0.5rem;overflow:hidden;">## Fee Schedule
The permit fee for car washes is
$500 for minor facilities and
$1,200 for major facilities...</pre>
<p style="font-size:0.85rem;color:#55f09a;margin-top:0.5rem;">Complete section stays together. Self-contained and retrievable.</p>
</div>
</div>

<div class="gov-callout">
<strong>Our rule:</strong> Split on H2 headers. Max 2,000 chars, min 100. Overflow splits on paragraph boundaries — never mid-sentence.
</div>

---

## Quality Assurance Pipeline

This pipeline is what separates a demo from production.

<div class="step-card"><div class="step-label">1 — Semantic Chunking</div><p>Split on meaning, not character count. H2 headers define chunk boundaries.</p></div>
<div class="step-card"><div class="step-label">2 — Embedding Generation</div><p>OpenAI text-embedding-3-small → 1,536-dimension vectors per chunk.</p></div>
<div class="step-card"><div class="step-label">3 — Deduplication</div><p>MD5 hash check — duplicate chunks are invisible poison for retrieval.</p></div>
<div class="step-card"><div class="step-label">4 — URL Validation</div><p>313 URLs tested. Dead links destroy credibility.</p></div>
<div class="step-card"><div class="step-label">5 — Adversarial Testing</div><p>35 real-world queries from Reddit and forums — NOT self-generated.</p></div>
<div class="step-card gold"><div class="step-label">6 — Gap Analysis & Retest</div><p>Find what's missing, add content, re-embed, repeat until 100%.</p></div>

---

## Testing with Real Questions

<div class="gov-callout red">
<strong>Critical:</strong> We tested with real questions from Reddit, water operator forums, and agency FAQ pages — NOT questions we wrote ourselves. This prevents <strong>circular testing</strong>.
</div>

We measure **cosine similarity** — how closely a user's question matches content in the knowledge base. 0.0 = no match, 1.0 = identical. Above **0.40** means the system found relevant content to answer from.

<div class="stat-row">
<div class="stat-card gold"><div class="stat-number">35/35</div><div class="stat-label">Passed — every query found relevant content</div></div>
<div class="stat-card green"><div class="stat-number">0.59 avg</div><div class="stat-label">Strong retrieval across all queries</div></div>
<div class="stat-card"><div class="stat-number">0.40</div><div class="stat-label">Pass/fail threshold</div></div>
</div>

---

## Sample Results

| Real-World Query | Score | Verdict |
|-----------------|------:|---------|
| "Recycled water regulations California" | 0.79 | STRONG |
| "TMDL pollution limits explained" | 0.76 | STRONG |
| "SAFER funding eligibility" | 0.72 | STRONG |
| "How do I report a sewage spill?" | 0.51 | STRONG |
| "Is chromium-6 in my tap water?" | 0.63 | STRONG |

All 35 queries sourced from outside the content creation process. Non-circular methodology.

---

## What Testing Revealed

Experts build knowledge bases that answer expert questions. Real users ask beginner questions.

<div class="compare-grid">
<div class="compare-card">
<h4>Before: 64% Coverage</h4>
<ul>
<li>Strong on permits and enforcement</li>
<li>Good on regional board jurisdictions</li>
<li style="color: #ff6b6b;">Missing: "Is my tap water safe?"</li>
<li style="color: #ff6b6b;">Missing: "How do I read my water bill?"</li>
</ul>
</div>
<div class="compare-card gold">
<h4>After: 100% Coverage</h4>
<ul>
<li>Added 25 consumer FAQ documents</li>
<li>Added conservation program guides</li>
<li style="color: #55f09a;">Chromium-6: 0.34 → 0.63</li>
<li style="color: #55f09a;">Water billing: new → 0.52</li>
</ul>
</div>
</div>

---

## Less Is More: The Clean-Slate Rebuild

The counterintuitive move that made WaterBot production-ready.

<div class="stat-row">
<div class="stat-card"><div class="stat-number">1,286</div><div class="stat-label">Original Chunks</div></div>
<div class="stat-card gold"><div class="stat-number">179</div><div class="stat-label">After Rebuild</div></div>
<div class="stat-card green"><div class="stat-number">86%</div><div class="stat-label">Reduction</div></div>
<div class="stat-card gold"><div class="stat-number">100%</div><div class="stat-label">Coverage Maintained</div></div>
</div>

<div class="gov-callout">
<strong>When your RAG system underperforms, your instinct will be to add more content.</strong> Often the right move is to <em>remove</em> content. Noise drowns signal.
</div>

---

## Trust Architecture

Every design decision in WaterBot prioritizes accuracy and transparency.

<div class="step-card"><div class="step-label">Source Citations</div><p>Every response links to original documents. 313 URLs to official waterboards.ca.gov pages.</p></div>
<div class="step-card"><div class="step-label">Grounded Generation</div><p>System prompt: <em>"Answer using ONLY the provided context."</em> No creative fill-in.</p></div>
<div class="step-card"><div class="step-label">Disclaimer Transparency</div><p>"This is not legal advice. For official guidance, contact your Regional Water Board."</p></div>
<div class="step-card gold"><div class="step-label">No PII Collection</div><p>No login. No personal data stored. Session state lives in the browser only.</p></div>

---

## Infrastructure

:::columns

### The Docker Stack

25 Docker containers on a single VPS:

- **n8n** — Workflow automation
- **Supabase** — PostgreSQL + pgvector, Auth, REST API
- **nginx-proxy** — SSL/TLS via Let's Encrypt
- **Tailscale** — Encrypted mesh networking
- **Portainer** — Container management UI

Backups follow the **3-2-1 rule:** local, remote sync, offsite cloud.

---

### Monitoring

Real-time health monitoring:

- **Prometheus** — Metrics collection (4 targets)
- **Grafana** — Visual dashboards (109 panels)
- **Uptime Kuma** — Health checks every 60 seconds
- **ntfy** — Push notifications on failure

Alerts fire in under 2 minutes. Full rebuild from scratch in under an hour via Docker Compose.

:::

---

## One Pattern, Three Bots

The same architecture powers two other chatbots — proving the pattern is reusable.

<div class="stat-row">
<div class="stat-card"><div class="stat-number">179</div><div class="stat-label">WaterBot Chunks</div></div>
<div class="stat-card gold"><div class="stat-number">425</div><div class="stat-label">BizBot Chunks</div></div>
<div class="stat-card green"><div class="stat-number">1,402</div><div class="stat-label">KiddoBot Chunks</div></div>
</div>

<div class="compare-grid">
<div class="compare-card">
<h4>Same Infrastructure</h4>
<ul>
<li>Same PostgreSQL + pgvector database</li>
<li>Same n8n workflow pattern</li>
<li>Same OpenAI embedding model</li>
<li><strong>Shared component library</strong> — ChatMessage, DecisionTreeView, RAGButton all reused</li>
</ul>
</div>
<div class="compare-card gold">
<h4>Different Domains</h4>
<ul>
<li><strong>WaterBot</strong> — Water regs + permits + funding navigator</li>
<li><strong>BizBot</strong> — Business permits + license finder</li>
<li><strong>KiddoBot</strong> — Childcare resources + program finder</li>
<li>Each has its own KB, test suite, and specialized tools</li>
</ul>
</div>
</div>

---

## Lessons Learned

Every "don't" below is something we did and had to fix.

<div class="do-dont">
<div class="do-col">
<h4>Do</h4>
<ol>
<li>Spend 80% of time on the knowledge base, 20% on technology</li>
<li>Test with real user queries from outside your team</li>
<li>Use semantic chunking — split on meaning, not character count</li>
<li>Start with a narrow domain and go deep, not wide</li>
</ol>
</div>
<div class="dont-col">
<h4>Don't</h4>
<ol>
<li>Assume more data means better answers — noise drowns signal</li>
<li>Test with questions you wrote yourself — that's circular testing</li>
<li>Skip deduplication — duplicate chunks are invisible poison</li>
<li>Launch without URL validation — dead links destroy credibility</li>
</ol>
</div>
</div>

<div class="gov-callout">
<strong>Biggest lesson:</strong> We had 2 weeks of false confidence from circular tests. Real user questions from Reddit dropped coverage from "100%" to 64%.
</div>

---

## Your Blueprint

<span class="section-tag">Your Turn</span>

WaterBot was built in about **20 hours** by one person. Here's the breakdown.

<div class="step-card"><div class="step-label">Day 1 — Pick Your Domain & Write the KB</div><p>"All of Caltrans" is too wide. "Encroachment permits for District 4" is right. Write markdown files with source URLs — this is the bulk of the work.</p></div>
<div class="step-card"><div class="step-label">Day 2 — Database + Chunking</div><p>PostgreSQL + pgvector (Supabase = one container). Split on headers, embed with OpenAI, load. A 50-line script.</p></div>
<div class="step-card"><div class="step-label">Day 3 — Orchestration + Frontend</div><p>n8n webhook wires the pipeline visually. React chat UI POSTs to your webhook. No server code.</p></div>
<div class="step-card gold"><div class="step-label">Day 4-5 — QA Gauntlet</div><p>Deduplicate. Validate URLs. Test with real queries from outside your team. Find gaps, add content, retest.</p></div>

<div class="gov-callout">
<strong>Total:</strong> ~20 hours with one technical person. The knowledge base is the longest part — plan accordingly.
</div>

---

## Resources

**Try WaterBot now** — [vanderdev.net/waterbot](https://vanderdev.net/waterbot)

**Open source** — The knowledge base and frontend are available on GitHub

**Related Training:**
- Module 1: [Perplexity AI for Government](decks/perplexity-ai-gov-training-2026-02.html) — Research tools
- Module 2: [GitHub for Non-Coders](decks/github-for-non-coders-2026-02.html) — Collaboration
- Module 5: [RAG Quality Assurance](decks/rag-quality-assurance-2026-01.html) — QA methodology

**Tools Used:**
- [n8n.io](https://n8n.io) — Workflow automation (open source)
- [supabase.com](https://supabase.com) — Database + pgvector (open source)
- [openai.com](https://openai.com) — Embeddings API
- [anthropic.com](https://anthropic.com) — Claude API (LLM)
