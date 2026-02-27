---
title: "Notas de versión"
date: 2022-08-02T16:34:40+02:00
draft: false
weight: 2

---

Esta página contiene información sobre los cambios en diferentes versiones (lanzamientos) y planes para el futuro.

---

## Lanzamientos

### Versión 2.7.1 (27-02-2026)

#### Nuevas funciones

- **Alternar pantalla negra durante la presentación**: Un nuevo botón en la barra de control de presentación le permite poner la pantalla en negro instantáneamente y restaurarla. El atajo de teclado `B` tiene el mismo efecto.

#### Correcciones de errores

- Se corrigieron fugas de memoria: `DestroyPresentationStyleSettings` era una operación nula y nunca liberaba el `TFont` propio, causando fugas de fuentes en cada inicio de presentación, actualización de vista previa de estilo y exportación de imagen.
- Se corrigió un bloqueo SIGSEGV al cerrar Cantara mientras una presentación estaba activa: `FormHide` se disparaba durante la destrucción del formulario (después de que `FormDestroy` ya había liberado objetos), causando desreferencias de punteros nulos a través de `PresentationCanvas` y accesos a manejadores de ventana no válidos.
- Se reemplazaron todas las llamadas `.Destroy` desnudas en destructores y manejadores `FormDestroy` con `FreeAndNil` para proteger contra bloqueos de punteros nulos durante el desmontaje.
- Se corrigió una fuga de memoria en `TLoadImageThread`: el `TPresentationStyleSettings.Font` almacenado nunca se liberaba cuando era sobrescrito por una nueva llamada `LoadData`.
- Se corrigió una fuga de memoria en `TfrmSettings.gbPresentationClick`: el canvas de vista previa existente no se liberaba antes de crear uno nuevo.

### Versión 2.7.0 (21-02-2026)

#### Nuevas funciones

- **Anulaciones de estilo por canción**: Cada canción en la selección puede ahora tener su propia imagen de fondo, color de fondo, color de texto, fuente, transparencia y alineación horizontal — independiente de la configuración global de presentación. Un diálogo dedicado "Estilo de canción" es accesible a través del menú contextual con clic derecho en cualquier canción.
- **Maestros PPTX por canción**: Al exportar a PowerPoint, cada canción puede usar su propia diapositiva maestra personalizada.
- **Transición de fundido entre diapositivas**: Se puede habilitar un suave efecto de fundido cruzado entre diapositivas en los ajustes. La duración del fundido es configurable (predeterminado: 150 ms).
- **Pantalla negra en diapositiva vacía**: Un nuevo ajuste hace que Cantara muestre una pantalla completamente negra en lugar del fondo cuando se muestra una diapositiva vacía.
- **Exportación/importación de selección de canciones JSON**: Las selecciones de canciones ahora se pueden guardar y cargar como archivos `.json`. El formato agrupa el contenido de la canción, las anulaciones de estilo por canción y las imágenes de fondo en un único archivo portátil, lo que permite la exportación/importación completa de ida y vuelta entre máquinas.
- **Modo oscuro de Windows**: Cantara ahora sigue la configuración del modo oscuro del sistema en Windows.
- **Instalador de Windows**: Ahora hay disponible un instalador Inno Setup para Windows.
- **Diálogo de bibliotecas de terceros**: Un nuevo diálogo lista todas las bibliotecas de terceros usadas por Cantara junto con sus licencias.

#### Mejoras

- Mejora en el manejo de permisos de Flatpak: Cantara ahora usa el portal XDG para el acceso a archivos en entornos sandbox y proporciona un diálogo de apertura estándar para seleccionar imágenes de fondo.
- Mejora en la representación de texto con una función de ajuste de línea personalizada para un salto de línea más preciso.
- Mejora en la configuración de calidad de representación de fuentes.
- Traducciones actualizadas y ampliadas.
- El título de la ventana principal se ha simplificado a "Cantara".

#### Correcciones de errores

- Se corrigió un bloqueo (SIGSEGV) al iniciar una presentación después de agregar canciones a través de "Seleccionar todo" o arrastrar y soltar, o después de usar el filtro de búsqueda — la referencia al objeto `TRepoFile` no estaba adjunta a las entradas de la lista en esos caminos de código.
- Se corrigió que el editor de canciones no abría la canción correcta cuando se invocaba desde el menú contextual (búsqueda de archivo incorrecta y un problema de tiempo de inicialización del formulario).
- Se corrigió que los cambios de color de fondo y transparencia no se reflejaran en el diálogo de vista previa del estilo de canción.
- Se corrigió que los cambios de color de fondo y transparencia no se aplicaran en la ventana de presentación y la exportación de imágenes cuando dos canciones comparten la misma imagen de fondo pero usan diferentes colores.
- Se corrigió que el análisis de metadatos truncara los valores de campo que contenían un carácter de dos puntos.
- Se corrigió una superposición de diseño del panel de color de fondo y un signo incorrecto en el valor de transparencia en el diálogo de estilo de canción.
- Se corrigió un error de conversión de tipo en la búsqueda de diapositiva maestra personalizada de PPTX.
- Se corrigió una excepción al cerrar la aplicación bajo ciertas condiciones.
- Se corrigió que los archivos `.txt` no se reconocieran como archivos de canciones válidos.
- Se corrigieron varios problemas de dimensionamiento de texto y cálculo de longitud de línea en el canvas de presentación.
- Se corrigió un error de diseño del área de contenido que afectaba a Cantara ejecutándose como Flatpak.

### Versión 2.6.0 (31-05-2024)

- Migración a bgrabitmap para mejor manejo y visualización de las diapositivas de presentación. En el futuro, se pueden implementar fácilmente más efectos de texto como sombras, etc.
- Rediseño del controlador de presentación multi-pantalla: Además de las canciones, cada diapositiva con contenido está listada y puede seleccionarse directamente.
- Menú contextual de la ventana de presentación: La pantalla completa y el final de la presentación ahora también se pueden seleccionar con ese menú.
- Mejoras menores del editor de canciones y búsqueda de texto completo.
- Agregar "Seleccionar todas las canciones" en el menú Archivo en la selección de canciones.
- Corrección de errores: Visualización incorrecta de la presentación cuando no se ha seleccionado una fuente específica #24
- Corrección de errores: Excepción de arrastrar y soltar en la ventana de selección de canciones
- Corrección de errores: Escape incorrecto de caracteres especiales en la exportación pptx
- Muchas correcciones de errores y correcciones menores
- Actualización de traducción

### Versión 2.5.0 (21-08-2023)

- Reescritura completa de grandes partes del código fuente incluyendo las estructuras internas para generar y pintar diapositivas de presentación
- Mejora del diseño de presentación
- Mejora del editor de canciones
- Implementación de una vista previa de la presentación en el menú de ajustes
- Implementación de exportación de diapositivas a pptx (usando PptxgenJs)
- Implementación de exportación de diapositivas a imágenes
- Implementación de exportación de letras de canciones a archivos de texto de markup
- Implementación de búsqueda de texto completo para navegar por letras de canciones
- Implementación de presentación de canciones en dos idiomas
- Mejoras de la ventana de presentación y control (se admiten más teclas y controles remotos)
- Corrección del [issue #17](https://github.com/reckel-jm/cantara/issues/17)
- Cantara ahora puede abrirse directamente con un archivo ```.songtex```.

### Versión 2.4.1 (30-01-2023) Traducción italiana y española

La versión 2.4.1 agrega traducción italiana y española a Cantara. A pesar de eso, no hay funcionalidad adicional en comparación con la versión 2.4.0, lo que significa que si no usa uno de los idiomas, no necesariamente necesita actualizar a esta versión.

**¡Gracias a los traductores!**

* La traducción italiana fue proporcionada por [@albanobattistella](https://github.com/albanobattistella)
* La traducción española fue proporcionada por [@haggen88](https://github.com/haggen88)

¡Gracias por el esfuerzo!

### Versión 2.4.0 (06-01-2023)

¡La versión 2.4 finalmente está aquí! Además de nuevas funciones, también trae muchas correcciones de errores. Vea la lista a continuación para más detalles.

#### Mejoras/Mejoras

* Se ha implementado un nuevo editor que permite editar canciones, convertir canciones CCLI al formato de canción, crear nuevas canciones, archivarlas y clonarlas (por ejemplo, para diferentes versiones).
* Un asistente de bienvenida guiará a los nuevos usuarios después del primer inicio de Cantara para configurar y entender el programa.
* Cantara puede dividir automáticamente diapositivas largas en dos páginas si se configura en los ajustes.
* El nuevo formato de archivo SongTeX permite exportar diapositivas de canciones con las letras y el orden.

#### Correcciones de errores

- Errores de punto flotante cuando no se selecciona ninguna imagen de fondo
- Cargar las diapositivas tomaba mucho tiempo si se seleccionaba un fondo

### Versión 2.3.2 (10-11-2022)

Esta es una versión menor que trae dos pequeñas pero útiles mejoras:

* Finalización de la traducción al chino tradicional
* Preparación para Flatpak

Consulte la correspondiente [página de GitHub](https://github.com/reckel-jm/cantara/releases/tag/v2.3.2) para más detalles.

### Versión 2.3.1 (12-08-2022)

Esta es una versión menor y seguimiento de la versión 2.3.

#### Mejoras

- La versión 2.3.1 trae soporte para imágenes de fondo. Estas se pueden ajustar y hacer transparentes (hacia el color de fondo) o más brillantes.

#### Correcciones de errores

- Corrección de error tipográfico en la etiqueta de licencia CCLI. Ahora es `ccli-licensenumber`
- Traducción al alemán completa

### Versión 2.3 (02-08-2022)

Después de pruebas y más desarrollo, se puede lanzar la versión 2.3.

Mejoras:

* Soporte del formato CCLI Songselect
* Soporte para metadatos que se pueden mostrar dinámicamente durante la canción
* Mejoras en el código fuente
* Preparaciones para más desarrollo en el código fuente, abstracciones
* Correcciones de errores en la visualización de canciones

Como siempre, estoy esperando comentarios, sugerencias e informes de errores.
¡Gracias!

[Ir a la página de Github del lanzamiento](https://github.com/reckel-jm/cantara/releases/tag/v2.3)
