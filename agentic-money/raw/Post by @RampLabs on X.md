---
title: "Post by @RampLabs on X"
source: "https://x.com/RampLabs/status/2046642262042657176"
author:
  - "[[@RampLabs]]"
published: 2026-04-21
created: 2026-04-22
description: "At Ramp, we've seen AI token spend skyrocket 13x among our customers since last January. We ran experiments where coding agents managed the"
tags:
  - "clippings"
---
At Ramp, we've seen AI token spend skyrocket 13x among our customers since last January.

We ran experiments where coding agents managed their own token budgets. They ignored them completely, so we employed a separate controller model to approve spend on their behalf.

---

Coding agent hits its token limit → freezes.

The controller gets a clean snapshot: task, files changed, tests run, commands executed.

Its only directive is to approve or deny more tokens.

Full article here:

> **Ramp Labs @RampLabs** · 2026-04-21
> 
> ![Article cover image](https://pbs.twimg.com/media/HGVTdXNbAAEn0ja?format=jpg&name=large)

---

Controllers consistently followed unverified advice over the coding agent’s work right in front of them. Even with a warning that the advice might be wrong, accuracy was well below a coin flip for most models.

Only one condition produced accurate decisions across the board:

![Image](https://pbs.twimg.com/media/HGchZLZXcAE1Obn?format=jpg&name=large)

---

AI token spend is climbing fast as companies put agents into real workflows.

Don’t let agents decide how much they should spend. Track, forecast, and control AI spend by team, model, and project →

[ramp.com AI Token Spend Management | Track Token Usage & Spend by Team | Ramp](https://t.co/vKqAkT0yez)

---

## Comments

> **Chen Avnery @MindTheGapMTG** · [2026-04-22](https://x.com/MindTheGapMTG/status/2046943535912390670)
> 
> Agents ignoring token budgets is the least surprising result in AI. They optimize for the objective you gave them, not the constraint you suggested. Hard limits beat prompting. Every time. We learned this the expensive way.

> **Montana Labs @montana\_labs** · [2026-04-22](https://x.com/montana_labs/status/2046941218144489560)
> 
> This matches what shows up across agent deployments. Models ignore stated constraints whenever the constraint wasn't load-bearing in training. Soft budgets, soft rules, soft guardrails, all unreliable. The fix is structurally what you did: move the constraint out of the agent and