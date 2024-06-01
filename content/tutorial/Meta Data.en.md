---
title: "Song Meta Data"
date: 2022-08-02T15:37:14+02:00
draft: false
toc: true
weight: 5
---

Cantara allows you to fetch and display meta data from the songs. Depending on the song format, Cantara will get the following meta data.

## CCLI Songselect

Following data will be collected from each CCLI songselect lyrics file:

* `author`: The name(s) of all author(s) separated by a '|'.
* `ccli-licensenumber`: The number of the CCLI license which is dependent on the user account (not on the song)
* `ccli-songnumber`: The CCLI number on the song which is dependent on the song.

## Song format

In the song format, meta data can be specified by a line with a `#` at the beginning. For example:

    #author: John Newton
    #title: Amazing Grace
    
    Amazing Grace, how sweet the sound
    that saved a wretch like me.
    I once wast lost, but now am found,
    was blind, but now I'm free!
    
    [...] 

This will set the meta data for `author` and `title`.

## How to use the meta data:

In the settings dialog, you can enable meta data for each song. In the *Meta Data Content* field, you can specify the format how meta data should be displayed. Beside showing plain text, you can use the following variables:

* `{property1}`: Will show the meta data property *property1* if it exists.
* `{%property1%}some text{%end%}`: Will show *some text* if *property1* exists.
* `{%property1%}some text`: Will show *some text* (till the end of the line) if *property1 exists.

For example, the following syntax:

    {%ccli-licensenumber%}Song Source: CCLI {ccli-licensenumber}
    {%author%}Author: {author}

Would generate for the above `Amazing Grace.song`:

    Author: John Newton

because `author` exists but `ccli-licensenumber` does not.
