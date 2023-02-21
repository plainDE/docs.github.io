---
layout: default
title: Installation
nav_order: 3
---


# Installation

## GNU/Linux repository

Learn more about our repository at [repo.plainde.org](https://repo.plainde.org)

## Arch-based distro

To install plainDE on Arch Linux you can install `plainde-meta` AUR package or add [plainDE repository](https://repo.plainde.org).

## From source

First of all, install the following dependencies:

| Distro | List of dependencies |
|---|---|
| Arch Linux | `git qt5-base xorg noto-fonts-emoji polkit ttf-opensans make alsa-utils kwindowsystem python3 picom upower`|
| Debian 11+ / Ubuntu 22.04+ | `git g++ qtbase5-dev xorg fonts-noto-color-emoji make alsa-utils libkf5windowsystem-dev python3 picom libxkbcommon-x11-dev policykit-1 curl upower` |
| Fedora 36 | `git qt5-qtbase-devel xorg-x11-server-Xorg google-noto-emoji-fonts make alsa-utils kf5-kwindowsystem-devel picom upower` |

**Caution**. Fedora is not tested yet.

After installing dependencies run

~~~sh
sh -c "$(curl -fsSL plainde.org/install)"
~~~

or run this as root

~~~sh
sh -c "$(curl -fsSL plainde.org/installAsRoot)"
~~~

This script will install all plainDE components (plainBase, plainPanel, plainControlCenter, plainAbout, plainArtwork)
