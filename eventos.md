---
layout: page
title: Eventos
subtitle:
image: /img/eventos.png
---

- [Próximos eventos](#próximos-eventos)
- [Eventos passados](#eventos-passados)

## Próximos eventos

Segue nosso calendário de eventos públicos. Nos siga no [linkedin](https://linkedin.com/company/grupo-cidamo) para ver notificações de novos eventos.

As apresentações ao vivo serão em geral pelo [YouTube](https://youtube.com/AbelSiqueira). Caso contrário, avisaremos na descrição.

Gostaria de fazer alguma apresentação no CiDAMO? Entre em contato com grupo.cidamo@gmail.com.

{% assign eventos=site.data.proxeventos | sort: 'data' %}
<table class="eventos">
  <tr>
    <th colspan="2"> Data </th>
    <th colspan="2"> Descrição </th>
  </tr>

{% for evento in eventos %}
  <tr class="evento-main">
    <td colspan="2"> {{ evento.data | date_to_string }} <br> {{ evento.hora }} </td>
    <td colspan="2"> {{ evento.nome | markdownify }} </td>
  </tr>
  {% for parte in evento.partes %}
  <tr class="evento-sub">
    <td> </td>
    <td colspan="2"> {{ parte.nome | markdownify }} </td>
    <td> {{ parte.desc | markdownify }} </td>
  </tr>
  {% endfor %}
{% endfor %}
</table>

## Eventos passados

{% assign eventos=site.data.eventospass | sort: 'data' | reverse %}
<table class="eventos">
  <tr>
    <th colspan="2"> Data </th>
    <th colspan="2"> Descrição </th>
  </tr>

{% for evento in eventos %}
  <tr class="evento-main">
    <td colspan="2"> {{ evento.data | date_to_string }} <br> {{ evento.hora }} </td>
    <td colspan="2"> {{ evento.nome | markdownify }} </td>
  </tr>
  {% for parte in evento.partes %}
  <tr class="evento-sub">
    <td> </td>
    <td colspan="2"> {{ parte.nome | markdownify }} </td>
    <td> {{ parte.desc | markdownify }} </td>
  </tr>
  {% endfor %}
{% endfor %}
</table>

