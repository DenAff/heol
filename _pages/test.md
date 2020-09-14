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
          padding-top: 80%;
        }

        .wrapper{
          display: grid;
          grid-template-columns: 1fr 1fr 3fr 1fr;
          grid-auto-rows: auto;
          grid-template-areas: 
            "sd hd hd hd"
            "sd main main main"
            "sd ft ft ft";
        }

        .text {
          display: flex;
          justify-content: center;
          align-items: center;
          padding: 20px;
          font-size: 70px;
          color: white;
          line-height: 1;
          font-family: "Lato", sans-serif;
          font-weight: 200;
        }

        .content-text {
          display: flex;
          justify-content: center;
          align-items: center;
          padding: 20px;
          font-size: 70px;
          color: black;
          line-height: 1;
          font-family: Arial;
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

a:active {
  text-decoration: none;
  color: white;
}

#main a:hover {
  text-decoration: none;
  color: black;
}

      </style>

  </head>

  <body>

        <div class='wrapper'>

          <div class='header'>
            <div class='text'> {{ page.title }} </div>
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
                <ul>
                    {% for post in site.posts %}
                        <li>
                          <a href="{{ post.url }}">{{ post.title}}</a>
                        </li>
                    {% endfor %}
                </ul>
            </div>
          </div>

          <div class='footer'>
            <div class='footer-text'> {{ site.title }} | {{ page.title }} </div>
          </div>

        </div>

  </body>

</html>