---
layout: blog
title: Security Blog!
permalink: /blog/
---

{% for post in paginator.posts %}
  <!-- Same loop as before for displaying posts -->
{% endfor %}

<!-- Pagination navigation -->
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path }}" class="prev">Previous</a>
  {% endif %}
  
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path }}" class="next">Next</a>
  {% endif %}
</div>
