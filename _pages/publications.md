---
layout: page
permalink: /publications/
title: publications
description: Selected publications in reversed chronological order. 
nav: true
nav_order: 2
---

<p> See my <a href="https://scholar.google.ca/citations?user=9XJum2AAAAAJ&hl=en"><font color="blue">Google Scholar page</font></a> for a complete and up-to-date list.</p>


<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% include bib_search.liquid %}

<div class="publications">

{% bibliography --query @*[selected=true]* %}

</div>
