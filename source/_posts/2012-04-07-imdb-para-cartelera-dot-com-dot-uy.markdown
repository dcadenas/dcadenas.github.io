---
layout: post
title: "IMDB para cartelera.com.uy"
date: 2012-04-07 03:21
comments: true
categories:
  javascript
---
A ver si me sale bien mi primer post en español sin detalles técnicos, para el bien de la comunidad cinéfila uruguaya.

Uso bastante [cartelera.com.uy](http://www2.cartelera.com.uy/apeliculafunciones.aspx?,,PELICULAS,FILM,0,3) cada vez que quiero ir al cine, tienen un buen resumen de lo que hay en todos los cines y se puede ver un listado rápido en una sola página sin dar muchas vueltas.

Lo que nunca me gustó del sitio es que nunca estoy de acuerdo con los ratings de los usuarios y en general me siento más identificado con las evaluaciones que da [IMDB](http://www.imdb.com/) y [Rotten Tomatoes](http://www.rottentomatoes.com/). Lo que hacía siempre era ver que película me parecía buena y luego me metía en [IMDB](http://www.imdb.com/) para verificar que no fuera un desastre y le hubiera errado como a las peras (o tomates mejor dicho). La verdad que no poder hacerlo de una sola mirada en el listado de películas era bastante engorroso.

Así que me cansé de tanto trabajo y me hice un [bookmarklet](http://es.wikipedia.org/wiki/Bookmarklet) que permite agregar un cuadrito al lado de cada película con esos dos ratings que me interesan. Ojo, no siempre funciona bien, en [cartelera.com.uy](http://www2.cartelera.com.uy/apeliculafunciones.aspx?,,PELICULAS,FILM,0,3) ponen los nombres de las películas en español y eso hace que la búsqueda en [IMDB](http://www.imdb.com/) a veces le erre feo. Igual me parece que en general los resultados son útiles.

Para instalarlo simplemente hay que arrastrar este link [[[<a href="javascript:(function(){var s = document.createElement('script');s.src = 'https://raw.github.com/gist/2325686/gistfile1.js';document.body.appendChild(s);})();">Poner ratings IMDB</a>]]] a la barra de favoritos (bookmarks si está en inglés).

Y listo! Ahora cada vez que vayan al listado por películas o por salas de [cartelera.com.uy](http://www2.cartelera.com.uy/apeliculafunciones.aspx?,,PELICULAS,FILM,0,3) hagan click en el link que arrastraron y de a poco van a ir apareciendo los ratings de [IMDB](http://www.imdb.com/) y de [Rotten Tomatoes](http://www.rottentomatoes.com/) en un cuadro amarillo bien feo que van a notar enseguida.

Que les sea útil!

NOTA TÉCNICA: El bookmarklet levanta este [gist](https://gist.github.com/2325686). Aportes bienvenidos.
