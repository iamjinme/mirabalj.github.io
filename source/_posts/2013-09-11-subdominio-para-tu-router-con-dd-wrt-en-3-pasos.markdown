---
layout: post
title: "Subdominio para tu router con DD-WRT en 3 pasos"
date: 2013-09-11 07:30
comments: true
categories: [3-pasos, redes, dd-wrt, wifi]
keywords: networking, dd-wrt, freedns, router, wifi
description: Configurando FreeDNS para configurar subdominio para el router
---
_¿Tienes tu propio dominio en Internet y un router en casa?_ **Este tutorial es para ti**. Más de una vez he querido conectarme al router (o a un computador) en casa desde la oficina; con la molestia de tener que aprenderme el **número mágico** ya que mi proveedor de servicios no ofrece direcciones IP fijas y ademas que cambia estas constantemente, por lo cual es necesario usar algún servicio [DDNS](http://es.wikipedia.org/wiki/DNS_din%C3%A1mico) y consecuentemente tener otro equipo encendido en casa que lo ejecute... **hasta hoy**
<!--more-->

[DD-WRT](http://es.wikipedia.org/wiki/DD-WRT) es un firmware **libre** para diversos ruteadores inalámbricos, necesitas tenerlo instalado para seguir este tutorial, aunque [Tomato](http://www.polarcloud.com/tomato) puede servir. También debes tener un dominio configurado con una cuenta en [FreeDNS](http://freedns.afraid.org/), sin embargo DD-WRT permite configurar otros servicios como DynDNS, ZoneEdit, NO-IP.com entre otros.

**Los pasos a seguir son:**

1. Crear un subdominio en FreeDNS
2. Suministrar los datos de conexión al router
3. Guardar/Reiniciar el router


### Creando un subdominio en FreeDNS

Entramos con nuestra cuenta en FreeDNS, nos vamos a la sección **Domains**, seleccionamos el enlace `[ Manage ]` del dominio donde queremos trabajar y finalmente el enlace `[ add ]`. Escoges un subdominio Tipo A. Escribe el nombre del subdominio que desees en la sección **Subdomain**, por ejemplo: _router_, indicas la dirección IP actual del router en **Destination**, si no la sabes [acá](http://whatismyipaddress.com/) la encontraras con el servicio **What is my IP Address**. Finalmente presionas el botón **Save!**.

{% img https://dl.dropboxusercontent.com/u/10635827/cdn/20130911-free-dns-afraid-sub-domain.png %}


### Configurando el router

Nos vamos a la página principal de configuración del router, _generalmente en 192.168.1.1_; en la sección **Setup** y la pestaña **DDNS** escogemos el _DDNS Service_ que vamos a configurar, que para nuestro caso es `freedns.afraid.org` junto con las credenciales del mismo, así mismo le indicamos el **hostname** que es el nombre del subdominio creado anteriormente. Por último le indicamos el intervalo de actualización en días; si tu ISP cambia constantemente la dirección IP, te sugiero quitar el valor por defecto y colocar **1 (uno)**.

{% img https://dl.dropboxusercontent.com/u/10635827/cdn/20130911-dd-wrt-setup-ddns.png %}


### Guardar/Reiniciar

En la parte inferior de la página está el botón **Save**, lo presionas y solo queda esperar unos segundos mientras el router se conecta al servicio y actualiza la información tal como se muestra en la imagen superior. _Excelente!_ con esto solo tendras que ingresar el nombre del subdominio configurado en el navegador y desde cualquier lugar podras acceder a tu router remotamente. Espero les haya gustado este tutorial en redes y si tienes alguna duda o sugerencia, deja tus comentarios.

**Happy Hacking!**
