---
layout: page
permalink: /teaching/
title: teaching
description: Some of the courses I taught, both in academia and in companies.
nav: true
nav_order: 5
horizontal: false # This sets the page.horizontal boolean variable.
---

<!--
  Note (Ema): the following block takes the same structure as for the projects section
              (indeed, the _includes/projects.html is used) but sources the data from
              the _courses directory.
-->
<!-- pages/teaching.md -->
<div class="teaching">
<!-- Display projects without categories -->
{%- assign sorted_courses = site.courses | sort: "importance" -%}
<!-- Generate cards for each project -->
{% if page.horizontal -%}
<div class="container">
  <div class="row row-cols-2">
  {%- for project in sorted_courses -%}
    {% include teaching_horizontal.html %}
  {%- endfor %}
  </div>
</div>
{%- else -%}
<div class="grid">
  {%- for project in sorted_courses -%}
    {% include teaching.html %}
  {%- endfor %}
</div>
{%- endif -%}
</div>
