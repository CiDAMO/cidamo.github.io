---
layout: page
title: Equipe
subtitle: Quem está no CiDAMO?
roles:
    - Coordenadores
    - Cientistas de Dados
    - Otimizadores
---

{% for role in page.roles %}
<h2> {{ role }} </h2>
<ul class="equipe-lista">
{% for p in site.data.equipe %}
{% if p[1].role == role %}
<li>
   {{ p[1].name }}
   {{ 
</li>
<!--
<div id="{{ p[0] }}" class="row membro">

<div class="col-xs-4">
<img class="membro-img card-img" src="{{ site.baseurl }}/equipe/{{ p[1].img }}">
</div>

<div class="membro-body col-xs-8">
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
<p class="email"> {{ p[1].email1 }}<i class="fa fa-at"></i>{{ p[1].email2 }} </p>
{% endif %}
</div>
</div>
-->
{% endif %}
{% endfor %}
</ul>
{% endfor %}
