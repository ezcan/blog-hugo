---
title: "Hello Hugo （二）語法高亮度"
date: 2019-10-02T15:26:33+08:00
draft: false
tags: ["hugo"]
---
### 語法高亮度

由於這裡打算筆記自己以後的開發上的學習經驗為主，所以裝個語法高亮度外掛是必須的，我選用的是 browser 渲染的解決方案。

1. 引入 highlight.js 的 css ，[這裡](https://highlightjs.org/static/demo/)可以預覽
2. 引入 highlight.js CDN，目前最新版本為9.15.10
3. 載入 js

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.15.10/styles/monokai-sublime.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.15.10/highlight.min.js"></script>
<script>hljs.initHighlightingOnLoad();</script>
```