---
layout: howtos
title: Skarlet IT & Security How To's!
permalink: /howtos/
pagination:
  enabled: true
  collection: post_lg
  per_page: 6
---

<!-- Pagination-aware post loop -->
{% assign today_unix = site.time | date: "%s" %}
{% assign one_week = 604800 %}

{% for post in paginator.posts %}
  {% assign post_unix = post.date | date: "%s" %}
  {% assign age = today_unix | minus: post_unix %}
  {% assign post_date = post.date | date: "%Y-%m-%d" %}
  {% assign today_date = site.time | date: "%Y-%m-%d" %}
  {% if post_date <= today_date %}
    <div class="col">
      <div class="card h-100 shadow-sm">
        {% if post.image %}
          <img src="{{ post.image }}" class="card-img-top" alt="{{ post.title }}">
        {% endif %}
        <div class="card-body d-flex flex-column">
          <h5 class="card-title">
            {{ post.title }}
            {% if age <= one_week %}
              <span class="badge bg-success ms-2">New</span>
            {% endif %}
          </h5>
          <p class="card-text text-muted small">{{ post.date | date: "%B %d, %Y" }}</p>
          <p class="card-text">{{ post.excerpt }}</p>
          <a href="{{ post.url }}" class="btn btn-primary mt-auto">Read More</a>
        </div>
      </div>
    </div>
  {% endif %}
{% endfor %}

<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path }}" class="prev">Previous</a>
  {% endif %}
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path }}" class="next">Next</a>
  {% endif %}
</div>
