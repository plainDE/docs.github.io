---
layout: default
title: Installation
nav_order: 3
---


# Installation

## Arch-based distro

To install plainDE on Arch Linux you can install `plainde-meta` AUR package or add [plainDE repository](https://repo.plainde.org).

## From source

Firstly, install the following dependencies:

| Distro | List of dependencies |
|---|---|
| Arch Linux | `git qt6-base xorg noto-fonts-emoji polkit ttf-opensans make alsa-utils kwindowsystem python3 xcompmgr`|
| Debian 11+ / Ubuntu 22.04+ | `git g++ qt6-base-dev xorg fonts-noto-color-emoji make alsa-utils libkf5windowsystem-dev python3 xcompmgr libxkbcommon-x11-dev` |
| Fedora 36 | `git qt6-qtbase-devel xorg-x11-server-Xorg google-noto-emoji-fonts make alsa-utils kf5-kwindowsystem-devel xcompmgr` |

**Caution**. Fedora is not tested yet.

After installing dependencies run

~~~sh
sh -c "$(curl -fsSL plainde.org/install)"
~~~

or run this as root

~~~sh
sh -c "$(curl -fsSL plainde.org/installAsRoot)"
~~~

This script will install all plainDE components (plainPanel, plainControlCenter, plainAbout)
