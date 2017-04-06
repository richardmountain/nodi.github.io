---
layout: main
title: Home
file: index
---

<section>
	
  {% for post in site.posts %}
	
	<article>
		{{ post.date | date: "%-d %B %Y"}}
		<h1><a href="{{ post.url }}">{{ post.title }}</a></h1>
		{{ post.excerpt }}
	</article>
    
  {% endfor %}

</section>