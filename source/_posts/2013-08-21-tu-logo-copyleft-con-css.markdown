---
layout: post
title: "Tu logo CopyLeft con CSS"
date: 2013-08-21 09:50
comments: true
categories: [css, copyleft, diseño-web, html] 
keywords: web design, css, html, copyleft
description: Snippet para crear un logo Copyleft con CSS
---
La mayoría de las cosas que comparto son de dominio público, y si hay algo que detesto es el asunto del Copyright, más aún cuando no <del>tengo</del> tenia un logo para mostrar el CopyLeft.
Pensado en CSS3 se me ocurrió crear este _pedazo_ de código para crear el CopyLeft en HTML5 **sin usar imágenes** que ahora les comparto. Puro código libre.
<!--more-->

## HTML5

Lo primero es tener el texto de tu CopyLeft, que por ahora será el carácter **©**, o sea el del Copyright, que colocaremos en un `span` e identificaremos con una clase.

``` html
<span class="copyleft-symbol">©</span>
```

## CSS3

A continuación agregamos a nuestra hoja de estilos el nombre de la clase asignada al `span` y el código que transformará el carácter a CopyLeft.

``` css
.copyleft-symbol {
	transform: rotate(180deg);
	-webkit-transform: rotate(180deg);
	-moz-transform: rotate(180deg);
	filter: progid:DXImageTransform.Microsoft.BasicImage(rotation=2);
}
```
Como verán insertamos código para que sea compatible con todos los navegadores, incluso IE que utiliza un **filtro** especial.
Si quieren ver como funciona, vayan el final de la página y se mostrará el logo CopyLeft activado. Espero les haya gustado este _snippet_.
