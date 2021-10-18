# Servidor DNS Linux bind9

**PLANTEAMIENTO:**

Realizar la instalación y configuración de un servidor DNS bind9 en una máquina de Linux y configurar tanto servidor cache como maestro definiendo las zonas directas e indirectas junto a comprobaciones en un cliente.

| MV | IP   |
| :------------- | :------------- |
| **MAESTRO/** oliveros26g2      | 172.19.26.20        |
| **CLIENTE/** oliveros26g1      | 172.19.26.21       |

### Instalación de servicio bind9

- Instalamos el `bind9` y comprobamos el estado del servicio.

![](img/002.png)

![](img/003.png)

![](img/004.png)

- Indicar a Linux que el servidor DNS es él mismo `(/etc/resolv.conf)`

- **ACLARACIÓN:** Aunque editáramos este archivo o incluso el archivo real, ya que este se trata de un enlace simbólico no se guardaria la configuración por algun problema que desconozco, al final tuve que cambiar un archivo que nos definía la configuración de red estáticamente en la máquina: `/etc/netplan/01-network-manager-all.yanl`.

![](img/007.png)

![](img/008.png)

**!! Siempre reiniciaremos después de un cambio realizado!!**

>También debemos definir el DNS del cliente con la IP del maestro.

---

### Configurar servidor como caché DNS

- Tenemos que añadir `reenviadores` al archivo de configuración al que previamente hacemos una copia de seguridad.

![](img/009.png)

![](img/010.png)

---

### Comprobaciones desde el maestro

![](img/011.png)

### Comprobaciones desde el cliente

![](img/012.png)

---

### Configurar como DNS maestro

- Para configurar las zonas de búsqueda directa e inversa tenemos que modificar el archivo `/etc/bind/named.conf.local`.

- Copiamos el archivo por seguridad.

![](img/013.png)

- Definimos la `ZBD (db.local)` y `ZBI (db.172.19)`.

![](img/014.png)

---

### Crear un archivo de búsqueda directa y otro de búsqueda inversa

`ZBD (db.local)`

- Donde definimos nuestro propio `servidor`, un `router` y un `pc`.

![](img/016.png)

- Comprobamos que el archivo está configurado correctamente.

![](img/015.png)

`ZBI (db.172.19)`

- Definimos nuestro propio `servidor`, un `printer` y un `router`.

![](img/019.png)

- Comprobamos que el archivo está configurado correctamente.

![](img/020.png)

---

### Comprobar que se resuelven los nombres desde la consola del servidor

`ZBD`

![](img/018.png)

![](img/022.png)

> Algunos dominios no funcionan, ya que son ficticios.

`ZBI`

![](img/021.png)

---

### Comprobar que se resuelven los nombres desde la consola del cliente.

`Ping a master y ZBD`

![](img/023.png)

`ZBI`

![](img/024.png)
