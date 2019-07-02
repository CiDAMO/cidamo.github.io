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
---

{% for p in site.data.equipe %}
<div class="row membro t30">

<div class="small-4 columns">
<img class="membro-img card-img" src="{{ site.urlimg }}equipe/{{ p.img }}">
</div>

<div class="membro-body small-8 columns">
<h3> {{ p.name }} </h3>
<p class="card-text">
   {% if p.github %}
   <a href="https://github.com/{{ p.github }}" class="fa fa-github"></a>
   {% else %}
   <i class="fa fa-github fa-gray"></i>
   {% endif %}
   {% if p.linkedin %}
   <a href="https://linkedin.com/in/{{ p.linkedin }}" class="fa fa-linkedin"></a>
   {% else %}
   <i class="fa fa-linkedin fa-gray"></i>
   {% endif %}
   {% if p.twitter %}
   <a href="https://twitter.com/{{ p.twitter }}" class="fa fa-twitter"></a>
   {% else %}
   <i class="fa fa-twitter fa-gray"></i>
   {% endif %}
</p>
</div>
</div>
{% endfor %}
