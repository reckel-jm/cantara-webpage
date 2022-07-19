---
title: "Install Cantara"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 2
---

Installing Cantara is quite simple if you are using Windows or Linux. Here you will find a detailed description for your operating system.

## Windows

The installation using windows is very easy. There is an installer which you can use and which will lead you through the process. After downloading, the installation should take **less than one minute**.

Simple [download and run the installer](https://github.com/reckel-jm/cantara/releases/download/v2.2.1/cantara2.2.1_setup_win64.exe), go through the questions and install Cantara. After the installation, you will find the program in your start menu. In addition, if you have chosen the option during the setup process, you will also have a shortcut on your desktop.

## Linux

Cantara was developed by a Linux fan and enthuisiast. So, it is my pleasure to make sure that Cantara is working well on every Linux distribution.

{{% notice info %}}
Cantara can use the QT5 and GTK2 librarys for the graphical user interface. Due to compatibility issues, I have switched to QT5 for the binary packages which means that **if you are using a binary package of cantara, you will get a QT5 application**. If you prefer GTK2, please [compile cantara by yourself](#generic-compilation).
{{% /notice %}}

### Arch Linux/Manjaro/etc.

#### Pre-Compiled

For all Pacman-based distros, there exists a Pacman package at the Github Repository which contains the compiled binary for 64-Bit-Systems. For installing the package, simply enter the following command in the command line:

    wget https://github.com/reckel-jm/cantara/releases/download/v2.2.1/cantara-2.2-1-x86_64.pkg.tar.zst
    sudo pacman -U cantara-2.2-1-x86_64.pkg.tar.zst

Cantara is now installed and ready for use. If you lader want to uninstall it, you can use Pacman as well:

    sudo pacman -R cantara

#### The Arch User Repository (AUR)

If you don't want to use the precompiled package, you can also generate it by yourself while using the PKGBUILD-File in the [Arch User Repository](https://aur.archlinux.org/packages/cantara). Note that for the installation process, the compilers and librarys of Pascal and Lazarus get installed. This can take up to 1 GB of disk space. You can delete these tools after the compilation process has been done. There are many ways how to install a package from the AUR. Most people might use a helper like yay:

    yay cantara

{{% notice warning %}}
Although I am the owner of the AUR package, it is **always** adviced to douplecheck the PKGBUILD-file before making the package.
{{% /notice %}}

### Ubuntu/Flat-Based Distributions

I am going to release a flatpack package soon. Untill that, you can follow the [generic instructions](#generic-installation-of-binarys) below.

### Generic Installation of Binarys

Download the Zip-File from the Github Repository, extract it and run `install.sh`:

    wget https://github.com/reckel-jm/cantara/releases/download/v2.2.1/cantara-2-2-1-linux-x86_64.tar.gz
    tar -zxvf cantara-2-2-1-linux-x86_64.tar.gz
    cd cantara-2-2-1-linux-x86_64
    chmod +x install.sh
    sudo ./install.sh

This will install Cantara globally on your system. You could also run Cantara directly from the dictionary. If you later want to uninstall a global installed Cantara, run the following commands:

    sudo rm /usr/bin/cantara
    sudo rm /usr/share/icons/cantara.png
    sudo xdg-desktop-menu uninstall reckel-cantara.desktop
    sudo rm /usr/share/locale/en/cantara.mo

### Generic Compilation

Install `lazarus` and `lazbuild` from your local repository. If you prefer QT5, you could also install `lazarus-qt` instead of lazarus if the distribution provides a certain package. After you have done that, the compilation is quite easy: Download the source code, extract it and run lazbuild with the appropriate options.

    wget https://github.com/reckel-jm/cantara/archive/refs/tags/v2.2.1.tar.gz
    tar -zxvf v2.2.1.tar.gz
    cd v2.2.1
    lazbuild -B Cantara.lpi --ws=qt5

If you prefer GTK2, change the option to `--ws=gtk2`. If done with no errors, you will find the executable binary `cantara` in the same folder.

### Mac OS X

Here, we unfortunately have a problem: There exists **no experience with Mac OS X** because the author of Cantara is simply not using it. However, due to the plattform-independancy of Cantara, it should be no problem to get Cantara to run. Install Lazarus first, download the source files and in best case, everything should work out of the box! Feel free to tell me more if you have gathered some experience.