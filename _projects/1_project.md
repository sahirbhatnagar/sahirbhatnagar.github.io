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
    Figure 1. Motivating dataset: Children born to mothers with gestational diabetes mellitus (GDM) are more likely to develop obesity or become overweight. Epigenetic factors, such as DNA methylation, are suspected to play a significant role in mediating the effects of GDM on childhood obesity. 
</div>


<!--
In this paper, we consider the prediction of an outcome variable 𝑦 observed on 𝑛 individuals from 𝑝 variables, where 𝑝 is much larger than 𝑛. Many of the high-dimensional (HD) features being collected in genomics ($$\mathbf{X}$$) may be influenced by lifestyle and demographic factors ($$E$$), and their interaction ($$\mathbf{X} \cdot E$$) is expected to play a role in predicting the response ($$Y$$). In HD settings however, power to estimate interactions is low, the number of possible interactions could be enormous, and their effects may be non-linear. Challenges in this  context include not only building a good predictor which will perform well in an independent data set, but also being able to interpret the factors that contribute to the predictions. This latter issue can be very challenging in ultra-HD predictor sets. For example, multiple different sets of covariates may provide equivalent measures of goodness of fit and therefore how does one decide which are important? ? If many variables are highly correlated, interpretation may be improved by acknowledging the existence of an underlying or latent factor generating these patterns. Many of the HD genomic data sets currently being generated capture a possibly dynamic view of how a tissue is functioning, and demonstrate differential patterns of coregulation
or correlation under different conditions. Highlights two key points: (1) environmental exposures can have a widespread effect on
regulatory networks and (2) this effect may be more easily discerned by looking at a measure for gene similarity, relative to
analyzing raw expression data. Therefore, in this paper, we pose the question whether clustering or dimension reduction that incorporates known covariate or exposure information can improve prediction models in HD genomic data settings. Substantial evidence of dysregulation of genomic coregulation has been observed in a variety of contexts, however we are not aware of any work that carefully
examines how this might impact the performance of prediction models. We propose a conceptual analytic strategy called
ECLUST, for prediction of a continuous or binary outcome in HD contexts while exploiting exposure-sensitive data clusters. We restrict our attention to two-step algorithms in order to implement a covariate-driven clustering. Specifically, we hypothesize that within two-step methods, variable grouping that considers exposure information can lead to improved predictive accuracy and interpretability. Our study is motivated by a study of maternal and child heatlh. Events during pregnancy are suspected to play a role in childhood obesity development but little is known about the mechanisms involved. Indeed, children born to women who had gestational diabetes mellitus (GDM) in pregnancy are more likely to be overweight and obese, and evidence suggests epigenetic factors are important piece of the puzzle. Recently, methylation changes in placenta and cord blood were associated with GDM, and here we explore how these changes are associated with obesity in the children at the age of about 5.



In this setting, we propose two complementary approaches for detecting interactions with a key environmental or exposure variable (e.g. smoking, treatment). We first proposed a two-stage procedure called \texttt{eclust} for dimension reduction that performs unsupervised clustering on the HD features using the exposure information only {% cite bhatnagar2018analytic %}. In the second stage, these dimension-reduced variables, constructed without using the response, can then be used in predictive models of any type. 

In a second manuscript, we develop a supervised approach called \texttt{sail} for detecting non-linear interactions between $$\mathbf{X}$$ and $$E$$ on a continuous $$Y$$ {% cite bhatnagar2023sparse %} . Each feature in $$\mathbf{X}$$ is projected onto a set of basis functions to account for non-linear effects on $$Y$$. Our method can accommodate either the strong or weak heredity constraints using a combination of $$\ell_1$$ and $$\ell_2$$ penalties. Furthermore, we prove that \sail ~has the oracle property, i.e., it asymptotically performs as well as if the true model were known in advance. Using this methodology, my PhD student has extended this framework for dynamic treatment regime estimation . 
-->


High-dimensional (HD) genomic data $$(\mathbf{X})$$ often reflect a tissue’s functioning and can be strongly influenced by lifestyle or demographic exposures $$(E)$$, making the interactions $$(\mathbf{X} \cdot E)$$ crucial for predicting outcomes $$(Y)$$. However, the sheer number of potential interactions, their non-linear nature, and the low power to detect them pose major challenges. In precision medicine, where the goal is to tailor interventions to individual risk profiles, it is equally important to build accurate models and to uncover which features—among possibly correlated or latent factors—actually drive predictions. Recent evidence also suggests that environmental exposures can broadly alter regulatory networks and that assessing gene similarity or co-regulation can capture these systemic effects better than simply modeling raw expression data. Yet most existing predictive methods that use HD data and exposures struggle with low power, limited interpretability, and difficulty handling interactions, underscoring the need for more appropriate analytic approaches.

 
To address this gap, we propose ECLUST {% cite bhatnagar2018analytic %}, a conceptual analytic strategy that uses exposure-sensitive data clusters in two-step algorithms for continuous or binary outcome prediction in HD contexts. We hypothesize that incorporating exposure data into variable grouping can improve both predictive accuracy and interpretability. Our approach is motivated by maternal-child health research, where events during pregnancy—such as gestational diabetes mellitus (GDM)—are suspected to influence the risk of childhood obesity. Indeed, children born to women with GDM are more likely to be overweight or obese, and epigenetic factors have emerged as crucial mediators. Methylation changes in placenta and cord blood have been linked to GDM, and here we explore how these changes relate to childhood obesity outcomes at around five years of age. By grouping features that exhibit a systematic response to GDM, ECLUST retains a systems-based perspective and avoids focusing solely on single markers. Through simulations and real data analyses, this approach has demonstrated improved prediction accuracy and interpretability in both linear and non-linear settings, shedding light on how exposures like GDM reshape genomic co-regulation and ultimately influence childhood obesity risk. An <a href="https://cran.r-project.org/package=eclust" target="_blank">R package implementing ECLUST is available on CRAN</a>, making it accessible to a wide range of researchers and practitioners.

Building on this foundation of exposure-centric modeling, we developped a new penalized regression method called SAIL that specifically targets non-linear interactions between a single key exposure and a large set of features under strong or weak heredity constraints {% cite bhatnagar2023sparse %}. This means that an interaction term is included in the model only if the corresponding main effects are also present (strong) or at least one of them is present (weak). Importantly, SAIL is shown to possess the oracle property asymptotically, implying that it can recover the true underlying model as well as if that model were known in advance. From a practical standpoint, SAIL employs a computationally efficient fitting algorithm with automatic selection of tuning parameters, allowing it to scale well to modern HD datasets. Simulation studies demonstrate its superiority over other penalized methods in accurately predicting outcomes and recovering the true set of active (and interacting) variables when interactions are genuinely non-linear. The proposed algorithms are implemented in an <a href="https://github.com/sahirbhatnagar/sail" target="_blank">R package available on GitHub</a>.

A compelling example of SAIL’s utility comes from a study of the Nurse Family Partnership (NFP) program. NFP is a psychosocial intervention program targeting low-income mothers with the goal of improving pregnancy outcomes, children’s health and development, and long-term economic self-sufficiency. Beginning in pregnancy and continuing through infancy, mothers receive regular home visits from nurses who provide guidance on maternal health, parenting, and mother-infant interactions. In a randomized trial, pregnant women were assigned either to the nurse-visited group (intervention) or a control group, and child IQ (using Stanford Binet scores) was measured at four years of age. In this scenario, researchers were interested in how a child’s genetic risk for educational attainment—summarized by a polygenic risk score (PRS)—might interact with participation in NFP to influence IQ at age four. Applying SAIL revealed that children with lower PRS scores (i.e., those genetically predisposed to lower educational attainment) benefited most from the intervention, indicating a clear gene-environment interaction (see Figure 2).


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/sail_nfp.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 2. Estimated interaction effect identified by the weak heredity sail using cubic B-splines and α = 0.1 for the Nurse Family Partnership data. The selected model, chosen via 10-fold cross-validation, contained three variables: the main effects for the intervention and the PRS for educational attainment using genetic variants significant at the 0.0001 level, as well as their interaction.
</div>


A third advancement expands hierarchical gene-environment interaction (GEI) modeling to high-dimensional mixed models. A longstanding challenge in GEI analysis is that population structure and closer relatedness, alongside shared environmental exposures, can create correlations that lead to spurious signals if not properly modeled. Recognizing that ignoring these dependencies can inflate false positive rates under polygenic models, my PhD student, Julien, developed a penalized quasi-likelihood approach for hierarchical variable selection within generalized linear mixed models (GLMMs) called pglmm {% cite st2023hierarchical %}. By incorporating random effects to account for both genetic and environmental correlations, pglmm reduces false discoveries for main and interaction effects and achieves higher F1 scores than existing methods in simulation studies. The method is implemented in an <a href='https://github.com/julstpierre/PenalizedGLMM' target='_blank'>open source Julia package</a>.

A motivating application of pglmm centers on the Orofacial Pain: Prospective Evaluation and Risk Assessment (OPPERA) study, which previously reported significant associations between temporomandibular disorder (TMD)—a painful jaw condition disproportionately affecting females—and four distinct genetic loci. Because TMD may involve sex-specific pathophysiological mechanisms, pglmm was used to identify important sex-specific predictors in the OPPERA discovery cohort and then evaluate the model’s predictive performance in two replication cohorts: OPPERA II Chronic TMD Replication and Complex Persistent Pain Conditions (CPPC). pglmm successfully retrieved the previously implicated loci, highlighting its ability to detect biologically relevant interactions and confirm risk predictions in independent samples. These results underscore the importance of accounting for correlated structures in GEI analyses and demonstrate how hierarchical selection in a mixed-model framework can improve both discovery and replication in complex trait genetics.















