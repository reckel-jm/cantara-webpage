---
title: "Metadatos de canciones"
date: 2022-08-02T15:37:14+02:00
draft: false
toc: true
weight: 5
---

Cantara le permite obtener y mostrar metadatos de las canciones. Dependiendo del formato de la canción, Cantara obtendrá los siguientes metadatos.

## CCLI Songselect

Se recopilarán los siguientes datos de cada archivo de letras CCLI Songselect:

* `author`: El nombre o nombres de todos los autores separados por un '|'.
* `ccli-licensenumber`: El número de la licencia CCLI que depende de la cuenta del usuario (no de la canción).
* `ccli-songnumber`: El número CCLI de la canción que depende de la canción.

## Formato de canción

En el formato de canción, los metadatos se pueden especificar mediante una línea que comienza con `#`. Por ejemplo:

    #author: John Newton
    #title: Amazing Grace

    Amazing Grace, how sweet the sound
    that saved a wretch like me.
    I once wast lost, but now am found,
    was blind, but now I'm free!

    [...]

Esto establecerá los metadatos para `author` y `title`.

## Cómo usar los metadatos:

En el diálogo de ajustes, puede habilitar metadatos para cada canción. En el campo *Contenido de metadatos*, puede especificar el formato en que deben mostrarse los metadatos. Además de mostrar texto sin formato, puede usar las siguientes variables:

* `{property1}`: Mostrará la propiedad de metadatos *property1* si existe.
* `{%property1%}algún texto{%end%}`: Mostrará *algún texto* si *property1* existe.
* `{%property1%}algún texto`: Mostrará *algún texto* (hasta el final de la línea) si *property1* existe.

Por ejemplo, la siguiente sintaxis:

    {%ccli-licensenumber%}Fuente de la canción: CCLI {ccli-licensenumber}
    {%author%}Autor: {author}

Generaría para el anterior `Amazing Grace.song`:

    Autor: John Newton

porque `author` existe pero `ccli-licensenumber` no.
