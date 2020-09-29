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

{% assign sorted_cats = site.categories | sort %} <!--permet d'assigner site.categories et de trier la liste-->
{% assign no_show_cat = "entrée plats" %} <!--permet d'assigner la catégorie "astuces" à la liste "no_show_cat"-->
  {% for category in sorted_cats %}
    {% unless no_show_cat contains category[0] %} <!--la liste "no_show_cat" est cachée-->
      <!-- <li-category><strong>{{ category[0] | capitalize }}</strong></li-category> -->
    {% endunless %} <!--fin de la fonction unless-->

  {% assign pages_list = category[1] | sort:"title" %} <!-- permet entre autres de trier les liens par ordre alphabétique -->
  {% assign no_show_cat = "entrée plats" %} <!--permet d'assigner la catégorie "astuces" à la liste "no_show_cat"-->
    {% for post in pages_list %}
      {% unless no_show_cat contains category[0] %} <!-- permet de retirer les liens des post "astuces" -->
        <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
      {% endunless %} <!--fin de la fonction unless-->
    {% endfor %}
  {% endfor %}

              </ul>

            </div>

</div>