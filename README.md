# Agentic Skills & Architecture

> **Wiki-first architectural governance for high-performance agentic engineering.**

This repo contains the operational skills and architectural patterns I use to keep autonomous agents from going off the rails. Completely framework-agnostic — no matter what stack you're using, these rules apply.

---

## Why this exists

If you've tried building complex software with AI, you know the drill: you give an agent a broad instruction, and eventually it loses the plot, hallucinates new architecture, or ignores existing patterns.

Standard prompt engineering isn't enough when you're scaling a codebase. You need strict, deterministic governance. You need the agent to behave like a disciplined senior engineer, not a creative writer.

---

## The core idea

**Build the entire application as a wiki first. Then code the wiki.**

Instead of hoping the AI guesses right, FMCF makes the agent author a complete **Obsidian-style wiki vault** — a second brain of interlinked Markdown notes describing the domain, architecture, modules, seams, and decisions of the system — *before* it writes a single line of implementation. Code becomes a faithful projection of the wiki.

The wiki — not the conversation history, not training data, not hash files — is the single deterministic source of truth. Every turn, the agent re-anchors to the vault. That's what actually kills context toxicity: the agent can't drift, because it's always reading current truth off disk.

---

## How it works

- **Wiki-First Hard-Lock** — the agent is constitutionally barred from writing implementation code for a module until that module exists as a complete page in the vault (purpose, interface, algorithm, negative logic, depth assessment). No page, no code.
- **The Vault is a real second brain** — `[[wikilinks]]`, backlinks, Maps of Content (MOCs), tags, aliases, and lightweight YAML frontmatter. Open it in Obsidian and navigate it like a knowledge base. The link graph *is* the dependency graph.
- **1:1 mirroring** — `wiki/src/` mirrors the application's source tree depth-for-depth: `src/api/router.ts` → `wiki/src/api/router.md`. Every source file has exactly one page (consolidating what v3.5 split across `router.hash.md`, `router.contract.json`, and `router.logic.md`). Alongside the mirror sit the FMCF-specific governance folders — `grammar/` (per-language Linguistic DNA shards) and `architecture/LANGUAGE.md` (canonical architecture vocabulary) — plus `domain/`, `seams/`, `subsystems/`, and `decisions/`.
- **grillme — autonomous self-grilling** — the agent interrogates its own design the way a tough senior reviewer would, and resolves every answerable question itself to the best production-grade default, recording the decision and rejected alternatives in the page's Grill Log. It never bounces an answerable question back to the user. Juniors get senior-grade decisions automatically; everything is documented and overridable.
- **handoff — zero-loss continuity** — when work passes between roles or a session ends, the agent writes a Handoff page into the vault. Any session, agent, or developer resumes by reading it — no reliance on conversation history surviving.
- **Seam-Driven Architecture** — boundaries are classified by capacity (BACKBONE / CRITICAL / EXPLORATORY / INTERNAL) and move through a defined lifecycle based on concrete events, not opinion.
- **Metrics before decisions** — every module is assessed across DEPTH_SCORE, coupling, stability, cognitive load, and NFR depth before any deepening decision. Architecture becomes data-driven.

---

## What's inside

```
/skills
  /fmcf
    SKILL.md        ← The core skill (FMCF v4.0 — Wiki-First Matrix)
```

### `SKILL.md` — FMCF v4.0

FMCF (Fibonacci Matrix Context Flow) is a complete operational specification for agentic software development — from a blank project to a governed, measurable, scalable codebase — organized around the wiki-first paradigm.

| Section | What it defines |
|---------|----------------|
| I. The Constitution | Five laws: Wiki-First lock, Wiki-as-Truth determinism, Sequential integrity, the Grammar law, and the Autonomous Resolution Law |
| II. The Wiki Vault | The Obsidian-style vault layout, its mechanics (wikilinks, MOCs, backlinks, tags, frontmatter), and *distillation* — the act that replaced hashing |
| III. The Four Roles | Architect / DNA Engineer / Shadow / Forensic Guardian — who writes which page types, and how they hand off |
| IV. Phase 1: Measure | DEPTH_SCORE and companions, the full seam model (capacity, lifecycle, drift, chain analysis, collapse), and maturity calibration |
| V. Phase 2 & 3: Predict & Govern | Decision risk, ADRs, friction discovery, the Deletion Test, and a lean governance dashboard on the Architecture MOC |
| VI. grillme & handoff | The two autonomous protocols — self-grilling to senior-grade decisions, and zero-loss continuity through Handoff pages |
| VII. Operational Workflow | The strict step sequence every session follows — open the vault, align, map impact, author the page first, project to code, verify, close the loop. No git-commit step |
| VIII. Page Schemas | Lightweight Markdown + frontmatter templates for every page type: module, seam, domain, grammar, ADR, LANGUAGE, CHANGELOG, INDEX/MOC |
| IX. Comments Law | Code comments mirror the wiki, briefly |
| X. Modes of Operation | Scaffold the vault / Enforce / Audit / Improve / Ship |
| XI. Integrity Anchor | The four constitutional invariants |

### Mode 5: Ship — the `gh` bridge

The `Ship` mode converts any approved ADR, plan, or set of wiki pages into independently-executable GitHub issues using vertical slices via the `gh` CLI. Slices are classified as AFK (Shadow can execute autonomously) or HITL (requires human judgment), ordered by dependency, and created with full traceability — linking back to the governing wiki pages rather than to commit SHAs. Because creating issues is an outward-facing action, it's the one place FMCF asks for explicit approval before acting.

---

## Key concepts

**Module, Interface, Implementation** — grounded in Ousterhout's *A Philosophy of Software Design*. A module is any unit with an interface and an implementation. The interface is everything a caller must know to use the module correctly — not just the signature, but invariants, error modes, ordering constraints, and side effects. The implementation is the body of code that carries out those promises, hidden from callers by design.

**Deep vs. shallow modules** — depth is the ratio of behaviors a caller can exercise to the interface they must learn. A deep module provides powerful functionality behind a simple interface. A shallow module has a complex interface relative to what it does. DEPTH_SCORE operationalizes this ratio; deepening is the act of redesigning an interface to hide more complexity behind a simpler surface.

**Distillation** — the act that replaced hashing. To distill a module is to write its essence into its wiki page so completely that the page alone is enough to rebuild the code. The page *is* the fingerprint. No hash files, no cache-trust gate — drift is caught by reading the page against the code.

**Seam lifecycle** — a seam moves HYPOTHETICAL → EXPLORATORY → CRITICAL → BACKBONE based on concrete events (adapter count, change frequency), not opinion. Seams that never earn a second adapter after 6 months are collapsed, not left as dead abstraction weight.

**Grammar page** — the sovereign truth for syntax. Before writing a line, the agent anchors to a language-specific page defining SDK versions, import paths, prohibited patterns, and architectural laws. If a pattern is missing, the agent records a Senior Definition Needed note rather than guessing.

**Autonomous Resolution** — the agent resolves every answerable design question itself, to the best senior default, and documents it. It only escalates genuine business/product decisions — and even then picks a safe default and flags it rather than blocking.

---

## Using the skill

Drop `skills/fmcf/SKILL.md` into your agent's skills directory, or paste it directly into your context / system prompt. Works with any agent that accepts Markdown instructions. The skill is self-contained — every schema, protocol, and decision rule is defined inline. No external dependencies, no scripts to run: Mode 1 (Scaffold) builds the vault by authoring pages, not by executing a scaffolder.

For projects that grow beyond a single session, the page schemas in Section VIII give you a full vault structure you can grow into any repo — and the Handoff pages mean you can stop and resume across sessions with zero context loss.

---

Built for engineers who need predictable, high-velocity output from their agentic systems.
