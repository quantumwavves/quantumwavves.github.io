---
layout: post
header-style: text
title: My personal dotfiles for BSPWM.
img: img/projects/dotfiles/rice.png
---
![Desktop View](/img/projects/dotfiles/cover.png){: w="800" h="600"}

My personal config for Arch Linux with bswpm. 
`Beta phase. Yet not completed`{:.warning}

<!--Componets-->
- **WM:** [bspwm](https://github.com/baskerville/bspwm)
- **OS:** [Arch Linux](https://archlinux.org)
- **Bar:** [Polybar](https://github.com/polybar/polybar)
- **Terminal:** [kitty](https://github.com/kovidgoyal/kitty)
- **Shell:** [zsh](https://wiki.archlinux.org/index.php/Zsh)
- **Compositor:** [picom](https://github.com/ibhagwan/picom)
- **Application Launcher:** [rofi](https://github.com/davatorium/rofi)

<!--Installation-->
## Manual Installation ⚙.
#### Arch Linux
```bash
#Arch Linux
$ yay -Syu bspwm sxhkd kitty polybar rofi picom-ibhagwan-git feh betterlockscreen xclip imagemagick maim pcmanfm-gtk3 ranger python-pywal lsd ueberzug stalonetray xdo pcmanfm-gtk3 tmux neovim
#Aditional dependecies
$ yay -S python-pywalfox pywal-discord-git 
$ git clone https://github.com/quantumwavves/quantum-dotfiles.git
$ cd quantum-dotfiles
$ cp -r fonts/* /usr/share/fonts/<your directory>
$ cp -r .config ~/.config
$ cp bin/* ~/.local/bin
$ fc-cache -v -f (root & nonroot)
```
<!--Scripts Installation-->
## Scripts for installation:
#### Arch Linux
```bash
#Arch Linux
$ Coming soon...
```
#### Debian
```bash
#Debian
$ Coming soon...
```
#### Fedora
```bash
#Fedora
$ Coming soon...
```
<!--Wallpapers-->
### Wallpapers 🌌.
**My wallpaper collection:** [here.](https://github.com/quantumwavves/wallpaper-qw.git)

<!--Screenshots-->
## Gallery 📷.
**Coming soon...**
<!--Usage-->
## Usage
```bash
$ wallcolor /path/of/wallpaper
``` 