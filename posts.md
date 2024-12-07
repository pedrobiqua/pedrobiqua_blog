---
layout: default
title: Posts
permalink: /posts/
---

# Posts

<div class="cards-container">
  {% if site.posts.size > 0 %}
    {% for post in site.posts %}
      <div class="card">
        <div class="card-title">{{ post.title }}</div>
        <div class="card-date">{{ post.date | date: "%B %d, %Y" }}</div>
        <p>{{ post.excerpt | strip_html | truncatewords: 20 }}</p>
        <a href="{{ post.url }}">Read More</a>
      </div>
    {% endfor %}
  {% else %}
    <p>No posts have been published yet. Stay tuned for updates!</p>
  {% endif %}
</div>
