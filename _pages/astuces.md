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
{% assign no_show_cat = "astuces" | split: "," %} <!--assign astuces to no_show_cat-->
{% for category in site.categories %}
  {% unless no_show_cat contains category[0] %} <!--la liste no_show_cat est cachée-->
  <h3 id="{{ category[0] | downcase | url_escape | strip | replace: ' ', '-' }}">{{ category[0] | camelcase }}</h3>
  {% endunless %} <!--fin de la fonction unless-->
<ul>
{% assign pages_list = category[1] %}
{% for post in pages_list %}
{% unless post.categories contains 'astuces' %} <!-- Retire les liens des post astuces -->
  <li><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <time datetime="{{ post.date | date_to_xmlschema }}" itemprop="datePublished">{{ post.date | date: "%B %d, %Y" }}</time></a></li>
{% endunless %} <!--fin de la fonction unless-->
{% endfor %}
</ul>
{% endfor %}

              </ul>

            </div>

</div>    