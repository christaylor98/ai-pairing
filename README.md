# ai-pairing

## Under construction - we are building out the core workflow and will have more documentation and examples soon. - Updating live as we go.


A practical workflow for pairing with AI tools effectively.

This repository defines a simple, repeatable way to work across:

- Human (authority)
- Reasoning AI (thinking)
- Execution AI (implementation)
- Local shell / tests / git (truth)

It is manual.
It is structured.
It is fast.
It is tool-agnostic.

---

## What This Is

A lightweight operating model for:

- Thinking clearly
- Executing quickly
- Preserving momentum
- Resuming work across sessions

If you've ever experienced:

- Context loss between AI sessions
- Overthinking before coding
- Coding without clarity
- Fatigue from constant context switching

This workflow solves that.

---

## Tool Roles

This workflow separates AI tools by role, not by brand.

You can swap tools freely as long as the role stays intact.

### 1️⃣ Reasoning AI

Used for:

- Clarifying intent
- Planning next steps
- Interpreting test failures
- Producing session handovers

It should **not directly modify your files**.

Examples:

- ChatGPT (web)
- Claude (web)
- Gemini (web)
- Any LLM used as a reasoning interface

Think of this as your *architect brain*.

---

### 2️⃣ Execution AI

Used inside your editor to:

- Implement clearly defined steps
- Apply diffs
- Perform mechanical refactors
- Run structured discovery commands

It should **not redesign architecture**.

Examples:

- VSCode + Copilot
- Cursor
- Claude CLI
- Codeium
- Any AI embedded in your editor

Think of this as your *hands*.

---

### 3️⃣ Truth Layer (Non-AI)

Mechanical reality.

- pytest
- unit tests
- compiler
- git status
- git diff
- shell output

If reasoning disagrees with the truth layer,  
the truth layer wins.

---

## Core Principles

1. Human owns intent.
2. Reasoning AI thinks.
3. Execution AI implements.
4. Tests and git decide truth.
5. Sessions are disposable.
6. State survives.

---

## The Loop

THINK → EXECUTE → VERIFY → THINK

- Think in your reasoning AI.
- Execute in your editor.
- Verify with tests.
- Adjust quickly.
- Repeat.

---

## Artifacts

The workflow revolves around three artifacts:

- PLAN_PROMPT
- DISCOVERY_REPORT
- SESSION_STATE.is

Only `SESSION_STATE.is` survives between sessions.

---

## Repo Structure

- `docs/` — human-facing explanations
- `prompts/` — structured `.is` operational prompts
- `artifacts/` — state templates
- `examples/` — minimal working examples

No automation engine.
No orchestration framework.
No governance layer.

Just a clean manual workflow.

---

## Getting Started

1. Read `docs/HUMAN_AI_WORKFLOW.md`
2. Review `docs/DAILY_OPERATING_RHYTHM.md`
3. Use prompts in `prompts/`
4. End sessions with `session-handover.is`
5. Start new sessions with `start-session.is`

That’s it.

---

## Scope

This repository defines a **manual collaboration protocol**.

It does NOT include:

- Automation systems
- AI orchestration engines
- CI integrations
- Tool plugins
- Model comparisons

Those are separate concerns.

---

## Why This Exists

Most people use AI conversationally.

This defines how to use AI operationally.
