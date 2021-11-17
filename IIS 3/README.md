# Informe IIS - Servidor Web avanzado - PHP, MySQL, phpMyAdmin, FTP y Drupal

Vamos a realizar las instalaciones y configuraciones necesarias para obtener un Servidor Web con soporte PHP y accesos a bases de datos relacionales, acceso FTP y gestor de bases de datos. Sobre este servidor, podremos realizar instalaciones de aplicaciones integradas desde el propio servidor o en modo remoto desde un cliente W7.

## Práctica de IIS Windows 2016 Server V

#### PHP

- Instalamos PHP para nuestro sitio web gestionado por IIS.

![](img/001.png)

![](img/002.png)

![](img/003.png)

![](img/004.png)

- Elegimos opcion IIS FastCGI.

![](img/005.png)

- En mi caso necesitaba agregarlo al IIS.

![](img/006.png)

![](img/007.png)

![](img/008.png)

![](img/009.png)

![](img/010.png)
> Ya estaría instalado el PHP.

- Configurar luego IIS para que
admita el fichero index.php por defecto en las carpetas y/o sitios que nos interese.

![](img/011.png)

- Comprobamos la instalación correcta de PHP colocando un fichero index.php en el sitio web (www.miempresa.com) con el siguiente código: <?php phpinfo(); ?>

![](img/012.png)

![](img/013.png)

![](img/014.png)

#### MySQL

- Instalamos MySQL y .NET Framework 4.0

![](img/029.png)

![](img/030.png)

![](img/031.png)

>En mi caso el .NET Framework 4.0 ya lo tenia instalado.

#### PHPMYADMIN

- Instalamos PHPmyAdmin para un nuevo sitio web asociado llamado phpmyadmin.miempresa.com, creado la correspondiente carpeta donde descomprimiremos los archivos y actualizar DNS.

![](img/056.png)

- Descomprimiremos en la ruta miempresa > phpmyadmin.

![](img/027.png)

![](img/032.png)

![](img/033.png)

DNS

![](img/057.png)

## Práctica de IIS Windows 2016 Server VI

#### FileZilla

- Instalamos el servidor FTP Filezilla en la MV servidor

![](img/034.png)

![](img/035.png)

![](img/036.png)
> Definimos una password para el administrador.

![](img/037.png)

- Crear un usuario denominado ftpuser en el Servidor FTP.

![](img/038.png)

- Crear un nuevo registro DNS que permita acceder a nuestro sitio FTP a través de la dirección ftp.miEmpresa.com.

![](img/039.png)

![](img/058.png)

**Desde el cliente:**

- Comprobar acceso a phpMyAdmin desde un navegador (phpmyadmin.miEmpresa.com)

![](img/040.png)

- Descargar CMS Drupal de drupal.org.

![](img/041.png)

![](img/042.png)

- Instalar un cliente FTP FileZilla.

![](img/043.png)

![](img/044.png)

- Comprobar el acceso al sitio FTP creado a través de un navegador y con el usuario ftpuser.

![](img/045.png)
> Nos conectamos al FileZilla Server.

- Y creamos un sitio remoto que una la carpeta principal del servidor con nuestra máquina cliente. Así podremos pasarle los archivos que queramos.

![](img/047.png)

Comprobamos el funcionamiento de FileZilla desde un navegador.

- La ruta quedaria asi:

![](img/059.png)

**Comprobación desde el Servidor:**

![](img/049.png)

![](img/050.png)

**Comprobación desde el Cliente:**

![](img/051.png)

- Descomprimir y subir archivos Drupal a carpeta principal (www.miEmpresa.com).

![](img/048.png)
> Una vez pasados los archivos podemos ir a www.miempresa.com y veremos la instalación del Drupal.

![](img/054.png)

- Crear una nueva base de datos, denominada cms, a través de phpMyAdmin y crear usuario cms y asignar todos los privilegios para la base de datos anterior.

![](img/053.png)

![](img/052.png)

- Instalar CMS Drupal desde el navegador siguiendo los pasos y consultando documentación
en Internet.

![](img/054.png)

- Definimos la base de datos que creamos con anterioridad.

![](img/055.png)

![](img/060.png)

![](img/061.png)

![](img/062.png)
>Ya estaría instalado.

**Configuración y creación del sitio Drupal**

- Cambiaremos el idioma al Español, además añadiremos la opción de poder traducir a varios idiomas.

![](img/063.png)

![](img/064.png)

![](img/065.png)

![](img/066.png)

![](img/067.png)

![](img/68.png)

![](img/069.png)

- Una vez finalizada la parte del idioma, instalaremos diferentes Temas que podríamos utilizar y configuraremos uno de ellos.

![](img/070.png)
> Antes de hacer nada verificamos cuál es el que estábamos usando de manera predeterminada.

- He instalado todos esos que se ven marcados, siendo el último el que utilizaré de manera predeterminada.
![](img/071.png)

![](img/072.png)

- Ahora crearemos dos páginas sencillas con su menú para probar este tipo de funciones.

![](img/073.png)
> Una primera página dentro del menú `Páginas de HTML`

![](img/074.png)
> Y una segunda dentro del menú `Páginas de Python`

**Resultado final:**

![](img/075.png)

![](img/076.png)

![](img/077.png)
