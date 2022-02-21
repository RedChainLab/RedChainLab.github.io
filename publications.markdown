---
layout: default
title: Publications
---
{% for publi in site.publications %}
  - ## {%if publi.doi %}[{{ publi.title }}]({{publi.doi}}) {%else%} {{ publi.title }} {% endif %} {%if publi.status %}({{publi.status}}){% endif %}
    {{publi.author}}{% case publi.type %} {% when "inproceedings" %} at {%if publi.publisher_url %}[{{ publi.booktitle }}]({{publi.publisher_url}}) {%else%} {{ publi.booktitle }} {% endif %} {% when "MAThesis" %} ({{publi.date | date: "%Y"}}) [Unpublished Master's Thesis, {{publi.location}}] {% endcase %}
{% endfor %}