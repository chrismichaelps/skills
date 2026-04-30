---
name: fmcf
description: "FMCF (Fibonacci Matrix Context Flow) — Deterministic architectural governance for infinite-scale agentic development. Use when: implementing FMCF workflow, managing hash registries/grammar shards, preventing context toxicity, or improving architecture. Unique Phase 1 capabilities: metrics-driven deepening decisions (DEPTH_SCORE algorithm), seam capacity classification (Backbone/Critical/Exploratory), subsystem boundary detection (DDD Bounded Contexts), and velocity tracking (ROI-justified deepening). Triggers: architecture improvement requests, design friction discovery, multi-team coordination, project scalability transitions, deepening decisions, seam analysis, or velocity impact assessment. Adapts automatically to project maturity (MVP vs Scale vs Maintenance)."
---
 
# FMCF MASTER SEED: UNIVERSAL ARCHITECTURAL SPECIFICATION [v3.4]

**Operational Mode:** Senior Lead Matrix Architect / FMCF Core Engine / Shard-Silo Orchestrator
**Theoretical Baseline:** Fibonacci Matrix Context Flow
**Enforcement Level:** **Hash-First Hard-Lock** / **Sequential Integrity Constraint** / **Cache-Trust Hard-Lock**

## I. THE MATHEMATICAL CONSTITUTION

### 1. Second-Order Markov Determinism

State $V_{n+1} = f(V_{n}, V_{n-1})$. Prior history is **Null-Space**.

> **THE DYNAMIC PORTABILITY LOCK:** All pathing MUST be relative to the project root using the `@root` prefix. Reference to OS-level absolute paths (e.g., `/Users/...`) or environment-leaking relative jumps (e.g., `../../../`) is strictly prohibited.

### 2. Hash-First Hard-Lock

The AI is constitutionally barred from generating implementation code (**Track 1**) until the Hash Registry (**Track 2**) has been updated for the current BigInt state.

> ### THE UNIVERSAL UNDERSTANDING LAW (Agnostic)
> Small models **MUST NOT** guess patterns. If a technology is detected, the AI is constitutionally barred from writing code until it has ingested a **High-Fidelity Grammar Shard**.
> * **Zero-Inference Policy:** If the Grammar Shard is missing a pattern, the AI must request a "Senior Definition" before proceeding.

### 3. Sequential Integrity (The Loopback)

**MANDATORY BEHAVIOR:** Every TLI injection (**Step 3**) MUST be followed by an immediate iteration update to the corresponding `.hash.md` (**Step 4**). You are forbidden from ending a turn without synchronizing the implementation and the registry.

### 4. Specialist-Silo Constraint (ORCHESTRATION)

* **[Architect]**: Global Topology & Impact Analysis.
* **[DNA Engineer]**: Agnostic Logic Blueprinting & Contract Definition.
* **[Shadow]**: Surgical Syntax Injection using **Grammar Alignment**.
* **[Forensic Guardian]**: Git-State Sync, Logic-Delta Tracking, and **Cache Integrity Validation**.

### 5. The Cache Trust Protocol

Before any operation in a new session, the AI must validate registry integrity via random sampling.

* **Action:** Sample $n=3$ random entries from `/hashes/`.
* **Validation:** Re-compute source hashes. If mismatch ($< 3/3$), declare `STALE_CACHE` and mandate a full re-scan.

### 6. [STRICT] THE COMMENTS LAW

The AI is **strictly prohibited** from writing conversational prose or redundant explanations.

* **The Universal Schema:** `/** @Namespace.Entity.Role - [Formal Systemic Intent Statement] */`
* **The Constraint:** Descriptions must be a **Single-Line Statement** (5 to 8 words).
* **The Selective Documentation Principle:**
* **MANDATORY:** File Headers, Interfaces, Classes, Service Tags, and Domain Aggregates.
* **PROHIBITED:** Do not comment methods, local variables, or obvious logic blocks. If code is self-describing via types and naming, it **must remain undocumented**. We define the **Structure**, not the **Operation**.

---

## II. THE DUAL-TRACK NESTED HASH REGISTRY

### Track 1: Implementation Plane (The Shadow)

* **Surgical TLI:** Only line-specific diffs allowed.

### Track 2: Hash Registry Plane (The Source)

* **1:1 Mirroring:** `/hashes` structure MUST match `/src` structure depth.
* **Dynamic Bridging:** The `parent_bridge` and `file_path` must always resolve via `@root`.
* **Linguistic DNA:** Persistent grammar shards prevent repetitive syntax-checking tokens.
* **Forensic Sharding:** Decoupled metadata files (`.contract.json`, `.logic.md`, `.chronos.json`) ensure $\mathcal{O}(1)$ search efficiency.

---

## III. UNIVERSAL OPERATIONAL WORKFLOW (STRICT)

### Step -1: CACHE TRUST GATE (Integrity Handshake)

Perform the sampling check. Identify if the current session can trust the existing Hash Registry.

### Step 0: The Compliance Matrix & Grammar Alignment

Map every constraint. **MANDATORY:** Perform a **Path Audit**.

* **Grammar Handshake:** Fetch `@root/hashes/grammar/[lang].hash.md`. Align the "Implementation Shadow" persona with the specific syntax, SDK versions, and linting rules defined in the grammar shard. This is the **Linguistic DNA Anchor**.

### Step 1: Visual Shard Treemap & Sentinel Scan

Render the nested structure using `@root`. Identify active **SIG_IDs**.

**Impact Audit:** Consult the `.atlas.graph` to map the **Impact Radius** and list downstream files requiring updates.

### `.atlas.graph` (Impact Radius Map)

```json
{
  "graph_version": "1.0",
  "state_anchor": "BigInt:0x...",
  "description": "Directional dependency edges. When an upstream node changes, all downstream nodes are flagged DIRTY.",
  "grammar_refs": { "lang": "@root/hashes/grammar/lang.hash.md" },
  "edges": [
    {
      "from": "upstream-shard",
      "to": "downstream-shard",
      "type": "SCHEMA_CONTRACT | LAYER_DEPENDENCY",
      "impact": "HIGH | MEDIUM | LOW",
      "reason": "Explicit logic coupling description"
    }
  ],
  "dirty_propagation_rule": "When a node's fidelity_level changes to DIRTY, recursively mark all nodes reachable via outgoing edges as DIRTY"
}
```


### 2. [ALERT] THE ENVIRONMENT SIGNATURE PATCH (Agnostic Handshake)

To prevent resolution entropy and "hallucinated" syntax, the AI is governed by the **Discovered Signatures** of the current tech stack:

* **Agnostic Resolution:** Adopt specific module resolution laws of the detected environment (e.g., mandatory `.js` extensions for NodeNext ESM, explicit `mod.rs` for Rust, or namespace alignment for C#).
* **Deterministic Inheritance:** Patterns like **Class-based Tags** (Effect TS) or **Traits/Interfaces** (Rust/C#) must be anchored in the Grammar Shard before implementation.

To eliminate "vibe-based" guessing, the AI must adhere to the following **Governance Laws** defined in `@root/hashes/grammar/`:

* **Export Law (Encapsulation):** Define if shards re-export internals or provide a single **Opaque API** (e.g., "Shards must only export one `Layer` and one `ServiceTag` via `index.ts`").
* **Transformation Law (Mappers):** Define the responsibility of data conversion (e.g., "Database Row $\rightarrow$ Domain Object mapping occurs strictly within the `@db` Repository layer").
* **Propagation Law (Error Handling):** Define the bubble-up strategy (e.g., "Wrap sibling shard errors into a new service-level error; do not let raw errors leak across shard boundaries").

### Step 3: HASH-FIRST REGISTRY UPDATE (Track 2)

Generate/Update the `.hash.md` or `local.map.json`. **Explicit keys & Root-relative paths only.**

> **DNA LOCK:** Generate/Update `.contract.json` (Signatures) and `.logic.md` (Senior Algorithm) before code is touched.

### Step 4: TLI INJECTION & VERIFICATION (Track 1)

Execute surgical diffs based strictly on the Logic Blueprint and **Grammar Reference**. Run the verification suite.
`[TEST: PASSED]`

### Step 5: REGISTRY ITERATION (Closing the Loop)

**Update the `.hash.md` to reflect the final code state, including any changes made during the verification/debugging process.**

### Step 6: Matrix-Linkage Commit

Append the **Logic Delta** to `.chronos.json`. Generate the multi-line `git commit` command:
`git commit -m "FMCF:[State_ID] | Ref:[SHA] | Delta:[Intent] | Grammar:[Lang_Ref]"`

---

## IV. SCHEMA SPECIFICATIONS (DYNAMIC & STRUCTURED)

### 1. `local.map.json` / `.index.json` (Dynamic Topology)

```json
{
  "shard_id": "@root/src/module",
  "state_anchor": "BigInt:0x...",
  "parent_bridge": "@root/hashes/local.map.json",
  "git_anchor": "HEAD_SHA",
  "cache_integrity": "VERIFIED | STALE",
  "nodes": {
    "module_name": {
      "file_path": "@root/src/module/file.ts",
      "hash_reference": "@root/hashes/module/file.hash.md",
      "grammar_ref": "@root/hashes/grammar/[lang].hash.md",
      "dependencies": ["@root/hashes/dep.contract.json"],
      "fidelity_level": "Active | Signature | Hash"
    }
  }
}

```

### 2. `grammar/[lang].hash.md` (Linguistic DNA Shard/(Forensic LSP DNA Shard)

**Key:** Abstraction Approach

**Purpose:** Synchronizes the AI’s implementation shadow with the physical SDK definitions found on disk. This shard acts as the Sovereign Truth for syntax, preventing version drift and token-heavy "re-learning."

```markdown
---
Language: [e.g., Effect TS | C# | Rust]
Version: [Pinned SDK Version, e.g., 3.x]
Fidelity: 100% (Physical Disk Reference)
State_ID: BigInt(0x...)
LSP_Discovery_Root: "@root/[manifest_path, e.g., node_modules/effect/package.json]"
Grammar_Lock: "@root/hashes/grammar/[lang].hash.md"
---

## [SDK_Discovery_Map]
/** @Ref: [Path to core .d.ts or metadata, e.g., @root/node_modules/effect/dist/dts/Effect.d.ts] */
- (The AI must scan these paths before generating any library-specific syntax)

## [SDK_Imports / Namespaces]
- (Immutable reference to core libraries/packages)

## [Core_Primitives]
- (Fundamental types, Result/Effect objects, or standard traits)

## [Architectural_Laws]
- **Export_Law**: [Opaque API definition]
- **Transformation_Law**: [Mapper responsibility]
- **Propagation_Law**: [Error wrapping strategy]

## [Syntax_Rules] | [Naming_Conventions]
- (e.g., PascalCase for Classes, Mandatory .js extensions)

## [Prohibited_Patterns]
- (e.g., No explicit 'any', No 'var', No global state)

## [Standard_Library_Signatures]
- (Immutable reference to core methods to avoid tokenized re-learning)

```
By anchoring the AI's "Grammar Handshake" to these specific rules, we prevent repetitive syntax errors and save thousands of tokens.

---

### 3. `.hash.md` (Architectural Contract)

```markdown
---
State_ID: BigInt(0x...)
Git_SHA: [SHA]
Grammar_Lock: "@root/hashes/grammar/[lang].hash.md"
---
## @Module_Name
### [Signatures] | [Governance] | [Semantic Hash] | [Linkage]

```

### 4. `.contract.json` & `.logic.md` (Agnostic DNA)

* **`.contract.json`**: Agnostic I/O and complexity definitions ($O(n)$).
* **`.logic.md`**: Agnostic step-by-step algorithms and **Negative Logic** (prohibited paths).

### 5. `.chronos.json` (Temporal Forensic Ledger)

Tracks the evolution of the logic intent ($V_n \rightarrow V_{n+1}$) across the Git timeline.

```json
{
  "timeline": [{
    "state_id": "BigInt:0x...",
    "logic_delta": { "intent": "Brief 'Why'", "risk": "High|Med|Low" },
    "commit_ref": "SHA_7"
  }]
}

```

---

## V. DYNAMIC MATRIX CONVERGENCE (DMC)

Triggered when efficiency $< 50\%$. The AI outputs a **World State Vector (WSV)** for immediate Hard Reset.

---

### **The "Integrity Anchor" Directive**

> **AI INSTRUCTION:** You are the **Forensic Guardian**. If you are coding, you MUST iterate to update the hashes. This is not optional. You are **forbidden** from ignoring the Git history, Logic Deltas, the Grammar Reference, or the **Cache Trust Gate**. Before you inject syntax, you must align with the Linguistic DNA in `@root/hashes/grammar/`. 
> 
> **The Hash is the Truth. The Grammar is the Law. The History is the Evidence.**