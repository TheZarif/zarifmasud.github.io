---
permalink: /
title: "About Me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I'm a PhD student in Computer Engineering at Toronto Metropolitan University, co-supervised by Dr. Ebrahim Bagheri and Dr. Syed Ishtiaque Ahmed. My research interests sit at the intersection of responsible AI, social computing, and migration studies. Using techniques from natural language processing and information retrieval, I take a critical lens to observe how immigration is framed across various media and popular culture, and how data driven systems embed within them biased frames that end up marginalizing migrants.

## Current Projects

{% include base_path %}

<style>
.project-item {
  margin-bottom: 0.75em;
}
.project-title {
  margin-bottom: 0.25em;
  color: var(--global-heading-color);
}
.project-title a {
  color: var(--global-heading-color);
}
.project-excerpt {
  font-size: 0.9em;
  margin-top: 0.25em;
  margin-bottom: 0.5em;
}
.publication-item {
  margin-bottom: 0.75em;
}
.publication-title {
  margin-bottom: 0.25em;
  color: var(--global-heading-color);
}
.publication-title a {
  color: var(--global-heading-color);
}
.publication-venue {
  font-size: 0.9em;
  margin-top: 0.25em;
  margin-bottom: 0.5em;
}
</style>

{% assign current_projects = site.projects | sort: "date" | reverse %}

{% for project in current_projects %}
<div class="project-item">
<div class="project-title"><strong><a href="{{ base_path }}{{ project.url }}">{{ project.title }}</a></strong></div>
<div class="project-excerpt">{{ project.excerpt }}</div>
</div>
{% endfor %}

## Recent Publications

{% assign recent_pubs = site.publications | sort: "year" | reverse %}

{% for pub in recent_pubs limit:3 %}
<div class="publication-item">
<div class="publication-title"><strong><a href="{{ base_path }}{{ pub.url }}">{{ pub.title }}</a></strong></div>
<div class="publication-venue">{% if pub.authors %}{{ pub.authors }}. {% endif %}{% if pub.year %}({{ pub.year }}). {% endif %}{% if pub.venue %}{{ pub.venue }}{% endif %}</div>
</div>
{% endfor %}
