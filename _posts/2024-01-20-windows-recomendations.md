---
layout: post
title: RECOMENDACIONES PARA WINDOWS.
subtitle: Recomendaciones para un sistema windows y privacidad para el uso cotidiano.
header-img: img/in-post/guias/windows_tips/header.webp
header-style: image
header-mask: rgba(0, 0, 0, .4)
catalog: true
tags:
  - windows
  - microsft
  - debloat
  - privacidad
---
## Introducción

Estas son recomendaciones que propongo para los usuarios del sistema operativo `Windows`, sabemos que el sistema operativo no es de codigo libre y tiene demasiadas restricciones que no favorecen a la libertad del usuario. Sin embargo he de admitir que es utopico pensar que estos mismos usuarios migren a otros sistemas que favorezcan su libertad como lo son `GNU/Linux` y `BSD`. Es por ello que en este post compartire herramientas hechas por la comunidad, de codigo abierto y `gratis`. Este post esta decicado a aquellas personas no tan tecnicas, por lo que no necesitaras conocimientos avanzados, ademas de que constantemente este post se actualizara y traere video tutoriales para las diferentes herramientas utilizadas en este post. 

## Debloat 

### [Winutil](https://github.com/ChrisTitusTech/winutil)

Esta utilidad es una compilación de scripts para Windows. Su objetivo es agilizar las instalaciones, eliminar errores relacionados con el sistema operativo, solucionar problemas con la configuración y corregir las actualizaciones de Windows. Esta utilidad es 100% Open source y puedes consultar el repositorio y el codigo del mismo.

#### Como utilizar:

Necesitaras permisos administrativos para powershell. Copia y pega el siguiente comando en powershell. 

```shell
iwr -useb https://christitus.com/win | iex
```
![winutil](/img/in-post/guias/windows_tips/ctt.webp)

### Ajustes que recomiendo:

#### Tweaks:

La herramienta ya tiene tweaks pre configurados para equipos de escritorio y laptops. Solo es necesario seleccionar el tipo de equipo. Adicionalmente, puedes configurar el servidor DNS de tu preferencia. Cloudflare es uno de los mejores.

![ctt-tweaks](/img/in-post/guias/windows_tips/ctt-tweaks.webp)

Estas son las configuraciones por defecto para escritorio (en laptop son casi las mismas, exceptuando la hibernación)

![winutil](/img/in-post/guias/windows_tips/ctt-tweaks-default.webp)

#### Actualizaciones:

Se recomienda utilizar las actualizaciones de seguridad, estas son las mínimas para que el sistema operativo pueda funcionar y para no llenar de bloatware el sistema operativo.

![winutil](/img/in-post/guias/windows_tips/ctt-updates.webp)

#### Configuraciones adicionales:

Algunas de las configuraciones adicionales que recomiendo son las siguientes:

- All .NET Framework (Es necesario para muchas aplicaciones o programas)
- HyperV (Siempre y cuando no tengas un hypervisor tipo VirtualBox o VMware)
- Windows Subsystem For Linux 2 (útil si estás estudiando informática u otros campos a fines de la computación)

![winutil](/img/in-post/guias/windows_tips/ctt-config.webp)


### [XToolBox](https://github.com/xemulat/XToolbox)

Xtoolbox es una herramienta CLI (Command Line) que recopila scripts, programas y archivos de instalación para diferentes sistemas operativos. El proyecto es open source, pero no todo el software que se encuentra en la herramienta es de código abierto. Quedan bajo la responsabilidad del usuario las herramientas o scripts que se usen.


![menu](/img/in-post/guias/windows_tips/xtool1.webp)
![menu](/img/in-post/guias/windows_tips/xtool2.webp)
![menu](/img/in-post/guias/windows_tips/xtool3.webp)

### [Hellzerg optimizer](https://github.com/hellzerg/optimizer)

Optimizer, una utilidad de configuración avanzada diseñada para mejorar su privacidad y seguridad en Windows. Se recomienda encarecidamente el uso de esta herramienta después de una nueva instalación de Windows para obtener los máximos beneficios de privacidad y seguridad. Dependiendo de su versión de Windows, Optimizer también puede ayudarle a aplicar ajustes específicos del sistema.

![menu](/img/in-post/guias/windows_tips/hellzerg.webp)

### [ET optimizer](https://github.com/semazurek/ET-Optimizer)

ET es un programa en Batch/PowerShell con interfaz grafica para mejorar el rendimiento,hacer debloat, optimizar y mejorar la privacidad para Windows 10/11. El proyecto es open source.

El proyecto tiene pre configuraciones por cada una de sus pestañas como lo son performance, visual o privacy. Por lo que solo tendras que seleccionar una categoria de ajustes que necesites:

![menu](/img/in-post/guias/windows_tips/et-optimizer.webp)

### [Mem Reduct](https://github.com/henrypp/memreduct)

Mem reduct es un proyecto open source que nos ayuda a liberar memoria (RAM) que podría estar en caché. Puedes asignarle configuraciones con base en porcentajes o periodos de tiempo.


![menu-mr](/img/in-post/guias/windows_tips/mr-menu.webp)

#### Configuraciones:

Configuraciones para el inicio:

![menu](/img/in-post/guias/windows_tips/mr-setting-1.webp)

Configuraciones para la limpieza de memoria:

![menu](/img/in-post/guias/windows_tips/mr-setting-2.webp)

Configuraciones para las notificaciones:

![menu](/img/in-post/guias/windows_tips/mr-setting-3.webp)


## Package Manager

### [Scoop](https://scoop.sh/)

Scoop es un gestor de paquetes que te permite administrar programas para Windows mediante la terminal o shell (powershell) permitiéndote instalación, actualización y eliminación de los paquetes. Estos son algunos de los beneficios que brinda scoop:

- Elimina las ventanas emergentes de permisos.
- Oculta los instaladores tipo asistente GUI
- Evita la contaminación del PATH al instalar muchos programas.
- Evita efectos secundarios inesperados al instalar y desinstalar programas.
- Busca e instala automáticamente las dependencias.
- Realiza todos los pasos de instalación adicionales para obtener un programa que funcione.

#### Instalación

Cambiar la politica de ejecución para la instalación:


```shell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```
Instalación de scoop:


```shell
Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
```
Adicionalmente se recomienda instalar `GIT` ya que es utilizado para el clonado de repositorios y actualizaciones.

```shell
scoop install git
````

#### Uso:

##### Buckets:

Agregar Bucket (repositorios) se utilizara como ejemplo el bucket `extras`, para conocer todos los buckets y los paquetes aqui: [BUCKETS](https://scoop.sh/#/buckets)

```shell
scoop bucket add extras
```
##### Instalación de programas 

Se utilizara como ejemplo firefox, para conocer todos los paquetes disponibles aqui: [PACKAGES](https://scoop.sh/#/apps)

```shell
scoop install firefox
```

##### Eliminación de programas: 

```shell
scoop uninstall firefox
```

##### Actualizar todos los paquetes:

```shell
scoop update -a
```
#### Video tutorial: `Proximamente`

## Privacidad

### [Privatezilla](https://github.com/builtbybel/privatezilla)

Privatezilla integra las configuraciones de privacidad más críticas de Windows 10 y le permite realizar rápidamente una comprobación de privacidad con respecto a estas configuraciones. Los ajustes activos se marcan con el estado "Configurado" e indican que su privacidad está protegida.

![menu](https://raw.githubusercontent.com/builtbybel/privatezilla/master/assets/intro.gif) 

### [Windows SPY Blocker](https://github.com/crazy-max/WindowsSpyBlocker)

WindowsSpyBlocker es una aplicación escrita en Go y entregada como un único ejecutable para bloquear el espionaje y el rastreo en sistemas Windows.

El planteamiento de este proyecto consiste en capturar e interpretar el tráfico de red basándose en un conjunto de herramientas. Dependiendo de las interacciones entre los servicios y el origen o destino del tráfico, se crean reglas y se ordenan por asignación.

![menu](/img/in-post/guias/windows_tips/wsb.webp)

## FOSS

### [Localsend](https://localsend.org/#/)

Comparte archivos a dispositivos cercanos. Gratis, código abierto, multiplataforma. Utiliza el pricipio basico de los protocolos de internet, como podrian ser http, ftp, scp, rsync, etc. Aplicados a una red local (LAN). Se plantea como una alternativa a Airdrop.

![localsend-phone](https://camo.githubusercontent.com/eaa4cf1da606c1bda895ed53bf80fe2fdd482db722127dcae1212df7f46d6f0e/68747470733a2f2f6c6f63616c73656e642e6f72672f696d672f73637265656e73686f742d6970686f6e652e77656270)

![localsend-win](https://camo.githubusercontent.com/ae6887f68d68f9b4c7ba863db039adcf9c710b92ab8d77261f08ed09a9f6c6c4/68747470733a2f2f6c6f63616c73656e642e6f72672f696d672f73637265656e73686f742d70632e77656270) 
