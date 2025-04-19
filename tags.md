---
layout: default
title: All Tags
permalink: /tags/
---

<ul>
  {% for tag in site.tags %}
    <li><a href="{{ '/tags/' | append: tag[0] | relative_url }}">{{ tag[0] }} ({{ tag[1].size }})</a></li>
  {% endfor %}
</ul>
