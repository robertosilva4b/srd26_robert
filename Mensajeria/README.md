<center>

# Instalación y Configuración de un Servidor de Mensajería Instantánea

</center>

***Nombre:*** Zebensui Lorenzo Esquivel

***Curso:*** 2º de Ciclo Superior de Administración de Sistemas Informáticos en Red.

***Nombre:*** Robert Oliveros Silva

***Curso:*** 2º de Ciclo Superior de Administración de Sistemas Informáticos en Red.

### ÍNDICE

- [Introducción](#id1)
- [Desarrollo](#id4)
  - [Comprobar que en tu servidor Windows 2012 están instalados y funcionan correctamente: IIS, PHP, MySQL y phpMyAdmin](#id4.1)
  - [Descargar e instalar el servidor de mensajería instantánea OpenFire para Windows.](#id4.2)
  - [Iniciar (Start) el servidor de mensajería Openfire.](#id4.3)
  - [Crear una base de datos en blanco en MySqQL a través de phpMyAdmin y recordar nombre de la BD, así como usuario y contraseña con privilegios.](#id4.4)
  - [Ejecutar el script de instalación de Openfire desde un navegador web del servidor, mediante la url http://127.0.0.1:9090.](#id4.5)
    - [Seguir las instrucciones del documento PDF de Servicio de Mensajería en Windows para seleccionar las distintas opciones de instalación y configuración de Openfire](#id4.5.1)
  - [Acceder a la consola de administración de Openfire con el usuario administrador creado.](#id4.6)
  - [Descargar e instalar un cliente de Mensajería.](#id4.7)
  - [Crear dos nuevos usuarios en OpenFire para poder mantener una conversación entre cliente y servidor.](#id4.8)
  - [Mantener conversacion entre ambas máquinas](#id4.9)
    - [Inicio de sesion con usuarios](#id4.9.1)
    - [Busqueda e Inicio de conversacion](#id4.9.2)
  - [Instalar, probar e informar FastPath WebChat o SparkWeb de OpenFire.](#id4.10)


#### ***Introducción***. <a name="id1"></a>

En esta práctica instalaremos y configuraremos un servidor de mensajeria instantanea utilizando programas y servicios como: `phpMyAdmin`, `PHP`, `MySQL`, `OpenFire`, `Spark`...

Para ello necesitamos dos MVs:

| Tipo  | IP  |
|---|---|
| Servidor  | 172.19.22.41  |
| Cliente | 172.19.22.42  |
> *DISCLAIMER: Hemos realizado la práctica desde una sola máquina real virtualizando ambas máquinas virtuales, ya que no podiamos trabajar juntos desde el aula por motivos ajenos a la asignatura.*

`Cliente:`

 ![](img/45.png)

`Servidor:`

![](img/46.png)

#### ***Desarrollo***. <a name="id4"></a>

###### **Comprobar que en tu servidor Windows 2012 están instalados y funcionan correctamente: IIS, PHP, MySQL y phpMyAdmin** <a name="id4.1"></a>

- Podriamos comprobar cada uno de estos servicios y su funcionamiento, pero a final de cuentas,si comprobamos que el `phpMyAdmin` funciona es suficiente, ya que este depende a su vez de un correcto funcionamiento de `PHP` y `MySQL` (phpMyAdmin es como un puente entre ambos).

![](img/12.png)
> Además comprobamos que el IIS funciona correctamente, ya que es el servicio que nos permite tener el phpMyAdmin en una página web propia.

###### **Descargar e instalar el servidor de mensajería instantánea OpenFire para Windows.** <a name="id4.2"></a>

- Descargamos el `OpenFire` y además descargamos el `Spark` para instalarlo más adelante, porque nos hara falta.

![](img/1.png)

![](img/2.png)

![](img/3.png)

![](img/4.png)

![](img/5.png)

![](img/6.png)

![](img/7.png)
> Finaliza la instalación del OpenFire, como se ha podido ver es una instalación de los más común.

###### **Iniciar (Start) el servidor de mensajería Openfire.** <a name="id4.3"></a>

- Una vez terminada la instalación podemos abrirlo y darle a "Start" para dejar el servidor iniciado.

![](img/13.png)

###### **Crear una base de datos en blanco en MySqQL a través de phpMyAdmin y recordar nombre de la BD, así como usuario y contraseña con privilegios.** <a name="id4.4"></a>

- Entramos en el `phpMyAdmin` con nuestro usuario "root"  y creamos la BD (en nuestro caso, con el nombre openfire) vacia.

![](img/14.png)

###### **Ejecutar el script de instalación de Openfire desde un navegador web del servidor, mediante la url http://127.0.0.1:9090.** <a name="id4.5"></a>

- Nos vamos a la ip 127.0.0.1:9090 que indica la práctica y estaremos ejecutando un script de instalación de `Openfire`.

![](img/15.png)

###### **Seguir las instrucciones del documento PDF de Servicio de Mensajería en Windows para seleccionar las distintas opciones de instalación y configuración de Openfire.** <a name="id4.5.1"></a>

Una vez seleccionado el idioma (foto anterior) tendremos la configuración del servidor.

- Definimos `Dominio` y `FQDN` (Con la dirección completa de dominio que en este caso tenía Zeben)

- Definimos ambos puertos que utilizara.

![](img/16.png)

- Seleccionamos `Conexion Estandard`.

![](img/17.png)

***IMPORTANTE*** A la hora de definir la URL de la BD tenemos que dejar claro el nombre de la misma, es decir, openfire.

-Definimos el usuario con el que tenemos acceso a la BD.

![](img/18.png)
> Donde definimos "localhost" también puede ir 172.19.22.41 ya que es la ip de nuestro servidor.

- El profesor nos hace hincapié en la guía que cambiemos la opción "`Servidor de Directorio (LDAP)`" a "`Por defecto`", ya que se recomienda en el tutorial de instalación.

![](img/21.png)

- Definimos los datos del administración para luego entrar al `Openfire` con los mismos.

![](img/22.png)

![](img/23.png)

###### **Una vez completada la instalación, acceder a la consola de administración de Openfire con el usuario administrador creado.** <a name="id4.6"></a>

- Es importante que en el usuario no pongamos el correo, simplemente ponemos el nombre "`admin`"

![](img/25.png)

- Una vez dentro de la consola de administración de `Openfire`, podemos ver datos como la versión, nombre del servidor, memoria...

![](img/26.png)

###### **Una vez instalado el servidor OpenFire, vamos a descargar e instalar un cliente de Mensajería.** <a name="id4.7"></a>

- La practica nos pide que nos instalemos el cliente de mensajería Spark como ya mencionamos con anterioridad, tanto en el servidor como en el cliente.

- La instalación de Spark es bastante simple, se vería tal que así:

![](img/8.png)

![](img/9.png)

![](img/10.png)

![](img/11.png)
> No hemos mostrado como instalamos el cliente en ambas máquinas para que no fuera repetitivo.

###### **Ahora vamos a crear dos nuevos usuarios en OpenFire (además del administrador) para poder mantener una conversación entre cliente y servidor.** <a name="id4.8"></a>

- Creamos los usuarios "`user1`" y "`user2`".

![](img/27.png)

![](img/28.png)

![](img/29.png)

###### **Mantener conversación entre ambas máquinas** <a name="id4.9"></a>

###### **Inicio de sesión con usuarios** <a name="id4.9.1"></a>

- En la MV Server utilizaremos el usuario "`user1`"

![](img/30.png)

- En la MV Cliente utilizaremos el usuario "`user2`"

![](img/32.png)

- Para ambos usuarios descartamos esta opcion, para que funcione la conversación.

![](img/31.png)
> Para llegar a este panel de preferencias, tenemos que picarle en `Avanzado` cuando estamos ingresando los datos de usuarios.

![](img/47.png)

- Una vez nos conectamos con ambos usuarios, la cosa debería ser algo tal que así:

![](img/33.png)

###### **Búsqueda e Inicio de conversación** <a name="id4.9.2"></a>

**Nos encontramos usando el user1 (server):**

- Buscamos al usuario cliente (`user2`), desde el apartado de "`Contactos`" que podemos apreciar abajo a la izquierda.

![](img/34.png)

- Una vez encontremos al usuario(`user2`), pinchamos en su nombre para iniciar la conversacion.

![](img/35.png)
> Vemos que el servicio de búsqueda es el dominio que definimos en el `Openfire`

- Enviamos un mensaje de prueba y vemos como se ha enviado y recibido sin problemas.

![](img/36.png)

- Enviamos un mensaje en la dirección opuesta.

![](img/37.png)

- A continuación, mostraremos varias funcionalidades que posee el menú de la mensajería instantánea, por alguna razon, no nos dejaba utilizarlos, nos congelaba las máquinas o se quedaba colgado el programa, pero creo que lo interesante es ver el proceso.

**Documento:** Podemos enviar docs como se puede observar en la foto, suponemos que deben ser de tamaño ligero y que no aceptara todo tipo de documento.

![](img/38.png)

**Imágenes:** También incluye la opción de enviar imágenes, en este caso no pudimos enseñar el proceso, pero intuimos que es exactamente igual a la de documentos, simplemente habría que hacer clic en el símbolo que aparece marcado en la foto.

![](img/42.png)

- Cerrando con las funcionalidades que ofrece Spark, tenemos las conferencias, lo que coloquialmente entemos como una sala de grupo.

- Esto sería un ejemplo de como crear una conferencia.

![](img/39.png)

- Añadimos al usuario cliente (`user2`) a la conferencia, ya que esta fue creada con el usuario servidor (user1).

![](img/40.png)

- Comprobamos el funcionamiento.

![](img/41.png)


###### **Instalar, probar e informar FastPath WebChat o SparkWeb de OpenFire.** <a name="id4.10"></a>

- En nuestro caso, no encontramos ningún de los dos plugins mencionados, lo único que encontramos fue uno de la misma distribución, pero con funcionalidades totalmente distintas. Aunque estuvimos buscando información, no parece haber nada que nos indique la causa, por ello decidimos no ingadar más en el asunto y nos ceñimos a instalar un plugin (no trabajamos con el, ya que no influía en la práctica ni en lo que se nos pedía).

- Prueba de búsqueda y descarga de un plugin:

![](img/43.png)

![](img/44.png)
