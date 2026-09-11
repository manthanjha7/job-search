---
created: 2026-09-07
area: career
type: note
tags: []
---

# Interview Debrief — Peakflo (PM Intern, Agentic Finance / Voice AI for Collections)

> **Date:** 14 July 2026 · 17:30 IST
> **Interviewer:** Mrinal Bhatt — Founder's Associate + HR Business Partner, Peakflo (Bengaluru)
>   *(auto-captions garbled his name as "Merinal / Minal / Runal / Reinaldo" — resolved via the prep doc; treat all as Mrinal.)*
> **Round:** Screening / first round of a two-day process. Decision expected by EOD 15 July.
> **Source transcript:** [transcript.md](./transcript.md) (verbatim auto-caption export)
> **Prep doc:** [../../prep/Peakflo-2026-07-14.md](../../prep/Peakflo-2026-07-14.md)
> **Company:** Peakflo (YC W22) — agentic AI for global finance teams (autonomous AP/AR). Voice AI for collections is a real product line they name.

---

## ⚠️ Prep-vs-Actual: the round was mis-scoped

The prep doc predicted a **pure HR / culture-fit + motivation screen** with Mrinal (availability, "why looking now", the failure story, and the elaborate Finrep-"consulting" positioning). **That is not what happened.** Mrinal ran a **product-substance** round:

| Prepped heavily for | Actually asked |
|---|---|
| "Consulting" positioning + availability/hours | ❌ Never came up |
| "Why looking now?" / failure story | ❌ Never came up |
| Values mirroring (customer-driven, make-it-happen) | ❌ Not directly probed |
| — | ✅ **PRD writing methodology** |
| — | ✅ **AP/AR domain knowledge** |
| — | ✅ **Live product/situational case** (voice AI, first 48h) |
| — | ✅ **Differentiation** ("why you over a core-fintech PM?") |

**Lesson:** even a round fronted by an HR/People-Ops title can go product-heavy. Don't down-weight product-case + domain rehearsal because the interviewer is "HR." The under-prepped areas (AP/AR, product-case execution) were exactly what got tested — and the tailor-made unfair advantage from the prep doc (**LLM-as-a-Judge / agent evals**, called out as "make sure it comes up") **never got surfaced.**

---

## Scored Q&A

### Q1: "Give me a quick intro about yourself."
**Your answer summary:** Pre-final year at IIT; ~1 year as PM at "Finrep/FinTech" building AI-native platforms for CFO offices — experience with agents, built the product roadmap, shipped features; plus months at a B2C startup working with brands (The Souled Store, Rare Rabbit, etc.).
**Score: 5/10**

**What worked:** Hit the headline (fintech PM at an AI startup, agents, CFO office). Named recognizable D2C brands for texture.
**What was missed:** You had a **far stronger 30-second pitch written in the prep doc and didn't use it.** No **$0→$100K ARR**, no **analytics-first** angle, no **eval frameworks / LLM-as-a-Judge**, no end-to-end shipping proof. Those are your differentiators and they were left on the table in the very first answer — the one that frames the whole call. "Second PM" also undersells (you were the *first* PM). Brand list drifted from the resume (Souled Store/Bewakoof/Burger Bae) — keep it consistent so it survives a resume glance.
**Stronger version (your own prepped pitch — Story #1 + #8):**
> "I'm Manthan — for the last ~year I've been the **first PM at Finrep**, an AI-native fintech for the CFO's office, where I helped go **from zero to $100K ARR** owning activation and retention. Two things map straight to this role: I'm **analytics-first** — built our Mixpanel + Metabase stack from scratch across 7 surfaces — and I work hands-on with **AI agents, including eval frameworks that judge agent output quality.** I've also shipped features fully end-to-end, like an accounting-standards library that let a customer migrate off a legacy incumbent."
**Key quote to remember:** "First PM, zero to $100K ARR, analytics-first, and I build the evals that judge whether the agent is actually good."

---

### Q2: "What exactly were you doing at Finrep? What did the PM work look like?"
**Your answer summary:** Major role was analytics — set up the entire analytics funnel, Mixpanel events, funnels, tracking; built AI cost monitors and latency dashboards. Also roadmap planning and internal tools (themselves agents) to lift team productivity.
**Score: 6.5/10**

**What worked:** Analytics-first identity came through clearly — that's your real strength and it's exactly Peakflo's "track workflow-completion KPIs" need. The AI cost/latency monitoring detail signals genuine agent-ops depth.
**What was missed:** **Activities without outcomes.** No numbers, no "so what." The prep doc's Story #1 has a concrete arc (Mixpanel taxonomy → session-abandonment pattern → shipped re-engagement trigger) and the resume has "cut weekly analytics 4–6 hrs → 1–2." Say the result, not just the task list.
**Stronger version (Story #1):** Same content, but land it: "…and the payoff was concrete — session-replay surfaced an abandonment point, I shipped a re-engagement trigger against it, and the Claude-skill automations cut our weekly user-analytics work from ~4–6 hours to 1–2."
**Key quote to remember:** "I didn't just instrument events — I turned a session-abandonment pattern into a shipped re-engagement trigger."

---

### Q3: "Describe your experience writing PRDs — what's your flow / methodology?"
**Your answer summary:** Two triggers (internal identification vs. customer request); took the customer-request path. Drill into the *real* pain behind the ask (a "build me a dashboard" request isn't the actual need) → rough manual solution → build a clean prototype on the existing design system to make it tangible → reviews → then write the PRD (pain point, what it solves, current scope, future scope) → then a DRD (design/technical requirement doc) → collaborate with eng + design.
**Score: 7/10**

**What worked:** This was your **strongest answer.** It's a real, defensible methodology: problem-before-solution, **prototype-first** ("don't dig straight into PRDs"), explicit **scope-now vs. scope-later**, and a clean PRD→DRD→build handoff. That maturity (prototyping to de-risk before spec) plays well.
**What was missed:** **No concrete example anchored it.** You described the process in the abstract when **FASB ASC (Story #8)** is the perfect proof: a direct customer ask → you drilled the real need → prototyped on Replit → shipped end-to-end (Docker scrape → Postgres → prod frontend) → customer migrated off Intelligize. One named example turns a good process answer into a credible one.
**Stronger version:** Keep the methodology, then: "Concretely — a customer asked for an in-product accounting-standards reference. I drilled past the ask to the real job (stop paying for Intelligize), prototyped it on Replit, wrote the PRD scoping v1 vs. later, then shipped it end-to-end. That customer fully migrated off the incumbent."
**Key quote to remember:** "I prototype before I spec — a clickable v0 tells me more about the real problem than another page of PRD."

---

### Q4: "What's your understanding of AP / AR? Are you familiar with the processes?"
**Your answer summary:** Honestly flagged you weren't very familiar with the terms but dug in; described it as purchases → general ledgers → trial balances → converting invoices into structured data; said you'd handled such workflows at small scale in a past internship.
**Score: 4/10**

**What worked:** **Honesty was the right instinct** (prep doc literally said "show curiosity, not bluff"). Admitting the gap beats faking it with an HR-adjacent interviewer watching for self-awareness.
**What was missed:** The actual explanation was **muddled and largely wrong** — you described the *bookkeeping/close* cycle (GL → trial balance → structuring invoices), not AP/AR. Simple, correct framing: **AP = money you owe your suppliers (bills to pay); AR = money your customers owe you (invoices to collect).** Peakflo's *whole product* is automating both, and the voice-AI case that came next is pure **AR / collections** — so this gap directly weakened your next answer. Worse, the **prep doc handed you the exact reframe and you didn't use it:** "I'm on the SEC-reporting / financial-data side of the CFO office, not AP/AR — but I ramp fast; I taught myself FASB ASC deeply enough to ship a 35K-standard library. I'd close the AP/AR gap in weeks." Also, "handled these workflows in a past internship" is a stretch (Tryo was D2C sourcing/ops) — don't reach.
**Stronger version:** "Candidly, AP/AR isn't my day-to-day — I'm on the SEC-reporting side of the CFO office. But conceptually: **AP is what a company owes its vendors, AR is what its customers owe it** — and collections, which this role touches, is the AR side: chasing overdue invoices. I don't have deep AP/AR reps yet, but I ramp fast — I taught myself FASB ASC well enough to ship a 35,000-standard library. I'd close this gap in weeks."
**Key quote to remember:** "AP = I owe my vendors; AR = my customers owe me — collections is the AR side."

---

### Q5: "You own a new voice AI for payment collections. No user research, no wireframes, engineers waiting on you. What do you do in the first 48 hours?"  ⭐ *the pivotal question*
**Your answer summary:** Asked clarifying questions first (scope of "payment collection", what kind of clients) — the interviewer got mildly impatient ("No no no, it's a very simple process"). Then you described a **system architecture**: gather context (which companies to call + their target groups) and the input numbers/contacts → feed a **system prompt** configured per client → a **tool call** to a calling service (third-party or in-house) → it calls the customer, reminds them of the overdue payment, collects the response, returns it to the finance team.
**Score: 4/10**

**What worked:** Clarifying before answering is the right PM reflex, and you clearly **understand agent architecture** (system prompt → tool call → calling service → response loop) — that's genuine and few intern candidates could sketch it.
**What was missed — this is the big one:** You answered **"how would you build the agent"** when the question was **"what do you do as a PM in the first 48 hours with no research and engineers blocked."** Those are different questions. The expected shape is a **discovery + de-risking + unblock-eng plan**, not a solution architecture:
- **Talk to 2–3 design-partner finance teams** (their existing customers) to see the real collections workflow — you don't need weeks, you need 3 calls.
- **Map the current manual process AS-IS → TO-BE** (the JD explicitly asks for this) — who calls, what they say, when they escalate.
- **Define the ONE narrow wedge + a success metric** for v0 (e.g. "% of overdue invoices where the agent gets a payment commitment") rather than boiling the ocean.
- **Write the thin slice of requirements / user stories to unblock engineering today** — they're waiting; give them the smallest shippable spec, not a full PRD.
- **Guardrails / compliance — the glaring omission:** automated debt-collection calls are **heavily regulated** (consent, call-recording disclosure, permitted hours/frequency, tone, opt-out, RBI recovery-agent-style norms). A voice agent that harasses a customer is a legal and brand disaster. **Human-in-the-loop, confidence thresholds, escalation, and an audit trail** — which the prep doc names as *your* Fina friction/eval lens — were the single most differentiating thing you could have said, and they didn't come up.
- **The eval hook:** "and I'd stand up an LLM-as-a-Judge rubric to grade call quality before we let it dial real customers" — this is your unfair advantage and it was *made* for this question.
**Stronger version (structure it as 4 buckets, ~90 sec):**
> "In 48 hours I'm not writing a full PRD — I'm de-risking and unblocking eng. **(1) Discovery:** 3 fast calls with existing finance-team customers to watch how collections actually happens today, AS-IS. **(2) Scope the wedge:** pick one narrow use case — say, first-reminder calls on invoices 15–30 days overdue — with one success metric, % of calls that get a payment commitment. **(3) Guardrails first:** collections is regulated — I'd define consent, call-recording disclosure, allowed hours, tone, opt-out, and a hard human-in-the-loop escalation on any dispute, plus an audit trail. **(4) Unblock eng today:** hand them the thinnest slice of user stories for that one flow so they're not idle, and in parallel stand up an LLM-as-a-Judge eval to grade call quality before we ever dial a real customer."
**Key quote to remember:** "In 48 hours I de-risk and unblock — I don't hand engineers a system prompt, I hand them the narrowest safe slice plus the guardrails, because an unsupervised collections call is a compliance problem before it's a product."

---

### Q6: "Why should we pick you over a candidate who already has core fintech PM experience and AP/AR knowledge?"
**Your answer summary:** Two points — (1) you've worked with agents a lot; building an agent is one part, but **designing the whole system** (where to put human-in-the-loop, how to keep it from breaking) is a separate skill you've built; (2) **ownership** — "you'll hardly hear that I missed a deadline," you take responsibility seriously.
**Score: 5.5/10**

**What worked:** Good two-beat structure (skill + ownership). "**Systems design + human-in-the-loop**" is a genuine, JD-aligned differentiator — and it's honest to lean into the agent angle rather than pretend you have the AP/AR depth you'd just admitted you lacked.
**What was missed:** **Claims without proof.** "I understand ownership / you'll hardly hear I missed a deadline" is an assertion — back it with the fact: *first PM, 0→$100K ARR, shipped end-to-end.* And you again skipped the single sharpest wedge against a "core fintech PM": **they probably can't build agent evals, and you can.** The JD explicitly asks for LLM-as-a-Judge; that's the one thing a traditional fintech PM almost certainly lacks. That's your answer to this exact question and it went unsaid twice.
**Stronger version:** "A core fintech PM knows AP/AR — I'll learn that in weeks. What's much harder to learn is what I already do: **designing agentic systems and evaluating them.** I've run production agent work at Finrep — deciding where a human stays in the loop, and building **LLM-as-a-Judge eval frameworks to prove an agent is actually good** before it ships. Your JD asks for exactly that, and most traditional fintech PMs have never built it. Pair that with the fact that I'm the first PM at Finrep who took us 0→$100K ARR owning outcomes end-to-end — that's the bet."
**Key quote to remember:** "Domain knowledge I can learn in weeks; building the evals that judge whether an agent is safe to ship is what I already do — and it's the one thing a traditional fintech PM usually can't."

---

## Overall Assessment

**Interview Score: 5.3/10**

### Strongest Moments
- **PRD methodology (Q3)** — the prototype-first, problem-before-spec, scope-now-vs-later flow was mature and real. Your best answer.
- **Honesty on the AP/AR gap (Q4)** — you didn't bluff, which is the right call with a People-Ops interviewer scoring self-awareness. (The *content* was wrong, but the instinct was right.)
- **Agent-architecture fluency (Q5)** — you can genuinely sketch a system-prompt → tool-call → calling-service loop; that competence is real even though you aimed it at the wrong question.

### Missed Opportunities (the pattern)
- **Your unfair advantage never surfaced.** The prep doc flagged in bold: "The JD literally asks for LLM-as-a-Judge eval experience… make sure it comes up." Across an intro, a differentiation question, and a voice-AI-agent case, **evals came up zero times.** That's the single biggest miss of the call.
- **Claims over proof throughout.** You have quantified wins ($0→$100K ARR, 4–6h→1–2h, 35K-standard library, customer migrated off Intelligize) and named STAR stories — and mostly described activities/traits instead. Every answer had a number-backed version available and unused.
- **Answered the question you wanted, not the one asked (Q5).** The 48-hour question wanted a PM discovery/de-risk/unblock plan; you gave build architecture. Read the verb of the question ("what do *you* do", "first 48 hours") before answering.

### Red Flags to Watch
- **Interviewer impatience during Q5** ("No no no… it's a very simple process") — your clarifying questions, while a good instinct, ran slightly long and read as not-tracking a "simple" prompt. Clarify with **one or two sharp questions, then commit** — don't loop.
- **AP/AR miss in an AP/AR company** — Peakflo *is* AP/AR automation. Getting the core definition muddled (and calling collections-adjacent workflows "handled in a past internship") is a domain-credibility ding for this specific employer.

### Signal Reading — **Neutral, leaning cautious**
- No deep follow-ups, the case answer visibly didn't satisfy him, mild impatience, and a boilerplate close ("we're evaluating profiles, hear back by EOD tomorrow"). It was a genuine screen, you got through every question, and the PRD + agent fluency landed — but nothing in his reactions signals strong enthusiasm. **Treat it as a coin-flip and make the thank-you email do real work** (below) — it's a rare chance to retroactively plant the eval advantage you didn't voice live.

---

## Pattern Learning
This is the **first debrief in the bank**, so no cross-interview trend yet. Baselines to track going forward:
- **Recurring weakness to watch:** *not deploying prepped material live* — strong pitch, STAR numbers, and the eval wedge were all written down and none were used. The gap isn't preparation; it's **retrieval under pressure.** Next mock: practice *saying the numbers out loud*, not just having them on the page.
- **Recurring strength to keep leveraging:** process/systems thinking (PRD flow, agent architecture) is a natural, credible mode for you — anchor it with one concrete example each time.

---

## Thank-You Email Draft

**To:** Mrinal Bhatt (Founder's Associate + HR Business Partner, Peakflo)
**Subject:** Thank you — PM Intern conversation

---

Hi Mrinal,

Thanks for the time yesterday — I enjoyed the conversation, especially the voice-AI-for-collections scenario. It stuck with me after we hung up.

Reflecting on it: the part I'd most want to own on day one is the **guardrails**. Automated collections calls are a trust-and-compliance surface before they're a product — consent, tone, allowed hours, and a hard human-in-the-loop escalation on any dispute. And to know the agent is actually ready for a real customer, I'd stand up an **LLM-as-a-Judge eval** to grade call quality before it ever dials out — which is exactly the kind of agent-evaluation work I've been doing at Finrep. I realized I under-sold that in our call, and it's the piece I'm most excited to bring to Peakflo's agentic workflows.

The SaaS-to-agent shift you're driving in AP/AR is the same inflection I've been living on the CFO-office side, so this maps closely to how I already think.

Thanks again — I'd love to keep going in the process.

Best,
Manthan

*(~150 words. It does three jobs: reinforces your real strength — PRD/systems thinking via the guardrails framing; retroactively plants the LLM-as-a-Judge eval advantage you never voiced live; and quietly reframes the Q5 miss by giving the PM-shaped answer, not the build-shaped one. Send within 24h — before EOD 15 July, ideally this morning, so it lands before their decision.)*
