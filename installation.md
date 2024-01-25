---
layout: default
title: Installation
nav_order: 3
---


# Installation

1. Install the following dependencies:

| Distro | List of dependencies |
|---|---|
| Arch Linux | `git qt5-base xorg noto-fonts-emoji polkit ttf-opensans make alsa-utils kwindowsystem5 python3 xcompmgr upower`|
| Debian 11+ / Ubuntu 22.04+ | `git g++ qtbase5-dev xorg fonts-noto-color-emoji make alsa-utils libkf5windowsystem-dev python3 xcompmgr libxkbcommon-x11-dev policykit-1 curl upower` |
| Fedora 36 | `git qt5-qtbase-devel xorg-x11-server-Xorg google-noto-emoji-fonts make alsa-utils kf5-kwindowsystem-devel xcompmgr upower` |

2. Run plainInstaller

(as user)
~~~sh
sh -c "$(curl -fsSL plainde.github.io/install)"
~~~

OR

(as root)
~~~sh
sh -c "$(curl -fsSL plainde.github.io/installAsRoot)"
~~~

This script will install all plainDE components (plainBase, plainPanel, plainControlCenter, plainAbout, plainArtwork)

3. Add plainPanel to window manager's autostart
Guide for Openbox:
  1. Create file ~/.config/openbox/autostart
  2. Append to the end `plainPanel &`

Note. Mint-Y or Mint-L is a recommended icon pack (We use a few Mint-Y only icons).
