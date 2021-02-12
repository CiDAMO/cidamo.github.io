
---
layout: page
title: II CiDWeek
subtitle: II Semana de Ciência de Dados do CiDAMO
---

Na semana dos dias 19 a 23 de abril de 2021 o CiDAMO irá realizar o II CiDWeek -- uma Semana de Ciência de Dados. Este evento contará com palestras de cientista de dados da área, palestra de empresas, apresentações acadêmica de alunos da graduação e pós-graduação e uma mesa redonda.

Os eventos acontecerão de forma online, na plataforma X.

### Inscrições
As inscrições dos alunos para apresentação de trabalhos no CiWeek são de forma gratuita, pelo seguinte endereço: [inscrição]
As inscrições como ouvinte e apresentação de trabalhos acadêmicos são de forma gratuita, conforme as datas a seguir.
-   Inscrição para apresentação de trabalhos: de 01/03/2021 a 19/03/2021. [inscrição apresentação](https://docs.google.com/forms/d/1j9L9wk2dbmNQ2kIHKl2rE25Qbma7F-ZmIq5w6H4F-rM).
-   Inscrição para ouvintes: a partir de 01/03/2021. [inscrição ouvinte](https://docs.google.com/forms/d/1iMjGoixWtu8W-HOZMe7GPQ6tbfLrk6o00RAA79_d_Hg).

### Programação

<!--  Teremos várias atividades no evento: -->
<table style="width: 700pxpx; height: 550px;">
<tbody>
<tr>
<th style="width: 84px;">Segunda</th>
<th style="width: 86px;">Ter&ccedil;a</th>
<th style="width: 92px;">Quarta</th>
<th style="width: 92px;">Quinta</th>
<th style="width: 94px;">Sexta</th>
</tr>
<tr>
<td style="width: 84px;" rowspan="2">
<a href="#palestras">Palestras<br /> 13h30 &agrave;s 18h30</a>
</td>
<td style="width: 86px;">
<a href="#palestras-acadêmicas">Palestras<br /> 13h30 &agrave;s 15h30</a>
</td>
<td style="width: 92px;">
<a href="#palestras-acadêmicas">Palestras <br /> 13h30 &agrave;s 15h30</a>
</td>
<td style="width: 92px;" rowspan="2">
<a href="#palestras-de-empresas">Palestras&nbsp;de Empresas <br/> 13h30 &agrave;s 18h30</a>
</td>
<td style="width: 94px;" rowspan="2">
<a href="#palestras-de-empresas">Palestras&nbsp;de Empresas <br /> 13h30 &agrave;s 18h30</a>
</td>
</tr>
<tr>
<td style="width: 86px;"><a href="#apresentações-acadêmica-de-alunos">Apresenta&ccedil;&otilde;es Acad&ecirc;mica de Alunos<br />15h30 &agrave;s 18h30</a></td>
<td style="width: 92px;">
<a href="#apresentações-acadêmica-de-alunos">Apresenta&ccedil;&otilde;es Acad&ecirc;mica de Alunos <br /> 15h30 &agrave;s 18h30</p>
</td>
</tr>
<tr>
<td style="width: 84px;" rowspan="2">
<a href="#mesa-redonda">Mesa Redonda <br /> 19h30 &agrave;s 20h30</a>
</td>
<td style="width: 86px;" rowspan="2"><a href="#palestras">Palestras<br />19h30 &agrave;s 21h30</a></td>
<td style="width: 92px;">
<a  href="#palestras">Palestras<br />19h30 &agrave;s 20h30</a>
<td style="width: 92px;" rowspan="2" href="#minicursos"><a href="#minicursos">Minicursos <br /> 19h30 &agrave;s 21h00</a>
<td style="width: 94px;" rowspan="2">&nbsp;</td>
</tr>
<tr>
<td style="width: 92px;"><a href="#mesa-redonda">Mesa Redonda <br /> 20h30 &agrave;s 21h30</a>
</tr>
</tbody>
</table>

<!-- <table class="cronograma">
<thead>
   <tr>
      <th>Seg</th>
      <th>Ter</th>
      <th>Qua</th>
      <th>Qui</th>
      <th>Sex</th>
   </tr>
</thead>
<tbody>
   <tr>
      <td class="aulas">
         <a href="#palestras-academicas">
         Palestras Acadêmicas <br>
         13h30 às 17h30
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
</table> -->

### Palestras de Empresas
As palestras de empresas acontecerão de hora em hora na quinta e sexta a partir das 13h30.

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
- Quinta
	- 13h30 - pessoa (empresa)
	- 14h30 - pessoa (empresa)
	- 15h30 - pessoa (empresa)
	- 16h30 - pessoa (empresa)
	- 17h30 - pessoa (empresa)
- Sexta
	- 13h30 - pessoa (empresa)
	- 14h30 - pessoa (empresa)
	- 15h30 - pessoa (empresa)
	- 16h30 - pessoa (empresa)
	- 17h30 - pessoa (empresa)

### Palestras
As apresentações das palestras acontecerão de segunda a quarta.

Programação:
- Segunda
	- 13h30 - palestrante
	- 14h30 - palestrante
	- 15h30 - palestrante
	- 16h30 - palestrante
	- 17h30 - palestrante
- Terça
	- 13h30 - palestrante
	- 14h30 - palestrante
	- 19h30 - palestrante
	- 20h00 - palestrante
	- 20h30 - palestrante
	- 21h00 - palestrante
- Quarta
	- 13h30 - palestrante
	- 14h30 - palestrante
	- 19h30 - palestrante
	- 20h00 - palestrante
### Apresentações Acadêmica de Alunos
As apresentações acadêmicas dos alunos de graduação e pós-graduação acontecem segunda e terça à tarde, e cada apresentação será de 15 a 20 minutos mais 5 minutos para perguntas. Programa das apresentações e resumos em breve. <!-- de acordo com o seguinte [programa](link editar). -->

A relação dos trabalhos aceitos serão divulgados neste site e os alunos palestrantes receberão e-mail de confirmação. Para submeter um trabalho será necessário enviar um resumo para o e-mail CiDAMO@gmail.com seguindo um dos modelos abaixo. O e-mail deve ter o título "Resumo II CidWeek", em anexo resumo no formato **TEX** ou **DOC** (conforme modelo) e respectivo arquivo em **PDF**. 

Modelos de resumo :
|       Tipo       |   Arquivo    |
|------------------|--------------|
|       LaTeX      |              |
|       Word       |              |

Os alunos inscritos  que forem selecionados de acordo com critérios do CiDAMO , serão avisados até dia 29 de Março.

### Minicursos
Os minicursos serão em forma de apresentação.

Programação:
|       |   Quinta    |
|-------|-------------|
| 19:30 | Minicurso 1 |
| 20:30 | Minicurso 2 |
| 21:30 | Minicurso 3 |

Os minicursos serão os seguintes:
- Minicurso 1: assunto - palestrante
- Minicurso 2: assunto - palestrante
- Minicurso 3: assunto - palestrante

### Mesa Redonda
A mesa redonda, com o tema LPGD (Lei de Proteção de Dados). Os profissionais que participarão são

- profissional 1
- profissional 2
- profissional 3
- profissional 4
- profissional 5

<!-- 
### Hackathon

Faremos um Hackathon no evento, realizado pelo Grupo Boticário com infraestrutura pela Math Analytics.
O Hackathon irá acontecer no laboratório 1/2 da informática.
Os escolhidos devem se apresentar no laboratório às 8h30 de Sexta, e devem
estar disponíveis no fim do dia às 17h para apresentar a solução.

As inscrições estão encerradas. Os participantes serão informados por e-mail dos detalhes.

**Importante:**
- As equipes devem ter até quatro pessoas;
- Um dos membros da equipe deve ser aluno regularmente matriculado na UFPR.-->
