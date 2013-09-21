---
layout: post
title: "Seguridad en el cliente Web de OpenERP"
date: 2013-09-21 08:39
comments: true
categories: [openerp, web, seguridad]
keywords: openerp, security, sfd, web client
description: Recomendaciones para asegurar el cliente web de OpenERP
---
Manejar la información de una empresa usando un sistema de planificación de recursos _(ERP)_ a través de un cliente Web es una excelente opción para cualquier organización moderna, sin embargo asegurar los datos debería ser una **prioridad**. Si provees [OpenERP](https://www.openerp.com/) como solución tecnológica en producción, te sugiero tomar en cuenta las siguientes recomendaciones.
<!--more-->

### Usa HTTPS

Siempre puedes usar XML-RPC a través de HTTPS para cifrar todas las comunicaciones. Por defecto OpenERP funciona simplemente con HTTP. En detrimento del rendimiento deberías activar esta opción.

### A través de una VPN

Es deseable usar OpenERP sobre una [red privada virtual](http://www.cwv.com.ve/?p=15259). Esto eliminará a curiosos foráneos que quieran obtener acceso al sistema. Esto se puede hacer mediante la configuración del servidor Apache para aceptar sólo conexiones de una dirección IP específica de la oficina.

### SSH como alternativa

Si no estas usando VPN o HTTPS, otra opción es crear un _túnel_ SSH.

### Instalar el modulo base_crypt

Por defecto las contraseñas y usuarios son guardados en _texto plano_. Es muy importante almacenarlos en forma cifrada. Instala el modulo base_crypt para lograrlo. 

### Usa Active Directory/LDAP

Para asegurar aún mas el sistema, es aconsejable utilizar Active Directory/LDAP; hay un modulo existente que permite hacer esto.

### Incluye un archivo Robot.txt

Para terminar de blindar tu sistema crea un archivo `Robot.txt` en la raíz del cliente Web para no dejar que Google indexe tu página de inicio.  

Recuerda que no es una solución definitiva, es un trabajo en progreso donde te invito a dejar tus comentarios y sugerencias. Ah! y **Feliz día del Software Libre**.

Esta es una _traducción libre_ del [artículo](http://pragtechblog.blogspot.com/2012/04/securing-openerp-web-client-security.html) de Pragmatic: Securing OpenERP Web Client (Security OpenERP).
