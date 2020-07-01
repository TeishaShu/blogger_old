---
title: Hexo 建立部落格 - NexT 美化
tags:
  - Hexo
  - blog
categories: Hexo
date: 2020-07-01 16:21:43
---

### 文章日期自己設定
原本日期是顯示檔案生成的時間，可以改成自己寫好的日期。

1. 文章的檔名前面加上日期
ex: 2020-01-01-oneBlog.md
<!--more-->
2. 在 _config.yml 檔案的 #Writing 下面的 # new_post_name: :title.md 改成
```
new_post_name: :year-:month-:day-:title.md
```

### 自定義 css
1. 在 themes/next/source/css 中建立 _mycss.styl 檔案放自己想要新增的。
2. 引入檔案，在 main.styl 中的最後加上下面程式碼。
```
@import "_mycss.styl";
```

### 大頭照設定
找到這個檔案 themes/next/source/images/avatar.gif
把自己的大頭蓋過去.可以改副檔名

到主題下的 _config.yml 改路徑
```
avatar:
  url: /images/avatar.jpg
```

### 推薦插件
#### 搜尋 search
1. 直接在終端機打下面的指令安裝
```
npm install hexo-generator-search --save
```

2. 在主題下的 _config.yml 中.下面 enable: false 改 true
```
local_search:
    enable: true
```

#### 留言板 disqus
照下面這安裝就可以呈現.只是不能在首頁看有沒有效果
[Hexo添加Disqus评论](https://www.jianshu.com/p/d68de067ea74)

#### sitemap
[hexo-generator-sitemap](https://github.com/hexojs/hexo-generator-sitemap)

### 推薦的網站
[Hexo-NexT 主题个性优化](https://guanqr.com/tech/website/hexo-theme-next-customization/)