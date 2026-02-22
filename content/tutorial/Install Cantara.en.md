---
title: "Install Cantara"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 2
---

This page describes how you can install Cantara on your local operating system.

## Windows

Installation on Windows is very easy and done in just one minute. You can either use the Windows package manager [Winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/) or download and run the installer manually.

### Using winget (Windows 10 and Windows 11)

If you are running one of the modern versions of Windows (Windows 10 1709 or later), you can use [Winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/) to install Cantara safely and keep it up to date. Simply open a Windows Powershell and run the following command:

```Powershell
winget install cantara
```

Winget will download the installer, ask you once for confirmation and afterwards runs the installer silently. If a new version gets published, you can update via `winget upgrade --all` or `winget upgrade cantara`.

If you would like to remove Cantara from your system, you can run `winget uninstall cantara`.

### Running the installer

If you don't like to use winget, you can also download and run the installer manually which will lead you through the process of installation.

Simply [download and run the installer](https://github.com/reckel-jm/cantara/releases/download/v2.6.0/cantara-2.6.0_setup_win64.exe), go through the questions and install Cantara. After the installation, you will find the program in your start menu. In addition, if you have chosen the option during the setup process, you will also have a shortcut on your desktop.

{{% notice info %}}
When starting the installer, Windows might warn you that the source is unknown and the executable unsigned. In this case, you can choose "Proceed" to continue.
This is due to the fact that I don't own a certificate which I could use for certification of the executable.
However as the software has been published to Winget, you can safely install it from there and without seeing this notification.
{{% /notice %}}

## Linux

Cantara was developed by a Linux fan and enthusiast. So, it is my pleasure to make sure that Cantara is working well on every Linux distribution.

{{% notice info %}}
Cantara can use the Qt6, QT5 and GTK2 librarys for the graphical user interface. Depending on the distribution channel, Cantara is precompiled with Qt6 or Qt5-bindings. If you prefer GTK2, please [compile cantara by yourself](#generic-compilation).
{{% /notice %}}

### Arch Linux and Arch based distributions (Manjaro, Garuda, etc.)

#### The Arch User Repository (AUR)

[![cantara](https://img.shields.io/aur/version/cantara?color=1793d1&label=cantara&logo=arch-linux&style=for-the-badge)](https://aur.archlinux.org/packages/cantara/)[![cantara-bin](https://img.shields.io/aur/version/cantara-bin?color=1793d1&label=cantara-bin&logo=arch-linux&style=for-the-badge)](https://aur.archlinux.org/packages/cantara-bin/)

The [Arch User Repository (AUR)](https://wiki.archlinux.org/title/Arch_User_Repository) contains package built information which allows you to build software packages automatically and install them on your local file system. This is the prefered way for installation of software outside of the official repositories. There are two Cantara package builds in the AUR: Use [cantara-bin](https://aur.archlinux.org/packages/cantara-bin) for a pre-compiled version of Cantara and [cantara](https://aur.archlinux.org/packages/cantara) if you would like the system to compile the package. Note that for the installation process of the **second option**, the compilers and libraries of Pascal and Lazarus have to get downloaded and installed which might require several hundred megabytes of disk space. You can delete these tools after the compilation process has been completed.

There are many ways how to install a package from the AUR. Most people might use a helper like `yay`. Just install **one of the packages**:

```bash
yay cantara-bin # fast and compact installation of pre-compiled binary
yay cantara # downloads source code and compile by yourself
```

{{% notice note %}}
A big advantage of using a helper like yay is that it will also keep the packages up-to-date! Whenever a new version of Cantara gets released, you should be able to update it via `sudo yay -Syu`
{{% /notice %}}

Once installed, Cantara can be uninstalled via pacman: `sudo pacman -R cantara`.

### Ubuntu/Debian based Linux distributions

Please use [Snap](#snap) or [Flatpak](#flatpakflathub) as described in the concerning sections.

### Snap

Cantara is available at the Snap Store! The snap package now only takes 4.5 MB and is therefore a good distribution-independent way to install Cantara. You can follow the instructions on the [Cantara store page](https://snapcraft.io/cantara) to find out how to install it on your local system or - if snapd is already running - install it via the command line.

[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)](https://snapcraft.io/cantara)

```bash
sudo snap install cantara
```

{{% notice info %}}
The way how a Snap application is running is different from a normal package. Therefore there might be some different behavior e.g. a different look of the program. In any case, feel free to report every unexpected behavior so that I can try to fix it.
{{% /notice %}}

Snap will create a starter in the start menu. If you like to run Cantara via the command line, the command is `snap run cantara`.

{{% notice tip %}}
You can also install different versions of Cantara at the same time and even install Cantara as a classical package and a snap together. Check the [Snap Documentation](https://snapcraft.io/docs/parallel-installs) for further details.
{{% /notice %}}

### Flatpak/Flathub

Cantara has been packaged as a Flatpak as well and can be installed and updated from [flathub.org](https://flathub.org/apps/details/app.cantara.Cantara). This requires an installed flatpak on your operation system. Some distribution like Fedora have this already out of the box, in other distributions like Arch Linux, you need to install it manually.

Installing a flatpak from flathub can be done via a graphical software management tool, for example Gnome Software or KDE Discover, or via the command line:

```bash
flatpak install app.cantara.Cantara
```

Depending on the flats you have already installed, flatpak might download several houndreds of megabytes for the required KDE/Qt-runtimes. That being said, although the actual Cantara flat is less then 4 MB installing Cantara via flatpak is for sure not the most disk space friendly way.

### Generic Run of Binaries

{{% notice warning %}}
Installing Cantara without using your native package manager or a containerized format (Snap/Flatpak) is strongly discouraged and not recommended. Use this only for locally running Cantara without installation.
{{% /notice %}}

As an other distribution-independant way of using Cantara, you can manually download and run the binary. Please be aware that Cantara needs the libqt5pas library which is normally resolved by the package dependancy management of your distribution's package manager. However, if you don't use the package manager for installation, you need to install libqt5pas manually. Afterwards, download the Zip-File from the Github Repository, extract it, make the binary executable and run `cantara`:

```sh
mkdir cantara && cd cantara
wget https://github.com/reckel-jm/cantara/releases/download/v{{% param "cantaraVersion" %}}/cantara-v{{% param "cantaraVersion" %}}-linux-x64.zip
unzip cantara-v{{% param "cantaraVersion" %}}-linux-x64.zip
chmod +x cantara
./cantara
```

### Generic Compilation

Install `lazarus` and `lazbuild` from your local repository. If you prefer QT5, you could also install `lazarus-qt` instead of lazarus if the distribution provides a certain package. After you have done that, the compilation is quite easy: Download the source code, extract it and run lazbuild with the appropriate options.

```sh
wget https://github.com/reckel-jm/cantara/archive/refs/tags/v{{% param "cantaraVersion" %}}.tar.gz
tar -zxvf v{{% param "cantaraVersion" %}}.tar.gz
cd v{{% param "cantaraVersion" %}}
make
```

If you prefer GTK2, change the option to `--ws=gtk2` in the makefile. If done with no errors, you will find the executable binary `cantara` in the same folder.

## Mac OS

Cantara is working on Mac OS X. However, it has not been officially certified which means that you can not install it in a normal way yet.
Please follow these steps to use Cantara:

1. Download the [Cantara Mac OS X binary](https://github.com/reckel-jm/cantara/releases/download/v{{% param "cantaraVersion" %}}/cantara-v{{% param "cantaraVersion" %}}-macos-x64.zip) from Github.
2. Open the zip-Archive in Finder so that it will exttract the content to a folder.
3. Open a terminal and navigate to the Folder, for example with `cd Downloads/cantara-{{% param "cantaraVersion" %}}-macos` if you are using the default Download folder.
4. When you are in the extracted folder, make the binary file executable with `chmod +x src/cantara.app/Contents/cantara`
5. Run the binary with `./src/cantara.app/Contents/cantara`. Cantara should start now. You can attach it to the dock so that you can open it easily again.
