---
title: "Hello Hugo （三） 發佈到GitHub Page"
date: 2019-10-02T15:30:31+08:00
draft: false
tags: ["hugo"]
---
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