---
layout: post
title: "Instalando y configurando Octopress"
date: 2013-08-19 11:07
comments: true
categories: [octopress, ruby, crunchbang, blog]
description: Tutorial sobre la instalación y configuración de Octopress
keywords: octopress, debian, git, ruby, blog
---
Luego de años sin blog, debido a la perdida de [MatandoTigres](http://matandotigres.wordpress.com) he decidido retornar con un espacio renovado.
Esta semana, intentando abordar excelentes lenguajes como Ruby y _auto-obligado_ a usar Git he decidido montar este nuevo Blog en [Github](https://github.com/) usando una excelente herramienta desarrollada en Software Libre llamada [Octopress](http://octopress.org/).
Que mejor manera de comenzar explicando como instalar y configurar Octopress, un _framework de blogging para hackers_.
**Manos a la obra entonces!**
<!--more-->

## Instalación

Aclaro que todo el procedimiento lo realicé con la distribución [Crunchbang](http://crunchbang.org/) por lo cual debería funcionar con cualquiera basada en **Debian**.
Simplemente debemos usar la consola _(terminal)_ para ejecutar ciertos comandos.

Lo primero es instalar Git.
``` bash
$ sudo aptitude install git
```

También debemos tener instalado Ruby, para ello usaremos **RVM (Ruby Version Manager)** que me parece el más completo y a _prueba-de-fallos_, lo bajamos como sigue.
``` bash
$ curl -L https://get.rvm.io | bash -s stable --ruby
```

Luego instalaremos específicamente la **versión 1.9.3** de Ruby, que es la que _exige_ Octopress.
``` bash
$ rvm install 1.9.3
$ rvm use 1.9.3
$ rvm rubygems latest
```
**Ejecuta** `ruby --version` para asegurarte que estas usando la versión Ruby 1.9.3.

Lo siguiente es hacer un _fork_ de Octopress en nuestro computador.
``` bash
$ git clone git://github.com/imathis/octopress.git octopress
$ cd octopress
```

Para finalizar la instalación instalamos las dependencias
``` bash
$ gem install bundler
$ rbenv rehash
$ bundle install
```
E instalamos el tema por defecto. **Sí,** Octopress tiene variados temas para usar.

``` bash
$ rake install
```


## Configuración
Aunque no lo crean, llegamos a la **parte fácil**, configurar Octopress solo requiere editar el archivo `_config.yml` que se encuentra en la raíz del directorio del framework.
Acá ud puede cambiar el `url`, `title`, `subtitle`, `permalink`, `twitter_account` e incluso comentarios vía [disqus](http://disqus.com/) provista por `disqus_short_name`.
Les dejo una breve descripción (en español) de algunas variables.
``` bash
url:                # Dirección URL para reescritura de RSS, etc
title:              # Usado en la cabecera y las etiquetas de titulo
subtitle:           # Descripción usada en la cabecera del sitio
author:             # Tu nombre, para RSS, Copyright, Metadata
simple_search:      # Buscador utilizado para realizar las busquedas (claro!)
description:        # Una meta-descripción de tu blog, para indexar el sitio
date_format:        # Formato de fecha usado por la función strftime de Ruby
subscribe_rss:      # Dirección URL para los feeds del blog, por defecto usa /atom.xml
subscribe_email:    # Dirección URL para suscribir por correo electrónico (requiere el servicio)
category_feeds:     # Habilita los feeds RSS por categoria (por defecto está desactivado)
email:              # Correo electrónico para los feeds del RSS, si lo deseas.
```
**Eso es todo amigos.** Para finalizar solo me queda indicarles que existen muchos _plugins_ de [terceros](http://octopress.org/docs/blogging/plugins/) para usar con este poderoso framework, solo queda instalar y probar.
Seguramente en próximos artículos estaré escribiendo sobre éste y otros temas relacionados. Espero por lo pronto que te haya sido útil el breve tutorial y **comiences con tu blog**!
