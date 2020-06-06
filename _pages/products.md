---
layout: archive
title: Products
permalink: /products/
catgory: products
---

<!-- Display posts in the logger category -->
<h1>Loggers</h1>
<hr>

<ul>
  	{% for post in site.categories.loggers %}
 	<li><h4><a href="{{ post.url }}">{{ post.title }}</a></h4></li>
 	<img src="{{ site.baseurl }}/images/{{ post.image.teaser }}" style="width:150px;height:150px;" />
	{% endfor %}
</ul>

<!-- display posts in the sensor category -->
<h1>Sensors</h1>
<hr>

<ul>
  	{% for post in site.categories.sensors %}
 	<li><h4><a href="{{ post.url }}">{{ post.title }}</a></h4></li>
 	<img src="{{ site.baseurl }}/images/{{ post.image.teaser }}" style="width:150px;height:150px;" />
	{% endfor %}
</ul>

<!-- display posts in the software category -->
<h1>Software</h1>
<hr>

<ul>
  	{% for post in site.categories.software %}
 	<li><h4><a href="{{ post.url }}">{{ post.title }}</a></h4></li>
 	<!-- <img src="{{ site.baseurl }}/images/{{ post.image.teaser }}" style="width:150px;height:150px;" /> -->
	{% endfor %}
</ul>
<!-- display posts in the other category -->
<h1>Others</h1>
<hr>

<ul>
  	{% for post in site.categories.other %}
 	<li><h4><a href="{{ post.url }}">{{ post.title }}</a></h4></li>
 	<img src="{{ site.baseurl }}/images/{{ post.image.teaser }}" style="width:150px;height:150px;" />
	{% endfor %}
</ul>
