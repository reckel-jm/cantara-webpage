---
title: "How Cantara Works"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 1
---

## Background Story

When I was at my high school time, I became part in the leadership of a Christian youth group. When conducting our events, we liked to sing a few songs at the beginning. However the problem occurred that the available song books where not enough and the content was sometimes not matching with the songs which were wished. At that time I was looking for an available song presentation program and became disappointed quickly. Most of the existing programs were either commercial, very complicated or simply an "overkill" for the basically quite simple purpose: People should be able to (spontaneously) choosing songs, the program should then display them.

At that time, I decided to start the development of Cantara. The name is coming from the Latin "cantare" (to sing) but more artificial then real. An other reason for choosing the name was that at the same time, I was becoming an organ player in church –and the German name for that position is "Kantor" which sounds quite similar.

Later I have been able to lead the [best student group in the world](https://www.smd-chemnitz.de) 😃 and while doing so, the program slowly was growing and updated with new futures like multi-screen-support and the opportunity to export song texts directly to the clipboard so that it can be used in small groups without beamer projection possibility. Cantara's development will continue and I hope that it will be a small tool to praise and worship our great heavenly father!

## The Approach

{{<mermaid align="left">}}
graph LR;
    A[Input File] -->|Collecting Songs| B(Song List)
    B --> C(Song Selection)
    C --> D{Generate Presentation Data}
    D --> E[Run Presentation Directly]
    D --> F[Export Lyrics in Markup Format]
    D --> G[Export Presentation as PPTX]
    D --> H[Export Presentation as Pictures]
{{< /mermaid >}}

Cantara takes the songs from *one particular folder* on the file system which is called the *song repository* (or briefly song repo). Every song is a simple text file which can be edited with a text editor of your choice. Cantara will recognize the song title from the name of the file (without the extension). So, for example. If you have a file like:

    Amazing Grace.song

Cantara will recognize it as "Amazing Grace" written in the song format (for formats see the next section).

{{% notice tip %}}
The song repository dictionary can be shared and synced easily via cloud services like NextCloud or Git. In that way you can distribute songs within your group or organization.
{{% /notice %}}

{{% notice tip %}}
Since version 2.4.0, Cantara offers a built-in editor which you can use to edit the songs and convert CCLI songs to the Cantara song format. Notice that the songs remain single text files and therefore can still be edited with any text editor.
{{% /notice %}}

{{% notice warning %}}
The developers of Cantara are not responsible for copyright issues which come along with the public use and distributions of song lyrics. Make sure that you obtain the rights for using the song lyrics! In Germany, religious gatherings with free admission enjoy higher copyright freedom than commercial events. However, please make sure with your organization that no legal problems arise.
{{% /notice %}}

## The windows/modes of Cantara

Cantara consists of different windows which allow you to use the program. 

{{< tabs groupid="main" style="primary" title="Windows" icon="window-maximize" >}}
{{< tab title="Song Selection Window" >}}
  This windows will be displayed after you start Cantara. It allows you to see the songs which are available and select those which you would like to use in the presentation or to export.

  <img src="/images/cantara-songselection-selected-hints-de.png" loading="lazy" alt="Song Selection Window of Cantara" class="bg-white border lazy noshadow">  
{{< /tab >}}

{{< tab title="Presentation Window" style="default" >}}
  The presentation window will show and control the loaded presentation (in single screen mode). It can be set to full screen and moved to an other screen.
  If you close the presentation window, the presentation will end and you will return to the song selection window.

  <img src="/images/cantara-presentation-de.png" loading="lazy" alt="Song Presentation Window of Cantara" class="bg-white border lazy noshadow">  

{{< /tab >}}

{{< tab title="Presentation Controller" style="default"  >}}
  In multi screen mode, the presentation controller allows you to control the presentation in detail which is shown at the presentation window. You can see all slides, jump to a slide directly or quit the presentation.

  Normally, you would place the presentation controller on the first screen (the default screen) and the presentation window at the second screen (which is displayed at the beamer, external monitor, etc.).

  <img src="/images/cantara-presentationcontroller-en.png" loading="lazy" alt="Presentation Controller Window of Cantara" class="bg-white border lazy noshadow">  

  {{% notice tip %}}
  The presentation controller uses the song selection window.
  {{% /notice %}}

{{< /tab >}}

{{< tab title="Settings" style="default" >}}
The settings window allows you to adjust the presentation style and change the path of the song repository. You can open the settings in the song selection window.

  <img src="/images/cantara-settings-en.png" loading="lazy" alt="The settings in Cantara" class="bg-white border lazy noshadow"> 
{{< /tab >}}

{{< tab title="Editor" style="default" >}}
The editor allows to add, modify, convert and remove songs in your song repository. You can open the editor via Edit -> Song Lyrics... in the song selection window.

<img src="/images/cantara-editor-en.png" loading="lazy" alt="The editor in Cantara" class="bg-white border lazy noshadow">
{{< /tab >}}

{{< /tabs >}}