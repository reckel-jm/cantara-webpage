---
title: "Traducir"
date: 2022-08-10T15:11:10+02:00
weight: 2
---

Cantara puede traducirse fácilmente a otro idioma. Al hacerlo, ayudará a difundir el uso del software en todo el mundo, para que también las personas que no hablan inglés tengan acceso a Cantara.

## Cómo funciona

Cantara usa archivos de idioma (`*.mo`-files) que contienen las cadenas de idioma traducidas en un lenguaje binario. Estos archivos se pueden crear usando un editor como [Poedit](https://poedit.net/) usando el archivo [cantara.pot](https://github.com/reckel-jm/cantara/blob/master/locals/cantara.pot) como plantilla.

Si desea hacer una traducción a un nuevo idioma, proceda de la siguiente manera:

1. Descargue [cantara.pot](https://github.com/reckel-jm/cantara/blob/master/locals/cantara.pot) y ábralo con un editor apropiado.
2. Traduzca las cadenas al idioma de destino deseado.
3. Exporte el contenido traducido como un archivo `.mo` **¡pero también conserve el archivo `.po` traducido!**
4. Copie el archivo `idioma.mo` a `<cantara-dir>/languages/idioma/cantara.mo` (reemplace `idioma` con el código corto del idioma, por ejemplo, *de* para alemán, *en* para inglés, *zh* para chino, etc.).
5. Pruebe su traducción ejecutando Cantara con la opción `--lang`:

    `cantara --lang=<código de idioma>`


6. Si la traducción funciona bien, por favor haga un pull request en GitHub para que otros también puedan beneficiarse de ella.

## Estado actual

Actualmente, Cantara está traducido a los siguientes idiomas:

| Idioma | Completitud |
|--------|-------------|
| Árabe                 | 100 %       |
| Bahasa Indonesia      | 100 %       |
| Inglés                | 100 %       |
| Chino (tradicional)   | 100 %       |
| Neerlandés            | 100 %       |
| Farsi                 | 100 %       |
| Francés               | 100 %       |
| Alemán                | 100 %       |
| Hebreo                | 100 %       |
| Italiano              | 100 %       |
| Japonés               | 100 %       |
| Coreano               | 100 %       |
| Polaco                | 100 %       |
| Ruso                  | 100 %       |
| Español               | 100 %       |
| Turco                 | 100 %       |
| Ucraniano             | 100 %       |
| Vietnamita            | 100 %       |
