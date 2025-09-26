# 1. Conociendo el servidor Linux

> En este apartado se recogen las capturas de pantalla y los comentarios de cada ejercicio realizado.
> Las imágenes están en la carpeta `img/`. 
---

## Hostname

Comandos y salidas:
- `hostname` → nombre corto del host.
- `hostname -I` → direcciones IP de la máquina.
- `hostname -f` → FQDN (si está configurado).

**Captura**
![Hostname - salida de hostname](img/hostname.png)

**Comentario**
> Se ve el nombre de la máquina y sus direcciones IP.

---

## Cambio Hostname

- `hostnamectl` → ver y cambiar hostname sin reiniciar.
- `cat /etc/hostname` → archivo con el nombre persistente.

**Captura**
![Cambio de hostname](img/cambiar-hostname.png)  
> Se observa el nuevo nombre configurado con `hostnamectl`.

---

## Versión del sistema

Comandos:
- `lsb_release -a`
- `cat /etc/os-release`
- `cat /etc/debían_version`

**Captura**
![Versión del sistema](img/version_sistema.png)

**Comentario**
> Indica la versión de Linux instalada.

---

## Versión del kernel y arquitectura

Comandos:
- `uname -a`
- `uname -r`

**Captura**
![Versión núcleo](img/versionNucleo.png)

**Comentario**
> Se ve la versión exacta del kernel.

---

## Memoria RAM

Comandos:
- `free -h`

**Captura**
![Memoria RAM](img/MemoriaRAM.png)

**Comentario**
> Se aprecia la memoria usada y disponible.

---

## CPU

Comandos:
- `lscpu`
- `nproc`

**Captura**
![CPU](img/CPU.png)

**Comentario**
> Se ven los núcleos y características del procesador.

---

## Discos y particiones

Comandos:
- `lsblk`
- `lsblk -f`
- `sudo fdisk -l` (si procede)

**Captura**
![Discos y particiones](img/DiscosYPars.png)

**Comentario**
> Se listan los discos y sus particiones.

---

## Sistemas montados

Comandos:
- `df -h`
- `df -hT`

**Captura**
![Sistemas montados](img/sistemas_montados.png)

**Comentario**
> Indica el espacio ocupado y libre en cada partición.

---

## Tamaño de carpetas

Comandos:
- `du -h`
- `du -hs /home`
- `du -hs /home/*`

**Captura**
![Tamaño de carpeta](img/tamaño_carpeta.png)

**Comentario**
> Se ve cuánto ocupa cada directorio dentro de `/home`.

---

## Usuarios y grupos

Comandos / ficheros:
- `getent passwd` (o `cat /etc/passwd`)
- `getent group` (o `cat /etc/group`)
- `getent shadow` (acceso restringido)

**Capturas**
- Usuarios: ![Usuarios](img/usuarios-grupos.1.png)
- Grupos: ![Grupos](img/usuarios-grupos.2.png)
- Comandos getent: ![getent](img/usuarios-grupos.3.png)
- Ejemplo de /etc/shadow (si procede): ![etc/shadow](img/usuarios-grupos.4.png)

**Comentario**
> Se observan las cuentas y grupos configurados.

---

## Información de la red

Comandos:
- `ip a` → tarjetas, IPs, estado UP/DOWN.
- `ip r` → ruta por defecto (gateway).
- `ping -c 4 <puerta_enlace>`
- `ping -c 4 google.es`
- `nslookup google.es` / `nslookup 8.8.8.8` (comprobar servidor DNS)

**Capturas**
- Salida `ip a`,`ip r` , gateway y pings: ![ip a](img/info-red-1.png)
- Salida `nslookup google.es` / `nslookup 8.8.8.8`: ![ip r](img/info-red-2.png)


**Comentario**
> En `ip a` subrayar la tarjeta de red (ej. `enp0s3`) y la IP asignada; en `ip r` subrayar la puerta de enlace.  
> En el inspector de red incluir la traza completa (orden, status HTTP, tamaño y tiempo) y marcar la petición principal (200/404/302).

---

## Configuración de la red

- `cat /etc/network/interfaces`
- `cat /etc/network/resolv.conf`

**Captura**
- Configuración de red (ej. `/etc/network/interfaces`): ![Conf.Red](img/config-red.png)

**Comentario**
> 


---

## Reinicio de red

- `systemctl status networking`
- `systemctl restart networking`

**Captura**
- Reinicio de red: ![Reinicio.Red](img/reiniciar-red.png)

---

## Configuración de la red: Otra forma

- `cat /etc/resolv.conf`

- Configuracíón de red(otra forma): ![Conf.Red.otra](img/reiniciar-red-otra.png) 

**Comentario**
> Este archivo guarda los servidores DNS. Si tienes instalado resolvconf, se actualizará automáticamente según la configuración indicada.



