# Agentic Skills & Architecture

> **Deterministic skills and architectural governance for high-performance engineering.**

This repo contains the operational skills, constraints, and architectural patterns I use to keep autonomous agents from going off the rails. It's completely framework-agnostic. No matter what stack you're using, these rules apply.

## Why this exists

If you've tried building complex software with AI, you know the drill: you give an agent a broad instruction, and eventually it loses the plot, hallucinates new architecture, or ignores existing patterns. 

Standard "prompt engineering" isn't enough when you're scaling a codebase. You need strict, deterministic governance.

## How it works

Instead of hoping the AI guesses right, we treat agent behavior like a state machine. 

*   **Hard Constraints:** Explicit rules on what the agent can touch, assume, or modify. No ad-hoc deviations.
*   **Architectural Flow:** Patterns like FMCF (Fibonacci Matrix Context Flow) are used to map out complex subsystems. This gives agents a rigid map so they don't bleed logic across bounded contexts.
*   **Procedural Skills:** The files in this repo act as strict operational manuals for the agent. They define exact inputs, outputs, and state transitions.

## What's inside

*   `/skills`: The markdown specifications. Drop these into your agent's context or system prompts to enforce predictable behavior in your own projects.

---
Built for engineers who need predictable, high-velocity output from their agentic systems.
