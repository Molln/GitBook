# GitBook 配置

在生成的 SUMMARY.md 文件所在目录创建 book.json 文件，使用该文件配置 GitBook

* titile

  ````
  配置标题
  "title": "GitBook"
  ````

* author

  ````
  作者
  "author": "Molln"
  ````

* description  描述

  ````
  "description": "GitBook 快速入门"
  ````

* language

  ````
  语言，中文可设置为 `zh-hans，版本2.6.4中可选的语言如下：
  en, ar, bn, cs, de, en, es, fa, fi, fr, he, it, ja, ko, no, pl, pt, ro, ru, sv, uk, vi, zh-hans, zh-tw
  "language": "zh-hans"
  ````

* gitbook

  ````
  指定使用的 GitBook 版本
  ````

* styles

  ````
  自定义页面样式
  
  默认情况下各generator对应的css文件
  "styles": {
      "website": "styles/website.css",
      "ebook": "styles/ebook.css",
      "pdf": "styles/pdf.css",
      "mobi": "styles/mobi.css",
      "epub": "styles/epub.css"
  }
  
  例如使h1 h2标签有下划线， 可以在website.css中设置
  h1 , h2{
      border-bottom: 1px solid #EEEEEE;
  }
  ````

* structure

  ```
  指定 Readme、Summary、Glossary 和 Languages 对应的文件名
  ```

* links

  ````
  在左侧导航栏添加链接信息
  "links" : {
      "sidebar" : {
          "Personal Book" : "http://www.gtwteam.com"
      }
  }
  ````

* plugins

  ````
  配置使用的插件
  ````

* pluginsConfig

  ````
  配置插件的属性
  ````


在 GitBook 插件章节，将会对 GitBook 插件及使用做详细的介绍

