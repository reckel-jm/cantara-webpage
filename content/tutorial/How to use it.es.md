---
title: "Uso general"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 3
---

## Primeros pasos

Después de la instalación, simplemente abra Cantara con su menú de inicio o el comando `cantara`. Verá el **asistente de bienvenida** que le ayuda a configurar Cantara.
![Los ajustes de Cantara en inglés](/images/cantara-welcome-assistent-step-1.png)

Aquí debe elegir un directorio de repositorio de canciones donde se almacenan todos los archivos de letras de canciones. Si todavía no tiene ninguno, puede crear una nueva carpeta vacía y seleccionarla como repositorio de canciones. El asistente le sugerirá agregar "Amazing Grace" como canción de ejemplo que puede usar para entender cómo funciona el programa.

Después de haber terminado el asistente de bienvenida, también debe ajustar la configuración de fuentes, el color del texto o el color de fondo según sus deseos. Puede hacerlo en los **Ajustes** (Editar -> Ajustes). La opción *Spoiler siguiente diapositiva* mostrará las letras de la siguiente parte de la canción en un tamaño de fuente más pequeño debajo de la parte actual.

Además, puede configurar cómo deben mostrarse los **metadatos** de las canciones. Vea más detalles en la sección Metadatos.

## La ventana de selección de canciones

Si la configuración se ha completado con éxito, llegará a la ventana de selección de canciones donde puede elegir las canciones que desea cantar. El campo de búsqueda puede ayudarle a encontrar la que le gusta. Simplemente haga doble clic o presione Enter después de la selección de la canción en la lista izquierda, y la canción irá a la lista derecha donde puede ajustar el orden o eliminar las canciones seleccionadas.
![](/images/cantara-songselection-en.png)

Cuando haya terminado, presione el botón *Presentación* para iniciar la presentación. También puede presionar *CTRL+P* en su lugar.

{{% notice tip %}}
Cantara detectará automáticamente al inicio si ha conectado un segundo monitor (como una segunda pantalla o un proyector) a su PC. Si es así, seleccionará el modo de dos ventanas automáticamente. También puede ajustar esto como desee.
{{% /notice %}}

## Durante el modo de presentación

Durante el modo de presentación, puede controlar las diapositivas de presentación de varias maneras:

* Usando las teclas de flecha: Puede usar las teclas de flecha de su teclado para avanzar o retroceder
* Presionando F5/F11: esto activará el modo de pantalla completa
* Usando la tecla Enter o Espacio: Puede usar Enter o Espacio para avanzar una diapositiva
* Presionando ESC: terminará la presentación
* Clic del ratón: Avanzará una diapositiva
* Haciendo clic en una canción en la lista de selección derecha en la ventana de selección de canciones (solo en modo multi-pantalla): Puede saltar directamente a una canción determinada

{{% notice tip %}}
Si está ejecutando otros programas como LibreOffice Impress o MS PowerPoint en modo de presentación al mismo tiempo, puede cambiar fácilmente entre los presentadores con Alt+Tab. Cuando el modo de presentación en Cantara se inicia, cubrirá la segunda pantalla y estará en primer plano. Para mover Cantara al fondo, presione Alt+Tab para navegar al programa que desea mostrar.
{{% /notice %}}

## Ajustar la presentación

Después de ver el estilo de presentación predeterminado, es posible que desee ajustarlo según sus deseos y necesidades. Para esto, puede abrir el diálogo de ajustes (Editar -> Ajustes). Allí puede configurar lo siguiente:

![](/images/cantara-settings-en.png)

- **Ruta del Song Repo**: La ruta del repositorio de canciones. Use el botón con los tres puntos (..) para seleccionar un diálogo de elección de archivo.
- **Diapositivas vacías entre canciones**: Esto crea una diapositiva vacía adicional en la presentación *entre* dos canciones diferentes.
- **Spoiler siguiente diapositiva**: Muestra el contenido o partes de la siguiente diapositiva debajo del texto si la canción tiene una diapositiva adicional y el espacio de la diapositiva es suficiente.
- **Alineación**: Ajusta la alineación horizontal y vertical del texto en las diapositivas de presentación. Presione **Detalles** para configurar el tamaño del borde.
- **Ajuste de línea automático**: Divide las diapositivas si una estrofa (parte de canción) ha alcanzado el límite especificado de líneas (recomendado especialmente si tiene canciones con estrofas largas).
- **Cambiar configuración de fuente.../Color de fondo.../Color de texto...**: Abre diálogos para especificar el diseño de la presentación.
- **Imagen de fondo**: Abre un diálogo de elección de archivo donde puede seleccionar una imagen de fondo para sus presentaciones. Si está disponible, la carpeta con algunas imágenes de fondo predeterminadas se abrirá primero.
- **Cambiar transparencia de imagen**: Ajusta la transparencia de la imagen **hacia** el color de fondo. Eso significa que si el color de fondo está configurado en (por ejemplo) negro, un valor más alto hará que la imagen sea *más oscura*. Si el fondo fuera blanco, un valor más alto haría que la imagen fuera *más brillante*.
- **Mostrar metadatos**: Ciertos metadatos se pueden mostrar en una diapositiva de título especial (si se elige), en la primera diapositiva o en la última diapositiva. Introduzca la sintaxis en el gran campo de edición en la parte inferior y consulte [Metadatos](/tutorial/meta-data) para más detalles.
- **Imagen de vista previa**: Haga clic en la vista previa para avanzar una diapositiva. Si la presentación ha llegado a su fin, volverá al principio.

## Exportar presentación

Cantara ofrece varias formas de exportar presentaciones para que puedan reutilizarse en otro programa o para otro propósito. Todas las opciones de exportación están disponibles en el *menú de exportación* de la ventana principal. Generalmente, hay dos tipos de exportaciones:

1. **Exportar las diapositivas de presentación**: Esto exportará las diapositivas de presentación exactamente como se muestran dentro de Cantara. Por el momento hay dos opciones de exportación para este tipo:
   1. **Presentación de PowerPoint** (archivo .pptx): Esto exportará la presentación de diapositivas como un archivo pptx para que pueda usarse en un programa de presentación (Microsoft PowerPoint, LibreOffice Impress, Softmaker Presentation, etc.). Para la generación de las diapositivas, la biblioteca JavaScript [PptxGenJs](https://gitbrent.github.io/PptxGenJS/) (licencia MIT) se usará dentro del navegador web local como renderizador.
   2. **Imágenes/Fotos**: Esto exportará un archivo JPEG para cada diapositiva y lo guardará en una carpeta a elegir.
2. **Exportar las letras como Markup**: Exportará las letras de las canciones en el orden correcto en un formato de markup especificado pero sin ninguna configuración de presentación (saltos de diapositiva, imagen de fondo, colores, etc.). Esto puede usarse (pero no se limita) para:
   - Exportar las canciones como un mensaje de WhatsApp/Telegram para que pueda compartirse en grupos/canales para que la congregación/personas canten
   - Exportar las canciones como una página web HTML para publicarlas en una página web
   - Exportar solo los títulos de las canciones para reportarlos a CCLI

La estructura del markup se puede especificar a través de un lenguaje de markup estilo LaTeX. Vaya a *Exportar -> Texto Markup* para abrir la ventana de exportación de Markup.

![](/images/cantara-markup-export.png)

El lenguaje de plantilla admite los siguientes comandos/entornos. Todos ellos son *opcionales*:

- ```\header { ... }```: La parte del encabezado del documento que se mostrará en la parte superior del documento. Aquí no se puede mostrar contenido específico de la canción ya que esta parte está fuera del bucle de canciones.
- ```\footer { ... }```: La parte del pie de página del documento que se mostrará en la parte inferior del documento. Aquí no se puede mostrar contenido específico de la canción ya que esta parte está fuera del bucle de canciones.
- ```\newline```: Inserta un salto de línea predeterminado del sistema
- ```\betweensongs { ... }```: Define qué debe mostrarse entre dos canciones (pero no antes de la primera canción y después de la última canción). El valor predeterminado se establece en dos saltos de línea (un nuevo párrafo: ```\betweensongs { \newline \newline }```)
- ```\lineending```: Especifica el final de línea dentro del bucle de canciones (el valor predeterminado es ```\newline```)
- ```\songloop { ... }``` El contenido que se mostrará **para cada canción** (repetido para cada canción). Dentro de este entorno, las etiquetas de canción (ver [Metadatos](/tutorial/meta-data)) se pueden acceder a través de ```\tagname``` — por ejemplo, ```\title``` para la etiqueta ```title``` y ```\author``` para la etiqueta ```author```. Las letras en sí se cargan a través del comando ```\lyrics```.

## Guardar y cargar selecciones de canciones

Puede guardar y cargar selecciones de canciones en Cantara para compartirlas dentro de la organización o para preparar un evento. Al hacerlo, tiene dos opciones:

1. El formato **songtex** contiene los nombres de las canciones **y** el archivo de canción con su contenido. Eso significa que si exporta la selección de canciones a un archivo songtex, el receptor no necesita tener las canciones en su repositorio de canciones. Al importar el archivo songtex, Cantara verifica si el archivo ya existe en el repositorio y, si no, lo agrega.
2. La función de exportación/importación heredada importa solo los títulos, lo que significa que el receptor necesita tener las canciones en su repositorio de canciones.
