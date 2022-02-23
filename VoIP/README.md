<center>

# Instalación y configuración de un Servidor de VoIP sobre Windows 2016


</center>

***Nombre:*** Robert Oliveros y Zebensui Lorenzo

***Curso:*** 2º de Ciclo Superior de Administración de Sistemas Informáticos en Red.

### ÍNDICE

+ [Introducción](#id1)
+ [3CX Phone System](#id2)
+ [Usuarios Movil](#id3)
  + [Comprobaciones Movil-Movil](#id3.1)
+ [Conclusiones](#id5)


#### ***Introducción***. <a name="id1"></a>

Siguiendo los pasos detallados en las guías y tutoriales proporcionados, instalar y
configurar un servidor y un cliente para establecer comunicaciones de voz mediante el
servicio VoIP (Voice Over Internet Protocol) sobre sistemas Windows.

Plantearemos una practica sobre VoIP en Windows utilizand 3CX Phone System, una distribución GNU/Linux especializada basada en Debian, creada por 3CX, diseñada para correr una plataforma completa de comunicaciones unificada, basada en el software de PBX.

#### ***3CX Phone System***. <a name="id2"></a>

La idea es registrarnos, configurar y descargar el software de 3CX Phone System, para ello utilizaremos una MV Windows Server.

- Nos creamos una nueva cuenta desde su pagina oficial: http://www.3cx.es/

![](img/001.png)

Una vez dentro del panel de nuestra suscripcion, marcamos que no queremos hacer un backup.

![](img/002.png)

Marcamos la opcion de "Local" ya que desde esta es donde podremos configurar nosotros mismos todos los datos importantes, la otra opcion seria que los hospedaran ellos, ofrecen 1 año gratis, pero perderia la gracia de la practica.

![](img/003.png)

Definimos un hostname cualquiera, en nuestro caso, parte del dominio del Windows Server.

![](img/004.png)

Descargamos el ejetucable de instalacion para Windows.

![](img/005.png)

Completamos una instalacion normal y basica:

![](img/006.png)

![](img/007.png)

![](img/008.png)

![](img/009.png)

Justo despues de la imagen anterior, se abre una consola que nos pregunta como preferimos configurar nuestro servicio, desde la consola o via Web, yo he documentado la parte Web, pero al haber tenido problemas durante la practica probe el otro metodo y es practicamente igual que este que mostrare a continuacion.

Primero nos pide la License Key que la tenemos en nuestro panel de perfil.

![](img/010.png)

![](img/011.png)

![](img/012.png)

Definimos un usuario y su contraseña.

![](img/013.png)

Comprobamos que nuestra IP publica sea la que nos muestra y aceptamos en nuestro caso que esta en lo cierto.

![](img/014.png)

Marcamos que nuestra IP Publica es dinamica para que el servicio detecte cada vez que iniciemos la maquina que IP estamos usando.

![](img/015.png)

Dejamos los puertos que vienen por defecto, los mas importantes para nosotros seran el 5000 y 5001 que son HTTP y HTTPS respectivamente.

![](img/016.png)

Seleccionamos el adaptador de red que este conectado a la red local y utilizamos el FQDN de nuestro controlador de Dominio Active Directory.

![](img/017.png)

![](img/018.png)

Seleccionamos que la extensiones funcionen con 3 digitos.

![](img/019.png)

Definimos un correo para el admin, este recibira notificaciones por actualizacion, fallos en el sistema, intentos de hackeo...

![](img/020.png)

Definimos nuestro Pais y Zona horaria.

![](img/021.png)

Configuramos los datos del operador, se le suele dar por defecto la extension 100 que es con la que podra acceder al sercicio.

![](img/022.png)

Nos llega un correo como el que veran a continuacion donde nos da informacion sobre el usuario, ademas de una contraseña unica e intrasferible.

![](img/036.png)

Seleccionamos el pais en el que trabajaremos y en el cual las llamadas seran realizadas.

![](img/023.png)

Seleccionamos el idioma en el que funcionara el servicio.

![](img/024.png)

Y por ultimo, registro de datos personales como cuenta administrador.

![](img/025.png)

![](img/026.png)

Ya tendriamos nuestro servicio de 3CX levantado.

![](img/027.png)

***DISCLAIMER*** - Hay que tener mucho cuidado con los servicios de Windows, hay que asegurarse de que estan bien levantados y que las dependecias de ellos estan tambien activas, muchos hay que levantarlos por primera vez de manera manual, y fue un fallo que ocurrio mucho en clase.

![](img/029.png)

Iniciamos sesion, ya sea con el nombre o la extension del operador.

![](img/028.png)

#### ***Usuarios Movil***. <a name="id3"></a>

Una vez dentro del panel de control, vamos al apartado de usuarios para agregarlos.

![](img/030.png)

*Cuando los agregamos tenemos que añadir un numero de telefono y escanear el QR que aparece con nuestro dispositivo movil, esto hara que el perfil se nos ponga en verde*

![](img/037.png)
> Cuando escaneamos el QR nos aparece el usuario que ahora representamos(El usuario con extension 100) listo para hacer llamadas y recibirlas.

![](img/031.png)

Lo hacemos con otro movil para un segundo usuario, y obviamente con diferente numero de telefono.

![](img/038.png)
> Vemos que en el movil nos aparece tanto nuestro nuevo usuario(Ext 101) como otro usuario que no somos nosotros pero que esta disponible para hacerle una llamada, mandar mensaje, etc.

![](img/032.png)

##### ***Comprobaciones Movil-Movil***. <a name="id3.1"></a>

Llamada del usuario (101) al usuario (100)

![](img/039.png)    > >     ![](img/040.png)   > > ![](img/041.png)     







![](img/042.png)








#### ***Conclusiones***. <a name="id5"></a>
