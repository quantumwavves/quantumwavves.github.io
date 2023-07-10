---
title: Activación KMS de Microsoft Office.
date: 2023-07-10 00:48:09 +/-TTTT
categories: [Windows, KMS]
tags: [windows, kms, activación, microsoft, office]     # TAG names should always be lowercase
comments: true
image:
  path: /assets/posts/office_post/office-banner.png
  alt: Microsoft Office Suite
pin: true
---
<br>
<p style="text-align: justify">Bom día. En este post les enseñaré como realizar una activación kms para Microsoft Office. Hay que aclarar que esto solo será válido siempre y cuando la versión sea anterior a Office 365. Ya hemos analizado algunos aspectos sobre que es KMS y sobre los servidores de terceros. Recomendamos leerlo para tener un mejor contexto.<a href="https://quantumwavves.github.io/posts/windows-kms-activation/"> Léase aquí.</a></p>

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

![Desktop View](/assets/posts/office_post/kita-icon.jpg){: w="400" h="200" }

<p style="text-align: justify">¿Como funciona KITA?
KITA es solo un script que realiza el deployment de office ProPlus y 365. Esto quiere decir que se hace uso de herramientas de microsoft y la descarga de la suite es directamente de los servidores de microsoft.</p>

**Uso de KITA**

```shell 
irm cutt.ly/KITA | iex
```

<p style="text-align: justify">El menú de KITA contiene cuatro opciones, entre las cuales se encuentran la instalación de la suite office (Sin activación), activación de la suite mediante KMS, desactivación de la suite.</p>

![Desktop View](/assets/posts/office_post/kita-menu.png){: w="400" h="200" }

Para nuestra primera opción podemos seleccionar la versión a instalar

![Desktop View](/assets/posts/office_post/kita-op-1.png){: w="400" h="200" }

De igual manera podemos seleccionar el bloat (peso) de las aplicaciones que queramos:

![Desktop View](/assets/posts/office_post/kita-op-1-bloat.png){: w="800" h="600" }

Una vez completada la instalación, nos preguntara si queremos activar office: 

![Desktop View](/assets/posts/office_post/kita-act-ask.png){: w="400" h="200" }

Nos mandara a la segunda opcion del menu: 

![Desktop View](/assets/posts/office_post/kita-op-2.png){: w="400" h="200" }

Cuando la activación muestra la salida. 

![Desktop View](/assets/posts/office_post/kita-act-com.png){: w="600" h="400" }

Para la elección 3, nos mostrará la siente salida:

![Desktop View](/assets/posts/office_post/kita-op-3.png){: w="600" h="400" }

**Problemas al momento de la desactivación**

<p style="text-align: justify">El script hace uso de /unpkey:XXXXX. Tambien se hace uso de la funcion /ckms para eliminar, de igual manera se hace uso de la funcion /rearm para re armar la instalación de office. En caso de no realizarse la desactivación realizar un /ream en el path de office, para ello introduciremos los siguientes comandos en PowerShell: </p>

```shell 
cd C:\Program Files\Microsoft Office\Office16
```
Y para realizar el re armado utilizaremos el siguiente comando:
```shell
& cscript.exe ospp.vbs /rearm
```

<p style="text-align: justify">Fuentes:<a href="https://learn.microsoft.com/en-us/deployoffice/overview-office-deployment-tool"> Overview of the office deployment</a>.</p>

### Comandos con ospp.vbs.

Mostrar información de la activación:
```shell
& cscript.exe ospp.vbs /dstatus
```
Mostrar información mas detallada de la activación:
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

### ¿Son seguros los servidores kms de terceros?

<p style="text-align: justify">Este punto ya lo hemos analizado en el post anterior, recomendamos leer el post anterior para tener un mejor contexto. Resumidamente podemos decir que se necesitan hacer pruebas para verificar su fiabilidad, sin embargo kms.digiboy.ir es un dominio seguro.</p>

### Conclusiones.

<p style="text-align: justify">Mientras adquieras este servicio mediante Microsoft no debería haber ningún problema y si vas a realizar una activación mediante un dominio, asegúrate que este sea seguro y hazlo bajo tu propio riesgo. :)</p>
