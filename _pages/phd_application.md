---
layout: page
title: "PhD Application"
permalink: "/application/"
order: 4
dropdown_folder: "phdapplication"
---

<div>
	<p> In this section, I have stored most of the documentation and info related to my application. Feel free to check the following links: </p>
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
