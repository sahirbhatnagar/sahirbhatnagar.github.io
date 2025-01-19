---
layout: page
title: Gene by environment interactions
description: High-dimensional gene by environment interactions with applications to maternal and child health
img: assets/img/maternal.png
importance: 1
category: work
related_publications: true
---


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/maternal.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>


Many of the HD features being collected in genomics ($$\mathbf{X}$$) may be influenced by lifestyle and demographic factors ($$E$$), and their interaction ($$\mathbf{X} \cdot E$$) is expected to play a role in predicting the response ($$Y$$). In HD settings however, power to estimate interactions is low, the number of possible interactions could be enormous, and their effects may be non-linear. In this setting, we propose two complementary approaches for detecting interactions with a key environmental or exposure variable (e.g. smoking, treatment). We first proposed a two-stage procedure called \texttt{eclust} for dimension reduction that performs unsupervised clustering on the HD features using the exposure information only {% cite bhatnagar2018analytic %}. In the second stage, these dimension-reduced variables, constructed without using the response, can then be used in predictive models of any type. In a second manuscript, we develop a supervised approach called \texttt{sail} for detecting non-linear interactions between $$\mathbf{X}$$ and $$E$$ on a continuous $$Y$$ {% cite bhatnagar2023sparse %} . Each feature in $$\mathbf{X}$$ is projected onto a set of basis functions to account for non-linear effects on $$Y$$. Our method can accommodate either the strong or weak heredity constraints using a combination of $$\ell_1$$ and $$\ell_2$$ penalties. Furthermore, we prove that \sail ~has the oracle property, i.e., it asymptotically performs as well as if the true model were known in advance. Using this methodology, my PhD student has extended this framework for dynamic treatment regime estimation {% cite bian2023variable %}. Future work in this area will focus on developing hierarchical convex penalties, as well as improving the computational algorithms and implementations for selecting optimal tuning parameters. We extended this to high dimensional GxE interactions {% cite st2023hierarchical %}.


