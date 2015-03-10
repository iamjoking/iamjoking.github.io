---
layout: page
title: Categories
permalink: /categories/
---

{% if site.posts != empty %}

<ul class = "post-tags-num">
{% for cat in site.categories %}
<li> <a href="#{{ cat[0] }}" title="{{ cat[0] }}" rel="{{ cat[1].size }}">{{ cat[0] }}<span> {{ cat[1].size }}</span></a> </li>
{% endfor %}
</ul>

<ul class="tags-box">
{% for cat in site.categories %}
<li id="{{ cat[0] }}">{{ cat[0]}}</li>
{% for post in cat[1] %}
<time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time> &raquo;
<a href="{{ site.baseurl }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a><br />
{% endfor %}
{% endfor %}
</ul>
{% else %}
<span>No posts</span>
{% endif %}

