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
          <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
        </div>
        <div class="card-body">
          <p>{{ project.excerpt | strip_html | truncatewords: 20 }}</p> <!-- Exibe uma descrição curta ou resumo do projeto -->
          <p><strong>Start:</strong> {{ project.start_date | date: "%B %d, %Y" }}</p>
          <p><strong>End:</strong>
            {% if project.end_date %}
              {{ project.end_date | date: "%B %d, %Y" }}
            {% else %}
              Ongoing
            {% endif %}
          </p>
        </div>
        <div class="card-footer">
          <a href="{{ project.url | relative_url }}">Read More</a>
        </div>
      </div>
    {% endfor %}
  {% else %}
    <p>No projects have been published yet. Check back later for updates!</p>
  {% endif %}
</div>