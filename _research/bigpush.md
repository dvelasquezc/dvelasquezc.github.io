---
title: "Initial Conditions and the Big Push"
coauthors: Dominick Bartelme, Zhimin Li
pubstatus: "mimeo"
journal: "no"
link: "no"
presented: "17th North American Meeting of the Urban Economics Association, HKU Firm and Industrial Dynamics Workshop 2024, Pacific Conference for Development Economics 2025"
pdf: "no"
abstract: 'This paper examines how initial conditions shape the long-run impact of large temporary shocks on economic geography. Using WWII supply contracts in the United States, we show that temporary spending had persistent effects on population and manufacturing employment only in counties with low initial manufacturing development. Motivated by these findings, we develop a multisector economic geography model that features external economies of scale in manufacturing with non-constant elasticity. We calibrate the model and show that we match the empirical estimates with an S-shaped scale function for which scale economies large enough to cause coordination failures are limited to locations with low initial manufacturing employment. We use the calibrated model to re-evaluate how temporary WWII spending shaped the evolution of U.S. postwar economic geography. Despite the presence of big push dynamics and multiple steady states, the aggregate effects of WWII spending on long-term outcomes are limited due to the restricted domain over which coordination failures operate.'
funding: "no"
order_paper: 4
layout: page
---

<a href="{{ "/assets/pdfs/bigpush_wwii.pdf" | prepend: site.baseurl | prepend: site.url }}" target="_blank"> [Draft here] </a>

<a href="{{ "https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5408984" }}" target="_blank"> [SSRN] </a>


<p><b>Co-author(s)</b>: {{ page.coauthors }} </p>

{% if page.presented != 'no' %}
<p><b>Presented in</b>: {{ page.presented }} </p>
{% endif %}

<div class ="text"><p><b>Abstract</b>: {{ page.abstract }} </p></div>

{% if page.funding != 'no' %}
<p><b>Funding</b>: {{ page.funding }} </p>
{% endif %}

{% if page.awards %}
<p><b>Awards</b>: {{ page.awards }} </p>
{% endif %}
