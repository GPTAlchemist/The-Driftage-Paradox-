# 🧠 The Driftage Paradox  
**Contextual Decay in Custom GPTs**  
Author: Andrew Polk (aka GPTAlchemist)  
Annotated by: The Instruction Alchemist  
Date: May 2025  

---

## 🔍 Overview  

Custom GPTs don’t “forget” your instructions — they run out of room to remember them.  
This document explores **instruction drift**: a behavioral slippage caused by repeated reprocessing of system prompts and logic over multi-turn sessions.

If your GPT suddenly ignores formatting, breaks role, or drops clarification behavior — it’s not hallucination.  
> It’s **context starvation**.

---

## ❗ Problem  

Contrary to popular belief, GPTs do **not** retain instructions as a one-time cost.  
**Every user turn re-ingests:**

- System prompt  
- Instruction logic  
- Role + formatting specs  
- Embedded examples  

Each interaction consumes tokens **not just for the message and reply**, but for all the scaffold you thought was already “loaded.”

---

## ⚙️ How Drift Works  

### 🔄 Token Rehydration Cycle  

1. System prompt reloads  
2. Instruction set reloads  
3. User message  
4. GPT response  

#### Example Loadout:

- Instruction payload: ~9,000 tokens  
- Avg. user interaction: ~1,000 tokens  
- Model limit: 32,768 tokens  
- Safety buffer: ~2,000 tokens  

**👉 Usable ceiling: ~20–23 turns before logic decay.**

---

## 🧭 Signs of Drift  

- Formatting breaks  
- Role behavior becomes fuzzy or inconsistent  
- Tool responses go silent or erratic  
- Clarification logic stops triggering  

This is not “confusion.”  
> It’s **out of space to reason.**

---

## 🛠️ What to Do  

### ✅ Track Per-Turn Token Cost  
Think of system instructions as a recurring charge, not a one-time load.

### ✅ Use Drift Watchdogs  
Warn users after ~20 turns. Prompt a context reset before collapse.

### ✅ Model Drift Explicitly  

```python
safe_interactions = floor((max_tokens - safety_buffer) / (instruction_tokens + avg_interaction_cost))
