# GitBook 使用

## 一 创建 Book

cmd 进入需要写作的目录，执行下列命令

````
gitbook init
````

此时会生成如下两个文件

* README.md        说明文档

* SUMMARY.md      章节目录

## 二 本地预览

````
gitbook serve
````

成功执行后，浏览器访问下方链接即可预览

<http://localhost:4000>

## 三 生成静态站点

````
gitbook build
````

运行该命令后会在文件夹种生成一个 _book 文件夹，该文件夹存放生成的 html 页面