# CLAUDE.md

Guidance for agents working in this repository.

## What this repo is

A collection of framework-agnostic agentic **skills** — operational specifications that govern how autonomous agents build software. The flagship skill is **FMCF (Fibonacci Matrix Context Flow)**, a wiki-first architectural governance system.

This repo contains the *specifications themselves* (Markdown), not an application. There is no build, no test suite, no runtime. "Correctness" here means: the skill text is internally consistent, self-contained, and faithful to its stated paradigm.

## Layout

```
README.md              ← public-facing overview of the repo and FMCF
CLAUDE.md              ← this file
skills/
  fmcf/
    SKILL.md           ← the FMCF skill (the source of truth — edit this)
    fmcf.skill         ← a zip of SKILL.md for drop-in install (GENERATED — keep in sync)
```

## FMCF in one sentence

**Build the entire application as an Obsidian-style wiki vault first, then write code as a faithful projection of the wiki.** The wiki — not conversation history, not training data, not hash files — is the deterministic source of truth.

Current version: **v4.0 — Wiki-First Matrix** (the header in `SKILL.md` is authoritative).

### Core invariants the skill encodes
- **Wiki-First Hard-Lock** — no implementation code for a module until its wiki page exists.
- **1:1 Mirroring Law** — `wiki/src/` mirrors the app source tree depth-for-depth; one page per source file.
- **grillme** — the agent resolves every answerable design question itself, to a senior-grade default, and records it. It never bounces answerable questions to the user.
- **handoff** — role/session continuity is written to `wiki/handoffs/*` pages, never left in conversation memory.
- **Grammar Law** — no stack-specific syntax without anchoring to the FMCF-specific `grammar/[lang].md` page.

## Working conventions

- **Edit `skills/fmcf/SKILL.md` as the single source of truth.** `fmcf.skill` is a generated artifact.
- **After editing `SKILL.md`, regenerate the zip** so the packaged install matches:

  ```bash
  cd skills/fmcf
  rm -f fmcf.skill
  mkdir -p /tmp/fmcf-pkg/fmcf && cp SKILL.md /tmp/fmcf-pkg/fmcf/SKILL.md
  (cd /tmp/fmcf-pkg && zip -q -r fmcf.skill fmcf)
  mv /tmp/fmcf-pkg/fmcf.skill ./fmcf.skill && rm -rf /tmp/fmcf-pkg
  ```

- **Code fences inside schema examples:** when a schema example (already inside a ```` ```markdown ```` block) needs its own fenced code block, make the **outer** fence four backticks and the inner three, so they don't collide.
- **No git-commit step inside FMCF.** v4.0 deliberately removed commit enforcement from the workflow — do not reintroduce it into the skill text. (This is about the skill's *content*; committing changes to *this repo* is normal and expected.)
- **Keep the migration story intact.** `SKILL.md` documents how each v3.5 artifact (`.hash.md`, `.contract.json`, `.logic.md`, `seams.json`, etc.) maps into the v4.0 wiki pages. When changing schemas, preserve that mapping so existing FMCF vaults can migrate mechanically.

## Self-review before committing skill changes

There is no automated test. Before committing changes to `SKILL.md`, verify by reading:
1. **Consistency** — no references to dropped concepts as if they were still live (e.g. hash cache-trust gates, JSON registries, BigInt `State_ID`, a git-commit workflow step).
2. **Self-containment** — every schema, protocol, and decision rule is defined inline; no external script or file is required to use the skill.
3. **Paradigm fidelity** — every mechanic ultimately serves "wiki first, then code."
4. **Zip sync** — `fmcf.skill` was regenerated from the current `SKILL.md`.

A quick grep for stale terms after an edit:

```bash
grep -nE "scaffold\.py|\.atlas|\.chronos|seams\.json|velocity\.json|BigInt|SIG-|git commit -m|Hash-First|STALE_CACHE" skills/fmcf/SKILL.md
```

Hits should only ever appear as intentional "replaces X" migration notes, never as live mechanics.

## Git

- Default branch: `main`. A `dev` branch tracks the same content for staging.
- Commit messages end with the Co-Authored-By trailer when authored with an assistant.
