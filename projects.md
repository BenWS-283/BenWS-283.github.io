---
title: "Projects"
permalink: /projects/
layout: single
author_profile: false
classes:
  - wide
  - projects-index
---

<div class="project-grid">
{% assign sorted_projects = site.projects | sort: "date" | reverse %}
{% for project in sorted_projects %}
<article class="project-card">
{% if project.thumbnail %}
<a class="project-card__image" href="{{ project.url | relative_url }}">
<img src="{{ project.thumbnail | relative_url }}" alt="{{ project.thumbnail_alt | default: project.title | escape }}" loading="lazy">
</a>
{% endif %}
<div class="project-card__body">
<h2><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h2>
<p>{{ project.excerpt }}</p>
<p class="project-card__tools">{{ project.tools }}</p>
<a class="btn btn--primary" href="{{ project.url | relative_url }}">View project</a>
</div>
</article>
{% endfor %}
</div>