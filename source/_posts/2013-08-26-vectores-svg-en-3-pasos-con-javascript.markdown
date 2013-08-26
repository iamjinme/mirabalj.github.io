---
layout: post
title: "Realizando vectores SVG con Javascript en 3 pasos"
date: 2013-08-26 08:42
comments: true
categories: [svg, javascript, 3 pasos, html]
keywords: vectores, svg, javascript, 3 pasos, web design, Raphaël
description: Tutorial para realizar gráficos SVG con Raphaël en Javascript
---
Algo que parecía imposible hace años era el uso de gráficos vectoriales o [SVG](http://es.wikipedia.org/wiki/Scalable_Vector_Graphics) en el navegador. **Hoy la historia es otra**, sin embargo realizarlos pudiera resultar difícil al principio, **hasta ahora**.

[Raphaël](http://raphaeljs.com/) es _una joya_, una pequeña librería en Javascript que simplifica trabajar con gráficos vectoriales en la web. Si deseas crear tu propio gráfico de barras, cortar una imagen o rotar un _widget_ puedes hacerlo simple y fácilmente con esta librería. Y te lo explico en **tres pasos**.

1. Bájate el pequeño archivo de **31 Kb** [acá](http://github.com/DmitryBaranovskiy/raphael/raw/master/raphael-min.js)
2. Incluye el _script_ `raphael-min.js` en cualquier parte de tu archivo HTML
3. Finalmente incluyes el código en javascript para realizar tu gráfico vectorial, aquí crearemos un simple circulo que quedaria como sigue.

``` javascript
<script src="raphael-min.js" type="text/javascript" charset="utf-8"></script>
<script type="text/javascript" charset="utf-8">

// Crea el canvas canvas (contenedor) de tamaño 320 × 200 en las coordenadas 10, 50
var paper = Raphael(10, 50, 320, 200);

// Crea un circulo en las coordenadas x = 50, y = 40, con radio 10
var circle = paper.circle(50, 40, 10);

// Configura el atributo de relleno del circulo a rojo (#f00)
circle.attr("fill", "#f00");

// Asignamos el atributo exterior del circulo a blanco
circle.attr("stroke", "#fff");

</script>
```

**Pruebalo.** Como veras es un proceso muy sencillo para crear gráficos SVG, claro está que tiene infinidad de elementos que puedes realizar, todos [documentados](http://raphaeljs.com/reference.html) y hasta con variados **ejemplos** que puedes utilizar.

Para finalizar les indico que esta útil librería soporta Firefox 3.0+, Safari 3.0+, Chrome 5.0+, Opera 9.5+ y hasta Internet Explorer 6.0+

**La imaginación es el limite!**
