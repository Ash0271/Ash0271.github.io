---
layout: page
title: Modeling Cognitive Operations from Neural Data Analysis
description: Final year undergraduate thesis at NUS
img: assets/img/projects/nus_soc.jpg
importance: 1
category: Research Projects
---

### Overview

For my final year undergraduate thesis, I am working with [Prof. Camilo Libedinsky](https://fass.nus.edu.sg/psy/people/libedinsky-camilo/) at the National University of Singapore. The first part of the thesis asks how need and surprise shape what an agent remembers: animals regulate their internal state (eating when hungry, stopping when full), and memory research suggests that surprising experiences relevant to an animal's needs are remembered more strongly. I am testing whether the same principle helps an artificial agent look after its needs. The project continues beyond the official thesis period.

### Project Details

**Duration:** Aug 2026 – Present<br>
**Role:** Undergraduate Thesis Student<br>
**Advisor:** [Prof. Camilo Libedinsky](https://fass.nus.edu.sg/psy/people/libedinsky-camilo/), Associate Professor, Department of Psychology, NUS<br>
**Collaborators:** Faculty in computing, a postdoc in reinforcement learning, a research assistant and a master's student

### Research Objectives

1. Building a two-resource foraging environment in which a simulated four-legged robot (MuJoCo Ant) must keep two internal nutrient levels in range by finding red and blue food
2. Training a DreamerV3 world-model agent and establishing a reliable baseline
3. Designing a relevance signal that combines the agent's surprise with homeostatic valence (whether its last action moved it towards or away from its setpoint) and uses it to control how strongly its memory updates
4. Evaluating whether this need-driven memory improves survival and food choice

### Technologies used

- Python, JAX (DreamerV3)
- MuJoCo
- GPU cluster (PBS batch jobs)

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/nus_architecture.png" title="Agent and environment" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The agent and environment. The orange dashed path is my addition: a relevance signal built from the world model's surprise, an eligibility trace and the sign of homeostatic valence, which scales the recurrent memory update.
</div>

### Learning Outcomes

The first runs showed weak locomotion and episodes that ended before hunger mattered, so I calibrated the environment first: how much food is worth, how fast nutrients drain, and which action distribution lets the robot move well. Only after that could any result be trusted.

The baseline then appeared to survive well, but when I looked at its behavior rather than its survival curves, it was following a habitual path and often eating the wrong food. I reworked the environment and agent until survival required genuine foraging. This was the most important lesson of the project so far: **summary metrics can hide what an agent is actually doing**, so I now evaluate food choice and behavior, not just how long the agent lives.

I then added the relevance signal and, after discussions with my advisor and the group, refined it so that changes near the edge of survival count more. In the latest frozen evaluation across multiple seeds, this version achieved the highest average survival of all the variants I tested. The differences are still within the confidence intervals, so I treat it as an early sign rather than a result, and I am now testing it with longer training.

The work has left me with the question I want to keep pursuing: how should an agent, or a brain, decide which moment and which memory deserve credit for an outcome?
