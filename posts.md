---
layout: default
title: Posts
permalink: /posts/
---

<style>
  .card-title {
    font-size: 1.5em; /* Aumenta o tamanho do título */
    font-weight: bold; /* Garante que o título seja em negrito */
    margin-bottom: 10px; /* Dá um espaço abaixo do título */
  }

  .card-date {
    font-size: 0.9em; /* Diminui o tamanho da data */
    color: #777; /* Dá uma cor mais suave para a data */
    margin-bottom: 10px; /* Dá um pequeno espaço abaixo da data */
  }
</style>

# Posts

<div class="cards-container">
  {% if site.posts.size > 0 %}
    {% for post in site.posts %}
      <div class="card">
        <div class="card-title">{{ post.title }}</div>
        <div class="card-date">{{ post.date | date: "%B %d, %Y" }}</div>
        <p>{{ post.excerpt | strip_html | truncatewords: 20 }}</p>
        <a href="{{ post.url | relative_url }}">Read More</a>
      </div>
    {% endfor %}
  {% else %}
    <p>No posts have been published yet. Stay tuned for updates!</p>
  {% endif %}
</div>
