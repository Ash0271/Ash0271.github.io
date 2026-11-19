---
layout: page
title: Everyday Object Catalog
description: Classification, attributes and retrieval with lightweight vision transformers
img: assets/img/projects/oc_deit_tsne.png
importance: 1
category: Semester Projects
---

### Overview

A two-milestone project for the Deep Learning course (CS F425) at BITS Pilani, taught by Prof. Pratik Narang. The goal was a lightweight, CPU-friendly image understanding system for a self-collected dataset of everyday objects: classifying an object, predicting its attributes (color, material, condition), and retrieving images from a text description. Although it was nominally a team project, I built it end to end on my own.

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

Most of the work in a project like this turns out to be the data. I collected and cleaned the images, wrote the scripts that build identity-disjoint splits (so the same physical object never appears in both training and validation), and audited the dataset for class balance and risky examples before training anything.

On my own dataset, DeiT-Tiny separated the classes almost perfectly, while MobileViT's main confusion was between visually similar lotion and shampoo bottles. The pooled cross-team dataset was harder, with more classes and far more varied photos, which made the gap between a model that memorizes a small dataset and one that generalizes much easier to see. Building retrieval on top of the same embeddings also showed how one backbone can serve several tasks at once.
