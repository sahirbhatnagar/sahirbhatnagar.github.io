---
layout: page
title: Causal Inference
description: Variable selection for individualised treatment rules
img: assets/img/smart_design.png
importance: 4
category: work
related_publications: true
---


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/smart_design.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1. Sequential Multiple Assignment Randomization Trial (SMART) design to optimize the delivery of a web-based, stress management intervention for patients with a cardiovascular disease (CVD). 59 patients with a CVD and moderate stress were randomized to a self-directed web-based stress management program (n = 30) or the same intervention plus lay telephone coaching (n = 29). After 6 weeks, non-responders were re-randomized to continue with their initial intervention or switched to motivational interviewing (MI). Source: Lambert et al. (2022.) <a href='https://doi.org/10.1016/j.pec.2021.10.020' target='_blank'>Adaptive web-based stress management programs among adults with a cardiovascular disease: A pilot Sequential Multiple Assignment Randomized Trial (SMART)</a>. 
</div>


In the precision medicine paradigm, treatment decisions are tailored to individuals rather than relying on a ‘one-size-fits-all’ approach. This approach to treatment is beneficial when treatment effects are heterogeneous. For example, effective management of stress requires the development of personalised approaches, as patients with different characteristics respond to and engage with treatments differently. With the aim of improving individuals’ health outcomes, individualised treatment rules (ITRs) recommend effective treatments based on each person’s specific characteristics. However, collected data often contain many variables that are irrelevant for tailoring treatment. Including all variables in an analysis could reduce statistical efficiency by estimating unnecessary coefficients whose estimates fluctuate around zero for variables that are not useful for tailoring treatment, and yielding an unnecessarily complicated treatment decision rule that is difficult for physicians to interpret or implement. It is therefore important to develop variable selection methods with the objective of optimising individuals’ outcomes by identifying useful tailoring variables. 

We are motivated by a Sequential Multiple Assignment Randomization Trial (SMART) design to optimize the delivery of a web-based, stress management intervention for patients with a cardiovascular disease (CVD). The trial aimed to assess an intervention adapted across time using a stepped-care approach where patients who do not respond to the initial intervention are re-randomized to receive an alternative intervention (Figure 1). A goal of ITR analysis in this setting is to identify the optimal treatment rule that assigns patients to the most effective treatment based on their individual characteristics.

Building on previous work of variable selection for interaction selection {% cite bhatnagar2023sparse %}, my PhD student Zeyu Bian (co-supervised by Dr. Erica Moodie), developed an ITR method using penalized dynamic weighted least squares {% cite bian2023variable bian2023tailoring %}. Our method has the strong heredity property, that is, an interaction term can be included in the model only if the corresponding main terms have also been selected. We show our method has both the double robustness property and the oracle property theoretically. We then extended this framework to count and binary outcome data and applied it to the SMART trial {% cite bian2024variable %}. The primary outcome in this analysis was the stress subscale from the Depression Anxiety Stress Scales (DASS), which is a count outcome measured at 6 weeks after stage 1 randomised allocation. A lower DASS-stress subscale score suggests the presence of fewer symptoms of stress, so the optimal treatment decision minimises the DASS-stress subscale score. We found that five variables were relevant for tailoring treatment: DASS at baseline, sex, marital status, stomach condition, and vision. The estimated treatment rule is

$$
\begin{aligned}
\widehat{a}^{\mathrm{opt}}=\mathbb{I}\{ & -0.78+0.09 \mathbb{I}(\text { male })+0.45 \mathbb{I}(\text { unmarried })+0.01 \mathrm{DASS} \\
& +0.45 \mathbb{I}(\text { stomach }=\text { yes })-0.08 \mathbb{I}(\text { vision }=\text { yes })<0\} .
\end{aligned}
$$

For example, a married woman who does not have either a vision problem or a stomach ailment and who has a DASS greater than 13 would be recommended for website plus weekly telephone coaching.