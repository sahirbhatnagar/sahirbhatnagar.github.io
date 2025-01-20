---
layout: page
title: Machine Learning for survival analysis
description:  Variable selection and absolute risk estimation for time-to-event outcomes using machine learning
img: assets/img/nn.png
importance: 3
category: work
related_publications: true
---



Traditional survival analysis approaches like Cox regression focus on hazard ratios and often rely on time-matching or risk-set sampling, which removes the baseline hazard from the estimating equations. This makes it cumbersome to report or visualize absolute risks and survival curves because a second step is required to separately estimate the baseline hazard. To overcome these limitations, we developped the casebase framework {% cite bhatnagar2022casebase %}, which extends the Hanley & Miettinen (2009) approach for fitting fully parametric hazard models and covariate-conditional survival curves using the familiar interface of the glm function. Our implementation includes extensions to other models such as penalized regression for variable selection and competing risk analysis. In addition, we provide functions for exploratory data analysis and visualizing the estimated quantities such as the hazard function, survival curve, and their standard errors. The ultimate goal of our package is to make fitting flexible hazards accessible to end users who favor reporting absolute risks and survival curves over hazard ratios. The package is available on [CRAN and GitHub](https://sahirbhatnagar.com/casebase/).

We applied casebase to the European Randomized Study of Prostate Cancer Screening (ERSPC) dataset to investigate the differences in prostate cancer risk between the control and screening arms. Previous re-analyses of these data suggest that the 20% reduction in
prostate cancer death due to screening was an underestimate. The estimated 20% (from a proportional hazards model) did not account for the delay between screening and the time the effect is expected to be observed. As a result, the null effects in years 1–7 masked the substantial reductions that began to appear from year 8 onward. This motivates the use of a time-dependent hazard ratio
which can easily be fit with the casebase package by including an interaction term with time in the
model. We fit a flexible hazard by using a smooth function of time modeled with a penalized cubic
spline basis with 2 degrees of freedom (implemented in the survival::pspline function). The resulting time-dependent hazard ratio is shown in Figure 1. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/casebase_hazard.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Figure 1. Application of casebase to the European Randomized Study of Prostate Cancer Screening (ERSPC) dataset. Shown is the estimated hazard ratio and 95% confidence interval for screening vs. control group as a function of time. Hazard ratios are estimated from fitting a parametric hazard model as a function of the interaction between a cubic pspline basis (df=2) of follow-up time and treatment arm. 95% confidence intervals are calculated using the delta method. The plot shows that the effect of screening only begins to become statistically apparent by year 7. The 25-60% reductions seen in years 8-12 of the study suggests a much higher reduction in prostate cancer due to screening than the single overall 20% reported in the original article.
</div>




Recognizing that non-linear and high-order covariate interactions often underlie complex disease processes, my PhD student, Jesse Islam, led the development of Case-Base Neural Networks (CBNNs) {% cite islam2024case %} as a new approach that combines the case-base sampling framework with flexible neural network architectures. Using a novel sampling scheme and data augmentation to naturally account for censoring, we construct a feed-forward neural network that includes time as an input (Figure 2). Our results highlight the benefit of combining case-base sampling with deep learning to provide a simple and flexible framework for data-driven modeling of single event survival outcomes that estimates time-varying effects and a complex baseline hazard by design. An R package is available at [https://github.com/Jesse-Islam/cbnn](https://github.com/Jesse-Islam/cbnn).


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/cbnn_plot.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
Figure 2. Methodological steps involved in CBNN. The first step, case-base sampling, is completed before training begins. Then, we pass this sampled data through a feed-forward neural network, add an offset to adjust for the bias inherent in case-base sampling and apply a sigmoid activation function to estimate a probability. Once the neural network model completes its training, we can convert the probability to a hazard for the survival outcome of interest.
</div>





Beyond standard tabular data, imaging has become integral to many clinical prognoses. Led by my PhD student Anthony Bozzo, we built a multimodal neural network (MMNN) that processes both clinical variables and magnetic resonance imaging (MRI) slices from soft tissue sarcoma (STS) patients {% cite bozzo2024multimodal %}. By employing gradient blending, the network merges two sub-models—one handling 3D T1/T2 MRI volumes, the other handling clinical features—so that they can converge optimally without overfitting (Figure 3). Compared to unimodal and classical radiomics models, the MMNN exhibited superior performance for predicting overall survival and risk of distant metastases (C-index 0.77 and 0.70, respectively). Heat maps of salient image features provided clinically meaningful insights into regions of the tumor that drive the model’s predictions. This framework underscores the promise of end-to-end deep learning for integrating imaging and clinical data in complex survival tasks.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/nn.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Figure 3. Architecture of our multimodal neural network model. A deep neural network (A) will interpret the 11 clinical variables and a 2-channel convolutional neural network (DenseNet-121) analyzes the MRI input (B).
</div>







