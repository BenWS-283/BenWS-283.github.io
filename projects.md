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
{% assign card_images = project.card_images | slice: 0, 3 %}
{% assign card_image_count = card_images | size %}
<article class="project-card">
{% if card_image_count > 0 %}
<a class="project-card__images project-card__images--{{ card_image_count }}" href="{{ project.url | relative_url }}">
{% for img in card_images %}
<img src="{{ img | relative_url }}" alt="{{ project.title }} image {{ forloop.index }}" loading="lazy">
{% endfor %}
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