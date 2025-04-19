---
layout: default
title: Archives by Month
permalink: /months/
---

<h1>Monthly Archives</h1>
<ul>
  {% assign posts_by_month = site.posts | group_by_exp: "post", "post.date | date: '%Y-%m'" %}
  {% for month in posts_by_month %}
    {% assign year = month.name | split: '-' | first %}
    {% assign month_number = month.name | split: '-' | last %}
    <li>
      <a href="{{ '/' | append: year | append: '/' | append: month_number | append: '/' | relative_url }}">
        {{ month.name | date: "%B %Y" }}
      </a>
    </li>
  {% endfor %}
</ul>
