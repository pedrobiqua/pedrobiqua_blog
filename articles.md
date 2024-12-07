---
layout: default
title: Articles
permalink: /articles/
---

# Articles

{% for article in site.articles %}
- [{{ article.title }}]({{ article.url }}) - *{{ article.date | date: "%B %d, %Y" }}*
{% endfor %}
