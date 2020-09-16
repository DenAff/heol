---
title: Test-02
layout: test
permalink: test-02.html
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
            overflow: hidden;
        }

/* Mise en forme de la grille du site */

        .header{
          grid-area: hd;
          background-color: black;
        }

        .footer{
          grid-area: ft;
          background-color: white;
        }

        .content{
          grid-area: main;
          overflow-y: scroll;
          background-color: white;
          padding: 50px;
        }

        .main-nav{
          grid-area: nav;
          padding: 30px;
          align-items: center;
          text-align: center;
          background-color: #111;
        }

        .wrapper{
          height: 100vh;
          width: 100vw;
          display: grid;
          grid-template-columns: auto 1fr;
          grid-template-rows: 1fr 1fr;
          grid-template-areas: 
            "nav hd"
            "nav main"
            "nav ft";
        }

/* Mise en forme du texte de la barre de navigation */

        .navLinks {
          display: flex;
          font-family: Verdana, Arial, Helvetica, sans-serif;
          font-size: 1.7em;
          text-decoration: none;
          color: grey
        }

        .navLinks:hover {
          color: white;
        }

/* Mise en forme de la grille du site pour petit écran */

        @media (max-width: 600px) {

          .wrapper{
            grid-template-columns: auto;
            grid-template-areas: 
              "nav"
              "hd"
              "main"
              "ft";
          }

          .main-nav{
            padding: 5px;
            align-items: center;
            text-align: center;
            background-color: #111;
          }

          .navLinks {
            display: inline-block;
            padding: 0px 10px;
            font-size: 1em;
          }

        } 

/* Mise en forme du contenu */

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
          font-family: Verdana, Arial, Helvetica, sans-serif; font-size: 14pt;
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
          font-family: Arial;
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

      </style>

  </head>

  <body>

<!--
  Grille de ma page
-->

        <div class='wrapper'>

          <div class='main-nav'>
            <a class='navLinks' href="/index"> {{ site.title }} </a>
            <a class='navLinks' href="/cartes">Cartes</a>
            <a class='navLinks' href="/recettes">Recettes</a>
            <a class='navLinks' href="/test">Test</a>
          </div>

        <div class='header'>
        </div>

          <div id="main" class='content'>

            <div class='content-text'>
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