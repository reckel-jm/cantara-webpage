---
title: "Instalar Cantara"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 2
---

Esta página describe cómo puede instalar Cantara en su sistema operativo local.

## Windows

La instalación en Windows es muy fácil y se completa en solo un minuto. Puede usar el administrador de paquetes de Windows [Winget](https://learn.microsoft.com/es-es/windows/package-manager/winget/) o descargar y ejecutar el instalador manualmente.

### Usando Winget (Windows 10 y Windows 11)

Si está ejecutando una de las versiones modernas de Windows (Windows 10 1709 o posterior), puede usar [Winget](https://learn.microsoft.com/es-es/windows/package-manager/winget/) para instalar Cantara de forma segura y mantenerlo actualizado. Simplemente abra un Windows PowerShell y ejecute el siguiente comando:

```Powershell
winget install cantara
```

Winget descargará el instalador, le pedirá confirmación una vez y luego ejecutará el instalador silenciosamente. Cuando se publique una nueva versión, puede actualizar con `winget upgrade --all` o `winget upgrade cantara`.

Si desea eliminar Cantara de su sistema, puede ejecutar `winget uninstall cantara`.

### Ejecutar el instalador

Si no desea usar Winget, también puede descargar y ejecutar el instalador manualmente, que le guiará a través del proceso de instalación.

Simplemente [descargue y ejecute el instalador](https://github.com/reckel-jm/cantara/releases/download/v{{% param "cantaraVersion" %}}/cantara-{{% param "cantaraVersion" %}}_setup_win64.exe), responda las preguntas e instale Cantara. Después de la instalación, encontrará el programa en su menú de inicio. Además, si eligió la opción durante el proceso de instalación, también tendrá un acceso directo en su escritorio.

{{% notice info %}}
Al iniciar el instalador, Windows podría advertirle que la fuente es desconocida y el ejecutable no está firmado. En este caso, puede elegir "Ejecutar de todas formas" para continuar.
Esto se debe a que no tengo un certificado que pueda usar para certificar el ejecutable.
Sin embargo, como el software se ha publicado en Winget, puede instalarlo desde allí de forma segura y sin ver esta notificación.
{{% /notice %}}

## Linux

Cantara fue desarrollado por un fanático y entusiasta de Linux. Por lo tanto, es un placer para mí asegurarme de que Cantara funcione bien en cada distribución de Linux.

{{% notice info %}}
Cantara puede usar las bibliotecas Qt6, Qt5 y GTK2 para la interfaz gráfica de usuario. Dependiendo del canal de distribución, Cantara está precompilado con enlaces Qt6 o Qt5. Si prefiere GTK2, por favor [compile Cantara usted mismo](#generic-compilation).
{{% /notice %}}

### Arch Linux y distribuciones basadas en Arch (Manjaro, Garuda, etc.)

#### El Arch User Repository (AUR)

[![cantara](https://img.shields.io/aur/version/cantara?color=1793d1&label=cantara&logo=arch-linux&style=for-the-badge)](https://aur.archlinux.org/packages/cantara/)[![cantara-bin](https://img.shields.io/aur/version/cantara-bin?color=1793d1&label=cantara-bin&logo=arch-linux&style=for-the-badge)](https://aur.archlinux.org/packages/cantara-bin/)

El [Arch User Repository (AUR)](https://wiki.archlinux.org/title/Arch_User_Repository) contiene información de construcción de paquetes que le permite construir paquetes de software automáticamente e instalarlos en su sistema de archivos local. Esta es la forma preferida de instalación de software fuera de los repositorios oficiales. Hay dos paquetes de Cantara en el AUR: use [cantara-bin](https://aur.archlinux.org/packages/cantara-bin) para una versión precompilada de Cantara y [cantara](https://aur.archlinux.org/packages/cantara) si desea que el sistema compile el paquete. Tenga en cuenta que para el proceso de instalación de la **segunda opción**, los compiladores y bibliotecas de Pascal y Lazarus deben descargarse e instalarse, lo que podría requerir varios cientos de megabytes de espacio en disco. Puede eliminar estas herramientas después de que el proceso de compilación se haya completado.

Hay muchas formas de instalar un paquete desde el AUR. La mayoría de la gente podría usar un ayudante como `yay`. Simplemente instale **uno de los paquetes**:

```bash
yay cantara-bin # instalación rápida y compacta del binario precompilado
yay cantara # descarga el código fuente y compila usted mismo
```

{{% notice note %}}
Una gran ventaja de usar un ayudante como yay es que también mantendrá los paquetes actualizados. ¡Cada vez que se publique una nueva versión de Cantara, debería poder actualizarlo con `sudo yay -Syu`!
{{% /notice %}}

Una vez instalado, Cantara puede desinstalarse a través de pacman: `sudo pacman -R cantara`.

### Distribuciones Linux basadas en Ubuntu/Debian

Por favor use [Snap](#snap) o [Flatpak](#flatpakflathub) como se describe en las secciones correspondientes.

### Snap

¡Cantara está disponible en Snap Store! El paquete snap ahora tiene solo 4.5 MB y es, por tanto, una buena forma independiente de la distribución para instalar Cantara. Puede seguir las instrucciones en la [página de la tienda de Cantara](https://snapcraft.io/cantara) para saber cómo instalarlo en su sistema local o — si snapd ya está en ejecución — instalarlo mediante la línea de comandos.

[![Consíguelo en Snap Store](https://snapcraft.io/static/images/badges/es/snap-store-black.svg)](https://snapcraft.io/cantara)

```bash
sudo snap install cantara
```

{{% notice info %}}
La forma en que se ejecuta una aplicación Snap es diferente de un paquete normal. Por lo tanto, puede haber algún comportamiento diferente, por ejemplo, un aspecto diferente del programa. En cualquier caso, no dude en informar cualquier comportamiento inesperado para que pueda intentar solucionarlo.
{{% /notice %}}

Snap creará un iniciador en el menú de inicio. Si desea ejecutar Cantara a través de la línea de comandos, el comando es `snap run cantara`.

{{% notice tip %}}
También puede instalar diferentes versiones de Cantara al mismo tiempo e incluso instalar Cantara como paquete clásico y como snap juntos. Consulte la [documentación de Snap](https://snapcraft.io/docs/parallel-installs) para más detalles.
{{% /notice %}}

### Flatpak/Flathub

Cantara también ha sido empaquetado como Flatpak y puede instalarse y actualizarse desde [flathub.org](https://flathub.org/apps/details/app.cantara.Cantara). Esto requiere tener flatpak instalado en su sistema operativo. Algunas distribuciones como Fedora ya lo tienen de serie, en otras distribuciones como Arch Linux, debe instalarlo manualmente.

La instalación de un Flatpak desde Flathub se puede hacer a través de una herramienta de gestión de software gráfica, por ejemplo Gnome Software o KDE Discover, o mediante la línea de comandos:

```bash
flatpak install app.cantara.Cantara
```

Dependiendo de los flatpaks que ya tenga instalados, flatpak podría descargar varios cientos de megabytes para los tiempos de ejecución KDE/Qt requeridos. Dicho esto, aunque el flatpak de Cantara en sí tiene menos de 4 MB, instalar Cantara a través de flatpak ciertamente no es la forma más eficiente en espacio en disco.

### Ejecución genérica de binarios

{{% notice warning %}}
Se desaconseja encarecidamente instalar Cantara sin usar el administrador de paquetes nativo o un formato contenedorizado (Snap/Flatpak) y no se recomienda. Use esto solo para ejecutar Cantara localmente sin instalación.
{{% /notice %}}

Como otra forma independiente de la distribución de usar Cantara, puede descargar y ejecutar el binario manualmente. Tenga en cuenta que Cantara necesita la biblioteca libqt5pas que normalmente se resuelve por la gestión de dependencias del administrador de paquetes de su distribución. Sin embargo, si no usa el administrador de paquetes para la instalación, necesita instalar libqt5pas manualmente. Después, descargue el archivo Zip del repositorio de Github, extráigalo, haga el binario ejecutable y ejecute `cantara`:

```sh
mkdir cantara && cd cantara
wget https://github.com/reckel-jm/cantara/releases/download/v{{% param "cantaraVersion" %}}/cantara-v{{% param "cantaraVersion" %}}-linux-x64.zip
unzip cantara-v{{% param "cantaraVersion" %}}-linux-x64.zip
chmod +x cantara
./cantara
```

### Compilación genérica {#generic-compilation}

Instale `lazarus` y `lazbuild` desde su repositorio local. Si prefiere Qt5, también podría instalar `lazarus-qt` en lugar de lazarus si la distribución proporciona un paquete determinado. Después de hacer eso, la compilación es bastante sencilla: Descargue el código fuente, extráigalo y ejecute lazbuild con las opciones apropiadas.

```sh
wget https://github.com/reckel-jm/cantara/archive/refs/tags/v{{% param "cantaraVersion" %}}.tar.gz
tar -zxvf v{{% param "cantaraVersion" %}}.tar.gz
cd v{{% param "cantaraVersion" %}}
make
```

Si prefiere GTK2, cambie la opción a `--ws=gtk2` en el makefile. Si termina sin errores, encontrará el binario ejecutable `cantara` en la misma carpeta.

## Mac OS

Cantara funciona en Mac OS X. Sin embargo, no ha sido certificado oficialmente, lo que significa que aún no puede instalarlo de manera normal.
Siga estos pasos para usar Cantara:

1. Descargue el [binario de Cantara para Mac OS X](https://github.com/reckel-jm/cantara/releases/download/v{{% param "cantaraVersion" %}}/cantara-v{{% param "cantaraVersion" %}}-macos-x64.zip) desde Github.
2. Abra el archivo zip en Finder para que extraiga el contenido a una carpeta.
3. Abra una terminal y navegue a la carpeta, por ejemplo con `cd Downloads/cantara-{{% param "cantaraVersion" %}}-macos` si está usando la carpeta de descargas predeterminada.
4. Cuando esté en la carpeta extraída, haga el archivo binario ejecutable con `chmod +x src/cantara.app/Contents/cantara`.
5. Ejecute el binario con `./src/cantara.app/Contents/cantara`. Cantara debería iniciarse ahora. Puede anclarlo al dock para que pueda abrirlo fácilmente de nuevo.
