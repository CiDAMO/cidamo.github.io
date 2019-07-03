---
layout: page-fullwidth
#
# Content
#
subheadline: ""
title: "Projetos"
teaser: ""
meta_description:
permalink: "/projetos/"
categories:
    - 
tags:
    - projetos
---

{% assign sorted_pages = (site.pages | sort: 'title') %}

<div class="row t60">
{% for page in sorted_pages %}
{% if page.key == 'projeto' %}

<div class="medium-6 columns b30">
  <a href="{{ page.url }}">
  <img src="{{ page.img }}" alt="{{ page.title }}: {{ page.description }}">
  <p>
  <strong>{{ page.title }}</strong><br>
  {{ page.description }}
  </p>
  </a>
</div>

{% endif %}
{% endfor %}
</div>
