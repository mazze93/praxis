# Praxis — Architecture

## The Sovereignty Stack

```
┌─────────────────────────────────────────────────────┐
│                      VOICE                          │
│              mazze-leczzare-blog                    │
│         Philosophy → Public Communication           │
└─────────────────────────────────────────────────────┘
                          │
┌─────────────────────────────────────────────────────┐
│                    COMMUNITY                        │
│                  Secure Pride                       │
│     First production deployment of Praxis           │
│     for LGBTQ+ communities under real threat        │
└─────────────────────────────────────────────────────┘
                          │
        ┌─────────────────┴─────────────────┐
        │                                   │
┌───────▼────────┐                 ┌────────▼───────┐
│   IDENTITY     │                 │   COGNITIVE    │
│   DAEDALUS     │◄───────────────►│ ContextSynapse │
│                │                 │                │
│ Who you are    │                 │ What you know  │
│ operationally  │                 │ and remember   │
│ VPN, terminal, │                 │ Bayesian priors│
│ browser, FS    │                 │ adaptive memory│
└───────┬────────┘                 └────────┬───────┘
        └─────────────────┬─────────────────┘
                          │
┌─────────────────────────────────────────────────────┐
│                  INFRASTRUCTURE                     │
│    template-python-secure-container                 │
│    secure-pride-aegis-icons                         │
│    Reusable primitives, secure build patterns       │
└─────────────────────────────────────────────────────┘
```

---

## Components

### Identity Layer — DAEDALUS
**Path**: `/Users/daedalus/Code/daedalus-`
**Stack**: zsh scripts, YAML config, ProtonVPN CLI, iTerm2, macOS Focus

The operational expression of identity. Manages the system state that surrounds you when you inhabit a given context: network (VPN), environment (terminal, SSH keys), attention (Focus modes, notifications), and filesystem visibility.

**Contexts**: `daedalus` (security), `ryan` (personal), `creator` (creative), `organizer` (community)

---

### Cognitive Layer — ContextSynapse
**Path**: `/Users/daedalus/Code/ContextSynapse`
**Stack**: Swift 5.8+, macOS 13+, local JSON persistence

The memory and adaptive intelligence layer. Maintains Bayesian priors around intent, tone, and domain — building a locally-owned model of how you think and work in each context. Deterministic, inspectable, no cloud dependency.

Per-user state at: `~/Library/Application Support/ContextSynapse/users/<context>/`

---

### Community Layer — Secure Pride
**Path**: `/Users/daedalus/Code/secure-pride`
**Stack**: Static HTML, Cloudflare Pages + DNS, `_headers` (HSTS, CSP)
**Domain**: securepride.org | **Repo**: `mazze93/Secure-Pride`

The first production deployment of Praxis principles for a community with real stakes. Privacy-first cybersecurity for LGBTQ+ communities. Every Praxis design principle applies here at its strictest — SOGI data protections, no telemetry, no tracking, pseudonymous accounts.

**Outstanding**: `_headers`, `_redirects` not yet created; Cloudflare Pages not configured.

---

### Infrastructure Layer
**Paths**:
- `/Users/daedalus/Code/templates/template-python-secure-container`
- `/Users/daedalus/Code/secure-pride-aegis-icons`

Reusable primitives. The Python secure container template provides a hardened, SBOM-signed baseline for any Praxis service. Aegis Icons provides the visual identity for Secure Pride — built to WCAG AA and accessibility standards.

---

### Voice Layer — mazze-leczzare-blog
**Path**: `/Users/daedalus/Code/mazze-leczzare-blog`
**Stack**: Astro, Cloudflare Functions

How Praxis speaks outward. The philosophy, the decisions, the reasoning — made public. The blog is not peripheral; it's how the system builds legitimacy and community beyond the code.

---

## Integration Points

### DAEDALUS ↔ ContextSynapse ✓ Built
`daedalus switch <context>` now carries cognitive state with the identity switch.

**New files in DAEDALUS:**
- `lib/state.sh` — tracks the active context in `~/.daedalus/state/current`
- `bin/_cognitive.sh` — save, load, and summarize ContextSynapse profiles

**Switch sequence:**
```
1. Load config
2. → save outgoing context's ContextSynapse state to ~/.daedalus/cognitive/<context>/state.json
3. VPN → Terminal → Browser → Notifications → Filesystem
4. → import incoming context's ContextSynapse state
5. → display cognitive summary:
      ── Cognitive context: ryan ─────────────────────
        Last active:  2026-02-26 14:30
        Intent:       Create (0.72)
        Tone:         Casual (0.81)
        Domain:       Personal (0.65)
      ────────────────────────────────────────────────
6. Context switch complete
```

**Non-blocking**: if ContextSynapse binary is absent or fails, the switch continues unaffected. All events logged to `~/.daedalus/logs/audit.log` (`COGNITIVE_SAVED`, `COGNITIVE_LOADED`, `COGNITIVE_INIT`).

**Context → user mapping**: DAEDALUS context names (`daedalus`, `ryan`, `creator`, `organizer`) map directly to ContextSynapse user IDs. Each context has its own isolated Bayesian profile.

---

### ContextSynapse → Secure Pride (Not yet built)
Adaptive prompting for community-facing AI tools. ContextSynapse's Bayesian engine can power privacy-preserving, locally-run AI assistance for Secure Pride users — no cloud, no context leakage.

---

## What's Built vs. What's Next

| Status | Item |
|--------|------|
| ✓ Built | DAEDALUS context switching (operational identity) |
| ✓ Built | ContextSynapse Bayesian engine (cognitive layer) |
| ✓ Built | DAEDALUS ↔ ContextSynapse integration (`lib/state.sh`, `bin/_cognitive.sh`) |
| ✓ Built | Secure Pride landing page + hosting config |
| ✓ Built | Python secure container template |
| ✗ Not built | Secure Pride `_headers` / `_redirects` / Cloudflare config |
| ✗ Not built | ContextSynapse → Secure Pride adaptive prompting |
| ✗ Not built | Praxis integration layer / shared protocol |
| ✗ Not built | Cross-device sync (encrypted, local-first) |
| ✗ Not built | Praxis installer / bootstrap script |
