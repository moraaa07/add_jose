### José Antonio Mora Cairós
### 2º ASIR

# Servidor de Impresión GNU/Linux (CUPS)

## 1. Servidor de Impresión.

1. En esta primera parte, instalaremos el sistema de impresión CUPS para Linux en el servidor. 

    <img src="./img/2.1.png">

2. Seguidamente, configuraremos el fichero `/etc/cups/cupsd.conf` y en los ejemplos de la siguiente captura, colocamos `Allow @LOCAL` esto significa que vamos a permitir el acceso al servicio vía Web del servidor a todas las maquias que esten en nuestra red local. 

    <img src="./img/2.2.png">

3. Abrimos la configuración del cortafuegos en la maquina del servidor y nos dirijimos a la zona `public` y añadimos a Servicios permitidos el `ipp`.

    <img src="./img/2.3.png">

4. Hacemos lo mismo pero con la máquina cliente. 

    <img src="./img/2.4.png">

5. Para ver lo que tenemos activo ejecutamos el comando de la siguiente captura. 

    <img src="./img/2.5.png">

6. Nos conectamos a la interfaz web de CUPS, y accedemos a la sección de `Administración` con el usuario/clave de root.

    <img src="./img/2.6.png">

7. Y vemos los access_log.

    <img src="./img/2.7.png">

## 2. Imprimir de forma local.

1. 