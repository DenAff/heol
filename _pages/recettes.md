---
title: Recettes
layout: test
permalink: recettes.html
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

</div>    