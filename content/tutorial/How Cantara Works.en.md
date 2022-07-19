---
title: "How Cantara Works"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 1
---

## Background Story

When I was at my high school time, I became part in the leadership of a Christian youth group. When conducting our events, we liked to sing a few songs at the beginning. However the problem occured that the available song books where not enough and the content was sometimes not matching with the songs which were wished. At that time I was looking for an available song presentation program and became dissapointed quickly. Most of the existing programs were either commercial, very complecated or simply an "overkill" for the basically quite simple purpose: People should be able to (spontanously) choosing songs, the program should then display them.

At that time, I decided to start the development of Cantara. The name is coming from the Latin "cantare" (to sing) but more artificial then real. An other reason for chosing the name was that at the same time, I was becoming an organ player in church –and the German name for that position is "Kantor" which sounds quite similar.

Later I have been able to lead the [best student group in the world](https://www.smd-chemnitz.de) 😃 and while doing so, the program slowly was growing and updated with new futures like multi-screen-support and the opportunity to export song texts directly to the clipboard so that it can be used in small groups without beamer projection possibility. Cantara's development will continue and I hope that it will be a small tool to praise and worship our great heavenly father!

## The Approach

{{<mermaid align="left">}}
graph LR;
    A[Song Rep] -->|Collecting Songs| B(Song List)
    B --> C{Song Selection}
    C -->|Generate Presentation Data| D[Run Presentation]
{{< /mermaid >}}

Cantara takes the songs from *one particular folder* on the file system which is called the *song repository* (or briefly song repo). Every song is a simple text file which can be edited with a text editor of your choice. Cantara will recognize the song title from the name of the file (without the extension). So, for example. If you have a file like:

    Amazing Grace.song

Cantara will recognize it as "Amazing Grace" written in the song format (for formats see the next section).

{{% notice tip %}}
The song repository dictionary can be shared and synced easily via cloud services like NextCloud or Git. In that way you can distribute songs within your group or organization.
{{% /notice %}}

{{% notice warning %}}
The developers of Cantara are not responsible for copyright issues which come along with the public use and distributions of song lyrics. Make sure that you obtain the rights for using the song lyrics! In Germany, religious gatherings with free admission enjoy higher copyright freedom than commercial events. However, please make sure with your organization that no legal problems arise.
{{% /notice %}}