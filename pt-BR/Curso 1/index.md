---
layout: default
title: Curso 1
---


<ul>
  {% for p in site.pages %}
	{% if p.term == 1%}
      <li>
        <a {% if p.url == page.url %}class="active"{% endif %} href="{{ p.url }}">
          {{ p.title }}
        </a>
      </li>
	{%endif %}
  {% endfor %}
</ul>
