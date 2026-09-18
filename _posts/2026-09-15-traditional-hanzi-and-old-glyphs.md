---
layout: post
title: 我的漢字審美事業：傳統字與舊字形
date: 2026-09-15 10:00:00-0700
description: 我爲甚麼堅持使用傳統漢字與舊字形，以及如何在 Linux、Android 和瀏覽器中實現它。
tags: hanzi typography linux android
categories: technology
---

我堅持使用傳統漢字，也偏愛舊字形。這不只是一種視覺趣味；字形背後保存着字與字之間的關係，也保存着漢字演變的脈絡。

## 爲甚麼使用傳統漢字？

我很認同人云E云列出的理由，也受到 BYVoid 相關文章的影響。簡單概括如下：

- 簡化字合併了不少本來不同的漢字，讓原有的區別消失。
- 漢字的長期發展並不只是把筆畫越減越少；爲了表意與區分，構成也會複雜化。
- 從篆書、隸書、楷書到宋體（明體），歷史上的字形變化往往是整體而有規律的；現代簡化則不是一套同樣完整的構形轉換。
- 簡化未必真正減少需要辨識的字量，異體與繁簡對照有時反而增加了學習負擔。
- 筆畫變少也不等於整個書寫系統的複雜度下降。

## 在 Linux 中使用舊字形

對我使用的 Linux 環境來說，一個直接的方法是調整 Fontconfig 的語言字體優先順序：

```bash
sudoedit /etc/fonts/conf.avail/64-language-selector-prefer.conf
```

在相應字形偏好中，將例如下面的韓文字體族放到第一行：

```xml
<family>Noto Serif CJK KR</family>
```

也可以按需要選擇 `Noto Sans CJK KR`。韓國印刷字形往往更接近我想要的舊字形效果。修改系統設定前最好先備份原文件；不同 Linux 發行版的 Fontconfig 路徑也可能不同。修改後如未立即生效，可以重建字體快取：

```bash
fc-cache -f
```

## 在瀏覽器中閱讀縱書

[竹取 JS](https://taketori.org/js.html) 提供了把網頁轉成縱書的書籤工具。遇到適合縱向閱讀的文章時，可以直接轉換頁面；配上明體，閱讀體驗很好。

## 在 Android 全系統使用舊字形

我也做了一個自己的實驗：[trad-glyph-pixel9a](https://github.com/Jiali-Xing/trad-glyph-pixel9a/tree/kr-index-hack)。它嘗試在 Android 手機上實現全系統舊字形，而不是只修改單一 App 的字體。

漢字審美事業大概不會畢業。畢竟每次系統更新，都可能帶來一輪新的字體調校。
