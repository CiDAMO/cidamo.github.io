---
layout: page
title: II CiDWeek
subtitle: II Semana de Ciência de Dados do CiDAMO
image: /img/II-CiDWeek.jpg
author: Grupo CiDAMO
---


<div class="sidenav">
  <a  href="#inscricao" >Inscrição</a>
  <!--<a  href="#programacao">Programação</a>-->
  <a  href="#apresentacao">Apresentações de Alunos</a>
  <a  href="#palestra_em">Palestra de Empresas</a>
  <a  href="#palestras">Palestras</a>
  <a  href="#mesa_redonda">Mesa Redonda</a>
</div>

Sejam bem-vindos à página da 2ª **CiDWeek**, a semana de Ciência de Dados do [Grupo CiDAMO](/sobre/), que ocorrerá entre os dias 26 e 30 de abril de 2021. O evento será online e as inscrições são gratuitas. Entre as atividades, teremos:

- Palestras de pesquisadores e profissionais renomados, que abordarão o assunto sob diversos aspectos;
- Apresentações de empresas com forte atuação em Ciência de Dados e que contratam profissionais nesta área;
- Apresentações de alunos de graduação, pós-graduação e especialização, que terão a oportunidade de compartilhar com a comunidade os trabalhos que vêm desenvolvendo.

A CiDWeek será transmitida no nosso Canal no <a href="https://www.youtube.com/channel/UCiVFjGGCh63QZ3-kswfQdRw" target="_blank">Youtube</a>, então se inscreva e marque na agenda!

Contamos com sua participação!


### Inscrições e Submissão de Currículos

<div id="inscricao"></div>

A inscrição para a CiDWeek é totalmente gratuita. Abaixo estão os links para as inscrições, bem como as datas a serem observadas.
-   **Inscrição para a CiDWeek:** a partir de 15/03/2021. <a href="https://forms.gle/kBRHJUBY7DfXwzCJ7" target="_blank">Clique aqui.</a>
-   **Inscrições para apresentar na CiDWeek:** de 15/03/2021 a 05/04/2021. <a href="https://forms.gle/WvNkhUPfRtVzqXxN6" target="_blank">Clique aqui.</a> 
    -- **Obs:** note que os alunos que desejam apresentar trabalhos precisam preencher os dois formulários acima. Além disso, será necessário e envio do título do trabalho e de um resumo. Para mais detalhes, consulte abaixo a seção **Apresentações de Alunos**.

-   **Submissão posterior de currículo:** a partir de 15/03/2021. Apenas para quem deseja enviar currículo às empresas participantes porém não o fez durante a inscrição. <a href="https://forms.gle/2n8kzXBfm9KsL8d89" target="_blank">Clique aqui.</a>


### Programação
A Programação da CiDWeek estará disponível em breve...

### Apresentações de Alunos
<div id="apresentacao"></div>
As apresentações de trabalhos de alunos terão duração de até 20 minutos e mais 5 minutos reservados para as perguntas. Durante a inscrição para apresentar um trabalho, será necessária a submissão de um resumo seguindo um dos modelos abaixo. **Atenção: o documento deve ser convertido para o formato PDF para que o envio seja aceito.**

Modelos de resumo :

|  Tipo |                                                           Arquivo                                                           |
|:-----:|:---------------------------------------------------------------------------------------------------------------------------:|
| LaTeX | <a href="https://drive.google.com/file/d/1B2PIuyYSQH3ypMjFkj03BhaIJmfuyRcD/view?usp=sharing" target="_blank">Modelo.tex</a> |
|  Word | <a href="https://drive.google.com/file/d/1lH2egK0rMSDWFKHpTo3IZ9DLBesa9sBc/view?usp=sharing" target="_blank">Modelo.doc</a> |

Os autores dos trabalhos selecionados pelo comitê científico do evento serão contactados num prazo de até duas semanas após o envio do resumo. O dia e horário da apresentação serão comunicados por e-mail e também ficarão disponíveis nesta página, fiquem atentos!


### Palestras de Empresas
<div id="palestra_em"></div>
Algumas empresas farão apresentações no evento, abordando temas como: problemas práticos resolvidos dentro da empresa, vagas e regras dos processos de contratação e estágio, ambiente de trabalho na empresa, desafios diários enfrentados por um cientista de dados, tipos de parcerias com a comunidade acadêmica que a empresa tem ou deseja iniciar, problemas que ainda estão em aberto, dentre outros.

Teremos a participação de 12 representantes de empresas, dentre os quais estão:
<div class="container_em">
{% for em in site.data.empresas_apresentadores.empresas %}
  <div class="caixa_empresa col-xs-12 col-sm-6 col-md-4">
    <div class="empresa_layout">
    {% if em.logoemp%}
        <img class="empresa-logo" alt="{{em.nome}}" title="{{em.nome}}" src="/img/cidweek-empresas/{{ em.logoemp }}">
    {% endif %}
    <!-- <span class="nome-titulo-empresa">{{ em.nome }}</span><br> -->
    <div class="palestrantes_empresa">
    {% for p in em.membros %}
        {% if p.linkedin%}
        <a class="" href="{{ p.linkedin }}" target="_blank">
        {% else %}
        <a>
        {% endif %}
        <div class="estilo-empresa empresa_{{em.numero}}">
            <div class="estilo-empresa-img">
              {% if p.logo%}
                <img class="pessoa-logo_empresa" src="/img/cidweek-empresas/{{ p.logo }}">
              {%else%}
                <img class="pessoa-logo_empresa" src="/img/cidweek-empresas/speaker.png">
            {% endif %}
            </div>
            <div class="estilo-empresa-data">
              <span class="nome">{{ p.nome }}</span><br>
              <span class="empresa-titulo">{{ p.title }}</span>
            </div>        
        </div>
        </a>
    {% endfor %}
    </div>
    </div>
  </div>
{% endfor %}
</div>
<!--<div class="container_em">
   <div class="row">
   {% for p in site.data.empresas_cidweek %}
   <div class="caixa_empresa col-xs-12 col-sm-6 col-md-4">
      <a class="empresa-link" href="{{ p.linkedin }}" target="_blank">
      <div class="empresa">
      {% if p.logo%}
      <img class="pessoa-logo" src="/img/cidweek-empresas/{{ p.logo }}">
      {%else%}
      <img class="pessoa-logo" src="/img/cidweek-empresas/speaker.png">
      {% endif %}
      {% if p.logoemp%}
          <img class="empresa-logo" src="/img/cidweek-empresas/{{ p.logoemp }}">
      {% endif %}
      <br>
      <span class="nome">{{ p.nome }}</span> <br>
      <span class="nome-empresa">{{ p.empresa }}</span> <br>
      <span class="empresa-titulo">{{ p.title }}</span>
      </div>
      </a>
   </div>
   {% endfor %}
  </div>
   <div style="clear:both"></div>
</div>-->

<!-- 
 
<div class="slideshow-container">

  <div class="mySlides fade">
    <div class="numbertext">1 / 3</div>
    <img src="img1.jpg" style="width:100%">
    <div class="text">Caption Text</div>
  </div>

  <div class="mySlides fade">
    <div class="numbertext">2 / 3</div>
    <img src="img2.jpg" style="width:100%">
    <div class="text">Caption Two</div>
  </div>

  <div class="mySlides fade">
    <div class="numbertext">3 / 3</div>
    <img src="img3.jpg" style="width:100%">
    <div class="text">Caption Three</div>
  </div>

  <a class="prev" onclick="plusSlides(-1)">&#10094;</a>
  <a class="next" onclick="plusSlides(1)">&#10095;</a>
</div>
<br>

The dots/circles 
<div style="text-align:center">
  <span class="dot" onclick="currentSlide(1)"></span>
  <span class="dot" onclick="currentSlide(2)"></span>
  <span class="dot" onclick="currentSlide(3)"></span>
</div>-->

### Palestras
<div id="palestra"></div>
Foram convidados palestrantes com muito domínio sobre os tópicos referentes às suas áreas de atuação. Será uma oportunidade única de refletir e aprender sobre a área de Ciência de Dados. Entre os temas abordados estarão empreendedorismo, parcerias universidade-empresas, questões de gênero e raça, avanços científicos em Aprendizagem de Máquina, entre outros. A lista (incompleta) dos palestrantes está abaixo.

<div class="container_em">
   <div class="row">
   {% for p in site.data.palestrantes%}
   <div class="caixa_empresa col-xs-12 col-sm-6 col-md-4">
      <a class="empresa-link" href="{{ p.linkedin }}" target="_blank">
      <div class="apresentador">
      {% if p.logo%}
      <img class="pessoa-logo" src="/img/cidweek-palestrantes/{{ p.logo }}">
      {%else%}
      <img class="pessoa-logo" src="/img/cidweek-empresas/speaker.png">
      {% endif %}
      {% if p.logoemp%}
          <img class="empresa-logo" src="/img/cidweek-palestrantes/{{ p.logoemp }}">
      {% endif %}
      <br>
      <span class="nome">{{ p.nome }}</span> <br>
      <span class="nome-empresa">{{ p.empresa }}</span> <br>
      <span class="empresa-titulo">{{ p.title }}</span>
      </div>
      </a>
   </div>
   {% endfor %}
  </div>
</div>



### Mesa Redonda
<div id="mesa_redonda"></div>
Durante a mesa redonda, uma seleção de profissionais discorrerá sobre o tema "Início da carreira em Ciência de Dados". Dentre os participantes confirmados, haverá uma recrutadora, um cientista de dados sênior e uma estagiária. Cada um deles tem experiências diferentes e bem interessantes sobre o assunto debatido, o que certamente resultará em uma discussão bastante enriquecedora. Participe!

<div class="container_em">
   <div class="row">
   {% for p in site.data.mesa_redonda%}
   <div class="caixa_empresa col-xs-12 col-sm-6 col-md-4" >
      <a class="empresa-link" href="{{ p.linkedin }}" target="_blank">
      <div class="apresentador">
      {% if p.logo%}
      <img class="pessoa-logo" src="/img/cidweek-palestrantes/{{ p.logo }}">
      {%else%}
      <img class="pessoa-logo" src="/img/cidweek-empresas/speaker.png">
      {% endif %}
      {% if p.logoemp%}
          <img class="empresa-logo" src="/img/cidweek-palestrantes/{{ p.logoemp }}">
      {% endif %}
      <br>
      <span class="nome">{{ p.nome }}</span> <br>
      <span class="nome-empresa">{{ p.empresa }}</span> <br>
      <span class="empresa-titulo">{{ p.title }}</span>
      </div>
      </a>
   </div>
   {% endfor %}
  </div>
</div>

<hr>
Icone de Palestrante por <a style="background-color:black;color:white;text-decoration:none;padding:4px 6px;font-family:-apple-system, BlinkMacSystemFont, &quot;San Francisco&quot;, &quot;Helvetica Neue&quot;, Helvetica, Ubuntu, Roboto, Noto, &quot;Segoe UI&quot;, Arial, sans-serif;font-size:12px;font-weight:bold;line-height:1.2;display:inline-block;border-radius:3px" href="https://www.freepik.com" target="_blank" rel="noopener noreferrer" title="Freepik from flaticon.com"><span style="display:inline-block;padding:2px 3px"><svg xmlns="http://www.w3.org/2000/svg" style="height:12px;width:auto;position:relative;vertical-align:middle;top:-2px;fill:white" viewBox="0 0 32 32"><title>unsplash-logo</title><path d="M10 9V0h12v9H10zm12 5h10v18H0V14h10v9h12v-9z"></path></svg></span><span style="display:inline-block;padding:2px 3px">Freepik</span></a>