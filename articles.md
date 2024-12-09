---
layout: default
title: Articles
permalink: /articles/
---

# Articles

{% if site.articles.size > 0 %}
  <div style="display: flex; flex-direction: column; gap: 20px;">
    {% for article in site.articles %}
    <a href="{{ article.url | relative_url }}" style="text-decoration: none; color: inherit; border: 1px solid #ddd; border-radius: 8px; padding: 15px; transition: box-shadow 0.2s ease;">
      <div style="display: flex; flex-direction: column; gap: 10px;">
        <h3 style="margin: 0;">{{ article.title }}</h3>
        <p style="margin: 0;"><strong>Authors:</strong> {{ article.authors }}</p>
        <p style="margin: 0;"><strong>Journal:</strong> {{ article.journal }}</p>
        <p style="margin: 0; font-style: italic;">Published on {{ article.date | date: "%B %d, %Y" }}</p>
      </div>
    </a>
    {% endfor %}
  </div>
{% else %}
  <p>No articles have been published yet. Check back later for updates!</p>
{% endif %}
