---
title: Recettes
layout: default
permalink: recettes.html
---

<div id="main" class='content'>

            <div class='content-text'>

<!--
  Liste des posts, trié par ordre alphabétique
-->

              <ul class="docs-nav">

{% assign sorted_cats = site.categories | sort %} <!--permet d'assigner site.categories et de trier la liste-->
{% assign no_show_cat = "astuces" | split: "," %} <!--permet d'assigner une catégorie à la liste "no_show_cat"-->
  {% for category in sorted_cats %}
    {% unless no_show_cat contains category[0] %} <!--la liste "no_show_cat" est cachée-->
      <li-category><strong>{{ category[0] | capitalize }}</strong></li-category>
    {% endunless %} <!--fin de la fonction unless-->

  {% assign pages_list = category[1] | sort:"title" %} <!-- permet entre autres de trier les liens par ordre alphabétique -->
    {% for post in pages_list %}
      {% unless post.categories contains 'astuces' %} <!-- permet de retirer les liens des post appartenant à cette catégorie -->
        <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
      {% endunless %} <!--fin de la fonction unless-->
    {% endfor %}
  {% endfor %}

              </ul>

            </div>

</div>    