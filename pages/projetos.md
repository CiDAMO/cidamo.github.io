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

{% assign count = 0 %}
{% for projeto in site.data.projetos %}

{% if count == 0 %}
<div class="row t60">
{% endif %}

   <div class="medium-6 columns b30">
      <a href="{{ projeto.url }}" alt="{{ projeto.title }}">
      <!-- <img src="{{ site.urlimg }}{{ projeto.image }}" alt=""> -->
      <img src="http://placekitten.com/958/564" alt="">
      {{ projeto.title }}
      <p>
      <strong>{{ projeto.name }}</strong><br>
      {{ projeto.description }}
      </p>
      </a>
   </div><!-- /.medium-6.columns -->

{% if count == 1 %}
</div>
{% endif %}

{% if count == 0 %}
{% assign count = 1 %}
{% else %}
{% assign count = 0 %}
{% endif %}

{% endfor %}
