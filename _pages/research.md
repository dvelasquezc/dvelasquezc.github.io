---
layout: page
title: "Research"
permalink: "/research/"
order: 3
dropdown_folder: "no"
---

<h2> Work in Progress</h2>

<div>
	{% assign research_sorted = site.research | sort: "order_paper" %}
	{% for paper in research_sorted %}
			
		<div>
		<ul>	
			<li><a href ="{{ paper.url }}"> <h3>{{ paper.title }}</h3></a></li>
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
			
			<div class ="conferences">
			{% if  paper.presented  != 'no' %}
				<i>Presented in: {{ paper.presented }}</i> <br />
			{% endif %}
			<br />
			</div>
		</ul>	
		</div>
			
	{% endfor %}
</div>

<h2> Other Research Efforts </h2>

<div class="text">
   <p> With other <a href="https://github.com/orgs/PeruData/people">prospective PhD students</a>, we are building an <a href="https://github.com/PeruData"> online repository</a> of Peruvian data, which we have named <a href="https://github.com/PeruData"><u><i>PeruData</i></u></a>. Our idea is to reduce the costs of researching about Peru by providing a public good useful for other researchers. We will progressively be uploading more codes and files.</p>
</div>