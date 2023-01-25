## José Antonio Mora Cairós

## 2º ASIR

# 1. Instalación.

1. Primeramente, instalaremos docker en nuestra máquina de OpenSuse.

<img src="./img/1.1.2.png">

2. Iniciación 
+ Iniciaremos el servidor. 
+ Ejecutamos el `enable` para que se inicie cada vez que encendemos la máquina.
+ Consultamos el estado del `ip_forward` que debe estar en `1`.

<img src="./img/1.1.3.png">

# 1.2 Primera Prueba.

1. Entramos como super usuario.

+ Ejecutamos `docker version` para saber que versión tiene:

<img src="./img/1.2.1.png">

+ Ejecutamos el siguiente comando para descargar una imagen.

<img src="./img/1.2.2.png">

+ Ejecutamos para ver la nueva imagen que tenemos y vemos que tenemos un contenedor en estado `Exited`.

<img src="./img/1.2.3.png">


# 2. Creación manual de nuestra imagen y contenedor.

1. Buscamos el repositorio de Docker Hub con la etiqueta de debian.

<img src="./img/2.1.1.png">

2. Descargamos una imagen en local.

<img src="./img/2.1.2.png">

3. Comprobamos que se ha descargado la imagen.

<img src="./img/2.1.3.png">

4. Creamos el contenedor `app1debian`.

<img src="./img/2.1.4.png">

# 2.1 Personalizar el contenedor.

1. Creamos el contenedor y lo ejecutamos.

2. Comprobamos que estamos en `Debian` y miramos las actualizaciones.

<img src="./img/2.2.1.png">

3. Ya dentro del contenedor, ejecutamos la instalación de nginx.

<img src="./img/2.2.2.png">

4. Instalamos `nano`.

<img src="./img/2.2.3.png">

5. Configuramos un fichero de html. Con el nombre `holamundo1.html`. En la ruta `/var/www/html/holamundo1.html`.

<img src="./img/2.2.4.png">

6. Creo un script en `/root/server.sh` con el siguiente contenido:

<img src="./img/2.2.5.png">

7. Creo el fichero, y seguidamente le doy permisos.

<img src="./img/2.2.6.png">

# 2.2 Crear una imagen a partir del contenedor.

1. Creamos una nueva imagen que se llamara `mora/nginx1`. Y muestro las imágenes que tengo. 

<img src="./img/2.3.2.png">

2. Ahora paro el contenedor y lo elimino.

<img src="./img/2.3.3.png">

# 3. Crear contenedor a partir de nuestra nueva imagen.

# 3.1 Crear contenedor con Nginx.

1. Iniciamos el contenedor a partir de la imagen anterior.

<img src="./img/3.1.1.png">

# 3.2 Comprobaciones.

1. Abrimos una nueva terminal, ejecutamos el siguiente comando para que nos muestren los contenedores en ejecución.

<img src="./img/3.2.1.png">

2. Abrimos un navegador y ponemos la ip y el puerto que nos aparecía en la captura anterior, y confirmamos que entramos a las bases de NGINX.

<img src="./img/3.2.2.png">

3. Entro con la misma ip, pero acompañado del html que hicimos anteriormente, y confirmamos que se ve y funciona bien.

<img src="./img/3.2.3.png">

4. Paramos el contenedor y lo eliminamos.

<img src="./img/3.2.4.png">

# 3.3 Migrar la imagen a otra máquina. 





# 4. Dockerfile.

1. Creamos el directorio siguinte `/home/mora/docker04local` y dentro ponemos un html, para ejecutar más adelante.

<img src="./img/4.1.1.png">

+ Visualizamos el contenido:

<img src="./img/4.1.2.png">

2. En el mismo directorio creamos un `Dockerfile` con el siguiente contenido:

<img src="./img/4.1.3.png">

# 4.1 Crear imagenes a partir del Dockerfile.

1. Entramos al directorio que creamos anteriormente, y ejecutamos el siguient comando.

<img src="./img/4.2.1.png">

2. Ejecutamos un `docker images` para ver las imagenes que tenemeos.

<img src="./img/4.2.2.png">

# 4.2 Crear contenedor y comprobar.

1. Ejecutamos en la terminal el siguiente comando. Se nos quedará como bloqueado sin avanzar, pero tenemos que abrir otra terminal y seguir. 

<img src="./img/4.3.1.png">

2. Ejecutamos un `docker ps` para comprobar que el contenedor está en ejecución.

<img src="./img/4.3.2.png">

3. Entramos en un navegador web y entramos como `localhost` con el puerto `8082`.

<img src="./img/4.3.3.png">

4. Entramos en un navegador web y entramos como `localhost` con el puerto `8082` y añadimos `/holamundo2.html`.

<img src="./img/4.3.4.png">

# 4.3 Usar imágenes ya creadas.

1. Creamos el directorio `docker04web` y creamos el fichero `holamundo3.html` lo vemos:

<img src="./img/4.4.1.png">

2. Creamos el fichero `Dockerfile` y lo vemos:

<img src="./img/4.4.2.png">

3. Creamos la imagen `mora/nginx3`.

<img src="./img/4.4.3.png">

4. Creamos el contenedor. 

<img src="./img/4.4.4.png">

5. Desde un navegador web, ponemos la ip y el puerto que pusimos anteriormente:

<img src="./img/4.4.5.png">

# 5. Docker Hub.

1. Creamos un contenedor más. Creamos una carpeta en `/home/mora/docker04push`. Hacemos un ficher `.sh` y lo vemos. 

<img src="./img/5.1.1.png">

2. Visualizamos el fichero que acabamos de crear. 

<img src="./img/5.1.2.png">

3. Creamos la imagen apartir del `Dockerfile` creado anteriormente. 

<img src="./img/5.1.3.png">

4. Probamos a ejecutar el docker que acabamos de crear, y funciona correctamente, con el siguiente comando.

<img src="./img/5.1.4.png">

# 5.1 Subir la imagen a Docker Hub.

1. Me registro previamente en `Docker Hub` por internet, y una vez creada la cuenta accedo. 

<img src="./img/5.2.1.png">

2. Etiquetamos la imagen con `version1`. 

<img src="./img/5.2.2.png">

3. Ahora subimos la imagen que acabamos de crear a los repositorios de Docker.

<img src="./img/5.2.3.png">

# 6 Limpiar contenedores e imágenes.

1. Ejecutamos el siguiente comando para identificar todos los contenedores que tenemos. 

<img src="./img/6.1.1.png">

2. Ahora paramos los contenedores y los borramos. 

<img src="./img/6.1.2.png">

