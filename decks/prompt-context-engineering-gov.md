# Prompt & Context Engineering for Government Work

From Good Questions to Great AI Output

<p class="thesis"><strong>Core Thesis:</strong> The difference between mediocre and exceptional AI output is almost never the AI — it's the prompt and context you give it. Master these fundamentals and you'll transform AI from a novelty into a daily force multiplier.</p>
<p class="meta">February 2026 · Module 4</p>

<style>
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
.step-card p { margin: 0; font-size: 0.95rem; }
.step-card.gold { border-left-color: #d4a04a; }
.step-card.gold .step-label { color: #d4a04a; }

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
.compare-card.warn { border-top-color: #a85454; }
.compare-card h4 { margin: 0 0 0.5rem 0; font-size: 1.05rem; }
.compare-card p, .compare-card li { font-size: 0.9rem; line-height: 1.5; }
.compare-card ul { padding-left: 1.2rem; margin: 0.5rem 0 0 0; }

/* ── Stat Cards ── */
.stat-row {
  display: flex;
  gap: 1rem;
  justify-content: center;
  margin: 1rem 0;
  flex-wrap: wrap;
}
.stat-card {
  background: rgba(255,255,255,0.04);
  border-radius: 10px;
  padding: 0.75rem 1.25rem;
  text-align: center;
  border-top: 3px solid #4a9eff;
  flex: 1;
  min-width: 120px;
}
.stat-card .stat-value {
  font-size: 1.5rem;
  font-weight: 700;
  color: #4a9eff;
  line-height: 1.2;
}
.stat-card .stat-label {
  font-size: 0.75rem;
  color: #a5a5b8;
  margin-top: 0.15rem;
}
.stat-card.gold { border-top-color: #d4a04a; }
.stat-card.gold .stat-value { color: #d4a04a; }

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
.feature-badge.warn { background: rgba(168,84,84,0.15); color: #a85454; }

/* ── Anatomy Diagram ── */
.anatomy-stack {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  margin: 1rem auto;
  max-width: 600px;
}
.anatomy-item {
  background: rgba(255,255,255,0.04);
  border-radius: 8px;
  padding: 0.6rem 1rem;
  text-align: left;
  display: flex;
  align-items: center;
  gap: 0.75rem;
}
.anatomy-item .anatomy-num {
  flex-shrink: 0;
  width: 28px;
  height: 28px;
  border-radius: 50%;
  background: #4a9eff;
  color: #0f0f1a;
  font-weight: 700;
  font-size: 0.75rem;
  display: flex;
  align-items: center;
  justify-content: center;
}
.anatomy-item .anatomy-label {
  font-weight: 600;
  color: #f2f2f8;
  font-size: 0.9rem;
}
.anatomy-item .anatomy-desc {
  font-size: 0.85rem;
  color: #a5a5b8;
}

/* ── Context Window Diagram ── */
.context-window {
  background: rgba(255,255,255,0.02);
  border: 2px solid #2a2a3a;
  border-radius: 12px;
  padding: 0.5rem;
  margin: 1rem auto;
  max-width: 550px;
  overflow: hidden;
}
.ctx-section {
  padding: 0.5rem 0.75rem;
  margin: 0.25rem 0;
  border-radius: 6px;
  text-align: left;
  font-size: 0.85rem;
}
.ctx-system { background: rgba(74,158,255,0.15); border-left: 3px solid #4a9eff; }
.ctx-history { background: rgba(168,84,168,0.12); border-left: 3px solid #9a6a9a; }
.ctx-retrieved { background: rgba(212,160,74,0.12); border-left: 3px solid #d4a04a; }
.ctx-tools { background: rgba(74,154,122,0.12); border-left: 3px solid #4a9a7a; }
.ctx-user { background: rgba(255,255,255,0.06); border-left: 3px solid #a5a5b8; }
.ctx-label { font-weight: 600; font-size: 0.8rem; }
.ctx-detail { font-size: 0.75rem; color: #a5a5b8; margin-top: 0.1rem; }

/* ── Flow Diagram ── */
.flow-diagram {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
  margin: 1.25rem 0;
  flex-wrap: wrap;
}
.flow-step {
  background: rgba(255,255,255,0.04);
  border-radius: 10px;
  padding: 0.85rem 1.1rem;
  text-align: center;
  font-size: 0.92rem;
  border-top: 3px solid #4a9eff;
  min-width: 110px;
}
.flow-step.gold { border-top-color: #d4a04a; }
.flow-step.teal { border-top-color: #4a9a7a; }
.flow-arrow {
  color: #65657a;
  font-size: 1.4rem;
  flex-shrink: 0;
}

/* ── U-Curve Diagram ── */
.u-curve {
  display: flex;
  align-items: flex-end;
  justify-content: center;
  gap: 3px;
  margin: 1rem auto;
  max-width: 500px;
  height: 120px;
  padding: 0 1rem;
}
.u-bar {
  flex: 1;
  border-radius: 4px 4px 0 0;
  min-width: 12px;
  max-width: 30px;
  transition: background 0.2s;
}
.u-bar.high { background: #4a9a7a; }
.u-bar.mid { background: #a85454; }
.u-bar.low { background: #6a3333; }

/* ── Prompt Example Box ── */
.prompt-box {
  background: rgba(255,255,255,0.03);
  border: 1px solid #2a2a3a;
  border-radius: 8px;
  padding: 0.75rem 1rem;
  margin: 0.5rem 0;
  text-align: left;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.82rem;
  line-height: 1.5;
  color: #d8d8e8;
}
.prompt-box .prompt-label {
  font-family: 'Inter', sans-serif;
  font-weight: 600;
  font-size: 0.7rem;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-bottom: 0.35rem;
  color: #a5a5b8;
}
.prompt-box.bad { border-color: #6a3333; }
.prompt-box.bad .prompt-label { color: #a85454; }
.prompt-box.good { border-color: #2a5a3a; }
.prompt-box.good .prompt-label { color: #4a9a7a; }

/* ── Checklist ── */
.checklist {
  text-align: left;
  margin: 0.75rem 0;
}
.checklist-item {
  display: flex;
  align-items: flex-start;
  gap: 0.5rem;
  font-size: 0.9rem;
  line-height: 1.4;
  margin-bottom: 0.35rem;
}
.checklist-icon {
  flex-shrink: 0;
  font-size: 0.85rem;
  margin-top: 0.1rem;
}
.check-yes { color: #4a9a7a; }
.check-no { color: #a85454; }

/* ── Two-Column Layout ── */
.two-col {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 1.25rem;
  margin: 0.75rem 0;
  text-align: left;
}
.two-col > div { font-size: 0.9rem; }
</style>

---

## Why This Matters

You've used AI. You've typed prompts. Sometimes the output is brilliant — sometimes it's garbage. **The variable isn't the AI. It's you.**

<div class="stat-row">
<div class="stat-card"><div class="stat-value">10x</div><div class="stat-label">Productivity gain with<br>well-crafted prompts</div></div>
<div class="stat-card gold"><div class="stat-value">80%</div><div class="stat-label">Of AI output quality<br>is determined by input</div></div>
<div class="stat-card"><div class="stat-value">~40%</div><div class="stat-label">Performance drop when<br>context is poorly structured</div></div>
</div>

This module teaches you to move from **casual AI user** to **intentional AI operator** — someone who consistently gets high-quality, compliant, useful output from every interaction.

<div class="gov-callout">
<strong>CDT Mandate:</strong> <a href="https://www.dgs.ca.gov/Resources/SAM/TOC/4900/4986-1/02-20-2025" target="_blank">SAM 4986.13</a> requires all state employees to complete GenAI training. This module builds on that foundation with practical skills you can use immediately.
</div>

---

## The Evolution: Prompts to Context Engineering

The field has moved fast. What worked in 2023 is already outdated.

<div class="flow-diagram">
<div class="flow-step"><strong>2023</strong><br>"Magic words"<br>era</div>
<div class="flow-arrow">→</div>
<div class="flow-step"><strong>2024</strong><br>Structured<br>prompts</div>
<div class="flow-arrow">→</div>
<div class="flow-step gold"><strong>2025-26</strong><br>Context<br>engineering</div>
<div class="flow-arrow">→</div>
<div class="flow-step teal"><strong>Now</strong><br>Agentic<br>workflows</div>
</div>

<div class="compare-grid">
<div class="compare-card">
<h4>Prompt Engineering (Old)</h4>
<ul>
<li>Focus on the <strong>question</strong> you type</li>
<li>"Add magic phrases to get better output"</li>
<li>One-shot: type a prompt, get an answer</li>
<li>Limited to what fits in a chat box</li>
</ul>
</div>
<div class="compare-card gold">
<h4>Context Engineering (Now)</h4>
<ul>
<li>Focus on <strong>everything the AI sees</strong></li>
<li>Curate the right information, examples, and constraints</li>
<li>Multi-turn: iterate, refine, build on previous output</li>
<li>Attach documents, use tools, retrieve knowledge</li>
</ul>
</div>
</div>

> **Andrej Karpathy** (OpenAI cofounder): *"Context engineering is the delicate art and science of filling the context window with just the right information for the next step."*

> **Tobi Lutke** (Shopify CEO): *"I prefer the term context engineering over prompt engineering. It describes the core skill better: the art of providing all the context for the task to be plausibly solvable by the LLM."*

---

## What Happens When You Hit Enter

Understanding the basics of how AI processes your input helps you write better prompts. You don't need to be an engineer — just know the flow.

<div class="flow-diagram">
<div class="flow-step"><strong>You type</strong><br>a prompt</div>
<div class="flow-arrow">→</div>
<div class="flow-step"><strong>Tokenizer</strong><br>breaks text<br>into tokens</div>
<div class="flow-arrow">→</div>
<div class="flow-step gold"><strong>Context<br>Assembly</strong><br>system + history<br>+ your message</div>
<div class="flow-arrow">→</div>
<div class="flow-step teal"><strong>AI Model</strong><br>processes<br>all tokens</div>
<div class="flow-arrow">→</div>
<div class="flow-step"><strong>Response</strong><br>generated<br>token by token</div>
</div>

**Tokens** are how AI reads text — roughly 1 token per ¾ of a word. "California Department of Technology" = ~5 tokens.

**The critical part is Context Assembly.** Your prompt is never processed alone. It's combined with:
- **System instructions** (set by the app developer — defines AI behavior)
- **Conversation history** (everything said so far in the chat)
- **Retrieved documents** (files, knowledge bases, search results)
- **Tool results** (data from web searches, calculations, API calls)

All of this competes for space in a fixed-size **context window** — AI's working memory.

---

## Context Windows: AI's Working Memory

A context window is the total amount of text an AI model can "see" at once. Think of it as a desk — everything needs to fit on the desk, or the AI simply can't see it.

<div class="stat-row">
<div class="stat-card"><div class="stat-value">200K–1M</div><div class="stat-label">Claude Opus 4.6<br>(1M beta)</div></div>
<div class="stat-card"><div class="stat-value">400K</div><div class="stat-label">GPT-5.2<br>(~300K words)</div></div>
<div class="stat-card gold"><div class="stat-value">1M</div><div class="stat-label">Gemini 3.1 Pro<br>(~750K words)</div></div>
</div>

**Context windows have exploded — even open-source models like Llama 4 Scout now offer 10M tokens.** Here's what today's windows look like in practice:

- **200K tokens** (Claude standard) ≈ 500 pages — a full policy manual + conversation history
- **400K tokens** (GPT-5.2) ≈ 1,000 pages — an entire agency's annual report suite
- **1M tokens** (Claude/Gemini) ≈ 2,500 pages — multiple codebases or years of legislation

<div class="context-window">
<div class="ctx-section ctx-system"><div class="ctx-label">System Prompt</div><div class="ctx-detail">Behavior rules, role definition, constraints (~100-1,000 tokens)</div></div>
<div class="ctx-section ctx-history"><div class="ctx-label">Conversation History</div><div class="ctx-detail">Everything said so far in the chat (grows each turn)</div></div>
<div class="ctx-section ctx-retrieved"><div class="ctx-label">Retrieved Documents</div><div class="ctx-detail">Uploaded files, knowledge base results, search results</div></div>
<div class="ctx-section ctx-tools"><div class="ctx-label">Tool Results</div><div class="ctx-detail">Web search data, API responses, calculation outputs</div></div>
<div class="ctx-section ctx-user"><div class="ctx-label">Your Current Message</div><div class="ctx-detail">The prompt you just typed</div></div>
</div>

<div class="gov-callout">
<strong>Why this matters:</strong> Even with million-token windows, your prompt is just one piece of what the AI sees. A well-structured prompt in a poorly managed context window will still produce poor results. Bigger desks don't help if they're covered in irrelevant paper — think about the <em>whole desk</em>, not just the note you're handing over.
</div>

---

## Anatomy of a Great Prompt

Every effective prompt has up to five components. You don't always need all five — but the more complex your task, the more components you should include.

<div class="anatomy-stack">
<div class="anatomy-item" style="border-left: 3px solid #4a9eff;">
<div class="anatomy-num">1</div>
<div><div class="anatomy-label">Role / Persona</div><div class="anatomy-desc">Who should the AI act as? "You are a senior policy analyst..."</div></div>
</div>
<div class="anatomy-item" style="border-left: 3px solid #d4a04a;">
<div class="anatomy-num" style="background:#d4a04a;">2</div>
<div><div class="anatomy-label">Context / Background</div><div class="anatomy-desc">What does the AI need to know? Agency, situation, constraints.</div></div>
</div>
<div class="anatomy-item" style="border-left: 3px solid #4a9a7a;">
<div class="anatomy-num" style="background:#4a9a7a;">3</div>
<div><div class="anatomy-label">Task / Instruction</div><div class="anatomy-desc">What exactly should the AI do? Be specific and actionable.</div></div>
</div>
<div class="anatomy-item" style="border-left: 3px solid #9a6a9a;">
<div class="anatomy-num" style="background:#9a6a9a;">4</div>
<div><div class="anatomy-label">Format / Output</div><div class="anatomy-desc">How should the response look? Bullet list, table, memo format, etc.</div></div>
</div>
<div class="anatomy-item" style="border-left: 3px solid #a85454;">
<div class="anatomy-num" style="background:#a85454;">5</div>
<div><div class="anatomy-label">Constraints / Guardrails</div><div class="anatomy-desc">What should the AI avoid? Length limits, tone, what NOT to include.</div></div>
</div>
</div>

> **Rule of thumb:** For quick questions, #3 alone is fine. For anything going into official work, use at least #2 through #5. The more stakes, the more structure.

---

## Before & After: Government Examples

The same AI, the same model, dramatically different results based on the prompt.

<div class="prompt-box bad">
<div class="prompt-label">Weak Prompt</div>
Write me a summary of the new water regulations.
</div>

<div class="prompt-box good">
<div class="prompt-label">Strong Prompt</div>
<strong>Role:</strong> You are a policy analyst at a California state water agency.<br><br>
<strong>Task:</strong> Summarize the key provisions of the 2025 updates to Title 23, Division 2 of the California Code of Regulations regarding water recycling.<br><br>
<strong>Format:</strong> Use a 3-section structure: (1) What changed, (2) Who is affected, (3) Implementation timeline. Use bullet points. Keep it under 400 words.<br><br>
<strong>Constraints:</strong> Focus only on agricultural reuse provisions. Do not include residential or industrial provisions. Cite specific section numbers where possible.
</div>

:::collapse More Government Examples

**Policy Memo**

<div class="prompt-box bad">
<div class="prompt-label">Weak</div>
Help me write a BCP narrative for more IT staff.
</div>

<div class="prompt-box good">
<div class="prompt-label">Strong</div>
You are a budget analyst at [Department]. Draft a Budget Change Proposal (BCP) narrative requesting 3.0 permanent IT positions (2 SSA and 1 SSMA) for the 2026-27 fiscal year. The positions will support the department's GenAI governance mandate under SAM 4986.<br><br>Structure the narrative with: (1) Problem statement citing specific workload metrics, (2) Proposed solution with classification justification, (3) Cost/benefit analysis with estimated annual costs using current CalHR salary ranges, (4) Consequences of not funding.<br><br>Tone: formal, data-driven. Audience: Department of Finance analysts.
</div>

**Summarizing Legislation**

<div class="prompt-box bad">
<div class="prompt-label">Weak</div>
What does SB 53 say?
</div>

<div class="prompt-box good">
<div class="prompt-label">Strong</div>
Summarize California SB 53 (Transparency in Frontier AI Act, effective January 2026). Cover: (1) Who it regulates, (2) Key requirements for frontier AI developers, (3) Enforcement mechanisms and penalties, (4) How it affects state agencies that procure AI systems.<br><br>Format as a 1-page executive briefing suitable for a non-technical CIO. Include the bill number and effective date at the top.
</div>

**Public Communications**

<div class="prompt-box good">
<div class="prompt-label">Strong</div>
Draft a public-facing FAQ (5 questions) about our department's new AI-assisted customer service chatbot. The audience is California residents with varying technical literacy. Tone should be reassuring, transparent, and plain language (8th grade reading level).<br><br>Must include: what data we collect, how to opt out and speak to a real person, and that AI-generated responses are reviewed by staff. This is required by SAM 4986.10 disclosure rules.
</div>

:::

---

## Prompt Library: Ready-to-Use Templates

Copy, adapt, and use these prompts for common government tasks. Each one uses the five-component structure.

<div class="prompt-box good">
<div class="prompt-label">Meeting Prep</div>
<strong>Role:</strong> You are my executive assistant.<br>
<strong>Context:</strong> I have a 30-minute briefing with [Deputy Director / stakeholder name] about [topic]. They care most about [budget impact / timeline / staffing].<br>
<strong>Task:</strong> Create a 1-page briefing sheet with: (1) 3 key talking points, (2) Anticipated questions with suggested responses, (3) One clear ask or decision I need from them.<br>
<strong>Format:</strong> Bullet points. Keep it to one page. Bold the ask.<br>
<strong>Constraints:</strong> No jargon. Assume the audience has 5 minutes to read this before the meeting.
</div>

<div class="prompt-box good">
<div class="prompt-label">Email Drafter</div>
<strong>Role:</strong> You are a senior state employee writing to [audience: team / executive / external stakeholder].<br>
<strong>Task:</strong> Draft an email about [topic]. The purpose is to [inform / request action / provide an update].<br>
<strong>Key points to include:</strong> [list 2-3 bullets]<br>
<strong>Tone:</strong> Professional but approachable. Keep it under 200 words.<br>
<strong>Constraints:</strong> Do not include any PII. End with a clear next step or call to action.
</div>

:::collapse More Ready-to-Use Templates

**Comparing Options / Alternatives Analysis**

<div class="prompt-box good">
<div class="prompt-label">Options Analysis</div>
<strong>Role:</strong> You are a policy analyst at [Department].<br>
<strong>Context:</strong> We need to decide between [Option A] and [Option B] for [project/initiative]. Budget is [amount]. Timeline is [deadline].<br>
<strong>Task:</strong> Create a comparison table with columns for: Option, Pros, Cons, Estimated Cost, Risk Level, Recommendation.<br>
<strong>Format:</strong> Markdown table followed by a 2-sentence recommendation with justification.<br>
<strong>Constraints:</strong> Be objective. Flag any assumptions you're making.
</div>

**Writing Procedures / SOPs**

<div class="prompt-box good">
<div class="prompt-label">Standard Operating Procedure</div>
<strong>Role:</strong> You are a process improvement specialist in state government.<br>
<strong>Task:</strong> Write a step-by-step SOP for [process, e.g., "onboarding a new hire to our team's AI tools"].<br>
<strong>Format:</strong> Numbered steps. Each step should include: the action, who is responsible, and any tools/forms needed. Add a "Common Mistakes" section at the end.<br>
<strong>Constraints:</strong> Assume the reader has never done this before. Reference SAM 4986 where relevant to AI tool access.
</div>

**Summarizing Long Documents**

<div class="prompt-box good">
<div class="prompt-label">Document Summary</div>
I'm attaching [document name — a 45-page audit report / legislative analysis / policy manual].<br><br>
<strong>Task:</strong> Provide a 3-level summary:<br>
1. <strong>Executive Summary</strong> (3 sentences max — what a CIO needs to know)<br>
2. <strong>Key Findings</strong> (5-7 bullet points with page references)<br>
3. <strong>Action Items</strong> (what our department needs to do in response)<br><br>
<strong>Constraints:</strong> Use the document's own terminology. Do not infer or add information not in the document. Flag anything that seems ambiguous.
</div>

**Editing & Tone Adjustment**

<div class="prompt-box good">
<div class="prompt-label">Tone Rewrite</div>
Here is a draft [memo / email / report section] I wrote:<br><br>
[paste your draft]<br><br>
<strong>Task:</strong> Rewrite this for [audience]. Adjust the tone to be [more formal / more accessible / more concise / more data-driven]. Keep all factual content intact.<br>
<strong>Format:</strong> Show me the rewritten version, then list the 3 biggest changes you made and why.
</div>

**Creating Training Materials**

<div class="prompt-box good">
<div class="prompt-label">Training Content</div>
<strong>Role:</strong> You are an instructional designer for state employee training.<br>
<strong>Context:</strong> I need to train [audience, e.g., "program managers with 10+ years experience but minimal AI exposure"] on [topic].<br>
<strong>Task:</strong> Create a 15-minute training outline with: learning objectives, 3 key concepts with real-world government examples, a hands-on exercise, and assessment questions.<br>
<strong>Constraints:</strong> Reading level should be accessible to non-technical staff. Include at least one California-specific example.
</div>

:::

---

## Prompting Techniques That Work

Different tasks call for different approaches. Here are the three you'll use most often.

<div class="compare-grid">
<div class="compare-card">
<h4>Zero-Shot</h4>
<p>Just ask. No examples needed. Works for simple, well-defined tasks.</p>
<div class="prompt-box" style="margin-top:0.5rem;font-size:0.78rem;">
"Translate this paragraph into plain language at an 8th-grade reading level."
</div>
<p><span class="feature-badge">Best for:</span> Simple transformations, summaries, translations</p>
</div>
<div class="compare-card gold">
<h4>Few-Shot</h4>
<p>Give examples of what you want. The AI mimics the pattern.</p>
<div class="prompt-box" style="margin-top:0.5rem;font-size:0.78rem;">
"Format these entries like this example:<br>
Input: John Smith, 2024-01-15, Sacramento<br>
Output: Smith, J. — Sacramento (Jan 2024)<br><br>
Now format these 50 entries the same way..."
</div>
<p><span class="feature-badge gold">Best for:</span> Data formatting, consistent style, structured output</p>
</div>
</div>

<div class="compare-grid">
<div class="compare-card" style="grid-column: span 2;">
<h4>Chain-of-Thought</h4>
<p>Ask the AI to <strong>reason step by step</strong>. Dramatically improves accuracy for complex analysis.</p>
<div class="prompt-box" style="margin-top:0.5rem;font-size:0.78rem;">
"Analyze whether this proposed regulation change is consistent with existing CalHR policy. Think through this step by step: (1) Identify the relevant existing policies, (2) Compare the proposed language against each one, (3) Flag any conflicts or gaps, (4) Provide your recommendation."
</div>
<p><span class="feature-badge">Best for:</span> Policy analysis, complex comparisons, multi-step reasoning, audit reviews</p>
</div>
</div>

<div class="gov-callout">
<strong>Counterintuitive finding:</strong> Chain-of-thought can actually <em>hurt</em> performance on simple tasks — research shows a <strong>36.3% drop</strong> when forcing step-by-step reasoning on tasks that don't need it. Match the technique to the task complexity.
</div>

> **When in doubt:** Start with zero-shot. If the output isn't right, add examples (few-shot). If the task requires reasoning, add "think through this step by step" (chain-of-thought). Note: the latest models (Claude Opus 4.6, GPT-5.2, Gemini 3.1) have **adaptive thinking** built in — they can dynamically decide when to reason deeper. But explicit CoT in your prompt still helps when you want to *see* the reasoning or control the analysis structure.

---

## Context Engineering: Beyond the Prompt

Your prompt is 5% of what the AI sees. The other 95% — the **context** — is where the real leverage is.

**Three ways to supercharge context:**

<div class="step-card"><div class="step-label">1. Attach Documents</div><p>Upload the actual policy, report, or legislation you're working with. Don't make the AI guess — <strong>give it the source material</strong>. In Perplexity, use Spaces to keep reference files persistent.</p></div>

<div class="step-card"><div class="step-label">2. Provide Examples</div><p>Show the AI what good output looks like. Paste a previous memo, a sample format, or an example response. The AI will match the pattern, tone, and structure.</p></div>

<div class="step-card"><div class="step-label">3. Set System Context</div><p>In tools that support it (Perplexity Spaces, Claude Projects), set persistent instructions: <em>"You are an analyst at [Department]. Always cite California code sections. Format responses as executive briefings."</em></p></div>

<div class="gov-callout">
<strong>CDT Compliance Note:</strong> When attaching documents, apply the <strong>Public Records Act test</strong> — would you be comfortable if this document appeared on a public website? If not, it likely contains confidential data that should NOT go into AI tools. See <a href="https://www.dgs.ca.gov/Resources/SAM/TOC/4900/4986-1/02-20-2025" target="_blank">SAM 4986.12</a> for acceptable use rules.
</div>

:::collapse Perplexity Spaces: Context That Persists

**Spaces** let you set up a project hub with persistent files and instructions:

1. Create a Space for your project (e.g., "2026-27 Budget Analysis")
2. Upload reference files: budget documents, prior year reports, relevant legislation
3. Set custom instructions: "Always reference FY amounts. Use Department of Finance formatting."
4. Every search within that Space automatically includes your files as context

This means the AI has your department's actual data — not generic internet knowledge — every time you ask a question.
:::

---

## The Lost in the Middle Problem

Here's a counterintuitive finding from <a href="https://direct.mit.edu/tacl/article/doi/10.1162/tacl_a_00638/119630/Lost-in-the-Middle-How-Language-Models-Use-Long" target="_blank">Stanford/MIT research</a>: AI pays the most attention to information at the **beginning** and **end** of its context. Information in the **middle gets overlooked** — even in models with massive context windows.

<div class="u-curve">
<div class="u-bar high" style="height:95%;" title="Position 1"></div>
<div class="u-bar high" style="height:85%;" title="Position 2"></div>
<div class="u-bar mid" style="height:60%;" title="Position 3"></div>
<div class="u-bar mid" style="height:50%;" title="Position 4"></div>
<div class="u-bar low" style="height:35%;" title="Position 5"></div>
<div class="u-bar low" style="height:30%;" title="Position 6"></div>
<div class="u-bar low" style="height:28%;" title="Position 7"></div>
<div class="u-bar low" style="height:32%;" title="Position 8"></div>
<div class="u-bar mid" style="height:45%;" title="Position 9"></div>
<div class="u-bar mid" style="height:55%;" title="Position 10"></div>
<div class="u-bar high" style="height:70%;" title="Position 11"></div>
<div class="u-bar high" style="height:85%;" title="Position 12"></div>
<div class="u-bar high" style="height:92%;" title="Position 13"></div>
</div>

<p style="text-align:center;font-size:0.8rem;color:#a5a5b8;">← Beginning of context &nbsp;&nbsp;|&nbsp;&nbsp; Middle (danger zone) &nbsp;&nbsp;|&nbsp;&nbsp; End of context →</p>

**What this means for you:**

- **Put the most important information first** in your prompts
- When pasting long documents, put your question **at the very end** (after the document)
- If you're analyzing a specific section, **extract and paste just that section** rather than uploading the entire 200-page document
- More context isn't always better — **curated context beats massive context**

> **In research terms:** The Stanford/MIT study found models actually performed *worse* when given documents with relevant info buried in the middle than with *no documents at all*. This pattern persists even in today's million-token models — bigger context with poor positioning actively hurts performance.

---

## How AI Gets Smarter: RAG & Knowledge Bases

When you use Perplexity or interact with a chatbot like <a href="https://vanderdev.net/waterbot" target="_blank">WaterBot</a>, the AI isn't just using its training data — it's **retrieving real information** first, then generating answers based on what it found.

This is called **Retrieval-Augmented Generation (RAG)**.

<div class="flow-diagram">
<div class="flow-step"><strong>Your<br>Question</strong></div>
<div class="flow-arrow">→</div>
<div class="flow-step gold"><strong>Search</strong><br>knowledge base<br>or the web</div>
<div class="flow-arrow">→</div>
<div class="flow-step"><strong>Retrieve</strong><br>most relevant<br>documents</div>
<div class="flow-arrow">→</div>
<div class="flow-step teal"><strong>Generate</strong><br>answer grounded<br>in real sources</div>
</div>

**Why RAG matters:**

- **Reduces hallucinations** — AI answers from retrieved facts, not memory
- **Stays current** — knowledge bases can be updated without retraining the model
- **Citable** — Perplexity shows inline citations; WaterBot references specific regulations

<div class="compare-grid">
<div class="compare-card">
<h4>Without RAG</h4>
<p>AI relies on training data (which has a cutoff date). May fabricate plausible-sounding but incorrect facts. No citations.</p>
</div>
<div class="compare-card gold">
<h4>With RAG</h4>
<p>AI searches real sources first, grounds its answer in retrieved documents, and can cite specific sources you can verify.</p>
</div>
</div>

> **Practical tip:** When using Perplexity, always click the citation numbers to verify sources — especially for facts going into official documents. RAG dramatically reduces hallucinations, but doesn't eliminate them entirely.

---

## Tool Use & Agentic AI

Modern AI doesn't just generate text — it can **use tools** and **take actions**. This is the "agentic" frontier.

<div class="compare-grid">
<div class="compare-card">
<h4>Perplexity (Tool Use)</h4>
<ul>
<li>Searches the live web for every query</li>
<li>Reads and synthesizes dozens of pages</li>
<li>Deep Research: multi-step research agent</li>
<li>Uploads: analyzes your PDFs and documents</li>
</ul>
<p><span class="feature-badge">You already use this</span></p>
</div>
<div class="compare-card gold">
<h4>Claude Code (Agentic Engineering)</h4>
<ul>
<li>Reads, writes, and edits code files</li>
<li>Runs terminal commands and tests</li>
<li>Plans multi-step tasks autonomously</li>
<li>Creates, deploys, and validates systems</li>
</ul>
<p><span class="feature-badge gold">The next frontier</span></p>
</div>
</div>

**The Agentic Loop:**

<div class="flow-diagram">
<div class="flow-step"><strong>Plan</strong><br>Break task<br>into steps</div>
<div class="flow-arrow">→</div>
<div class="flow-step gold"><strong>Act</strong><br>Call a tool<br>or run code</div>
<div class="flow-arrow">→</div>
<div class="flow-step teal"><strong>Observe</strong><br>Read the<br>result</div>
<div class="flow-arrow">→</div>
<div class="flow-step"><strong>Decide</strong><br>Done? Or<br>next step?</div>
<div class="flow-arrow">↺</div>
</div>

This is how Claude Code built this entire presentation — researching, writing markdown, building HTML, and deploying to GitHub Pages — in a single session. Agentic AI is the future of government technology work: fewer repetitive tasks, more strategic thinking.

---

## CDT Compliance: Know the Rules

California has one of the most comprehensive AI governance frameworks in the nation. These aren't suggestions — they're **policy**.

<div class="step-card gold"><div class="step-label">The Big Three</div><p>Every state employee using AI must follow these three rules from <a href="https://www.dgs.ca.gov/Resources/SAM/TOC/4900/4986-1/02-20-2025" target="_blank"><strong>SAM 4986</strong></a>:</p></div>

<div class="step-card"><div class="step-label">Rule 1: Approved Tools Only</div><p>Use <strong>only state-approved AI tools</strong> on state-approved equipment. Do not use your personal ChatGPT, Google Gemini, or other consumer AI accounts for state work. Do not register for AI tools using your state email without IT approval. (<a href="https://cdt.ca.gov/policy/technology-letters/technology-letter-24-01/" target="_blank">TL 24-01</a>)</p></div>

<div class="step-card"><div class="step-label">Rule 2: No Confidential Data in AI</div><p>Never enter PII, confidential, proprietary, or sensitive state data into AI prompts. This includes names, SSNs, case files, draft policies, vendor details, and employment records. <strong>Treat every prompt as if it were publicly visible.</strong></p></div>

<div class="step-card"><div class="step-label">Rule 3: Human Review Required</div><p>All AI output used for decision-making <strong>must</strong> have human verification. AI generates drafts, not final products. You are responsible for accuracy, bias review, and DEIA compliance. (<a href="https://www.dgs.ca.gov/Resources/SAM/TOC/4900/4986-1/02-20-2025" target="_blank">SAM 4986.12</a>)</p></div>

<div class="gov-callout">
<strong>The Golden Rule:</strong> Treat AI prompts as if they were subject to the <strong>California Public Records Act</strong>. If you wouldn't put it on a public website, don't put it in a prompt.
</div>

---

## Data Classification & AI

Not all data is created equal. California classifies data into categories — and your classification determines what can go into AI tools.

<div class="two-col">
<div>

**You CAN put in AI prompts:**

<div class="checklist">
<div class="checklist-item"><span class="checklist-icon check-yes">✓</span> Publicly available information</div>
<div class="checklist-item"><span class="checklist-icon check-yes">✓</span> Published reports and statistics</div>
<div class="checklist-item"><span class="checklist-icon check-yes">✓</span> General policy frameworks</div>
<div class="checklist-item"><span class="checklist-icon check-yes">✓</span> Public legislation and regulations</div>
<div class="checklist-item"><span class="checklist-icon check-yes">✓</span> Your own draft content for editing</div>
<div class="checklist-item"><span class="checklist-icon check-yes">✓</span> Non-sensitive meeting agendas</div>
</div>

</div>
<div>

**You CANNOT put in AI prompts:**

<div class="checklist">
<div class="checklist-item"><span class="checklist-icon check-no">✗</span> Names, SSNs, DOB, addresses (PII)</div>
<div class="checklist-item"><span class="checklist-icon check-no">✗</span> Medical or health records (PHI)</div>
<div class="checklist-item"><span class="checklist-icon check-no">✗</span> Draft policies or internal memos</div>
<div class="checklist-item"><span class="checklist-icon check-no">✗</span> Vendor/procurement details</div>
<div class="checklist-item"><span class="checklist-icon check-no">✗</span> Employment or investigation records</div>
<div class="checklist-item"><span class="checklist-icon check-no">✗</span> Passwords, API keys, credentials</div>
</div>

</div>
</div>

:::collapse The Full Data Classification Table

| Classification | Enterprise AI? | Consumer AI? | Notes |
|---|---|---|---|
| **Public** | Yes (with authorization) | Generally yes | Already widely available |
| **Confidential** | Only with explicit approval + security assessment | **Never** | Exempt from CA Public Records Act |
| **PII** | Only with privacy assessment + controls | **Never** | Names, SSN, addresses, DOB, photos |
| **Sensitive Personal** | Only with heightened protections | **Never** | Financial, biometric, health, genetic data |
| **Proprietary** | Only with explicit authorization | **Never** | Trade secrets, attorney-client privileged |

**Key policies:** <a href="https://www.dgs.ca.gov/Resources/SAM/TOC/4900/4986-1/02-20-2025" target="_blank">SAM 4986.10</a> (Privacy), <a href="https://cdt.ca.gov/policy/technology-letters/technology-letter-24-03/" target="_blank">TL 24-03</a> (Clarifications), <a href="https://cdt.ca.gov/policy/simm/" target="_blank">SIMM 5310-C</a> (Privacy Threshold Assessment)

As of January 2025 (<a href="https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202320240AB1008" target="_blank">AB 1008</a>), AI-generated data about individuals is classified as "personal information" under CCPA — meaning both your input AND the AI's output derived from personal data are subject to privacy law.
:::

---

## Human Review & Disclosure

AI generates **first drafts**, not final products. SAM 4986.12 is explicit: human verification is mandatory for any AI output used in decision-making.

**Best practices for human review:**

<div class="step-card"><div class="step-label">Form Your Own Assessment First</div><p>CDT guidance explicitly warns against <strong>anchoring bias</strong> — don't look at the AI output before forming your own initial assessment. Read the source material yourself first, then compare.</p></div>

<div class="step-card"><div class="step-label">Verify Claims & Citations</div><p>AI can generate citations that <em>look</em> real but don't exist. <strong>Click every link. Check every reference.</strong> Verify numerical data against authoritative sources.</p></div>

<div class="step-card"><div class="step-label">Review for Bias & DEIA</div><p>Check AI output for discriminatory language, embedded stereotypes, or exclusionary framing — especially for content affecting vulnerable populations.</p></div>

**When AI content is public-facing, you MUST include:**

<div class="checklist">
<div class="checklist-item"><span class="checklist-icon check-yes">✓</span> A disclaimer that AI was used (placed <strong>before</strong> the content, not after)</div>
<div class="checklist-item"><span class="checklist-icon check-yes">✓</span> Contact information for a real state employee</div>
<div class="checklist-item"><span class="checklist-icon check-yes">✓</span> An opt-out option to speak with a real person instead of AI</div>
</div>

<div class="gov-callout">
<strong>Required disclosure language:</strong> <em>"This [content type] has been generated, in whole or in part, using artificial intelligence."</em> — <a href="https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202320240SB896" target="_blank">SB 896</a> (CA AI Accountability Act, effective Jan 2025)
</div>

---

## Workflow: Drafting a Policy Memo

Here's a practical workflow for using AI to draft a policy document while staying compliant.

<div class="step-card"><div class="step-label">Step 1: Gather Context</div><p>Collect your source materials: relevant statutes, existing policy language, data/metrics, stakeholder input. <strong>Remove any PII or confidential data</strong> before uploading.</p></div>

<div class="step-card"><div class="step-label">Step 2: Research with Perplexity</div><p>Use Perplexity (or Deep Research for complex topics) to gather background: "What are other states' approaches to [topic]?" "What are the latest federal guidelines on [topic]?" Save citations.</p></div>

<div class="step-card"><div class="step-label">Step 3: Draft with a Structured Prompt</div><p>Use all five prompt components: role, context, task, format, constraints. Attach relevant documents. Be specific about audience and tone.</p></div>

<div class="step-card"><div class="step-label">Step 4: Iterate & Refine</div><p>Review the first draft critically. Ask for specific revisions: "Make the problem statement more data-driven." "Add a cost-benefit section." "Match the tone of [attached example]."</p></div>

<div class="step-card gold"><div class="step-label">Step 5: Human Review & Finalize</div><p>Verify all facts, citations, and data against authoritative sources. Review for bias. Add disclosure if needed. <strong>The final product is yours — you own the accuracy.</strong></p></div>

<div class="gov-callout">
<strong>Remember:</strong> AI is your research assistant and first-draft machine, not your replacement. The value you add is <strong>judgment, domain expertise, and accountability</strong> — things AI cannot provide.
</div>

---

## Workflow: Research & Legislative Analysis

Perplexity is particularly powerful for government research tasks. Here's how to use it effectively.

<div class="compare-grid">
<div class="compare-card">
<h4>Quick Lookups (Regular Search)</h4>
<ul>
<li>"What is the current CalPERS contribution rate for state employees?"</li>
<li>"When does AB 2013 take effect?"</li>
<li>"What is CDT's Technology Letter 24-01 about?"</li>
</ul>
<p><strong>Speed:</strong> 10-30 seconds | <strong>Sources:</strong> 5-10 pages</p>
</div>
<div class="compare-card gold">
<h4>Deep Analysis (Deep Research)</h4>
<ul>
<li>"Compare California's AI governance framework with the EU AI Act. Focus on risk classification."</li>
<li>"What are the fiscal impacts of the 2024 California AI legislation package?"</li>
<li>"Analyze trends in state IT procurement spending from 2020-2025."</li>
</ul>
<p><strong>Speed:</strong> Up to 3 min | <strong>Sources:</strong> 20-50+ pages</p>
</div>
</div>

**Pro tips for government research:**

- **Include specificity:** Agency names, bill numbers, date ranges, California-specific terms
- **Request citations:** "Cite the specific code section" or "Include the URL for each source"
- **Cross-reference:** Ask Perplexity to compare its findings against a specific document you upload
- **Use Spaces:** Create a Space for ongoing projects — upload baseline documents so every search has your context

> **For Module 1 veterans:** This builds on the Perplexity training (Module 1). If you haven't set up your free .gov Pro account yet, start there.

---

## Workflow: Data Analysis

AI can accelerate data work — from summarizing spreadsheets to identifying patterns in large datasets.

<div class="prompt-box good">
<div class="prompt-label">Example: Budget Data Analysis</div>
I'm attaching our department's FY 2024-25 expenditure data (CSV). Please:<br><br>
1. Summarize total spending by program area<br>
2. Identify the top 5 line items by dollar amount<br>
3. Flag any line items that increased more than 15% from the prior year<br>
4. Present results as a formatted table<br><br>
Note: This data contains only aggregate budget figures — no PII or confidential information.
</div>

**Best practices:**

- **Anonymize first** — remove names, IDs, and PII before uploading data to AI
- **State what the data contains** (and doesn't contain) so the AI processes it correctly
- **Ask for methodology** — "Explain how you calculated each figure" catches errors
- **Verify calculations independently** — AI math is generally reliable but not infallible

<div class="gov-callout">
<strong>CDT Compliance:</strong> Before uploading data to any AI tool, classify it per your department's data governance policy. Aggregate, de-identified, publicly available budget data is generally safe. Individual-level records, case data, and employee data are NOT. When in doubt, consult your Information Security Officer.
</div>

---

## The Iteration Loop

Great AI output almost never comes from a single prompt. It comes from **iteration** — a cycle of prompting, evaluating, and refining.

<div class="flow-diagram">
<div class="flow-step"><strong>Prompt</strong><br>Your initial<br>request</div>
<div class="flow-arrow">→</div>
<div class="flow-step"><strong>Evaluate</strong><br>Is the output<br>what you need?</div>
<div class="flow-arrow">→</div>
<div class="flow-step gold"><strong>Refine</strong><br>Be specific about<br>what to change</div>
<div class="flow-arrow">→</div>
<div class="flow-step teal"><strong>Repeat</strong><br>Until the<br>output is right</div>
<div class="flow-arrow">↺</div>
</div>

**Effective refinement prompts:**

<div class="step-card"><div class="step-label">Too Long</div><p>"Cut this to 250 words while keeping all key policy points."</p></div>
<div class="step-card"><div class="step-label">Wrong Tone</div><p>"Rewrite this for a non-technical executive audience. Remove all jargon."</p></div>
<div class="step-card"><div class="step-label">Missing Detail</div><p>"Add a section on fiscal impact. Include estimated costs using CalHR salary data."</p></div>
<div class="step-card"><div class="step-label">Wrong Format</div><p>"Convert this narrative into a comparison table with columns for: Current Policy, Proposed Change, Impact."</p></div>

> **Mindset shift:** Anthropic's own guide says to *"think of Claude as a brilliant but new employee who lacks context on your norms."* You'd never hand a new hire a task with zero context. Give the AI the same courtesy — and iterate like you would with a colleague.

---

## Common Mistakes & How to Avoid Them

<div class="compare-grid">
<div class="compare-card warn">
<h4>The Lazy Prompt</h4>
<p>"Summarize this document."</p>
<p><strong>Fix:</strong> What aspect? For what audience? In what format? How long? What should it emphasize?</p>
</div>
<div class="compare-card warn">
<h4>The Trust Fall</h4>
<p>Copying AI output directly into an official document without verifying.</p>
<p><strong>Fix:</strong> Always verify facts, citations, and calculations. AI is a draft machine, not an authority.</p>
</div>
</div>

<div class="compare-grid">
<div class="compare-card warn">
<h4>The Data Leak</h4>
<p>Pasting constituent names, case numbers, or confidential data into ChatGPT.</p>
<p><strong>Fix:</strong> Apply the PRA test before every prompt. Anonymize data. Use approved tools only.</p>
</div>
<div class="compare-card warn">
<h4>The One-Shot Wonder</h4>
<p>Accepting the first output without iterating.</p>
<p><strong>Fix:</strong> Expect 2-3 rounds of refinement. Each iteration should target a specific improvement.</p>
</div>
</div>

<div class="compare-grid">
<div class="compare-card warn">
<h4>The Kitchen Sink</h4>
<p>Dumping an entire 200-page document and asking a vague question.</p>
<p><strong>Fix:</strong> Extract the relevant section. Put key info at the beginning or end. Be specific.</p>
</div>
<div class="compare-card warn">
<h4>The Copy-Paste Zombie</h4>
<p>Taking AI output and pasting it into three different documents without adapting it for each audience.</p>
<p><strong>Fix:</strong> Each audience needs a different version. Ask the AI to rewrite for each context: "Now rewrite this for [audience] with [tone]."</p>
</div>
</div>

---

## Your AI Toolkit

Different tools for different jobs. Know when to reach for each one.

<div class="compare-grid">
<div class="compare-card">
<h4>Perplexity AI</h4>
<p><strong>Best for:</strong> Research, fact-finding, legislative analysis, current events</p>
<ul>
<li>Searches the live web with citations</li>
<li>Deep Research for multi-step analysis</li>
<li>Spaces for persistent project context</li>
<li>Free Pro for .gov emails</li>
</ul>
<p><a href="https://www.perplexity.ai" target="_blank">perplexity.ai</a> · <span class="feature-badge">Module 1</span></p>
</div>
<div class="compare-card gold">
<h4>Claude (Anthropic)</h4>
<p><strong>Best for:</strong> Writing, analysis, long-document processing, nuanced reasoning</p>
<ul>
<li>Opus 4.6 / Sonnet 4.6 — 200K standard, 1M beta context</li>
<li>Adaptive thinking with configurable effort levels</li>
<li>Strong on safety — constitutional AI with reason-based alignment</li>
<li>Projects feature for persistent context</li>
</ul>
<p><a href="https://claude.ai" target="_blank">claude.ai</a></p>
</div>
</div>

<div class="compare-grid">
<div class="compare-card" style="grid-column: span 2; border-top-color: #4a9a7a;">
<h4>Claude Code (Agentic Engineering)</h4>
<p><strong>Best for:</strong> Building systems, automating workflows, technical projects</p>
<ul>
<li>Reads, writes, and runs code autonomously</li>
<li>Plans multi-step tasks and executes them end-to-end</li>
<li>This entire presentation was built with Claude Code — from research to deployed slides</li>
<li>The future of how government technology teams will work</li>
</ul>
<p><a href="https://docs.anthropic.com/en/docs/claude-code" target="_blank">Claude Code docs</a> · <span class="feature-badge gold">Advanced</span></p>
</div>
</div>

---

## Key Takeaways

<div class="step-card gold"><div class="step-label">1. Context Over Cleverness</div><p>Don't obsess over finding the "perfect prompt." Instead, give the AI the right context: relevant documents, clear examples, specific constraints. What you feed the AI matters more than how you ask.</p></div>

<div class="step-card gold"><div class="step-label">2. Structure Your Prompts</div><p>Use the five components: Role, Context, Task, Format, Constraints. The more important the output, the more structure you should provide.</p></div>

<div class="step-card gold"><div class="step-label">3. Iterate, Don't One-Shot</div><p>Treat AI like a capable colleague, not a search engine. Have a conversation. Refine the output. Expect 2-3 rounds for quality work.</p></div>

<div class="step-card gold"><div class="step-label">4. Comply by Default</div><p>Know SAM 4986. Use approved tools. Never put confidential data in prompts. Always verify AI output. Disclose AI use in public-facing content.</p></div>

<div class="step-card gold"><div class="step-label">5. AI Augments, It Doesn't Replace</div><p>You bring judgment, domain expertise, and accountability. AI brings speed, breadth, and tireless first drafts. Together, you're unstoppable.</p></div>

---

## Resources & References

**California AI Policy**
- <a href="https://www.dgs.ca.gov/Resources/SAM/TOC/4900/4986-1/02-20-2025" target="_blank">SAM 4986 — GenAI Policy</a> (the primary policy document)
- <a href="https://www.gov.ca.gov/wp-content/uploads/2023/09/AI-EO-No.12-_-GGN-Signed.pdf" target="_blank">Executive Order N-12-23</a> (the foundational directive)
- <a href="https://cdt.ca.gov/policy/technology-letters/technology-letter-24-01/" target="_blank">Technology Letter 24-01</a> (GenAI inventory & procurement)
- <a href="https://cdt.ca.gov/policy/technology-letters/technology-letter-24-03/" target="_blank">Technology Letter 24-03</a> (clarifications & revisions)
- <a href="https://cdt.ca.gov/policy/simm/" target="_blank">SIMM Index</a> (risk assessment forms, privacy assessments)
- <a href="https://www.govops.ca.gov/generative-ai-genai-executive-order/" target="_blank">GovOps GenAI page</a> (executive order implementation)

**California AI Legislation (Key Bills)**
- <a href="https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202320240SB53" target="_blank">SB 53</a> — Transparency in Frontier AI Act (effective Jan 2026)
- <a href="https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202320240SB896" target="_blank">SB 896</a> — CA AI Accountability Act (effective Jan 2025)
- <a href="https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202320240AB1008" target="_blank">AB 1008</a> — CCPA AI Amendment (effective Jan 2025)
- <a href="https://leginfo.legislature.ca.gov/faces/billNavClient.xhtml?bill_id=202320240AB2885" target="_blank">AB 2885</a> — Uniform AI definition across CA law

**Prompt & Context Engineering Guides**
- <a href="https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents" target="_blank">Anthropic: Effective Context Engineering for AI Agents</a>
- <a href="https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview" target="_blank">Anthropic Prompt Engineering Guide</a>
- <a href="https://platform.openai.com/docs/guides/prompt-engineering" target="_blank">OpenAI Prompt Engineering Guide</a>
- <a href="https://cloud.google.com/discover/what-is-prompt-engineering" target="_blank">Google Cloud Prompt Engineering Guide</a>
- <a href="https://direct.mit.edu/tacl/article/doi/10.1162/tacl_a_00638/119630/Lost-in-the-Middle-How-Language-Models-Use-Long" target="_blank">"Lost in the Middle" (Stanford/MIT research paper)</a>
- <a href="https://www.promptingguide.ai" target="_blank">Prompting Guide</a> (community reference with 58 techniques)

**Training Tools**
- <a href="https://www.perplexity.ai" target="_blank">Perplexity AI</a> (free Pro for .gov emails)
- <a href="https://claude.ai" target="_blank">Claude</a> by Anthropic
- <a href="https://docs.anthropic.com/en/docs/claude-code" target="_blank">Claude Code</a> (agentic AI for engineering)

**Fellowship Resources**
- <a href="https://innovation.ca.gov" target="_blank">California Innovation Fellowship</a>
- Questions about this training: Contact your Fellowship cohort lead

<div class="gov-callout">
<strong>Start today:</strong> Pick one task you do regularly — a research question, a memo draft, a data summary — and try the structured prompt approach from this module. Compare the output to your usual approach. See the difference for yourself.
</div>
