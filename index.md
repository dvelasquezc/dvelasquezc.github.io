---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: wrapper
title: "Home"
order: 1
dropdown_folder: "no"
---
<article>
<header class="page-header">
	<h2>Welcome to my homepage!</h2>	
</header>

<hr>
  
<div class="img_profile col-xs-12">	
	<div class="profile-text"> 
		<img src="/assets/images/profile4.jpg" alt="Daniel Velásquez Cabrera">
	</div> 
	
	<div class="profile-content">
		<div class="profile-description">
			<p>I am a Ph.D. Candidate in Economics at the University of Michigan, originally from Lima, Peru. I am currently on the 2024-2025 job market. </p>
		</div>
		<div class="profile-description">
			<p> My research interests lie in International Trade, Economic Geography, Urban Economics, and Development Economics.</p>
		</div>		
		<div class="profile-links">
			<p><a href="{{ "/cv/" | prepend: site.baseurl | prepend: site.url }}"><b>CV</b></a>.   <a href="https://scholar.google.com/citations?user=sUhPhVgAAAAJ&hl=en&oi=ao"><b>Google Scholar</b></a></p>.
			<p><b>Contact: danielvc [at] umich [dot] edu</b></p>			
		</div>
	</div>
</div>

</article>




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
				<a href="{{ "/assets/pdfs/JMP_online.pdf" | prepend: site.baseurl | prepend: site.url }}" target="_blank"> [Draft here] </a>
			</div>
			{% endif %}		

			
			
			{% if paper.title == 'Transit Infrastructure, Couples&apos; Commuting Choices, and Gender Earnings Inequality' %}
			<div class = "pdf">
				<a href="{{ "/assets/pdfs/lima_couples_urban.pdf" | prepend: site.baseurl | prepend: site.url }}" target="_blank"> [Draft here] </a>
			</div>
			<div class = "conferences">
				<i>Submitted</i>
			</div>				
			<div class = "conferences">
				<i>&#42; “Honorable Mention” for Best Student Paper Prize, Urban Economic Association, Milan 2023</i>
			</div>			
			{% endif %}
			
			
			{% if paper.title == 'Skill Allocation and Urban Amenities in the Developing World' %}
			<div class = "pdf">
				<a href="{{ "/assets/pdfs/peurban03.pdf" | prepend: site.baseurl | prepend: site.url }}" target="_blank"> [Preliminary draft here] </a>
			</div>
			{% endif %}			
			
			
			{% if paper.title == 'Trade in Appliances, Household Production, and Labor Force Participation (draft coming soon)' %}	
			<div class = "conferences">
				<i>In preparation for the <b><a href="https://www.worldbank.org/en/events/2024/09/12/tradeconf" target="_blank" style="color: black;"> Journal of International Economics special issue on Trade and Uneven Economic Development </a></b> </i>
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