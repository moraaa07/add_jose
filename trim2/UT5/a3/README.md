## José Antonio Mora Cairós

## 2º ASIR

# 1.1 Preparativos.

+ Master --> master04g --> 10.0.2.31
+ Minion1 --> minion04g --> 10.0.2.32
+ Minion2 --> minion3_04g --> 10.0.2.7

# 2. Master: Instalar y configurar

1. Estando en la MV1 (master) instalamos el propio software del Máster.

<img src="./img/2.1.png">

2. Modificamos el fichero `/etc/salt/master` para configurar nuestro Máster con:

<img src="./img/2.2.png">

+ Ahora activamos el servicio en el arranque del sistema. `systemctl enable salt-master.service`. 

+ Iniciamos el servicio. `systemctl start salt-master.service`.

+ Y este último comando es para consultar los Minions aceptados, dado que todavía no tenemos ninguno, no aparece nada. `salt-key -L`.

<img src="./img/2.3.png">

# 3. Instalamos y configuramos los Minions.

1. Instalamos el software del agente Minion.

<img src="./img/3.1.png">

2. Modificamos el fichero.

<img src="./img/3.1.2.png">

3. Activo el minion en el arranque del sistema e inicio el servicio.

<img src="./img/3.1.3.png">

4. Comprobamos que no tenemos instalado el apache2.

<img src="./img/3.1.4.png">

# 3.1 Cortafuegos.

1. En la MV1 consultamos el estado de la red.

<img src="./img/3.2.1.png">

2. Abrimos el puerto de forma permanente en la zona `public`.

<img src="./img/3.2.2.png">

3. Reiniciamos el firewall.

<img src="./img/3.2.3.png">

4. Consultamos la configuración actual. 

<img src="./img/3.2.4.png">

# 3.2 Aceptación desde el Master

1. Si ejecutamos el siguiente comando siguiente para que el master acepte al minion.

<img src="./img/3.3.2.png">

2. Comprobamos que lo aceptó correctamente.

<img src="./img/3.3.3.png">

# 3.3 Comprobar conectividad

1. Desde el master comprobamos la conectividad siguiente:

<img src="./img/3.4.png">

# 4. Preparar el directorio para los estados.

1. Creamos los siguiente directorios. 

<img src="./img/4.1.2.png">

2. Creamos el fichero siguiente y escribimos tal cual está.

<img src="./img/4.1.3.png">

3. Reiniciamos el servicio. 

# 4.1 Creo un nuevo estado.

1. Creo el siguiente fichero:

<img src="./img/4.2.1.png">

# 4.2 Asociar Minions a estados.

1. Creo el fichero siguiente:

<img src="./img/4.3.1.png">

# 4.3 Comprobar estados definidos.

1. Consulto los estados que tenemos definidos.

<img src="./img/4.4.1.png">

# 4.4 Aplicar el nuevo estado.

1. Consulto el primer estado:

<img src="./img/4.5.1.png">

2. Consulto el segundo estado:

<img src="./img/4.5.2.png">

3. Aplicamos el nuevo estado:

<img src="./img/4.5.3.1.png">

<img src="./img/4.5.3.2.png">

# 5. Crear más estados.

1. En el siguiente fichero creo el nuevo grupo y usuario. 

<img src="./img/5.1.1.png">

2. Aplico el estado.

# 6. Minion con Windows.

1. Instalo `Salt-minion` y mientras se configura, ponemos la IP del Master.

<img src="./img/6.1.1.png">

2. Voy a la MV1 y acepto al nuevo minion.

<img src="./img/6.1.2.png">

3. Vemos como lo acepta y lo incluye.

<img src="./img/6.1.3.png">
