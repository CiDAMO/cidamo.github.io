---
layout: equipe
title: Equipe
subtitle: Quem está no CiDAMO?
roles:
    - Pesquisador Colaborador
    - Pesquisadores de Graduação
---

<h2> Coordenadores </h2>
<div class="row">
{% for p in site.data.coordenadores %}
<div class="col-xs-12 col-sm-6 col-md-4">
   <div class="image-flip" >
      <div class="mainflip flip-0">
         <div class="frontside">
               <div class="card">
                  <div class="card-body text-center">
                     <br><br>
                     <img class="img-fluid" src="{{ site.baseurl }}/equipe/{{ p[1].img }}">
                     <h4 class="card-title">{{ p[1].name }}</h4>
                     <a class="btn btn-primary btn-sm"><i class="fa fa-plus"></i></a>
                  </div>
               </div>
         </div>
         <div class="backside">
               <div class="card">
                  <div class="card-body text-center mt-4">
                     <h4 class="card-title">{{ p[1].name }}</h4>
                     <p class="card-text">{{ p[1].bio }}</p>
                     <ul class="list-inline">
                        <div class="card-info">
                           {% if p[1].github %}
                              <a href="https://github.com/{{ p[1].github }}" class="fa fa-2x  fa-github"></a>
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
                     </ul>
                  </div>
               </div>
         </div>
      </div>
   </div>
</div>
{% endfor %}
</div>


{% for role in page.roles %}
<h2> {{ role }} </h2>
<div class="row">
   {% assign i = 0 %}
   {% for p in site.data.equipe %}
   {% if p[1].role == role %}
<div class="col-xs-12 col-sm-6 col-md-4">
      <div >
         <div>
            <div class="frontside">
                  <div class="card">
                     <div class="card-body text-center">
                        <img class="img-fluid" src="{{ site.baseurl }}/equipe/{{ p[1].img }}">
                        <h4 class="card-title">{{ p[1].name }}</h4>
                        <p class="card-text">{{ p[1].bio }}</p>
                        <ul class="list-inline">
                           <div class="card-info">
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
                        </ul>
                     </div>
                  </div>
            </div>
         </div>
      </div>
</div>
{% endif %}
   {% endfor %}
</div>
{% endfor %}