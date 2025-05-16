# 🧠 The Driftage Paradox  
**Contextual Decay in Custom GPTs**  
By Andrew Polk (aka GPTAlchemist)

---

## 🔍 Use Case Summary

Custom GPTs don’t get lazy — they get overloaded.

**The Driftage Paradox** names the slow collapse of instruction integrity that happens when system prompts are reprocessed recursively — until role, tone, and logic decay.

This repo frames the issue — and introduces the tool that combats it: **Driftwarden Profiler.**

---

## ❗ Problem Statement

Every GPT turn reloads everything:  
- System prompts  
- Role instructions  
- Format rules  
- Fallback logic  
- Examples and schema  

Not just the user's message.

The result? **Token congestion**, not memory loss.  
Your GPT isn’t forgetting — it’s **fighting for space**.

> Drift doesn’t slam into you. It creeps.

---

## 🧠 Solution Overview

### 🔎 **The Driftage Paradox** (Concept Layer)

Defines how recursive token loading causes GPTs to degrade over time:

- 🎭 Roles soften  
- 🔁 Format breaks  
- ❌ Clarification logic stops firing  
- 😵‍💫 Personality tone fades or contradicts itself  

Drift isn’t hallucination.  
> It’s **context starvation**.

---

### 🛡️ **Driftwarden Profiler** (Execution Layer)

Your first line of defense against GPT decay.

**Driftwarden** is a diagnostic engine that:

- Simulates token usage and behavioral decay over multi-turn sessions  
- Calculates when and where drift will hit  
- Injects logic to extend instruction durability and trigger warnings before collapse

---

## 🧰 What Driftwarden Includes

### 🧩 **Instruction Loader + Token Map**
Parses your instruction set, logic files, and example data  
→ Calculates token overhead  
→ Identifies what’s bloating you

---

### 🔁 **Interaction Lifecycle Simulator**
Replays multi-turn GPT usage:
- Clarifications
- Regenerations
- Tool call inflation
→ Models token accumulation over time

---

### 📉 **Drift Risk Calculator**
Projects safe interaction counts, then issues turn-based warnings:

```yaml
instruction_tokens: 8700
avg_interaction_cost: 1150
drift_threshold_tokens: 60000
projected_safe_interactions: 16
warn_at: 11
reset_recommended_at: 16
