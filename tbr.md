---
layout: page
title: TBR
permalink: /tbr/
---

Books I want to read next.

<ul class="book-grid">
{% assign tbr = site.books | where: 'status', 'tbr' | sort: 'title' %}
{% for b in tbr %}
  <li class="book-card">
    {% if b.cover %}
      <img class="book-cover" src="{{ b.cover | relative_url }}" alt="Cover of {{ b.title }}">
    {% else %}
      <div class="book-cover" aria-hidden="true"></div>
    {% endif %}
    <div>
      <a href="{{ b.url | relative_url }}"><strong>{{ b.title }}</strong></a>
      <div class="book-meta">{{ b.author }}</div>
      {% if b.genre %}<div class="book-meta"><span class="badge">{{ b.genre | join: " · " }}</span></div>{% endif %}
    </div>
  </li>
{% endfor %}
</ul>
