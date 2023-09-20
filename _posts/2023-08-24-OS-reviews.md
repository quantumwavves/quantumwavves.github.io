---
layout: post
title: LISTA DE SISTEMAS OPERATIVOS.
subtitle: Una pequeña guia sobre SO.
header-img: img/in-post/os_guide/void.webp
header-style: image
header-mask: rgba(0, 0, 0, .4)
catalog: true
tags:
  - sistema-operativo
  - windows
  - linux
  - bsd
  - macos
---

## CONCEPTOS

### ¿Qué es un sistema operativo?

<p style="text-align: justify">
El sistema operativo es un conjunto de programas especializados que gestionan todas las operaciones de una computadora. Controla y supervisa la ejecución de todos los demás programas que residen en el pc, lo que también incluye programas de aplicación. El sistema operativo ayuda a que una aplicación interactúe con la parte hardware sin conocer la configuración real del hardware.
</p>

### Funciones del sistema operativo:

- Gestión de recursos: El sistema operativo gestiona y asigna memoria, tiempo de CPU y otros recursos de hardware entre los distintos programas y procesos que se ejecutan en el ordenador.
- Gestión de procesos: El sistema operativo es responsable de iniciar, detener y gestionar los procesos y programas. También controla la programación de los procesos y les asigna recursos.
- Gestión de la memoria: El sistema operativo gestiona la memoria primaria del ordenador y proporciona mecanismos para optimizar el uso de la memoria.
- Seguridad: El sistema operativo proporciona un entorno seguro para el usuario, las aplicaciones y los datos mediante la aplicación de políticas y mecanismos de seguridad como los controles de acceso y el cifrado.
- Contabilidad de trabajos: Realiza un seguimiento del tiempo y los recursos utilizados por los distintos trabajos o usuarios.
- Gestión de archivos: El sistema operativo se encarga de organizar y gestionar el sistema de archivos, incluyendo la creación, eliminación y manipulación de archivos y directorios.
- Gestión de dispositivos: El sistema operativo gestiona los dispositivos de entrada/salida, como impresoras, teclados, ratones y pantallas. Proporciona los controladores e interfaces necesarios para permitir la comunicación entre los dispositivos y el ordenador.
- Redes: El sistema operativo proporciona capacidades de red como establecer y gestionar conexiones de red, manejar protocolos de red y compartir recursos como impresoras y archivos a través de una red.
- Interfaz de usuario: El sistema operativo proporciona una interfaz de usuario que permite a los usuarios interactuar con el sistema informático. Puede ser una interfaz gráfica de usuario (GUI), una interfaz de línea de comandos (CLI) o una combinación de ambas.
- Copia de seguridad y recuperación: El sistema operativo proporciona mecanismos para hacer copias de seguridad de los datos y recuperarlos en caso de fallos, errores o desastres del sistema.
- Virtualización: El sistema operativo proporciona capacidades de virtualización que permiten ejecutar varios sistemas operativos o aplicaciones en una única máquina física. Esto puede permitir un uso eficiente de los recursos y flexibilidad en la gestión de las cargas de trabajo.
- Monitorización del rendimiento: El sistema operativo proporciona herramientas para supervisar y optimizar el rendimiento del sistema, incluida la identificación de cuellos de botella, la optimización del uso de recursos y el análisis de registros y métricas del sistema.
- Tiempo compartido: El sistema operativo permite que varios usuarios compartan simultáneamente un sistema informático y sus recursos mediante mecanismos de tiempo compartido que asignan los recursos de forma justa y eficiente.
- Llamadas al sistema: El sistema operativo proporciona un conjunto de llamadas al sistema que permiten a las aplicaciones interactuar con el sistema operativo y acceder a sus recursos. Las llamadas al sistema proporcionan una interfaz estandarizada entre las aplicaciones y el sistema operativo, lo que permite la portabilidad y la compatibilidad entre diferentes plataformas de hardware y software.
- Ayudas para la detección de errores: Contienen métodos que incluyen la producción de volcados, trazas, mensajes de error y otros métodos de depuración y detección de errores.

## WINDOWS OS

### Windows 10 LTSB 2016

<img src="/img/in-post/os_guide/win_os/win-10-ltsb-2016.png" onclick="window.open(this.src)">

#### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga oficial: | No existe, se puede tener acceso a la ISO mediante una suscripción a Visual Studio. |
| Requisitos mínimos: | Indicados por microsoft <a href="https://www.microsoft.com/es-xl/windows/windows-10-specifications">microsoft.com</a> |
| CPU: | Procesador a 1 GHz o más rápido o sistema en un chip (SoC).|
| RAM: | 1 GB RAM para 32 bits o 2 GB para 64 bits.|
| STORAGE: | 16 GB ROM para SO de 32 bits; 32 GB para SO de 64 bits.|
| GRAPHICS: | DirectX 9 o posterior con controlador WDDM 1.0.|
| Última versión y compilación: |1607 (14393.5427).|
| Año de lanzamiento: | 2016.|
| Arquitectura: | 64 y 32 bits.|

#### Características

|PROS|CONTRAS|
|-|-|
| Soporte extendido hasta 13 de octubre de 2026. | No cuenta con Microsoft Store, pero se le puede instalar. |
| Versión 1607, al ser una de las primeras versiones el sistema no contiene las mismas características y servicios que una actual como la 21H2 o 22H2. | Actualizar por primera vez el sistema toma su tiempo. |
No contiene bloatware. | Difícilmente encontrarás la ISO con sus hashes de verificación, por lo que la forma más segura de descargar el archivo ISO es con una suscripción enterprise a visual studio. |
| Ideal para un equipo de bajos recursos ya que la versión de esta rama es utilizada en cajeros o equipos médicos que requieren estabilidad para estar funcionando constantemente. | No tiene updates de nuevas características. |
| Instalación gráfica. | Para activar este sistema debes adquirir los servicios de volumen de licencia que Microsoft ofrece. |
| WD Cloud, protección de sincronizada con la nube. | Es necesario instalar el framework de .NET para ciertas aplicaciones y los MSVC (Microsoft visual C++) ya que no vienen nativamente en el SO. |
| App-V, virtualización de aplicaciones. | |


### Windows 10 LTSC 2021

<img src="/img/in-post/os_guide/win_os/win-10-ltsc-2021.png" onclick="window.open(this.src)">

#### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga: | Disponible al tener suscripción a Visual Studio. |
| Requisitos mínimos windows 10: | Especificados por microsoft <a href="https://www.microsoft.com/es-xl/windows/windows-10-specifications">microsoft.com</a>
| CPU: | Procesador a 1 GHz o más rápido o sistema en un chip (SoC) |
| RAM: |1 GB RAM para 32 bits o 2 GB para 64 bits |
| ROM | 16 GB ROM para SO de 32 bits; 32 GB para SO de 64 bits |
| GRAPHICS: | DirectX 9 o posterior con controlador WDDM 1.0 |
| Año de lanzamiento: | 2021 |
| Última versión y compilación: | 21H2 (19044.2364). |
| Arquitectura: | 64 y 32 bits. |

#### Características

| PROS | CONTRAS |
|-|-|
| Soporte hasta el 12 de junio de 2027. | No tiene actualizaciones de nuevas características. |
| No contiene bloatware. | No tiene Microsoft Store pero se puede instalar. |
| Instalación Gráfica. | Para activar este sistema debes adquirir los servicios de volumen de licencia que Microsoft ofrece. |
| Penúltima versión hasta la fecha. | |
| Es utilizada principalmente por las empresas en sus equipos debido a su estabilidad. | |
| Consumo de recursos menor que su sucesor windows 11. | |
| No tiene como requisitos el módulo TPM 2.0 ni el secure boot. | |
| Es 137% seguro que Windows 11, en su última versión. | |


### Windows 10 HOME/PRO

<img src="/img/in-post/os_guide/win_os/win-10-pro.png" onclick="window.open(this.src)">

#### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga: | <a href="https://www.microsoft.com/es-mx/software-download/windows10ISO">microsoft.com</a> |
| Requisitos mínimos windows 10: | Especificados por microsoft <a href="https://www.microsoft.com/es-xl/windows/windows-10-specifications">microsoft.com</a> |
| CPU: |Procesador a 1 GHz o más rápido o sistema en un chip (SoC)|
| RAM: |1 GB RAM para 32 bits o 2 GB para 64 bits |
| ROM: |16 GB ROM para SO de 32 bits; 32 GB para SO de 64 bits |
| GRAPHICS: |DirectX 9 o posterior con controlador WDDM 1.0  |
|Año de lanzamiento: | 2015. |
|Última versión y compilación: | 21H2 (19044.2364). |
|Arquitectura: | 64 y 32 bits. |

#### Características

| PROS | CONTRAS |
|-|-|
| Soporte hasta el 14 de octubre 2025. | No tiene actualizaciones de nuevas características. |
| No necesitas servicios de licenciamiento por volumen para activar tu instalación | Contiene una cantidad absurda de bloatware |
| Instalación Gráfica. | Solo añadieron soporte a la versión 22H2 hasta 2025, no hubo nuevas características |
| Ultima versión hasta la fecha. | |
| Consumo de recursos menor que su sucesor windows 11. | |
| No tiene como requisitos el módulo TPM 2.0 ni el secure boot. | |

### Windows 11 HOME/PRO

<img src="/img/in-post/os_guide/win_os/win-11.png" onclick="window.open(this.src)">

#### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga oficial: | <a href="https://www.microsoft.com/es-es/software-download/windows11">microsoft.com</a> |
| Requisitos minimos: | Especificados por microsoft <a href="https://www.microsoft.com/en-us/windows/windows-11-specifications">microsoft.com</a>
| CPU: | Procesador 1 giga Hertz (GHz) o más rápido con 2 o más núcleos en un procesador de 64 bits compatible o sistema en un chip (SoC). |
| RAM: | 4 gigabytes (GB). |
| ROM | Dispositivo de almacenamiento de 64 GB o más. |
| UEFI: | Compatible con Arranque seguro. |
| TPM 2.0: | Si |
| GRAPHICS: | Tarjeta gráfica compatible con DirectX 12 o posterior con controlador WDDM 2.0. |
| Año de lanzamiento: | 2021 |
| Última versión y compilación: | 22H2 (22621.963) |
| Arquitectura: | 64 bits |

#### Características

|PROS|CONTRAS|
|-|-|
| Rediseño total de la interfaz de usuario para windows. |  Consume un poco más de recursos a comparación de windows 10 pero nada alarmante. |
| Instalación gráfica.|  No todos los procesadores tienen compatibilidad con el sistema. |
| Añadidas nuevas características como: Carpetas en el menú de windows, personalización del menú de inicio, esquinas redondeadas y más aquí. |  Es un 237% más vulnerable que windows 10 en su versión 21H2. |
| Se puede actualizar desde windows 10 al 11 mediante windows update. |  Se requiere de un módulo TPM 2.0 para poder funcionar, lo que no es problema si tienes una motherboard reciente o tan vieja. |
| Se añaden constantemente nuevas características en las versiones insiders. |  Distintas funciones de windows 10 fueron removidas, aunque poco a poco están volviendo a incorporarlas. |
| WSA (Windows Subsystem For Android) Aplicaciones de android en windows [De momento solo disponible para USA]. |

### Versiones de windows que no se colocaron

- ¿Por qué no se encuentra Windows Vista, XP, 2000, etc?
  - Porque son versiones que ya no tienen soporte y además bastante desactualizadas.
- ¿Por qué no hay versiones de Windows server?
  - Porque existen demasiadas versiones de windows server Datacenter, Essentials, Standard. Están basados en builds diferentes y adquirir sus licencias o ISO’s requieren una suscripción o pago de servicios.

### EVITA los Windows MODIFICADOS.

#### ¿Por qué?
<p style="text-align:justify">Modificar y redistribuir un sistema operativo windows con fines de lucro no es legal. Sumando que las modificaciones y herramientas que incluyen son de origen totalmente desconocido .Quitando características básicas como Windows Update , UAC(User Access Control. Ejecturar programas como administrador sin confirmacion) y Windows Defender. Dejando al usuario sin actualizaciones no solo de nuevas características si no también de seguridad y esto por que se rompe el sistema con solo actualizar. La mayoría de estos sistemas no tienen el antivirus windows defender, con el argumento de “Es que consume muchos recursos” cuando puede modificarse el uso de este mismo, sin embargo es recomendable endurecer a windows defender ya que de stock carece de ser un buen antivirus. Ahora mencionando el problema más grande de estos sistemas modificados: La inestabilidad dada por eliminar servicios no vitales pero sí importantes para otros programas, malas configuraciones en el registro del sistema (regedit), corrupción  de archivos (drivers incluidos).</p>

#### MiniOS vs Debloat

##### MiniOS

<img src="/img/in-post/os_guide/shitOS.png" onclick="window.open(this.src)">

##### W10 PRO 22H2 con Debloat

<img src="/img/in-post/os_guide//W10PROD.png" onclick="window.open(this.src)">

##### Conclusiones:

`Hazle debloat a tu Instalación, no seas gay`{: .error }

## AOSP Y WEB BASED OS

### Fyde OS

<img src="/img/in-post/os_guide/aosp_os/fyde-os.png" onclick="window.open(this.src)">

#### Ficha tecnica

|Componente|Ficha tecnica|
|-|-|
| Link de descarga: | <a href="https://fydeos.io/download/">fydeos.io</a> |
| Requisitos mínimos: | Aun que no los explica, contiene unas instrucciones en base al cpu de tu PC: <a href="https://fydeos.io/faq/how-to-choose-fydeos-release-and-how-to-run-fydeos">fydeos.io.faq</a> Sin embargo, tomaremos los de Chrome OS como referencia |
| CPU: | Intel o AMD x86-64-bit |
| RAM: | 4 GB |
| Storage: | 16 GB |
| Última versión: | 15.1. |
| Año de lanzamiento: | 2016. |
| Arquitectura: | 64 bits, OVA, ARM. |

#### Características

| PROS | CONTRAS |
|-|-|
| Sistema operativo ligero que lleva un kernel Linux, está impulsado por la plataforma web y la tecnología de contenedores. Basado en el proyecto Chromium. | Se necesitará un tiempo de adaptación si vienes de un sistema windows. |
| Instalación gráfica. | No hay compatibilidad gratuita con windows apps. |
| Facilidad para configurar las Android Apps con Open GApps (Servicios de google). | WINE puede presentar problemas. |
| Soporta aplicaciones de linux. | |
| Se puede instalar en microcomputadoras ARM como una Raspberry Pi. | |
| Open Source: <a href="https://openfyde.io/">source</a> | |
| Una buena alternativa a Chrome OS. | |
| Interfaz intuitiva. | |

### Prime OS
<img src="/img/in-post/os_guide/aosp_os/prime-os.png" onclick="window.open(this.src)">

#### Ficha tecnica

|Componente|Ficha tecnica|
|-|-|
| Link de descarga: | <a href="https://www.primeos.in/download/">primeos.in</a>|
| Requisitos mínimos: | Aunque no se indica en la página oficial, diferentes sitios han hecho pruebas sobre diferente hardware llegando a uno mínimo: <a href="https://getandroidemulator.com/primeos-android-emulator-system-requirements-featuers/">primeos-system-requieriments</a> Se recomienda ampliamente la versión Standard para evitar problemas de compatibilidad. |
| Última versión: | 2.1.3. |
| Año de lanzamiento: | 2019. |
| Arquitectura: x86 (32 bits), ARM |

#### Características

|PROS|CONTRAS|
|-|-|
| Funciones de mapeo para gamepads. | No se pueden utilizar aplicaciones x86-64 (Aplicaciones de escritorio). |
| Instalación semigrafica, CLI (Command Line) | La versión classic puede tener problemas con los controladores wifi (Recomendable utilizar la versión estándar). |
| Servicios de Google incluidos (play store). | Aunque puedas utilizarlo en un equipo viejo, no quiere decir que va a correr los juegos mejor que tu celular, eso depende completamente del hardware. |
| Creado con el fin de tener un sistema con base android para poder jugar sin los contras de la virtualización/emulación. |
| Utiliza el escritorio con el que viene Chrome OS. |
| Ventaja poder jugar con el SO sin miedo a baneos por uso de emuladores. |


### Chrome OS
<img src="/img/in-post/os_guide/aosp_os/chrome-os.png" onclick="window.open(this.src)">

#### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Guía de instalación: | <a href="https://support.google.com/chromeosflex/answer/11541904?hl=en&ref_topic=11551271"> support.google.com </a>|
| Extensión para la creación del medio booteable: | <a href ="https://chrome.google.com/webstore/detail/chromebook-recovery-utili/pocpnlppkickgojjlmhdmidojbmbodfm"> chromebook-recovery-utility</a> |
| Requerimientos mínimos especificados en la guía de instalación de Chrome OS: | Arquitectura: dispositivo compatible Intel o AMD x86-64-bit. |
| RAM: | 4 GB. |
| Storage: | 16 GB. |
| GPU: | Los componentes fabricados antes de 2010 pueden resultar en una mala experiencia. |
| Año de lanzamiento: | 2022. |
| Última versión: | 96.4. |
| Arquitectura: | 64 bits. |
| Diferencias entre Chrome OS y Chrome OS Flex explicadas por Google: | <a href="https://support.google.com/chromeosflex/answer/11542901?hl=en"> aqui.</a> |

#### Características

| PROS | CONTRAS |
|-|-|
| Consumo ridículo de recursos al menos en máquina virtual, puede cambiar dependiendo del hardware. |  A diferencia de Chrome OS la playstore y las android apps no son compatibles con este sistema. |
| Fluidez en el sistema. | Chrome OS está basado en su propio kernel de linux, sin embargo para poder ejecutar las Linux APPS es necesario habilitar la virtualización en el procesador ya que se creara una máquina virtual con un kernel muy ligero para hacer de capa de compatibilidad entre Chrome OS y Linux. |
| Ideal para estudiantes y profesionales que trabajen con ofimática. | No recomendable para jugar. |
| Menor consumo de recursos y energía a diferencia de Chrome OS. |
| Chrome OS Flex es un Chrome OS liteado y aún en fase beta. |
| Linux Apps, mediante virtualización. |

## GNU/LINUX OS

### FAQ

#### ¿Qué es una distribución GNU/Linux?
La versión pura de Linux es un kernel de sistema operativo, es decir, el núcleo del sistema se encarga de gestionar los recursos del hardware y facilitarles a las distintas herramientas y programas del sistema operativo. GNU es el sistema que hace uso del kernel de linux. Una distribución GNU/Linux es un conjunto de programas predefinidos con la integración del kernel.
#### ¿Qué es un flavor (sabor)?
El sabor es una característica importante de la distribución que se caracteriza por un entorno gráfico determinado con sus funcionalidades específicas y cientos de paquetes de software incorporados. Un ejemplo de esto es Ubuntu y sus diversos sabores, como lo son xubuntu, kubuntu, ubuntu mate, lubuntu.
#### ¿Qué entornos gráficos o escritorios existen?
Entre los más populares destacan KDE Plasma, XFCE, GNOME, Cinnamon, MATE, Budgie, Pantheon. La diferencia entre cada uno es el framework que utiliza y sus diferentes novedades o funciones incluidas propias de cada escritorio. Sin embargo también existen entornos gráficos sin escritorio, conocidos como gestores de ventanas (Windows Manager) son mucho más ligeros y recomendados para productividad, sin embargo se requiere mayor grado de conocimiento para su configuración. Algunos ejemplos son i3WM, Qtile, BSPWM, xmonad.
#### ¿Qué distribución es mejor que otra?
Ninguna, todas las distribuciones son parecidas entre sí, teniendo como principal diferencia el package manager que utilizan, algunos cambios en los paths de x programa o aplicación. Pero todas te permitirán hacer uso de la computadora. Utiliza la que más se ajuste a tus necesidades.

| PROS | CONTRAS |
|-|-|
| Estabilidad, Rapidez, es robusto. | Incompatibilidad con Windows: Muchos de los programas de windows no funcionan en linux. Siempre existe una alternativa open source. Sin embargo no se recomienda para actividades de diseño/edición o gaming. |
| Personalizable, Modificable, Modular y redistribuible. | Incompatibilidad con Windows: Muchos de los programas de windows no funcionan en linux. Siempre existe una alternativa open source. Sin embargo no se recomienda para actividades de diseño/edición o gaming. |
| Gratuito y con amplia documentación. | Curva de aprendizaje: Esta varía dependiendo qué tanto quiera aprender el usuario y la distribución. Un ejemplo es la dificultad para manejar una distribución como Linux Mint que es muy poca, comparado a la dificultad de utilizar una distro como Arch o Gentoo. |
| Al no tener más del 1% de la cuota de mercado en el ámbito doméstico, la existencia de virus es casi nula (a menos que instales software de terceros y con permisos de root pero hay que ser tontos), por lo que no requeriras antivirus además de que constantemente recibe actualizaciones de seguridad y soporte. | Filosofía de la distribución: Como ejemplo TRISQUEL o Slackware son distribuciones que solo hacen uso del open source, por lo que instalar software privativo es complicado. |
| Un poco más de privacidad. | |
| Gestores de paquetes: Es una herramienta por terminal para gestionar el software de un repositorio. | |

### Debian base.
#### Debian
 
<img src="/img/in-post/os_guide/gnu_os/debian.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link oficial de descarga: | <a href="https://www.debian.org/download">debian.org</a> |
| Requisitos mínimos especificados por Debian.org: | <a href="https://www.debian.org/releases/stretch/amd64/ch03s04.html.en">debian.org</a> |
| Sin escritorio | Con escritorio |
| RAM: 128MB | 256 MB RAM. |
| ROM: 2GB | 10 GB ROM. |
| Última versión: | 12 bookworm. |
| Año de lanzamiento: | 1993. |
| Arquitectura: | amd64, arm64, armelarmhf, i386, mips64el, mipselppc64, els390x, multi-arch. |

##### Características

| PROS | CONTRAS |
|-|-|
|Modularidad y personalización a full distribución DIY (Do it yourself), es decir le puedes colocar el entorno que más te guste, Gnome, mate, xfce, etc. En este ejemplo se usó un window manager llamado i3WM. | Desventajas generales de linux. |
| Distribución madre (no está basada en ninguna). | El gestor de paquetes APT es algo sencillo por no decir obsoleto. Nala es una excelente arternavita. |
| Multipropósito (La puedes utilizar como sistema operativo principal, servidor, etc) | Para el soporte de drivers privativos es necesario ocupar la ISO non-free: <a href="https://cdimage.debian.org/cdimage/unofficial/non-free/cd-including-firmware/">Aqui.</a> |
| Estabilidad (Tanto que cada actualización es cada 2 años aprox, debido a que todas las características incluidas son testeadas y se corrigen bugs durante todo ese lapso de tiempo. |
| Instalador gráfico. |

#### Zorin OS

<img src="/img/in-post/os_guide/gnu_os/zorin.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga: | <a href="https://zorin.com/os/download/">zorin.com</a> |
| Requisitos Mínimos | especificados por Zorin <a href="https://zorin.com/help/system-requirements/">zorin.com/help</a>
| CPU: | 1 GHz Single Core – Intel/AMD 64-bit processor |
| RAM: | 1 GB |
| Storage: | 10 GB (Lite), 22 GB (Education Lite), or 40 GB (Pro Lite) |
| Display: | 800 × 600 resolution |
| Última versión: | 16.3. |
| Año de lanzamiento: | 2009. |
| Arquitectura: | 32  y 64 bits. |


##### Características

| PROS | CONTRAS |
|-|-|
| Escritorio basado en XFCE y personalizado por Zorin por lo que consume pocos recursos. Sin embargo también existe el flavor con GNOME en su versión original: aquí. | No tiene repositorios propios, hace peticiones a los de ubuntu. |
| Basada en ubuntu 20.04 LTS. Es estable, existe documentación y la curva de aprendizaje es mínima ideal para principiantes. | Poca personalización y libertad de uso comparado a otras distribuciones. |
| Programas preinstalados como Suite LibreOffice (Ofimática), Juegos y tienda de software. | Existe una versión pro que es de paga, en ella se incluye soporte vía remoto y demás características. |
| Interfaz similar a windows. | Desventajas generales de Linux. |
| Instalación gráfica (modo live). |
| Ready for games (Optimización en drivers nvidia, amd). |

#### Elementary OS

<img src="/img/in-post/os_guide/gnu_os/elementary.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link oficial de descarga: | <a href="https://elementary.io/es/">elementary.io</a>
| Requerimientos: | especificados por elementary OS <a href="https://elementary.io/es/docs/installation#download-elementary-os">docs.elementary.io</a> “Aunque no tengamos un conjunto estricto de requisitos mínimos del sistema, recomendamos como poco las especificaciones siguientes para la mejor experiencia:” |
| CPU: | Procesador reciente, Intel i3 o equiparable, de dos núcleos y de 64 bits. |
| STORAGE: |(SSD) 32 GB de espacio libre, aunque también funciona con HDD. |
| RAM: | 4 GB de memoria del sistema (RAM). |
| Año de lanzamiento: | 2011. |
| Última versión: | 7.0. |
| Arquitectura: | 64 bits. |

##### Características

| PROS | CONTRAS |
|-|-|
| Un sustituto hecho a conciencia, potente y ético para Windows y macOS. | Desventajas generales de Linux |
| Instalación gráfica. | Aunque tiene repositorios propios lo mejor sería añadir también los de Ubuntu o Debian. |
| Minimalismo, contiene las aplicaciones necesarias para las tareas del día a día, no tiene bloatware. | Para descargar la ISO sin aportar donación solo es necesario escribir un 0 en monto personalizado. |
| Escritorio Pantheon es una réplica de Mac OS hecho en Vala y usando GTK3 con funciones de multitarea. | La evolución del proyecto es lenta. |
| Privacidad y transparencia. |
| Tienda de aplicaciones. |
| Recomendada para principiantes, fácil de utilizar. |

#### Amarok Linux

<img src="/img/in-post/os_guide/gnu_os/amarok.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga: | <a href="https://amaroklinux.org/download/">amoroklinux.org</a> |
| Requisitos mínimos: | Especificados por amarok linux: <a href="https://es.osdn.net/projects/amaroklinux/releases/">amarokliux.org</a> |
| RAM: | Necesita al menos 1 GB de memoria. |
| STORAGE |Necesita aproximadamente 7.5 GB de espacio libre en su disco duro. |
| CPU: | Su procesador debe tener soporte PAE para ejecutar Amarok Linux. |
| Año de lanzamiento: | 2021. |
| Última versión: | 22.09, Rolling Release. |
| Arquitectura: | 64 bits. |

##### Características

| PROS | CONTRAS |
|-|-|
| Basado en Debian 11. | Desventajas generales de linux. |
| Escritorio disponibles: MATE y LXQT (Se utilizó MATE para la prueba). | Algunas traducciones no están bien pulidas (la distro es de brazil). |
| Curva de aprendizaje mínima. | A medida que se quieran modificar cosas del sistema la curva de aprendizaje aumenta. |
| Software preinstalado: Stacer. (Optimizador), qBitorrent (cliente torrent), VLC (multimedia), tienda de software. | No se aprenden los mismos conceptos que se aprenderán en Debian a pesar de que esté basada en esta |
| Modularidad y personalización. |
| Instalación gráfica (modo live). |
| Ideal para quien empieza en linux pero tiene intenciones de aprender más. |


#### MX Linux

<img src="/img/in-post/os_guide/gnu_os/mx.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga: | <a href="https://mxlinux.org/download-links/">mxlinux.org</a> |
| Requisitos mínimos: | Mxlinux no los especifica, pero tomaremos estos como referencia: <a href="https://www.ionos.mx/digitalguide/servidores/configuracion/mx-linux/">ionos.mx</a> |
| RAM: | 1 GB RAM (2GB recomendado). |
| ROM: | 5 GB de storage. (20 GB recomendado). |
| CPU: | Procesador Intel o AMD moderno i686 |
| Año de lanzamiento: | 2014 |
| Última versión: | 21.2.1 |
| Arquitectura: | 64 y 32 bits |

##### Características

| PROS | CONTRAS |
|-|-|
| Basado en Debian. | Desventajas generales de linux |
| Cuenta con modo live. | Curva de aprendizaje entre principiante a media. |
| A diferencia de Debian este sistema ya cuenta con firmware non-free para drivers que no son open source. |
| Cuenta con entornos xfce, KDE, Fluxbox sin embargo existe una ISO sin desktop para colocar el de tu preferencia. |
| Cuenta con un init diferente a StystemD, Sysvinit. |
| Cuenta con repositorios propios. |
| Instalación gráfica. |
| MX-Package installer, instalador de paquetes automático, con opción a cambiar el entorno de trabajo desde esta herramienta así como también el kernel de manera automática. |
| Backports, acceso a betas y características de prueba en Debian |

### RHEL base.

#### RHEL 7.9 - 9.x

<img src="/img/in-post/os_guide/gnu_os/rhel.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga: |  <a href="https://developers.redhat.com/products/rhel/download">redhat.com</a> *Se requiere una suscripción a Red Hat* |
| Requisitos mínimos: | No existe un estándar de requisitos mínimos, ya que varía con el uso que se le vaya a dar al sistema: <a href="https://access.redhat.com/articles/rhel-limits">access.redhat.com</a> |
| Año de lanzamiento: | 1991. |
| Última versión: | 8.7. |
| Arquitectura: | Intel/AMD64 (x86_64), ARM 64-bit (aarch64), IBM Power LE (ppc64le), IBM Z (s390x). |

##### Características

| PROS | CONTRAS |
|-|-|
| Amplia documentación. | Curva de aprendizaje difícil. |
| Red Hat Satellite, poder actualizar servidores en masa desde una sola consola. | Su uso es exclusivamente como servidor, no se recomienda para uso doméstico. |
| Soporte garantizado con Red Hat. |Aplicaciones en cloud,  edge computing, kubernetes. |
| Estabilidad y actualizaciones continuas de seguridad. | Se requiere de una suscripción para poder acceder a sus repositorios. |
| Soporte extendido hasta junio de 2030. |  Difícil administración. |
| Red Hat lidera la cuota de mercado en servidores. | Normalmente son los Linux que más se buscan vulnerar. |
| Existen versiones posteriores como RHEL 8.6 y RHEL 9 (Beta). |
| Las certificaciones de RHEL tienen mucho prestigio en el campo laboral. |
| Instalación gráfica. |

#### Fedora

<img src="/img/in-post/os_guide/gnu_os/fedora.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga oficial: | <a href="https://getfedora.org/es/">fedora.org</a> |
| Requisitos del sistema: | Especificados por fedora: <a href="https://docs.fedoraproject.org/en-US/fedora/latest/release-notes/welcome/Hardware_Overview/">docs.fedoraproject.org</a> |
| CPU: | Procesador dual core a 2GHz o mas rapido. |
| RAM: | 2GB. |
| STORAGE: | 15GB. |
| Año de lanzamiento: | 2003. |
| Última versión: | 38, Rolling Release. |
| Arquitectura: | 64 bits, ARM64. |

##### Características

| PROS | CONTRAS |
|-|-|
| Basada en RHEL. | Es el patio de pruebas de Red Hat. |
| Ideal para desarrolladores y administradores de sistemas. | Su uso principalmente para servidores, cloud o programación, sin embargo hay distribuciones que se basan en fedora para otros ámbitos, como Nobara Linux. |
| Usa el gestor de paquetes dnf sin embargo es compatible con yum (antiguo gestor de paquetes de RHEL). | Se requieren conocimientos de Linux y terminal de comandos para poder administrar Fedora. |
| ZFS como file system por defecto. |
| Spins, Fedora pero con otros entornos graficos: <a href="https://spins.fedoraproject.org/">aqui.</a> |
| RPM Fusion, repositorio con paquetes extras para fedora o RHEL: <a href="https://rpmfusion.org/">aqui.</a> |
| Podría tomarse en cuenta como una distro “Core” ya que RHEL invierte dinero a Fedora. |
| Instalación gráfica. |

#### Rocky Linux

<img src="/img/in-post/os_guide/gnu_os/rocky.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga official: | <a href="https://rockylinux.org/download">rockylinux.org</a> |
| Requisitos del sistema: | Al ser un clonico 1:1 de RHEL tiene las mismas limitaciones, se tomaran en cuenta las especificadas por redhat: <a href="https://access.redhat.com/articles/rhel-limits">access.redhat.com</a> |
| CPU: | Procesador a 1.1 GHz. |
| RAM: | Minimum: 1 GB. Recommended: 2 GB. |
| STORAGE: | Minimum: 20 GB. Recommended: 40 GB. |
| Año de lanzamiento: | 2021. |
| Última versión: 9.1. |
| Arquitectura: | 64 y 32 bits, ARM64, s390x, ppc64le. |

##### Características

| PROS | CONTRAS |
|-|-|
| Clonico 1:1 a nivel binario de redhat | Por su naturaleza redhat quiere limitar su contenido para que no pueda ser reproducido |
| Ideal para los pequeños negocios que no puedan adquirir redhat | No es un sistema para uso domestico |
| La mayoria de los paquetes son reempaquetados de los repositorios de redhat | Aun que sea clonico 1:1 de redhat sus servicios pueden variar |
| Ofrece todas las características que redhat para tener un ambiente de produccion estable | |
| No requiere una subscripcion | |

### Arch base.

#### Arch Linux

<img src="/img/in-post/os_guide/gnu_os/arch.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga: | <a href="https://archlinux.org/download/">archlinux.org</a>|
|Requisitos mínimos especificado por la Arch wiki:| <a href="https://wiki.archlinux.org/title/installation_guide">wiki.archlinux.org</a>|
| RAM + STORAGE| Arch Linux debería ejecutarse en cualquier máquina compatible con arquitectura x86_64 con un mínimo de 512 MiB de RAM, aunque se necesita más memoria para iniciar el sistema en vivo para la instalación. Una instalación básica debería ocupar menos de 2 GiB de espacio en disco. |
| Año de lanzamiento: | 2002. |
| Última versión: | Rolling Release. |
| Arquitectura: | 64 y 32 bits, ARM64. |

##### Características

| PROS | CONTRAS |
|-|-|
| Modularidad y personalización, distribución DIY(Do it Yourself), permite instalar prácticamente cualquier entorno ya sea escritorio o window manager (Para la prueba se usó BSPWM). | Desventajas generales de linux. |
| Ligero debido a que es uno mismo quien elige qué paquetes y que entorno utilizar. | Curva de aprendizaje avanzada. |
| AUR (Arch User Repository) repositorio con software hecho por usuarios o subido por empresas en espera de entrar a los repositorios oficiales. | Instalación no gráfica (terminal), aunque existen maneras de instalarlo automáticamente, como es el caso del script archinstall que viene por defecto y está desarrollado por la organización de Arch Linux. Otra manera es mediante Arch GUI que cuenta con instalador gráfico. |
| Arch Wiki (Documentación para errores, instalaciones, etc): <a href="https://wiki.archlinux.org/">wiki.archlinux.org</a> | Su modo live es una terminal. |
| Aprendizaje, se aprende demasiado de sistemas y cómo es que funcionan. Ideal para desarrolladores. |
| Se le pueden agregar los repositorios de BlackArch(Para ciberseguridad) y los Chaotic Aur. |
| Distribución Core, no se basa en ninguna otra. |

#### Manjaro Linux

<img src="/img/in-post/os_guide/gnu_os/manjaro.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga: | <a href="https://manjaro.org/download/">manjaro.org</a> |
| Requisitos mínimos especificados en la wiki de manjaro: | <a href="https://wiki.manjaro.org/index.php/About_Manjaro">wiki.manjaro.org</a> |
| RAM: | Un gigabyte (GB) de memoria ram. |
| STORAGE | Treinta gigabytes (GB) de espacio en disco duro. |
| CPU: | Un procesador de un gigahercio (Ghz). |
| GRAPHICS: | Una tarjeta gráfica y un monitor de alta definición (HD). |
| Año de lanzamiento: | 2011. |
| Última versión: | Rolling Release. |
| Arquitectura: | 64 y 32 bits, ARM. |

##### Características

| PROS | CONTRAS |
|-|-|
| Archcraft en esencia es un Arch Linux personalizado por la comunidad de reddit. No hace uso de escritorios como lo son KDE, GNOME, XFCE, MATE, etc. Hace uso únicamente de gestores de ventanas (Window Manager) sin embargo ya vienen configurados para el usuario final. Es decir, no es necesario que lo personalices o que te pongas a crearlo desde 0. | Curva de aprendizaje intermedia, aunque no es necesario configurar el window manager, siempre que tengas los conocimientos puedes hacerlo para adaptarlo más a tu gusto. |
| ARCH LINUX con instalación gráfica y personalizado. | Desventajas generales de Linux. |
| Uso de window manager, perfecto para productividad y es muy ligero. | Requiere un mayor tiempo de adaptación debido al uso del window manager sin embargo todos los atajos y funciones vienen explicadas en su wiki. |
| Actualmente cuenta con 5 window manager: bspwm, openbox, dwm, i3wm, berry (El utilizado en esta prueba fue Berry). | Un error comun es la ruptura de las claves GPG de los repositorios de Arch, pero se arregla fácilmente con el post que tienen en su wiki: aquí. |
| Temas jodidamente épicos. |
| Arch User Repository (AUR), Chaotic AUR y repositorio propios de Archcraft instalados por defecto (Atasquese de software padrino). |
Minimalismo y sin bloatware. |

#### Artix Linux

<img src="/img/in-post/os_guide/gnu_os/artix.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga official: | <a href="https://artixlinux.org/download.php">artixlinux.org</a> |
| Requisitos del sistema: | No se especifica, pero son los mismo que Arch Linux: <a href="https://archlinux.org/download/">archlinux.org</a> |
| Año de lanzamiento: | 2017. |
| Última versión: | Rolling Release. |
| Arquitectura: | 64 y 32 bits. |

##### Características

| PROS | CONTRAS |
|-|-|
| Está basado en Arch Linux, por lo que se tienen todas las ventajas de un sistema Arch Linux | Dependiendo de la ISO contará o no con modo live o no. |
| Wiki y Foro para la solución de problemas: https://wiki.artixlinux.org/ | No tiene el init de SystemD, por lo que iniciar e instalar servicios se hace de forma diferente a cualquier distro. |
| Tiene ISOs con diferentes Flavors (LXDE, LXQT, MATE, PLASMA, XFCE) | Curva de aprendizaje superior a Arch. |
| Instalador gráfico, sin embargo también se puede hacer la instalación desde terminal como en Arch Linux. | Desventajas generales de linux. |
| Se puede seleccionar con qué init se quiere trabajar (Runit, S6, openrc). |



### Independientes.
#### Void Linux

<img src="/img/in-post/os_guide/gnu_os/void.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga official: | <a href="https://voidlinux.org/download/">voidlinux.org</a> |
| Requisitos del sistema: | Especificados por void: <a href="https://docs.voidlinux.org/installation/index.html">docs.voidlinux.org</a> |
| CPU: | Procesador arquitectura x86_64 o i686.
| RAM: | 96MB |
| ROM: | 700MB |
| Año de lanzamiento: | 2008. |
| Última versión: | Rolling Release. |
| Arquitectura: | 64 y 32 bits, i686, ARM. |


##### Características

| PROS | CONTRAS |
|-|-|
| Distribución independiente, no se basa en ninguna otra. | Desventajas generales de linux. |
| Gestor de paquetes XBPS. | Curva de aprendizaje avanzada. |
| Paquetes non-free, una distribución que no está peleada con el software privativo. | Tiempo de adaptación debido a que es una distro independiente. |
| Distribución DIY (Do it yourself), personalización a full. | Distribución mantenida por la comunidad, por lo que no tiene un soporte tan bueno. |
| No tiene bloatware, ya que uno mismo la va adaptando a sus necesidades. |
| Cuenta con modo live en escritorio XFCE. |
| Instalación semi gráfica CLI(Command Line). |

#### Alpine Linux

<img src="/img/in-post/os_guide/gnu_os/alpine.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga official: | <a href="https://www.alpinelinux.org/downloads/">alpinelinux.org</a> |
| Requisitos del sistema. Especificados por la wiki de alpine linux: | <a href="https://wiki.alpinelinux.org/wiki/Requirements">wiki.alpinelinux.org</a> |
| CPU: | Procesador con arquitectura x86_64, arm. |
| RAM: | 512mb ram para window manager. 2gb para escritorio. |
| STORAGE: | Almacenamiento interno o externo.|
| Año de lanzamiento: | 2012. |
| Última versión: | 3.18.3. |
| Arquitectura: | 64 y 32 bits, ARM, IBM ESA/390, ppc64. |

##### Características

| PROS | CONTRAS |
|-|-|
| Distribución independiente. | Desventajas generales de Linux. |
| Prácticamente una de las distribuciones con el kernel linux más puro. | Pocos paquetes de software, sin embargo cuenta con los suficientes para el uso de propósito general. Incluso se tiene la posibilidad de usar paquetes flatpak. |
| Rendimiento superior a todas las distribuciones anteriormente mostradas (siendo la más rápida). | Evolución del proyecto muy lenta. |
| Tiene como objetivo ser ligera y segura por defecto sin dejar de ser útil para tareas de propósito general. (de ahi que se use en proyectos con docker). | Poca documentación, sin embargo la que existe proviene mayormente de la wiki. |
| La instalación más rápida que verás en tu vida. | Tiene una de las curvas de aprendizaje más avanzadas. |
| Distribución DIY, soporta la gran mayoría de entornos gráficos, claramente no tiene bloatware. |
| Repositorios Edge, paquetes de la rama de testeo y Community paquetes desarrollados por los usuarios. |
| Instalación no gráfica, pero guiada. |

#### Open SUSE

<img src="/img/in-post/os_guide/gnu_os/open-suse.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga official: | <a href="https://www.opensuse.org/">opensuse/org</a> |
| Requisitos del sistema: | Especificados por Open SUSE: <a href="https://documentation.suse.com/external-tree/en-us/suma/4.1/suse-manager/installation/uyuni-install-requirements.html">documentation.suse.com</a> |
| CPU: | Minimum 4 dedicated 64-bit CPU cores (x86-64). |
| RAM: | Test Server Minimum 8 GB. Base Installation Minimum 16 GB. Production Server Minimum 32 GB. |
| STORAGE: | Disk space depends on your channel requirements, at least 100 GB. |
| Año de lanzamiento: | 1994. |
| Última versión: | 15.2. |
| Arquitectura: | 64 y 32 bits, ARM64, ppc64le, S390X, ppc64. |


##### Características

| PROS | CONTRAS |
|-|-|
| Basada en SUSE Linux. | No tiene un uso dedicado, por lo que su existencia queda volando en el aire. |
| Instalación gráfica. | Requiere conocimientos en manejo de terminal. |
| Utiliza paqueteria RPM (Red Hat Package Manager). | Desventajas generales de Linux. |
| Tiene su gestor de paquetes independiente, zypper. |
| Debido a que no tiene un uso específico, puede usarse para un uso doméstico, como servidor, workstation o para cloud. |

#### Bedrock Linux

<img src="/img/in-post/os_guide/gnu_os/bedrock.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga official: | <a href="https://raw.githubusercontent.com/bedrocklinux/bedrocklinux-userland/0.7/releases">bedrocklinux.org</a> |
| Requisitos del sistema: | Compatibilidad para sistemas: <a href="https://bedrocklinux.org/0.7/distro-compatibility.html">bedrocklinux.org/distro-compatibility</a> |
| OS | Compatibilidad |
| Arch Linux | Si |
| Debian | Si |
| Gentoo | Si |
| Pop!_OS | Si |
| Ubuntu | Si |
| Void Linux | Si |
| Año de lanzamiento: | 2021. |
| Última versión: | 0.7.28. |
| Arquitectura: | x86_64, s390x, ppc64le, ppc64, ppc, mipsel, mips64el, mips, i686, i586, i486, i386, armv7l, arm7hl, aarch64. |


##### Características

| PROS | CONTRAS |
|-|-|
| Meta distribución (Combinar distribuciones). | Curva de aprendizaje alta. |
| Poder tener más de un init (systemd, open-rc, S6, etc). | Administración complicada. |
| Poder manejar múltiples package managers (pacman, apt, dnf). | No es compatible con ZFS. |
| Tener acceso a software de otras distribuciones. | Desventajas generales de linux. |
| Se puede instalar sobre una distribución que ya tengas (importante mirar la compatibilidad). | La realidad es que solo vale la pena por el AUR. |

#### Gentoo Linux

<img src="/img/in-post/os_guide/gnu_os/ogentoo.png" onclick="window.open(this.src)">

##### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga official: | <a href="https://www.gentoo.org/downloads/">gentoo.org</a> |
| Requisitos del sistema. | Especificados por la wiki de gentoo: <a href="https://wiki.gentoo.org/wiki/Handbook:X86/Full/Installation">wiki.gentoo.org</a> |
| CPU: | i486 o posterior para la versión minimal, i686 o posterior para la versión live |
| RAM: | 256 MB para la versión minimal, 512 MB para la versión live cd |
| STORAGE: | 2.5 GB (excluyendo espacio de swap) |
| Swap space: | mayor a 256 MB |
| Año de lanzamiento: | 2000. |
| Última versión: | Rolling Release. |
| Arquitectura: | 64 y 32  bits, Alpha, ARM, AMR64, hppa, ia64, loong, mips, m68k, ppc, riscv, s390x,sparcm, i686. |


##### Características

| PROS | CONTRAS |
|-|-|
| Su nombre viene del pingüino Pygoscelis papua también conocido como Gentoo, el cual es el más rápido del mundo de ahí que se conozca como la distribución más rápida de linux debido a que en su mayoría todo es compilado. | Administración compleja. |
| Administración modular, permisos, cambios a nivel de código, paquetes, drivers y más. | No contiene instalación gráfica, es mediante terminal, preferiblemente contar con un segundo equipo para su instalación vía SSH. |
| Full personalización. | No recomendada para equipos de bajos recursos, debido a que en esta distribución utiliza el 100% de los núcleos del procesador para compilar paquetes y kernel además de que se recomienda 2gb de ram por núcleo, sin embargo con paciencia puede usarse hasta en una piedra: https://www.youtube.com/watch?v=nZudFif409M&t=3s  |
| Al compilarse la mayoría de paquetes y el kernel este sistema es uno de los mejor optimizados. | Procesos de compilación tardados dependiendo del hardware y del número de paquetes instalados |
| Overlays, proveen de software que no se encuentre en los repositorios de Gentoo. | De las curvas de aprendizaje más altas. |


## BSD OS

### FreeBSD

<img src="/img/in-post/os_guide/bsd_os/freebsd.png" onclick="window.open(this.src)">

#### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga official: | <a href="https://www.freebsd.org/es/where/">freebsd.org</a> |
| Requisitos del sistema: | Especificados por Free BSD: Son distintos dependiendo el propósito <a href="https://docs.freebsd.org/en/books/handbook/bsdinstall/">docs.freebsd.org</a> |
| Año de lanzamiento: | 1993.|
| Última versión: | 13.1. |
| Arquitectura: | amd64, i386, powerpc, powerpc64, powerpc64le, powerpcspe, armv6, armv7, aarch64, riscv64. |

#### Características

| PROS | CONTRAS |
|-|-|
| Es 48% más seguro con respecto al kernel de Linux. | No contiene instalador gráfico. |
| Es la distribución BSD más utilizada, por ende tiene un buen soporte. | Difícil administración. |
| Buena alternativa a sistemas GNU/Linux. | Su uso principalmente es para el uso de servidores y administración de bases de datos o aplicaciones web, no es ideal para un uso doméstico (Pero hay gente que le gusta como DAILY desktop, para gustos, colores). |
| Tiene su propia wiki: <a href="https://wiki.freebsd.org/">aquí.</a> | Poco software a comparación de GNU/Linux. |
| Sistema DIY (Do it yourself) por lo que puedes elegir tu entorno gráfico, en este se eligió XFCE. | No esperes gaming aquí. |
| PKG como package manager. | 
| BSD Ports, una forma fácil de instalar software en BSD: aquí. |

### GHOST BSD

<img src="/img/in-post/os_guide/bsd_os/ghostbsd.png" onclick="window.open(this.src)">

#### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga official: https://ghostbsd.org/download 
| Requisitos del sistema. Especificados por la wiki de Ghost BSD: https://wiki.ghostbsd.org/index.php/Hardware_Requirements 
| CPU: | 64-bit processor. |
| RAM: | 4 GB |
| STORAGE: | 15 GB of free hard drive space. |
| Año de lanzamiento: | 2010. |
| Última versión: | 13.1. |
| Arquitectura: | 64 bits. |


#### Características

| PROS | CONTRAS |
|-|-|
| Su utilidad es para labores empresariales, capacitación, administración e introducción a los sistemas basados en BSD. | No está creado para el uso doméstico. |
| Contiene un instalador gráfico. | No se recomienda para equipos con pocos recursos. |
| No contiene bloatware. | Administración compleja. |
| Una buena alternativa a Free BSD. | Poco software a comparación de un sistema Linux. |
| Contiene más software en sus repositorios a comparación de Free BSD. |
| Comúnmente utilizado en el ámbito científico y de investigaciones. |
| Está más optimizado a comparación de otros sistemas BSD. |


### OPEN BSD

<img src="/img/in-post/os_guide/bsd_os/openbsd.png" onclick="window.open(this.src)">

#### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga official: | <a href="https://www.openbsd.org/faq/faq4.html#Download">openbsd.org</a>
| Requisitos del sistema: | Aunque no los hay como tal esto es lo que se especifica para una buena experiencia: <a href="https://www.openbsd.org/faq/faq4.html">faq.opensbd.org</a> |
| HARDAWARE: | OpenBSD puede instalarse en tan sólo 512 MB, pero usar un dispositivo tan pequeño es cosa de usuarios avanzados. Hasta que tenga algo de experiencia, se recomiendan 8GB o más de espacio en disco. |
| Año de lanzamiento: | 1996 |
| Última versión: | 7.2 |
| Arquitectura: | alpha, amd64, arm64, armv7, hppa, i386, landisk, loongson, luna88k, macppc, octeon, powerpc64, riscv64, sparc64 |


#### Características

| PROS | CONTRAS |
|-|-|
| Se puede instalar en tan solo 512 MB de disco, claro teniendo conocimientos avanzados de la estructura del sistema. | No es un sistema para el uso doméstico, si no para la administración de servidores o firewalls dedicados. |
| Es muy ligero, llegando a consumir solo 36MB de ram en su versión minimal. | Administración compleja. |
| Es open source. | No tiene instalador gráfico. |
| Es 63% más seguro respecto al kernel Linux. | Debido a la poca compatibilidad que tiene con software sus usos son limitados en cuanto a deploy de aplicaciones web. |

## MAC OS

### Monterrey

<img src="/img/in-post/os_guide/mac_os/catalina.png" onclick="window.open(this.src)">

#### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
| Link de descarga official: | <a href="macappstores://apps.apple.com/mx/app/macos-monterey/id1576738294?mt=12">apps.apple.com</a> |
| Equipos compatibles con Mac OS Monterrey: | <a href="https://support.apple.com/en-us/HT212551">support.apple.com</a> |
| Año de lanzamiento: | 2021 |
| Última versión: | 12.6.2 |
| Arquitectura: | x86-64, ARM64 |

#### Características

| PROS | CONTRAS |
|-|-|
| Ideal para diseñadores y desarrolladores. | Claramente no puedes hacer funcionar este sistema operativo en tu computadora, necesitas adquirir uno de los dispositivos de Apple, virtualizarlo o realizar un Hacking Tosh el cual solo es funcional con procesadores intel. |
| Consume un poco menos que Mac OS 12, pero apenas existe diferencia. | No es open source. |
| Upgrade de kernel del 19.6.0 a el 20.6.0 y nuevas características aquí. | Gaming en apple es: XD, pero si aun asi eres terco pues existe PlayOnMac. |
| No esperes un buen rendimiento en juegos, ya que no va dirigido a ese mercado. |

### Big Sur

<img src="/img/in-post/os_guide/mac_os/bigsur.png" onclick="window.open(this.src)">

#### Ficha tecnica

| Componente | Ficha tecnica |
|-|-|
 Link de descarga official: | <a href="macappstores://apps.apple.com/mx/app/macos-big-sur/id1526878132?mt=12">apps.apple.com</a> |
| Requisitos del sistema y equipos compatibles: | Especificados por Apple: <a href="https://support.apple.com/kb/sp833?locale=es_MX">apple.support.com</a> |
| RAM: | 4 GB de memoria |
| STORAGE: | 35.5 GB de almacenamiento disponible en macOS Sierra o posterior* |
| Año de lanzamiento: | 2020 |
| Última versión: | 11.7.2 |
| Arquitectura: | x86-64, ARM64 |


#### Características

| PROS | CONTRAS |
|-|-|
| Ideal para diseñadores y desarrolladores. | Claramente no puedes hacer funcionar este sistema operativo en tu computadora, necesitas adquirir uno de los dispositivos de Apple, virtualizarlo o realizar un Hacking Tosh el cual solo es funcional con procesadores intel. |
| Consume un poco menos que Mac OS 12, pero apenas existe diferencia. | No es open source. |
| Upgrade de kernel del 19.6.0 a el 20.6.0 y nuevas características aquí. | Gaming en apple es: XD, pero si aun asi eres terco pues existe PlayOnMac. |

## Contribuye

Si piensas que se pueden añadir mas sistemas operativos a la lista. Sin hacerla redundante (proponer distribuciones similares), mandame un MD a discord: <a href="https://discord.com/users/690450705512661002">quantumwavves</a>
