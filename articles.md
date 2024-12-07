---
layout: default
title: Articles
permalink: /articles/
---

# Articles

{% if site.articles.size > 0 %}
  {% for article in site.articles %}
  - [{{ article.title }}]({{ article.url | relative_url }}) - *{{ article.date | date: "%B %d, %Y" }}*
  {% endfor %}
{% else %}
  <p>No articles have been published yet. Check back later for updates!</p>
{% endif %}

