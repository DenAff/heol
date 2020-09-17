---
title: Test
layout: test
permalink: test.html
---

 <div id="main" class='content'>

            <div class='content-text'>

<!--
  Liste des posts, trié par ordre alphabétique
-->

              <ul class="docs-nav">
              {% assign posts_list = site.posts | sort:"title" %}
              {% assign last_cat = "" %}
              {% for posts in posts_list %}
                {% if posts.title != "" %}
                  {% for category in posts.categories limit:1 %}
                    {% if category != last_cat %}
              <li-category><strong>{{ category | replace: "-", " " | capitalize  }}</strong></li-category>
                {% endif %}
                {% assign last_cat = category %}
              {% endfor %}
              <li><a href="{{ posts.slug }}" class="cc-active">{{ posts.title }}</a></li>
              {% endif %}
              {% endfor %}
              </ul>

            </div>

<!--
  La carte de nos lieux de sorties à Paris
-->
            <div class="conteneur">
              <iframe
                allowfullscreen
                src="//umap.openstreetmap.fr/fr/map/sortir-a-paris_482924?scale
                Control=true&miniMap=false&scrollWheelZoom=true&zoom
                Control=false&allowEdit=false&more
                Control=false&search
                Control=true&tilelayersControl=false&embedControl=true&datalayers
                Control=true&onLoadPanel=none&captionBar=false&fullscreen
                Control=true&locate
                Control=true&measureControl=false&editinosm
                Control=false">
              </iframe>
            </div>

            <p style="text-align:center">
             <a href="//umap.openstreetmap.fr/fr/map/sortir-a-paris_482924" target="_blank">Voir en plein écran</a>
            </p>

        </div>
       