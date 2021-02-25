---
layout: page
title: II CiDWeek
subtitle: II Semana de Ciência de Dados do CiDAMO
image: /img/chairs.jpg
author: Grupo CiDAMO
customjs:
 - https://code.jquery.com/jquery-3.5.1.js
---
<script
  src="https://code.jquery.com/jquery-3.5.1.js"
  integrity="sha256-QWo7LDvxbWT2tbbQ97B53yJnYU3WhH/C8ycbRAkjPDc="
  crossorigin="anonymous">

</script>
<script type="text/javascript">
  // smooth scroll
$(document).ready(function(){
  // Add smooth scrolling to all links
  $('a[href*="#"]').on('click', function(event) {

    // Make sure this.hash has a value before overriding default behavior
    if (this.hash !== "") {
      // Prevent default anchor click behavior
      event.preventDefault();
    
      // Store hash
      var hash = this.hash;
    
      // Using jQuery's animate() method to add smooth page scroll
      // The optional number (800) specifies the number of milliseconds it takes to scroll to the specified area
      $('html, body').animate({
        scrollTop: $(hash).offset().top - 140
      }, 500, function(){
        
      });
    } // End if
  });
});
</script>
<style type="text/css" rel="stylesheet">
  /* The sidebar menu */
body {
    scroll-behavior: smooth;
}
.linkedin_icon {
    background: url('/img/in.png');
    background-size: cover;
    display: inline-block;
    height: 15px;
    width: 15px;
    top: 3px;
}
.sidenav {
  height: 50%; /* Full-height: remove this if you want "auto" height */
  width: 200px; /* Set the width of the sidebar */
  position: fixed; /* Fixed Sidebar (stay in place on scroll) */
  z-index: 1; /* Stay on top */
  top: 25%; /* Stay at the top */
  left: 0;
  background-color: transparent; /* Black */
  overflow-x: hidden; /* Disable horizontal scroll */
  padding-top: 20px;
  border-radius: 20px;
}

/* The navigation menu links */
.sidenav a {
  padding: 6px 8px 6px 16px;
  text-decoration: none;
  font-size: 14px;
  color: #5C5C5C;
  display: block;
}

/* When you mouse over the navigation links, change their color */
.sidenav a:hover {
  color: #000000;
}

/* Style page content */
.main {
  margin-left: 160px; /* Same as the width of the sidebar */
  padding: 0px 10px;
}

/* On smaller screens, where height is less than 450px, change the style of the sidebar (less padding and a smaller font size) */
@media screen and (max-height: 450px) {
  .sidenav {padding-top: 15px;}
  .sidenav a {font-size: 18px;}
}
</style>

<!-- Side navigation -->
<div class="sidenav">
  <a  href="#inscricao" >Inscrição</a>
  <a  href="#palestra_em">Palestra de Empresas</a>
  <a  href="#palestras">Palestras</a>
  <a  href="#apresentacao">Apresentações de Alunos</a>
  <a  href="#mesa_redonda">Mesa Redonda</a>

</div>
Seja muito bem-vindo a II Edição da **CiDWeek**, uma incrível semana de Ciência de Dados! Realizado por nós, o [Grupo CiDAMO](/sobre/). <br>O Evento ocorrerá na semana do dia 26 a 30 de abril de 2021, então marque na sua agenda e se prepare! O evento contará com palestras de cientista de dados da área, palestra de empresas, apresentações acadêmica de alunos da graduação e pós-graduação, além de uma mesa redonda com um assunto muito bacana.

Os eventos acontecerão online e contarão com transmissão ao vivo no YouTube e interação na plataforma X. Participe com a gente e não perca essa incrível oportunidade!

### Inscrições e Ajustes
<div id="inscricao"></div>
As inscrições dos alunos para participação e para a apresentação de trabalhos no CiDWeek são de forma gratuita. As inscrições seguem as datas abaixo, assim como seus respectivos formulários. <br>Caso ainda não tenha enviado seu currículo na sua inscrição, por favor preencha o formulário de ajuste.

Caso queira se inscrever como um aluno apresentador, por favor use os dois formulários (participante e apresentador), caso contrário use apenas o formulário de participante.

-   Inscrição para participante: a partir de 01/03/2021. 
-   Inscrição para apresentação de trabalhos: de 01/03/2021 a 19/03/2021.

<a href="https://docs.google.com/forms/d/1iMjGoixWtu8W-HOZMe7GPQ6tbfLrk6o00RAA79_d_Hg" target="_blank">Inscrição para Participante</a><br>

<a href="https://docs.google.com/forms/d/1j9L9wk2dbmNQ2kIHKl2rE25Qbma7F-ZmIq5w6H4F-rM" target="_blank">Inscrição para Apresentador</a><br>

<a href="https://docs.google.com/forms/d/1o7Wbv4gedTbUxE1asVBPn59BkmYKjrLEtqPQYtxSlAE" target="_blank">Ajuste de Dados</a><br>


### Programação
<div id="programacao"></div>
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
#legenda{width: 30%; }
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-j5fz{background-color:#FFD966;text-align:center;vertical-align:middle}
.tg .tg-rxsi{background-color:#A2C4C9;text-align:center;vertical-align:middle}
.tg .tg-w80k{background-color:#B4A7D6;text-align:center;vertical-align:middle}
.tg .tg-vxkg{background-color:#FF9D9D;text-align:center;vertical-align:middle}
.tg .tg-vt8p{background-color:#0F4F00;font-weight:bold;text-align:center;vertical-align:middle}
.tg .tg-2cz1{background-color:#F193C1;text-align:center;vertical-align:middle}
.tg .tg-in69{background-color:#89C7FF;text-align:center;vertical-align:middle}
</style>
<table class="tg" id="legenda">
<thead>
  <tr>
    <th class="tg-vt8p"><span style="font-weight:bold;background-color:#0F4F00">Legenda:</span></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-j5fz"><span style="background-color:#FFD966">Organizadores</span></td>
  </tr>
  <tr>
    <td class="tg-rxsi"><span style="background-color:#A2C4C9">Empresas</span></td>
  </tr>
  <tr>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Palestrantes</span></td>
  </tr>
  <tr>
    <td class="tg-vxkg"><span style="background-color:#FF9D9D">Alunos</span></td>
  </tr>
  <tr>
    <td class="tg-in69"><span style="background-color:#89C7FF">Intervalo</span></td>
  </tr>
  <tr>
    <td class="tg-2cz1"><span style="background-color:#F193C1">Mesa redonda</span></td>
  </tr>
</tbody>
</table>

<br>
<!--  Teremos várias atividades no evento: -->

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;text-align:center;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-baqh{text-align:center;vertical-align:top}
.tg .tg-j5fz{background-color:#FFD966;text-align:center;vertical-align:middle}
.tg .tg-rxsi{background-color:#A2C4C9;text-align:center;vertical-align:middle}
.tg .tg-w80k{background-color:#B4A7D6;text-align:center;vertical-align:middle}
.tg .tg-vxkg{background-color:#FF9D9D;text-align:center;vertical-align:middle}
.tg .tg-2cz1{background-color:#F193C1;text-align:center;vertical-align:middle}
.tg .tg-0lax{text-align:left;vertical-align:top}
.tg .tg-in69{background-color:#89C7FF;text-align:center;vertical-align:middle}
.tg .tg-3033{background-color:#89C7FF;text-align:center;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-0lax">Horário</th>
    <th class="tg-0lax">Segunda-Feira</th>
    <th class="tg-0lax">Terça-Feira</th>
    <th class="tg-0lax">Quarta-Feira</th>
    <th class="tg-0lax">Quinta-Feira</th>
    <th class="tg-0lax">Sexta-Feira</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-baqh">8h30-10h</td>
    <td class="tg-0lax"></td>
    <td class="tg-0lax"></td>
    <td class="tg-vxkg"><span style="background-color:#FF9D9D">Palestras Alunos</span></td>
    <td class="tg-vxkg"><span style="background-color:#FF9D9D">Palestras Alunos</span></td>
    <td class="tg-vxkg"><span style="background-color:#FF9D9D">Palestras Alunos</span></td>
  </tr>
  <tr>
    <td class="tg-baqh">10h-10h30</td>
    <td class="tg-0lax"></td>
    <td class="tg-0lax"></td>
    <td class="tg-in69"><span style="background-color:#89C7FF">Intervalo</span></td>
    <td class="tg-in69"><span style="background-color:#89C7FF">Intervalo</span></td>
    <td class="tg-in69"><span style="background-color:#89C7FF">Intervalo</span></td>
  </tr>
  <tr>
    <td class="tg-baqh">10h30-12h</td>
    <td class="tg-0lax"></td>
    <td class="tg-0lax"></td>
    <td class="tg-vxkg"><span style="background-color:#FF9D9D">Palestras Alunos</span></td>
    <td class="tg-vxkg"><span style="background-color:#FF9D9D">Palestras Alunos</span></td>
    <td class="tg-vxkg"><span style="background-color:#FF9D9D">Palestras Alunos</span></td>
  </tr>
  <tr>
    <td class="tg-baqh">12h-13h15</td>
    <td class="tg-0lax"></td>
    <td class="tg-0lax"></td>
    <td class="tg-3033" rowspan="2">Intervalo</td>
    <td class="tg-3033" rowspan="2">Intervalo</td>
    <td class="tg-3033" rowspan="2">Intervalo</td>
  </tr>
  <tr>
    <td class="tg-baqh">13h15</td>
    <td class="tg-j5fz"><span style="background-color:#FFD966">Abertura</span></td>
    <td class="tg-0lax"></td>
  </tr>
  <tr>
    <td class="tg-baqh">13h30-14h30</td>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Angela Bassa</span></td>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Palestra</span></td>
    <td class="tg-rxsi"><span style="background-color:#A2C4C9">James Delivery</span></td>
    <td class="tg-rxsi"><span style="background-color:#A2C4C9">Ebanx</span></td>
    <td class="tg-rxsi"><span style="background-color:#A2C4C9">Math Analytics</span></td>
  </tr>
  <tr>
    <td class="tg-0lax">14h30-15h30</td>
    <td class="tg-w80k"><span style="color:#000;background-color:#B4A7D6">Francisco Louzada</span></td>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Palestra</span></td>
    <td class="tg-rxsi"><span style="background-color:#A2C4C9">O Boticario</span></td>
    <td class="tg-rxsi"><span style="background-color:#A2C4C9">Magalu</span></td>
    <td class="tg-rxsi"><span style="background-color:#A2C4C9">Nestlé</span></td>
  </tr>
  <tr>
    <td class="tg-0lax">15h30-16h30</td>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Palestra </span></td>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Palestra</span></td>
    <td class="tg-rxsi"><span style="background-color:#A2C4C9">Contabilizei</span></td>
    <td class="tg-rxsi"><span style="background-color:#A2C4C9">Pacer</span></td>
    <td class="tg-rxsi"><span style="background-color:#A2C4C9">Paraná Bco/Olist</span></td>
  </tr>
  <tr>
    <td class="tg-0lax">16h30-17h30</td>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Palestra</span></td>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Palestra</span></td>
    <td class="tg-rxsi"><span style="background-color:#A2C4C9">NeuralMed</span></td>
    <td class="tg-rxsi"><span style="background-color:#A2C4C9">Kimberly-Clark</span></td>
    <td class="tg-rxsi"><span style="background-color:#A2C4C9">Bosch</span></td>
  </tr>
  <tr>
    <td class="tg-0lax">17h30-17h45</td>
    <td class="tg-3033" rowspan="2">Intervalo</td>
    <td class="tg-3033" rowspan="2">Intervalo</td>
    <td class="tg-3033" rowspan="2">Intervalo</td>
    <td class="tg-3033" rowspan="2">Intervalo</td>
    <td class="tg-j5fz"><span style="background-color:#FFD966">Encerramento</span></td>
  </tr>
  <tr>
    <td class="tg-0lax">17h45-19h30</td>
    <td class="tg-0lax"></td>
  </tr>
  <tr>
    <td class="tg-0lax">19h30-20h30</td>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Lenora Schwaitzer</span></td>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Anderson Soares</span></td>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Eduardo Ferreira</span></td>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Andressa Freires</span></td>
    <td class="tg-0lax"></td>
  </tr>
  <tr>
    <td class="tg-0lax">20h30-21h30</td>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Palestra</span></td>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Téo Calvo</span></td>
    <td class="tg-w80k"><span style="background-color:#B4A7D6">Denise Tsunoda</span></td>
    <td class="tg-2cz1"><span style="background-color:#F193C1">Mesa Redonda</span></td>
    <td class="tg-0lax"></td>
  </tr>
</tbody>
</table>



### Palestras de Empresas
<div id="palestra_em"></div>
Estarão presentes no evento algumas empresas convidadas, as quais estarão aceitando entrega de currículos e possivelmente empregando participantes, como ocorrido na CiDWeek anterior.

As palestras de empresas acontecerão de hora em hora *De Quarta a Sexta* a partir das 13h30.

E contaremos com a participação de: 

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
<!--As empresas confirmadas são as seguintes:

- Contabilizei
- Ebanx
- Magalu
- Math Analytcs
- Nestlé
- NeuralMed
- O Boticário
- Pacer
- James Delivery

<!-- As empresas ainda não confirmadas:

- Paraná Banco (Eduardo Veiga)
- Olist
- Kimberly Klark

Reservas

- Nubank
- Olist
- Picpay
- Mercado Livre
- Condor
- BCred
- Eletrolux
- Paraná Banco
- Bothub
- Pipefy -->

<!--
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
     -->

### Palestras

As apresentações das palestras acontecerão de segunda a quarta, conforme o cronograma acima. Os palestrantes são os seguintes:

- **Abertura**
   - <a href="https://www.linkedin.com/in/angelabassa/" target="_blank">Angela Bassa</a>
     - Senior Director of the Data Science e Analytics Center of Excellence at iRobot
- **Acadêmico**
   - <a href="https://www.linkedin.com/in/francisco-louzada-639048b7/" target="_blank">Franscisco Louzada</a>
      - Director of the MBA in Data Science na CeMEAI
  - Eduardo Vargas Ferreira
    - DEST - Universidade Federal do Paraná (UFPR)
  - Anderson Soares
    - Professor na Universidade Federal de Goiás (UFG)
- **Sociedade**
   -  <a href="https://www.linkedin.com/in/andressafreires/" target="_blank">Andressa Freires</a>
      - PicPay. Data Science, Inclusão Racial e de Gênero
   -  <a href="https://www.linkedin.com/in/teocalvo/" target="_blank">Téo Calvo</a>
      - Streamer. Professor na ASN.Rocks



<!-- Denise Tsunoda - https://www.linkedin.com/in/denise-tsunoda-65ab59/

DECIGI - Universidade Federal do Paraná (UFPR) (os palestrantes comentados retirar quando confirmados - lista baseada com o que está no Discord) 
 Lenora Schwaitzer - https://www.linkedin.com/in/lenoraschwaitzer/

Sócia e responsável técnica da GDGI 
Juliana Guamá - https://www.linkedin.com/in/juliana-guama/

Take Blip. e PyLadies BH -->

<!--
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
     -->

### Apresentações Acadêmica de Alunos
<div id="apresentacao"></div>
As apresentações acadêmicas dos alunos de graduação e pós-graduação acontecem segunda e terça à tarde, e cada apresentação será de 15 a 20 minutos mais 5 minutos para perguntas. Programa das apresentações e resumos em breve. <!-- de acordo com o seguinte [programa](link editar). -->

A relação dos trabalhos aceitos serão divulgados neste site e os alunos palestrantes receberão e-mail de confirmação. Para submeter um trabalho será necessário enviar um resumo para o grupo_cidamo@gmail.com seguindo um dos modelos abaixo. O e-mail deve ter o título com base no estilo "Resumo_PrimeiroNome_UltimoNome", em anexo resumo no formato **TEX** ou **DOC** (conforme o Modelo) e respectivo arquivo em **PDF**. 

Modelos de resumo :

| Tipo  | Arquivo                                                      |
| ----- | ------------------------------------------------------------ |
| LaTeX |                                                              |
| Word  | <a href="https://drive.google.com/file/d/1lH2egK0rMSDWFKHpTo3IZ9DLBesa9sBc/view?usp=sharing" target="_blank">Modelo.doc</a> |
| PDF   | <a href="https://drive.google.com/file/d/1toMnNJIhX7eeb8QvrIHA21cnABFrwY0p/view?usp=sharing" target="_blank">Modelo.pdf</a> |

Os alunos inscritos  que forem selecionados de acordo com critérios do CiDAMO , serão avisados até dia 29 de Março e serão informados do dia e da hora da palestra por e-mail, essa informação também ficará disponível no site do CiDAMO, então iquem atentos! Caso queira cancelar sua inscrição para a palestra, favor mandar e-mail o quão antes possível para o seguinte e-mail: grupo_cidamo@gmail.com.

### Mesa Redonda
<div id="mesa_redonda"></div>
A mesa redonda será um evento de discussão, no qual abordaremos os tema " Início da carreira em Ciência de Dados" e contaremos com uma Tech Recruiter, um cientista de dados, e um estagiário na área. Participe!

-  <a href="https://www.linkedin.com/in/kleberbenatti/" target="_blank">Kléber Benatti</a>
   - Cientista de Dados Sênior, Itaú Unibanco
- Tatiana Negrelli
   - Supervisora de RH e Business Partner Tech na James Delivery
- <a href="https://www.linkedin.com/in/lara-clink-205923184/" target="_blank">Lara Clink</a>
   - Estagiária de Engenharia de Dados na EBANX

