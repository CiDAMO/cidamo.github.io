---
layout: page
title: Resumos de Palestrantes - 2ª CiDWeek
subtitle: 
image: /img/II-CiDWeek.jpg
author: Grupo CiDAMO
---

Nessa página estão disponíveis os resumos correspondentes as apresentações de nossos palestrantes da 2ª CiDWeek do Grupo CiDAMO.

{% assign sorted_p = site.data.palestrantes | sort:'nome' %}

<div class="container_em">
{% for p in sorted_p%}
      <hr>
	<div class="resumo">
            <span class="nome-resumo">{{ p.nome }}</span>
            <br>
            {% if p.abstract%}
                  <div class="abstract">
                  <span class="titulo-resumo">
                        {{p.abstract.title}}
                  </span>
                  <span>
                  <br>
                        {{p.abstract.content}}
                  </span>
                  </div> 
            {%else%}
            <span>Resumo ainda não disponível...</span>
            {% endif %}
      </div>

{% endfor %}
</div>