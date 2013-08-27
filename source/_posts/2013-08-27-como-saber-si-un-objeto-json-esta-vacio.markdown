---
layout: post
title: "Cómo saber si un objeto JSON está vacío"
date: 2013-08-27 08:13
comments: true
categories: [json, javascript, programacion, jquery]
keywords: development, json, empty, object, javascript, jquery
description: Código para saber si un objeto JSON esta vacío
---
Hace unos días leía un _tuit_ con la pregunta que inspira este artículo, no especificaba el lenguaje de programación ni nada, así que me pareció ideal **agregar todos** los posibles lenguajes para resolver este problema tan común. Puedes obtener la solución o colaborar con otros dando la tuya en los comentarios, por ahora les dejo la de **Javascript**.
<!--more-->

## Javascript
Puedes hacer una prueba creando una variable `var objeto = {}` y llamar a la función `isEmptyJSON(objeto)`

``` javascript
	function isEmptyJSON(obj) {
		for(var i in obj) { return false; }
		return true;
	}
```

### jQuery
Si trabajas con [jQuery](http://jquery.com/), esta librería tiene la función `jQuery.isEmptyObject(objeto)` que puedes utilizar.

Recuerda que si tienes la solución en algún lenguaje de tu interés o la necesitas, **deja tus comentarios**.
