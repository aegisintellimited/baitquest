# BaitQuest MVP — Product Decision Register

**Status:** Workshop baseline  
**Target MVP launch:** 1 December 2026

Items are marked **Confirmed**, **Proposed**, or **Open** so draft values do not become accidental requirements.

## Product purpose and principles

- **Confirmed:** BaitQuest is an open-source, self-hostable cybersecurity, privacy/data-protection and fraud-awareness game platform.
- **Confirmed:** Learning is the primary goal; the competition encourages regular engagement, not only high scores.
- **Confirmed:** Themes and organisation branding may change presentation, but must not change mission content, answers or scoring.
- **Confirmed:** Validate the clickable prototype and UX before finalising production architecture, schema and BDD acceptance criteria.
- **Confirmed:** Public GitHub repository: `aegisintellimited/baitquest`; Apache License 2.0; separate from Quantivis.
- **Confirmed:** No separate CLA is required at this stage. Contributions are offered under Apache License 2.0, subject to the project contribution guidance.

## Weekly missions and season

- **Confirmed:** One featured mission per week.
- **Confirmed:** Each organisation selects 52 missions from a 60-scenario library for its annual season. Selection is randomised once and fixed for that organisation/season.
- **Confirmed:** All players in an organisation receive the same weekly mission.
- **Confirmed:** Default start is Thursday at 6:00 PM in the organisation's configured timezone; organisations can configure day and time.
- **Confirmed:** Schedule changes take effect at the next weekly boundary by default, with an audit trail.
- **Confirmed:** Changing the weekly schedule does not reshuffle annual mission allocation.
- **Confirmed:** At rollover, completed results remain; unfinished official attempts expire without a fabricated full score. Missed-mission review/practice remains available.
- **Open:** Daylight-saving/timezone edge cases and exceptional immediate changes.

## Gameplay and attempts

- **Confirmed:** Hybrid missions may combine interactive stories, spot-the-threat, decisions, knowledge checks and meaningful branching.
- **Confirmed:** Target 3–7 minutes and typically 3–5 meaningful interactions; this is not a time limit.
- **Confirmed:** No timer, speed bonus or time penalty.
- **Confirmed:** One official attempt per weekly mission; interrupted attempts can resume during the active week.
- **Confirmed:** After finishing, provide question-by-question feedback in plain English for correct and incorrect decisions.
- **Confirmed:** Players who miss a mission can practise later. Practice cannot change official results, award retroactive competition points or be used to farm unlimited XP.
- **Confirmed:** Prototype authentication and persistence are simulated and must be labelled as such.

## Participation, completion and score

- **Confirmed — Participation:** At least one submitted answer to a scored interaction in the official mission. Opening a mission or reading instructions alone does not count.
- **Confirmed — Completion:** Reach the end and successfully submit the final response.
- **Confirmed — Mission score:** Normalised to 0–100 using explicit, versioned rules defined before publication.
- **Confirmed:** Partial credit only where authored; no speed-based scoring; scenario types must be scored fairly.
- **Confirmed:** Missed missions do not receive fabricated zero scores.

## Annual leaderboard

Ranking priority:
1. **Participation:** count of eligible weekly missions meaningfully engaged with.
2. **Completion:** count of official missions completed.
3. **Mission score:** average score across completed official attempts.
4. **Shared rank** if all three criteria remain equal.

- **Confirmed:** Compare players within the same organisation and annual season against the same scheduled mission calendar.
- **Confirmed:** Practice does not affect competitive ranking.
- **Open:** Final treatment of season joiners/leavers and exact average-score denominator rules.

## XP and progression

- **Confirmed:** XP and levels are personal progression, separate from leaderboard ranking.
- **Confirmed:** Lifetime XP persists across seasons; XP alone determines level.
- **Confirmed:** Practice cannot create unlimited repeatable XP; awards must be server-verified and idempotent.
- **Proposed level thresholds:** Rookie 0–199; Scout 200–499; Defender 500–999; Guardian 1,000–1,999; Sentinel 2,000–3,499; Champion 3,500–5,999; Legend 6,000+.
- **Proposed XP:** participation +10 per official mission; completion +40; first completed mission +25 once; five completed missions +50 once; ten completed missions +100 once.
- **Open:** Validate XP values and thresholds against realistic player journeys.

## Badges

### Five learning/engagement badges
1. **First Steps** — complete the first official mission. Proposed +25 XP once.
2. **Consistent Defender** — participate in four consecutive weekly missions. Recognition badge.
3. **Getting into the Groove** — complete five official missions. Proposed +50 XP once.
4. **BaitQuest Legend** — complete ten official missions in one season. Proposed +100 XP; earnable again in later seasons, preserving history.
5. **Lifelong Learner** — reach 25 completed official missions over the player's lifetime. Recognition badge.

### Two launch skill badges
6. **Threat Spotter** — demonstrate sound decisions across designated phishing, suspicious-message and fraud scenarios.
7. **Privacy Protector** — demonstrate sound decisions across designated privacy and personal-data scenarios.

- **Conditional future badge:** **Secure Operator**, only if starter content supports explicit criteria across secure workplace behaviour, account protection and safe information handling.
- **Confirmed:** Skill badges require evidence across multiple relevant scenarios, not one lucky answer.
- **Confirmed:** Criteria should be transparent and awards server-verified.
- **Open:** Final skill thresholds and XP bonus values.

## Visual direction and prototype

- **Confirmed:** Modern game-inspired default; friendly/corporate alternatives may be offered.
- **Confirmed:** Themes/branding cannot affect content, answers, feedback rules or scoring.
- **Confirmed:** Prototype covers dashboard, active mission, results/feedback, missed-mission practice, leaderboard, progression/badges and appearance settings.

## Architecture direction — proposed, not final

- React + TypeScript + Vite, FastAPI, PostgreSQL, SQLAlchemy/Alembic, Docker Compose, Caddy, Pytest and browser E2E.
- Modular monolith, one organisation per deployment; avoid mandatory Redis, WebSockets, worker fleet and external analytics.
- Separate presentation/themes, game engine/scoring, versioned content packs and persistence.
- Security, privacy, integrity, backup/restore, accessibility and auditability are release gates.

## Next steps

1. Refine and review the clickable SPA prototype.
2. Validate proposed reward values and close open scoring questions.
3. Finalise BDD acceptance criteria, including rollover, interruptions, duplicate submissions, cutoff races, content versioning and reward idempotency.
4. Finalise architecture and data model after UX/BDD review.
5. Bootstrap repository governance and keep the decision register current as decisions are confirmed.
6. Delay release if mandatory security, privacy, integrity, recovery or accessibility gates fail.
