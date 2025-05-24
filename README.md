# 🧠 DriftWarden: Protocol Against GPT Signal Decay

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)

> “You didn’t lose control. You lost clarity.” — The IdeaCrusher-9000

---

## 📚 Table of Contents

- [:mag: Overview](#mag-overview)
- [:boom: What Drift Actually Is](#boom-what-drift-actually-is)
- [:question: The Paradox That Isn’t](#question-the-paradox-that-isnt)
- [:warning: When Drift Starts](#warning-when-drift-starts)
- [:cyclone: Signal Dilution in Action](#cyclone-signal-dilution-in-action)
- [:bar_chart: Typical Stack Breakdown](#bar_chart-typical-stack-breakdown)
- [:shield: Enter DriftWarden](#shield-enter-driftwarden)
- [:white_check_mark: Why It Matters](#white_check_mark-why-it-matters)
- [:brain: Final Takeaways](#brain-final-takeaways)
- [📄 Disclaimer](#-disclaimer)

---

## :mag: Overview

Custom GPTs don’t “forget” — they degrade.

What looks like broken logic, missing formats, or role confusion is just **instruction drift**: a predictable breakdown of clarity as token reprocessing outpaces signal retention.

If your GPT starts skipping logic, derailing tone, or collapsing schemas — it’s not hallucinating.

It’s drowning.

---

## :boom: What Drift Actually Is

Let’s stop pretending it’s about token limits or random bugs.

Every GPT turn re-ingests:
- 🛠 Your system prompt
- 🎭 Role and format scaffolds
- 📜 Logic rules
- 🧪 Embedded examples

...and evaluates what still matters based on position and recency.

The result? Earlier instructions **lose influence** by Turn 10 in heavy sessions — long before 128K tokens.

Stateless inference means every turn is a re-roll of your clarity dice.

---

## :question: The Paradox That Isn’t

It feels like betrayal:
> “It worked yesterday. Nothing changed. Now it’s broken.”

But the system didn’t fail — it functioned *exactly* as designed.

Driftage isn’t a bug. It’s a visibility gap between model behavior and user expectation. That’s the paradox.

Your GPT never forgets. It just re-prioritizes — badly.

---

## :warning: When Drift Starts

Myth: It begins at 100K tokens.

Reality:
- 🧠 Signal erosion can begin at **15–25K tokens**
- 🔁 Noticed typically by **Turn 7–12**
- 🛠 At ~60K tokens: role misfires, formatting loss, schema dropout

If you’re seeing weird behavior mid-chat, you’re likely **10 turns too late**.

---

## :cyclone: Signal Dilution in Action

Every interaction reprocesses the stack:

1. Reloads full instruction payload
2. Re-evaluates formatting/role prompts
3. Parses new user input
4. Generates output — with diluted weight for early logic

There’s no cache.
There’s no state.
Only a war of tokens, every turn.

---

## :bar_chart: Typical Stack Breakdown

| Component               | Tokens |
|-------------------------|--------|
| Instruction Payload     | ~9,000 |
| Avg. User Turn          | ~1,000 |
| Tool / Schema Buffer    | ~5,000 |
| Drift Onset             | ~20,000 |
| Full Window (GPT-4o)    | 128,000 |

By Turn 15:
- GPT **estimates** context
- **Approximates** roles
- **Forgets** the edge-case logic that made it work

---

## :shield: Enter DriftWarden

**Your line of defense against invisible drift.**

### 1. 🧪 Instruction Stack Simulation

Upload:
- System Prompt
- Instruction Logic
- Logic Scaffolds
- Reference Files

DriftWarden simulates token progression to predict:
- Onset of signal loss
- Where drift first appears
- Which behaviors degrade

It’s not magic. It’s foresight.

### 2. 📊 Turn-Based Drift Report

Every session gets a drift profile:
- Token + Turn estimates for signal decay
- Format/role/schema drop-off detection
- Entropy patterns by input type

This isn’t “vibes.” This is modeling.

### 3. 🧬 Soft_Reset.yaml Generator

Auto-builds a YAML you can embed in your GPT system with:
- Tone refreshers
- Role/format anchors
- Instruction recaps

Deploy manually or trigger after X turns.  
This isn’t a patch — it’s a **signal anchor.**

---

## :white_check_mark: Why It Matters

Without DriftWarden:
- Drift goes unseen until collapse
- Users blame hallucinations
- Builders patch blind

With DriftWarden:
- You measure degradation
- You enforce mid-session clarity
- You give users a reset vector

**Drift isn’t failure. It’s unmanaged clarity loss.**

---

## :brain: Final Takeaways

- Drift is not a capacity issue — it’s clarity decay
- Stateless inference is lossy, not broken
- The “Driftage Paradox” exposes design vs. perception
- DriftWarden gives builders a map, a meter, and a reset button

If your GPT starts acting “off,”  
it’s already been fading for 10 turns.

