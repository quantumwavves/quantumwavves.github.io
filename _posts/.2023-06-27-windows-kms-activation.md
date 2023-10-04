---
layout: post
title: ACTIVACION KMS WINDOWS.
subtitle: ¿Que es KMS, como funciona y que pasa con los servidores de terceros?
header-img: img/in-post/jawa_post/yelan.jpg
header-style: image
header-mask: rgba(0, 0, 0, .4)
catalog: true
tags:
  - windows
  - kms
  - activación
---

<!-- HTML Meta Tags -->
<title>ACTIVACION KMS WINDOWS. - Quantum</title>
<meta name="description" content="Un pequeño post que explica la activación KMS de windows.">
<meta property="og:site_name" content="QuantumWavves">
<meta property="og:image" content="https://quantumwavves.github.io/img/in-post/jawa_post/yelan.jpg">

<!-- Facebook Meta Tags -->
<meta property="og:url" content="https://quantumwavves.github.io/2023/06/26/windows-kms-activation/">
<meta property="og:type" content="website">
<meta property="og:title" content="ACTIVACION KMS WINDOWS. - Quantum">
<meta property="og:description" content="Un pequeño post que explica la activación KMS de windows.">
<meta property="og:image" content="https://quantumwavves.github.io/img/in-post/jawa_post/yelan.jpg">

<!-- Twitter Meta Tags -->
<meta name="twitter:card" content="summary_large_image">
<meta property="twitter:domain" content="quantumwavves.github.io">
<meta property="twitter:url" content="https://quantumwavves.github.io/2023/06/26/windows-kms-activation/">
<meta name="twitter:title" content="ACTIVACION KMS WINDOWS. - Quantum">
<meta name="twitter:description" content="Un pequeño post que explica la activación KMS de windows.">
<meta name="twitter:image" content="https://quantumwavves.github.io/img/in-post/jawa_post/yelan.jpg">

<!-- Meta Tags Generated via https://opengraph.dev -->

<p style='text-align: justify;'>En este post veremos como realizar una activación kms para Windows, con base en documentación proporcionada por Microsoft. Daremos un vistazo a los diferentes modos de activación para Windows y se resolverá dudas acerca de los mitos con respecto a la activación kms.</p>

### ¿Que es KMS?
<p style='text-align: justify;'>
KMS por sus siglas en ingles de Key Management Service (Servicio de gestión de claves) como lo indica su nombre es un servicio. Esto quiere decir que responde a protocolos de Internet como por ejemplo ssh, telnet, ftp entre otros. KMS es un servicio que proporciona Microsoft para la activación de windows por volumen, sin embargo no solo esta limitado a windows si no también a la suite de ofimática microsoft office. Este producto se ofrece a las empresas, para poder acceder a el es necesario realizar un registro en el portal <a href="https://vlcc0.blob.core.windows.net/es-xx/MVLC_QS_Register_for_the_Volume_Licensing_Center.pdf">bussines</a> de microsoft.</p>

### ¿Como funciona KMS?
1. KMS es instalado en un servidor.
2. La clave de host de KMS se instala en el host de KMS y, a continuación, se activa poniéndose en contacto con los servicios de activación alojados en Microsoft.
3. Una vez activado, KMS hace un registro SRV en el sistema de nombres de dominio (DNS) cada vez que se inicia KMS o una vez al día.
4. Un ordenador cliente descubre el servidor KMS a partir de una entrada configurada o a través del registro SRV de KMS en DNS.
5. El cliente envía una solicitud RPC al servidor KMS por el puerto 1688 TCP/IP (Configuración predeterminada) Esta solicitud incluye un ID del ordenador cliente cifrado y si no hay respuesta del servidor KMS, el cliente envía una solicitud de re activación al cabo de siete días.
6. El servidor KMS añade el ID del cliente a una tabla y devuelve el recuentro de activaciones al cliente.
7. El cliente evalua el recuerdo de activaciones comparandolo con la politica de licencias y lo activa.

![Desktop View](/img/in-post/jawa_post/network-kms-example.jpg){: w="400" h="100" }

<p style='text-align: justify'>Fuente: <a href= "https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831612(v=ws.11)#how-does-volume-activation-work"> How does volume activation work?</a></p>

### Modelos de activación.
<p style= 'text-align: justify'>Actualmente existen 3 tipos de activación para windows estos son:</p>

1.- Licencias OEM y Retail.
* OEM: Esta se adhiere al hardware de tu computadora y a menos que cambies la motherboard no se vera afectada.
* Retail: Esta se vincula a tu cuenta de microsoft y es permanente mientras el SO aún tenga soporte.

2.- KMS o MAK.
* KMS: Activación mediante servidor.
* MAK: Clave de activación múltiple (MAK) activa los sistemas de forma única mediante los servicios de activación hospedados de Microsoft

3.- Vía telefónica: 
* Activación automatizada por teléfono (requieres licencia)

### Claves KMS (Basadas en documentación).

**Windows Server LTSC (versions)**

Windows Server 2022

| Edición de Sistema Operativo | Clave KMS |
|----------|----------|
| Windows Server 2022 Datacenter | WX4NM-KYWYW-QJJR4-XV3QB-6VM33 |
| Windows Server 2022 Datacenter Azure Edition    | NTBV8-9K7Q8-V27C6-M2BTV-KHMXV |
| Windows Server 2022 Standard | VDYBN-27WPP-V4HQT-9VMD4-VMK7H |

Windows Server 2019

| Edición de Sistema Operativo | Clave KMS |
|----------|----------|
| Windows Server 2019 Datacenter | WMDGN-G9PQG-XVVXX-R3X43-63DFG |
| Windows Server 2019 Standard  | N69G4-B89J2-4G8F4-WWYCC-J464C |
| Windows Server 2019 Essentials | WVDHN-86M7X-466P6-VHXV7-YY726 |

Windows Server 2016

| Edición de Sistema Operativo | Clave KMS |
|----------|----------|
| Windows Server 2016 Datacenter | CB7KF-BWN84-R7R2Y-793K2-8XDDG |
| Windows Server 2016 Standard  | WC2BQ-8NRM3-FDDYY-2BFGV-KHKQY |
| Windows Server 2016 Essentials | JCKRF-N37P4-C2D82-9YXRT-4M63B |

**Windows Server (Semi-Annual-Channel versions)**

Windows Server, versions 20H2, 2004, 1909, 1903 and 1809.

| Edición de Sistema Operativo | Clave KMS |
|----------|----------|
| Windows Server Datacenter | 6NMRW-2C8FM-D24W7-TQWMY-CWH2D |
| Windows Server Standard  | N2KJX-J94YW-TQVFB-DG9YT-724CC |

**Windows 11 y Windows 10 (Semi-Annual Channel versions)**

|Edición de Sistema Operativo | Clave KMS |
|---|---|
|Windows 11 Pro  <br>Windows 10 Pro|W269N-WFGWX-YVC9B-4J6C9-T83GX|
|Windows 11 Pro N  <br>Windows 10 Pro N|MH37W-N47XK-V7XM9-C7227-GCQG9|
|Windows 11 Pro for Workstations  <br>Windows 10 Pro for Workstations|NRG8B-VKK3Q-CXVCJ-9G2XF-6Q84J|
|Windows 11 Pro for Workstations N  <br>Windows 10 Pro for Workstations N|9FNHH-K3HBT-3W4TD-6383H-6XYWF|
|Windows 11 Pro Education  <br>Windows 10 Pro Education|6TP4R-GNPTD-KYYHQ-7B7DP-J447Y|
|Windows 11 Pro Education N  <br>Windows 10 Pro Education N|YVWGF-BXNMC-HTQYQ-CPQ99-66QFC|
|Windows 11 Education  <br>Windows 10 Education|NW6C2-QMPVW-D7KKK-3GKT6-VCFB2|
|Windows 11 Education N  <br>Windows 10 Education N|2WH4N-8QGBV-H22JP-CT43Q-MDWWJ|
|Windows 11 Enterprise  <br>Windows 10 Enterprise|NPPR9-FWDCX-D2C8J-H872K-2YT43|
|Windows 11 Enterprise N  <br>Windows 10 Enterprise N|DPH2V-TTNVB-4X9Q3-TJR4H-KHJW4|
|Windows 11 Enterprise G  <br>Windows 10 Enterprise G|YYVX9-NTFWV-6MDM3-9PT4T-4M68B|
|Windows 11 Enterprise G N  <br>Windows 10 Enterprise G N|44RPN-FTY23-9VTTB-MP9BX-T84FV|

**Windows 10 (LTSC/LTSB versions)**

Windows 10 LTSC 2021 and 2019

|Edición de Sistema Operativo| Clave KMS|
|---|---|
|Windows 10 Enterprise LTSC 2021  <br>Windows 10 Enterprise LTSC 2019|M7XTQ-FN8P6-TTKYV-9D4CC-J462D|
|Windows 10 Enterprise N LTSC 2021  <br>Windows 10 Enterprise N LTSC 2019|92NFX-8DJQP-P6BBQ-THF9C-7CG2H|

Windows 10 LTSB 2016

|Edición de Sistema Operativo| Clave KMS|
|---|---|
|Windows 10 Enterprise LTSB 2016|DCPHK-NFMTC-H88MJ-PFHPY-QJ4BJ|
|Windows 10 Enterprise N LTSB 2016|QFFDN-GRT3P-VKWWX-X7T3R-8B639|

Windows 10 LTSB 2015

|Edición de Sistema Operativo| Clave KMS|
|---|---|
|Windows 10 Enterprise 2015 LTSB|WNMTR-4C88C-JK8YV-HQ7T2-76DF9|
|Windows 10 Enterprise 2015 LTSB N|2F77B-TNFGY-69QQF-B8YKP-D69TJ|

**Earlier versions of Windows Server**

Windows Server, version 1803

|Edición de Sistema Operativo| Clave KMS|
|---|---|
|Windows Server Datacenter|2HXDN-KRXHB-GPYC7-YCKFJ-7FVDG|
|Windows Server Standard|PTXN8-JFHJM-4WC78-MPCBR-9W4KR|

Windows Server, version 1709

|Edición de Sistema Operativo| Clave KMS|
|---|---|
|Windows Server Datacenter|6Y6KB-N82V8-D8CQV-23MJW-BWTG6|
|Windows Server Standard|DPCNP-XQFKJ-BJF7R-FRC8D-GF6G4|

Windows Server 2012 R2

|Edición de Sistema Operativo| Clave KMS|
|---|---|
|Windows Server 2012 R2 Standard|D2N9P-3P6X9-2R39C-7RTCD-MDVJX|
|Windows Server 2012 R2 Datacenter|W3GGN-FT8W3-Y4M27-J84CP-Q3VJ9|
|Windows Server 2012 R2 Essentials|KNC87-3J2TX-XB4WP-VCPJV-M4FWM|

Windows Server 2012

|Edición de Sistema Operativo| Clave KMS|
|---|---|
|Windows Server 2012|BN3D2-R7TKB-3YPBD-8DRP2-27GG4|
|Windows Server 2012 N|8N2M2-HWPGY-7PGT9-HGDD8-GVGGY|
|Windows Server 2012 Single Language|2WN2H-YGCQR-KFX6K-CD6TF-84YXQ|
|Windows Server 2012 Country Specific|4K36P-JN4VD-GDC6V-KDT89-DYFKP|
|Windows Server 2012 Standard|XC9B7-NBPP2-83J2H-RHMBY-92BT4|
|Windows Server 2012 MultiPoint Standard|HM7DN-YVMH3-46JC3-XYTG7-CYQJJ|
|Windows Server 2012 MultiPoint Premium|XNH6W-2V9GX-RGJ4K-Y8X6F-QGJ2G|
|Windows Server 2012 Datacenter|48HP8-DN98B-MYWDG-T2DCC-8W83P|

Windows Server 2008 R2

|Edición de Sistema Operativo| Clave KMS|
|---|---|
|Windows Server 2008 R2 Web|6TPJF-RBVHG-WBW2R-86QPH-6RTM4|
|Windows Server 2008 R2 HPC edition|TT8MH-CG224-D3D7Q-498W2-9QCTX|
|Windows Server 2008 R2 Standard|YC6KT-GKW9T-YTKYR-T4X34-R7VHC|
|Windows Server 2008 R2 Enterprise|489J6-VHDMP-X63PK-3K798-CPX3Y|
|Windows Server 2008 R2 Datacenter|74YFP-3QFB3-KQT8W-PMXWJ-7M648|
|Windows Server 2008 R2 for Itanium-based Systems|GT63C-RJFQ3-4GMB6-BRFB9-CB83V|

Windows Server 2008

|Edición de Sistema Operativo| Clave KMS|
|---|---|
|Windows Web Server 2008|WYR28-R7TFJ-3X2YQ-YCY4H-M249D|
|Windows Server 2008 Standard|TM24T-X9RMF-VWXK6-X8JC9-BFGM2|
|Windows Server 2008 Standard without Hyper-V|W7VD6-7JFBR-RX26B-YKQ3Y-6FFFJ|
|Windows Server 2008 Enterprise|YQGMW-MPWTJ-34KDK-48M3W-X4Q6V|
|Windows Server 2008 Enterprise without Hyper-V|39BXF-X8Q23-P2WWT-38T2F-G3FPG|
|Windows Server 2008 HPC|RCTX3-KWVHP-BR6TB-RB6DM-6X7HP|
|Windows Server 2008 Datacenter|7M67G-PC374-GR742-YH8V4-TCBY3|
|Windows Server 2008 Datacenter without Hyper-V|22XQ2-VRXRG-P8D42-K34TD-G3QQC|
|Windows Server 2008 for Itanium-Based Systems|4DWFP-JF3DJ-B7DTH-78FJB-PDRHK|

**Earlier versions of Windows**

Windows 8.1

|Edición de Sistema Operativo| Clave KMS|
|---|---|
|Windows 8.1 Pro|GCRJD-8NW9H-F2CDX-CCM8D-9D6T9|
|Windows 8.1 Pro N|HMCNV-VVBFX-7HMBH-CTY9B-B4FXY|
|Windows 8.1 Enterprise|MHF9N-XY6XB-WVXMC-BTDCT-MKKG7|
|Windows 8.1 Enterprise N|TT4HM-HN7YT-62K67-RGRQJ-JFFXW|

Windows 8

|Edición de Sistema Operativo| Clave KMS|
|---|---|
|Windows 8 Pro|NG4HW-VH26C-733KW-K6F98-J8CK4|
|Windows 8 Pro N|XCVCF-2NXM9-723PB-MHCB7-2RYQQ|
|Windows 8 Enterprise|32JNW-9KQ84-P47T8-D8GGY-CWCK7|
|Windows 8 Enterprise N|JMNMF-RHW7P-DMY6X-RF3DR-X2BQT|

Windows 7

|Edición de Sistema Operativo| Clave KMS|
|---|---|
|Windows 7 Professional|FJ82H-XT6CR-J8D7P-XQJJ2-GPDD4|
|Windows 7 Professional N|MRPKT-YTG23-K7D7T-X2JMM-QY7MG|
|Windows 7 Professional E|W82YF-2Q76Y-63HXB-FGJG9-GF7QX|
|Windows 7 Enterprise|33PXH-7Y6KF-2VJC9-XBBR8-HVTHH|
|Windows 7 Enterprise N|YDRBP-3D83W-TY26F-D46B2-XCKRJ|
|Windows 7 Enterprise E|C29WB-22CC8-VJ326-GHFJW-H9DH4|

Windows Vista

|Edición de Sistema Operativo| Clave KMS|
|---|---|
|Windows Vista Business|YFKBB-PQJJV-G996G-VWGXY-2V3X8|
|Windows Vista Business N|HMBQG-8H2RH-C77VX-27R82-VMQBT|
|Windows Vista Enterprise|VKK3X-68KWM-X2YGT-QR4M6-4BWMV|
|Windows Vista Enterprise N|VTC42-BM838-43QHV-84HX6-XJXKV|

<p style='text-align: justify'>Fuente: <a href= "https://learn.microsoft.com/en-us/windows-server/get-started/kms-client-activation-keys."> Key Management Services client activation and product key.</a></p> 

### Activación manual (Basada en documentación).
Ejecutarse en cmd como administrador.

1.- Conectarse al servidor (Normalmente este paso es automatizado cuando el server KMS existe en la misma red.)

```console
slmgr /skms <Dominio>
```

2.- Agregar clave del producto

```console
slmgr /ipk <clave kms>
```

3.- Active el producto utilizando el ID de confirmación proporcionado por el usuario. (Este paso también es automatizado cuando el servidor KMS existe en la misma red.)

```console
slmgr /ato
```

<p style='text-align: justify'>Fuente: <a href= "https://learn.microsoft.com/en-us/windows-server/get-started/kms-client-activation-keys#install-a-product-key"> Install product key</a>, <a href="https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn502540(v=ws.11)">slmgr.</a></p>

### NIJIKA. Script escrito en powershell.

![Desktop View](/img/in-post/jawa_post/nijika-icon.jpg){: w="400" h="200" }

<p style='text-align: justify'>NIJIKA (Nijika Is Just Interface KMS Activator) es un script hecho en powershell, con el objetivo de realizar una activación mediante KMS. De manera rápida, sin descargar archivos con la mínima cantidad de lineas escritas. Actualmente solo cuenta con soporte para las siguientes versiones: <a href='https://github.com/quantumwavves/NIJIKA#supported-versions'>Versiones soportadas.</a> NIJIKA es open source por lo que cualquiera puede leer el código fuente para poder estudiarlo, modificarlo u redistribuirlo: </p>

<center><a href="https://github.com/quantumwavves/NIJIKA"><img src="/img/in-post/jawa_post/github-logo.png" alt="Github" style="width:60px;height:60px;"></a></center>

<br>
Uso de NIJIKA

Ejecutar la siguiente linea en powershell como administrador:

```console
irm cutt.ly/NIJIKA | iex
```

<p style='text-align: justify'>Saltaran un menu con 3 opciones, una donde el usuario puede elegir su propio servidor kms, otro con la opción de colocar un servidor kms por defecto y una tercera opción para eliminar cualquier activación por kms, elija en base a sus necesidades. El script aun esta en construcción, por lo que se añadirán opciones mas adelante.</p>

![Desktop View](/img/in-post/jawa_post/nijika-menu.png){: w="500" h="200" }

Una vez completado el paso a elegir se mostrará el siguiente mensaje:

Para activar la licencia:

![Desktop View](/img/in-post/jawa_post/nijika-op1-2.png){: w="500" h="200" }

Para eliminar la licencia:

![Desktop View](/img/in-post/jawa_post/nijika-op3.png){: w="500" h="200" }

### Algunos comandos con slmgr.

Seguramente estés buscando este jaja, quitar licencia KMS:

```console
slmgr /upk
```

Sin embargo para quitar la conexión del servidor KMS usa:

```console
slmgr /ckms
```

Obtener información de la activación:

```console
slmgr /dti 
```
Obtener fecha de expiración:

```console
slmgr /xpr
```

<p style='text-align: justify'>Fuente: <a href= "https://learn.microsoft.com/en-us/windows-server/get-started/activation-slmgr-vbs-options"> slmgr.vbs</a>.</p>

### Dudas de la activación por kms.

<p style='text-align: justify'>¿Es segura la activación por kms?<br>La respuesta corta es SI. Siempre y cuando hayas adquirido estos servicios con microsoft y tengas desplegado tu propio servidor KMS. Para más información de como deployar un KMS server <a href="https://learn.microsoft.com/en-us/windows-server/get-started/kms-create-host">aqui</a>.</p>
<p>¿Pero es seguro conectarse a los servidores que encontramos en diferentes sitios?<br>Para ello tenemos que entender como funciona un los protocolos TCP y UDP. Transmission Control Protocol (TCP) es el protocolo usado en la red de redes, es decir, el internet. El protocolo TCP es incluso utilizado por otros protocolos de internet como lo son SSH, FTP, HTTP. Este modelo se compone de 4 capas:</p>
<ul>
  <li>Capa de aplicación: establece la conexión entre la aplicación y los datos. También abre el acceso a múltiples recursos de la red.</li>
  <li>Capa de transporte: crea conexiones TCP y determina la cantidad de datos que deben enviarse.</li>
  <li>Capa de Internet: envía paquetes IP al destino real utilizando varias redes.</li>
  <li>Capa de enlace o interfaz de red: controla la mensajería física y los medios para la transmisión de datos.</li>
</ul>

![Desktop View](/img/in-post/jawa_post/tcp-diagram.jpg){: h='900' w='400' }

<p style='text-align: justify'>Aquí. La principal diferencia entre TCP y UDP es que el protocolo TCP reenvía paquetes que pueden haberse perdido en la transmisión y lo hace de manera secuencial, mientras que el protocolo UDP no reenviá paquetes y no es secuencial, por lo que puede haber perdida de paquetes.<br>Ahora que tenemos un poco de contexto sobre estos protocolos, analizaremos la conexión con un servidor conocido para este tipo de prácticas. El servidor seleccionado es kms.digiboy.ir,  lo primero que haremos es escanear los puertos del dominio, para ello utilizaremos la herramienta nmap. Haremos un escaneo desde el puerto 1 al 65535.</p>

#### Analizando servidor de 3ros.

![Desktop View](/img/in-post/jawa_post/nmap-kms-server.png){: w="600" h="400"}

<p style='text-align: justify'>Vemos que el puerto 53 TCP está abierto, por lo que sabiendo los puertos conocidos, este se utiliza tanto UDP como TCP para la transmisión de nombres de dominio (DNS). Quiere decir que al conectarse a este servidor es como si nos conectásemos al 8.8.8.8 que es el servidor de nombres de dominio de Google. En estos se guardarán los registros para los hosts, por lo que habrá que realizar un tracert o tracepath para saber hacia qué servidor se está haciendo la conexión. Utilizando la utilidad de tracert en Windows obtenemos la dirección final de un servidor.</p>

![Desktop View](/img/in-post/jawa_post/tracert-kms.png){: w="600" h="400" }

Realizaremos un escaneo a los puertos del servidor final con nmap.

![Desktop View](/img/in-post/jawa_post/nmap-kms-instance1.png){: w="600" h="400" }

<p style='text-align: justify'>Por los puertos conocidos nos damos cuenta de que es un windows server. Y podemos ver los puertos que están abiertos, los cuales son:
53 TCP utilizado para nombres de dominio.</p>
<ul>
<li>135 TCP se utiliza para el servicio de DCOM (Distributed Component Object Model) en Windows. DCOM permite la comunicación entre aplicaciones en diferentes computadoras en una red. Este puerto es utilizado para el acceso remoto y la administración de componentes distribuidos.</li>
<li>80 TCP es el puerto predeterminado utilizado para el protocolo HTTP (Hypertext Transfer Protocol). Se utiliza para servir páginas web a través de Internet. El tráfico web regularmente se dirige a este puerto cuando se accede a un servidor web.</li>
<li>445 TCP se utiliza para el protocolo de intercomunicación de sistemas abiertos de Microsoft (MS-SMB) sobre el protocolo TCP/IP. Es utilizado por el servicio de uso compartido de archivos de Windows (SMB) para permitir la comunicación y el intercambio de archivos en una red local.</li>
<li>1392 TCP En este caso este servicio corresponde a un servidor de impresión o print server en inglés.</li>
<li>1688 TCP se utiliza para el servicio de activación de Microsoft (MS Licensing). Específicamente, este puerto se utiliza para la activación de volumen de Windows y Office. Se comunica con los servidores de Microsoft para validar las licencias y activar el software en los sistemas clientes.</li>
<li>49145 TCP este es un protocolo desconocido.</li>
</ul>

Ahora utilizaremos traceroute, en teoría debería darnos el mismo path que tracert.

![Desktop View](/img/in-post/jawa_post/traceroute-kms.png){: w="800" h="600"}

<p>Observamos que obtenemos otra dirección IPV4 diferente a la que nos mostró tracert, esto nos indica que existen 2 servidores a los cuales hace conexión por el puerto 1688 tcp. Esto fácilmente se puede ver con la herramienta nslookup.</p>

![Desktop View](/img/in-post/jawa_post/nslookup-kms.png){: w="600" h="400"}

<p style='text-align: justify'>Ya hemos analizado los puertos de uno de los dos servidores, ahora realizáremos el escaneo al otro servidor.</p>

![Desktop View](/img/in-post/jawa_post/nmap-kms-instance2.png){: w="600" h="400"}

<p style='text-align: justify'>Vemos que existen algunos puertos repetidos, pero aparecen otros que no. Estos puertos son:</p>
<ul>
<li>21 TCP este protocolo es un puerto conocido para FTP de las siglas file transfer protocol, sirve para transferencia de archivos. En este caso el puerto es cerrado.</li>
<li>1395 TCP en este caso el protocolo corresponde a un programa de PC Workstation Manager software</li>
<li>34775 TCP puerto desconocido</li>
<li>51413 TCP puerto desconocido</li>
</ul>

<p style='text-align: justify'>Adicional a esto haremos un escaneo a la máquina cliente, la cual fue activada con este servidor.</p>

![Desktop View](/img/in-post/jawa_post/kms-client.png){: w="600" h="400"}

<p style='text-align: justify'>Esto solo nos muestra los puertos abiertos en el cliente, para saber que conexiones son las que están en uso debemos directamente consultarlo desde powershell o cmd. Obtendremos las conexiones TCP:</p>

![Desktop View](/img/in-post/jawa_post/tcp-client.png){: w="800" h="600"}

Adicionalmente, agregaré las conexiones UDP, pero como explicamos, este protocolo no reenvía paquetes y no lo hace secuencialmente.

![Desktop View](/img/in-post/jawa_post/udp-client.png){: w="800" h="600"}

Ahora realizaremos una enumeracion al servicio SMB

![Desktop View](/img/in-post/jawa_post/smb-enum.png){: w="800" h="600"}

Podemos notar que no existen reglas seteadas para un usuario NULL

Este servidor contiene un reporte en AnyRun, véase <a href="https://any.run/report/4b8da721706aa2264c5c402c2bd4d46274d81ad6108e827c65dfbcd2dc83aef1/881e29e9-29ed-48ad-8435-87f672ac48bb">aquí</a>.

![Desktop View](/img/in-post/jawa_post/kms-anyrun.png){: w="800" h="600"}

Ahora analizaremos el tráfico HTTP y HTTPS en el tiempo de la activación.

 <video width="700" height="500" controls>
  <source src="/img/in-post/jawa_post/TCP-Services.mp4" type="video/mp4">
</video> 

### Conclusiones.

<p style='text-align: justify'>Siempre y cuando adquieras este método de licenciamiento con Microsoft no hay problema. Por otro lado, si quieres conectarte a un servidor de terceros tienes que ser precavido, ya que al menos en esta ocasión y con este servidor en particular se han hecho pruebas e investigación para saber sobre su fiabilidad y seguridad. Aunque a priori este servidor parece ser el menos intrusivo y seguro, no quiere decir que todos lo sean, además agregar que tú eres el responsable de la seguridad de tu sistema, usa ANTIVIRUS, ten al día tus bases de datos el mismo y siempre ten bien configurado tu firewall. Sin embargo, siempre te recomendaré adquirir tus licencias con el fabricante del software.  Eso ha sido todo por este post, esperando que te haya gustado y estaré atento a tus comentarios :).</p>



<script src="https://giscus.app/client.js"
        data-repo="quantumwavves/quantumwavves.github.io"
        data-repo-id="R_kgDOJ0bLEg"
        data-category="[NOMBRE CATEGORÍA]"
        data-category-id="[ID CATEGORÍA]"
        data-mapping="pathname"
        data-strict="0"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="bottom"
        data-theme="dark"
        data-lang="es"
        crossorigin="anonymous"
        async>
</script>
