---
title: "安装 Cantara"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 2
---

本页介绍如何在您的本地操作系统上安装 Cantara。

## Windows

在 Windows 上安装非常简单，只需一分钟即可完成。您可以使用 Windows 包管理器 [Winget](https://learn.microsoft.com/zh-cn/windows/package-manager/winget/) 或手动下载并运行安装程序。

### 使用 Winget（Windows 10 和 Windows 11）

如果您运行的是现代版本的 Windows（Windows 10 1709 或更高版本），可以使用 [Winget](https://learn.microsoft.com/zh-cn/windows/package-manager/winget/) 安全地安装 Cantara 并保持更新。只需打开 Windows PowerShell 并运行以下命令：

```Powershell
winget install cantara
```

Winget 将下载安装程序，询问一次确认，然后静默运行安装程序。当新版本发布时，您可以通过 `winget upgrade --all` 或 `winget upgrade cantara` 进行更新。

如果您想从系统中删除 Cantara，可以运行 `winget uninstall cantara`。

### 运行安装程序

如果您不想使用 Winget，也可以手动下载并运行安装程序，它将引导您完成安装过程。

只需[下载并运行安装程序](https://github.com/reckel-jm/cantara/releases/download/v{{% param "cantaraVersion" %}}/cantara-{{% param "cantaraVersion" %}}_setup_win64.exe)，按照提示安装 Cantara。安装完成后，您可以在开始菜单中找到该程序。此外，如果您在安装过程中选择了相应选项，桌面上也会有快捷方式。

{{% notice info %}}
启动安装程序时，Windows 可能会警告您来源未知且可执行文件未签名。在这种情况下，您可以选择"仍然运行"继续。
这是因为我没有可用于认证可执行文件的证书。
但由于该软件已发布到 Winget，您可以从那里安全安装，而不会看到此通知。
{{% /notice %}}

## Linux

Cantara 由一位 Linux 爱好者开发。因此，确保 Cantara 在每个 Linux 发行版上都能正常运行是我的荣幸。

{{% notice info %}}
Cantara 可以使用 Qt6、Qt5 和 GTK2 库作为图形用户界面。根据分发渠道，Cantara 预编译了 Qt6 或 Qt5 绑定。如果您偏好 GTK2，请[自行编译 Cantara](#generic-compilation)。
{{% /notice %}}

### Arch Linux 及基于 Arch 的发行版（Manjaro、Garuda 等）

#### Arch 用户仓库（AUR）

[![cantara](https://img.shields.io/aur/version/cantara?color=1793d1&label=cantara&logo=arch-linux&style=for-the-badge)](https://aur.archlinux.org/packages/cantara/)[![cantara-bin](https://img.shields.io/aur/version/cantara-bin?color=1793d1&label=cantara-bin&logo=arch-linux&style=for-the-badge)](https://aur.archlinux.org/packages/cantara-bin/)

[Arch 用户仓库（AUR）](https://wiki.archlinux.org/title/Arch_User_Repository)包含软件包构建信息，允许您自动构建软件包并将其安装到本地文件系统。这是在官方仓库之外安装软件的首选方式。AUR 中有两个 Cantara 软件包：使用 [cantara-bin](https://aur.archlinux.org/packages/cantara-bin) 安装预编译版本，使用 [cantara](https://aur.archlinux.org/packages/cantara) 让系统自行编译软件包。请注意，安装**第二个选项**时，需要下载并安装 Pascal 和 Lazarus 的编译器和库，可能需要数百兆字节的磁盘空间。编译完成后可以删除这些工具。

从 AUR 安装软件包的方法有很多。大多数人可能会使用 `yay` 等助手工具。只需安装**其中一个软件包**：

```bash
yay cantara-bin # 快速紧凑地安装预编译二进制文件
yay cantara # 下载源代码并自行编译
```

{{% notice note %}}
使用 yay 等助手工具的一大优势是它还会保持软件包更新！每当 Cantara 发布新版本时，您应该能够通过 `sudo yay -Syu` 进行更新。
{{% /notice %}}

安装后，可以通过 pacman 卸载 Cantara：`sudo pacman -R cantara`。

### Ubuntu/Debian 基础的 Linux 发行版

请使用相关章节中描述的 [Snap](#snap) 或 [Flatpak](#flatpakflathub)。

### Snap

Cantara 已在 Snap Store 上架！Snap 包现在只有 4.5 MB，是一种很好的发行版无关安装方式。您可以按照 [Cantara 商店页面](https://snapcraft.io/cantara)上的说明了解如何在您的本地系统上安装，或者——如果 snapd 已在运行——通过命令行安装。

[![从 Snap Store 获取](https://snapcraft.io/static/images/badges/zh/snap-store-black.svg)](https://snapcraft.io/cantara)

```bash
sudo snap install cantara
```

{{% notice info %}}
Snap 应用程序的运行方式与普通软件包不同。因此可能会有一些不同的行为，例如程序外观不同。无论如何，请随时报告任何意外行为，以便我尝试修复。
{{% /notice %}}

Snap 将在开始菜单中创建启动项。如果您想通过命令行运行 Cantara，命令是 `snap run cantara`。

{{% notice tip %}}
您也可以同时安装不同版本的 Cantara，甚至可以将 Cantara 作为经典包和 Snap 同时安装。查看 [Snap 文档](https://snapcraft.io/docs/parallel-installs)了解更多详情。
{{% /notice %}}

### Flatpak/Flathub

Cantara 也已打包为 Flatpak，可以从 [flathub.org](https://flathub.org/apps/details/app.cantara.Cantara) 安装和更新。这需要在您的操作系统上安装 flatpak。一些发行版如 Fedora 已经内置，其他发行版如 Arch Linux 则需要手动安装。

从 Flathub 安装 Flatpak 可以通过图形软件管理工具（如 Gnome Software 或 KDE Discover）或命令行完成：

```bash
flatpak install app.cantara.Cantara
```

根据您已安装的 Flatpak，flatpak 可能会为所需的 KDE/Qt 运行时下载数百兆字节。话虽如此，尽管实际的 Cantara Flatpak 不足 4 MB，通过 Flatpak 安装 Cantara 肯定不是最节省磁盘空间的方式。

### 通用二进制文件运行

{{% notice warning %}}
强烈不建议不使用原生包管理器或容器化格式（Snap/Flatpak）安装 Cantara。仅在本地运行 Cantara 而无需安装时使用此方式。
{{% /notice %}}

作为另一种与发行版无关的使用 Cantara 的方式，您可以手动下载并运行二进制文件。请注意，Cantara 需要 libqt5pas 库，该库通常由您发行版的包管理器的依赖管理来解决。但如果您不使用包管理器安装，则需要手动安装 libqt5pas。之后，从 Github 仓库下载 Zip 文件，解压它，使二进制文件可执行并运行 `cantara`：

```sh
mkdir cantara && cd cantara
wget https://github.com/reckel-jm/cantara/releases/download/v{{% param "cantaraVersion" %}}/cantara-v{{% param "cantaraVersion" %}}-linux-x64.zip
unzip cantara-v{{% param "cantaraVersion" %}}-linux-x64.zip
chmod +x cantara
./cantara
```

### 通用编译 {#generic-compilation}

从您的本地仓库安装 `lazarus` 和 `lazbuild`。如果您偏好 Qt5，如果发行版提供了特定软件包，也可以安装 `lazarus-qt` 代替 lazarus。完成后，编译非常简单：下载源代码，解压它并使用适当选项运行 lazbuild。

```sh
wget https://github.com/reckel-jm/cantara/archive/refs/tags/v{{% param "cantaraVersion" %}}.tar.gz
tar -zxvf v{{% param "cantaraVersion" %}}.tar.gz
cd v{{% param "cantaraVersion" %}}
make
```

如果您偏好 GTK2，请在 makefile 中将选项更改为 `--ws=gtk2`。如果没有错误完成，您将在同一文件夹中找到可执行二进制文件 `cantara`。

## Mac OS

Cantara 可在 Mac OS X 上运行。但是，它尚未经过官方认证，这意味着您目前还不能以正常方式安装它。
请按照以下步骤使用 Cantara：

1. 从 Github 下载 [Cantara Mac OS X 二进制文件](https://github.com/reckel-jm/cantara/releases/download/v{{% param "cantaraVersion" %}}/cantara-v{{% param "cantaraVersion" %}}-macos-x64.zip)。
2. 在 Finder 中打开 zip 压缩包，将内容解压到文件夹中。
3. 打开终端并导航到该文件夹，例如，如果您使用默认下载文件夹，可以使用 `cd Downloads/cantara-{{% param "cantaraVersion" %}}-macos`。
4. 当您在解压的文件夹中时，使用 `chmod +x src/cantara.app/Contents/cantara` 使二进制文件可执行。
5. 使用 `./src/cantara.app/Contents/cantara` 运行二进制文件。Cantara 现在应该启动了。您可以将其固定到 Dock，以便以后轻松打开。
