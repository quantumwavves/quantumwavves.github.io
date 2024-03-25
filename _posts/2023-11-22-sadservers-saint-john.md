---
layout: post
title: Saint John Sad Servers
subtitle: Resolucion de la maquina saint john de sad servers.
header-img: img/in-post/sadservers/saint-john/header.webp
header-style: image
header-mask: rgba(0, 0, 0, .4)
catalog: true
tags:
  - sadservers
  - linux
  - troubleshoting
---

<!-- HTML Meta Tags -->
<title>Saint John Sad Servers - QuantumWavves</title>
<meta name="description" content="Resolución de la máquina Saint John de Sadservers.">

<!-- Facebook Meta Tags -->
<meta property="og:url" content="https://quantumwavves.github.io/2023/11/22/sadservers-saint-john/">
<meta property="og:type" content="website">
<meta property="og:title" content="Saint John Sad Servers - QuantumWavves">
<meta property="og:description" content="Resolución de la máquina Saint John de Sadservers.">
<meta property="og:image" content="https://quantumwavves.github.io/img/in-post/sadservers/saint-john/header.webp">

<!-- Twitter Meta Tags -->
<meta name="twitter:card" content="summary_large_image">
<meta property="twitter:domain" content="quantumwavves.github.io">
<meta property="twitter:url" content="https://quantumwavves.github.io/2023/11/22/sadservers-saint-john/">
<meta name="twitter:title" content="Saint John Sad Servers - QuantumWavves">
<meta name="twitter:description" content="Resolución de la máquina Saint John de Sadservers.">
<meta name="twitter:image" content="https://quantumwavves.github.io/img/in-post/sadservers/saint-john/header.webp">

## Escenario
- Tipo: `Fix`
- Dificultad: `Fácil`
- OS: `Debian 11`
- Descripción: Un desarrollador ha creado un programa de pruebas que está escribiendo continuamente en un archivo de registro /var/log/bad.log y llenando el disco. Puede comprobarlo, por ejemplo, con tail -f /var/log/bad.log.
Este programa ya no es necesario. Búscalo y termínalo.
- Tiempo para resolver: 10 minutos.

## Solución

### Comprobando el contenido del log

```ruby
admin@i-0f0f88adaca3a6413:~$ tail -f /var/log/bad.log
2023-11-26 01:30:24.674537 token: 1042100318
2023-11-26 01:30:24.974971 token: 1489633634
2023-11-26 01:30:25.275387 token: 596091179
2023-11-26 01:30:25.575799 token: 1326033134
2023-11-26 01:30:25.876198 token: 1261829972
2023-11-26 01:30:26.176608 token: 1431147608
2023-11-26 01:30:26.477018 token: 1739306965
2023-11-26 01:30:26.777433 token: 1801514668
2023-11-26 01:30:27.077834 token: 934257659
2023-11-26 01:30:27.378233 token: 1765170710
2023-11-26 01:30:27.678642 token: 1731989046
2023-11-26 01:30:27.979075 token: 776788644
2023-11-26 01:30:28.279959 token: 592100110
2023-11-26 01:30:28.580850 token: 1792490108
2023-11-26 01:30:28.881730 token: 1026630811
2023-11-26 01:30:29.182622 token: 1869422293
2023-11-26 01:30:29.483507 token: 177398155
2023-11-26 01:30:29.784364 token: 816040937
2023-11-26 01:30:30.084911 token: 679360542
2023-11-26 01:30:30.385802 token: 1938468024
2023-11-26 01:30:30.686298 token: 783990644
2023-11-26 01:30:30.987025 token: 1159555988
2023-11-26 01:30:31.287726 token: 88099705
2023-11-26 01:30:31.588447 token: 2057841797
```
### Uso del comando lsof

`lsof` es una conocida herramienta de monitorización de sistemas operativos tipo Unix que se utiliza para mostrar todos los archivos de disco que mantienen abiertos los procesos, incluyendo los sockets de red abiertos, pipes, entre otros tipos. Haremos uso del comando lsof y utilizaremos una pipe para realizar una busqueda con el comando `grep` pasandole como argumento el archivo mencionado que es `badlog.py`.

```ruby
admin@i-0f0f88adaca3a6413:~$ lsof -f | grep bad.log
badlog.py 589   admin    3w   REG   259,1    23539 265802 /var/log/bad.log
```
Notamos que existe una coincidencia, que tiene el asignado el numero 589 como `PID`.

### Matando el proceso

Para terminar el proceso utilizaremos el comando `kill` el cual mandara una señal para terminar el proceso.

```ruby
admin@i-0f0f88adaca3a6413:~$ kill 589
```
## Resultado

Cuando revisamos nuestra solución la pagina nos dice que es la correcta.

![solucion](/img/in-post/sadservers/saint-john/solution.webp)

Eso ha sido todo por este post, si piensas que me he equivocado con la información o que he omitido algo, no dudes en contactarme por discord `quantumwavves`.
