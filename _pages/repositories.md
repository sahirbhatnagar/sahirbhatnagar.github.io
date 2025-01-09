---
layout: page
permalink: /software/
title: software
nav: true
nav_order: 4
---

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Software</title>
  <style>
    .software-entry {
      margin-bottom: 30px;
      padding: 15px;
      border: 1px solid #ddd;
      border-radius: 8px;
      background-color: #f9f9f9;
    }

    .software-entry h3 {
      margin-top: 0;
    }

    .software-entry p {
      margin: 10px 0;
      font-size: 14px;
    }

    .software-entry .badges {
      display: flex;
      flex-wrap: wrap; /* Ensures badges wrap if they don't fit in one row */
      gap: 10px; /* Adds space between badges */
    }

    .software-entry .badges a {
      text-decoration: none; /* Removes underline from links */
    }

    .software-entry .badges img {
      vertical-align: middle;
      height: 20px; /* Uniform height for all badges */
    }
  </style>
</head>


<body>
  <div class="software-entry">
    <h3><a href="http://sahirbhatnagar.com/casebase/" target="_blank">casebase</a></h3>
    <p>
      <a href="https://journal.r-project.org/articles/RJ-2022-052/" target="_blank">
        Journal Article: casebase: An Alternative Framework for Survival Analysis and Comparison of Event Rates
      </a>
    </p>
    <p>
    A method for fitting fully parametric hazard models and covariate-conditional survival curves using the familiar interface of the glm function. Our implementation includes extensions to other models such as penalized regression for variable selection and competing risk analysis. In addition, we provide functions for exploratory data analysis and visualizing the estimated quantities such as the hazard function, survival curve, and their standard errors. The ultimate goal of our package is to make fitting flexible hazards accessible to end users who favor reporting absolute risks and survival curves over hazard ratios.
    </p>
    <div class="badges">
      <a href="https://app.codecov.io/github/sahirbhatnagar/casebase?branch=master" target="_blank">
        <img src="https://img.shields.io/codecov/c/github/sahirbhatnagar/casebase/master.svg" alt="Coverage Status">
      </a>
      <a href="https://cran.r-project.org/package=casebase" target="_blank">
        <img src="https://www.r-pkg.org/badges/version/casebase?color=blue" alt="CRAN Version">
      </a>
      <a href="https://www.r-pkg.org/pkg/casebase" target="_blank">
        <img src="https://cranlogs.r-pkg.org/badges/grand-total/casebase?color=blue" alt="Total Downloads">
      </a>
      <a href="https://lifecycle.r-lib.org/articles/stages.html" target="_blank">
        <img src="https://img.shields.io/badge/lifecycle-maturing-blue.svg" alt="Lifecycle: Maturing">
      </a>
      <a href="https://github.com/sahirbhatnagar/casebase/actions" target="_blank">
        <img src="https://github.com/sahirbhatnagar/casebase/workflows/R-CMD-check/badge.svg" alt="R-CMD-check">
      </a>
      <a href="https://app.codecov.io/gh/sahirbhatnagar/casebase?branch=master" target="_blank">
        <img src="https://codecov.io/gh/sahirbhatnagar/casebase/branch/master/graph/badge.svg" alt="Codecov Test Coverage">
      </a>
    </div>
  </div>
  <br>
  <div class="software-entry">
  <h3><a href="http://sahirbhatnagar.com/ggmix/" target="_blank">ggmix</a></h3>
  <p>
    <a href="https://doi.org/10.1371/journal.pgen.1008766" target="_blank">
      Journal Article: Simultaneous SNP selection and adjustment for population structure in high dimensional prediction models
    </a>
  </p>
  <p>
    A General Framework for Variable Selection in Linear Mixed Models with Applications to Genetic Studies with Structured Populations. 
    This is a penalized regression method that selects and estimates predictors in a single random effects model.
  </p>
  <div class="badges">
    <a href="https://codecov.io/github/sahirbhatnagar/ggmix?branch=master" target="_blank">
      <img src="https://codecov.io/gh/sahirbhatnagar/ggmix/branch/master/graph/badge.svg" alt="Coverage Status">
    </a>
    <a href="https://cran.r-project.org/package=ggmix" target="_blank">
      <img src="http://www.r-pkg.org/badges/version/ggmix" alt="CRAN Version">
    </a>
    <a href="https://cran.r-project.org/package=ggmix" target="_blank">
      <img src="http://cranlogs.r-pkg.org/badges/grand-total/ggmix?color=blue" alt="Total Downloads">
    </a>
  </div>
</div>
<br>
<div class="software-entry">
  <h3><a href="http://sahirbhatnagar.com/sail/" target="_blank">sail</a></h3>
  <p>
    <a href="https://doi.org/10.1016/j.csda.2022.107624" target="_blank">
      Journal Article: A sparse additive model for high-dimensional interactions with an exposure variable
    </a>
  </p>
  <p>
    Sparse additive interaction learning. This software package implements the <code>sail</code> method described in the accompanying paper. This is a penalized regression method that selects and estimates both linear and non-linear interactions with a single exposure variable.
  </p>
  <div class="badges">
    <a href="https://codecov.io/github/sahirbhatnagar/sail?branch=master" target="_blank">
      <img src="https://codecov.io/gh/sahirbhatnagar/sail/branch/master/graph/badge.svg" alt="Coverage Status">
    </a>
    <a href="https://cran.r-project.org/package=sail" target="_blank">
      <img src="http://www.r-pkg.org/badges/version/sail" alt="CRAN Version">
    </a>
    <a href="https://cran.r-project.org/package=sail" target="_blank">
      <img src="http://cranlogs.r-pkg.org/badges/grand-total/sail?color=blue" alt="Total Downloads">
    </a>
  </div>
</div>
<br>
<div class="software-entry">
  <h3><a href="http://sahirbhatnagar.com/eclust/" target="_blank">eclust</a></h3>
  <p>
    <a href="https://doi.org/10.1002/gepi.22112" target="_blank">
      Journal Article: An analytic approach for interpretable predictive models in high-dimensional data in the presence of interactions with exposures
    </a>
  </p>
  <p>
    A Statistical Software Tool for the Analysis of High-Dimensional Interactions. This software is written in the open source software environment R. Its main functionality is to cluster a high-dimensional dataset (e.g., genomics, brain imaging) by leveraging the environmental exposures.
  </p>
  <div class="badges">
    <a href="https://cran.r-project.org/package=eclust" target="_blank">
      <img src="http://www.r-pkg.org/badges/version/eclust" alt="CRAN Version">
    </a>
    <a href="https://cran.r-project.org/package=eclust" target="_blank">
      <img src="http://cranlogs.r-pkg.org/badges/grand-total/eclust?color=blue" alt="Total Downloads">
    </a>
  </div>
</div>
<br>
<div class="software-entry">
  <h3><a href="https://cran.r-project.org/web/packages/manhattanly/" target="_blank">manhattanly</a></h3>
  <p>
    <a href="https://www.youtube.com/watch?v=sawf9fnbsOA" target="_blank">
      Watch the Plotcon talk in New York City about manhattanly
    </a>
  </p>
  <p>
    Create interactive Q-Q, manhattan, and volcano plots that are usable from the R console, in the 'RStudio' viewer pane, in 'R Markdown' documents, and in 'Shiny' apps. Hover the mouse pointer over a point to show details or drag a rectangle to zoom.
  </p>
  <div class="badges">
    <a href="https://cran.r-project.org/package=manhattanly" target="_blank">
      <img src="http://www.r-pkg.org/badges/version/manhattanly" alt="CRAN Version">
    </a>
    <a href="https://cran.r-project.org/package=manhattanly" target="_blank">
      <img src="http://cranlogs.r-pkg.org/badges/grand-total/manhattanly?color=blue" alt="Total Downloads">
    </a>
  </div>
</div>
<br>
<div class="software-entry">
  <h3><a href="https://cran.r-project.org/package=gglasso" target="_blank">gglasso</a></h3>
  <p>
    A unified algorithm, blockwise-majorization-descent (BMD), for efficiently computing the solution paths of the group-lasso penalized least squares, logistic regression, Huberized SVM, and squared SVM.
  </p>
  <div class="badges">
    <a href="https://codecov.io/github/emeryyi/gglasso?branch=master" target="_blank">
      <img src="https://codecov.io/gh/emeryyi/gglasso/branch/master/graph/badge.svg" alt="Coverage status">
    </a>
    <a href="https://cran.r-project.org/package=gglasso" target="_blank">
      <img src="http://www.r-pkg.org/badges/version/gglasso" alt="CRAN Version">
    </a>
    <a href="https://cran.r-project.org/package=gglasso" target="_blank">
      <img src="http://cranlogs.r-pkg.org/badges/grand-total/gglasso?color=blue" alt="Total Downloads">
    </a>
  </div>
</div>
</body>



<br>

## GitHub Repositories

{% if site.data.repositories.github_repos %}

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% endif %}


<br>

## GitHub stats

{% if site.data.repositories.github_users %}

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.liquid username=user %}
  {% endfor %}
</div>

---

{% if site.repo_trophies.enabled %}
{% for user in site.data.repositories.github_users %}
{% if site.data.repositories.github_users.size > 1 %}

  <h4>{{ user }}</h4>
  {% endif %}
  <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% include repository/repo_trophies.liquid username=user %}
  </div>

---

{% endfor %}
{% endif %}
{% endif %}

<!--
### Shiny Apps

* [cdiff](https://sahir.shinyapps.io/cdiff/)    
Interactive, online web application to guide preoperative decision making for patients with fulminant Clostridium difficile colitis (FCDC) being evaluated for surgery. This calculator predicts 30-day postoperative mortality for patients with FCDC based on easily attainable pre-operative parameters.   

* [Supplementary results for our paper "Assessing transmission ratio distortion in extended families: a comparison of analysis methods"](https://sahir.shinyapps.io/TRDtest/)  
-->