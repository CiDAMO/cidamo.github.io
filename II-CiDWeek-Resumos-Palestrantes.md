---
layout: page
title: Resumos de Palestrantes - 2ª CiDWeek
subtitle: 
image: /img/II-CiDWeek.jpg
author: Grupo CiDAMO
---

Nessa página estão disponíveis os resumos correspondentes as apresentações de nossos palestrantes da 2ª CiDWeek do Grupo CiDAMO.
<div class="container_em">
{% for p in site.data.palestrantes%}
      <hr>
	<div class="resumo">
      {% if p.logo%}
      <img class="logo-resumo" src="/img/cidweek-palestrantes/{{ p.logo }}">
      {%else%}
      <img class="logo-resumo" src="/img/cidweek-empresas/speaker.png">
      {% endif %}
      <span class="nome-resumo">{{ p.nome }}</span>
      <br>
      <span class="titulo-resumo">{{ p.title }}</span>
      <br>
      {% if p.abstract%}
      <span>
      {{p.abstract.title}}
      </span>
      <span>
      <br>
      {{p.abstract.content}}
      </span>
      {%else%}
      <span>Resumo ainda não disponível...</span>
      {% endif %}
      </div>

{% endfor %}
</div>