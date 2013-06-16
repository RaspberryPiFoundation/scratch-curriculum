---
layout: default
title: Curso 1
---


<ul>
{% assign count = '0' %}

{% assign sorted_pages = site.pages  | sort: "url" %}
  {% for p in sorted_pages %}
	{% if p.term == 1%}
	{% capture count %}{{ count | plus: '1' }}{% endcapture %}

      <li>
        <a {% if p.url == page.url %}class="active"{% endif %} href="{{ p.url }}">
         {{ count }} - {{ p.title }}
        </a>
      </li>
	{%endif %}
  {% endfor %}
</ul>
