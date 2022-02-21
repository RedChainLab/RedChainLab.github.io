---
layout: default
title: News
---

<ul class="news">
  {% for new in site.news %}
    <li>
      <div class="NewsImage">
       {% include logo.html img= new.name alt= new.name %}
      </div>
      <h2>{{ new.title }}</h2>
      <h3 style="color: #808080;">{{ new.date | date: "%d %b %Y"}}{% if new.location%} - {{new.location}}{% endif %}</h3>
      
      <p>{{ new.content | markdownify }}</p>
    </li>
  {% endfor %}
</ul>