---
layout: page
title: Equipe
subtitle: Quem está no CiDAMO?
roles:
    - Cientistas de Dados
    - Otimizadores
i: 0
---

<h2> Coordenadores </h2>

{% for p in site.data.coordenadores %}
{% assign info=p[1] %}

<div class="row">
<div class="card">
<!-- Image -->
<div class="col-lg-2">
   <img class="img-responsive" src="{{ site.baseurl }}/equipe/{{ info.img }}">
</div>
<!-- Name, Bio, Icons -->
<div class="col-lg-10">
   <span class="card-name"> {{ info.name }} </span>
   <p class="card-bio"> {{ info.bio }} </p>
   <div class="card-info">
   {% include card-icons.html %}
   </div>
</div>
</div>
</div>

{% endfor %}

{% for role in page.roles %}
<h2> {{ role }} </h2>
{% assign i = 0 %}

{% for p in site.data.equipe %}
{% assign info=p[1] %}
{% if info.role == role %}

{% if i == 0 %}
<div class="row">
{% endif %}
<div class="col-lg-6">
<!-- Card start -->
<div class="card">
<div class="row">
<!-- Image -->
<div class="col-lg-4">
   <img class="img-responsive" src="{{ site.baseurl }}/equipe/{{ info.img }}">
</div>
<!-- Name, Bio, Icons -->
<div class="col-lg-8">
   <span class="card-name"> {{ info.name }} </span>
   <p class="card-bio"> {{ info.bio }} </p>
   <div class="card-info">
   {% include card-icons.html %}
   </div>
</div>
</div>
</div>

</div>

{% if i == 0 %}
{% assign i = 1 %}
{% else %}
{% assign i = 0 %}
</div>
{% endif %}

{% endif %}
{% endfor %}
</div>
{% endfor %}
