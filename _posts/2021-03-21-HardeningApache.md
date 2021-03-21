---
title: Hardening de Apache
layout: post
author: Patrick Campillo
excerpt_separator: <!--more-->
typora-copy-images-to: ../images/
typora-root-url: ../
---

## Configuración inicial

Para comenzar a añadir la seguridad a nuestro servidor **Apache**, desactivaremos el módulo, que viene activado por defecto, que crea un índice del contenido de una carpeta si esta no posee un fichero `index.html` o `index.php`. Este módulo se llama `mod_autoindex`, y lo encontraremos con el nombre `autoindex.load` en la carpeta `mods-enabled`. Tras esto deberemos reiniciar **Apache**.

![](/images/hardeningapache/1.PNG)



Si lo comprobamos, veremos que si realizamos la búsqueda de la carpeta `public_html`, no la encontrará.

![](/images/hardeningapache/1-1.PNG)

Sin embargo, si buscamos la página `login.php`, que se encuentra dentro de la carpeta si la mostrará.

![](/images/hardeningapache/1-2.PNG)





## Cabecera del Servidor

**Apache**, por defecto, muestra en la cabecera `Server` del navegador, su versión y el sistema operativo al que pertenece.

![](/images/hardeningapache/2.PNG)



Para solucionar esto deberemos añadir las líneas "`ServerTokens ProductOnly`" y "`ServerSignature Off`" al fichero de configuración de **Apache**, `apache2.conf`.

![](/images/hardeningapache/3.PNG)



Y como podremos observar al reiniciar el servicio, ya solo mostrará que se trata de un **Apache**.

![](/images/hardeningapache/3-1.PNG)







## Web Application Firewall (WAF) con OWASP

Para añadir más seguridad a nuestro servidor, utilizaremos dos reglas de seguridad que tiene la configuración **OWASP**. Para esto, deberemos instalar el paquete `libapache2-mod-security2`. El cual, al configurarlo e instalarlo, nos aplicará dos reglas para fortificar más nuestro servidor.

![](/images/hardeningapache/4.PNG)



Una vez instalado, deberemos modificar el valor de "`SecRuleEngine`" a "`On`", del archivo de configuración de `modsecurity`. Ubicado en `/etc/modsecurity`.

![](/images/hardeningapache/5.PNG)



Tras esto reiniciamos el servidor y habremos aplicado las reglas.







## Dockerfile

Por último, crearemos una imagen `Dockerfile`, que realice todos los pasos anteriores al realizar el "build" de la imagen. Por eso, algunas de las capturas que he ido mostrando pertenecían a un `Dockerfile`. El Dockerfile final, quedaría tal que así:



![](/images/hardeningapache/6.PNG)

![](/images/hardeningapache/6-1.PNG)



Además podéis descargarlo y probarlo desde el siguiente [link](https://github.com/patrickcampillo/hardeningapache).