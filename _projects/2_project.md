---
layout: page
title: Polygenic risk scores
description: Polygenic risk scores for complex diseases with applications in screening, risk stratification, and identification of rare variants
img: assets/img/prs_circgen.jpg
importance: 2
category: work
related_publications: true
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/collider1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/collider2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1. Illustration of how we used collider bias and a polygenic risk score for low-density lipoprotein cholesterol (LDL-C) to identify individuals who have rare but penetrant alleles leading to familial hypercholesterolemia (FH). Left: In the general population, there is no association between the PRS for LDL-C and the predicted probability of carrying an FH variant. Right: Selecting individuals with severe hypercholesterolemia, i.e., conditioning on a collider variable, induces a spurious negative association between the PRS and the predicted probability of carrying an FH variant (red points and regression line). We can then infer from this relationship that individuals with severe hypercholesterolemia but a low PRS for LDL-C are more likely to carry FH variants. Indeed, among individuals with severe hypercholesterolemia, those with a low PRS (2 SD below the mean) had a 21-fold higher probability of carrying an FH variant compared to those with a high PRS (2 SD above the mean) {% cite wu2021polygenic %}. It is important to note that the strength of this association depends on the strengths of the causal relationships between the genetic causes and the common outcome (severe hypercholesterolemia).
</div>


We have been developing new polygenic risk score (PRS) methods for complex diseases to improve screening, risk stratification, and the identification of individuals with rare variant carriers. In a study led by my Master’s student, Haoyu Wu (co-supervised by Dr. Brent Richards), we investigated the clinical potential of a low-density lipoprotein cholesterol (LDL-C) PRS to identify carriers of Familial Hypercholesterolemia (FH)—a disorder that often warrants costly therapies, such as PCSK9 inhibitors, to prevent cardiovascular outcomes {% cite wu2021polygenic %}. Because routine genetic testing for FH among hypercholesterolemia patients remains expensive and administratively challenging, we used a relatively inexpensive genome-wide genotyping strategy to derive an LDL-C PRS. Our approach explained 21% of the variance in LDL-C levels in White British individuals from the UK Biobank. Notably, among patients with severe hypercholesterolemia, those with a low LDL-C PRS were 21 times more likely to harbor an FH variant compared to those with a high PRS—a difference attributable in part to collider bias (Figure 1). In this context, collider bias arises because we conditioned on the common outcome of severe hypercholesterolemia, which can result from either a rare FH pathogenic variant or a polygenic predisposition captured by the PRS. Consequently, once we focused on individuals who developed severe hypercholesterolemia, those with a low polygenic risk stood out as more likely to carry the monogenic cause. By leveraging this negative correlation between PRS and FH variants in the presence of severe hypercholesterolemia, PRS-based triaging emerges as a viable, cost-effective strategy for enhancing FH detection and prioritizing genetic testing.


We also investigated the use of PRSs as a negative screening tool. For example, we developed a PRS for quantitative ultrasound speed of sound (SOS) to improve screening for fracture risk {% cite forgetta2020development lu2020improved %}. Osteoporosis is a common disease characterized by low bone mineral density and increased fracture risk.  Screening for osteoporosis is typically done using the Fracture Risk Assessment Tool (FRAX), which calculates a 10-year probability of major osteoporotic fracture.  However, current screening guidelines identify only a small proportion of the population as eligible for intervention, meaning that much of the screening expenditure is spent on individuals who will not qualify for intervention. In our study, we developed a PRS for SOS, a heritable risk factor for osteoporotic fracture.  We found that this PRS could identify individuals at low risk of osteoporosis who could safely be excluded from further screening. This approach could potentially reduce the number of individuals needing to be screened, while maintaining a high sensitivity and specificity to identify individuals who should be recommended an intervention. 


My work on polygenic risk scores (PRS) has also focused on overcoming key methodological hurdles in high-dimensional genetic prediction, including population structure, relatedness, and binary outcomes. First, we developped ggmix, which provides a single-step penalized linear mixed model that adjusts for both population structure and correlated SNPs in continuous traits; its efficient blockwise coordinate descent algorithm is freely available in an open-source[R package](https://sahirbhatnagar.com/ggmix/) {% cite bhatnagar2020simultaneous %}. Building on this framework, my PhD student Julien St-Pierre (co-supervised with Dr. Karim Oualkacha) led the development of pglmm, which extends penalized mixed-model methods to generalized linear mixed models for binary traits {% cite st2023efficient %}. By accounting for between-individual correlations via random effects, pglmm selects predictive markers more accurately than principal-component–adjusted methods in case-control studies; a [Julia implementation supports large-scale analyses](https://github.com/julstpierre/PenalizedGLMM). Additionally, Julien also spearheaded a study on diverse SNP selection strategies for PRS, emphasizing how selection criteria affect predictive performance—especially when disease risk varies across populations {% cite pierre2022considering %}. Together, these advances strengthen the foundation for PRS research, as they address multiple sources of bias, improve power, and offer computationally efficient open-source solutions for practitioners in both research and clinical settings.



