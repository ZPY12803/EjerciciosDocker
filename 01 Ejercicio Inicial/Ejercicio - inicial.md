---
title: Ejercicios Docker
author: Cristina Herrero Rodríguez
---

# Ejercicios Docker

> Trabajo realizado por: Cristina Herrero Rodríguez

[TOC]

### Ejercicio inicial

​	*Creación del contenedor funcionando*

```bash
docker run -d --name servidor_web -p 8181:80 nginx
docker ps -a
```

![image-20220113173820494](Docker.assets/image-20220113173820494.png)

​	*Acceso al servidor web usando un navegador web*

![image-20220113173706615](Docker.assets/image-20220113173706615.png)

​	*Imágenes de registro local*

```bash
docker ps -a
```

![image-20220113165601460](Docker.assets/image-20220113165601460.png)

​	*Eliminación del contenedor*

```bash
docker stop servidor_web
docker rm servidor_web
```

![image-20220113174043439](Docker.assets/image-20220113174043439.png)
