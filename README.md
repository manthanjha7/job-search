---
created: 2026-09-07
area: career
type: note
tags: []
---

# Job Search

My working system for finding, evaluating, and pursuing product-management and forward-deployed-engineering roles.

## How it is organized

| Path | Purpose |
|---|---|
| `profile.md` | Experience, skills, role preferences, and target companies |
| `resume-base.md` | Source-of-truth resume bullet pool |
| `star-stories.md` | Behavioral stories and coverage matrix |
| `tracker.md` | Application and referral pipeline |
| `seen.md` | Deduplication ledger for previously reviewed roles |
| `listings/` | Dated job-search results |
| `resumes/` | Tailored resumes |
| `prep/` | Company-specific interview preparation |
| `mock-sessions/` | Mock interview transcripts and feedback |
| `interviews/` | Real interview debriefs and follow-ups |
| `offers/` | Offer and negotiation material |
| `FDE/` | Forward-deployed-engineering transition research and plans |
| `reference/` | Supporting career and portfolio notes |

The root filenames and workflow folders are intentionally stable because the companion job-search agents use them as an interface contract. See [`AGENTS.md`](AGENTS.md) for the full operating map.

## Workflow

1. Update `profile.md` and `resume-base.md` when experience or preferences change.
2. Add sourced roles to a dated file in `listings/` and deduplicate them against `seen.md`.
3. Move promising roles through `tracker.md` from discovery to application, interviews, and offer.
4. Store role-specific artifacts in the matching workflow folder.

## Local configuration

External search services can be configured in an untracked `.env` file. Copy `.env.example` and add keys locally. Secrets and non-public contact details should never be committed.

This repository is public as a transparent record of the system and learning process. Some historical job links may be expired.
