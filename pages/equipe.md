---
layout: page
permalink: "/equipe/"
#
# Content
#
subheadline: ""
title: "Equipe"
teaser: ""
categories:
  -
tags:
  - 
#
# Styling
#
image:
    thumb: "header-quadras-thumb.jpg"
header:
    image_fullwidth: "header-quadras.jpg"
    caption: Equipe CiDAMO
roles:
    - Coordenador
    - Membro
---

{% for role in page.roles %}
<h2> {{ role }} </h2>
{% for p in site.data.equipe %}
{% if p[1].role == role %}
<div id="{{ p[0] }}" class="row membro t30">

<div class="small-4 columns">
<img class="membro-img card-img" src="{{ site.urlimg }}equipe/{{ p[1].img }}">
</div>

<div class="membro-body small-8 columns">
<h3> {{ p[1].name }} </h3>
<p class="card-text">
   {% if p[1].github %}
   <a href="https://github.com/{{ p[1].github }}" class="fa fa-github"></a>
   {% else %}
   <i class="fa fa-github fa-gray"></i>
   {% endif %}
   {% if p[1].linkedin %}
   <a href="https://linkedin.com/in/{{ p[1].linkedin }}" class="fa fa-linkedin"></a>
   {% else %}
   <i class="fa fa-linkedin fa-gray"></i>
   {% endif %}
   {% if p[1].twitter %}
   <a href="https://twitter.com/{{ p[1].twitter }}" class="fa fa-twitter"></a>
   {% else %}
   <i class="fa fa-twitter fa-gray"></i>
   {% endif %}
</p>

{% if p[1].email1 %}
<span class="email"> {{ p[1].email1 }}<i class="fa fa-at"></i>{{ p[1].email2 }} </span>
{% endif %}
</div>
</div>
{% endif %}
{% endfor %}
{% endfor %}
