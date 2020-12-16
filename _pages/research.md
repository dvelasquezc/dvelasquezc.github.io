---
layout: page
title: "Research"
permalink: "/research/"
order: 2
dropdown_folder: "no"
#corregir linea 62-64 donde puse manualmente el link al paper de trade violence
---

<h2> Published and accepted papers </h2>
<div>
	{% assign research_sorted = site.research | sort: "order_paper" %}
	{% for paper in research_sorted %}
	{% if paper.pubstatus == "Published" %}
			
		<div>
		<ul>	
			<li style= "font-weight: bold;"><a href ="{{ paper.url }}">{{ paper.title }}</a></li>
			{% if paper.coauthors %}
				<i>With
				{% assign coauthors = paper.coauthors | join: ',' | strip | split: ', ' %}
				{% assign last = coauthors | last %}
				{% assign first = coauthors | first %}
				{% for author in coauthors %}
					{% assign authordata = site.data.authors[author] %}
					{% if author == last and author == first %}
						{% if authordata.webpage  != "no" %}
							<a href="{{ authordata.webpage }}">{{ author }}</a>
						{% else %}
							{{ author }}
						{% endif %}
					{% elsif author == last and author != first %}
						{% if authordata.webpage != "no" %}
							and
							<a href="{{ authordata.webpage }}">{{ author }}</a>
						{% else %}
							and
							{{ author }}
						{% endif %}
					{% elsif author != last and author == first %}
						{% if authordata.webpage  != "no" %}
							<a href="{{ authordata.webpage }}">{{ author }}</a>,
						{% else %}
							{{ author | append:',' }}
						{% endif %}
					{%	elsif author != last and author != first %}
						{% if authordata.webpage  != "no" %}
							<a href="{{ authordata.webpage }}">{{ author }}</a>,
						{% else %}
							{{ author | append:',' }}
						{% endif %}
					{% endif %}
				{% endfor %}
				</i>
			{% endif %}
			
			<div class = "pdf">
				<u><a href="{{ paper.link }}" target="_blank"> [{{ paper.journal }}] </a></u>
			</div>
			
			{% if  paper.presented  != 'no' %}
			<div class ="conferences">
				<i>Presented in: {{ paper.presented }}</i>
			</div>
			{% endif %}						
					
		</ul>	
		</div>
	{% endif %}	
	{% endfor %}
</div>




<h2> Work in progress </h2>

<div>
	{% assign research_sorted = site.research | sort: "order_paper" %}
	{% for paper in research_sorted %}
	{% if paper.pubstatus == "mimeo" %}
			
		<div>
		<ul>	
			<li style= "font-weight: bold;"><a href ="{{ paper.url }}">{{ paper.title }}</a></li>
			{% if paper.coauthors %}
				<i>With
				{% assign coauthors = paper.coauthors | join: ',' | strip | split: ', ' %}
				{% assign last = coauthors | last %}
				{% assign first = coauthors | first %}
				{% for author in coauthors %}
					{% assign authordata = site.data.authors[author] %}
					{% if author == last and author == first %}
						{% if authordata.webpage  != "no" %}
							<a href="{{ authordata.webpage }}">{{ author }}</a>
						{% else %}
							{{ author }}
						{% endif %}
					{% elsif author == last and author != first %}
						{% if authordata.webpage != "no" %}
							and
							<a href="{{ authordata.webpage }}">{{ author }}</a>
						{% else %}
							and
							{{ author }}
						{% endif %}
					{% elsif author != last and author == first %}
						{% if authordata.webpage  != "no" %}
							<a href="{{ authordata.webpage }}">{{ author }}</a>,
						{% else %}
							{{ author | append:',' }}
						{% endif %}
					{%	elsif author != last and author != first %}
						{% if authordata.webpage  != "no" %}
							<a href="{{ authordata.webpage }}">{{ author }}</a>,
						{% else %}
							{{ author | append:',' }}
						{% endif %}
					{% endif %}
				{% endfor %}
				</i>
			{% endif %}
			
			
			{% if paper.pdf != 'no' %}
			<div class = "pdf">
				<u>{{ paper.pdf }}</u>
			</div>
			{% endif %}
			{% if paper.title == 'Does Trade Liberalization Foster Intimate Partner Violence?' %}
			<div class = "pdf">
				<u><a href="{{ "/assets/pdfs/trade_violence.pdf" | prepend: site.baseurl | prepend: site.url }}" target="_blank"> [Submitted - Latest version here] </a></u>
			</div>
			{% endif %}

			{% if paper.title == 'Computers, Discretion and Discrimination: Evidence from Two Natural Field Experiments' %}
			<div class = "pdf">
				<u><a href="{{ "/assets/pdfs/digital_police.pdf" | prepend: site.baseurl | prepend: site.url }}" target="_blank"> [R&R in Economic Development and Cultural Change - Latest version here] </a></u>
			</div>
			{% endif %}
				
			{% if paper.title == 'Spillovers and Long Run Effects of Messages on Tax Compliance: Experimental Evidence from Peru' %}
			<div class = "pdf">
				<u><a href="{{ paper.link }}" target="_blank"> [Submitted - Latest version here] </a></u>
			</div>
			{% endif %}
			
			
			{% if  paper.presented  != 'no' %}
			<div class ="conferences">
				<i>Presented in: {{ paper.presented }}</i>
			</div>
			{% endif %}						
					
		</ul>	
		</div>
	{% endif %}	
	{% endfor %}
</div>

<h2> Broader Audience Writing </h2>
<ul>
<li style="font-weight: bold;"><a href ="https://jorgedelaroca.name/r_covidperu.pdf"> Incidencia de COVID-19 en las áreas urbanas del Perú </a></li>
	<i> With <a href ="https://jorgedelaroca.name/index.html"> Jorge de la Roca</a></i> 
</ul>


<h2> Other Research Efforts </h2>
<div class="text">
   <p> With other <a href="https://github.com/orgs/PeruData/people">prospective PhD students</a>, we are building an <a href="https://github.com/PeruData"> online repository</a> of Peruvian data, which we have named <a href="https://github.com/PeruData"><u><i>PeruData</i></u></a>. Our objective is to provide a public good, useful for other researchers aiming to study about Peru. We will progressively be uploading more codes and files.</p>
</div>