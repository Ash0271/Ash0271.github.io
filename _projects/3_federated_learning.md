---
layout: page
title: Cross-Modal Evaluation of Federated Learning Defenses
description: BITS Pilani · Aug 2025 – Aug 2026 · First-author paper under review
importance: 3
category: research
---

**Advisor:** [Prof. Jagat Sesh Challa](https://www.bits-pilani.ac.in/), Department of Computer Science & Information Systems, BITS Pilani <!-- TODO: replace with his profile URL -->

### The question

Federated learning trains one shared model across many clients without collecting their data, which makes it vulnerable to a malicious client manipulating its updates. Most defenses against this have been developed and tested on **vision data**. Do they hold up on **tabular and medical data**?

### What I found

- **Defenses don't transfer across modalities.** A defense that suppressed a boosted backdoor attack on images offered almost no protection against the identical attack on tabular data.
- **Many "successful attacks" weren't attacks at all.** Looking closer, I found that in about a third of binary-classification runs the model had **collapsed** to predicting a single class. Standard metrics such as accuracy and attack success rate count this collapse as a successful attack, even though no backdoor was implanted.
- **A modality-aware defense.** Combining update-norm clipping with multi-client selection reduced attack success on tabular datasets.

### Takeaway

Defenses should be chosen according to the data modality, and evaluations need to check for collapse before reporting an attack as successful.

### Role

When our team shrank midway, I designed the modality-aware defense, with a PhD student reviewing my work. I am the first author on the resulting paper, currently under review.

**Tools:** Python, PyTorch, Flower
