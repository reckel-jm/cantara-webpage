---
title: "翻譯"
date: 2022-08-10T15:11:10+02:00
---

Cantara 可以被容易地翻譯為其他語言。通過翻譯，您將可以向全世界推廣本程式，所以非英文、德文使用者也可以使用 Cantara。

## 如何翻譯

Cantara 使用將翻譯的語言字符串存儲在一種二進位語言的語言文件 （`*.mo`-文件）。 這種文件可以用如 [Poedit](https://poedit.net/) 編輯器經由臨時模板文件 [cantara.pot](https://github.com/reckel-jm/cantara/blob/master/locals/cantara.pot) 進行編輯。

如果您要將 Cantara 翻譯成新的語言，請按以下步驟進行：

1. 下載 [cantara.pot](https://github.com/reckel-jm/cantara/blob/master/locals/cantara.pot) 並使用合適的編輯器打開。
2. 將字符串翻譯成所需的目標語言。
3. 將翻譯後的內容導出為 `.mo`文件 **但請保留翻譯的 `.po` 文件！**
4. 複製 `language.mo` 文件至 `<cantara-dir>/languages/language/cantara.mo` （將 `language` 替換為目標語言的短代碼，如德文 *de*、英文 *en*、中文 *zh* 等）。
5. 以 `--lang` 啟動項運行 Cantara 以測試您的翻譯。

    `cantara --lang=<language code>` 


6. 若翻譯運行良好，請在 GitHub 上發起一個 Pull request，以便其他人也可以使用您的翻譯。

## 目前翻譯狀況

目前，Cantara 被翻譯為如下語言：

| 語言 | 完成度 |
|-----|--------|
| 英文 | 100 %        |
| 德文 | 100 %        |
| 中文 | 100 %        |
