---
layout: page
title: I CiDWeek
subtitle: I Semana de Ciência de Dados do CiDAMO
---

Na semana dos dias 3 a 7 de Fevereiro o CiDAMO irá realizar o primeiro CiDWeek -- uma Semana de Ciência de Dados.
Este evento contará com um minicurso de introdução à aprendizagem de máquina, apresentações de trabalhos, palestras de empresas, job fair, e um hackathon.

O evento acontecerá primariamente no 1° andar do prédio de administração do Centro Politécnico na UFPR.

## Inscrições

As inscrições estão fechadas. Os inscritos serão notificados em breve.

__A entrada é 1 kg de alimento não perecível.__

Os inscritos serão selecionados de acordo com critérios pessoais do CiDAMO, e serão avisados até o dia 31 de Janeiro.

## Programação

Teremos várias atividades no evento:

<table class="cronograma">
<thead>
   <tr>
      <th>Seg-Qua</th>
      <th>Qui</th>
      <th rowspan="3">Sex</th>
   </tr>
</thead>
<tbody>
   <tr>
      <td class="aulas">
         <a href="#minicurso">
         Minicurso Machine Learning <br>
         09h00 às 12h20
         </a>
      </td>
      <td rowspan="0" class="empresas">
         <a href="#palestras-de-empresas">
         Palestras de empresas <br>
         8h às 18h30 <br>
         </a> <br>
         <a href="#job-fair">
         Estandes de empresas <br>
         durante o dia
         </a>
      </td>
      <td rowspan="0" class="hackathon">
         <a href="#hackathon">
         Hackathon <br>
         8h30 às 17h30
         </a>
      </td>
   </tr>
   <tr>
      <td class="simposio">
         <a href="#apresentação-de-trabalhos">
         Trabalhos acadêmicos <br>
         14h às 17h30
         </a>
      </td>
   </tr>
</tbody>
</table>

### Minicurso

As aulas serão todas em forma de apresentação, devido ao espaço e tempo disponível.

Programação:

|       | Segunda | Terça  | Quarta |
|-------|---------|--------|--------|
| 09:00 | Aula 1  | Aula 3 | Aula 5 |
| 10:30 | Break   | Break  | Break  |
| 10:50 | Aula 2  | Aula 4 | Aula 6 |
| 12:10 | Almoço  | Almoço | Almoço |

As aulas serão as seguintes:

- Aula 1: Introdução, regressão linear e polinomial - Prof. César Augusto Taconeli
- Aula 2: Validação cruzada, overfitting e underfitting - Prof. Abel Soares Siqueira
- Aula 3: Classificação, KNN, árvores e florestas - Prof. Lucas Garcia Pedroso
- Aula 4: Naive Bayes e regressão logística - Henrique Laureano
- Aula 5: Clusterização - Prof. Walmes Zeviani
- Aula 6: Análise descritiva e tratamento de dados - Kally Chung

### Apresentação de trabalhos

As sessões acontecem segunda e terça à tarde, de acordo com o seguinte [programa]({{ site.baseurl }}/files/programa.pdf).

### Palestras de empresas

As palestras de empresas acontecerão de hora em hora na Quinta a partir das 08h00.

<div class="container-full">
   <div class="row">
   {% for p in site.data.empresas %}
   <div class="row col-sm-12 col-md-6">
      <a class="empresa-link" href="{{ p.linkedin }}">
      <div class="empresa">
      <img class="pessoa-logo" src="/img/cidweek-logos-empresas/{{ p.logo }}">
      {% if p.logoemp %}
      <img class="empresa-logo" src="/img/cidweek-logos-empresas/{{ p.logoemp }}"> <br>
      {% else %}
      {{ p.empresa }} <br>
      {% endif %}
      <span class="nome">{{ p.nome }}</span> <br>
      <span class="nome-empresa">{{ p.empresa }}</span> <br>
      <span class="empresa-titulo">{{ p.title }}</span>
      </div>
      </a>
   </div>
   {% endfor %}
   </div>
</div>

Programação:

- 08h00 - Cauê Guimarães/Romulo Leite (EBANX)
- 09h00 - Giovani Buchelt (Numera)
- 10h00 - Coffee break
- 10h20 - Luiz Hadich (Math Analytics)
- 11h20 - Felipe Uliano (BRF)
- 12h20 - Almoço
- 14h00 - Cleibson Almeida (Olist)
- 15h00 - Fabio Tavares (James)
- 16h00 - Coffee break
- 16h20 - Edjan de Matos (Boticario)
- 17h20 - Rafael Cavalcanti (Bradesco)

### Job Fair

Estandes ficarão na frente da biblioteca onde as empresas poderão interagir com os participantes do evento.

### Hackathon

Faremos um Hackathon no evento, realizado pelo Grupo Boticário com infraestrutura pela Math Analytics.
O Hackathon irá acontecer no laboratório 1/2 da informática.
Os escolhidos devem se apresentar no laboratório às 8h30 de Sexta, e devem
estar disponíveis no fim do dia às 17h para apresentar a solução.

As inscrições estão encerradas. Os participantes serão informados por e-mail dos detalhes.

**Importante:**
- As equipes devem ter até quatro pessoas;
- Um dos membros da equipe deve ser aluno regularmente matriculado na UFPR.
