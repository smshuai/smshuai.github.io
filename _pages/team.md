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
      {% assign categorized_projects = site.team | where: "category", category %}
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
    {% assign sorted_projects = site.team | sort: "importance" %}
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

  <hr>
  <h2>Alumni</h2>
  <table style="width:100%">
    <tr>
      <th>Name</th>
      <th>Time in COmics</th>
      <th>Role in COmics</th>
      <th>Next Position</th>
    </tr>
    <tr>
      <td>Nuo Xu</td>
      <td>2021.09-2024.07</td>
      <td>MSc Student</td>
      <td>Beijing Institute of Genomics</td>
    </tr>  
    <tr>
      <td>Lanlan Cheng</td>
      <td>2023.05-2024.06</td>
      <td>Research Assistant</td>
      <td>SUSTech</td>
    </tr>    
    <tr>
      <td>Yi Ren</td>
      <td>2022.01-2024.05</td>
      <td>MSc Student & RA</td>
      <td>Industry</td>
    </tr>
    <tr>
      <td>Yongwei Zhu</td>
      <td>2023.07-2023.08</td>
      <td>Visiting Scientist</td>
      <td>Central South University</td>
    </tr>      
    <tr>
      <td>Yueshan Liang</td>
      <td>2023.07-2023.08</td>
      <td>Visiting Student</td>
      <td>Duke University</td>
    </tr>
    <tr>
      <td>Zican Zhou</td>
      <td>2021.12-2023.06</td>
      <td>Research Assistant</td>
      <td>Johns Hopkins University</td>
    </tr>   
    <tr>
      <td>Xing Wu</td>
      <td>2022.08-2022.12</td>
      <td>Visiting Student</td>
      <td>Westlake University</td>
    </tr>
    <tr>
      <td>Baoling Zhen</td>
      <td>2022.01-2022.10</td>
      <td>Research Assistant</td>
      <td>-</td>
    </tr> 
    <tr>
      <td>Guijun Sun</td>
      <td>2021.11-2022.08</td>
      <td>Admin Assistant</td>
      <td>Shihezi University</td>
    </tr>
  </table>
</div>