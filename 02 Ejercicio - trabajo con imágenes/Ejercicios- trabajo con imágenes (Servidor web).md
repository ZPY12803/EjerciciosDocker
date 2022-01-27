---
title: Ejercicios Docker
author: Cristina Herrero Rodríguez

---

# Ejercicios Docker

> Trabajo realizado por: Cristina Herrero Rodríguez

[TOC]

## Ejercicio - trabajo con imágenes

### Servidor web

​	*Arrancar contenedor `php:7.4-apache` con nombre `web` accesible en el puerto 8000*

```bash
docker run -d -p 8000:80 --name web -v /home/christie/datos_php:/var/www/html:ro php:7.4-apache
docker ps -a
```

![image-20220126161157491](Ejercicios-%20trabajo%20con%20im%C3%A1genes%20(Servidor%20web).assets/image-20220126161157491.png)

​	*Fichero `index.html`en `/var/www/html` y visualización en el navegador*

![image-20220126161310597](Ejercicios-%20trabajo%20con%20im%C3%A1genes%20(Servidor%20web).assets/image-20220126161310597.png)

​	*Contenido del archivo `mes.php`*

![image-20220127170011454](Ejercicios-%20trabajo%20con%20im%C3%A1genes%20(Servidor%20web).assets/image-20220127170011454.png)

​	*Visualización del nombre del mes actual del archivo `mes.php` a través del navegador*

![image-20220127170047823](Ejercicios-%20trabajo%20con%20im%C3%A1genes%20(Servidor%20web).assets/image-20220127170047823.png)

​	*Eliminación del contenedor*

```bash
docker rm -f web
docker ps -a
```

![image-20220127170235209](Ejercicios-%20trabajo%20con%20im%C3%A1genes%20(Servidor%20web).assets/image-20220127170235209.png)
