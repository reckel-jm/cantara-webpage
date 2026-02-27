---
title: "管理歌曲"
date: 2022-07-19T15:37:14+02:00
draft: false
toc: true
weight: 4
---

使用 Cantara 时，您需要收集、编辑和分发用于演示或导出的歌曲。第一次启动 Cantara 时，您会注意到——根据您在欢迎助手中的选择——可能只有一首歌曲可用："Amazing Grace"。从那时起，您就可以开始获取和添加歌曲了。

您选择作为歌曲仓库的文件夹将包含您在 Cantara 中使用的所有歌曲。这意味着要添加新歌曲，只需在该文件夹中添加新文件即可。编辑或删除歌曲也可以采用类似方法。如果您想与他人共享所有歌曲，只需复制目录中的文件或共享文件夹本身即可。
也有一种常见做法是在仓库文件夹中创建 Git 仓库，然后通过 Github、Gitlab 或其他提供商进行共享。

## 了解歌曲的保存方式

Cantara 支持两种不同的歌曲格式。一种文件扩展名为 `.song`，设计非常简单。它只包含按应呈现顺序排列的歌词，以及描述歌曲元数据的一些标签。另一种格式由 [CCLI Songselect](https://songselect.ccli.com/) 使用，文件扩展名为 `.txt` 或 `.ccli`。CCLI 是一个商业数据库，您可以从中下载许多用于教会或基督徒团体的基督教歌曲。

{{% notice tip %}}
德国许多基督教教会团体（包括 FeG、SMD 等，据我所知）为会员提供 CCLI Songselect 访问权限。您可以了解您的组织是否已为您订阅。
{{% /notice %}}

Cantara 将自动检测正确的歌曲格式并按以下方式进行解释。

### 歌曲文件格式

歌曲文件格式是以 `.song` 结尾的文件。歌词必须按照应显示的顺序排列，包括重复部分。不同幻灯片用双换行（空行）分隔。例如，如果您想添加歌曲"'Tis so sweet to trust in Jesus"，请添加一个新文件 `'Tis so sweet to trust in Jesus.song`，内容如下：

{{%expand "展开文件内容 " %}}
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

该歌曲由四节经文组成，每节后重复副歌。现在，假设我们想要一个稍微不同的版本，两节一起唱。一个好的约定是将现有文件 `'Tis so sweet to trust in Jesus.song` 复制到 `'Tis so sweet to trust in Jesus [两节一起].song` 并调整内容：

{{%expand "展开文件内容 " %}}
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

Cantara 将检测两个歌曲文件并将它们并排列出。虽然这种方法起初看起来有些复杂，但实际使用表明它比使用更复杂的文件格式要容易得多。您随时可以使用本地文本编辑器按需调整歌词，不存在误解或顺序错误的风险。

### CCLI Songselect

当您从 CCLI Songselect 下载歌曲时，将使用 CCLI Songselect 格式。与歌曲格式不同，CCLI Songselect 歌词格式没有提供关于歌曲不同部分（节/副歌等）正确顺序的明确信息。因此，Cantara 必须使用实现的算法来猜测顺序。对于**大多数歌曲**，Cantara 会将歌词排列成正确的顺序。但是，一些 CCLI 歌曲文件缺乏一致性。在这种情况下，您可以将 CCLI 文件转换为歌曲文件，并根据您的需要手动编辑它。

{{% notice note %}}
由于缺乏一致性，不建议直接编辑 CCLI Songselect 文件。Cantara 会要求您先将其转换为歌曲文件。
{{% /notice %}}

以下是 Cantara 能理解的部分信息：

  * "Vers/Strophe"：将在放置位置只唱一次的节
  * "Chorus"：如果可用，副歌将在放置位置演唱，然后在每节或桥段后重复。如果出现另一个副歌，它将替换第一个。
  * "Bridge"：像节一样对待。如果之前有副歌，则很可能会跟随副歌。
  * "PreChorus"：在副歌之前演唱（这里格式相当不一致！）
  * "Schluss"：歌曲的结束部分。不会跟随副歌。

{{% notice note %}}
编辑器能够将 CCLI 文件转换为歌曲格式。只需在编辑器中打开 CCLI 文件并确认您想要进行转换。
{{% /notice %}}

## 从 CCLI Songselect 下载歌曲

如上所述，您可以直接从 [CCLI Songselect](https://songselect.ccli.com/) 导入歌曲。前往其网站，用您的账户登录，搜索您想下载的歌曲。按其右侧的对话气泡符号（见下图）。显示文本后，点击从左边数第三个带下载符号的蓝色按钮。将 .txt 文件直接保存到 Cantara 歌曲仓库目录中。Cantara 应该能识别该歌曲并以正确顺序使用歌词。

![](/images/ccli-results.jpg?width=800) ![](/images/ccli-song-download.jpg?width=800)

{{% notice warning %}}
如前所述，在使用 CCLI 及歌曲版权所有者的服务时，遵守 CCLI 的法律要求是您的责任！
{{% /notice %}}

## 其他歌词来源

  * [Hymnary.org](https://hymnary.org/)：非常大的赞美诗收藏（主要是英语）
  * [Evangeliums.net](https://www.evangeliums.net/lieder/)：德语基督教歌曲收藏，由于版权限制，部分内容无法直接访问
  * [Github 上的 Cantara SongRepo](https://github.com/reckel-jm/cantara_songrepo)：包含公共领域歌曲，可免费直接使用

## 使用内置编辑器编辑和转换歌曲

Cantara 提供内置编辑器，为创建、编辑或删除歌曲提供简便方式。此外，您可以将 CCLI 歌曲转换为歌曲格式，以便根据需要进行调整。
