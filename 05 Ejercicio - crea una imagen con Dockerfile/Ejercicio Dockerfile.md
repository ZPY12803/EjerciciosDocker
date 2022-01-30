---
Título: Ejercicios Docker
Autores: Cristina Herrero Rodríguez, Carolina Medina Llorente, Sergio Fernández Peñil
---

# Ejercicios Docker

> Tarea realizada por Cristina Herrero Rodríguez, Carolina Medina Llorente y Sergio Fernández Peñil

[TOC]





### 5. Ejercicio Dockerfile

Para la realización de este ejercicio es necesario tener una cuenta en Docker Hub.

##### Crear una imagen con un servidor web que sirva un sitio web

- Basar la imagen en `nginx` o `apache` 
- Desplegar una plantilla, o un trabajo de clase, que tenga, al menos, un `index.html` y una carpeta para estilos, imágenes, etc. 

Deberás entregar los siguientes pantallazos y los comandos empleados para resolver cada apartado: 

1. Pantallazo/bloque de código con el Dockerfile 

   ```dockerfile
   FROM nginx
   ADD public_html /usr/share/nginx/html
   RUN chown -R nginx /usr/share/nginx/html
   EXPOSE 80
   ```

2. Pantallazo donde se vea el comando que crea la nueva imagen. 

   ```bash
   docker build -t zpy12803/retodiw_nginx .
   docker run -d -p 8080:80 --name prueba zpy12803/retodiw_nginx
   ```

   ![IMAGE-~2](Ejercicio%20Dockerfile.assets/IMAGE-2.PNG)

3. Pantallazo donde se vea la imagen subida a tu cuenta de Docker Hub. 

   ![IMAGE-~3](Ejercicio%20Dockerfile.assets/IMAGE-3.PNG)

   ![IMAGE-~4](Ejercicio%20Dockerfile.assets/IMAGE-4.PNG)

4. Pantallazo donde se vea la bajada de la imagen - por parte de otra persona del grupo - y la creación de un contenedor. 

   ![IMAGE-5](Ejercicio%20Dockerfile.assets/IMAGE-5.png)

   ![IMAGE-6](Ejercicio%20Dockerfile.assets/IMAGE-6.png)

   

5. Pantallazo donde se ve el acceso al navegador con el sitio servido

   ![IMAGE-~1](Ejercicio%20Dockerfile.assets/IMAGE-1.PNG)

