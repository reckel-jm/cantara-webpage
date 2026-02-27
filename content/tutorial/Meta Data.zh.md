---
title: "歌曲元数据"
date: 2022-08-02T15:37:14+02:00
draft: false
toc: true
weight: 5
---

Cantara 允许您从歌曲中获取并显示元数据。根据歌曲格式，Cantara 将获取以下元数据。

## CCLI Songselect

从每个 CCLI Songselect 歌词文件中将收集以下数据：

* `author`：所有作者的姓名，以"|"分隔。
* `ccli-licensenumber`：CCLI 许可证编号，取决于用户账户（不取决于歌曲）。
* `ccli-songnumber`：歌曲的 CCLI 编号，取决于歌曲。

## 歌曲格式

在歌曲格式中，元数据可以通过以 `#` 开头的行来指定。例如：

    #author: John Newton
    #title: Amazing Grace

    Amazing Grace, how sweet the sound
    that saved a wretch like me.
    I once wast lost, but now am found,
    was blind, but now I'm free!

    [...]

这将为 `author` 和 `title` 设置元数据。

## 如何使用元数据：

在设置对话框中，您可以为每首歌曲启用元数据。在*元数据内容*字段中，您可以指定元数据应如何显示的格式。除了显示纯文本外，您还可以使用以下变量：

* `{property1}`：如果元数据属性 *property1* 存在，则显示它。
* `{%property1%}某些文字{%end%}`：如果 *property1* 存在，则显示*某些文字*。
* `{%property1%}某些文字`：如果 *property1* 存在，则显示*某些文字*（直到行末）。

例如，以下语法：

    {%ccli-licensenumber%}歌曲来源：CCLI {ccli-licensenumber}
    {%author%}作者：{author}

对于上面的 `Amazing Grace.song` 将生成：

    作者：John Newton

因为 `author` 存在，但 `ccli-licensenumber` 不存在。
