---
layout: default
title: Archives by Year
permalink: /years/
---

<h1>Yearly Archives</h1>
<ul>
  {% assign years = site.posts | map: 'date' | map: 'year' | uniq | sort | reverse %}
  {% for year in years %}
    <li>
      <a href="{{ '/' | append: year | append: '/' | relative_url }}">{{ year }}</a>
    </li>
  {% endfor %}
</ul>
