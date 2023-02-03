---
title: "Install Cantara"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 2
---

Installing Cantara is quite simple if you are using Windows or Linux. It should also be no problem with Mac OS. Here you will find a detailed description for your operating system.

## Windows

The installation using windows is very easy. There is an installer which you can use and which will lead you through the process. After downloading, the installation should take **less than one minute**.

Simply [download and run the installer](https://github.com/reckel-jm/cantara/releases/download/v2.4.1/cantara-2.4.1_setup_win64.exe), go through the questions and install Cantara. After the installation, you will find the program in your start menu. In addition, if you have chosen the option during the setup process, you will also have a shortcut on your desktop.

## Linux

Cantara was developed by a Linux fan and enthusiast. So, it is my pleasure to make sure that Cantara is working well on every Linux distribution.

{{% notice info %}}
Cantara can use the QT5 and GTK2 librarys for the graphical user interface. Due to compatibility issues, I have switched to QT5 for the binary packages which means that **if you are using a binary package of cantara, you will get a QT5 application**. If you prefer GTK2, please [compile cantara by yourself](#generic-compilation).
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

#### Pre-Built Pacman Installation Package

If you don't like to use the AUR, you can also use the pre-built Pacman package from the Github repository. For downloading and installing the package, simply enter the following commands in the command line:

```bash
wget https://github.com/reckel-jm/cantara/releases/download/v2.4.1/cantara-2.4.1-1-x86_64.pkg.tar.zst
sudo pacman -U cantara-2.4.1-1-x86_64.pkg.tar.zst
```

Cantara is now installed and ready for use. If you later would like to uninstall it, you can use Pacman as well:

    sudo pacman -R cantara

### Ubuntu/Debian based Linux distributions

There is a DEB-Package for 2.3 Beta which works well with Ubuntu. You can [download it here](https://github.com/reckel-jm/cantara/releases/download/v2.2.3beta/cantara-2.2.3beta.deb) and then open it with "Software Installation" or use `dpkg` in the command line:

    wget https://github.com/reckel-jm/cantara/releases/download/v2.3/cantara-2.3.deb
    sudo dpkg -i cantara-2.3.deb

If you would like to remove Cantara at a later point, you can use `sudo apt-get remove cantara`. In addition to that, you can get Cantara as a [Snap](#snap) via the Ubuntu Software Store.

{{% notice warning %}}
This is not the latest version at the moment. Please wait till the latest versios been deployed as a Debian package or use snap in the meantime.
{{% /notice %}}

### Snap

Cantara is available at the Snap Store! The snap package now only takes 4.5 MB and is therefore a good distribution-independent way to install Cantara. You can follow the instructions on the [Cantara store page](https://snapcraft.io/cantara) to find out how to install it on your local system or - if snapd is already running - install it via the command line.

[![Get it from the Snap Store](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)](https://snapcraft.io/cantara)

    sudo snap install cantara

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

	flatpak install app.cantara.Cantara

Depending on the flats you have already installed, flatpak might download several houndreds of megabytes for the required KDE/Qt-runtimes. That being said, although the actual Cantara flat is less then 4 MB installing Cantara via flatpak is for sure not the most disk space friendly way.

### Generic Installation of Binaries

As an other distribution-independant way of using Cantara, you can manually download and install the binaries. Please be aware that Cantara needs the libqt5pas library which is normally resolved by the package dependancy management of your distribution's package manager. However, if you don't use the package manager for installation, you need to install libqt5pas manually. Afterwards, download the Zip-File from the Github Repository, extract it and run `make install`:

    wget https://github.com/reckel-jm/cantara/releases/download/v2.4.0/cantara-2.4.0-linux-x86_64_bin.zip
    tar -zxvf cantara-2.4.0-linux-x86_64_bin.zip
    sh install.sh

This will install Cantara globally on your system. You could also run Cantara directly from the dictionary without installing it. If you later want to uninstall a global installed Cantara, run the following commands:

    sudo rm /usr/bin/cantara
    sudo rm /usr/share/icons/cantara.png
    sudo xdg-desktop-menu uninstall reckel-cantara.desktop
    sudo rm /usr/share/locale/en/cantara.mo

### Generic Compilation

Install `lazarus` and `lazbuild` from your local repository. If you prefer QT5, you could also install `lazarus-qt` instead of lazarus if the distribution provides a certain package. After you have done that, the compilation is quite easy: Download the source code, extract it and run lazbuild with the appropriate options.

    wget https://github.com/reckel-jm/cantara/archive/refs/tags/v2.4.0.tar.gz
    tar -zxvf v2.4.0.tar.gz
    cd v2.3
    make

If you prefer GTK2, change the option to `--ws=gtk2` in the makefile. If done with no errors, you will find the executable binary `cantara` in the same folder.

## Mac OS

Thanks to Github's [setup-lazarus action](https://github.com/gcarreno/setup-lazarus), there are now also binarys for Mac OS X created by the Github Matrix virtual host. However I personally have **no experience with Mac OS X** because I don't use it by myself. Nethertheless: Due to Lazarus' plattform-independency, it should be no problem to run it. You can try the following steps:

1. [Download the MacOS X binary archive from the last artifact(Zip-File)](https://github.com/reckel-jm/cantara/suites/10219630045/artifacts/500741790).
2. Extract the zip file and run the .app-bundle.

If you went through the steps, please tell me how it worked out! If these steps fail, you can also install the Lazarus IDE, open the project source code and compile Cantara by yourself.
