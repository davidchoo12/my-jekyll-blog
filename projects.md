---
layout: default
title: Projects
permalink: /projects/
---

<h1>Projects</h1>

<p>Here is a list of my pet projects which I worked on during my free time. Many of which arises from my personal interest/needs.</p>
{% for project in site.data.projects %}
  <h2>{{ project.name }}</h2>
  <p>
    {% if project.url %}<a href="{{ project.url }}">Project link</a><br>{% endif %}
    {% if project.repo_url %}<a href="{{ project.repo_url }}">Github repo</a><br>{% endif %}
    {% if project.tech %}Tech used:
    {{ project.tech | join: ", " | markdownify | remove: '<p>' | remove: '</p>'}}<br>
    {% endif %}
    {% if project.progress %}Progress: {{ project.progress }}<br>{% endif %}
    {% if project.usage %}Usage frequency: {{ project.usage }}<br>{% endif %}
    {% if project.period %}Development period: {{ project.period }}{% endif %}
  </p>
  {% if project.image_url %}<img src="{{ project.image_url }}">{% endif %}
  {% if project.desc %}<p>{{ project.desc }}</p>{% endif %}
{% endfor %}
