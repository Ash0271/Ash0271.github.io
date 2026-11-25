---
layout: page
title: Modeling Cognitive Operations from Neural Data Analysis
description: Final year undergraduate thesis at NUS
img: assets/img/projects/nus_soc.jpg
importance: 1
category: Research Projects
---

### Overview

For my final-year thesis, I am working with [Prof. Camilo Libedinsky](https://fass.nus.edu.sg/psy/people/libedinsky-camilo/) at the National University of Singapore on how need and surprise shape what an agent remembers. Animals remember surprising, need-relevant experiences more strongly, and I am testing whether the same principle helps an artificial agent look after its needs.

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

I first calibrated the environment (food value, metabolic rates and the robot's action distribution) so that results could be trusted. The baseline then appeared to survive well, but its behavior showed a habitual path and frequent wrong food choices, so I reworked the environment until survival required genuine foraging. The lesson: **summary metrics can hide what an agent is actually doing**.

After refining the relevance signal with my advisor and the group so that changes near the edge of survival count more, it achieved the highest average survival of all variants in a multi-seed frozen evaluation. The differences are still within the confidence intervals, so I treat this as an early sign, and I am now testing it with longer training.

