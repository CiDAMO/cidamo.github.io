---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
  image_fullwidth: header-lago.jpg
widget1:
  title: "Projetos"
  url: '/projetos/'
  image: 'header-dados-normal.jpg'
  text: 'Veja nossos projetos finalizados e em andamento'
widget2:
  title: "Equipe"
  url: '/equipe/'
  image: 'header-quadras.jpg'
  text: 'Conheça a nossa equipe'
widget3:
  title: "Blog"
  url: '/blog'
  image: 'header-caneta.jpg'
  text: 'Blog é blog'
#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#
callforaction:
  url: /
  text: Exemplo de mensagem de alerta
  style: alert
permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---

<div id="videoModal" class="reveal-modal large" data-reveal="">
  <div class="flex-video widescreen vimeo" style="display: block;">
    <iframe width="1280" height="720" src="https://www.youtube.com/embed/3b5zCFSmVvU" frameborder="0" allowfullscreen></iframe>
  </div>
  <a class="close-reveal-modal">&#215;</a>
</div>
