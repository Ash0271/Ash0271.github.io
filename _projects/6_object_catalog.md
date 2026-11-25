---
layout: page
title: Everyday Object Catalog
description: Classification, attributes and retrieval with lightweight vision transformers
img: assets/img/projects/oc_deit_tsne.png
importance: 1
category: Semester Projects
---

### Overview

A two-milestone project for CS F425 Deep Learning (Prof. Pratik Narang): a lightweight image system for a self-collected dataset of everyday objects that classifies an object, predicts its attributes and retrieves images from text. I built it end to end on my own.

### Project Details

**Duration:** Aug 2025 – Nov 2025<br>
**Course:** CS F425 Deep Learning, BITS Pilani<br>
**Instructor:** Prof. Pratik Narang<br>
**Code:** [github.com/Ash0271/everyday-object-catalog](https://github.com/Ash0271/everyday-object-catalog)

### Objectives

1. Collecting and curating a custom image dataset of 10 everyday object classes, with captions and identity-disjoint train/validation splits
2. Fine-tuning two lightweight vision transformers (DeiT-Tiny and MobileViT) as a shared backbone for classification, multi-attribute prediction and text-to-image retrieval
3. Comparing performance on my own dataset and on a larger pooled dataset combined across all teams, to study how dataset scale and diversity affect generalization

### Technologies used

- Python, PyTorch
- timm, Hugging Face
- scikit-learn, Matplotlib

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/oc_deit_tsne.png" title="DeiT embeddings (t-SNE)" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/projects/oc_deit_confusion.png" title="DeiT confusion matrix" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    DeiT-Tiny on my custom dataset. Left: a t-SNE view of the learned embeddings, with each object class forming its own cluster. Right: the confusion matrix on the validation set.
</div>

### Learning Outcomes

Most of the work was the data: collecting and cleaning images, building identity-disjoint splits and auditing class balance before training. On my dataset, DeiT-Tiny separated the classes almost perfectly, while MobileViT mainly confused lotion and shampoo bottles; the larger pooled dataset was harder and clearly showed the gap between memorizing and generalizing.

