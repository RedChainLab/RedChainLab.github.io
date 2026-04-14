---
layout: default
title: Publications
---
# Theses
{% assign years = site.publications | group_by: "year" %}
{% assign yearsSorted = years | sort: "name" | reverse %}
{% for y in yearsSorted %}
{% assign yearTitlesSorted = y.items | sort: "title" %}
{% for publi in yearTitlesSorted %}
{% case publi.type %}
{% when "PhDThesis" %}
- ## {%if publi.doi %}[{{ publi.title }}]({{publi.doi}}) {%else%} {{ publi.title }} {% endif %} {%if publi.github %}<a href="{{ publi.github }}"><img width=30em style="margin-bottom: -.25em;" src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png"></a>{% endif %}
    {{publi.author}} ({{publi.year}}). *PhD Thesis, {{publi.location}}*
{% when "MAThesis" %}
- ## {%if publi.doi %}[{{ publi.title }}]({{publi.doi}}) {%else%} {{ publi.title }} {% endif %} {%if publi.github %}<a href="{{ publi.github }}"><img width=30em style="margin-bottom: -.25em;" src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png"></a>{% endif %}
    {{publi.author}} ({{publi.year}}). *MA Thesis, {{publi.location}}*
{% endcase %}
{% endfor %}
{% endfor %}

{% assign years = site.publications | group_by: "year" %}
{% assign yearsSorted = years | sort: "name" | reverse %}
{% for y in yearsSorted %}
{% assign yearTitlesSorted = y.items | sort: "title" %}
# {{y.name}}
{% for publi in yearTitlesSorted %}
{% unless publi.type contains "Thesis" %}
  - ## {%if publi.doi %}[{{ publi.title }}]({{publi.doi}}) {%else%} {{ publi.title }} {% endif %} {%if publi.status %}({{publi.status}}){% endif %} {%if publi.github %}<a href="{{ publi.github }}"><img width=30em style="margin-bottom: -.25em;" src="https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png"></a>{% endif %}
    {{publi.author}}{% case publi.type %} {% when "inproceedings" %} in the {%if publi.publisher_url %}[*{{ publi.booktitle }}*]({{publi.publisher_url}}) {%else%} *{{ publi.booktitle }}* {% endif %} {% when "journal" %} in {%if publi.publisher_url %}[*{{ publi.booktitle }} {{publi.issue}}, {{publi.article_number}}*]({{publi.publisher_url}}) {%else%} *{{ publi.booktitle }} {{publi.issue}}, {{publi.article_number}}* {% endif %} ({{publi.date | date: "%Y"}}) {% when "preprint" %} (preprint) {% when "PhDThesis" %}. {%if publi.publisher_url %}[*{{ publi.booktitle }}*]({{publi.publisher_url}}) {%else%} *{{ publi.booktitle }}* {% endif %} {% endcase %}
{% endunless %}
{% endfor %}
{% endfor %}