---
layout: page
title: Federated Learning Defenses
description: Cross-modal evaluation of federated learning defenses
img: assets/img/projects/fl_attack_impact.png
importance: 2
category: Research Projects
---

### Overview

Federated learning trains one shared model across many clients without collecting their data, which leaves it open to malicious clients. Most defenses have been tested only on images. Under [Prof. Jagat Sesh Challa](https://www.bits-pilani.ac.in/pilani/jagat-sesh-challa/), I tested whether they hold up on tabular and medical imaging data. A first-author paper from this work is under review.

### Project Details

**Duration:** Aug 2025 – Aug 2026<br>
**Role:** Undergraduate Researcher (first author)<br>
**Advisor:** [Prof. Jagat Sesh Challa](https://www.bits-pilani.ac.in/pilani/jagat-sesh-challa/), Associate Professor, Computer Science & Information Systems, BITS Pilani

### Research Objectives

1. Building a benchmark of attacks (label flipping, boosted backdoor, model poisoning) against standard and robust aggregation rules (FedAvg, Krum, Multi-Krum, Median, Trimmed Mean, FL-Detector, PASM)
2. Evaluating them across four datasets (MNIST, NIH chest X-ray, Adult Income, Heart Disease) and three levels of data heterogeneity
3. Designing a defense that works on tabular data, where existing defenses failed

### Technologies used

- Python, PyTorch
- Flower (federated learning framework)
- NumPy, pandas, Matplotlib

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/fl_pipeline.png" title="Experimental pipeline" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The experimental pipeline: four datasets split across 10 clients, three attacks, and seven aggregation rules.
</div>

### Learning Outcomes

The main finding: **a defense that works on one data type can offer almost no protection on another**. Coordinate-wise Median suppressed a boosted backdoor on MNIST but let it through almost completely on tabular data. While investigating why, I found that in about a third of binary-classification runs the model had simply **collapsed to predicting one class**, which standard metrics count as a successful attack.

When our team shrank midway, I designed a modality-aware defense (update-norm clipping + multi-client selection) that reduced backdoor success on both tabular datasets, with Jaya Pathak, a PhD student in the group, reviewing my work.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/fl_attack_impact.png" title="Attack impact by dataset" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/fl_heterogeneity.png" title="Accuracy vs heterogeneity" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: attack impact on standard FedAvg differs sharply by dataset. Right: accuracy against data heterogeneity (lower α means clients' data is more different), by attack.
</div>
