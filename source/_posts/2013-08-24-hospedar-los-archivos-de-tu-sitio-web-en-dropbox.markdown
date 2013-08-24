---
layout: post
title: "Hospedar los archivos de tu sitio web en Dropbox"
date: 2013-08-24 10:58
comments: true
categories: [dropbox, octopress, redes]
keywords: dropbox, octopress, wordpress, cdn, networking
description: Tutorial para usar Dropbox como un seudo-CDN
---
Ahora que he dado vida a este blog, estoy intentado **mejorar el rendimiento** del mismo _(si se puede)_ a través de distintas herramientas o arquitecturas de redes disponibles. Se me ocurrió aplicar una especie de [CDN](http://es.wikipedia.org/wiki/Red_de_entrega_de_contenidos), pero para **Octopress**. Si estas buscando algo para Wordpress, existe en la red mucha información al respecto, como el uso de [jsdelivr](http://mvkoen.com/cdn-gratuito-de-jsdelivr-para-wordpress/).
<!--more-->

Actualmente uso [Github](https://github.com) para alojar el blog, entonces ¿porque no usar un **servicio gratuito** como Dropbox para alojar todo lo que no sea HTML? como las imágenes, javascript, css, vídeos y documentos. Con estos pasos creamos una especie de **seudo-CDN** donde el contenido es distribuido a través de distintas redes disponibles _casi siempre_.

**Paso 1.** [habilitar la carpeta pública](https://www.dropbox.com/enable_public_folder) de Dropbox. 

**Paso 2.** subir los archivos necesarios (css, imagenes, javascript) a la carpeta pública.

**Paso 3.** obtener el enlace público del archivo como se muestra en la imagen _(si usas la interfaz web)_.

{% img https://dl.dropboxusercontent.com/u/10635827/cdn/20130824-cdn-dropbox.png %}

Como veras tengo los archivos alojados en una carpeta llamada **cdn** dentro de la carpeta pública, para tener un poco más de organización.

**Paso 4.** por último solo debes hacer referencia en el código al enlace obtenido `https://dl.dropboxusercontent.com/enlace/al/archivo`, en el caso de imágenes y estilos se hace de la siguiente forma.

``` html
<img src="https://dl.dropboxusercontent.com/u/143061433/cdn/0.jpg">
<link rel="stylesheet" type="text/css" href="https://dl.dropboxusercontent.com/u/143061433/cdn/style.css">
```

Para finalizar es importante leer los _términos de uso_, para evitar **saturar** el uso de tu cuenta en **Dropbox** y que te la puedan cancelar. No conozco ningún caso, pero si tu sitio es muy visitado mejor apúntate a algo más profesional como el servicio [Cloudfare](https://www.cloudflare.com/) del cual probablemente hablaré más adelante.

**Y listo!**
