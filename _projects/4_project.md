---
layout: page
title: Medical image analysis
description: Radiomics and Deep Learning for medical image analysis in Radiology
img: assets/img/spharm.jpg
importance: 5
category: work
related_publications: true
---


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/spharm.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 1. Schematic illustration of the spherical harmonic (SPHARM) decomposition workflow developed for unravelling histopathological phenotypes of endometrial carcinoma on multiparametric magnetic resonance imaging (MRI). Source: {% cite lefebvre2023predicting %}.
</div>


This research theme focuses on developing and applying advanced machine learning techniques to enhance computer-aided diagnosis using medical imaging modalities, particularly MRI and CT. This work aims to improve diagnostic accuracy, facilitate early disease detection, and ultimately contribute to improved patient outcomes. We employ a variety of approaches, including spherical harmonics decomposition {% cite lefebvre2023predicting %}, quantitative 3D radiomics {% cite dana2022malignancy golchi2022sparse %}, and convolutional neural networks (CNNs) {% cite savadjiev2021improved %}, to enhance predictive accuracy and identify clinically relevant imaging biomarkers for diseases such as endometrial carcinoma, chronic obstructive pulmonary disease, and cystic renal lesions.

We demonstrated the effectiveness of a CT-based radiomics model in distinguishing benign from malignant cystic renal lesions, outperforming the conventional Bosniak classification system and offering a more refined approach to patient management {% cite dana2022malignancy %}. Building on this work, we developed a sparse Bayesian hierarchical model for predicting tumor response in head and neck cancer using radiomic features, showcasing the ability to handle missing data and incorporate uncertainty in the prediction process {% cite golchi2022sparse %}.

In another study, we worked on leveraging spherical harmonics (SPHARM) decomposition for quantitative image analysis for endometrial carcinoma. We introduce a novel SPHARM-based pipeline (Figure 1) for predicting deep myometrial invasion and high-grade tumor histology, demonstrating performance comparable or superior to traditional radiomics, thus offering a robust and potentially more generalizable approach to image feature extraction {% cite lefebvre2023predicting %}.

Beyond radiomics and SPHARM, we also explore the application of computer vision techniques in conjunction with deep learning to enhance disease detection. We recently showed that the mean curvature of isophotes (MCI), a standard computer vision algorithm, can improve the detection of chronic obstructive pulmonary disease (COPD) on chest CT scans when used in combination with CNNs or as a standalone feature, highlighting the potential of combining classical and deep learning methods {% cite savadjiev2021improved %}.


More recently, I have been involved in the evaluation of large language models (LLMs) for radiology diagnosis. Recognizing the transformative potential of LLMs in medical imaging, we have been looking into their diagnostic accuracy using challenging, text-based Radiology "Diagnosis Please" cases. These studies compare the performance of different LLMs, such as GPT-3.5, GPT-4, GPT-4o and LLaMA 3-70b, in generating accurate differential diagnoses based on clinical history and imaging findings {% cite li2024comparing li2025comparative %}. Our work has highlighted the unexpected performance drift in these models over time, the need for more robust LLM monitoring, as well as the surprisingly comparable performance of open-source models to their proprietary counterparts. These findings challenge common assumptions about the superiority of proprietary LLMs. Such a paradigm shift could lead to more
accessible and cost-effective generative artificial intelligence applications in radiology, ultimately enhancing patient care.
