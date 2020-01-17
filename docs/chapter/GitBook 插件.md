# GitBook 插件

## 一 默认插件

GitBook 默认带有 5 个插件

````
highlight	 代码高亮
search	   导航栏查询功能
sharing	  右上角分享功能
font-settings  字体设置（最上方的"A"符号）
livereload      为GitBook实时重新加载
````

如果要去除自带的插件， 可以在插件名称前面加 `-`，比如：

````
"plugins": [
    "-search"
]
````

## 二 如何添加插件

在book.json中配置如下（这里用code插件作为例子）

````
{
    "plugins": [
        "code"
    ],
    "pluginsConfig": {
        "code": {
            "copyButtons": false
        }
    }
}
````

然后通过以下三种方式中的一种进行安装

* 执行`gitbook install`

* 使用npm安装，命令格式`npm install gitbook-plugin-插件名字`，如`npm install gitbook-plugin-code`

* 从GitHub下载源码，放到node_modules文件夹里。

安装是可以指定版本，如：`plugin@0.1.1`。有些插件可能很久没升级，不会随着GitBook版本升级，所以使用插件未生效或报错时要注意GitBook版本。

## 三 插件示例

下面列举部分 GitBook V3.2.3 可用插件

### 1 back-to-top-button

功能描述：返回顶部

引入插件：

````
{
    "plugins": [
        "back-to-top-button"
    ]
}
````

### 2 code

功能描述：代码添加行号&复制按钮

引入插件：

````
{
    "plugins": [
        "code"
    ]
}
````

插件配置：

````
{
    "pluginsConfig": {
        "code": {
            "copyButtons": false	# 去掉复制按钮
        }
    }
}
````

### 3 search-pro

功能描述：高级搜索，支持中文

引入插件：

````
{
    "plugins": [
        "search-pro"
    ]
}
````

### 4 github

功能描述：在右上角添加github图标

引入插件：

````
{
    "plugins": [
        "github"
    ]
}
````

插件配置：

```
{
    "pluginsConfig": {
        "github": {
            "url": "https://github.com/lijiam"	# 设置GitHub地址
        }
    }
}
```

### 5 splitter

功能描述：侧边栏宽度可调节

引入插件：

````
{
    "plugins": [
        "splitter"
    ]
}
````

### 6 tbfed-pagefooter

功能描述：页面添加页脚，简单格式

引入插件：

````
{
    "plugins": [
        "tbfed-pagefooter"
    ]
}
````

插件配置：

````
{
    "pluginsConfig": {
        "tbfed-pagefooter": {
            "copyright":"Copyright &copy lijiam 2019",
            "modify_label": "本书发布时间：",
            "modify_format": "YYYY-MM-DD HH:mm:ss"
        }
    }
}
````

### 7 page-copyright

功能描述：页面页脚版权，复杂的

引入插件：

````
{
    "plugins": [
        "page-copyright"
    ]
}
````

插件配置：

````
{
    "pluginsConfig": {
        "page-copyright": {
          "description": "modified at",
          "signature": "你的签名",
          "wisdom": "Designer, Frontend Developer & overall web enthusiast",
          "format": "YYYY-MM-dd hh:mm:ss",
          "copyright": "Copyright &#169; 你的名字",
          "timeColor": "#666",
          "copyrightColor": "#666",
          "utcOffset": "8",
          "style": "normal",
          "noPowered": false,
     }
}
````

### 8 donate

功能描述：打赏插件

引入插件：

````
{
    "plugins": [
        "donate"
    ]
}
````

插件配置：

````
{
    "pluginsConfig": {
        "donate": {
            "wechat": "微信收款的二维码URL",
            "alipay": "支付宝收款的二维码URL",
            "title": "",
            "button": "赏",
            "alipayText": "支付宝打赏",
            "wechatText": "微信打赏"
        }
    }
}
````

### 9 sharing-plus

功能描述：分享当前页面，比默认的 sharing 插件多了一些分享方式。

引入插件：

````
{
    "plugins": [
        "sharing-plus"
    ]
}
````

插件配置：

````
{
    "plugins": ["-sharing", "sharing-plus"],
    "pluginsConfig": {
        "sharing": {
            "facebook": true,
            "twitter": true,
            "weibo": true,
            "qq": true,
        "all": [
            "douban", "google", "instapaper", "linkedin", "twitter", "messenger", "qzone", "viber", "whatsapp"
           ]
       }
    }
}
````

其中：为true的代表直接显示在页面顶端，为false的不显示，不写默认为false，"all"中代表点击分享符号显示出来的，支持网站：

````
    "douban", "facebook", "google", "hatenaBookmark", 
    "instapaper", "linkedin","twitter", "weibo", 
    "messenger","qq", "qzone","viber","vk","weibo",
    "pocket", "stumbleupon","whatsapp"
````

### 10 custom-favicon

功能描述：修改标题栏图标

引入插件：

````
{
    "plugins": [
        "sharing-plus"
    ]
}
````

插件配置：

````
{
    "pluginsConfig": {
        "favicon": "images/favicon.ico"
    }
}
````

### 11 prism

功能描述：代码高亮

引入插件：

````
{
    "plugins": [
        "prism", 
        "-highlight"
    ]
}
````

插件配置：

````
{
    "pluginsConfig": {
        "prism": {
            "css": [
                "prismjs/themes/prism-okaidia.css"
            ],
            "lang": {
                "flow": "typescript"
            }
        }
    }
}

````

### 12 todo

功能描述：代复选框

引入插件：

````
{
    "plugins": [
        "todo"
    ]
}
````

使用示例：

````
* [ ] 这是一个未选中的
* [x] 这是一个已选中的
````

### 13 pageview-count

功能描述：阅读量计数

引入插件：

````
{
    "plugins": [
        "pageview-count"
    ]
}
````

这里可能需要改下源代码，在`node_modules`中找到`gitbook-plugin-pageview-count`插件，然后找到`assets`下的`plugins.js`，按照下面的改法调整代码

````
// 未调整前
var fontSize = bookHeader.find('.dropdown');
// 调整后
var fontSize = bookHeader.find('.font-settings');

````

### 14 auto-scroll-table

功能描述：表格滚动条，为避免表格过宽，增加滚动条。

引入插件：

````
{
    "plugins": [
        "auto-scroll-table"
    ]
}
````

### 15 image-captions

功能描述：显示图片名称，抓取内容中图片的 alt 或 title 属性，在图片下面显示标题。

引入插件：

````
{
    "plugins": [
        "image-captions"
    ]
}
````

插件配置：

````
{
    "pluginsConfig": {
        "image-captions": {
          "caption": "Image _PAGE_LEVEL_._PAGE_IMAGE_NUMBER_ - _CAPTION_"
      }
    }
}

````

### 16 styles-sass

功能描述：使用sass替换css

引入插件：

````
{
    "plugins": ["styles-sass"],
    "styles": {
        "pdf": "styles/pdf.sass"
    }
}

````

### 17 styles-less

功能描述：使用less替换css

引入插件：

````
{
    "plugins": ["styles-less"],
    "styles": {
        "pdf": "styles/pdf.less"
    }
}

````

### 18 toggle-chapters

功能描述：目录折叠

引入插件：

````
{
    "plugins": [
    	"toggle-chapters"
    ]
}
````

### 19 multipart

功能描述：分章节展示

引入插件：

````
{
    "plugins": [
    	"multipart"
    ]
}
````

`SUMMARY.md`例子：

````
# GitBook

## 第一章
* [第一节](part1/1/README.md)
    * [1.1](part1/1.1/README.md)
* [第二节](part1/2/README.md)
* [第三节](part1/3/README.md)

## 第二章
* [第一节](part2/1/README.md)

## 第三章

````

### 20 其他

功能描述：设置导航序号

配置示例：

````
{
    "pluginsConfig": {
        "theme-default": {
            "showLevel": true
        }
    }
}
````

