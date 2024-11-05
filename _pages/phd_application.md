---
layout: page
title: "PhD Application"
permalink: "/application/"
order: 4
dropdown_folder: "phdapplication"
show: "no"
---

<div>
	<p> In this section, I have stored most of the documentation and info related to my application. I am keeping online my application material to help Peruvian students applying to a Ph.D. in Economics. If anyone is need of guidance, feel free to write me an e-mail or to contact me via twitter. </p>
</div>
<div>
	{% assign sorted_pages2 = site.phdapplication | sort:"order" %}
	<ol>
	{% for pp2 in sorted_pages2 %}
		{% if pp2.hide != 1 %}
		<div class="phdapplication_box">
			<li><a href="{{ pp2.url | prepend: site.baseurl | prepend: site.url }}"> <h3>{{ pp2.title }}</h3> </a></li>
		</div>
		{% endif %}
	{% endfor %}
	</ol>
</div>
