---
layout: page
title: Federated Learning Defenses
description: Cross-modal evaluation of federated learning defenses
img: assets/img/projects/fl_attack_impact.png
importance: 2
category: Research Projects
---

### Overview

Federated learning trains one shared model across many clients without collecting their data, which makes it vulnerable to a malicious client that manipulates its updates. Most defenses against such attacks have been developed and tested on image data alone. In this project, done under [Prof. Jagat Sesh Challa](https://www.bits-pilani.ac.in/pilani/jagat-sesh-challa/) at BITS Pilani, I tested whether these defenses hold up across vision, tabular and medical imaging data. The resulting paper, on which I am first author, is currently under review.

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

The main finding was that **a defense that works in one data modality can offer almost no protection in another**. Coordinate-wise Median, for example, suppressed a boosted backdoor on MNIST but let the identical attack through almost completely on the tabular datasets. No single defense was best everywhere.

While investigating why, I found a second problem. In about a third of the binary-classification runs, the model had simply **collapsed to predicting one class**. Standard metrics such as accuracy and attack success rate count this collapse as a successful attack, even though no backdoor was implanted. Separating real attacks from collapse changed how several results should be read.

To address the tabular failures, I designed a modality-aware defense that combines update-norm clipping with multi-client selection, which reduced backdoor attack success on both tabular datasets. Our team shrank midway through the project, so I took on more of the experiment design and writing than planned, with Jaya Pathak, a PhD student in the group, reviewing my work. It taught me to check what a metric is actually measuring before trusting it.

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
