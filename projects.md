---
layout: default
title: Projects
permalink: /projects/
---

# Projects

<div class="projects-container">
  {% for project in site.projects %}
    <div class="card">
      <div class="card-header">
        <a href="{{ project.url }}">{{ project.title }}</a>
      </div>
      <div class="card-body">
        <p>{{ project.excerpt }}</p> <!-- Exibe uma descrição curta ou resumo do projeto -->
      </div>
      <div class="card-footer">
        <a href="{{ project.url }}">Read More</a>
      </div>
    </div>
  {% else %}
    <p>No projects found yet.</p>
  {% endfor %}
</div>
