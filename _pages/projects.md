---
layout: page
title: team
permalink: /team/
description: 
nav: true
nav_order: 2
display_categories: [PhD, Postgraduate]
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  <!-- {%- assign sorted_projects = categorized_projects | sort: "importance" %} -->
  {%- assign sorted_projects = site.data.team[category] %}
  <artiacle>{{ site.data.team.test}}</artiacle>
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
    <div>proje</div>
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid" style="display:flex;flex-direction: column;justify-content: center;justify-items: center;">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}
{%- endif -%}
</div>
