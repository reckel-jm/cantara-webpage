---
title: "Translate"
date: 2022-08-10T15:11:10+02:00
weight: 2
---

Cantara can be easily translated to an other language. While doing so, you will help to spread the use of the software all over the world, so that also people who don't speak English have access to Cantara.

## How it works

Cantara uses language files (`*.mo`-files) which contain the translated language strings in a binary language. This files can be created by using an editor like [Poedit](https://poedit.net/) using the [cantara.pot](https://github.com/reckel-jm/cantara/blob/master/locals/cantara.pot) file as a template.

If you would like to do a translation into a new language, procedure in the following way:

1. Download [cantara.pot](https://github.com/reckel-jm/cantara/blob/master/locals/cantara.pot) and open it with an appropriate editor.
2. Translate the strings into the desired target language.
3. Export the translated content as an `.mo`-file **but also keep the translated `.po` file!**
4. Copy the `language.mo` file to `<cantara-dir>/languages/language/cantara.mo` (replace `language` with the shortcode of the language, e.g. *de* for German, *en* for English, *zh* for Chinese, etc.).
5. Test your translation by running Cantara with the `--lang` option:

    `cantara --lang=<language code>`


6. If the translation works well, please make a pull request at GitHub so that others can make use of it as well.

## Current State

Currently, Cantara is translated to the following languages:

| Language | Completeness |
|----------|--------------|
| English               | 100 %        |
| German                | 100 %        |
| Chinese (traditional) | 100 %        |
