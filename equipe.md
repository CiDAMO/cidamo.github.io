---
layout: page
title: Equipe
subtitle: Quem está no CiDAMO?
roles:
    - Coordenadores
    - Cientistas de Dados
    - Otimizadores
i: 0
---

{% for role in page.roles %}
<h2> {{ role }} </h2>
<div class="row">
   {% assign i = 0 %}
   {% for p in site.data.equipe %}
      {% if p[1].role == role %}
         {% if i == 0 %}
<div class="row">
         {% endif %}
<div class="col-xs-12 col-md-6 col-lg-4">
   <div class="card">
      <img class="img-responsive" src="{{ site.baseurl }}/equipe/{{ p[1].img }}">
      <div class="card-info">
         <h4>{{ p[1].name }}</h4>
         {% if p[1].github %}
            <a href="https://github.com/{{ p[1].github }}" class="fa fa-2x fa-github"></a>
         {% else %}
            <i class="fa fa-2x fa-github fa-gray"></i>
         {% endif %}
         {% if p[1].linkedin %}
            <a href="https://linkedin.com/in/{{ p[1].linkedin }}" class="fa fa-2x fa-linkedin"></a>
         {% else %}
            <i class="fa fa-2x fa-linkedin fa-gray"></i>
         {% endif %}
         {% if p[1].twitter %}
            <a href="https://twitter.com/{{ p[1].twitter }}" class="fa fa-2x fa-twitter"></a>
         {% else %}
            <i class="fa fa-2x fa-twitter fa-gray"></i>
         {% endif %}
      </div>
   </div>
</div>
         {% if i == 2 %}
</div>
            {% assign i = 0 %}
         {% else %}
            {% if i == 3 %}
               {% assign i = 0 %}
            {% else %}
               {% if i == 0 %}
                  {% assign i = 1 %}
               {% else %}
                  {% assign i = 2 %}
               {% endif %}
            {% endif %}
         {% endif %}
      {% endif %}
   {% endfor %}
</div>
{% endfor %}