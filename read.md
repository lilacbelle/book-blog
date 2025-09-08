---
layout: page
title: Read
permalink: /read/
---

Books I finished — newest first.

<ul class="book-grid">
{% assign read = site.books | where: 'status', 'read' | sort: 'finished' | reverse %}
{% for b in read %}
  <li class="book-card">
    {% if b.cover %}
      <img class="book-cover" src="{{ b.cover | relative_url }}" alt="Cover of {{ b.title }}">
    {% else %}
      <div class="book-cover" aria-hidden="true"></div>
    {% endif %}
    <div>
      <a href="{{ b.url | relative_url }}"><strong>{{ b.title }}</strong></a>
      <div class="book-meta">{{ b.author }}{% if b.finished %} · Finished: {{ b.finished }}{% endif %}</div>
      <div class="book-meta">
        <span class="badge">{{ b.rating }}★</span>
        {% if b.audiobook %}<span class="badge">Audiobook</span>{% endif %}
      </div>
    </div>
  </li>
{% endfor %}
</ul>
