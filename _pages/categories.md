---
layout: page
permalink: /categories/
title: Categories
---

{% for category in site.categories %}
  {% capture category_name %}{{ category | first }}{% endcapture %}
  <h2 class="category-name" id="{{ category_name | cgi_escape }}">{{ category_name }}</h2>
  {% for post in site.categories[category_name] %}
  <li class="category-post"><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></li>
  {% endfor %}
{% endfor %}

<script src="/assets/activate-category.js"></script>
