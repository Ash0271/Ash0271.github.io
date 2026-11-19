---
layout: page
title: Modeling Cognitive Operations from Neural Data Analysis
description: Undergraduate thesis · National University of Singapore · Aug 2026 – present
importance: 1
category: Research Projects
---

**Advisor:** [Prof. Camilo Libedinsky](https://fass.nus.edu.sg/psy/people/libedinsky-camilo/), Department of Psychology, NUS, in collaboration with faculty in computing <!-- TODO: name the collaborating faculty if you want -->

So far, the thesis has focused on its first part: how need and surprise shape what an agent remembers. The project continues beyond the official thesis period.

### The question

Animals regulate their internal state: they eat when hungry and stop when full. Memory research suggests that experiences which are both surprising and relevant to the animal's needs are remembered more strongly. I wanted to know whether the same principle helps an artificial agent: **does an agent that remembers surprising, need-relevant events more strongly look after its needs better?**

### Setup

- A four-legged ant robot that has to keep **two nutrient levels** near their setpoints by finding red and blue food.
- The agent is a **DreamerV3** world-model agent, which learns a model of its environment and plans inside it.
- My plan had three stages: build a reliable baseline, add a memory signal, and evaluate it rigorously.

### A baseline that only looked like it worked

At first the baseline appeared to survive well. On closer analysis, it was following a habitual path and often eating the wrong food. Survival curves alone were hiding what the agent was actually doing. I reworked the environment and agent until survival required genuine foraging, and I now evaluate behavior (which food it chooses and when), not just how long it lives.

### The memory signal

I proposed a signal that combines two things:

1. **Surprise:** how much the agent's world model was wrong about what just happened.
2. **Homeostatic relevance:** whether its last action moved its internal state towards or away from the setpoint.

This signal controls how strongly the agent's memory updates. Through discussions with the group, I refined it so that changes **near the edge of survival count more**.

### Where it stands

In the latest frozen evaluation (5 seeds, 4 conditions, 16 episodes each), the distance-weighted version achieved the highest average survival of all variants. The differences are still within the confidence intervals, so I treat this as an early sign rather than a result, and I am now testing it with longer training.

### The question it raised

How should an agent, or a brain, decide which moment and which memory deserve credit for an outcome?

### Team

Regular discussions with a postdoc in reinforcement learning, a research assistant and a master's student in the group.
