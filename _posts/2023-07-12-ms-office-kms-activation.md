---
title: DESPLIEGUE DE MICROSOFT OFFICE.
description: Guía para el despliegue de Microsoft office.
author: Quantum 
date: 2023-07-12
categories: [Deploys]
tags: [deploy,microsoft office,microsoft]
image:
  path: /assets/img/posts/guias/office_post/header.webp
  alt: Paquetería Microsoft Office.
---

### Introduccion:
Saludos a todos. En este post les enseñaré como un desplegar una instalación de Microsoft Office. La activación con Key Managment Server (KMS) de Microsoft Office (Hay que aclarar que esto solo será válido siempre y cuando la versión sea anterior a Office 365)

### Despliegue de Office

#### ¿Que es office deployment tool?

- Link de descarga oficial: [office develoment tool.](https://www.microsoft.com/en-us/download/details.aspx?id=49117)


La Herramienta de implementación de Office (ODT) es una herramienta de línea de comandos que puede usar para descargar e implementar Aplicaciones Microsoft 365 o Microsoft Office 2021,2019. La ODT le ofrece más control que una instalación de Office: se pueden definir los productos e idiomas que se instalarán, cómo se actualizarán esos productos y si se quiere o no mostrar la experiencia de instalación a los usuarios. La ODT consiste en dos archivos: setup.exe y configuration.xml (la cual se puede personalizar al gusto de cada quien). Para trabajar con la herramienta, es necesario crear el archivo de configuración para definir las opciones que quiera usar, tales como productos, idiomas y actualizaciones.

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
### Deploy con KITA. 

KITA (Kita Interface Tool Activator). Es un script escrito en PowerShell que busca automatizar la instalación de Microsoft Office, activación y desactivación KMS de una manera sencilla. KITA solo tiene estas versiones soportadas: [véase aquí](https://github.com/quantumwavves/KITA#supported-versions).

![Desktop View](/assets/img/posts/guias/office_post/kita.gif)

¿Como funciona KITA?

KITA es solo un script que realiza el despliegue de Microsoft Office. Esto quiere decir que se hace uso de herramientas de microsoft y la descarga de la suite es directamente de los servidores de microsoft. KITA es open source, por lo que se puede leer, estudiar y redistribuir. Esta licenciado bajo GPL v3. Véase aquí: [KITA](https://github.com/quantumwavves/KITA).


#### Uso de KITA

Ejectuar en PowerShell como administrador:
```shell 
irm cutt.ly/ikuyo | iex
```
El menú de KITA contiene cuatro opciones, entre las cuales se encuentran la instalación de la suite office (Sin activación), activación de la suite mediante KMS, desactivación de la suite.

![Desktop View](/assets/img/posts/guias/office_post/kita-menu.png)

Para nuestra primera opción podemos seleccionar la versión a instalar:

![Desktop View](/assets/img/posts/guias/office_post/kita-op-1.png)

De igual manera podemos seleccionar el bloat (peso) de las aplicaciones que queramos:

![Desktop View](/assets/img/posts/guias/office_post/kita-op-1-bloat.png)

Finalización. Para este punto nos indicara que la instalación termino cuando el `Deploy Status:` se encuentre en `completed`.

![Desktop View](/assets/img/posts/guias/office_post/kita-act-ask.png)

Fuente y mas demas parametros para la herramienta: [Overview develoment tool](https://learn.microsoft.com/es-mx/deployoffice/overview-office-deployment-tool).
