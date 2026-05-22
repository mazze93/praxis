# Praxis — Claude Context

Praxis is the overarching personal OS for identity sovereignty. Not a single project —
a system of interdependent components each owning one layer of the sovereignty problem.

## The System

Post-Atlas paths (ritual completed 2026-05-22 — see `~/.claude/projects/-Users-daedalus/memory/user_transfer_plan.md`).

| Layer | Component | Path |
|-------|-----------|------|
| Anchor | Stele | `/Users/daedalus/Code/tools/stele` |
| Identity | DAEDALUS | `/Users/daedalus/Code/cognitive/daedalus` |
| Cognitive | ContextSynapse | `/Users/daedalus/Code/cognitive/ContextSynapse` |
| Agentic Trust | praxis-aegis | `/Users/daedalus/Code/cognitive/praxis-aegis` |
| Community | Secure Pride | `/Users/daedalus/Code/secure-pride/secure-pride-site` |
| Infrastructure | Templates, Aegis Icons | `/Users/daedalus/Code/templates/`, `/Users/daedalus/Code/secure-pride/aegis-icons` |
| Voice | Blog | `/Users/daedalus/Code/blog` |

## Core Thesis
Surveillance capitalism and hostile state actors target **cognitive substrate** — the living
context of who you are, what you think, what you're working on. Praxis keeps that substrate
local, private, and under your control.

## Design Principles
1. Local-first — no required cloud dependency
2. Privacy is the architecture, not a feature
3. Cognitive accessibility first (ADHD-accessible throughout)
4. Sovereignty requires composability — layers must integrate
5. The personal is political — built for communities with real stakes

## Integration Status

- **DAEDALUS ↔ ContextSynapse** — built. `daedalus switch <context>` saves/loads cognitive
  profiles via `lib/state.sh` and `bin/_cognitive.sh`.
- **DAEDALUS → praxis-aegis** — not yet built. Context switch should initiate/tear down
  a praxis-aegis session for the incoming identity.
- **ContextSynapse → praxis-aegis** — not yet built. Intent weights could auto-populate
  the `trigger` field (research/ops/write/admin) without per-call declaration.
- **ContextSynapse → Secure Pride** — not yet built. Adaptive local prompting for community tools.

## Full Docs
- Vision + manifesto: `README.md`
- Technical architecture: `ARCHITECTURE.md`
- Memory file: `~/.claude/projects/-Users-daedalus/memory/praxis.md`
