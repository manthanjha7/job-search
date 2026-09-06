# Jobs/

Career life area: PM/APM job search pipeline, application materials, interview prep. Driven by the `jobs`, `resume-tailor`, `outreach`, `interview` (prep/mock/debrief, merged 14 Aug 2026), and `negotiate` skills.

## Layout
| Path | What lives here | Owned by |
|------|-----------------|----------|
| `profile.md` | Master profile: experience, skills, targets, dream companies (source of truth) | hand-edited |
| `resume-base.md` | Master bullet pool, tagged for JD matching | hand-edited |
| `star-stories.md` | STAR behavioral stories + coverage matrix | hand-edited |
| `tracker.md` | Application/referral pipeline status | `jobs`, `outreach` |
| `seen.md` | Dedup ledger of jobs already surfaced | `jobs` |
| `listings/` | Dated job-scout output (`YYYY-MM-DD.md`) | `jobs` |
| `resumes/` | Tailored resumes per role | `resume-tailor` |
| `prep/` | Per-company interview prep dossiers | `interview` (prep mode) |
| `mock-sessions/` | Mock interview transcripts + scores | `interview` (mock mode) |
| `interviews/` | Post-interview debriefs + thank-you emails | `interview` (debrief mode) |
| `offers/` | Offer details + negotiation prep | `negotiate` |
| `reference/` | Working/reference docs not read by skills | hand-edited |

Root file + folder names are a contract the skills hardcode — don't rename or move `profile.md`, `resume-base.md`, `star-stories.md`, `tracker.md`, `seen.md`, or the skill output folders.

## Skills — what each one does (job-search toolkit)

The career life area runs on 5 skills (was 7 until the three interview skills merged on 14 Aug 2026). They map roughly to the funnel: **find → apply → connect → prep → practice → debrief → negotiate.** Just say what you want in plain words (example phrases below) and the right skill fires.

| Skill | What it does | Use it when… | Say something like |
|-------|--------------|--------------|--------------------|
| `jobs` | Searches PM/APM/intern roles across LinkedIn, JSearch, web, career pages. Scores each 0–100 against `profile.md`, dedupes, validates open/closed, writes a dated listing + updates `tracker.md`. Also does status updates & stale checks. | You want fresh roles to apply to, or to update a job's status. | "find jobs", "scout PM jobs", "any new openings", "I applied to CRED", "shortlist Rupeek", "check stale jobs" |
| `resume-tailor` | Picks the most relevant bullets from `resume-base.md` for a specific JD, reorders sections, writes a targeted summary. Saves to `resumes/`. | You found a role and want a resume aimed at it. | "tailor resume for AlphaSense", "resume for [JD/role]" |
| `outreach` | Finds referral contacts at a target company on LinkedIn, drafts connection requests + referral asks, tracks referral status, writes follow-up nudges. | You want a referral or warm intro before applying. | "outreach for Clinikally", "find a referral at Paytm", "referral sweep for shortlisted jobs" |
| `interview` (prep mode) | Builds a per-company interview prep dossier (role, likely questions, your matching stories, company intel). Saves to `prep/`. | You have an interview scheduled and want to prepare. | "prep for [company] interview", "interview prep for Meesho" |
| `interview` (mock mode) | Runs an interactive mock PM interview — asks behavioral/product/analytical questions, grades answers on a rubric, suggests STAR swaps, tracks improvement. Saves to `mock-sessions/`. | You want to practice answering out loud before the real thing. | "mock interview", "mock me for CRED", "run a mock" |
| `interview` (debrief mode) | After a real interview: scores each answer, finds missed openings, rewrites weak answers, drafts a personalized thank-you email. Saves to `interviews/`. | You just finished an interview. | "debrief CRED", "I just interviewed at Paytm", "write thank-you email for [company]" |
| `negotiate` | Benchmarks the offer vs market, suggests counter ranges, writes negotiation scripts + emails. Saves to `offers/`. | You got an offer. | "got an offer from [company]", "negotiate offer from CRED", "help me counter" |

**Supporting context (not in `Jobs/`):** `profile.md` is the source of truth all of these read. Resume/portfolio bullets can also pull from the external project repos (COOX hackathon, Real Estate venture) per the root `CLAUDE.md`.
