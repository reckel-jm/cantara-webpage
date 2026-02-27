---
title: "Cantara 的工作原理"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 1
---

## 背景故事

高中时，我加入了一个基督教青年团契的领导团队。在举办活动时，我们喜欢在开始时唱几首歌。然而问题出现了——现有的歌本数量不足，内容有时也与大家希望唱的歌曲不符。那时我开始寻找可用的歌曲演示软件，但很快就感到失望。大多数现有程序不是商业软件，就是极其复杂，或者对于这个本质上很简单的目的来说过于"大材小用"：人们应该能够（自发地）选择歌曲，程序随后将其显示出来。

那时，我决定开始开发 Cantara。这个名字来自拉丁语"cantare"（唱歌），但更多是人为选取的而非自然而然。选择这个名字的另一个原因是，同一时期我成了教会的管风琴手——而德语中这个职位的名称是"Kantor"，听起来颇为相似。

后来我有幸领导了[世界上最好的学生团契](https://www.smd-chemnitz.de) 😃，在此期间，这个程序慢慢成长并更新了新功能，如多屏支持以及将歌词直接导出到剪贴板的功能，使其可以在没有投影仪的小组中使用。Cantara 的开发将继续，我希望它能成为赞美和敬拜我们伟大天父的小工具！

## 方法

{{<mermaid align="left">}}
graph LR;
    A[输入文件] -->|收集歌曲| B(歌曲列表)
    B --> C(歌曲选择)
    C --> D{生成演示数据}
    D --> E[直接运行演示]
    D --> F[以标记格式导出歌词]
    D --> G[将演示导出为 PPTX]
    D --> H[将演示导出为图片]
{{< /mermaid >}}

Cantara 从文件系统上的*一个特定文件夹*获取歌曲，该文件夹称为*歌曲仓库*（简称 song repo）。每首歌曲都是一个简单的文本文件，可以用您选择的任何文本编辑器进行编辑。Cantara 将根据文件名（不含扩展名）识别歌曲标题。例如，如果您有一个这样的文件：

    Amazing Grace.song

Cantara 会将其识别为以歌曲格式书写的"Amazing Grace"（关于格式，请参见下一节）。

{{% notice tip %}}
歌曲仓库目录可以通过 NextCloud 或 Git 等云服务轻松共享和同步。这样您就可以在您的团队或组织内分发歌曲。
{{% /notice %}}

{{% notice tip %}}
从 2.4.0 版本开始，Cantara 提供了内置编辑器，您可以使用它来编辑歌曲并将 CCLI 歌曲转换为 Cantara 歌曲格式。请注意，歌曲仍然是单个文本文件，因此仍然可以用任何文本编辑器进行编辑。
{{% /notice %}}

{{% notice warning %}}
Cantara 的开发者对公开使用和分发歌词时产生的版权问题不承担责任。请确保您已获得使用歌词的权利！在德国，免费入场的宗教集会比商业活动享有更高的版权自由度。但请与您的组织确认，以免出现法律问题。
{{% /notice %}}

## Cantara 的窗口/模式

Cantara 由不同的窗口组成，让您可以使用该程序。

{{< tabs groupid="main" style="primary" title="窗口" icon="window-maximize" >}}
{{< tab title="歌曲选择窗口" >}}
  启动 Cantara 后，此窗口将显示出来。它允许您查看可用的歌曲，并选择您想在演示中使用或导出的歌曲。

  <img src="/images/cantara-songselection-selected-hints-de.png" loading="lazy" alt="Cantara 歌曲选择窗口" class="bg-white border lazy noshadow">
{{< /tab >}}

{{< tab title="演示窗口" style="default" >}}
  演示窗口将显示并控制已加载的演示（在单屏模式下）。可以设置为全屏并移动到另一个屏幕。
  如果您关闭演示窗口，演示将结束，您将返回到歌曲选择窗口。

  <img src="/images/cantara-presentation-de.png" loading="lazy" alt="Cantara 歌曲演示窗口" class="bg-white border lazy noshadow">

{{< /tab >}}

{{< tab title="演示控制器" style="default" >}}
  在多屏模式下，演示控制器允许您详细控制演示窗口中显示的演示。您可以查看所有幻灯片、直接跳转到某张幻灯片或退出演示。

  通常，您会将演示控制器放在第一个屏幕（默认屏幕）上，将演示窗口放在第二个屏幕（显示在投影仪、外部显示器等上）上。

  <img src="/images/cantara-presentationcontroller-en.png" loading="lazy" alt="Cantara 演示控制器窗口" class="bg-white border lazy noshadow">

  {{% notice tip %}}
  演示控制器使用歌曲选择窗口。
  {{% /notice %}}

{{< /tab >}}

{{< tab title="设置" style="default" >}}
设置窗口允许您调整演示样式并更改歌曲仓库的路径。您可以在歌曲选择窗口中打开设置。

  <img src="/images/cantara-settings-en.png" loading="lazy" alt="Cantara 中的设置" class="bg-white border lazy noshadow">
{{< /tab >}}

{{< tab title="编辑器" style="default" >}}
编辑器允许您在歌曲仓库中添加、修改、转换和删除歌曲。您可以通过歌曲选择窗口中的"编辑 -> 歌词..."来打开编辑器。

<img src="/images/cantara-editor-en.png" loading="lazy" alt="Cantara 中的编辑器" class="bg-white border lazy noshadow">
{{< /tab >}}

{{< /tabs >}}
