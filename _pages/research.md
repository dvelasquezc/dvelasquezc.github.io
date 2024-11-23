---
layout: page
title: "Research"
permalink: "/research/"
order: 2
dropdown_folder: "no"
show: "yes"
#corregir linea 62-64 donde puse manualmente el link al paper de trade violence
---



<h2> Working papers </h2>

<div>
	{% assign research_sorted = site.research | sort: "order_paper" %}
	{% for paper in research_sorted %}
	{% if paper.pubstatus == "mimeo" %}
			
		<div>
		<ul>	
			<li ><a href ="{{ paper.url }}" style= "font-weight: bold;">{{ paper.title }}</a>
			{% if paper.coauthors %}
				<i> (with
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
				{% endfor %})
				</i>
			{% endif %}</li>
			
			
			{% if paper.pdf != 'no' %}
			<div class = "pdf">
				<u>{{ paper.pdf }}</u>
			</div>
			{% endif %}
			
			{% if paper.title == '(Job Market Paper) Highways, Commuting and Trade:  Unpacking Suburban Growth' %}
			<div class = "pdf">
				<u><a href="{{ "/assets/pdfs/JMP_online.pdf" | prepend: site.baseurl | prepend: site.url }}" target="_blank" style="color:#ff0000;"> <b>[Draft here]</b> </a></u>
			</div>
			{% endif %}					
				
			
			{% if paper.title == 'Transit Infrastructure, Couples&apos; Commuting Choices, and Gender Earnings Inequality' %}
			<div class = "pdf">
				<u><a href="{{ "/assets/pdfs/lima_couples_urban.pdf" | prepend: site.baseurl | prepend: site.url }}" target="_blank" style="color:#ff0000;"> <b>[Draft here]</b> </a></u>
			</div>
			<div class = "conferences">
				<i>Submitted</i>
			</div>				
			<div class = "conferences">
				<i>&#42;“Honorable Mention” for Best Student Paper Prize, Urban Economic Association, Milan 2023</i>
			</div>			
			{% endif %}
			
			
			{% if paper.title == 'Skill Allocation and Urban Amenities in the Developing World' %}
			<div class = "pdf">
				<u><a href="{{ "/assets/pdfs/peurban03.pdf" | prepend: site.baseurl | prepend: site.url }}" target="_blank" style="color:#ff0000;"> <b>[Preliminary draft here - do not cite]</b> </a></u>
			</div>
			{% endif %}			
			
			
			{% if paper.title == 'Trade in Appliances, Household Production, and Labor Force Participation (draft coming soon)' %}	
			<div class = "conferences">
				<i>In preparation for the Journal of International Economics special issue on Trade and Uneven Economic Development</i>
			</div>			
			{% endif %}			
			
			
			{% if  paper.funding  != 'no' %}
			<div class ="conferences">
				<i>&#42; Project financed by grant from {{ paper.funding }}</i>
			</div>
			{% endif %}
			
			{% if  paper.presented  != 'no' %}
			<div class ="conferences">
				<i>&#42; Presented in: {{ paper.presented }}</i>
			</div>
			{% endif %}						
					
		</ul>	
		</div>
	{% endif %}	
	{% endfor %}
</div>





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
				
			{% if paper.link != 'no' %}
			<div class = "pdf">
				<u><a href="{{ paper.link }}" target="_blank"> [{{ paper.journal }}] </a></u>
			</div>
			{% endif %}
					
			
			{% if  paper.funding  != 'no' %}
			<div class ="conferences">
				<i>Project financed by grant from {{ paper.funding }}</i>
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

