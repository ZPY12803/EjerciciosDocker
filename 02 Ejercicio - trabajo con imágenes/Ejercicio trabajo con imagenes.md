---
Título: Ejercicios Docker
Autores: Cristina Herrero Rodríguez, Carolina Medina Llorente, Sergio Fernández Peñil
---

# Ejercicios Docker

> Tarea realizada por  Sergio Fernández Peñil

[TOC]





### 2. Ejercicio - trabajo con imágenes 

### Servidor de base de datos

Arrancar un contenedor que se llame bbdd y que ejecute una instancia de la imagen mariadb para que sea accesible desde el puerto 3336. 

Antes de arrancarlo visitar la página del contenedor en Docker Hub y establecer las variables de entorno necesarias para que: 

- La contraseña de root sea root . 
- Crear una base de datos automáticamente al arrancar que se llame prueba . 
- Crear el usuario invitado con la contraseña invitado .

```bash
docker run --name bbdd -p 3336:3306 -v /home/usuario/bbdd:/var/lib/mysql \
--env MARIADB_USER=invitado --env MARIADB_PASSWORD=invitado \
--env MARIADB_ROOT_PASSWORD=root --env MARIADB_DATABASE=prueba \
-d mariadb
```

![image(1)](Ejercicio%20trabajo%20con%20imagenes.assets/image(1).png)

![image(2)](Ejercicio%20trabajo%20con%20imagenes.assets/image(2).png)





Se comprueba que no se puede borrar la imagen mariadb mientras el contenedor bbdd está creado:

![image(3)](Ejercicio%20trabajo%20con%20imagenes.assets/image(3).png)
