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
{% assign card_layout = project.card_layout | default: "stack" %}
{% case card_layout %}
{% when "single" %}{% assign img_count = 1 %}
{% when "pair" %}{% assign img_count = 2 %}
{% else %}{% assign img_count = 3 %}
{% endcase %}
<article class="project-card">
<a class="project-card__images project-card__images--{{ card_layout }}" href="{{ project.url | relative_url }}">
{% for img in project.card_images limit: img_count %}
<img src="{{ img | relative_url }}" alt="{{ project.title }} image {{ forloop.index }}" loading="lazy">
{% endfor %}
</a>
<div class="project-card__body">
<h2><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h2>
<p>{{ project.excerpt }}</p>
<p class="project-card__tools">{{ project.tools }}</p>
<a class="btn btn--primary" href="{{ project.url | relative_url }}">View project</a>
</div>
</article>
{% endfor %}
</div>