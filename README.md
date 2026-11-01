# fullstack-guardian

Security-focused full-stack application scaffold built with the **fullstack-guardian** skill.

## Skill status

The `fullstack-guardian` skill (v1.1.1, @jeffallan) has been installed. Its complete output and supporting references were captured at:

- `/tmp/opencode/fullstack-guardian-output.txt`
- `/tmp/skills-use-nC3eZn/fullstack-guardian/` (SKILL.md + `references/`)

## Skill workflow

Per the skill, every feature follows this order:

1. **Gather requirements** — feature scope + acceptance criteria (no implementation without them)
2. **Design solution** — Frontend / Backend / Security three-perspective design
3. **Write technical design** — `specs/{feature}_design.md` (EARS-format requirements)
4. **Security checkpoint** — run `references/security-checklist.md` (auth, authz, validation, output encoding, rate limiting, logging) before any code
5. **Implement** — incrementally, testing each component
6. **Hand off** — to QA / Test Master

## Constraints (MUST DO / MUST NOT)

- Address all three perspectives (Frontend, Backend, Security)
- Validate input on client **and** server
- Use parameterized queries only (no SQL injection)
- Sanitize output (prevent XSS)
- Explicit response schemas — no sensitive data leakage
- Server-side auth as the gate; client header is convenience only
- Proper error handling at every layer (not happy-path only)
- Log security-relevant events

## Target stack

This repo is intended to be paired with the `zainpreneur-app` stack:
- Client: React 19 + Vite 7 + Tailwind 4 (port 5173)
- Server: Node + Express 5 + better-sqlite3 (port 4000)
- Tests: `node --test` (server) + Vitest (DOM)
- Gate: `npm run verify:all` (`npm run lint` = `tsc --noEmit`)

## Next step

Provide feature requirements (scope + acceptance criteria + auth rules) so implementation can begin per the skill workflow. No code is written until requirements and acceptance criteria are defined.

---

Maintained with [fullstack-guardian](https://github.com/jeffallan/claude-skills).
