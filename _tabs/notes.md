---
layout: page
title: Notes
icon: fas fa-sticky-note
order: 1.5
permalink: /notes/
---

<div id="notes-archive">
  {% for note in site.notes reversed %}
    {% assign cur_month_year = note.date | date: '%B %Y' %}
    
    {% if cur_month_year != last_month_year %}
      {% unless forloop.first %}</ul>{% endunless %}
      
      <h2 class="mt-4 mb-3">{{ cur_month_year }}</h2>
      <ul class="list-unstyled">
      
      {% assign last_month_year = cur_month_year %}
    {% endif %}
    
    <li class="mb-2">
      <span class="text-muted">{{ note.date | date: '%d' }}</span>
      <a href="{{ note.url | relative_url }}">{{ note.date | date: '%B %d, %Y' }}</a>
    </li>
    
    {% if forloop.last %}</ul>{% endif %}
  {% endfor %}
</div>
