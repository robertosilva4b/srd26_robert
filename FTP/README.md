# Informe FTP - Prácticas Windows y Linux

Crear un manual de instalación y configuración de un servidor FTP en una máquina con Windows Server y otra Linux.

## Instalación y Configuración del Servicio FTP en Windows 2016 Server

- Necesitaremos dos MVs:

| MV  | Hostname  | IP  |
|---|---|---|
| MV1 Server | server26s  | 172.19.26.10 |
| MV2 Cliente | cliente26  | 172.19.26.11 |

#### Instalar Servicio FTP en Windows 2016 Server, a través de Agregar roles y características (IIS)

- Agregamos Roles y Características.

![](img/001.png)

![](img/002.png)

![](img/003.png)

- Servidor web (IIS) --> Servidor FTP

![](img/004.png)

![](img/005.png)

#### Acceder a la creación y configuración de Sitios FTP por medio de la Administración de IIS.

- Esta es la configuración y creación de sitios FTP.

![](img/006.png)

#### Crear tres nuevos sitios FTP

**Primer sitio FTP - Asociado a la unidad C:**
 - No debe permitir accesos anónimos,
 - Sin uso de SSL
 - Solo el usuario Administrador podrá acceder al sitio.
 - Modos lectura y escritura.

![](img/011.png)

![](img/008.png)

![](img/009.png)

Examina todas las opciones de configuración de la página principal de tu Sitio FTP (IIS) y haz una descripción breve de cada una en el informe.

- Las opciones son muy parecidas a los Virtual Hosts, tenemos registros de las sesiones FTP, cuantas hay conectadas en el momento, podemos configurar el certificado si lo hubiese, editar como se deben autentificar los usuarios al servicio ftp, etc..

![](img/010.png)



Trata de acceder al sitio ftp desde el propio servidor a través de un navegador y un explorador de archivos.

- Accedemos con el usuario Administrador que es el único que tiene permisos.

*Navegador*

![](img/013.png)

![](img/014.png)

*Explorador de Archivos*

![](img/016.png)

![](img/015.png)

Si intentamos acceder desde otros usuarios no nos dejara. El usuario "Administrador" tiene permisos de lectura y escritura.

![](img/017.png)

![](img/018.png)

Comprobamos descargar archivos desde Server y Cliente.

![](img/022.png)

![](img/023.png)

Accede ahora desde un cliente Windows de la misma forma.

*Navegador*

![](img/019.png)

![](img/020.png)

*Explorador de Archivos*

![](img/021.png)

Instala el software WinSCP en el cliente Windows, configura la conexión a tu sitio ftp y trata de establecer conexión y realizar comprobaciones.

![](img/024.png)

![](img/025.png)

- Elegimos la instalación típica.

![](img/026.png)

![](img/027.png)

![](img/028.png)

- Configuramos la conexión al sitio ftp del servidor.

![](img/029.png)

- Lo que vemos a la derecha es el contenido del Disco Local C:

![](img/030.png)

- Probamos a descargar un archivo.

![](img/031.png)

![](img/032.png)

![](img/033.png)

![](img/034.png)

**Segundo Sitio FTP - Inetpub**
 - Se permitirá el acceso a todos los usuarios de Active Directory.
 - Modo Lectura y Escritura.
 - No permitimos acceso anónimo.
 - Habilitamos en este caso la posibilidad (permitir, no requerir) de conexiones SSL.

![](img/036.png)

![](img/037.png)

![](img/039.png)

Estos son los usuarios de Active Directory

![](img/038.png)

*Navegador*

- Probamos el funcionamiento con el usuario "Administrador" (server)

![](img/041.png)

![](img/042.png)

- Probamos con el usuario "alfredo" (server)

![](img/043.png)

![](img/044.png)

*Explorador de Archivos*

- Probamos con el usuario "julia" (server)

![](img/046.png)

![](img/047.png)

**Cliente**

- Probamos el funcionamiento con el usuario "alfredo" desde el cliente.

![](img/048.png)

![](img/049.png)

**Conexion desde el cliente usando WinSCP**

- Usando el cifrado SSL y el usuario "robert"

![](img/050.png)

- A la derecha se encuentra el contenido de inetpub/wwwroot

![](img/051.png)

- Descargamos un archivo.

![](img/052.png)

![](img/053.png)

**Tercer Sitio FTP - Archivos y Carpetas**

 - Crear un directorio que contengan carpetas y archivos.
 - Permitiremos acceso anónimo.
 - Modo consulta y lectura.
 - Registro DNS (ftp.miserver.com)

Creamos la carpeta Prueba 3er FTP

![](img/054.png)

![](img/055.png)
>Contenido de la carpeta

Creamos el sitio FTP.

![](img/056.png)

![](img/057.png)

![](img/058.png)

![](img/067.png)

Probamos el acceso desde el servidor

![](img/059.png)

Nos metemos dentro de algún archivo

![](img/060.png)

![](img/061.png)

Probamos la conexión desde el cliente usando WinSCP.

![](img/062.png)

![](img/063.png)

Comprobamos el acceso desde el navegador del cliente.

![](img/065.png)

- Se debe crear un nuevo registro DNS que permita acceder a nuestro sitio FTP a través de la dirección ftp.miserver.com

![](img/066.png)

![](img/068.png)

![](img/069.png)

![](img/070.png)

- La manera para que podamos ofrecer varios sitios FTP simultáneos es cambiando los puertos de los mismos, porque no pueden ser iguales.

 - Sitio FTP Inetpub - Puerto 22
 - Sitio FTP Unidad C - Puerto 23
 - Sitio FTP Archivos y Carpetas - Puerto 21

![](img/071.png)

![](img/072.png)

Hacemos inicio de sesión en los tres sitios FTP desde el WinSCP del cliente.

![](img/073.png)

![](img/074.png)

![](img/075.png)

![](img/076.png)

## Instalación y Configuración del Servicio FTP en Linux

| MV  | Hostname  | IP  |
|---|---|---|
| MV1 Server | oliveros26g1  | 172.19.26.21 |
| MV2 Cliente | oliveros26g2  | 172.19.26.20  |

#### Instalar Servicio SSH en el servidor Linux.

![](img/078.png)

#### Crear dos usuarios en el sistema, con diferentes privilegios y niveles de acceso al filesystem.

- He creado el usuario1 y usuario2.

![](img/079.png)

- El usuario1 tambien pertenece al grupo "root" mientras que el usuario2 no pertenece, así tendrán permisos diferentes.

![](img/080.png)

#### Comprobar, desde una máquina cliente, acceso de los usuarios mediante ssh.

- Usuario1

![](img/081.png)

- Usuario2

![](img/082.png)

#### Tratar de ejecutar una aplicación gráfica del servidor de forma remota, desde el cliente, mediante ssh.

- Usuario1

![](img/084.png)

![](img/085.png)

- Usuario2

![](img/086.png)

#### Acceder, también desde el cliente, mediante sftp (ftp seguro, incluido en el paquete ssh) al sistema de ficheros del servidor y probar acceso, carga y descarga de archivos con ambos usuarios.

- Creamos dos archivos desde el cliente para enviarlo al servidor, uno para cada usuario.

![](img/087.png)

- Creamos en el servidor un archivo para enviarlo al cliente (usuario1)

![](img/088.png)

- Enviamos y Recibimos archivos mientras estamos conectados via sftp con el usuario1.

![](img/089.png)

![](img/090.png)

![](img/091.png)
>Amarillo: archivo que enviamos / Verde: archivo que recibimos

Desde el usuario2

![](img/092.png)

![](img/093.png)

![](img/094.png)
>Amarillo: archivo que enviamos / Verde: archivo que recibimos

#### Realizar varias copias de archivos hacia / desde el servidor mediante scp, utilizando también los dos usuarios creados anteriormente

*usuario1:*

- Enviamos un archivo desde el cliente al /home del usuario.

![](img/095.png)
> En este caso me equivoqué de archivo porque le puse el nombre de usuario2, pero los demás están bien.

- Descargamos un archivo del servidor al cliente.

![](img/096.png)

*usuario2:*

- Enviamos un archivo desde el cliente al /home del usuario.

![](img/097.png)

- Descargamos un archivo del servidor al cliente.

![](img/098.png)

#### Instalar el paquete proftpd

![](img/099.png)

#### Investigar y editar el fichero de configuración /etc/proftpd/proftpd.conf buscando información en Internet

- Tenemos que descomentar el parámetro "DefaultRoot" , esto significa que el usuario esta limitado a su carpeta personal /home. También podríamos definir muchas cosas como una carpeta "DefaultRoot /carpeta" para usar el ftp de manera más organizada. Pero en mi caso no.

![](img/100.png)

- Siempre que hagamos un cambio hay que reiniciar el servicio.

![](img/101.png)

#### Tratar de conectar al servicio ftp gestionado por proftpd tanto desde el servidor como desde un cliente.

*Servidor*

![](img/109.png)

*Cliente*

![](img/102.png)

#### Desde la máquina cliente, probar el acceso al ftp mediante los usuarios creados y realizando diferentes operaciones de listado, subida y descarga de archivos.

*usuario1:*

- Creamos un archivo en el servidor para la descarga y otro en el cliente para la subida.

![](img/103.png)

- Hacemos la subida de un archivo, además listamos los archivos del directorio /home/usuario1.

![](img/104.png)

- Descargamos un archivo del servidor.

![](img/105.png)

*usuario2:*

- Creamos un archivo en el servidor para la descarga y otro en el cliente para la subida.

![](img/106.png)

- Hacemos la subida de un archivo.

![](img/107.png)

- Descargamos un archivo del servidor, además listamos los archivos del directorio /home/usuario2.

![](img/108.png)
