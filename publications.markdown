---
layout: default
title: Publications
---
{% for publi in site.publications %}
  - ## {%if publi.doi %}[{{ publi.title }}]({{publi.doi}}) {%else%} {{ publi.title }} {% endif %} {%if publi.status %}({{publi.status}}){% endif %} {%if publi.github %}<a href="{{ publi.github }}"><img width=30em style="margin-bottom: -.25em;" src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png"></a>{% endif %}
    {{publi.author}}{% case publi.type %} {% when "inproceedings" %} at {%if publi.publisher_url %}[{{ publi.booktitle }}]({{publi.publisher_url}}) {%else%} {{ publi.booktitle }} {% endif %} {% when "journal" %} in {%if publi.publisher_url %}[{{ publi.booktitle }} {{publi.issue}}, {{publi.article_number}}]({{publi.publisher_url}}) {%else%} {{ publi.booktitle }} {{publi.issue}}, {{publi.article_number}} {% endif %} ({{publi.date | date: "%Y"}}) {% endcase %}
{% endfor %}