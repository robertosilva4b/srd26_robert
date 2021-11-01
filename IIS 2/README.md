# Informe IIS - Servidor Web avanzado - Carpetas seguras y privadas

## Práctica de IIS Windows 2016 IV

#### Crea una nueva zona de búsqueda directa en los servicios DNS asociado al dominio miEmpresa. Crea también una carpeta miEmpresa en C:\ y una subcarpeta ‘principal’.

![](img/001.png)

#### Crea un nuevo sitio web denominado miEmpresa en IIS asociado a la subcarpeta anterior y con acceso a través de la dirección www.miEmpresa.com. Actualiza DNS adecuadamente.

![](img/002.png)

- Comprobamos el funcionamiento desde el servidor.

![](img/003.png)

- Desde el cliente.

![](img/004.png)

####  Crea un nuevo sitio web denominado ‘pagos’ (pagos.miEmpresa.com) y configura este último para ser accedido de forma segura, vía ‘https’.

##### Configuración A:

- Para ello creamos la carpeta `miempresa/pagos` y configuramos para que el sitio este asociado a esta.

![](img/007.png)

- El sitio web de "`Pagos`" lo certificaremos con un `Certificado Autofirmado`.

![](img/005.png)

![](img/006.png)

![](img/008.png)

- Configuramos adecuadamente el `DNS`.

![](img/009.png)

- Comprobamos el acceso via "`http`" desde el `servidor`.

![](img/012.png)

- Comprobamos desde el `cliente`.

![](img/015.png)

Vemos como en ambos, la página se autodirige a la página principal del IIS.

- Comprobamos el acceso "`https`" desde el `servidor`.

![](img/010.png)

![](img/011.png)

- Comprobamos desde el `cliente`.

![](img/013.png)

![](img/014.png)

##### Configuración B:

#### Crearemos un nuevo sitio seguro (tienda.miempresa.com) con la generación de un Certificado Digital a través de la aplicación OpenSSL

![](img/017.png)

- Descargamos `OpenSSL`.

![](img/018.png)

![](img/019.png)

- Solicitamos el certificado.

![](img/020.png)

- Importante acordarse de la longitud en bits que definimos.

![](img/021.png)

![](img/022.png)

- Guardamos el archivo generado en la ruta `C:/OpenSSL/bin`.

![](img/023.png)

![](img/024.png)

- Siguiendo los pasos que se nos detallan, generamos un archivo para certificar nuestra web.

![](img/025.png)

![](img/026.png)

![](img/027.png)

![](img/028.png)

- Generamos un archivo `.crt` que definimos para completar la solicitud.

![](img/036.png)

![](img/029.png)

- Lo agregamos al sitio.

![](img/030.png)

- Comprobamos en el `servidor`.

![](img/031.png)

- Si intentamos acceder desde "`HTTP`" nos redirige a la página principal.

![](img/032.png)

- Desde el `cliente`.

![](img/033.png)

![](img/034.png)

- Comprobamos desde el cliente que nos redirige a la página principal si accedemos vía "`HTTP`"

![](img/035.png)

## Práctica de IIS Windows 2016 IV B

#### Necesitamos crear una carpeta empleados (dentro de miEmpresa) y, dentro de esta, tres o cuatro subcarpetas personales con nombres de empleados y una, denominada común, a la que tendrán acceso todos los empleados, pero no otros usuarios sin identificar.

![](img/037.png)

![](img/038.png)

#### o Crearemos el nuevo sitio web, como subdominio de nuestro dominio principal, asociado a la carpeta genérica empleados.

![](img/039.png)

- Definimos el `DNS`.

![](img/040.png)

#### Colocar un fichero index.html diferente en cada una de las carpetas creadas, con el objetivo de poder comprobar el acceso desde un navegador

![](img/043.png)

![](img/044.png)

![](img/045.png)

![](img/046.png)

#### Para el sitio web creado y para cada una de sus carpetas, deshabilitamos el acceso anónimo

![](img/041.png)

![](img/042.png)

#### Agregar función de Autenticación Básica a nuestro Servicio de IIS a través de la Administración del Servidor

![](img/047.png)

#### En Active Directory, crearemos un usuario para cada empleado (tantos como carpetas personales) y un grupo Empleados que los incluya a todos

![](img/048.png)

![](img/049.png)

#### Desactivamos, para la carpeta empleados, los permisos heredables a través de las opciones avanzadas en la ficha de seguridad. Añadimos grupo de Administradores con Control Total y grupo Empleados con Lectura y Ejecución+ Mostrar Carpeta+Leer.

![](img/050.png)

#### Realizamos el mismo procedimiento para cada una de las carpetas personales de los empleados, colocando como usuarios autorizados el Grupo de Administradores (Control Total) y el empleado propietario de cada carpeta (con los permisos que creas convenientes).

![](img/053.png)

![](img/054.png)

![](img/055.png)

#### Realizamos el mismo procedimiento para la carpeta ‘común’, colocando como usuarios autorizados el Grupo de Administradores (Control Total) y el grupo Empleados (con los permisos que creas convenientes).

![](img/056.png)

#### Comprobamos el acceso, tanto desde el servidor como desde el cliente W7, a las diferentes carpetas con distintos usuarios.

- Comprobaciones desde el `servidor`:

![](img/057.png)

![](img/058.png)

- Intentamos entrar en la página de `Isabel` desde el usuario `Alfredo`.

![](img/059.png)

![](img/060.png)

![](img/061.png)

![](img/062.png)

![](img/063.png)

- Entramos a la página común desde algún usuario.

![](img/064.png)

![](img/065.png)

- Comprobaciones desde el `Cliente`:

![](img/066.png)

![](img/067.png)

![](img/068.png)

![](img/069.png)

![](img/070.png)

![](img/071.png)

![](img/072.png)

![](img/073.png)
