---
layout: main
title: Home
file: index
---

The words of a Indie Game Developer. [More about No Dime Games]({{ site.url }}/about.html).

{:.title}
## Latest Posts

<div class="group">
{% for post in site.posts %}
	<div class="posts">
		<div class="posts-img">
			<img class="img-responsive {% if post.image.class != ''%}{{ post.image.class }}{% endif %}" title="{{ post.title }}" alt="{{ post.title }}" src="{{ post.image.feature }}">
		</div>
		<a class="title" href="{{ site.url }}{{ post.url }}">{{ post.title}}</a>
		<div class="posts-date">{{ post.date | date: "%-d %B %Y"}}</div>
	</div>
{% endfor %}
</div>
 