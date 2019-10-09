---
title: "Hello Hugo （五） 導入 Google Analytics"
date: 2019-10-03T00:52:31+08:00
draft: false
tags: ["hugo"]
---
寫這篇文章前我其實還沒有深入了解過 Google Analytics (GA)，不過大抵知道有以下兩個優點：

1. 了解使用者（如何進入你的網站、可能的背景）
2. 觀察使用者進入網站後的行為

雖然不知道上述資訊對這種筆記部落格有什麼幫助，反正 GA 基本版是完全免費的，在 hugo 上設定也只要兩、三個步驟就好，順手開始囉！

1. 第一個步驟當然是到 [Google Analytics](https://analytics.google.com/analytics/web/) 去建立一個專案，並且複製它的應用程式 ID ，可能長得是這個樣子： UA-xxxxxxx-1
2. 回到專案的 config.toml ，加入步驟1. 拿到的 ID
```
googleAnalytics = "UA-xxxxxxx-1" 
```
3. 在 layouts/partials/head.html 中加入以下程式碼。
```html
{{ if not .Site.IsServer }}
  {{ template "_internal/google_analytics_async.html" . }}
{{ end }}
```

簡單補充一下，其實導入 GA 只要上述中間那行程式碼就可以了，只是這樣會不分青紅皂白的連本地預覽資料都往 server 送，以上。