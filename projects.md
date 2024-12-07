---
layout: default
title: Projects
permalink: /projects/
---

# Projects

<div class="projects-container">
  {% if site.projects.size > 0 %}
    {% for project in site.projects %}
      <div class="card">
        <div class="card-header">
          <a href="{{ project.url }}">{{ project.title }}</a>
        </div>
        <div class="card-body">
          <p>{{ project.excerpt | strip_html | truncatewords: 20 }}</p> <!-- Exibe uma descrição curta ou resumo do projeto -->
        </div>
        <div class="card-footer">
          <a href="{{ project.url }}">Read More</a>
        </div>
      </div>
    {% endfor %}
  {% else %}
    <p>No projects have been published yet. Check back later for updates!</p>
  {% endif %}
</div>
