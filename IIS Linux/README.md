# Servidor Web Apache Linux

Realizaremos una serie de instalaciones para conseguir varios sitios webs que funcionen de diferentes maneras.

#### Dominio principal: miempresa.com

**Apache**

- Instalaremos Apache con sudo apt-get install apache2.

![](img/001.png)

![](img/002.png)

![](img/005.png)

- Comprobar carpeta raíz sitio web: /var/www

![](img/003.png)

![](img/008.png)

- Comprobar acceso a localhost //It works!

![](img/004.png)

- Añadir línea www.miempresa.com asociada a IP servidor en /etc/hosts.

![](img/006.png)

- Comprobamos el acceso mediante el dominio.

![](img/007.png)

- Comprobar la carpeta de apache2 y ver sus logs.

![](img/009.png)

**PHP**

- Instalamos PHP con su version actual.

![](img/010.png)

- Comprobar acceso a index.php, para ello crearemos un sitio de prueba donde incluiremos un index.

- Ademas aprovechare este sitio de prueba para explicar como se crean.

**Crear una carpeta en la ruta /var/www**

- Dentro de esta carpeta es donde almacenas todo tipo de index, imagenes, etc..

![](img/012.png)

**Crear archivo de configuracion en sites-available**

- Nos iremos a la ruta de /etc/apache2/sites-available y crearemos un archivo .conf donde definimos el nombre del servidor, la ruta de los archivos que queramos que se vean en la web (/var/www/prueba), el puerto y muchas mas cosas, el que utilizo en este caso es bastante sencillo.

![](img/013.png)

**Habilitar el sitio y reiniciar apache2**

- Lo ultimo que queda es habilitar el archivo, lo que seria equivalente a hacer un enlace simbolico a sites-enabled y reiniciar el servicio.

![](img/014.png)

**Resultado**

![](img/016.png)

#### Sitio seguro (https): pagos.miempresa.com

- Creamos otra nueva carpeta en /var/www con un HTML sencillo

![](img/017.png)

- Generamos certificado automatico dentro de una carpeta que hemos creado en la ruta de apache2.

![](img/025.png)

![](img/021.png)

- Habilitamos el ssl

![](img/026.png)

- Creamos el archivo .conf y definimos las rutas con la ubicacion del certificado

![](img/023.png)

![](img/024.png)

![](img/027.png)

#### Carpetas privadas protegidas: empleados.miempresa.com

- Creamos una nueva carpeta en /var/www llamada "privada" , dentro crearemos a su vez dos carpetas personales, para el acceso de emplead@s.


![](img/044.png)
>Creamos un .htaccess y un index.html para cada emplead@ y tambien para el sitio web en general.

**Archivos .htacces**

![](img/037.png)

![](img/041.png)

![](img/042.png)

**Archivos html**

![](img/033.png)

![](img/032.png)

![](img/043.png)

**Para definir las claves:**

![](img/038.png)

![](img/045.png)

![](img/046.png)

**Archivo conf dentro de sites-available**

![](img/047.png)

**Resultados**

![](img/039.png)

![](img/040.png)

![](img/048.png)

![](img/049.png)

![](img/050.png)

![](img/051.png)

#### Instalación PHP, MySQL, phpMyAdmin

![](img/052.png)

![](img/053.png)

![](img/054.png)

- Creamos otra carpeta "phpmyadmin" y metemos todo los archivos del programa.

![](img/055.png)

#### Gestión bases de datos: phpmyadmin.miempresa.com

![](img/056.png)

![](img/057.png)

![](img/058.png)
>Tuve un problema y tuve que instalar otra dependencia

![](img/059.png)

![](img/060.png)

- Creamos un base de datos y usuario.

![](img/061.png)

#### Instalación y configuración de un CMS (En mi caso WordPress)

![](img/062.png)

![](img/063.png)

![](img/064.png)

![](img/065.png)

![](img/066.png)

![](img/067.png)

![](img/068.png)

![](img/069.png)

![](img/070.png)
