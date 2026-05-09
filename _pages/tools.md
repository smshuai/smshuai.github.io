---
layout: page
title: tools
order: 4
permalink: /tools/
description: Computational tools and web portals developed by the lab
nav: true
display_categories: ["Software", "Web portals"]
---

<div class="tools">
  {% for category in page.display_categories %}
    <h2 class="category mt-5 mb-3" style="border-bottom: 1px solid #e0e0e0; padding-bottom: 0.3rem;">{{ category }}</h2>
    {% assign tools_in_cat = site.tools | where: "category", category | sort: "importance" %}
    {% for tool in tools_in_cat %}
      {% include tools.html %}
    {% endfor %}
  {% endfor %}
</div>
