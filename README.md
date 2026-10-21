# BaitQuest

**Play Smart. Stay Secure.**

BaitQuest is an open-source, self-hostable cybersecurity, privacy and fraud-awareness game platform. It helps organisations build lasting security habits through short, engaging weekly missions.

> **Project status:** Product discovery and UX validation. Production implementation has not started. The clickable SPA prototype is illustrative; authentication, persistence, scoring and other backend behaviours are not production-ready.

## Product goals

- Make security learning engaging, practical and accessible.
- Reward consistent participation and completion, not only high scores.
- Explain correct and incorrect decisions in plain English.
- Support organisation-specific schedules, branding and content packs.
- Preserve privacy, data integrity and fair competition.

## Current design direction

- One featured mission per week.
- One official attempt per weekly mission; interrupted attempts can be resumed during the active week.
- No gameplay timer, speed bonus or time penalty.
- After an official attempt, explain each important decision.
- Missed missions remain available for practice, but practice cannot change official results or award retroactive competition points.
- Annual leaderboard order: participation, completion, then average official mission score.
- Lifetime XP and levels persist across seasons; badges recognise learning milestones and demonstrated skills.

See [the Product Decision Register](docs/product-decision-register.md) for the workshop baseline and decisions that remain provisional.

## Proposed technology direction

The stack is still subject to UX and BDD validation. The current proposal is React + TypeScript + Vite, FastAPI, PostgreSQL, SQLAlchemy/Alembic, Docker Compose, Caddy, Pytest and browser-based end-to-end tests.

## Repository status

This repository currently contains product documentation and project-governance files. It is not yet a production application. Do not deploy it as a working service or assume that the prototype demonstrates production security controls.

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md), [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md), and [SECURITY.md](SECURITY.md) before contributing. Contributions are licensed under Apache License 2.0; no separate CLA is required at this stage.

## Licence

BaitQuest is licensed under the [Apache License, Version 2.0](LICENSE). See the licence file for terms, permissions and conditions.
