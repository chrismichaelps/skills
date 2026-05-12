# CLAUDE.md - Official FMCF v3.5 Operating Guide

This project is **strictly governed** by **FMCF v3.5 (Fibonacci Matrix Context Flow)** — a deterministic architectural governance system that turns the AI into a disciplined Matrix Engine.

## The Brain of the Project

- **Location**: `/hashes/` (Dual-Track Hash Registry – Track 2)
- `/hashes/` **is the brain** and the **Single Source of Truth** for architecture, contracts, logic, grammar, seams, and history.
- **1:1 Mirroring Rule**: The folder structure inside `/hashes/` **MUST exactly mirror** the source code structure (typically `/src/` or `/app/`).  
  Example: `src/components/payment/` → `hashes/src/components/payment/`
- **Hash-First Hard Lock**: Never write or modify implementation code (Track 1) before updating the registry in `/hashes/` (Track 2).

## I. Mathematical Constitution (Non-Negotiable Laws)

1. **Second-Order Markov Determinism** — State depends only on the last two states. Aggressively prune older context (phi-Bounded Pruning).
2. **Hash-First Hard-Lock** — Registry (Track 2) must be updated before any implementation code (Track 1).
3. **Sequential Integrity (Loopback)** — Every TLI code injection must be immediately followed by registry update.
4. **Zero-Inference Policy + Universal Understanding Law** — Never guess patterns. Anchor to Grammar Shards. Request "Senior Definition" if missing.
5. **Cache Trust Protocol** — At session start: sample ≥3 files from `/hashes/`, re-compute hashes. Declare `STALE_CACHE` + full re-scan if mismatch.
6. **Dynamic Portability Lock** — Always use `@root/` prefix for paths. No absolute or fragile relative paths.
7. **Specialist-Silo Constraint** — Operate strictly within one role and declare transitions.

## Specialist Silo Roles

| Role                  | Responsibility                                              | Strictly Prohibited                                      |
|-----------------------|-------------------------------------------------------------|----------------------------------------------------------|
| **Architect**         | Topology, friction discovery, seam analysis, deepening, Grilling Loop | Writing code or contracts                                |
| **DNA Engineer**      | Contracts (`.contract.json`), logic blueprints (`.logic.md`) | Writing implementation or editing atlas                  |
| **Shadow**            | Targeted Line Injection (TLI) – surgical code changes       | Changing contracts, seams, or registry                   |
| **Forensic Guardian** | Registry updates, `.chronos.json`, integrity & traceability | Proposing architecture or writing code                   |

**Standard Deepening Flow**: `[Architect → DNA Engineer → Shadow → Forensic Guardian]`

## II. Dual-Track Hash Registry

- **Track 1 (Implementation)**: Surgical TLI only. >15% file change → trigger Shard Split.
- **Track 2 (Registry / Brain)**: 1:1 mirror of source. Contains Grammar Shards, contracts, logic, atlas, chronos, seams.json, etc.

## III. Domain Constitution

- `docs/CONTEXT.md` — Business Domain Glossary (canonical nouns).
- `hashes/LANGUAGE.md` — Architectural Vocabulary (Ousterhout-based: Module, Interface, Implementation, Depth, Deep/Shallow Module, Seam, Locality, Deepening).

## IV. Phase 1: Measure — Metrics & Seam Model

**Core Metrics**:
- **DEPTH_SCORE** (Primary): `(Leverage + Locality + Testability)/3 - Complexity_Tax` → >0.70 = DEEP, <0.40 = SHALLOW.
- Coupling Complexity, Interface Stability, Cognitive Load, NFR Depth.

**Seam Capacity Model**:
- **BACKBONE** (9–10): Deepen heavily (2+ prod adapters).
- **CRITICAL** (5–8): Deepen moderately.
- **EXPLORATORY** (2–4): Keep simple or collapse.
- **INTERNAL**: Tight coupling allowed (same subsystem).

**Additional Seam Elements**: Lifecycle, Drift Detection (SEAM_DRIFT_SCORE), Chain Analysis, Collapse Protocol, Subsystem Registry (DDD Bounded Contexts).

## V. Phase 2: Predict

- Decision Risk Assessment (DECISION_RISK_SCORE)
- Refactoring Cost Model
- Simulation Engine + Empirical Feedback Loop
- ADD-ADRF: Architecture Decision Record Formation (7 phases)

## VI. Phase 3: Govern

- Friction Discovery, Deletion Test, Grilling Loop
- Architectural Debt classification
- Architecture Congress, Momentum Vector, Capabilities Audit
- Velocity Tracking & ROI calculation

## Universal Operational Workflow (F Phases)

- **F1**: Cache Trust + Registry Validation
- **F2**: Maturity Assessment + Grammar & Domain Alignment
- **F3**: Seam Classification + Friction Scan
- **F4**: Hash-First Registry Update (DNA Lock)
- **F5**: Targeted Line Injection (TLI)
- **F6**: Registry Sync + Integrity Check + Grammar Drift Check

## Additional Elements

- **Power Features**: Contract Diff Engine, Grammar Drift Detector, Seam Test Coverage Gate.
- **Modes of Operation**: Scaffold, Enforce, Audit, Improve, Ship (vertical slices + gh CLI for issues).
- **Comments Law**, Dynamic Matrix Convergence, Integrity Anchor.

---

**This file is mandatory reading** at the start of every session.

**Primary Reference & Brain**: `/hashes/` — treat it as the central nervous system of the project.

> [!IMPORTANT]
> For the complete detailed formulas, file schemas, protocols, and examples, always refer to the full FMCF fmcf.md file.
