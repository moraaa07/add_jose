## José Antonio Mora Cairós
## 2º ASIR

# Servicio de Directorio con Comandos

**En esta práctica, no me funcionaba bien la máquina propiamente servidor, y la hice desde una máquina cliente. 

## 1. Instalar el Servidor LDAP 

1. Abrimos una consola como root, y seguidamente ejecutamos el comando para instalar el servidor, y ponemos una comprobación de la versión. 

<img src="./img/2.1.PNG">

Aquí comprobamos la versión

<img src="./img/2.1.1.PNG">

2. Creamos el fichero /root/instance.inf

<img src="./img/2.2.1.PNG">

+ Creamos una nueva instancia: 

<img src="./img/2.2.2.PNG">

+ Comprobamos el estado actual de la instancia. 

<img src="./img/2.2.3.PNG">

+ Creamos el fichero /root/.dsrc.

<img src="./img/2.2.4.PNG">

3. Abrimos los puertos del cortafuego.

<img src="./img/2.3.1.PNG">

4. Comprobamos el servicio.

<img src="./img/2.4.1.PNG">

5. Comprobamos el acceso al contenido del LDAP. 

Aquí se muestra el contenido de nuestra base de datos LDAP. 

<img src="./img/2.5.1.PNG">

En esta siguiente comprobación hacemos una consulta.

<img src="./img/2.5.2.PNG">

6. Buscamos, seguidamente, Unidades Organizativas. 

<img src="./img/3.1.1.PNG">

7. Agregamos los usuarios. 

<img src="./img/3.2.1.PNG">

8. Escribimos los datos del fichero ldif anterior dentro de LDAP. 

<img src="./img/3.2.2.PNG">

9. Comprobamos el nuevo usuario. 

Ejecutamos el siguiente comando de la captura, para verificar si se ha creado el usuario correctamente. 

<img src="./img/3.3.1.PNG">

10. Agregamos más usuarios. 

Seguido vamos agregar un usuario más. 

<img src="./img/4.1.1.PNG">

11. Vemos la comprobación: 

<img src="./img/4.1.2.PNG">
