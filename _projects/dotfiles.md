---
layout: post
header-style: text
title: My personal dotfiles for BSPWM.
img: img/projects/dotfiles/rice.webp
---
![Desktop View](/img/projects/dotfiles/cover.webp){: w="800" h="600"}

My personal config for Arch Linux with bswpm.<br>
**Github repo here:**[dotfiles](https://github.com/quantumwavves/quantum-dotfiles)<br><br>
`Beta phase. Yet not completed`{:.warning}

# Table of content

- [Components](#Components)
- [Manual installation](#manual-installation-)
- [Automatic installation](#scripts-for-installation-)
    - [Arch Linux](#arch-linux)
    - [Debian](#debian)
    - [Fedora](#fedora)
- [Additional Features](#additional-features-optional-)
- [Wallpapers](#wallpapers-)
- [Gallery](#rice-gallery-)
- [Usage](#usage-%EF%B8%8F)
    - [Enviroment](#setup-enviroment)
    - [Keybinds](#keybinds-cheat-sheet)
- [Troubleshoting](#troubleshoting-)
- [FAQ](#faq-)
- [To do list](#to-do-list-)
- [Credits](#credits-)

## Components
<!--Componets-->
- **WM:** [bspwm](https://github.com/baskerville/bspwm)
- **OS:** [Arch Linux](https://archlinux.org)
- **Bar:** [Polybar](https://github.com/polybar/polybar)
- **Terminal:** [kitty](https://github.com/kovidgoyal/kitty)
- **Shell:** [zsh](https://wiki.archlinux.org/index.php/Zsh)
- **Compositor:** [picom jonaburg fork](https://github.com/jonaburg/picom)
- **Application Launcher:** [rofi](https://github.com/davatorium/rofi)

<!--Installation-->
## Manual Installation ⚙
#### Manual instrucctions archlinux
```bash
#Arch Linux
#Update system and install dependecies(You need yay)
yay -Syu bspwm sxhkd kitty polybar rofi feh git tmux\
  betterlockscreen xclip imagemagick maim pcmanfm-gtk3\
  ranger python-pywal lsd stalonetray xdo neofetch\
  checkupdates+aur pulseaudio xorg-xrandr curl ttf-jetbrains-mono-nerd\
  dunst awesome-terminal-fonts ttf-font-awesome
#Aditional dependecies (for discord and firefox)
# Instrucctions for Aditional features here: 
yay -S python-pywalfox pywal-discord-git betterdiscordctl
#Compile picom jonaburg fork
git clone https://github.com/jonaburg/picom
cd picom
meson --buildtype=release . build
ninja -C build
# To install the binaries in /usr/local/bin (optional)
sudo ninja -C build install
#Clone repository
git clone https://github.com/quantumwavves/quantum-dotfiles.git
cd quantum-dotfiles
#Copy fonts in $HOME/.fonts
cp -r fonts/* $HOME/.fonts
#Copy config files in $HOME/.config
cp -r .config/* ~/.config
#Copy binarys for setup enviroment
cp bin/* ~/.local/bin
#Install termux package manager
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
#Install zsh and ohmyzsh
yay -S zsh && sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
#Rebuild fonts
fc-cache -v -f
sudo fc-cache -v -f
#Export variables to shell
echo 'export PATH=$PATH:"$HOME/.local/bin"' >>$HOME/.<bashrc or zshrc>
#Setup enviroment
wmcolor $HOME/quantum-dotfiles/wallpaper/defalt.jpg
```
<!--Scripts Installation-->
## Scripts for installation 🪄
#### Arch Linux
```bash
#Arch Linux
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/quantumwavves/quantum-dotfiles/master/tools/dots-install-arch.sh)"
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
## Additional Features (optional) 🎲

Discord wallpaper theme (you need betterdiscord):

![Desktop View](/img/projects/dotfiles/discord-feature.webp){: w="800" h="600"}

Firefox wallpaper theme (you need pywalfox extension):

![Desktop View](/img/projects/dotfiles/firefox-feature.webp){: w="800" h="600"}

Bluetooth menu with rofi theme (you need bluez utils and bluetooth adapter, obviusly): 

<img src="/img/projects/dotfiles/menu-bluetooth.webp"  width="200" height="150">

RGB shotcuts with rofi (you need to openrgb and have compatible devices)

<img src="/img/projects/dotfiles/rgb-menu.webp"  width="250" height="200">

<!--Wallpapers-->
## Wallpapers 🌌
**My wallpaper collection:** [here.](https://github.com/quantumwavves/wallpaper-qw.git)

**Genshin Impact wallpapers**
![Desktop View](/img/projects/dotfiles/genshin-wallpapers.webp){: w="800" h="600"}
**Keyboards wallpapers**
![Desktop View](/img/projects/dotfiles/keyboards-wallpapers.webp){: w="800" h="600"}
**Anime wallpapers**
![Desktop View](/img/projects/dotfiles/anime-wallpapers.webp){: w="800" h="600"}
**Architecture wallpapers**
![Desktop View](/img/projects/dotfiles/arch-wallpapers.webp){: w="800" h="600"}
**Eye candy wallpapers**
![Desktop View](/img/projects/dotfiles/eyecandy-wallpapers.webp){: w="800" h="600"}
**Nature wallpapers**
![Desktop View](/img/projects/dotfiles/nature-wallpapers.webp){: w="800" h="600"}
**Abstract wallpapers**
![Desktop View](/img/projects/dotfiles/abstract.webp){: w="800" h="600"}

# Rice Gallery 📷
`Customize it as you like`{:.success}<br><br>
`Genshin impact thematic`{:.info}
![Desktop View](/img/projects/dotfiles/gallery/kokomi.png){: w="800" h="600"}
![Desktop View](/img/projects/dotfiles/gallery/nilou.png){: w="800" h="600"}
![Desktop View](/img/projects/dotfiles/gallery/hu-tao.png){: w="800" h="600"}
![Desktop View](/img/projects/dotfiles/gallery/yelan.png){: w="800" h="600"}
![Desktop View](/img/projects/dotfiles/gallery/kamisato-ayaka.png){: w="800" h="600"}
`Abstract thematic`{:.info}
![Desktop View](/img/projects/dotfiles/gallery/lake.png){: w="800" h="600"}
![Desktop View](/img/projects/dotfiles/gallery/gas-station.png){: w="800" h="600"}
![Desktop View](/img/projects/dotfiles/gallery/keyboard.png){: w="800" h="600"}
![Desktop View](/img/projects/dotfiles/gallery/fuji-pink.png){: w="800" h="600"}
`Anime thematic`{:.info}
![Desktop View](/img/projects/dotfiles/gallery/ai-hoshino.png){: w="800" h="600"}
![Desktop View](/img/projects/dotfiles/gallery/makima.png){: w="800" h="600"}
![Desktop View](/img/projects/dotfiles/gallery/nanakusa-nazuna.png){: w="800" h="600"}
![Desktop View](/img/projects/dotfiles/gallery/zero-two.png){: w="800" h="600"}

<!--Usage-->
## Usage ⌨️

### Setup enviroment

```bash
#Basic window manager setup, only changes color themes in polybar, terminal & rofi
$ wmcolor /path/of/wallpaper
```
```bash
#Complete window manager setup, bspwm, polybar, terminal, rofi, discord (needed betterdiscord), firefox (onlyworks on this browser)
$ wmcolor+ /path/of/wallpaper 
```
### Keybinds cheat sheet

| map | function |
|-|-|
| alt + d | show rofi launcher |
| leader + alt + p | show power menu |
| impr paint | show screenshot menu |
| leader + alt + b | open bluetooth menu |
| alt + l | open global menu configurator |

## Troubleshoting ❌
`For nvidia users with that error:`{:.error}
```
[ 11.11.2020 20:51:24.270 x_fence_sync ERROR ] Failed to trigger the fence (X error 136 XSyncBadFence request 134 minor 15 serial 2033)
[ 11.11.2020 20:51:24.270 paint_all ERROR ] x_fence_sync failed, xrender-sync-fence will be disabled from now on.
````
solution is replace `picom &` in $HOME/.config/bspwm/bspwmrc for:
```bash
picom --experimental-backends --backend glx --xrender-sync-fence &
```
`For problems with picom for intel users (General)`{:.error}<br>
solution is replace `picom &` in $HOME/.config/bspwm/bspwmrc for:
```bash
picom --experimental-backends &
```
`For problems with rofi for C locale`{:.error}

```
Rofi-WARNING **: 23:23:38.603: Failed to set locale
```
Solution is verify the locales in /etc/locale.conf file and generate locale config

```bash
#You need root
#Export locale into file
echo 'LC_ALL="C"' >> /etc/locale.conf
#generate locale
locale-gen
```
Another solution is export locale variable in your shell
```bash
#For bash
echo 'export LC_ALL="C"' >> $HOME/.bashrc
#For zsh
echo 'export LC_ALL="C"' >> $HOME/.zshrc
```
`How do i extract my backup in .tar.gz format?`{:.warning}

```bash
#You need gzip
tar -xzvf $HOME/.dots-backup/<backupfile>
```
## To Do List 📑
- [ ] Finalizing the component monitoring modules for polybar
- [ ] Make eww widgets
- [ ] Create eww bar configuration
- [ ] Create more modules for polybar
- [ ] Create more scripts for rofi
- [ ] Export colorscheme to GTK2 ad GTK3
- [ ] Export colorscheme to QT
- [ ] Create Debian and Fedora installer scripts
## Credits ☕
- **Bluetooth module rofi:** [nickclyde](https://github.com/nickclyde)
- **Rofi themes:** [adi1090x](https://github.com/adi1090x)
