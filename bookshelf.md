---
layout: page
title: Bookshelf
permalink: /bookshelf/
---

Browse everything I've added so far.

<ul class="book-grid">
{% assign all = site.books | sort: 'title' %}
{% for b in all %}
  <li class="book-card">
    {% if b.cover %}
      <img class="book-cover" src="{{ b.cover | relative_url }}" alt="Cover of {{ b.title }}">
    {% else %}
      <div class="book-cover" aria-hidden="true"></div>
    {% endif %}
    <div>
      <a href="{{ b.url | relative_url }}"><strong>{{ b.title }}</strong></a>
      <div class="book-meta">{{ b.author }}{% if b.series %} · {{ b.series }}{% endif %}</div>
      <div class="book-meta">
        <span class="badge">{{ b.status | upcase }}</span>
        {% if b.rating and b.rating > 0 %}<span class="badge">{{ b.rating }}★</span>{% endif %}
        {% if b.pages and b.pages > 0 %}<span class="badge">{{ b.pages }} pages</span>{% endif %}
      </div>
    </div>
  </li>
{% endfor %}
</ul>
