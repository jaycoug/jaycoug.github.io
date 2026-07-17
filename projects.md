---
title: Projects
layout: default
---

Three active projects across public health analytics, operations forecasting, and sports analytics. Each deliverable links out to its hosted version or GitHub repo.

---

<div class="project-grid">
{% for project in site.data.projects %}
  <div class="project-card"
       data-domain="{{ project.domain | slugify }}"
       data-tech="{{ project.tech | join: ',' | downcase }}">

    <h2>{{ project.title }}</h2>
    <span class="category-tag">{{ project.domain }}</span>

    <p><strong>Question:</strong> {{ project.question }}</p>
    <p><strong>Data:</strong> {{ project.data }}</p>
    <p><strong>Data preparation:</strong> {{ project.data_prep }}</p>
    <p><strong>Methods:</strong> {{ project.methods }}</p>
    <p><strong>Findings:</strong> {{ project.findings }}</p>
    <p><strong>Limitation:</strong> {{ project.limitation }}</p>
    <p><strong>Links:</strong>
      {% for link in project.links %}<a href="{{ link.url }}">{{ link.label }}</a>{% unless forloop.last %} &mdash; {% endunless %}{% endfor %}
    </p>
  </div>
  {% unless forloop.last %}<hr>{% endunless %}
{% endfor %}
</div>
