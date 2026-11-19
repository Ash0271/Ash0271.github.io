---
layout: page
title: Hybrid Models for Solar Irradiance Forecasting
description: Ensemble learning for GHI prediction, published at IEEE ODICON 2026
img: assets/img/projects/ghi_rmse.png
importance: 4
category: Research Projects
related_publications: true
---

### Overview

This was my first research project, done as a study project under Prof. Sumanta Pasari at BITS Pilani. Accurate forecasts of global horizontal irradiance (GHI), the solar energy reaching the ground, matter for planning solar power. Statistical models capture regular patterns in GHI well, while deep learning models capture nonlinear ones, so we asked whether **combining them** forecasts better than either alone. The work was published at IEEE ODICON 2026 {% cite shukla2026solar %}.

### Project Details

**Duration:** Jan 2024 – May 2024<br>
**Role:** Undergraduate Researcher (second author)<br>
**Advisor:** Prof. Sumanta Pasari, Department of Mathematics, BITS Pilani<br>
**Code:** [github.com/Ash0271/ghi-hybrid-forecasting](https://github.com/Ash0271/ghi-hybrid-forecasting)

### Research Objectives

1. Learning the statistical (sliding-window ARIMA) and deep learning (BiLSTM) forecasting models built by a PhD student in the group
2. Designing a hybridization layer that combines them in four ways: weighted averaging (with blend weights found by NSGA-II multi-objective optimization), stacking (ARIMA predictions as a feature for a BiLSTM meta-model), bagging and boosting
3. Comparing all four across four Indian sites (Bhopal, Hamirpur, Jafarabad, Thiruvananthapuram) using RMSE, MAE, MAPE and R²

### Technologies used

- Python, NumPy
- scikit-learn (bagging, gradient boosting, evaluation)
- pymoo (NSGA-II multi-objective optimization)

<div class="row mt-3">
    <div class="col-sm-8 mt-3 mt-md-0 mx-auto">
        {% include figure.liquid loading="eager" path="assets/img/projects/ghi_rmse.png" title="RMSE by hybridization technique" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Forecasting error (RMSE) of the four hybridization techniques at each site. Boosting had the lowest error at all four.
</div>

### Learning Outcomes

I came into this project new to machine learning, so the first weeks went into teaching myself the base models and their code. I then built the hybridization layer on top, with the PhD student reviewing my work as it developed.

Boosting, which trains a model to correct the combined errors of the base models step by step, performed best at all four sites, and the hybrid outperformed both base models. The broader lesson stayed with me: **mixing models with different strengths often works better than relying on one**. I later reused this idea at USC, where adding a convolutional stem to a vision transformer helped it learn from limited brain MRI data.
