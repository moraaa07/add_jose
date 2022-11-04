### José Antonio Mora Cairós
### 2º ASIR

# NFS (Network File System)

## 1. Instalamos el servicio NFS. Y agregamos el rol. 

<img src="./img/2.1.PNG">

Vemos el resultado y preparando la instalación. 

<img src="./img/2.1.1.PNG">

## 2. Configurar el servidor NFS.

+ Creamos la carpeta `exports04` y dentro de esta misma, creamos `public`. 

    + En esta carpeta, pulsamos botón derecho, y buscamos la parte de `Compartir con NFS`. Lo ponemos todo tal cual la captura. 

    <img src="./img/2.2.2.PNG">

    
+ Creamos dentro de `exports04` la carpeta `private`. 

    + Hacemos lo mismo con la carpeta `private`.

    <img src="./img/2.2.3.PNG">

+ Ejecutamos el comando `showmount -e 192.168.1.100`

<img src="./img/2.2.4.PNG">


## 3. Cliente NFS.

+ Instalamos el componente cliente NFS. `Panel de Control --> Programas --> Activar o desactivar características de Windows.`

<img src="./img/3.1.1.PNG">

+ Ejecutamos el comando `nfsadmin client start` para iniciar el servicio cliente NFS.

<img src="./img/3.1.2.PNG">

## 4. Montando el recurso.

+ En modo usuario normal, montamos el siguiente comando. 

<img src="./img/3.2.1.PNG">

+ Vemos que esta montado: 

<img src="./img/3.2.2.PNG">

# 5. SO OpenSUSE 

+  En el Servidor `Instalamos yast2-nfs-server`. 

<img src="./img/4.1.1.PNG">

+ Creamos la carpeta `/srv/exports04/public`, `/srv/exports04/private`. Y además creamos los permisos que pongo en la captura. 

<img src="./img/4.1.2.PNG"> 

+ Editamos el fichero `/etc/exports` y ponemos lo siguiente.

<img src="./img/4.1.3.PNG">

+ Instalamos en el cliente `zypper install nfs-client` 

<img src="./img/5.1.1.PNG">

+ Hacemos ping y nmap a los siguientes ip. 

<img src="./img/5.1.2.PNG">

### Problemas. 

Tuve problemas a la hora de conectarme con la 192.168.1.102, y revisé todas las ip y no había ninguno problema a priori. 

