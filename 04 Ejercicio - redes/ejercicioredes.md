# EJERCICIO REDES

> Tarea realizada!

[TOC]

## EERCICIO REDES

#### Apartado 1

 1. Crea una red bridge `redbd`

    ```bash
    docker network create redbd
    docker network inspect redbd
    ```

    

​	![image-20220127164428615](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220127164428615.png)



#### Apartado 2

​	Crea un contenedor con una imagen de `mariaDB` que estará en la red `redbd` . Este contenedor se ejecutará en segundo plano, y será accesible a través del puerto 3306. (Es necesario definir la contraseña del usuario `root` y un volumen de datos persistente)

```bash
docker run -d --name contenedormariadb --network redbd -e MYSQL_ROOT_PASSWORD=root -p 8000:3306 mariadb 

```

![image-20220127171300273](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220127171300273.png)

#### Apartado 3 y 4

​	 Crear un contenedor con `Adminer` que se pueda conectar al contenedor de la BD. Comprobar que el contenedor `Adminer` puede conectar con el contenedor `mysql` abriendo un navegador web y accediendo a la URL: http://localhost:8080

```bash
docker run -d --name contenedoradminer --network redbd -p 8080:8080  adminer 
```

![image-20220127175000862](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220127175000862.png)



![image-20220127175344378](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220127175344378.png)

```bash
docker exec -it contenedormariadb bash
mysql -u root -p
show databases;
```

![image-20220127180349160](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220127180349160.png)

```bash
docker rm -f $(docker ps -aq)
```

![image-20220127180745983](C:\Users\Sergio\AppData\Roaming\Typora\typora-user-images\image-20220127180745983.png)
