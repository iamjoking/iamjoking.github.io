---
layout: page
title: Tags
permalink: /tags/
---


{% if site.posts != empty %}
<ul class = "post-tags-num">
{% for tag in site.tags %}
<li> <a href="#{{ tag[0] }}" title="{{ tag[0] }}" rel="{{ tag[1].size }}">{{ tag[0] }}<span> {{ tag[1].size }}</span></a> </li>
{% endfor %}
</ul>

<ul class="tags-box">
{% for tag in site.tags %}
<li id="{{ tag[0] }}">{{ tag[0] }}</li>
{% for post in tag[1] %}
<time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time> &raquo;
<a href="{{ site.baseurl }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a><br />
{% endfor %}
{% endfor %}
{% else %}
<span>No posts</span>
{% endif %}
</ul>
