---
title: Test
layout: test
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
    <title> {{ site.title | downcase | capitalize }} </title>

      <style>

        body,html {
            padding: 0;
            margin: 0;
            overflow: hidden;
            font-family: Verdana, Arial, Helvetica, sans-serif;
        }

/* Mise en forme de la grille du site */

        .header{
          grid-area: hd;   
          background-image: url('{{ site.baseurl }}/_assets/images/home/pattern.jpg');
          background-position: center; /* Center the image */
          background-repeat: repeat; /* Do not repeat the image */
          background-size: contain; /* Resize the background image to cover the entire container */
          background-color: white;
          border-top: 20px solid white;
        }

        .footer{
          grid-area: ft;
          background-color: white;
        }

        .content{
          grid-area: main;
          overflow-y: scroll;
          background-color: white;
          padding: 0px 50px;
        }

        .main-nav{
          grid-area: nav;
          padding: 30px;
          align-items: center;
          text-align: center;
          background-color: white;
        }

        .wrapper{
          height: 100vh;
          width: 100vw;
          display: grid;
          grid-template-columns: auto 1fr;
          grid-template-rows: 0.3fr 1fr auto;
          grid-template-areas: 
            "hd hd"
            "nav main"
            "ft ft";
        }

/* Mise en forme du texte de la barre de navigation */

        .navLinks {
          display: flex;
          font-size: 1.7em;
          text-decoration: none;
          color: grey
        }

        .navLinks:hover {
          color: black;
        }

        .navLinksLogo {
          display: flex;
          font-size: 1.7em;
          font-weight: 800;
          text-decoration: none;
          color: black;
        }

        .navLinksLogo:hover {
          color: grey;
        }
       

/* Mise en forme de la grille du site pour petit écran */

        @media (max-width: 600px) {

          .wrapper{
            grid-template-columns: auto;
            grid-template-rows: auto 0.3fr 1fr auto;
            grid-template-areas:
              "nav"
              "hd"
              "main"
              "ft";
          }

          .header{
            border-top: 0px;
          }

          .main-nav{
            padding: 5px;
            align-items: center;
            text-align: center;
          }

          .navLinks {
            display: inline-block;
            padding: 0px 10px;
            font-size: 1em;
          }

          .navLinksLogo {
            display: inline-block;
            padding: 0px 10px;
            font-size: 1em;
          }

        } 

/* Mise en forme du contenu */

        .content-text {
          display: flex;
          justify-content: left;
          align-items: center;
          padding: 10px;
          font-size: 14pt;
          color: black;
          line-height: 1;
          font-weight: 200;
        }

        .footer-text {
          display: flex;
          justify-content: center;
          align-items: center;
          padding: 20px;
          font-size: 10px;
          color: grey;
          line-height: 1;
          font-weight: 200;
        }

/* Mise en forme des liens hypertexte #main */

        #main a:link {
          text-decoration: none;
          color: grey;
        }

        #main a:visited {
          text-decoration: none;
          color: grey;
        }

        #main a:hover {
          text-decoration: none;
          color: black;
        }

        #main a:active {
          text-decoration: none;
          color: white;
        }

/* Mise en forme des puces pour les listes */

        ul {
          list-style-type: none;
          margin: 0;
          padding: 0;
        }

        ul {list-style: none}
        li::before {content: "⨉"; color: grey; font-size: 10px;
          display: inline-block; width: 1.2em; height: 2em;
          margin-left: -1em
        }

        ul li-category {
          color: white;
          background: black;
          margin: -10px;
          padding: 5px 10px;
          line-height: 4;
        }

/* Mise en forme iframes */

        .conteneur {
          position: relative;
        }

        .conteneur iframe {
          width: 100%;
          height: 600px;
        }

      </style>

  </head>

  <body>

<!--
  Grille de ma page
-->

        <div class='wrapper'>

          <div class='main-nav'>
            <a class='navLinksLogo' href="/index"> {{ site.title | upcase }} </a>
            <a class='navLinks' href="/cartes">Cartes</a>
            <a class='navLinks' href="/recettes">Recettes</a>
            <a class='navLinks' href="/test">Test</a>
          </div>

        <div class='header'>
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

          <div class='footer'>
            <div class='footer-text'> {{ site.title | downcase | capitalize }} | {{ page.title }} </div>
          </div>

        </div>

  </body>

</html>