### José Antonio Mora Cairós

### 2º ASIR

# Samba (con OpenSUSE y Windows)

## 1. Servidor Samba (MV1)

### 1.1 Preparativos

+ En este primer punto, agrego los hosts. Poniendo tanto la IP de casa como las de clase.

<img src="./img/1.1.PNG">

### 1.2 Usuarios locales

+ Creamos los grupos `piratas, soldados y sambausers`.

<img src="./img/1.2.1.PNG">

+ Creamos el usuario `sambaguest`.

<img src="./img/1.2.2.PNG">

+ Editamos el fichero `/etc/passwd` y ponemos lo siguiente:

<img src="./img/1.2.3.PNG">

+ Dentro del grupo `piratas` incluyo los siguientes usuarios:

<img src="./img/1.2.4.PNG">

+ Dentro del grupo `soldados` incluyo los siguientes usuarios:

<img src="./img/1.2.5.PNG">

<img src="./img/1.2.6.PNG">

### 1.3 Crear las carpetas para los futuros recursos compartidos

+ Creamos la carpeta base para los recursos de la red y le ponemos el permiso siguiente:

<img src="./img/1.3.1.PNG">

+ Creamos seguidamente, las carpetas para los recursos compartidos, y les agregamos los permisos necesarios. 

<img src="./img/1.3.2.PNG">

<img src="./img/1.3.3.PNG">

### 1.4 Configurar el servidor Samba

+ Hacemos una copia del fichero. 

<img src="./img/1.4.1.PNG">

+ Ponemos el nombre del Workgroup:

<img src="./img/1.4.2.PNG">

+ Ponemos que se nos inicie durante el arranque y abrimos el puerto en el cortafuegos.

<img src="./img/1.4.3.PNG">

### 1.5 Crear los recursos compartidos de red

+ Creamos una configuracion con las secciones, tenemos que editar el fichero `/etc/samba/smb.conf`

<img src="./img/1.5.1.PNG">


### 1.6 Usuarios Samba

+ Creamos los usuarios y contraseñas:

<img src="./img/1.6.1.PNG">

+ Comprobamos que todos los usuarios están instalados con `pdbedit -L`.

<img src="./img/1.6.2.PNG">

## 2. Windows

## 2.1 Cliente Windows GUI

+ Escribimos la ip de nuestro servidor, Windows 10, en la zona de red de la biblioteca, para asi poder contactar con el servidor. 

De esta manera, accedo a `barco04` para hacer pruebas. Salió todo perfecto.

<img src="./img/2.1.1.PNG">

+ Compruebo los resultados:

<img src="./img/2.1.2.PNG">

+ Compruebo las conexiones establecidad con la máquiza cliente.

<img src="./img/2.1.3.PNG">

## 2.2 Cliente Windows comandos

+ Abrimos un `cmd` en windows y ejecutamos esto siguiente:

<img src="./img/2.2.1.PNG">

+ Si tenemos alguna conexión las cerramos.

<img src="./img/2.2.2.PNG">

+ Ahora nos fijamos y ya no tenemos nada.

<img src="./img/2.2.4.PNG">

+ Vemos los recursos del servidor remoto:

<imf src="./img/2.2.5.PNG">

+ Creamos una conexión con el recurso compartido:

<img src="./img/2.2.6.PNG">

+ Le preguntamos al demonio si está todo bien.

<img src="./img/2.2.7.PNG">

+ Comprobamos las conexiones establecidad con el cliente:

<img src="./img/2.2.8.PNG">


## Cliente GNU/Linux GUI

+ Creamos la carpeta de prueba.

<img src="./img/3.1.3.PNG">

+ Comprobamos el resultado:

<img src="./img/3.1.4.PNG">

+ Probamos que tenemos conectado:

<img src="./img/3.1.5.PNG">

### 3.2 Cliente GNU/Linux comandos

+ Mostramos la lista de los nombres de kali. 

<img src="./img/3.2.1.PNG">

+ Montamos el recurso compartido de Samba Server:

<img src="./img/3.2.2.PNG">

+ Hacemos un `df -hT` y vemos que en la parte de abajo hay una conexión al routers.

<img src="./img/3.2.3.PNG">

+ Si reiniciamos el pc, cuando volvemos ya no está el fichero de antes:

<img src="./img/3.3.1.PNG">

+ Agregamos al fichero una linea más:

<img src="./img/3.3.2.PNG">

+ Al hacer un `df -hT`nos saldrá a tiempoo, si hace frio. 

<img src="./img/3.3.3.PNG">

## 4. Preguntas para resolver

1. ¿Por qué tenemos dos servicios (smb y nmb) para Samba?

Porque un servicio responde las peticiones de servicio de nombres NetBIOS (nmb) servicios para compartir archivos e impresión a clientes Windows(smb).

2. ¿Las claves de los usuarios en GNU/Linux deben ser las mismas que las que usa Samba?. 

No, no tiene que ver que coincidan. 

3. ¿Puedo definir un usuario en Samba llamado soldado3, y que no exista como usuario del sistema?.

En el sistema, debe de apercer un usuario, si no es asi, debe de existir otra cosa.

4. ¿Cómo podemos hacer que los usuarios soldado1 y soldado2 no puedan acceder al sistema pero sí al samba?.

Abriendo el programa de yast, en entorno gráfico.
