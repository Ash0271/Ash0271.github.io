---
layout: page
title: Brain Age Prediction with Hybrid Vision Transformers
description: IUSSTF–Viterbi Fellowship · University of Southern California · Summer 2025
importance: 2
category: research
---

**Advisor:** [Prof. Andrei Irimia](https://gero.usc.edu/labs/irimialab/), University of Southern California

**Code:** [github.com/Ash0271/brain-age-vision-transformer](https://github.com/Ash0271/brain-age-vision-transformer)

### Context

The IUSSTF–Viterbi program selects 15 students from India each year for a fully funded summer of research at USC. I chose its brain-imaging project.

The gap between a person's **predicted brain age** and their actual age is a biomarker: a brain that looks older than it should can be an early sign of neurodegenerative disease.

### The question

Can a **vision transformer**, which relates every part of an image to every other part, predict a person's age from a structural MRI scan?

### What I did

- Built a **3D vision transformer** on FreeSurfer-processed structural MRI scans from the UK Biobank, downsampled from 256³ to 128³ voxels.
- **Smaller patches:** reducing the patch size from 16³ to 8³ preserved finer anatomical detail and lowered validation error from 5.98 to 5.72 years.
- **Overfitting:** training error settled near 2 years while validation error stalled near 5. A plain transformer has no built-in sense of locality, and about 3,000 scans were too few to learn one.
- **Hybrid model:** drawing on my earlier forecasting work on combining models, I discussed the idea with the PhD student guiding me and we added a two-layer **convolutional stem** in front of the transformer. Validation error fell to 5.19 years.
- Replacing a learning-rate schedule that decayed too quickly with cosine annealing, and adding dropout, brought it to **4.83 years**.

### What I took from it

The result was still above published CNN baselines, but it showed that in a data-limited setting the right inductive bias matters more than model size.

### The question it left me with

Which brain regions was the model relying on, and do they match known patterns of brain aging?
