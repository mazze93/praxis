# Praxis — Claude Context

Praxis is the overarching personal OS for identity sovereignty. Not a single project —
a system of interdependent components each owning one layer of the sovereignty problem.

## The System

| Layer | Component | Path |
|-------|-----------|------|
| Identity | DAEDALUS | `/Users/daedalus/Code/daedalus-` |
| Cognitive | ContextSynapse | `/Users/daedalus/Code/ContextSynapse` |
| Community | Secure Pride | `/Users/daedalus/Code/secure-pride` |
| Infrastructure | Templates, Aegis Icons | `/Users/daedalus/Code/templates/`, `secure-pride-aegis-icons/` |
| Voice | Blog | `/Users/daedalus/Code/mazze-leczzare-blog` |

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

## Critical Integration Gap
DAEDALUS (operational identity) and ContextSynapse (cognitive memory) are not yet connected.
`daedalus switch <context>` should also load/save the ContextSynapse profile for that context.
This is the highest-value unbuilt piece of the system.

## Full Docs
- Vision + manifesto: `README.md`
- Technical architecture: `ARCHITECTURE.md`
- Memory file: `~/.claude/projects/-Users-daedalus/memory/praxis.md`
