---
layout: page
title: IUSSTF-Viterbi'25
description: My summer research internship at USC
img: assets/img/projects/usc_viterbi.jpg
importance: 1
category: Research Internship
---

### Overview

I spent the summer of 2025 at the University of Southern California, Los Angeles, as part of the [IUSSTF–Viterbi program](https://iusstf.org/iusstf-viterbi-program), doing research at the [Irimia Lab](https://gero.usc.edu/labs/irimialab/) led by [Prof. Andrei Irimia](https://gero.usc.edu/faculty/andrei-irimia-ph-d/). My project used deep learning to predict a person's brain age from structural MRI scans. The gap between predicted brain age and actual age is studied as a biomarker for neurodegeneration.

### Project Details

**Duration:** May 2025 – July 2025<br>
**Role:** Summer Research Intern<br>
**Advisor:** [Prof. Andrei Irimia](https://gero.usc.edu/faculty/andrei-irimia-ph-d/), Leonard Davis School of Gerontology, USC<br>
**Code:** [github.com/Ash0271/brain-age-vision-transformer](https://github.com/Ash0271/brain-age-vision-transformer)

### Research Objectives

1. Building a 3D Vision Transformer to predict brain age from structural MRI scans (UK Biobank)
2. Running ablation studies across architecture and training choices (patch size, depth, loss, optimizer, learning-rate schedule)
3. Exploring hybrid CNN–transformer architectures to reduce overfitting with limited data

### Technologies used

- Python, PyTorch
- FreeSurfer-processed MRI volumes
- NumPy, pandas, Matplotlib

<div class="row mt-3">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/usc_certificate.jpg" title="Final presentation day" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/usc_val_mae.png" title="Validation error of the models I trained" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The final presentation day, with Nikhil Chaudhari and Dean Prof. Cauligi Raghavendra in the left image, and the validation error of the models I trained in the right.
</div>

### Learning Outcomes

Working with about 3,000 UK Biobank scans, I first reduced the patch size from 16³ to 8³, lowering validation error from 5.98 to 5.72 years. When the model began to overfit, I discussed hybrid models with the PhD student I was working with and added a convolutional stem, bringing the error to 5.19 years; cosine annealing and dropout then took it to **4.83 years**.

The result was still above published CNN baselines, but it showed that with limited data, the right inductive bias matters more than model size. I left wanting to know which brain regions the model relied on.

