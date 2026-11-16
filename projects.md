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
{% assign img = project.card_image | default: project.card_images[0] | default: project.header.teaser %}
<article class="project-card">
{% if img %}
<a class="project-card__image" href="{{ project.url | relative_url }}">
<img src="{{ img | relative_url }}" alt="{{ project.title }}" loading="lazy">
</a>
{% endif %}
<div class="project-card__body">
<h2><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h2>
<p class="project-card__blurb">{{ project.excerpt | strip_html }}</p>
<div class="project-card__tools">
{% assign tool_list = project.tools | split: " · " %}
{% for tool in tool_list %}<span class="tool-tag">{{ tool }}</span> {% endfor %}
</div>
</div>
</article>
{% endfor %}
</div>