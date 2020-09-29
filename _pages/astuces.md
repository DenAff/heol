---
title: Astuces
layout: default
permalink: astuces.html
---

<div id="main" class='content'>

            <div class='content-text'>

<!--
  Liste des posts, trié par ordre alphabétique
-->

              <ul class="docs-nav">

{% assign no_show_cat = "astuces" | split: "," %} <!--permet d'assigner la catégorie "astuces" à la liste "no_show_cat"-->
{% for category in site.categories %}
  {% unless no_show_cat contains category[0] %} <!--la liste "no_show_cat" est cachée-->
  <h3 id="{{ category[0] | downcase | url_escape | strip | replace: ' ', '-' }}">{{ category[0] | camelcase }}</h3>
  {% endunless %} <!--fin de la fonction unless-->
<ul>
{% assign pages_list = category[1] %}
{% for post in pages_list %}
{% unless post.categories contains 'astuces' %} <!-- permet de retirer les liens des post "astuces" -->
  <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
{% endunless %} <!--fin de la fonction unless-->
{% endfor %}
</ul>
{% endfor %}

              </ul>

            </div>

</div>