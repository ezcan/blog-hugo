---
title: "Hello Hugo"
date: 2019-10-01T00:01:29+08:00
draft: false
description: "本文記錄了這個部落格的建置過程包括，環境建置、語法亮度與上傳到Github Page"
tags: ["hugo"]
---
基於某些因素，決定來寫個部落格；又考慮了幾個選項與方案，包含wordpress、medium等；最後選定了靜態html產生器，與號稱兩分鐘就上手的hugo這個工具，並順手將建置的過程筆記起來。

### 兩分鐘體驗
1. 第一步是安裝homebrew（我原本就用mac開發，所以這就略過了）
2. 再來安裝hugo
```
brew install hugo
```
3. 建立一個新的網站
```
hugo new site blog
```
產生的專案架構如下
```
# <project-name> file structure
|- archetypes
|- content
|- data
|- layouts
|- resources
|- static
|- themes
|- config.toml
```

4. 進入themes目錄，並從[hugo theme](https://themes.gohugo.io)中選一套佈景來套用
```
cd blog/themes
git clone https://github.com/spf13/hyde.git
cd ..
```
5. 然後就可以打開慣用的編輯器了，我原先以為專案直接跑會有預設畫面，但並沒有，開起來是全白的畫面XD
```
# config.toml
baseURL = "http://ezcan.github.io/" 
languageCode = "zh_TW"
title = "ezcan's note"

# 記得要在 config.toml 指定對應的主題
theme = "Hyde"
```
6. 新增一篇文章，就是你現在看到的這篇
```
hugo new posts/hello_hugo
```
7. 本機瀏覽一下，兩分鐘到這邊完成。
```
hugo server -D
```

### 語法高亮度

由於這裡打算筆記自己以後的開發上的學習經驗為主，所以裝個語法高亮度外掛是必須的，我選用的是 browser 渲染的解決方案。

1. 引入 highlight.js 的 css ，[這裡](https://highlightjs.org/static/demo/)可以預覽
2. 引入 highlight.js CDN，目前最新版本為9.15.10
3. 載入 js
```html
# themes/hyde/layout/partials/head.html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.15.10/styles/monokai-sublime.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.15.10/highlight.min.js"></script>
<script>hljs.initHighlightingOnLoad();</script>
```

### 上傳到Github
空間的部分，我打算上傳到 github page 個人主頁，所以...

1. 自動建立 public 資料夾
```
hugo
```
2. 在 /public 中初始化 git
```
cd public
git init
git commit -m "first commit"
git remote add origin https://github.com/ezcan/ezcan.github.io.git
git push -u origin master
```