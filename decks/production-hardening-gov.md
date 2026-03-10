# Production Hardening for Government Web Services

Real Metrics from Securing a Live AI-Powered Public Website

<p class="thesis"><strong>Core Thesis:</strong> A $0-budget, 6-phase hardening pipeline transformed an unprotected demo site into a production-ready government web service — with 50+ verified metrics proving every claim.</p>
<p class="meta">February 2026 · vanderdev.net · Innovation Fellowship</p>

<style>
/* ── Before/After Pill ── */
.ba-pill {
  display: inline-block;
  padding: 0.2rem 0.7rem;
  border-radius: 20px;
  font-size: 0.75rem;
  font-weight: 600;
  margin-bottom: 0.35rem;
}
.ba-pill.before { background: rgba(232, 88, 88, 0.15); color: #e85858; }
.ba-pill.after { background: rgba(96, 212, 160, 0.15); color: #60d4a0; }

/* ── Cache Table ── */
.cache-table {
  width: 100%;
  border-collapse: collapse;
  margin: 1rem 0;
  font-size: 0.85rem;
}
.cache-table th {
  text-align: left;
  padding: 0.5rem 0.75rem;
  border-bottom: 2px solid rgba(212, 160, 74, 0.3);
  color: #d4a04a;
  font-weight: 600;
}
.cache-table td {
  padding: 0.45rem 0.75rem;
  border-bottom: 1px solid rgba(255, 255, 255, 0.06);
  color: #c8ccd8;
}
.cache-table .speedup {
  color: #60d4a0;
  font-weight: 600;
}

/* ── Tradeoff Card ── */
.tradeoff-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 0.75rem;
  margin: 1rem 0;
}
.tradeoff-card {
  background: rgba(30, 33, 50, 0.6);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 10px;
  padding: 0.85rem 1rem;
}
.tradeoff-card .tc-title {
  font-weight: 600;
  font-size: 0.85rem;
  color: #e8b860;
  margin-bottom: 0.3rem;
}
.tradeoff-card .tc-desc {
  font-size: 0.8rem;
  color: #9a9ab0;
  line-height: 1.5;
}

/* ── Lesson Card ── */
.lesson-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 0.65rem;
  margin: 1rem 0;
}
.lesson-card {
  background: rgba(30, 33, 50, 0.5);
  border-left: 3px solid #d4a04a;
  border-radius: 0 8px 8px 0;
  padding: 0.7rem 1rem;
}
.lesson-card .lc-gotcha {
  font-weight: 600;
  font-size: 0.85rem;
  color: #e85858;
  margin-bottom: 0.2rem;
}
.lesson-card .lc-fix {
  font-size: 0.8rem;
  color: #9a9ab0;
  line-height: 1.45;
}

/* ── Architecture Box ── */
.arch-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 0.75rem;
  margin: 1rem 0;
}
.arch-box {
  background: rgba(30, 33, 50, 0.6);
  border: 1px solid rgba(255, 255, 255, 0.08);
  border-radius: 10px;
  padding: 0.75rem 1rem;
  text-align: center;
}
.arch-box .ab-icon { font-size: 1.5rem; margin-bottom: 0.25rem; }
.arch-box .ab-label { font-weight: 600; font-size: 0.85rem; color: #f0f2f8; }
.arch-box .ab-desc { font-size: 0.75rem; color: #9a9ab0; margin-top: 0.15rem; }

/* ── Flood Test ── */
.flood-result {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  margin: 0.75rem 0;
  padding: 0.65rem 1rem;
  background: rgba(30, 33, 50, 0.5);
  border-radius: 10px;
  border: 1px solid rgba(255, 255, 255, 0.06);
}
.flood-bar {
  flex: 1;
  height: 24px;
  border-radius: 6px;
  overflow: hidden;
  display: flex;
}
.flood-pass { background: rgba(96, 212, 160, 0.5); }
.flood-block { background: rgba(232, 88, 88, 0.5); }
.flood-label {
  font-size: 0.8rem;
  color: #b8bcc8;
  min-width: 100px;
  font-weight: 600;
}
.flood-nums {
  font-size: 0.75rem;
  color: #9a9ab0;
  min-width: 140px;
  text-align: right;
}
</style>

---

## What Is Production Hardening?

Taking a working website and **making it safe for real users** — preventing crashes, blocking abuse, adding monitoring, and proving it all works under load.

:::callout tip
Think of it like getting a building up to code before opening day. The building works — the lights turn on, doors open — but it hasn't been inspected for fire exits, sprinklers, emergency lighting, or maximum occupancy.
:::

**Production hardening is the inspection and retrofit process for web servers.**

It answers three questions:
- **Can it survive abuse?** (rate limiting, memory caps, auth)
- **Will we know when something breaks?** (alerts, monitors, health checks)
- **Does it perform under real load?** (caching, CDN, load testing)

## The Problem — What Was at Risk

Our site ([vanderdev.net](https://vanderdev.net)) hosts three AI chatbots, a workflow engine, a database, and monitoring tools — all on one server. Before hardening:

:::callout warning
**The site was functional but unprotected.** Any of these could happen during a live demo:
:::

- **Anyone could crash the server** by exhausting memory — programs had no safety limits. When a computer's memory (RAM) fills up, the operating system starts force-killing running programs (**OOM kill** — "out of memory kill"). There was no overflow space (**swap** — emergency disk-based memory) either.

- **Anyone could run up AI costs** by spamming the chatbots — no limits on how many requests one person could make per second (**rate limiting**).

- **No one would know if something broke** — no automatic alerts, no health checks, no uptime monitoring.

- **No protection against flood attacks** — a single attacker could knock the site offline by overwhelming it with fake traffic (**DDoS** — distributed denial-of-service).

## The Architecture

vanderdev.net runs **28 programs** (called **containers** — isolated mini-servers, each running one job) on a single VPS with 4 vCPU and 16 GB RAM:

<div class="arch-grid">
<div class="arch-box">
<div class="ab-icon">🤖</div>
<div class="ab-label">3 AI Chatbots</div>
<div class="ab-desc">WaterBot, BizBot, KiddoBot</div>
</div>
<div class="arch-box">
<div class="ab-icon">⚙️</div>
<div class="ab-label">Workflow Engine</div>
<div class="ab-desc">n8n — like Zapier, self-hosted</div>
</div>
<div class="arch-box">
<div class="ab-icon">🗄️</div>
<div class="ab-label">Database + Auth</div>
<div class="ab-desc">Supabase (PostgreSQL)</div>
</div>
<div class="arch-box">
<div class="ab-icon">📊</div>
<div class="ab-label">Monitoring Stack</div>
<div class="ab-desc">Prometheus + Grafana</div>
</div>
<div class="arch-box">
<div class="ab-icon">🌐</div>
<div class="ab-label">Web Server</div>
<div class="ab-desc">nginx reverse proxy</div>
</div>
<div class="arch-box">
<div class="ab-icon">🛡️</div>
<div class="ab-label">Edge Protection</div>
<div class="ab-desc">Cloudflare CDN + DNS</div>
</div>
</div>

**VPS** = Virtual Private Server — a rented cloud computer. **Docker** = the platform that runs all 28 containers.

## The 6-Phase Approach

We tackled hardening in order — security first, then visibility, then speed, then edge protection, then tested everything, then documented it all.

:::step-sequence
Lock It Down | Phase 1: Add memory limits, traffic caps, and authentication to block abuse
Watch It | Phase 2: Add alerts, health checks, and monitors so we know the instant something breaks
Speed It Up | Phase 3: Cache repeat AI answers, reduce background traffic, add security headers
Shield It | Phase 4: Put Cloudflare in front of the server — absorbing attacks and caching files globally
Prove It | Phase 5: Simulate 50 simultaneous users and verify every security measure holds
Teach It | Phase 6: Compile real metrics into this training deck for the Fellowship
:::

---

## Phase 1: Lock It Down

**Goal: Stop crashes and block abuse before anything else.**

**Swap** (emergency overflow memory on disk) gives the OS a safety net when RAM fills up, instead of killing programs. **Container limits** cap each program so one runaway can't consume everything. **Rate limiting** (speed limits for web traffic) prevents one user from flooding the system. **Webhook auth** (password-protecting the AI chatbot endpoints) blocks unauthorized callers. **fail2ban** (auto-blocking repeat offenders) watches logs and bans bad IPs.

:::stat-cards
4 GB | Swap Safety Net | gold
25 of 25 | Programs Capped | blue
3 | Traffic Speed Limits | green
4 | Auto-Block Rules
:::

- **Memory tiers:** Heavy (2 GB) for n8n and the database. Medium (512 MB) for 7 services. Light (256 MB) for 15 services. Minimal (128 MB) for the SSL certificate manager.
- **Rate limiting zones:** Bot webhooks (URLs that trigger AI workflows) at 10 req/s, API at 2 req/s, general traffic at 30 req/s.
- **fail2ban:** Upgraded from 1 jail (SSH only) to 4 jails — added nginx auth failures, bot scanners, and rate limit violators. Uses polling backend because Docker container logs aren't visible to the standard system journal.

## Phase 2: Watch It

**Goal: If something breaks at 2 AM, know before users report it.**

**Prometheus** (a metrics collection system — like a health monitor for servers) already collected data, but never acted on it. We added **alert rules** that trigger automatic push notifications when thresholds are crossed. **Uptime Kuma** sends synthetic test requests every 60 seconds to verify each service is actually responding.

:::stat-cards
16 | Alert Rules | gold
11 | Uptime Monitors | blue
30s | Health Check Interval | green
2 | Notification Channels
:::

- **16 alert rules** across 4 categories: host health (CPU, memory, disk), service availability (container down), dead man's switch (proves monitoring itself is running), and platform compatibility.
- **Health endpoint** at `/health` — a cron job writes a status file every 30 seconds. This works even if the main API server is down, because it's just a static file served by nginx.
- **11 monitors:** 4 HTTP (website, API, webhooks, health), 4 TCP (database, Prometheus, Grafana, n8n), 3 Docker container checks.
- **Notification path:** Prometheus → Alertmanager → [ntfy.sh](https://ntfy.sh/) (a free push notification service) → phone.

## Phase 3: Speed It Up

**Goal: Stop paying the AI to answer the same question twice.**

When two users ask the same question, the AI used to generate a fresh (and expensive) response every time. **Redis** (a fast in-memory cache — like keeping the answer sheet next to the phone) stores recent answers for 10 minutes. A cache "hit" returns the stored answer in milliseconds instead of waiting seconds for the AI.

:::stat-cards
129x | Faster Cached Responses | gold
6x | Fewer Background Requests | blue
A+ | Security Header Grade | green
24h | Browser CORS Cache
:::

- **Dashboard poll optimization:** The frontend used to ask "anything new?" every 5 seconds (1,200 requests/minute at 50 users). Now every 30 seconds (200 req/min) — with browser-level caching on the response.
- **Security headers** (**CSP**, **CORS**, and more) — browser-level rules that prevent unauthorized scripts and cross-site attacks. Frontend scores A+ (7 of 7 headers), API scores B (4 of 6 — CSP intentionally excluded for JSON APIs).
- **CORS** (Cross-Origin Resource Sharing — browser rules controlling which websites can talk to your API): Changed from wildcard (any site) to restricted (only vanderdev.net).

## Phase 4: Shield It

**Goal: Put a global shield between the internet and our server.**

**Cloudflare** (a content delivery network, or **CDN** — a global network that sits in front of your server) absorbs attack traffic and caches files at edge servers worldwide. We migrated DNS (the "phone book" that translates domain names to server addresses) from Hostinger to Cloudflare.

:::stat-cards
TLS 1.3 | Encryption Standard | gold
1 CA | Certificate Authority | blue
4 | Domains Shielded | green
15+7 | IP Ranges Configured
:::

- **SSL/TLS** (encryption that makes `https://` work — the lock icon) upgraded to Full Strict mode: encrypted end-to-end, with TLS 1.3 as the primary protocol and TLS 1.1 rejected entirely.
- **CAA records** (DNS entries that control which companies can issue security certificates for your domain): Reduced from 12 authorized certificate authorities to 1 — only [Let's Encrypt](https://letsencrypt.org/).
- **nginx real_ip** configured BEFORE enabling Cloudflare proxy — this ensures rate limiting sees the real visitor's IP address, not Cloudflare's. Order matters.
- **4 domains proxied** through Cloudflare (vanderdev.net, www, api, n8n), **5 DNS-only** (grafana, portainer, telemetry, pgadmin, studio — internal tools accessed via Tailscale).

## Phase 5: Prove It

**Goal: Simulate real load and verify every security measure.**

We used **k6** (a load testing tool that simulates many users at once) to hit the site with 50 concurrent virtual users, plus targeted flood tests against rate-limited endpoints.

:::stat-cards
6,512 | Test Requests Sent | gold
48.4ms | Response Time (p95) | blue
A+ | Header Score | green
44% | Requests Shed by Rate Limiter
:::

- **p95 latency** (95% of requests finish faster than this time): 48.4ms — meaning the server responds in under 50 milliseconds for the vast majority of traffic, even under load.
- **44% error rate is a PASS** — those aren't failures, they're the rate limiter correctly blocking excess traffic. The server was protecting itself by returning "429 Too Many Requests" to requests that exceeded the speed limit.
- **Latency under load** only increased 4-9ms compared to baseline (30-35ms idle) — negligible degradation at 50 concurrent users.

---

## Before/After: Security Posture

:::compare-grid
## Before Hardening

- No traffic speed limits — any user could flood the server
- AI chatbot endpoints completely open to the public
- 1 auto-block rule (SSH only — nothing for web traffic)
- 3 security headers (minimal browser protection)
- Basic encryption (TLS 1.2+, no enforcement)
- Any website could call our API (wildcard CORS)
- Basic DNS with 12 authorized certificate authorities
- No DDoS protection

---

## After Hardening

- 3 rate limiting zones (10/2/30 requests per second)
- Webhook endpoints password-protected at the nginx level
- 4 auto-block rules (SSH + auth + bot scanners + rate limit)
- 7 security headers — A+ grade on frontend
- TLS 1.3 primary, TLS 1.1 rejected, Full Strict mode
- Only vanderdev.net can call the API (restricted CORS)
- Cloudflare DNS with 1 authorized CA (Let's Encrypt only)
- Cloudflare DDoS protection active
:::

## Before/After: Performance

:::compare-grid
## Before

- Every repeat question costs AI processing time (4-10 seconds)
- Dashboard polls every 5 seconds (1,200 req/min at scale)
- No browser caching on API responses
- No CDN — all traffic hits origin server directly
- No CORS preflight cache

---

## After

- Cached answers return in 80-115ms via Redis (free)
- Dashboard polls every 30 seconds (200 req/min at scale)
- 15-second browser cache on API responses
- Cloudflare global edge caching configured
- 24-hour CORS preflight cache eliminates redundant checks
:::

## Before/After: Monitoring

:::compare-grid
## Before

- Metrics collected by Prometheus but never acted on
- Zero notifications when things break
- No health check endpoint
- No synthetic uptime testing
- No dead man's switch

---

## After

- 16 alert rules across 4 categories trigger push notifications
- Phone notifications via ntfy.sh (2 topics: infra + uptime)
- /health endpoint updated every 30 seconds (works even if API is down)
- 11 synthetic monitors (HTTP, TCP, Docker container checks)
- Cron-based dead man's switch (proves monitoring is still running)
:::

---

## Deep Dive: Rate Limiting in Action

We flooded the chatbot webhook endpoint with 30 simultaneous requests. The **rate limiter** (speed limit for web traffic) did exactly what it should — let legitimate traffic through and blocked the excess with 429 "Too Many Requests" responses.

**Webhook flood test (30 parallel requests):**

<div class="flood-result">
<div class="flood-label">Webhooks</div>
<div class="flood-bar">
  <div class="flood-pass" style="width: 70%"></div>
  <div class="flood-block" style="width: 30%"></div>
</div>
<div class="flood-nums">21 passed · 9 blocked (429)</div>
</div>

**API flood test (15 serial requests):**

<div class="flood-result">
<div class="flood-label">API</div>
<div class="flood-bar">
  <div class="flood-pass" style="width: 60%"></div>
  <div class="flood-block" style="width: 40%"></div>
</div>
<div class="flood-nums">9 passed · 6 blocked (429)</div>
</div>

The rate limiter uses a **"nodelay burst"** strategy — it processes the initial burst of requests immediately (no queueing delay), then hard-blocks anything over the limit. This means legitimate users get instant responses while abuse is stopped cold.

**Auth verification** also passed: no token → 403 (blocked), wrong token → 403 (blocked), valid token → 200 (success).

## Deep Dive: AI Response Caching

When two users ask the same question, why pay for the AI to answer twice? **Redis** (fast in-memory database used as a cache) stores answers for 10 minutes using DJB2 hash keys.

<table class="cache-table">
<tr><th>Bot</th><th>Without Cache</th><th>With Cache</th><th>Speedup</th></tr>
<tr><td>WaterBot</td><td>9.7 seconds</td><td>95ms</td><td class="speedup">103x faster</td></tr>
<tr><td>BizBot</td><td>4.5 seconds</td><td>115ms</td><td class="speedup">39x faster</td></tr>
<tr><td>KiddoBot</td><td>10.3 seconds</td><td>80ms</td><td class="speedup">128x faster</td></tr>
<tr><td>Permit Finder</td><td>10.2 seconds</td><td>79ms</td><td class="speedup">129x faster</td></tr>
</table>

:::callout info
**How it works:** Each chatbot workflow has 8 Redis nodes — check cache first, skip AI if found, store new answers for 10 minutes. Cache keys use a DJB2 hash (a fast, simple hashing algorithm) instead of MD5 because n8n's sandboxed code environment blocks external modules.
:::

## Key Decisions and Tradeoffs

Every security decision is a tradeoff between protection, cost, and usability. Here are the ones that shaped this project:

<div class="tradeoff-grid">
<div class="tradeoff-card">
<div class="tc-title">Client-Side Auth Token</div>
<div class="tc-desc">The chatbot's webhook token lives in a JavaScript config file — visible in browser dev tools. It's a speed bump (stops casual abuse), not vault-level security. Acceptable for a demo site with no sensitive data.</div>
</div>
<div class="tradeoff-card">
<div class="tc-title">Free Notification Service</div>
<div class="tc-desc">Using ntfy.sh's public server — the topic name is the only "security." Fine for a demo VPS. Production government systems should self-host the notification server.</div>
</div>
<div class="tradeoff-card">
<div class="tc-title">$0 Total Cost</div>
<div class="tc-desc">Every tool in this pipeline is free-tier: Cloudflare Free, Let's Encrypt, Redis (self-hosted), Prometheus, Grafana, Uptime Kuma, ntfy.sh, fail2ban, k6. Zero procurement needed.</div>
</div>
<div class="tradeoff-card">
<div class="tc-title">Nodelay Burst Strategy</div>
<div class="tc-desc">Rate limiter processes the initial burst immediately (no queue delay for real users), then hard-blocks excess. Prioritizes user experience over strict throttling.</div>
</div>
</div>

## Lessons Learned

Gotchas for anyone doing this themselves — each one cost us debugging time:

<div class="lesson-grid">
<div class="lesson-card">
<div class="lc-gotcha">Docker logs aren't in the system journal</div>
<div class="lc-fix"><strong>Fix:</strong> fail2ban needs a polling backend and explicit log volume mounts to read container logs. The default systemd backend can't see Docker output.</div>
</div>
<div class="lesson-card">
<div class="lc-gotcha">SSH + special characters = broken configs</div>
<div class="lc-fix"><strong>Fix:</strong> Sending configuration files over SSH? YAML, Prometheus rules, and nginx configs contain characters that break shell escaping. Use base64 encoding to pipe files safely.</div>
</div>
<div class="lesson-card">
<div class="lc-gotcha">Real IP must be configured BEFORE Cloudflare proxy</div>
<div class="lc-fix"><strong>Fix:</strong> nginx must be told to trust Cloudflare's IP ranges and extract the real visitor IP from the CF-Connecting-IP header. If you enable proxy first, rate limiting sees Cloudflare's IP — not the user's — and blocks everyone.</div>
</div>
<div class="lesson-card">
<div class="lc-gotcha">n8n sandbox blocks external modules</div>
<div class="lc-fix"><strong>Fix:</strong> n8n's Task Runner sandbox blocks process.env and require(). Use n8n's built-in Redis nodes instead of Code nodes with ioredis. Use DJB2 hash instead of crypto.createHash().</div>
</div>
</div>

## Build Metrics — How Long Did This Take?

:::stat-cards
6 | Phases Completed | gold
13 | Execution Plans | blue
157 min | Active Build Time | green
$0 | Total Cost
:::

:::callout info
**Average: 13 minutes per plan.** The entire hardening project — from first swap file to final load test — took under 3 hours of active work using [Claude Code](https://claude.ai/claude-code). Wall-clock time was longer due to breaks and decisions between phases, but the actual build time was 157 minutes across 13 plans.
:::

| Phase | Plans | Time | Avg/Plan |
|-------|-------|------|----------|
| 1. Lock It Down | 3 | 27 min | 9 min |
| 2. Watch It | 3 | 26 min | 9 min |
| 3. Speed It Up | 2 | 56 min | 28 min |
| 4. Shield It | 2 | 29 min | 15 min |
| 5. Prove It | 2 | 19 min | 10 min |
| 6. Teach It | 1 | This deck | — |

## What's Next

This hardening covers **10-50 concurrent unauthenticated users** — the demo-day tier. Scaling beyond that requires:

- **Streaming chatbot responses** — real-time typing effect so users see answers as they're generated, not after a multi-second wait
- **Queue-based processing** — at 100+ concurrent users, webhook requests should be queued and processed in order, not all at once
- **Self-hosted notification server** — production government systems need ntfy on their own infrastructure, not a public service
- **Fix Supabase health checks** — 4 containers report "unhealthy" because their Docker images lack the `curl` binary used by health check commands (services work fine — it's cosmetic)

:::callout tip
**The hardening approach scales.** The same 6-phase pipeline — lock down, observe, optimize, shield, validate, document — applies to any web service. The specific tools change; the methodology doesn't.
:::

## Resources

**From this project:**
- Verification Matrix — 50+ metrics with before/after values
- [Innovation Fellowship Library](https://govfellows.github.io/presentations/) — all training decks

**Tools used (all free tier):**
- [Cloudflare](https://www.cloudflare.com/) — DNS, CDN, DDoS protection
- [Let's Encrypt](https://letsencrypt.org/) — free SSL/TLS certificates
- [Prometheus](https://prometheus.io/) + [Grafana](https://grafana.com/) — metrics and dashboards
- [Uptime Kuma](https://github.com/louislam/uptime-kuma) — self-hosted uptime monitoring
- [k6](https://k6.io/) — open-source load testing
- [fail2ban](https://www.fail2ban.org/) — intrusion prevention
- [Redis](https://redis.io/) — in-memory caching
- [ntfy](https://ntfy.sh/) — push notifications

**Questions?** This deck is part of the Governor's Innovation Fellowship training library.
