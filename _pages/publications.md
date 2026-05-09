---
layout: page
permalink: /publications/
title: publications
order: 3
description: >
  Hope this list never ends😊
years: [2026, 2025, 2024, 2023, 2022, 2020, 2019, 2017]
nav: true
---

Author roles are shown after <u style="color:#ed6b00">COmics member</u> names only.


<div class="publications">
  
{% for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
