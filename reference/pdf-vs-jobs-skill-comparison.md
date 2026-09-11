---
created: 2026-09-07
area: career
type: note
tags: []
---

# Aakash Gupta Job Search OS vs Our /jobs Skill -- Gap Analysis

**Date:** 2026-04-21
**Source:** "The Claude Code Job Search Operating System" by Aakash Gupta (Apr 01, 2026)

---

## Tab 1: Feature-by-Feature Comparison

The PDF describes an 18-skill system covering the **full job search funnel** (discovering roles to landing offers). Our /jobs skill covers discovery + tracking deeply, but doesn't touch later funnel stages.

| # | PDF Feature | Description (from PDF) | We Have It? | Our Implementation | Gap / Notes |
|---|------------|------------------------|-------------|-------------------|-------------|
| 1 | **Job Discovery / Search** | Scan job boards, target companies, multiple sources | YES (strong) | LinkedIn MCP, JSearch, WebSearch (Tavily), Firecrawl, Internshala, Naukri, Wellfound, YC, Unstop, BuiltIn, APMList | Our source coverage is arguably broader than the PDF's. No gap. |
| 2 | **Fit Scoring & Ranking** | Score and rank roles against profile | YES (strong) | 0-100 rubric: Skills (30) + Level (20) + Location (20) + Company (15) + Recency (15). Badges: STRONG FIT / Good Fit / Possible / Stretch | Solid. Could add "culture fit" or "growth trajectory" dimensions but not critical. |
| 3 | **Daily Briefing** | Open laptop, daily brief is waiting. Automated overnight scan. | PARTIAL | We have "Brief Mode" (manual trigger: "daily briefing"). No automated/scheduled overnight scan. | **GAP:** No automated cron/scheduled run. User must manually invoke. See Tab 2 #1. |
| 4 | **Application Funnel Tracker** | Track status: Discovered > Shortlisted > Applied > Interview > Offer | YES | Status Update Mode with states: DISCOVERED > SHORTLISTED > APPLIED > INTERVIEWING > OFFER / REJECTED / EXPIRED / PASSED | Solid. Could add date-per-stage tracking for velocity metrics. |
| 5 | **Dream Company Watchlist** | Monitor target companies for any openings | YES | Tier 1 dream companies searched via LinkedIn MCP (no date filter). Curated page checks (TheFintechPM, ProductManagerHQ). | Good. |
| 6 | **Resume Tailoring** | Customized resume for each JD. Different bullets, different ordering, different summary. "No two resumes look alike." | NO | We generate "match signals" and "gaps to address" but don't produce an actual tailored resume. | **MAJOR GAP.** PDF's core differentiator. See Tab 2 #2. |
| 7 | **Cover Letter Generation** | Personalized cover letter per application | NO | Not implemented. | **GAP.** See Tab 2 #3. |
| 8 | **Outreach / Networking Messages** | Draft personalized messages for each person. Follow-ups for connections. Referral requests. Nudges for stale referrals. | NO | We identify referral potential (search_people for 75+ fit) but don't draft any messages. | **GAP.** See Tab 2 #4. |
| 9 | **Referral Strategy** | "Referrals stacked before you submit." System builds referral at each target company before applying. | PARTIAL | We check for PM-adjacent people at companies (Step 6e). But no referral request workflow, no tracking of referral status, no follow-up nudges. | **GAP.** See Tab 2 #5. |
| 10 | **Company Research** | Deep research: funding, product news, culture, recent launches, interviewer background | PARTIAL | Company Intelligence (Step 6d): LinkedIn profile, funding, AmbitionBox/Glassdoor rating, recent news. | Good for discovery phase. PDF goes deeper for interview prep (interviewer background, candidate debriefs). |
| 11 | **Interview Prep** | Company-specific questions from real interview data. Interviewer's background. Recent product news. Game plan for candidacy gaps. | NO | Not implemented. | **MAJOR GAP.** See Tab 2 #6. |
| 12 | **Mock Interviews** | Grade your answers. Tell you which stories to swap in. Pattern learning across rounds. | NO | Not implemented. | **GAP.** See Tab 2 #7. |
| 13 | **Post-Interview Debrief** | Score every answer. Identify where you left value on the table. Rewrite weak answers. Auto-suggest question focus areas. | NO | Not implemented. | **GAP.** See Tab 2 #8. |
| 14 | **Thank-You Emails** | Personalized thank-you referencing what was actually discussed in the interview. | NO | Not implemented. | **GAP.** See Tab 2 #9. |
| 15 | **Offer Negotiation** | `/negotiate` skill mentioned in screenshot | NO | Not implemented. | **GAP.** See Tab 2 #10. |
| 16 | **Compensation Research** | Salary data for benchmarking during negotiation | YES | Step 6f: AmbitionBox for India, levels.fyi for US. Shown in listings. | We have this for discovery. PDF uses it for negotiation leverage too. |
| 17 | **Stale Job Validation** | Re-check old discoveries for expired status | YES | Step 0.5: Re-validates DISCOVERED/SHORTLISTED jobs 5+ days old via MCP and WebFetch. | Good. |
| 18 | **Deduplication** | Cross-source dedup | YES | URL dedup + title normalization dedup. Prefer LinkedIn version. seen.md tracking. | Strong. |

### Score Summary
- **Features we have fully:** 9 out of 18 (50%)
- **Features we have partially:** 3 out of 18 (17%)
- **Features we're missing entirely:** 6 out of 18 (33%)

**Key insight:** Our /jobs skill is a best-in-class **discovery engine**. The PDF's OS covers the **full funnel** -- discovery is just 1 of 6 stages (Discover > Tailor > Outreach > Prep > Interview > Negotiate).

---

## Tab 2: Improvement Details & Implementation Ideas

### #1: Automated Daily Briefing (Scheduled Scan)
**Current state:** Manual trigger only ("daily briefing", "job brief")
**PDF vision:** Overnight automated scan. You open your laptop and the brief is waiting.
**How to improve:**
- Use Claude Code's `/schedule` skill or cron hooks to run `/jobs` in Brief Mode every morning (e.g., 7 AM IST)
- Output saved to `Jobs/listings/YYYY-MM-DD-brief.md`
- When you open Claude Code, it surfaces: "Your daily brief is ready. X new jobs, Y strong fits."
**Effort:** Low (config only, no skill code changes)
**Input needed from you:** Preferred scan time? Which days (weekdays only or daily)?

---

### #2: Resume Tailoring Skill (`/resume-tailor`)
**Current state:** We generate match signals ("Your match: fintech experience -> Direct: Finrep") but don't produce a tailored resume.
**PDF vision:** Every resume is restructured for that specific JD. Different bullets selected. Different ordering. Different summary. "No two resumes look alike."
**How to implement:**
- New skill: `/resume-tailor`
- Input: Job URL or job details from tracker + `profile.md` + base resume file
- Steps:
  1. Read JD requirements (from listings or fetch live)
  2. Read base resume (need a `Jobs/resume-base.md` master file with ALL bullets/experiences)
  3. Select most relevant bullets for this JD
  4. Reorder sections to front-load matching experience
  5. Rewrite summary/objective for this specific role
  6. Output: tailored resume as Markdown + optionally trigger export to PDF
- Key rule from PDF: "Never fabricate a bullet." Only reframe real experience.
**Effort:** Medium (new skill, needs base resume file)
**Input needed from you:**
- Do you have a master resume with all possible bullets? Or should we build one from profile.md?
- Preferred resume format (1-page? sections order?)
- Do you want PDF export (requires a tool like pandoc or LaTeX)?

---

### #3: Cover Letter Generation (`/cover-letter`)
**Current state:** Not implemented.
**How to implement:**
- New skill: `/cover-letter`
- Input: Job URL/details + profile.md
- Generate personalized cover letter matching JD language
- Highlight 2-3 strongest match points from profile
- Company-specific "why this company" paragraph (reuse company intel data)
**Effort:** Low-Medium (relatively simple prompt-based skill)
**Input needed from you:** Do you actually use cover letters for the roles you're targeting? Many PM intern roles in India don't require them. If not needed, skip this.

---

### #4: Outreach Message Drafting
**Current state:** We identify referral potential people but don't draft messages.
**PDF vision:** Personalized messages per person. Follow-ups. Referral requests. Nudges for stale referrals.
**How to implement:**
- Add to `/jobs` skill or create `/outreach` skill
- For each SHORTLISTED+ job, generate:
  1. Cold connection request message (personalized based on shared background)
  2. Referral request template (if already connected)
  3. Follow-up message (if no response after X days)
- Use LinkedIn profile data we already fetch (Step 6e) to personalize
- Track outreach status in tracker.md (new columns: Referral Contact, Outreach Status, Last Follow-up)
**Effort:** Medium
**Input needed from you:** Your outreach style/tone? Any existing templates you like? Do you want auto-send via LinkedIn MCP or just draft for review?

---

### #5: Referral Workflow System
**Current state:** We check for PM people at companies (search_people). That's it.
**PDF vision:** "Referrals stacked before you submit." Full system: identify contacts > send request > track status > follow up > then apply.
**How to implement:**
- Add referral tracking columns to tracker.md: `Referral Contact | Referral Status (NONE/IDENTIFIED/REQUESTED/CONFIRMED/DECLINED) | Referral Date`
- Workflow: Before status moves from SHORTLISTED to APPLIED, prompt: "Have you secured a referral? [Contact name] was identified."
- Generate referral request messages (ties into #4)
- Nudge system: "You requested a referral from [Name] 5 days ago with no response. Draft a follow-up?"
**Effort:** Medium
**Input needed from you:** Do you actually use referrals for applications? How important is this for India PM intern roles?

---

### #6: Interview Prep Skill (`/interview-prep`)
**Current state:** Not implemented.
**PDF vision:** Company-specific questions from real interview data + hundreds of candidate debriefs. Interviewer background. Recent product news. Game plan for candidacy gaps.
**How to implement:**
- New skill: `/interview-prep`
- Input: Company name + role (pull from tracker)
- Steps:
  1. Company deep dive: product, recent news, competitors, funding, culture (expand existing company intel)
  2. WebSearch for interview questions: `"[Company] product manager interview questions" site:glassdoor.com OR site:ambitionbox.com OR site:leetcode.com`
  3. Interviewer lookup (if name provided): LinkedIn profile, background, published articles
  4. Gap analysis: compare your profile gaps against likely questions
  5. Suggested STAR stories from your experience for each likely question
  6. Output: structured prep doc saved to `Jobs/prep/[Company]-[Date].md`
**Effort:** Medium-High (new skill, rich output)
**Input needed from you:** Do you have a "story bank" of STAR-format experiences? Should we build one?

---

### #7: Mock Interview Skill
**Current state:** Not implemented.
**PDF vision:** Ask questions, grade answers, suggest which stories to swap in. System learns your patterns over rounds.
**How to implement:**
- New skill: `/mock-interview`
- Interactive mode: Claude asks questions, you answer, Claude grades
- Scoring rubric: Structure (STAR), Relevance, Specificity, Impact quantification
- After each answer: "Score: 7/10. Swap suggestion: Use your Finrep onboarding redesign story instead -- stronger impact metrics."
- Session history saved for pattern analysis
**Effort:** Medium
**Input needed from you:** Is this something you'd actually use regularly? Interactive mock interviews take time.

---

### #8: Post-Interview Debrief
**Current state:** Not implemented.
**PDF vision:** Score every answer. Identify where you left value on the table. Rewrite weak answers. Pattern learning.
**How to implement:**
- New skill: `/debrief`
- Input: "I just interviewed at [Company]. Here's what they asked and what I said..."
- Output: scored answers, missed opportunities, rewritten versions, patterns to fix
- Save to `Jobs/interviews/[Company]-[Date]-debrief.md`
**Effort:** Low-Medium (prompt-driven, no API calls needed)

---

### #9: Thank-You Email Generator
**Current state:** Not implemented.
**PDF vision:** Personalized thank-you referencing what was actually discussed.
**How to implement:**
- Add to `/debrief` skill as final step
- Input: interview notes/debrief
- Output: email draft referencing specific discussion points, reinforcing strongest moments
**Effort:** Low (can be part of debrief skill)

---

### #10: Offer Negotiation (`/negotiate`)
**Current state:** Not implemented. We do have compensation data from Step 6f.
**PDF vision:** Full negotiation prep and strategy.
**How to implement:**
- New skill: `/negotiate`
- Input: Company, offer details (base, equity, bonus, benefits)
- Steps:
  1. Pull comp data (AmbitionBox, levels.fyi, Glassdoor)
  2. Benchmark against market (percentile analysis)
  3. Generate negotiation script with specific talking points
  4. Counter-offer range suggestion
  5. Email template for written negotiation
**Effort:** Medium
**Input needed from you:** Probably premature for intern roles in India where comp is mostly fixed. Worth building when you're at the offer stage.

---

## Tab 3: Prioritized Implementation Roadmap (Updated 2026-04-21)

### All Implemented

| Feature | Status | Date | Skill / File |
|---------|--------|------|-------------|
| #2 Resume Tailoring | DONE | 2026-04-21 | `/resume-tailor` |
| #4+#5 Outreach + Referral Workflow | DONE | 2026-04-21 | `/outreach` |
| STAR Story Bank | DONE | 2026-04-21 | `Jobs/star-stories.md` (10 stories + coverage matrix) |
| #6 Interview Prep | DONE | 2026-04-21 | `/interview-prep` |
| #7 Mock Interviews | DONE | 2026-04-21 | `/mock-interview` |
| #8+#9 Post-Interview Debrief + Thank-You | DONE | 2026-04-21 | `/debrief` |
| #10 Offer Negotiation | DONE | 2026-04-21 | `/negotiate` |

### Files Created
- `Jobs/resume-base.md` -- Master resume with 14 tagged bullets
- `Jobs/star-stories.md` -- 10 STAR stories with theme-to-story coverage matrix
- `~/.claude/skills/resume-tailor/SKILL.md` -- JD-specific resume builder
- `~/.claude/skills/outreach/SKILL.md` -- Referral networking + message drafting
- `~/.claude/skills/interview-prep/SKILL.md` -- Company-specific interview preparation
- `~/.claude/skills/mock-interview/SKILL.md` -- Interactive mock interview simulator
- `~/.claude/skills/debrief/SKILL.md` -- Post-interview debrief + thank-you emails
- `~/.claude/skills/negotiate/SKILL.md` -- Offer negotiation strategy + scripts

### Dropped (Not Needed)

| Feature | Reason |
|---------|--------|
| #1 Automated Daily Briefing | Manthan prefers on-demand. Already works via Brief Mode. |
| #3 Cover Letter | Unclear if needed for target roles. Revisit if encountered. |

---

## Tab 4: Resolved Inputs

| Question | Answer | Impact |
|----------|--------|--------|
| Base Resume | Provided PDF resume (14 bullets extracted to resume-base.md) | resume-tailor skill can now select per JD |
| Daily Briefing Schedule | "On demand" -- no automated scheduling needed | Dropped from roadmap |
| Cover Letters | "I don't know" -- skip for now | Dropped from roadmap |
| STAR Stories | Doesn't have them yet. Wants to learn from peers. | Added story bank to P1 |
| Referral Importance | "Very important" | Upgraded outreach/referral to P0, now DONE |

### Still Open
- **Resume PDF export:** Do you need PDF output or is Markdown fine for now?
- **Dream company list:** Is profile.md's list still current?
