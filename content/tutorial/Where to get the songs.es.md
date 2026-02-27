---
title: "Gestionar canciones"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 4
---

Al usar Cantara, necesitará recopilar, editar y distribuir canciones que pueden usarse para presentar o exportar. Si inicia Cantara por primera vez, notará que — dependiendo de lo que haya elegido en el asistente de bienvenida — puede que solo encuentre una canción disponible: "Amazing Grace". A partir de ese punto, puede comenzar a obtener y agregar canciones.

La carpeta que elija como repositorio de canciones contendrá todas las canciones que use en Cantara. Eso significa que para agregar una nueva canción, es suficiente con agregar un nuevo archivo en esa carpeta. Del mismo modo puede proceder para editar o eliminar canciones. Si desea compartir todas las canciones con alguien más, simplemente copie los archivos de su directorio o comparta la propia carpeta.
También se ha desarrollado como práctica común crear un repositorio Git en la carpeta de su repositorio que luego puede compartirse a través de Github, Gitlab u otros proveedores.

## Comprender la forma en que se guardan las canciones

Cantara admite dos formatos de canciones diferentes. Uno tiene la extensión de archivo `.song` y está diseñado de manera muy simple. Solo contiene las letras en el orden en que deben presentarse junto con algunas etiquetas que describen los metadatos de las canciones. El otro formato es usado por [CCLI Songselect](https://songselect.ccli.com/) y tiene las extensiones de archivo `.txt` o `.ccli`. CCLI es una base de datos comercial de donde puede descargar muchas canciones cristianas para su uso en iglesias o grupos cristianos.

{{% notice tip %}}
Muchas denominaciones e iglesias y grupos cristianos en Alemania (incluyendo FeG, SMD, por lo que sé) proporcionan acceso de miembro a CCLI Songselect. Puede averiguar si su organización ya ha reservado una suscripción para usted.
{{% /notice %}}

Cantara detectará automáticamente el formato de canción correcto y lo interpretará de la manera indicada a continuación.

### El formato de archivo de canción

El formato de archivo de canción es un archivo que termina con `.song`. Las letras deben imprimirse en el mismo orden en que deben mostrarse, incluidas las repeticiones. Las diferentes diapositivas se separan con un doble salto de línea (una línea vacía). Por ejemplo, si desea agregar la canción "'Tis so sweet to trust in Jesus", agregue un nuevo archivo `'Tis so sweet to trust in Jesus.song` con el siguiente contenido:

{{%expand "Expandir el contenido del archivo " %}}
    'Tis so sweet to trust in Jesus
    Just to take Him at His word
    Just to rest upon His promise
    Just to know thus saith the Lord

    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more

    O how sweet to trust in Jesus
    Just to trust His cleansing blood
    Just in simple faith to plunge me
    'Neath the healing cleansing flood

    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more

    Yes 'tis sweet to trust in Jesus
    Just from sin and self to cease
    Just from Jesus simply taking
    Life and rest and joy and peace

    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more

    I'm so glad I learned to trust Thee
    Precious Jesus Savior Friend
    And I know that Thou art with me
    Wilt be with me to the end

    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more
{{% /expand%}}

La canción consta de cuatro estrofas con el coro repetido después de cada una. Ahora, digamos que querríamos tener una versión ligeramente diferente de la canción donde cantamos dos estrofas juntas. Una buena convención para esto sería copiar el archivo existente `'Tis so sweet to trust in Jesus.song` a `'Tis so sweet to trust in Jesus [dos estrofas juntas].song` y ajustar el contenido:

{{%expand "Expandir el contenido del archivo " %}}
    'Tis so sweet to trust in Jesus
    Just to take Him at His word
    Just to rest upon His promise
    Just to know thus saith the Lord

    O how sweet to trust in Jesus
    Just to trust His cleansing blood
    Just in simple faith to plunge me
    'Neath the healing cleansing flood

    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more

    Yes 'tis sweet to trust in Jesus
    Just from sin and self to cease
    Just from Jesus simply taking
    Life and rest and joy and peace

    I'm so glad I learned to trust Thee
    Precious Jesus Savior Friend
    And I know that Thou art with me
    Wilt be with me to the end

    Jesus Jesus how I trust Him
    How I've proved Him o'er and o'er
    Jesus Jesus precious Jesus
    O for grace to trust Him more
{{% /expand%}}

Cantara detectará ambos archivos de canciones y los listará uno al lado del otro. Mientras que este enfoque puede parecer un poco complicado al principio, el uso práctico ha demostrado que es mucho más fácil que usar formatos de archivo más complejos. Siempre puede usar su editor de texto local para ajustar las letras como desee. No habrá peligro de malinterpretación o orden incorrecto.

### CCLI Songselect

El formato CCLI Songselect se usará si descarga una canción de CCLI Songselect. A diferencia del formato de canción, el formato de letras CCLI Songselect no proporciona información clara sobre el orden correcto de las diferentes partes en una canción (estrofas/coros, etc.). Por lo tanto, Cantara tiene que adivinar el orden con un algoritmo implementado. Para **la mayoría de las canciones**, Cantara pondrá las letras en el orden correcto. Sin embargo, algunos de los archivos de canciones CCLI carecen de consistencia. En este caso, puede convertir el archivo CCLI a un archivo de canción y editarlo manualmente según sus necesidades.

{{% notice note %}}
Debido a la falta de consistencia, no se recomienda editar un archivo CCLI Songselect directamente. Cantara le pedirá que lo convierta primero a un archivo de canción.
{{% /notice %}}

Aquí hay información sobre las partes que Cantara entiende:

  * "Vers/Strophe": una estrofa que se cantará solo una vez en la posición colocada
  * "Chorus": si está disponible, el coro se cantará en la posición colocada y luego se repetirá después de cada estrofa o puente. Si viene otro coro, reemplazará al primero.
  * "Bridge": Se tratará como una estrofa. Un coro seguirá (muy probablemente) si había uno antes.
  * "PreChorus": Se cantará antes del coro (¡aquí el formato es bastante inconsistente!)
  * "Schluss": Una parte final de la canción. No seguirá ningún coro.

{{% notice note %}}
El editor es capaz de convertir archivos CCLI al formato de canción. Solo abra un archivo CCLI en el editor y confirme que desea realizar la conversión.
{{% /notice %}}

## Descargar canciones de CCLI Songselect

Como se indicó anteriormente, puede importar canciones directamente desde [CCLI Songselect](https://songselect.ccli.com/). Vaya a su página web, inicie sesión con su cuenta y busque la canción que desea descargar. Presione el símbolo de burbuja de diálogo justo al lado (ver imagen a continuación). Después de que se muestre el texto, haga clic en el tercer botón azul desde la izquierda con el símbolo de descarga. Guarde el archivo .txt directamente en el directorio del repositorio de canciones de Cantara. Cantara debería reconocer la canción y usar las letras en el orden correcto.

![](/images/ccli-results.jpg?width=800) ![](/images/ccli-song-download.jpg?width=800)

{{% notice warning %}}
¡Como se indicó antes, es su responsabilidad cumplir con los requisitos legales de CCLI y los propietarios de derechos de autor de las canciones al usar sus servicios!
{{% /notice %}}

## Fuentes adicionales de letras de canciones

  * [Hymnary.org](https://hymnary.org/): Una colección de himnos muy grande (principalmente en inglés)
  * [Evangeliums.net](https://www.evangeliums.net/lieder/): Una colección alemana de canciones cristianas, algunas no pueden accederse directamente debido a restricciones de derechos de autor
  * [El SongRepo de Cantara en Github](https://github.com/reckel-jm/cantara_songrepo): Contiene canciones de dominio público para uso libre y directo

## Editar y convertir canciones con el editor integrado

Cantara ofrece un editor integrado que proporciona una forma fácil de crear, editar o eliminar canciones. Además, puede convertir una canción CCLI al formato de canción para que pueda adaptarse a sus necesidades.
