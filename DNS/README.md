# Instalación y Configuración DNS Windows Server

### PLANTEAMIENTO

- Utilizamos la MV Windows Server 2016 y Cliente Windows que hemos usado en tareas anteriores.

- En mi caso tengo activado ya el servicio `DNS`, porque al promover el AC a controlador de dominio se nos activa el servicio `DNS`.

- Pero si no lo tuvieramos simplemente agregamos roles y lo configuramos con el asistente.

![](img/001.png)

![](img/002.png)

### 1. Crear una zona de busqueda directa

![](img/003.png)

- Empezamos la creacion de la nueva zona con ayuda del asistente.

- Elegimos zona principal.

![](img/004.png)

![](img/005.png)

- Nombre elegido (`ZBD-RobertOliveros`).

![](img/006.png)

![](img/007.png)

- Finalizamos la zona.

![](img/008.png)

![](img/009.png)

### 2. Crear una zona de busqueda inversa

![](img/010.png)

- Empezamos la creacion de la nueva zona con ayuda del asistente.

![](img/011.png)

![](img/012.png)

![](img/0013.png)

- En la id. de red `172.19.26`.

![](img/014.png)

![](img/015.png)

- Finalizamos la zona.

![](img/016.png)

![](img/017.png)

### 3. Configurar reenviadores de DNS

![](img/024.png)

![](img/025.png)

El funcionamiento de esto es el siguiente:

- Los reenviadores de `DNS publico` serviran de puerta para que el servidor pueda pedir respuestas a preguntas que no esten dentro de su red, por ejemplo, si el cliente hace alguna operacion y necesita respuesta fuera de la red que conforman `servidor-cliente` utilizara el servidor y este utilizara los reenviadores.

- Si hacemos alguna operacion `nslookup` con el cliente hacia afuera podemos comprobar los reenviadores.

![](img/052.png)  

### 4. Configurar el servidor DNS Cache

- Para ello es necesario la configuracion estatica tanto de server como de cliente, en la que el cliente tendra como DNS la ip del server.

- Servidor:

![](img/018.png)

- Cliente:

![](img/019.png)

- Sus configuraciones:

![](img/020.png)

![](img/021.png)

- Comprobacion del funcionamiento DNS Cache en servidor:

![](img/026.png)

![](img/027.png)

- Comprobacion del funcionamiento DNS Cache en cliente:

![](img/028.png)

![](img/029.png)

### 5. Configurar el servidor DNS Maestro

 En la zona de búsqueda directa añadir los siguientes registros:
- Un alias para tu servidor denominado server.

![](img/030.png)

![](img/031.png)

![](img/032.png)

- Una impresora con IP fija denominada printer.

![](img/033.png)

- Un servidor de correo (ficticio) denominado correo, asociado a una dirección en tu servidor.

![](img/034.png)

![](img/035.png)

Cada vez que creamos un Host(A) creamos los `registros PTR` que aparecen en la `ZBI`.

![](img/036.png)

- Crear una subzona denominada servicios (dominio nuevo) y agregar a ésta un servidor `ftp` (asociado a la misma IP del servidor), una `impresora` nueva (con una IP fija) y el equipo del `administrador` del sistema (también con IP fija).

![](img/037.png)

![](img/038.png)

![](img/039.png)

![](img/040.png)

![](img/041.png)

![](img/042.png)

### 6. Comprobar que se resuelven los nombres desde el servidor.

- Registros ZBD.

![](img/053.png)

- Registros Servicios.

![](img/054.png)

- registros ZBI.

![](img/046.png)

### 7. Comprobar que se resuelven los nombres desde el cliente.

Primero comprobamos que el cliente esta en el dominio y aparece en la zona de busqueda del servidor como registro A.

![](img/043.png)

![](img/047.png)

- Registros ZBD.

![](img/049.png)

- Registros Servicios.

![](img/050.png)

- registros ZBI.

![](img/051.png)
