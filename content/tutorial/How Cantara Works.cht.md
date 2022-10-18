---
title: "Cantara 如何工作"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 1
---

## 背景故事

在我上高中的時候，我成為了一個青年團契的領導。在進行我們的活動時，我們喜歡以歌唱開始。然而我們遇到了一些問題：可用的歌曲書籍數量不夠，其內容也未必能獲得我們的青睞。

At that time I was looking for an available song presentation program and became disappointed quickly. Most of the existing programs were either commercial, very complicated or simply an "overkill" for the basically quite simple purpose: People should be able to (spontaneously) choosing songs, the program should then display them.

At that time, I decided to start the development of Cantara. The name is coming from the Latin "cantare" (to sing) but more artificial then real. An other reason for choosing the name was that at the same time, I was becoming an organ player in church –and the German name for that position is "Kantor" which sounds quite similar.

Later I have been able to lead the [best student group in the world](https://www.smd-chemnitz.de) 😃 and while doing so, the program slowly was growing and updated with new futures like multi-screen-support and the opportunity to export song texts directly to the clipboard so that it can be used in small groups without beamer projection possibility. Cantara's development will continue and I hope that it will be a small tool to praise and worship our great heavenly father!

## The Approach

{{<mermaid align="left">}}
graph LR;
    A[Song Rep] -->|Collecting Songs| B(Song List)
    B --> C(Song Selection)
    C --> D{Generate Presentation Data}
    D --> E[Run Presentation]
    D --> F[Copy Lyrics to Clipboard]
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
