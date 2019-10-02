---
title: "Hello Hugo （一） 環境建置"
date: 2019-10-01T00:01:29+08:00
draft: false
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