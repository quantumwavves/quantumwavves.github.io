---
layout: post
title: DESPLIEGUE Y ACTIVACION DE MICROSOFT OFFICE
subtitle: ¿Qué es un deploy, como funciona, como activar office y que pasa con los servidores de terceros?
header-img: img/in-post/office_post/ganyu-hutao.png
header-style: image
header-mask: rgba(0, 0, 0, .4)
catalog: true
tags:
  - office
  - kms
  - activación
  - deploy
---

<!-- HTML Meta Tags -->
<title>DESPLIEGUE Y ACTIVACION DE MICROSOFT OFFICE.</title>
<meta name="description" content="Un pequeño post que explica que es la office deployment tool y la activación KMS.">
<meta property="og:site_name" content="QuantumWavves">
<meta property="og:image" content="https://quantumwavves.github.io/img/in-post/office_post/ganyu-hutao.png">

<!-- Facebook Meta Tags -->
<meta property="og:url" content="https://quantumwavves.github.io/2023/07/12/ms-office-kms-activation/">
<meta property="og:type" content="website">
<meta property="og:title" content="DESPLIEGUE Y ACTIVACION DE MICROSOFT OFFICE.">
<meta property="og:description" content="Un pequeño post que explica que es la office deployment tool y la activación KMS.">
<meta property="og:image" content="https://quantumwavves.github.io/img/in-post/office_post/ganyu-hutao.png">

<!-- Twitter Meta Tags -->
<meta name="twitter:card" content="summary_large_image">
<meta property="twitter:domain" content="quantumwavves.github.io">
<meta property="twitter:url" content="https://quantumwavves.github.io/2023/07/12/ms-office-kms-activation/">
<meta name="twitter:title" content="DESPLIEGUE Y ACTIVACION DE MICROSOFT OFFICE.">
<meta name="twitter:description" content="Un pequeño post que explica que es la office deployment tool y la activación KMS.">
<meta name="twitter:image" content="https://quantumwavves.github.io/img/in-post/office_post/ganyu-hutao.png">

<!-- Meta Tags Generated via https://opengraph.dev -->

### Introduccion:
<p style="text-align: justify">Saludos a todos. En este post les enseñaré como un desplegar una instalación de Microsoft Office. La activación con Key Managment Server (KMS) de Microsoft Office (Hay que aclarar que esto solo será válido siempre y cuando la versión sea anterior a Office 365)</p>

### Despliegue de Office

#### ¿Que es office deployment tool?

- Link de descarga oficial: <a href="https://www.microsoft.com/en-us/download/details.aspx?id=49117" class="fa-brands fa-windows"> www.microsoft.com</a>

<p style="text-align: justify">La Herramienta de implementación de Office (ODT) es una herramienta de línea de comandos que puede usar para descargar e implementar Aplicaciones Microsoft 365 o Microsoft Office 2021,2019. La ODT le ofrece más control que una instalación de Office: se pueden definir los productos e idiomas que se instalarán, cómo se actualizarán esos productos y si se quiere o no mostrar la experiencia de instalación a los usuarios. La ODT consiste en dos archivos: setup.exe y configuration.xml (la cual se puede personalizar al gusto de cada quien). Para trabajar con la herramienta, es necesario crear el archivo de configuración para definir las opciones que quiera usar, tales como productos, idiomas y actualizaciones.</p>

#### ¿Como realizar un deploy?

##### Configuración hecha en XML 

Ejemplo de un archivo XML para la instalación de Microsoft Office 365: 

```xml
<!--Office 365 minimal version-->
<!--configuración tomada del proyecto KITA-->

<Configuration>
  <Add OfficeClientEdition="64">
    <Product ID="O365ProPlusRetail">
      <Language ID="MatchOS" Fallback="en-us" />
      <ExcludeApp ID="Outlook" />
      <ExcludeApp ID="OneDrive" />
      <ExcludeApp ID="Access" />
      <ExcludeApp ID="Publisher" />
      <ExcludeApp ID="Lync" />
      <ExcludeApp ID="Skype" />
      <ExcludeApp ID="Bing" />
    </Product>
  </Add>
  <RemoveMSI All="True" />
  <Display Level="None" AcceptEULA="TRUE" />
</Configuration>
```
Todos los parametros de configuración aqui: <a href="https://learn.microsoft.com/en-us/deployoffice/office-deployment-tool-configuration-options">Office deployment tool configuration options</a>

##### Pasos para realizar el despliegue 

Necesitaremos extraer el archivo ejecutable de setup que se encuentra dentro del ejecutable del office developement tool. Para ello haremos uso del siguiente comado:

```shell
officedeploymenttool_16731-20290.exe /quiet /extract:C:\Users\People1\Documents\FilesDevTool"
```

Explicando el comando anterior, `officedeploymenttool_16731-20290.exe` es el ejecutable previamente descargado de la pagina oficial de microsoft, su nombre puede cambiar ya que constantemente recibe actualizaciones, un ejemplo seria `officedeploymenttool_16961-20870.exe`.info en donde solo cambian los ultimos numeros del nombre, `/quiet` es un parametros del ejecutable que indica una ejecucion silenciosa (sin output en la shell), `/extract` es un parametro que nos permite extraer los ficeros del ejecutable este parametro necesita una ruta, en el ejemplo se coloco `C:\Users\People1\Documents\FilesDevTool` aun que podria ser cualquier otra.<br>

Para realizar el despliegue (Instalación) de los productos de Office, utilizaremos la PowerShell integrada en Windows (Se requieren permisos administrativos). El comando consta de dos partes, el primero que es `setup.exe` que es un ejecutable, el parametro `/configure` que indica que se utilizara un archivo XML para una instalación custom y la ruta del archivo `XML` que en este ejemplo es `config.xml`

```shell
setup.exe /configure config.xml
```

El ejecutable `setup.exe` cuenta con un modo descarga:

```shell
setup.exe /download config.xml
```

Fuente y mas demas parametros para la herramienta: <a href="https://learn.microsoft.com/es-mx/deployoffice/overview-office-deployment-tool"> microsoft learn deployoffice overview-office-deployment-tool</a>

## KMS

### ¿Que es KMS?

<p style="text-align: justify">KMS es un servicio de activación ofrecido por Microsoft, esta modalidad es mediante volumen de licencias, por ello debera adquirirse mediante Business Center. Como ya hemos visto en el post anterior, podemos afirmar que KMS de las siglas (Key management volume) es un servicio de internet, asi como lo son SSH, FTP, HTTPS, SMTP. Como todos los servicios de internet este utiliza un puerto conocido, que en este caso es el 1688 TCP/IP.</p>
Fuente <a href="https://learn.microsoft.com/en-us/deployoffice/vlactivation/plan-volume-activation-of-office">Plan volume activation of office.</a>

### KMS Keys

|Office 2021 | KMS Key |
|---|---|
|Office LTSC Professional Plus 2021	|FXYTK-NJJ8C-GB6DW-3DYQT-6F7TH
|Office LTSC Standard 2021	|KDX7X-BNVR8-TXXGX-4Q7Y8-78VT3
|Project Professional 2021	|FTNWT-C6WBT-8HMGF-K9PRX-QV9H8
|Project Standard 2021	|J2JDC-NJCYY-9RGQ4-YXWMH-T3D4T
|Visio LTSC Professional 2021	|KNH8D-FGHT4-T8RK3-CTDYJ-K2HT4
|Visio LTSC Standard 2021|	MJVNY-BYWPY-CWV6J-2RKRT-4M8QG
|Access LTSC 2021	|WM8YG-YNGDD-4JHDC-PG3F4-FC4T4
|Excel LTSC 2021	|NWG3X-87C9K-TC7YY-BC2G7-G6RVC
|Outlook LTSC 2021	|C9FM6-3N72F-HFJXB-TM3V9-T86R9
|PowerPoint LTSC 2021	|TY7XF-NFRBR-KJ44C-G83KF-GX27K
|Publisher LTSC 2021	|2MW9D-N4BXM-9VBPG-Q7W6M-KFBGQ
|Skype for Business LTSC 2021	|HWCXN-K3WBT-WJBKY-R8BD9-XK29P
|Word LTSC 2021	|TN8H9-M34D3-Y64V9-TR72V-X79KV

|Office 2019 | KMS Key |
|---|---|
|Office Professional Plus 2019 |NMMKJ-6RK4F-KMJVX-8D9MJ-6MWKP
|Office Standard 2019 |6NWWJ-YQWMR-QKGCB-6TMB3-9D9HK
|Project Professional 2019 |B4NPR-3FKK7-T2MBV-FRQ4W-PKD2B
|Project Standard 2019 |C4F7P-NCP8C-6CQPT-MQHV9-JXD2M
|Visio Professional 2019 |9BGNQ-K37YR-RQHF2-38RQ3-7VCBB
|Visio Standard 2019 |7TQNQ-K3YQQ-3PFH7-CCPPM-X4VQ2
|Access 2019 |9N9PT-27V4Y-VJ2PD-YXFMF-YTFQT
|Excel 2019 |TMJWT-YYNMB-3BKTF-644FC-RVXBD
|Outlook 2019 |7HD7K-N4PVK-BHBCQ-YWQRW-XW4VK
|PowerPoint 2019 |RRNCX-C64HY-W2MM7-MCH9G-TJHMQ
|Publisher 2019 |G2KWX-3NW6P-PY93R-JXK2T-C9Y9V
|Skype for Business 2019 |NCJ33-JHBBY-HTK98-MYCV8-HMKHJ
|Word 2019 |PBX3G-NWMT6-Q7XBW-PYJGG-WXD33

|Office 2016 | KMS Key |
|---|---|
|Office Professional Plus 2016 |XQNVK-8JYDB-WJ9W3-YJ8YR-WFG99
|Office Standard 2016 |JNRGM-WHDWX-FJJG3-K47QV-DRTFM
|Project Professional 2016 |YG9NW-3K39V-2T3HJ-93F3Q-G83KT
|Project Standard 2016 |GNFHQ-F6YQM-KQDGJ-327XX-KQBVC
|Visio Professional 2016 |PD3PC-RHNGV-FXJ29-8JK7D-RJRJK
|Visio Standard 2016 |7WHWN-4T7MP-G96JF-G33KR-W8GF4
|Access 2016 |GNH9Y-D2J4T-FJHGG-QRVH7-QPFDW
|Excel 2016 |9C2PK-NWTVB-JMPW8-BFT28-7FTBF
|OneNote 2016 |DR92N-9HTF2-97XKM-XW2WJ-XW3J6
|Outlook 2016 |R69KK-NTPKF-7M3Q4-QYBHW-6MT9B
|PowerPoint 2016 |J7MQP-HNJ4Y-WJ7YM-PFYGF-BY6C6
|Publisher 2016 |F47MM-N3XJP-TQXJ9-BP99D-8837K
|Skype for Business 2016 |869NQ-FJ69K-466HW-QYCP2-DDBV6
|Word 2016 |WXY84-JN2Q9-RBCCQ-3Q3J3-3PFJ6

Fuente: <a href="https://gist.github.com/jerodg/502bd80a715347662e79af526c98f187#office-2019">jerodg/windows_and_office_kms_setup.adoc.</a>

### Activación manual basada en documentación.

Para realizar la activación manualmente con base a la documentación, realizaremos los siguientes comandos en cmd:
Movernos al path de office:
```shell
cd /d %ProgramFiles(x86)%\Microsoft Office\Office16
cd /d %ProgramFiles%\Microsoft Office\Office16
```
Instalar las licencias:
```shell
for /f %x in ('dir /b ..\root\Licenses16\<office volume versión>VL_KMS*.xrm-ms') do cscript ospp.vbs /inslic:"..\root\Licenses16\%x"
```
Setear puerto para la activación, instalar product key, setear servidor kms:
```shell 
cscript ospp.vbs /setprt:1688
cscript ospp.vbs /unpkey:<last 5 digits keys> >nul
cscript ospp.vbs /inpkey:<kms key>
cscript ospp.vbs /sethst:<kms server>
cscript ospp.vbs /act
```


Fuente: <a href="https://learn.microsoft.com/en-us/deployoffice/vlactivation/tools-to-manage-volume-activation-of-office#the-osppvbs-script">Tools to manage volume activation off office.</a>

### KITA. Script en PowerShell.
<p style="text-align: justify">KITA (Kita Interface Tool Activator). Es un script escrito en PowerShell que busca automatizar la instalación de Microsoft Office, activación y desactivación KMS de una manera sencilla. KITA solo tiene estas versiones soportadas:<a href="https://github.com/quantumwavves/KITA#supported-versions"> Véase aquí.</a></p>

![Desktop View](/img/in-post/office_post/kita.gif)

<p style="text-align: justify">¿Como funciona KITA?
KITA es solo un script que realiza el despliegue de Microsoft Office. Esto quiere decir que se hace uso de herramientas de microsoft y la descarga de la suite es directamente de los servidores de microsoft. KITA es open source, por lo que se puede leer, estudiar y redistribuir. Esta licenciado bajo GPL v3.</p> 

- <a href="https://github.com/quantumwavves/KITA" class="fa-brands fa-github"> KITA</a>


#### Uso de KITA

Ejectuar en PowerShell como administrador:
```shell 
irm cutt.ly/IKUYO | iex
```

<p style="text-align: justify">El menú de KITA contiene cuatro opciones, entre las cuales se encuentran la instalación de la suite office (Sin activación), activación de la suite mediante KMS, desactivación de la suite.</p>

![Desktop View](/img/in-post/office_post/kita-menu.png){: w="400" h="200" }

Para nuestra primera opción podemos seleccionar la versión a instalar

![Desktop View](/img/in-post/office_post/kita-op-1.png){: w="400" h="200" }

De igual manera podemos seleccionar el bloat (peso) de las aplicaciones que queramos:

![Desktop View](/img/in-post/office_post/kita-op-1-bloat.png){: w="800" h="600" }

Una vez completada la instalación, nos preguntara si queremos activar office: 

![Desktop View](/img/in-post/office_post/kita-act-ask.png){: w="400" h="200" }

Nos mandara a la segunda opcion del menu: 

![Desktop View](/img/in-post/office_post/kita-op-2.png){: w="400" h="200" }

Cuando la activación muestra la salida. 

![Desktop View](/img/in-post/office_post/kita-act-com.png){: w="600" h="400" }

Para la elección 3, nos mostrará la siente salida:

![Desktop View](/img/in-post/office_post/kita-op-3.png){: w="600" h="400" }

**Problemas al momento de la desactivación**

<p style="text-align: justify">El script hace uso de /unpkey:XXXXX, esto nos permite quitar la clave del producto. Tambien se hace uso de la funcion /ckms para eliminar el registro al dominio, de igual manera se hace uso de la funcion /rearm para re armar la instalación de office con los valores default de una instalación limpia. En caso de no realizarse la desactivación se necesita realizar un /rearm en el path de office manualmente, para ello introduciremos los siguientes comandos en PowerShell como administrador: </p>

```shell 
cd C:\Program Files\Microsoft Office\Office16
```
Y para realizar el re armado utilizaremos el siguiente comando:
```shell
& cscript.exe ospp.vbs /rearm
```

<p style="text-align: justify">Fuentes:<a href="https://learn.microsoft.com/en-us/deployoffice/vlactivation/rearm-an-office-installation-on-an-image-when-using-kms-to-activate"> Overview of the office deployment</a>.</p>

### Comandos con ospp.vbs.

Mostrar información de la activación:
```shell
& cscript.exe ospp.vbs /dstatus
```
Mostrar información mas detallada de todas las activaciónes:
```shell
& cscript.exe ospp.vbs /dstatusall
```
Mostrar el historial KMS:
```shell
& cscript.exe ospp.vbs /dhistorykms 
```
Desactivar el caching:
```shell
& cscript.exe ospp.vbs /cachst:FALSE
```

Fuente: <a href="https://learn.microsoft.com/en-us/deployoffice/vlactivation/tools-to-manage-volume-activation-of-office#global-options-for-osppvbs">Global options for ospp.vbs.</a>

## Servidores KMS de terceros

<p style="text-align: justify">Este punto ya lo hemos analizado en el post anterior, sin embargo abarcaremos la misma informacion que se coloco no obstante recomendamos leer el post anterior para tener un mejor contexto. A dia de hoy existen solo dos maneras de lograr una activación KMS. Adquiriendo esto mediante el Business center de microsoft o mediante emulacion de un servidor KMS. De cualquier modo, recae en el usuario el servidor al cual se conecte. Y si el mismo lo ha validado como seguro o no.</p>

#### Analizando servidor kms.digiboy.ir 

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

Podemos notar que no existen recursos compartidos para un usuario NULL o anonimo.

Este servidor contiene un reporte en AnyRun, véase <a href="https://any.run/report/4b8da721706aa2264c5c402c2bd4d46274d81ad6108e827c65dfbcd2dc83aef1/881e29e9-29ed-48ad-8435-87f672ac48bb">aquí</a>.

![Desktop View](/img/in-post/jawa_post/kms-anyrun.png){: w="800" h="600"}

Ahora analizaremos el tráfico HTTP y HTTPS en el tiempo de la activación.

 <video width="700" height="500" controls>
  <source src="/img/in-post/jawa_post/TCP-Services.mp4" type="video/mp4">
</video> 

#### ¿Backdoors en servidores de terceros?
Para poder empezar con este punto primero hay que dejar en claro que es un backdoor, la enciclopedia de kaspersky lo define como: Los Backdoors (troyanos de puerta trasera) están diseñados para dar a los usuarios maliciosos el control de un equipo infectado. En términos de funcionalidad, las “puertas traseras” son similares a muchos sistemas de administración diseñados y distribuidos por desarrolladores de programas legítimos. Fuente: <a href="https://encyclopedia.kaspersky.es/knowledge/backdoor/">encyclopedia.kaspersky.es</a><br><br>
Una vez definido que es un backdoor podemos pasar al siguiente articulo por Malwarebytes labs: <a href="https://www.malwarebytes.com/blog/news/2022/08/kmspico-explained-no-kms-is-not-kill-microsoft">kmspico explained, no KMS is not kill microsoft</a><br>

![malwarebytes](/img/in-post/office_post/kms-malwarebytes.jpg) 

En este articulo nos explican el funcionamiento de `KMSPico` un programa conocido por realizar activaciones tanto de windows como de Microsoft Office. En este post nos explica que KMSPico hace uso del proceso legitimo de una activacion KMS. Sin embargo esta publicacion tambien no habla sobre los riegos alrededor de esta herramienta los cuales describe como el tener multiples "paginas oficiales" generando desconfianza, ya que usuarios advierten que el sitio A contiene malware y otros que el sitio B tiene malware. Tambien nos menciona que la herramienta si existe y tiene como ultima version la `10.2.0` la cual solo puede descargarse en un foro que es solo accesible a miembros y que tiene mas de una decada que fue hecha dicha publicacion de la release. En este post cualifican al software `KMSPico` como un riskware debido a su origen desconocido de la herramienta, mas no al procedimiento legitimo de KMS.

¿Pero, que es un `riskware`? Kaspersky lo clasifica como: Riskware es el nombre que se asigna a programas legítimos que pueden causar daño si son aprovechados por usuarios maliciosos para eliminar, bloquear, modificar o copiar datos, así como para alterar el rendimiento de computadoras o redes. El riskware incluye los siguientes tipos de programas que se usan comúnmente para fines legítimos:

- Utilidades de administración remota
- Clientes IRC
- Programas de marcador
- Descargadores de archivos 
- Software para monitorear la actividad de la computadora
- Utilidades de administración de contraseña 
- Servicios de servidor de Internet, como FTP, Web, proxy y telnet

Bajo este concepto `MSI Afterburner` podria considerarse como riskware si se hace un uso ilegitimo de el mediante una vulnerabilidad. Pero a que se debe que un software que tenga fines legítimos pueda ser utilizado como un riskware, bueno esto tiene multiples factores, pero sin dudas el principal es la tasa de mercado del sistema operativo `Windows` ya que actualmente tiene 75% de cuota de mercado en computadoras de escritorio y laptos, esto basado en el tercer trimestre de 2022 estos datos son publicados por <a href="https://es.statista.com/estadisticas/576870/cuota-de-mercado-mundial-de-los-sistemas-operativos/">statista.com</a>.

![cuota](/img/in-post/office_post/cuota.png) 

Esto hace que Windows sea un objetivo recurrente a vulnerar y si comparamos el numero de vulnerabilidades de `Windows` con otros sistemas operativos veremos el sistema de Microsoft tiene 11232 vulnerabilidades listadas desde el año 1999 hasta el 2023 por lo que es `36.07 %` mas vulnerable a comparacion del kernel `Linux` quien cuenta con 7180 vulnerabilidades listadas desde 1999, Windows es `62.56 %` mas vulnerable a comparacion de `MacOS` quien cuenta con 4205 vulnerabilidades listadas desde 1999 y es `98.88 %` mas vulnerable a comparacion de el kernel `BSD` el cual tiene 125 vulnerabilidades generales desde 1999. Estas cifras son solo aproximaciones sacadas con fecha del `22 Octubre 2023` usando como referencia a Mitre, la base de datos de vulnerabilidades mas conocida: <a href="https://cve.mitre.org/index.html">cve.mitre.org</a><br>

"Bueno pero al conectarse con servidor de estos pueden establecer politicas en tu computadora para poder crear puertas traseras". Hay que entender que una cosa es la activación KMS donde es necesario al menos establecer una conexión para la activación y una revalidacion cada 180 dias y la activación basada en Active Directory,esta ultima ya no hace uso de registros SRV ni de un puerto en especifico, si no que se hace mediante la administración de Active Directory donde si se pueden estasblecer workgroups, usuarios o politicas de control, que en un principio no deberia ser un problema `Si tu empresa es quien administra este metodo de Active Directory y la activacion por volumen`.

¿Pero que son los servidores KMS de terceros? Estos principalmente son servidores que son emulados, podemos ver que existen los siguientes proyectos que cumplen con esa funcion:

- [py-kms](https://github.com/SystemRage/py-kms). Emulador escrito en python.
- [vlmcsd](https://github.com/Wind4/vlmcsd). Emulador escrito en C.

Estos utilizan las keys GVLK, mismas que se encuentran en microsoft: <a href="https://learn.microsoft.com/en-us/windows-server/get-started/kms-client-activation-keys">generic-volume-license-keys-gvlk</a>

## Conclusiones.

Explorar este tipo de activaciones por volumen es meramente con fines educativos, estos metodos de activación estan principalmente dirigidos a las grandes empresas quienes puedes costearlos. Si necesitas realizar una activación de Office o Windows puedes adquirir claves OEM. Sin embargo existen software de ofimatica de codigo abierto como lo son libreoffice, open office o WPS office. 
