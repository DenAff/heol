---
title: Cartes
layout: default
permalink: cartes.html
---
<html>

<head>

<style>

body, html {
  height: 30%;
  margin: 0;
}

.bg {
  /* The image used */
  background-image: url('{{ site.baseurl }}/_assets/images/home/travis-grossen.jpg');

  /* Full height */
  height: 50%; 

  /* Center and scale the image nicely */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
}

</style>

</head>

<body>

<!--
  La carte de nos lieux de sorties à Paris
-->

<div class="parent">

    <iframe
        width="90%" height="600px" allowfullscreen
        src="//umap.openstreetmap.fr/fr/map/sortir-a-paris_482924?scale
        Control=true&miniMap=false&scrollWheelZoom=true&zoom
        Control=false&allowEdit=false&moreControl=false&search
        Control=true&tilelayersControl=false&embedControl=true&datalayers
        Control=true&onLoadPanel=none&captionBar=false&fullscreen
        Control=true&locateControl=true&measureControl=false&editinosm
        Control=false">
    </iframe>
        
</div>

    <p style="text-align:center">
        <a id="a1" href="//umap.openstreetmap.fr/fr/map/sortir-a-paris_482924" target="_blank">Voir en plein écran</a>
    </p>

</body>

</html>