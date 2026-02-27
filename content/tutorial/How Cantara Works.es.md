---
title: "Cómo funciona Cantara"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 1
---

## Historia de fondo

Cuando estaba en el instituto, me uní al liderazgo de un grupo juvenil cristiano. Al realizar nuestros eventos, nos gustaba cantar algunas canciones al principio. Sin embargo, surgió el problema de que los libros de canciones disponibles no eran suficientes y el contenido a veces no coincidía con las canciones que se deseaban. En ese momento estaba buscando un programa de presentación de canciones disponible y me decepcioné rápidamente. La mayoría de los programas existentes eran comerciales, muy complicados o simplemente un "exceso" para el propósito básicamente bastante simple: las personas deberían poder elegir canciones (espontáneamente), el programa debería mostrarlas.

En ese momento decidí comenzar el desarrollo de Cantara. El nombre proviene del latín "cantare" (cantar) pero es más artificial que real. Otra razón para elegir el nombre fue que al mismo tiempo me estaba convirtiendo en organista en la iglesia — y el nombre alemán para esa posición es "Kantor", que suena bastante similar.

Más tarde pude dirigir el [mejor grupo de estudiantes del mundo](https://www.smd-chemnitz.de) 😃 y mientras lo hacía, el programa fue creciendo lentamente y se actualizó con nuevas funciones como el soporte multi-pantalla y la posibilidad de exportar textos de canciones directamente al portapapeles para que pueda usarse en grupos pequeños sin posibilidad de proyección. ¡El desarrollo de Cantara continuará y espero que sea una pequeña herramienta para alabar y adorar a nuestro gran Padre celestial!

## El enfoque

{{<mermaid align="left">}}
graph LR;
    A[Archivo de entrada] -->|Recopilando canciones| B(Lista de canciones)
    B --> C(Selección de canciones)
    C --> D{Generar datos de presentación}
    D --> E[Ejecutar presentación directamente]
    D --> F[Exportar letras en formato Markup]
    D --> G[Exportar presentación como PPTX]
    D --> H[Exportar presentación como imágenes]
{{< /mermaid >}}

Cantara toma las canciones de *una carpeta particular* en el sistema de archivos que se llama el *repositorio de canciones* (o brevemente song repo). Cada canción es un simple archivo de texto que se puede editar con un editor de texto de su elección. Cantara reconocerá el título de la canción por el nombre del archivo (sin la extensión). Por ejemplo, si tiene un archivo como:

    Amazing Grace.song

Cantara lo reconocerá como "Amazing Grace" escrito en el formato de canción (para formatos vea la siguiente sección).

{{% notice tip %}}
El directorio del repositorio de canciones puede compartirse y sincronizarse fácilmente a través de servicios en la nube como NextCloud o Git. De esa manera puede distribuir canciones dentro de su grupo u organización.
{{% /notice %}}

{{% notice tip %}}
Desde la versión 2.4.0, Cantara ofrece un editor integrado que puede usar para editar las canciones y convertir canciones CCLI al formato de canción de Cantara. Tenga en cuenta que las canciones siguen siendo archivos de texto individuales y, por lo tanto, aún pueden editarse con cualquier editor de texto.
{{% /notice %}}

{{% notice warning %}}
Los desarrolladores de Cantara no son responsables de los problemas de derechos de autor que surjan con el uso público y la distribución de letras de canciones. ¡Asegúrese de obtener los derechos para usar las letras de canciones! En Alemania, las reuniones religiosas con entrada gratuita gozan de mayor libertad de derechos de autor que los eventos comerciales. Sin embargo, asegúrese con su organización de que no surjan problemas legales.
{{% /notice %}}

## Las ventanas/modos de Cantara

Cantara consta de diferentes ventanas que le permiten usar el programa.

{{< tabs groupid="main" style="primary" title="Ventanas" icon="window-maximize" >}}
{{< tab title="Ventana de selección de canciones" >}}
  Esta ventana se mostrará después de iniciar Cantara. Le permite ver las canciones disponibles y seleccionar las que desea usar en la presentación o exportar.

  <img src="/images/cantara-songselection-selected-hints-de.png" loading="lazy" alt="Ventana de selección de canciones de Cantara" class="bg-white border lazy noshadow">
{{< /tab >}}

{{< tab title="Ventana de presentación" style="default" >}}
  La ventana de presentación mostrará y controlará la presentación cargada (en modo de pantalla única). Se puede poner en pantalla completa y moverla a otra pantalla.
  Si cierra la ventana de presentación, la presentación terminará y volverá a la ventana de selección de canciones.

  <img src="/images/cantara-presentation-de.png" loading="lazy" alt="Ventana de presentación de canciones de Cantara" class="bg-white border lazy noshadow">

{{< /tab >}}

{{< tab title="Controlador de presentación" style="default" >}}
  En el modo de múltiples pantallas, el controlador de presentación le permite controlar en detalle la presentación que se muestra en la ventana de presentación. Puede ver todas las diapositivas, saltar directamente a una diapositiva o salir de la presentación.

  Normalmente, colocaría el controlador de presentación en la primera pantalla (la pantalla predeterminada) y la ventana de presentación en la segunda pantalla (que se muestra en el proyector, monitor externo, etc.).

  <img src="/images/cantara-presentationcontroller-en.png" loading="lazy" alt="Ventana del controlador de presentación de Cantara" class="bg-white border lazy noshadow">

  {{% notice tip %}}
  El controlador de presentación usa la ventana de selección de canciones.
  {{% /notice %}}

{{< /tab >}}

{{< tab title="Ajustes" style="default" >}}
La ventana de ajustes le permite ajustar el estilo de presentación y cambiar la ruta del repositorio de canciones. Puede abrir los ajustes en la ventana de selección de canciones.

  <img src="/images/cantara-settings-en.png" loading="lazy" alt="Los ajustes en Cantara" class="bg-white border lazy noshadow">
{{< /tab >}}

{{< tab title="Editor" style="default" >}}
El editor permite agregar, modificar, convertir y eliminar canciones en su repositorio de canciones. Puede abrir el editor a través de Editar -> Letras de canciones... en la ventana de selección de canciones.

<img src="/images/cantara-editor-en.png" loading="lazy" alt="El editor en Cantara" class="bg-white border lazy noshadow">
{{< /tab >}}

{{< /tabs >}}
