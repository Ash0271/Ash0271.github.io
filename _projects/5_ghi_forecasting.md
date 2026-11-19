---
layout: page
title: Hybrid Models for Solar Irradiance Forecasting
description: BITS Pilani · Jan – May 2024 · Published at IEEE ODICON 2026
importance: 4
category: Research Projects
related_publications: true
---

**Advisor:** Prof. Sumanta Pasari, Department of Mathematics, BITS Pilani

**Code:** [github.com/Ash0271/ghi-hybrid-forecasting](https://github.com/Ash0271/ghi-hybrid-forecasting)

### The question

Statistical models capture regular patterns in solar irradiance well, while deep learning models capture nonlinear ones. Does **combining them** forecast global horizontal irradiance better than either alone?

### What I did

This was my first research project. New to machine learning, I taught myself the statistical (ARIMA) and deep learning (BiLSTM) models a PhD student in the group had built, then designed a hybridization framework comparing four ways of combining them: weighted averaging, stacking, bagging and boosting. The PhD student reviewed my work throughout.

### Result

The hybrid model outperformed both base models at all four Indian sites we studied. The work was published at IEEE ODICON 2026 {% cite shukla2026solar %}.

### Takeaway

Mixing models with different strengths often works better than using one, an idea I later reused at USC.
