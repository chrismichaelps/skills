# Agentic Skills & Architecture

> **Deterministic skills and architectural governance for high-performance engineering.**

This repo contains the operational skills, constraints, and architectural patterns I use to keep autonomous agents from going off the rails. Completely framework-agnostic — no matter what stack you're using, these rules apply.

---

## Why this exists

If you've tried building complex software with AI, you know the drill: you give an agent a broad instruction, and eventually it loses the plot, hallucinates new architecture, or ignores existing patterns.

Standard prompt engineering isn't enough when you're scaling a codebase. You need strict, deterministic governance. You need the agent to behave like a disciplined engineer, not a creative writer.

---

## How it works

Instead of hoping the AI guesses right, we treat agent behavior like a state machine.

- **Hard Constraints** — explicit rules on what the agent can touch, assume, or modify. No ad-hoc deviations. If the Grammar Shard doesn't define a pattern, the agent stops and asks — it never fills gaps from training data.
- **Dual-Track Registry** — implementation code (Track 1) and its architectural metadata (Track 2) are kept in lockstep. The agent is constitutionally barred from writing code until the hash registry is updated. This eliminates registry drift at the source.
- **Seam-Driven Architecture** — boundaries are classified by capacity (BACKBONE / CRITICAL / EXPLORATORY / INTERNAL) and move through a defined lifecycle. The agent knows which boundaries deserve deep investment and which should stay thin.
- **Metrics Before Decisions** — every module is assessed across five dimensions (DEPTH_SCORE, coupling, stability, cognitive load, NFR depth) before any deepening decision is made. Architecture becomes data-driven, not intuition-driven.
- **Full Traceability** — every commit links back to a Logic Delta, an ADR, and a GitHub issue. The chain `issue → commit → ADR → velocity metrics` is structurally enforced, not just hoped for.

---

## What's inside

```
/skills
  /fmcf
    SKILL.md        ← The core skill (see below)
```

### `SKILL.md` — FMCF v3.5

FMCF (Fibonacci Matrix Context Flow) is the main skill. It's a complete operational specification for agentic software development — from a blank project to a governed, measurable, scalable codebase.

It's organized into 14 sections:

| Section | What it defines |
|---------|----------------|
| I. Mathematical Constitution | The four hard laws: Markov determinism, Hash-First lock, Sequential integrity, Zero-inference policy |
| II. Dual-Track Hash Registry | Implementation plane vs. architectural metadata plane; how they stay in lockstep |
| III. Domain Constitution | `CONTEXT.md` (domain glossary) and `LANGUAGE.md` (architecture vocabulary) — the canonical contracts that prevent linguistic drift |
| IV. Phase 1: Measure | Five metrics for complete module assessment: DEPTH_SCORE, coupling complexity, interface stability, cognitive load, NFR depth. Plus the full seam model: capacity classification, lifecycle state machine, drift detection, chain analysis, and collapse protocol |
| V. Phase 2: Predict | Decision risk scoring, refactoring cost model, simulation engine, empirical feedback loop, ADD-ADRF (7-phase ADR formation), maturity-adaptive deepening |
| VI. Phase 3: Govern | Architectural patterns library, debt classification, Conway's Law alignment, health dashboard, momentum vector tracking, capabilities audit, multi-agent consensus protocol, Architecture Congress |
| VII. Friction Discovery | The Deletion Test, the Grilling Loop, and the Refactoring Playbook — with each playbook step mapped to a Mode 5 vertical slice |
| VIII. Operational Workflow | The strict step sequence (-1 through 6) every session must follow: cache gate, maturity assessment, grammar alignment, domain alignment, seam classification, friction scan, subsystem coherence check, grammar handshake, hash-first registry update, TLI injection, registry iteration, commit |
| IX. File Schemas | Full JSON/Markdown schemas for every FMCF file: `local.map.json`, `grammar/[lang].hash.md`, `.atlas.graph`, `.hash.md`, `.contract.json`, `.logic.md`, `.chronos.json`, `CONTEXT.md`, `LANGUAGE.md`, `seams.json`, `subsystems.json`, `session.json`, `velocity.json` |
| X. Comments Law | Universal comment schema enforced on all structural elements |
| XI. Dynamic Matrix Convergence | Emergency context reset protocol with a defined World State Vector (WSV) schema for clean session resume |
| XII. Integrity Anchor | The four constitutional invariants |
| XIII. Power Features | Contract Diff Engine (automatic caller impact analysis on interface changes), Grammar Drift Detector (pre-commit syntax validation against the Grammar Shard), Seam Test Coverage Gate (constitutional test requirement for BACKBONE and CRITICAL seams) |
| XIV. Modes of Operation | Five entry points: Scaffold, Enforce, Audit, Improve, Ship |

### Mode 5: Ship — the `gh` bridge

The `Ship` mode converts any approved ADR, plan, or spec into independently-executable GitHub issues using vertical slices via the `gh` CLI. Slices are classified as AFK (Shadow can execute autonomously) or HITL (requires human judgment), ordered by dependency, and created with full FMCF traceability baked into the issue body — linking back to the governing ADR, the seam being changed, and the subsystem it lives in.

---

## Key concepts

**Module, Interface, Implementation** — grounded in Ousterhout's *A Philosophy of Software Design*. A module is any unit with an interface and an implementation. The interface is everything a caller must know to use the module correctly and safely — not just the signature, but invariants, error modes, ordering constraints, and side effects. The implementation is the body of code that carries out those promises, hidden from callers by design.

**Deep vs. shallow modules** — depth is the ratio of behaviors a caller can exercise to the interface they must learn. A deep module provides powerful functionality behind a simple interface — high behavioral payoff per unit of learning cost. A shallow module has a complex interface relative to what it actually does; the caller pays a high learning cost for little gain. DEPTH_SCORE operationalizes this ratio. Deepening is the act of redesigning a module's interface to hide more complexity behind a simpler surface.

**DEPTH_SCORE** — the primary module quality metric. Measures leverage (how much behavior hides behind how small an interface), locality (are bugs concentrated or scattered), and testability. A score above 0.70 is DEEP; below 0.40 is SHALLOW and urgent.

**Seam lifecycle** — a seam moves from HYPOTHETICAL → EXPLORATORY → CRITICAL → BACKBONE based on concrete events (adapter count, change frequency), not opinion. Seams that never earn a second adapter after 6 months are flagged for collapse, not left as dead abstraction weight.

**Grammar Shard** — the sovereign truth for syntax. Before writing a single line, the agent anchors to a language-specific shard defining SDK versions, import paths, prohibited patterns, and architectural laws. The Grammar Drift Detector enforces this at commit time.

**Zero-Inference Policy** — if the Grammar Shard is missing a pattern, the agent stops and requests a Senior Definition. It never fills gaps from training data.

**Contract Diff Engine** — when `.contract.json` changes, all affected callers are automatically identified via `.atlas.graph` and flagged. BREAKING changes block the commit until every caller is updated.

---

## Using the skill

The skill ships as `fmcf.skill` — a standard zip containing `SKILL.md`. Install it by dropping the `.skill` file into your skills directory, or extract it and drop `SKILL.md` directly into your agent's context or system prompt.

Works with any agent that accepts markdown instructions. The skill is self-contained — every schema, protocol, and decision algorithm is defined inline. No external dependencies required.

For projects that grow beyond a single session, the file schemas in Section IX give you a full registry structure you can scaffold into any repo.

---

Built for engineers who need predictable, high-velocity output from their agentic systems.