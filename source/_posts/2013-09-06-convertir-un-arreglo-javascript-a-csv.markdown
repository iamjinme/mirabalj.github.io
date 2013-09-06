---
layout: post
title: "Convertir un arreglo Javascript a CSV"
date: 2013-09-06 09:13
comments: true
categories: [javascript, array, trucos, csv]
keywords: javascript, array, tricks, CSV
description: Truco para convertir un arreglo a formato CSV
---
Los archivos [CSV](http://es.wikipedia.org/wiki/CSV) básicamente poseen un **formato abierto** que permite de manera sencilla el intercambio de información organizado tabularmente. Tal como se muestra en el ejemplo.

``` text
987,juan,87345,10 norte 342
876,pedro,43649,8 oriente 342
123,jorge,03342,av. libertad 23
```
A continuación explico como **convertir los datos de un arreglo** a este formato.
<!--more-->

Primeramente mostramos la información de un arreglo usando la función `valueOf()`

``` javascript
var frutas = ['manzana', 'duraznos', 'naranjas', 'mangos'];
  
var str = frutas.valueOf();
  
//print str: manzana,duraznos,naranjas,mangos
```
Como vemos el método convierte un arreglo javascript a un _string_ usando la coma como separador, suficiente para compartirlo en un archivo CSV.

Ahora bien, si queremos usar el _pipe_ **(|)** como separador, valido para el CSV; usaremos el método `join()` 

``` javascript
var frutas = ['manzana', 'duraznos', 'naranjas', 'mangos'];
  
var str = frutas.join("|");
  
//print str: manzana|duraznos|naranjas|mangos
```
**¿Interesante, no?** espero en el futuro ir publicando más trucos en el blog, _siempre necesarios._ Deja tus comentarios si tienes algún _snippet_ en particular.
