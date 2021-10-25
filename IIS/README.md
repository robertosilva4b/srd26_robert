# Informe IIS - Servidor Web básico

#### PLANTEAMIENTO

Instalaremos el servicio IIS y configuraremos diversos sitios webs planteados en los diferentes PDFs.

| MV  | Rol  | IP  |
|---|---|---|
| MV1 (oliveros26s)  |Server   |172.19.26.10   |
| MV2 (oliveros26s1)  |  Cliente | 172.19.26.11  |

![](img/018.png)

![](img/020.png)

## Práctica de IIS Windows 2016 Server I

- Instalar IIS en Windows.

![](img/001.png)

![](img/002.png)

![](img/003.png)

![](img/004.png)

![](img/005.png)

![](img/006.png)

![](img/007.png)

![](img/008.png)

![](img/009.png)

##### Comprobar acceso a nuestro servidor web (localhost)

![](img/010.png)

#### Entrar en cliente Windows y acceder, desde un navegador web a través de la IP del servidor

![](img/019.png)

#### Acceder ahora desde MV2 a la misma página mediante el nombre principal del dominio y desde cualquier otro alias que haya sido definido en la configuración DNS.

- Tenemos que definir que nuestro sitio web tenga como enlace el nombre principal del dominio.

![](img/012.png)

![](img/013.png)

`En el servidor:`

![](img/014.png)

`En el cliente:`

![](img/021.png)

![](img/022.png)

#### Añade un alias en el servicio DNS que relacione el sitio www con el dominio principal

- Creamos la relación www en el servicio DNS.

![](img/011.png)

En el servidor:

![](img/015.png)

En el cliente:

![](img/023.png)

#### Crea una página web HTML sencilla (index.html) como página principal de tu dominio y colócala en `C:\Inetpub\wwwroot`.

![](img/025.png)

- Comprobaremos la nueva página HTML.

En el servidor:

![](img/028.png)

![](img/029.png)

![](img/030.png)

![](img/031.png)

En el cliente:

![](img/032.png)

![](img/033.png)

![](img/034.png)

#### Crea un pequeño sitio web con varias páginas e imágenes organizadas en subcarpetas de wwwroot.

![](img/037.png)

![](img/038.png)

En el servidor:

![](img/039.png)

![](img/040.png)

En el cliente:

![](img/041.png)

![](img/042.png)

## Práctica de IIS Windows 2016 Server II

#### Creación de sitios web independiente

- Agregamos un nuevo Sitio Web.

![](img/044.png)

![](img/051.png)

![](img/050.png)

- Cambiamos los permisos.

![](img/052.png)

- Creamos una carpeta donde estará nuestro index junto a otras carpetas e imágenes.

![](img/047.png)

- Probamos el sitio web en el servidor:

![](img/053.png)

- En el cliente:

![](img/054.png)

## Práctica de IIS Windows 2016 Server III

 Crearemos un directorio virtual que vincularemos a la página anterior de servicios.

 - Creamos un directorio fuera del directorio de la página, ahí dentro definimos las páginas HTML, carpetas e imágenes que consideremos.

![](img/057.png)
> En verde está marcado el directorio de la página creada en la práctica anterior y en rojo el directorio que usaremos virtualmente.

![](img/056.png)

![](img/059.png)

![](img/060.png)

- Definimos que podamos acceder tanto desde servicios como de departamentos.

![](img/061.png)

![](img/062.png)

**En el servidor:**

![](img/064.png)

![](img/065.png)

![](img/066.png)

Desde servicios también nos conecta:

![](img/067.png)

**En el cliente:**

![](img/068.png)

![](img/069.png)

![](img/070.png)

Desde servicios en el cliente:

![](img/071.png)
