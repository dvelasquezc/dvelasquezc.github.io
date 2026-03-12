---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: wrapper
title: "Home"
order: 1
dropdown_folder: "no"
---
<article>
<header class="page-header-online">
	<hr>
	<h2>Daniel Velasquez-Cabrera</h2>
</header> 

<hr>

  
<div class="img_profile col-xs-12">
	<div class="profile-left">
		<div class="profile-text">
			<img src="/assets/images/profile4.jpg" alt="Daniel Velasquez-Cabrera">
		</div>
		<div class="profile-logos">
			<img src="/assets/images/cmc-logo.png" alt="Claremont McKenna College">
			<img src="/assets/images/umich-logo.png" alt="University of Michigan">
		</div>
	</div>

	<div class="profile-content">
		<div class="profile-name">Daniel Velasquez-Cabrera</div>
		<div class="profile-title">Assistant Professor of Economics</div>
		<div class="profile-institution">Robert Day School of Economics · Claremont McKenna College</div>
		<div class="profile-education">Ph.D., University of Michigan</div>
		<div class="profile-links">
			<a href="mailto:dvelasquez@cmc.edu">dvelasquez@cmc.edu</a> ·
			<a href="{{ "/cv/" | prepend: site.baseurl | prepend: site.url }}"><b>CV</b></a> ·
			<a href="https://scholar.google.com/citations?user=sUhPhVgAAAAJ&hl=en&oi=ao" target="_blank"><b>Google Scholar</b></a>
		</div>
		<div class="profile-bio">
			<p>I study economic development using historical evidence from developed economies and contemporary data from developing countries. My work focuses, though not exclusively, on geographic and coordination frictions, including how transport and market access shape outcomes.</p>
		</div>
	</div>
</div>

</article>


<hr>

<h2> Working papers </h2>

<div>
	{% assign research_sorted = site.research | sort: "order_paper" %}
	<ol style="list-style-type: decimal;" start="1">		
		{% for paper in research_sorted %}
			{% if paper.pubstatus == "mimeo" %}
					<li><b><a href ="{{ paper.url }}">{{ paper.title }}</a></b>
						{% if paper.coauthors %}
							<span class="conferences"><i> (with
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
							</i></span>
						{% endif %}
						
						
						{% if paper.pdf != 'no' %}
						<div class = "pdf">
							<u>{{ paper.pdf }}</u>
						</div>
						{% endif %}
							
						
						{% if paper.title == '(Job Market Paper) Highways, Commuting and Trade:  Unpacking Suburban Growth' %}
						<div class = "pdf">
							<a href="{{ "/assets/pdfs/JMP_online.pdf" | prepend: site.baseurl | prepend: site.url }}" target="_blank"> [Draft here] </a>
						</div>
						<div class = "award">
							<i>🏆 Best Paper by a Junior Researcher, The International Transportation Economics Association, Evanston 2025</i>
						</div>							
						{% endif %}		

						
						
						{% if paper.title == 'Transit Infrastructure, Couples&apos; Commuting Choices, and Gender Earnings Inequality' %}
						<div class = "pdf">
							<a href="{{ "/assets/pdfs/lima_couples_urban.pdf" | prepend: site.baseurl | prepend: site.url }}" target="_blank"> [Draft here] </a>
						</div>
						<div class = "conferences">
							<i>Submitted</i>
						</div>				
						<div class = "award">
							<i>🏆 Honorable Mention, Best Student Paper Prize, Urban Economic Association, Milan 2023</i>
						</div>			
						{% endif %}
						
						
						{% if paper.title == 'Skill Allocation and Urban Amenities in the Developing World' %}
						<div class = "pdf">
							<a href="{{ "/assets/pdfs/peurban03.pdf" | prepend: site.baseurl | prepend: site.url }}" target="_blank"> [Preliminary draft here] </a>
						</div>
						{% endif %}			
						
						
						
						
						{% if paper.title == 'Initial Conditions and the Big Push' %}
						<div class = "pdf">
							<a href="{{ "/assets/pdfs/bigpush_wwii.pdf" | prepend: site.baseurl | prepend: site.url }}" target="_blank"> [Draft here] </a> <a href="{{ "https://papers.ssrn.com/sol3/papers.cfm?abstract_id=5408984" }}" target="_blank"> [SSRN] </a>
						</div>
						<div class = "conferences">
							<i>Submitted</i>
						</div>
						{% endif %}

						{% if paper.title == 'Spatial Dutch Disease and the Financial Propagation of Commodity Booms' %}
						<div class = "conferences">
							<i>Working paper coming soon</i>
						</div>
						{% endif %}

						{% if  paper.funding  != 'no' %}
						<div class ="conferences">
							<i>&#42; Project financed by grant from {{ paper.funding }}</i>
						</div>
						{% endif %}
						
						{% if  paper.presented  != 'no' %}
						<div class ="conferences">
							<!-- <i>&#42; Presented in: {{ paper.presented }}</i> -->
						</div>
						{% endif %}		
					</li>				
							
			{% endif %}	
		{% endfor %}
	</ol>				
</div>





<h2> Published and accepted papers </h2>
<div>
	{% assign research_sorted = site.research | sort: "order_paper" %}
	<ol style="list-style-type: decimal;">		
	{% for paper in research_sorted %}
	{% if paper.pubstatus == "Published" %}
			
			<li><b><a href ="{{ paper.url }}">{{ paper.title }}</a></b>
				{% if paper.coauthors %}
					<span class="conferences"><i>With
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
					</i></span>
				{% endif %}

				{% if paper.journal_name %}
				<div class = "conferences">
					<b>{{ paper.journal_name }}</b>, {{ paper.journal_year }}. &nbsp; {% if paper.link != 'no' %}<a href="{{ paper.link }}" target="_blank">[Published version]</a>{% endif %}{% if paper.draft_link and paper.draft_link != 'no' %} &nbsp;|&nbsp; <a href="{{ paper.draft_link | prepend: site.baseurl | prepend: site.url }}" target="_blank">[Working paper]</a>{% endif %}{% if paper.ssrn and paper.ssrn != 'no' %} &nbsp;|&nbsp; <a href="{{ paper.ssrn }}" target="_blank">[SSRN]</a>{% endif %}
				</div>
				{% endif %}

				{% if paper.title == 'Trade in Appliances, Household Production, and Labor Force Participation' %}
				<div class ="conferences">
					<i>Accepted at the <b>Journal of International Economics</b></i> &nbsp; <a href="{{ "/assets/pdfs/MSV_THL_jan25.pdf" | prepend: site.baseurl | prepend: site.url }}" target="_blank">[Working paper]</a>
				</div>
				{% endif %}
			</li>				
					
	{% endif %}	
	{% endfor %}
	</ol>			
		
</div>

	