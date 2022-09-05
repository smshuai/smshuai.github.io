---
layout: page
title: team
order: 1
permalink: /team/
description: 🥷 <i>H. sapiens</i> studying <i>H. sapiens</i>
nav: true
display_categories: 
horizontal: false
---

<div class="projects">
  {% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
    {% for category in page.display_categories %}
      <h2 class="category">{{category}}</h2>
      {% assign categorized_projects = site.members | where: "category", category %}
      {% assign sorted_projects = categorized_projects | sort: "importance" %}
      <!-- Generate cards for each project -->
      {% if page.horizontal %}
        <div class="container">
          <div class="row row-cols-2">
          {% for project in sorted_projects %}
            {% include projects_horizontal.html %}
          {% endfor %}
          </div>
        </div>
      {% else %}
        <div class="grid">
          {% for project in sorted_projects %}
            {% include projects.html %}
          {% endfor %}
        </div>
      {% endif %}
    {% endfor %}

  {% else %}
  <!-- Display projects without categories -->
    {% assign sorted_projects = site.members | sort: "importance" %}
    <!-- Generate cards for each member -->
    {% if page.horizontal %}
      <div class="container">
        <div class="row row-cols-1 no-gutters">
        {% for project in sorted_projects %}
          {% include projects_horizontal.html %}
        {% endfor %}
        </div>
      </div>
    {% else %}
      <div class="container">
        <div class="row">
        {% for project in sorted_projects %}
          <div class="col-sm-4">
          {% include members.html %}
          </div>
        {% endfor %}
        </div>
      </div>
    {% endif %}

  {% endif %}

  <h2>Alumni</h2>
  <table>
    <tr>
      <th>Name</th>
      <th>Time in COmics</th>
      <th>Position in COmics</th>
      <th>Current Position</th>
    </tr>
    <tr>
      <td>Guijun Sun</td>
      <td>2021-2022</td>
      <td>Admin Assistant</td>
      <td>-</td>
    </tr>
  </table>
</div>


