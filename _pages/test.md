---
title: Test
permalink: test.html
---

<html>

  <head>

    <!--
    La balise suivante permet de déclarer la table d'encodage des caractères.
    la table UTF-8, permet théoriquement d'encoder toutes les langues, du français au japonais en passant par l'arabe.
    -->
    <meta charset="utf-8">
    
    <!--
    La balise suivante permet de ne pas indexer mon site web et bien plus.
    Plus d'info sur https://developers.google.com/search/reference/robots_meta_tag#max-image-preview
    -->
    <meta name="robots" content="noindex, nofollow, noarchive, nosnippet, notranslate, noimageindex">
    
    <!-- Permet de controler la dimenssion d'affichage de ma page web et le zoom dans celle-ci -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
 
    <!-- Titre ddu site web dans le navigateeur web -->
    <title>{{ site.title }} | {{ page.title }}</title>

      <style>

        body,html {
            padding: 0;
            margin: 0;
        }

        .header{
          grid-area: hd;
          background: url('{{ site.baseurl }}/_assets/images/home/travis-grossen.jpg');      
          background-position: center;
          background-repeat: no-repeat;
          background-size: cover;
          color: #ffffff;
          padding: 50px;
        }

        .footer{
          grid-area: ft;
          background-color: white;
        }

        .content{
          grid-area: main;
          background-color: white;
          padding: 50px; 
        }

        .sidebar{
          grid-area: sd;
          background-color: #111;
          padding-top: 30%;
        }

        .wrapper{
          display: grid;
          grid-template-columns: 1fr 1fr 3fr 1fr;
          grid-auto-rows: auto;
          grid-template-areas: 
            "hd hd hd hd"
            "sd main main main"
            "sd ft ft ft";
        }

        .text {
          display: flex;
          justify-content: center;
          align-items: center;
          padding: 20px;
          font-size: 30px;
          color: white;
          line-height: 1;
          font-family: "Lato", sans-serif;
          font-weight: 200;
        }

        .content-text {
          display: flex;
          justify-content: left;
          align-items: center;
          padding: 10px;
          font-size: 25px;
          color: black;
          line-height: 1;
          font-family: Arial;
          font-weight: 00;
        }

        .footer-text {
          display: flex;
          justify-content: center;
          align-items: center;
          padding: 20px;
          font-size: 10px;
          color: grey;
          line-height: 1;
          font-family: Arial;
          font-weight: 200;
        }        

        a:link {
          text-decoration: none;
          color: grey;
        }

        a:visited {
          text-decoration: none;
          color: grey;
        }

        #sidebar a:hover {
          text-decoration: none;
          color: white;
        }

        #main a:hover {
          text-decoration: none;
          color: black;
        }

        a:active {
          text-decoration: none;
          color: white;
        }

      </style>

  </head>

  <body>

<!--
  Grille de ma page
-->

        <div class='wrapper'>

          <div class='header'>
            <div class='text'> {{ site.title }} </div>
          </div>

          <div id="sidebar" class='sidebar'>
            <div class='text'>
              <a href="/index">Home</a>
            </div>

            <div class='text'>
              <a href="/cartes">Cartes</a>
            </div>

            <div class='text'>
              <a href="/recettes">Recettes</a>
            </div>

            <div class='text'>
              <a href="/test">Test</a>
            </div>
          </div>

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
    <li><strong>{{ category | replace: "-", " " | capitalize  }}</strong></li>
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

            <iframe
                width="100%" height="600px" allowfullscreen
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

            <p style="text-align:center">
             <a href="//umap.openstreetmap.fr/fr/map/sortir-a-paris_482924" target="_blank">Voir en plein écran</a>
            </p>

          </div>

          <div class='footer'>
            <div class='footer-text'> {{ site.title }} | {{ page.title }} </div>
          </div>

        </div>

  </body>

</html>