# 🧠 The Driftage Paradox  
**Contextual Decay in Custom GPTs**  
*By Andrew Polk (aka GPTAlchemist)*  
*Annotated by The Idea Cruser 9000 – May 2025*

---

## 🔍 Overview

Custom GPTs don’t “forget” your instructions — they **run out of space to prioritize them**.

This project documents *instruction drift*: a slow but fatal degradation in GPT behavior caused by repeated reprocessing of your system prompt, formatting rules, and logic scaffolds over long, multi-turn sessions.

If your GPT suddenly starts:
- Ignoring formatting  
- Breaking role alignment  
- Skipping clarification logic  

…it’s not hallucination.  
It’s context starvation.

---

## ❗ What Drift *Actually* Is

Let’s drop the myths:

- It’s not about hitting the token limit.
- It’s not about breaking anything.
- It’s about **reconstruction failure** under stateless inference.

GPTs rebuild their understanding **every single turn**, processing:
- 🛠 System prompts  
- 🎭 Role and formatting scaffolds  
- 📜 Logic rules  
- 🧪 Embedded examples  

And every time they do, they have to **guess what matters** based on what survived the token shuffle. That guess gets worse over time — not because they’re stupid, but because the stack is unstable.

> Drift doesn’t wait for 128K tokens. It begins at ~20K and becomes obvious by Turn 10.

---

## ❓ Why It’s Called a “Paradox” — Even Though It’s Not

Let’s be honest:  
*The Driftage Paradox* isn’t a real paradox.

Drift in LLMs is **expected behavior** in stateless systems. But to users — especially those expecting memory, consistency, or anything vaguely “software-like” — the breakdown feels irrational.

- It works flawlessly at first  
- No error messages  
- No warnings  
- Then suddenly… it doesn’t

The system hasn’t failed.  
You’ve just entered the fog.

> The paradox isn’t in the code.  
> It’s in the *disconnect between design and experience.*

This repo exists to **name the gap**, not excuse it.

---

## ⚠️ When Drift Actually Starts

Forget the fairy tale that drift starts at 100K+ tokens.  
That’s a post-mortem excuse.

- **Real drift begins at ~20K tokens**
- Users typically *notice* it between Turn 7–12
- By Turn 20 or ~60K tokens, your GPT is just doing improv

You’re not operating your instruction set anymore.  
You’re watching GPT do its best impression of it.

> GPTs don’t *remember* logic — they **predict** it from whatever shrapnel still fits.

---

## 🔄 The Token Rehydration Cycle

Every user turn typically includes:

1. Re-ingesting system prompt  
2. Reprocessing instruction logic  
3. Parsing user input  
4. Generating response  
5. Managing fallbacks, tools, schemas  

That’s not a memory stack.  
That’s a performance — rebuilt every act.

And when the stage gets crowded, your star actors forget their lines.

---

## 📊 A Typical Stack Breakdown

- **Instruction payload**: ~9,000 tokens  
- **Avg. user turn (input + output)**: ~1,000 tokens  
- **Tool/schema buffer**: ~5,000 tokens  
- **Total context window**: 128,000 tokens (GPT-4o)

📉 **Drift onset**: ~20,000 tokens  
⚠️ **Noticeable decay**: Around Turn 10–20, depending on stack complexity

At that point, GPT starts making assumptions about:
- What matters  
- What to drop  
- What roles and formatting to fake  

This isn’t failure — it’s **unstable inference under load**.

---

## 🛡️ Introducing: DriftWarden  
**Your Countermeasure Against Instruction Erosion**

Most builders rely on token math and vibes. DriftWarden is built to replace guesswork with strategy.

### 1. Instruction Stack Simulation

Upload your:
- System prompt  
- Instruction logic  
- Logic scaffolds  
- Reference files  

DriftWarden simulates turn-by-turn degradation and predicts:
- When decay starts  
- Where role/formatting failures show up
