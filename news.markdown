---
layout: default
title: News
---

<ul class="news">
  {% for new in site.news %}
    <li>
      <h2>{{ new.title }}</h2>
      <h3 style="color: #808080;">{{ new.date | date_to_string}}</h3>
      {% if new.location%}<h3>{{new.location}}</h3>{% endif %}
      <p>{{ new.content | markdownify }}</p>
    </li>
  {% endfor %}
</ul>