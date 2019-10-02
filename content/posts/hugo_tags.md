---
title: "Hello Hugo （四） 文章分類標籤"
date: 2019-10-02T15:34:25+08:00
draft: false
tags: ["hugo"]
---
### 

建立一篇新的 .md 檔案時，會自動帶入一些內容如下，其中 title 與 date 應該不難理解； draft 為註記是否為草稿，如為 true 則不會發佈。可能是我選擇的主題（hyde）不支援 tags 這種文章分類，因此在原本的樣板中沒有看到，所以就自己動手新增囉！

```md
title: "Hello Hugo （四） 文章分類標籤"
date: 2019-10-02T15:34:25+08:00
draft: false
tags: ["hugo"]
```

我預計在兩個地方新增標籤，一是文章的目錄頁，二是文章的內容頁（現在這頁），因此我們找到 layout 下尋找兩個檔案。

1. layout/index.html
2. layout/_default/single.html

分別在想要出現 tags 的地方插入下面這段程式碼，以我自己為例，就是文章標題與時間的下方。
```html
{{ with .Params.tags }}
  <ul class="tags">
    {{ range . }}
    <li> <a class="page-tag" href="{{ "tags" | absURL }}/{{ . | urlize }}">{{ . }}</a> </li>
    {{ end }}
  </ul>
{{ end }}
```
沒意外的話，應該會出現原始 html 中醜醜的清單，剩下就是樣式的事情了，同時為了方便以後修改，我在 static/css 下建立了我自己的 style.css ，並在 head.html 中匯入，比方說這樣。
```css
#tags {
  list-style: none;
  margin-left: 0;
  padding-left: 0;
  display: flex;
}

#tags .page-tag {
  display: inline-block;
  font-size: 14px;
  font-weight: 400;
  background-color:#9a9a9a;
  color: #fff;
  font-style: normal;
  margin-right: 4px;
  margin-left: 0px;
  padding: 2px 8px;
  border-radius: 4px;
  text-decoration: none;
  will-change: background-color;
  transition: background-color .3s
}

#tags .page-tag:hover {
  background-color: #ccc;
}
```