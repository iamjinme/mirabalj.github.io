---
layout: post
title: "Evitar y borrar el archivo libpeerconnection.log que crea Google Chrome"
date: 2013-09-12 10:08
comments: true
categories: [chrome, linux, consola, crunchbang]
keywords: console, chrome, gnu, linux, libpeerconnection, google, debian
description: Truco para evitar archivo fantasma de Google Chrome
---
Hace unos días me percaté de un archivo _fantasma:_ `libpeerconnection.log` que aparece en distintos directorios del disco duro donde tengo instalado Crunchbang, si lo borras vuelve a aparecer sobre todo en el $HOME. Investigando di con el **culpable: Google Chrome**. Acá te dejo la solución.
<!--more-->

Lo primero es abrir la consola _(o terminal)_ del sistema y ejecutar `sudo nano /opt/google/chrome/google-chrome` o usar tu editor favorito: gedit, geany, vi _(sustituyendo a nano)_. Luego nos vamos al final del archivo que estamos editando, donde están las siguientes lineas:

``` bash
export CHROME_VERSION_EXTRA="stable"

# We don't want bug-buddy intercepting our crashes. http://crbug.com/24120
export GNOME_DISABLE_CRASH_DIALOG=SET_BY_GOOGLE_CHROME

exec -a "$0" "$HERE/chrome"  "$@"
```

Antes del comando `exec` escribimos `cd /tmp`, con lo cual Chrome creará en adelante el archivo en el directorio temporal de nuestra distribución. Quedaría algo como esto:

``` bash
export CHROME_VERSION_EXTRA="stable"

# We don't want bug-buddy intercepting our crashes. http://crbug.com/24120
export GNOME_DISABLE_CRASH_DIALOG=SET_BY_GOOGLE_CHROME

cd /tmp
exec -a "$0" "$HERE/chrome"  "$@"
```

Guardas el archivo `Ctrl + O`. Luego si deseas borrar todos estos archivos "fantasmas" en tu disco duro, lo puedes hacer con el siguiente _comando_ en la consola.

``` bash
sudo find -name libpeerconnection.log -exec rm -f {} \;
```

Con esto me pude librar de esta molestia, espero que tu también. **No olvides dejar tus comentarios.**
