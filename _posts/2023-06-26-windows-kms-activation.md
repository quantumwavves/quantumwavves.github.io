---
title: Activación KMS de Windows
date: 2023-06-26 11:30:09 +/-TTTT
categories: [Windows, Kms]
tags: [windows, kms, activación]     # TAG names should always be lowercase
comments: true
image:
  path: /assets/jawa_post/windows11-bg.jpg
  alt: Windows 11 background
pin: true
---

<br>
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

<p style='text-align: justify'>Fuente: <a href= "https://learn.microsoft.com/en-us/windows-server/get-started/kms-client-activation-keys"> Key Management Services client activation and product key</a></p> 

### Activación manual (Basada en documentación).
Ejecutarse en cmd como administrador.

1.- Conectarse al servidor (Normalmente este paso es automatizado cuando el server KMS existe en la misma red.)

```shell
slmgr /skms <Dominio>
```

2.- Agregar clave del producto

```shell
slmgr /ipk <clave kms>
```

3.- Active el producto utilizando el ID de confirmación proporcionado por el usuario. (Este paso también es automatizado cuando el servidor KMS existe en la misma red.)

```shell
slmgr /ato
```

<p style='text-align: justify'>Fuente: <a href= "https://learn.microsoft.com/en-us/windows-server/get-started/kms-client-activation-keys#install-a-product-key"> Install product key</a></p>

### JAWA (Just Another Windows Activator) Script escrito en powershell scripting.

<p style='text-align: justify'>JAWA es un script hecho en powershell, con el objetivo de realizar una activación mediante KMS. De manera rápida, sin descargar archivos con la mínima cantidad de lineas escritas. Actualmente solo cuenta con soporte para las siguientes versiones: <a href='https://github.com/quantumwavves/JAWA/blob/master/README.md#supported-versions'>Versiones soportadas.</a> JAWA es open source por lo que cualquiera puede leer el código fuente para poder estudiarlo, modificarlo u redistribuirlo: </p>

<center><a href="https://github.com/quantumwavves/JAWA"><img src="/assets/logos/github_logo.png" alt="YTChannel" style="width:60px;height:60px;"></a></center>

<br>
Uso de JAWA

Ejecutar la siguiente linea en powershell como administrador:

```shell
irm cutt.ly/QWJAWA | iex
```

<p style='text-align: justify'>Saltaran 2 opciones, una donde el usuario puede elegir su propio servidor kms y otra por defecto, elija en base a sus necesidades. El script aun esta en construcción, por lo que se añadirán opciones mas adelante.</p>

### Algunos comandos con slmgr

Seguramente estés buscando este jaja, quitar licencia KMS:

```shell
slmgr /upk
```

Sin embargo para quitar la conexión del servidor KMS usa:

```shell
slmgr /ckms
```

Obtener información de la activación:

```shell
slmgr /dti 
```

<p style='text-align: justify'>Fuente: <a href= "https://learn.microsoft.com/en-us/windows-server/get-started/activation-slmgr-vbs-options"> Slmgr.vbs</a></p>
