---
layout: page
title: DNF
permalink: /dnf/
---

Didn’t click for me (no hate! just taste).

<ul class="book-grid">
{% assign dnf = site.books | where: 'status', 'dnf' | sort: 'title' %}
{% for b in dnf %}
  <li class="book-card">
    {% if b.cover %}
      <img class="book-cover" src="{{ b.cover | relative_url }}" alt="Cover of {{ b.title }}">
    {% else %}
      <div class="book-cover" aria-hidden="true"></div>
    {% endif %}
    <div>
      <a href="{{ b.url | relative_url }}"><strong>{{ b.title }}</strong></a>
      <div class="book-meta">{{ b.author }}</div>
      {% if b.recommend %}<div class="book-meta"><span class="badge">Why: {{ b.recommend }}</span></div>{% endif %}
    </div>
  </li>
{% endfor %}
</ul>
