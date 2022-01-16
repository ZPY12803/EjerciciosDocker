---
Título: Ejercicios Docker
Autores: Cristina Herrero Rodríguez, Carolina Medina Llorente, Sergio Fernández Peñil
---

# Ejercicios Docker

> Tarea realizada por Cristina Herrero Rodríguez, Carolina Medina Llorente y Sergio Fernández Peñil

[TOC]





### 3. Ejercicio Almacenamiento

##### Bind mount para compartir datos 

1. Crea una carpeta llamada `saludo` y dentro de ella crea un fichero llamado `index.html` con el siguiente contenido (Deberás sustituir ese XXXXX por tu nombre.): 

   ```html
   <h1>HOLA SOY XXXXX</h1>
   ```

2. Una vez hecho esto arrancar dos contenedores basados en la imagen php:7.4-apache que hagan un bind mount de la carpeta `saludo` en la carpeta `/var/www/html` del contenedor. Uno de ellos vamos a acceder con el puerto 8181 y el otro con el 8282. Y su nombres serán `c1` y `c2` . 

   ```bash
   docker pull php:7.4-apache
   docker run -d -p 8181:80 -v /home/carol/saludo:/var/www/html --name c1 php:7.4-apache
   docker run -d -p 8282:80 -v /home/carol/saludo:/var/www/html --name c2 php:7.4-apache
   ```

   ![image-20220116172958032](Ejercicio%20almacenamiento.assets/image-20220116172958032.png)

   ![image-20220116173125254](Ejercicio%20almacenamiento.assets/image-20220116173125254.png)

   ![image-20220116173242423](Ejercicio%20almacenamiento.assets/image-20220116173242423.png)

   ![image-20220116173308502](Ejercicio%20almacenamiento.assets/image-20220116173308502.png)

3. Modifica el contenido del fichero `~/saludo/index.html`. 

   ![image-20220116173654882](Ejercicio%20almacenamiento.assets/image-20220116173654882.png)

4. Comprueba que puedes seguir accediendo a los contenedores, sin necesidad de reiniciarlos.

   ![image-20220116173514022](Ejercicio%20almacenamiento.assets/image-20220116173514022.png)

   ![image-20220116173610209](Ejercicio%20almacenamiento.assets/image-20220116173610209.png)

   

   

   

5. Borra los contenedores utilizados.

   ```bash
   docker stop c1
   docker stop c2
   docker rm c1
   docker rm c2
   ```

   ![image-20220116173957515](Ejercicio%20almacenamiento.assets/image-20220116173957515.png)

