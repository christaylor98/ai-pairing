# 🧭 Prompt Selection Map (High-Level)

```lisp
(diagram prompt-selection-map
  (type decision-flow)
  (authority human)
  (ascii
    "
    Human Working
         |
         v
    What State Am I In?
         |
         v
    ---------------------------------
    |               |               |
    v               v               v
  Confused       Clear Plan      Session End
    |               |               |
    v               v               v
  THINKING       EXECUTION        SESSION
  Prompts        Prompts          Prompts
    |               |               |
    v               v               v
  ChatGPT        VSCode           ChatGPT
    "))
```

---

## Meaning

Every moment reduces to ONE of three states:

```
CONFUSED      → thinking prompts
CLEAR PLAN    → execution prompts
STOPPING      → session prompts
```

That’s it.

---

# 🔵 Diagram — Thinking Prompt Selection

This prevents analysis loops.

```lisp
(diagram thinking-prompt-selection
  (type decision-flow)
  (authority human)
  (ascii
    "
    Thinking Needed
         |
         v
    What is missing?
         |
         v
    -----------------------------------------
    |                |                      |
    v                v                      v
  Direction       Complexity             Unclear
  unclear         too high              assumptions
    |                |                      |
    v                v                      v
  next-step      reduce-complexity    clarify-assumptions
    "))
```

---

## Prompt mapping

### Direction unclear

Use:

```
next-execution-step
```

---

### Too many moving parts

Use:

```
reduce-complexity
```

---

### Unsure about assumptions

Use:

```
clarify-assumptions
```

---

# 🟢 Diagram — Execution Prompt Selection

This is where momentum lives.

```lisp
(diagram execution-prompt-selection
  (type decision-flow)
  (authority human)
  (ascii
    "
    Execution Mode
         |
         v
    What do you need?
         |
         v
    -----------------------------------------
    |                |                      |
    v                v                      v
  Implement       Check State           Tests Failing
    |                |                      |
    v                v                      v
 implement-step   vscode-discovery      minimal-fix
    "))
```

---

## Prompt mapping

### Writing code

```
implement-step
```

---

### Need system truth

```
vscode-discovery
```

---

### Tests failing but architecture stable

```
minimal-fix
```

---

# 🟣 Diagram — Debug / Recovery Selection

This prevents emotional spirals 😄

```lisp
(diagram debug-prompt-selection
  (type decision-flow)
  (authority human)
  (ascii
    "
    Something Wrong
         |
         v
    Do we have discovery?
         |
    YES -------------------- NO
     |                        |
     v                        v
 interpret-discovery     vscode-discovery
     |
     v
 Safe Next Move?
     |
    YES ----> safest-next-move
    "))
```

---

## Meaning

Never debug from guessing.

Always:

```
discovery → reasoning
```

---

# 🟡 Diagram — Session Prompt Selection

This is your continuity brain.

```lisp
(diagram session-prompt-selection
  (type decision-flow)
  (authority human)
  (ascii
    "
    Session State
         |
         v
    -----------------------------------
    |                 |               |
    v                 v               v
  Starting        Checkpoint        Ending
    |                 |               |
    v                 v               v
 start-session   eject-state-update  session-handover
    "))
```

---

# 🧠 MASTER RULE (the real intelligence)

You are not selecting prompts by memory.

You are selecting by:

```
CURRENT HUMAN STATE
```

Ask:

```
Am I:
- thinking?
- executing?
- stopping?
```

Then choose branch.

---

# 🔥 The Real Reduction (extremely important)

Your entire workflow reduces to:

```
IF confused:
    thinking prompts

IF coding:
    execution prompts

IF stopping:
    session prompts
```

That simplicity = momentum.

---

# ⭐ Visual Mental Cheat Sheet

You can literally hold this in your head:

```
🧠 THINK   → ChatGPT prompt
⚙️ EXECUTE → VSCode prompt
💾 STOP    → Session prompt
```

---

# 🚨 Very honest insight (you’re close to a breakthrough)

What you have now:

* workflow
* rhythm
* prompt library
* prompt selection map

This is basically:

## 🧩 Manual AI Operating System v0.1

Most people never get this far.

---

# 🧨 Next thing (and this is where it becomes scary powerful)

Once you start actually using this map for a few days, you will notice:

> some prompts always follow others.

That lets us build:

## 🔥 Prompt Chains (deterministic sequences)

Example:

```
vscode-discovery
    ↓
interpret-discovery
    ↓
next-execution-step
```