## José Antonio Mora Cairós
## 2º ASIR

# Cliente para autenticación LDAP

1. Primero hacemos unos preparativos y unas comprobaciones. 

+ Comprobamos el acceso al LDAP desde el cliente. 

Voy a la máquina cliente, y ejecuto el siguiente comando para comprobar que el servidor es accesible. 

<img src="./img/1.1.PNG">

+ Comprobamos que los usuarios del LDAP remoto son visibles. 

<img src="./img/1.1.1.PNG">

2. Configuramos la autenticación LDAP 

+ Creamos conexión el servidor. 

    + En la máquina cliente, vamos al apartado `LDAP y Kerberos` de en la aplicación de YAST y configuramos los parámetros como lo tengo puesto en la siguiente captura. 

        <img src="./img/2.1.1.PNG">

    + Resultado:

        <img src="./img/2.1.2.PNG">

+ Comprobamos con los comandos siguientes la información del usuario, los datos del mismo, y por ultimo entrar como usuario definido.

<img src="./img/2.2.PNG">



3.   Creamos usuarios usando los comandos. 

+ Consultamos la lista de usuarios:

<img src="./img/3.1.PNG">

+ Creamos usuario `robot1`:

<img src="./img/3.2.PNG">

+ Ponemos la clave al usuario:

<img src="./img/3.3.PNG">

+ Volvemos a consultar la lista de usuarios:

<img src="./img/3.4.PNG">

+ Entramos con el usuario:

<img src="./img/3.5.PNG">


4. Entramos en Yast, y nos dirigimos a `grupos y usuarios` de esta manera en la derecha superior, en definir filtro ponemos usuario LDAP y ponemos las credenciales. 

<img src="./img/4.1.1.PNG">

4. Agregamos y comprobamos que pusimos el nuevo usuario baron:

<img src="./img/4.2.PNG">



