# NexT [![views](https://sourcegraph.com/api/repos/github.com/iissnan/hexo-theme-next/.counters/views.svg)](https://sourcegraph.com/github.com/iissnan/hexo-theme-next)

> NexT是一款高质量简洁的 [Hexo](http://hexo.io)主题，她经过精心雕琢而来。


[在线预览](http://notes.iissnan.com) |  [English Documentation](README.en.md)


## 预览

[桌面设备预览](screenshots/desktop.png)


![Mobile Preview](screenshots/mobile.png)


## 安装

1. 从`GitHub`下载

        $ cd your-hexo-site
        $ git clone https://github.com/iissnan/hexo-theme-next themes/next

2. 将`_config.yml`中的`theme`字段设置为`next`

        theme: next

## 更新

```
cd theme/next
git pull
```


## 特性

特性概览：

- 支持自定义LOGO以及主题图标
- 支持英语/简体中文双语
- 支持多说/DISQUS评论系统
- 支持标签云页面
- 支持RSS链接
- 支持about页面
- 支持5款代码高亮主题
- 支持[Google](www.google.com/analytics)/[百度统计](http://tongji.baidu.com/)
- 支持Google Webmaster tools
- 支持Creative Commons
- 支持指定站点建立时间

### 自定义LOGO以及主题图标

NexT使用[IcoMoon](http://icomoon.io)的服务为主题提供四套内建的图标。

借助于这个特性，你可以定制自己的`LOGO`以及主题的图标。自定义图标需要手工处理：

1. 在[IcoMoon](http://icomoon.io)挑选图标，并生成对应的字体文件。假设你的字体文件命名为`foo`。需要注意的是，生成字体的文件名`icomoon`不要更改。
2. 在`source/fonts/`目录下新建一个目录，名称以`icon-`开头加上`foo`，即`source/fonts/icon-foo`。
3. 在`source/css/_fonts/`目录下新建一个`styl`文件，名字为`icon-foo.styl`。将IcoMoon提供的样式文件迁移到这个`styl`文件中。请参看内置的文件。

    |class               | usage                |
    |:-------------------|:---------------------|
    |icon-logo           | 指定Logo图标          |
    |icon-home           | 指定菜单中Home链接图标  |
    |icon-archives       | 指定菜单中Archives链接图标    |
    |icon-tags           | 指定菜单中Tags链接图标    |
    |icon-feed           | 指定菜单中RSS链接图标   |
    |icon-about          | 指定菜单中About链接图标    |
    |icon-heart          | 指定菜单中底部心的图标      |
    |icon-external-link  | 指定菜单中外链的链接图标  |

4. 在主题中将`icon_font`设置为`foo`，即：

        icon_font: foo

完成。

### 英语/简体中文双语支持

> 默认语言是英文
> 编辑站点的`_config.yml`，将`language`字段更改为`zh-Hans`来启用中文

```
language: zh-Hans
```

### 多说/DISQUS评论系统支持

> 添加多说或者Disqus第三方评论系统。当同时设置了多说和Disqus时，优先选择多说。

使用多说

编辑**站点**的`_config.yml`，添加`duoshuo_shortname`字段，设置如下

```
duoshuo_shortname: your-duoshuo-shortname
```

使用[Disqus](https://disqus.com)

编辑**站点**的`_config.yml`，添加`duoshuo_shortname`字段，设置如下

```
disqus_shortname: your-disqus-shortname
```

### 标签云页面

> 添加一个标签云页面，并在菜单中显示标签云链接。

- 新建一个页面，命名为`tags`。命令如下：

        hexo new page "tags"

- 编辑刚新建的页面，将页面的类型设置为`tags`，主题将自动为这个页面显示标签云。

        title: All tags
        date: 2014-12-22 12:39:04
        type: "tags"

- 在菜单中添加链接。编辑主题的`_config.yml`，添加`tags`到`menu`中，如下:

        menu:
          home: /
          archives: /archives
          tags: /tags


### RSS链接

> 显示feed链接

打开主题的`_config.yml`中，将 `rss`字段设置为：

1. `rss: false`，这将会禁用Feed链接。
2. `rss:  `，当值为空的时候，默认会使用站点的Feed链接。在此之前需要使用[hexo-generator-feed](https://github.com/hexojs/hexo-generator-feed) 插件生成feed。

    依照`hexo-generator-feed`插件的安装说明进行feed生成，当配件配置完毕后，主题将自动显示feed链接。

3. `rss: http://your-feed-url`，指定特定的链接地址，适用于已经烧制过feed的情形。


### about页面

> 新建 about 页面

新建一个`about`页面：

```
hexo new page "about"
```

菜单显示`About`链接，在主题的`_configy.yml`设置中将`menu`中`about`前面的注释去掉即可。

```
menu:
  home: /
  archives: /archives
  tags: /tags
  about: /about
```

### 支持5款代码高亮主题

NexT 使用 [Tomorrow Theme](https://github.com/chriskempson/tomorrow-theme) 作为代码高亮，共有5款主题供你选择。
默认使用的是白色的`normal`，以下是`normal` 与 `night` 的预览：

![Tomorrow Normal Preview](screenshots/tomorrow-normal.png)
![Tomorrow Night Preview](screenshots/tomorrow-night.png)

请访问[Tomorrow Theme](https://github.com/chriskempson/tomorrow-theme)查看更多主题。


### 支持Google统计/百度统计

> 添加Google或者百度的统计ID即可开启网站统计

编辑**站点**的`_config.yml`，新增字段`google_analytics`或者`baidu_analytics`（取决于使用的统计系统）

```
google_analytics: your-analytics-id

baidu_analytics: your-analytics-id

```

### 支持Google Webmaster tools

> 设置[Google站点管理工具](https://www.google.com/webmasters/tools/)的验证字符串，用于提交sitemap

编辑**站点**的`_config.yml`，新增字段`google_site_verification`

```
google_site_verification: your-verification-meta
```

### 支持Creative Commons

> 设置站点的[Creative commons协议](http://creativecommons.org/)

编辑**站点**的`_config.yml`，新增字段`creative_commons`。
可选的值有： `by | by-nc | by-nc-nd | by-nc-sa | by-nd | by-sa | zero`

```
creative_commons: by-nc-sa
```

### 支持指定站点建立时间

> 这个时间将在站点的底部显示，例如 `© 2013 - 2015`

编辑**站点**的`_config.yml`，新增字段`since`。

```
since: 2013
```

## 主题配置

> NexT 坚持将复杂的细节隐藏，提供尽量少并且简便的设置，保持最大限度的易用性。

```
# 菜单配置
menu:
  home: /
  archives: /archives
  tags: /tags
  #about: /about

# Favicon
# 从`Next 0.2`起，favicon将不再放置于主题之内。
# 请将你的favicon放置在`hexo-site/source/`目录下。
favicon: /favicon.ico

# 设置为`false`不显示`rss`链接
# 留空，并且通过`hexo-site-feed`插件配置使用默认的feed
# 设置成特定的`url`，适用于通过第三方服务定制feed的情况。
rss: false


# 图标字体
# NexT内建四种图标: default | linecons | fifty-shades | feather
icon_font: default
#icon_font: fifty-shades
#icon_font: feather
#icon_font: linecons


# 代码高亮主题
# available: normal | night | night eighties | night blue | night bright
highlight_theme: normal
```

## 浏览器支持

![Browser support](screenshots/browser-support.png)


## 贡献

接受各种形式的贡献，包括不限于提交问题与需求，修复代码。等待您的`PR`。


## 开发

> NexT is built for easily use with elegant appearance.

First things first, always keep things simple.

## TODO

- [x] Using Swig instead of jade.
- [x] Using SCSS instead of stylus (depends?).
- [x] Rewrite link post related stuffs (Breaking changes).
- [x] Redesign pagination for mobile devices.
- [x] Support category.(Won't support).
- [x] Support gallery posts.
- [x] Make PAJAX and NProgress as optional. (Removed, conflicts with fancybox)
- [x] Add a feed link.
- [x] Refactor.
- [x] i18n.
- [x] How to use this theme.
- [x] Publish as a bower package.
- [ ] Home page.
- [ ] HTML5 Please
- [ ] Add [typicons.font](https://github.com/stephenhutchings/typicons.font).
- [x] Disuqus support.
- [ ] TIT - Theme in theme.
- [ ] Motion design.
- [ ] Expandable information area.
- [ ] New Gallery design.
- [x] Add Google site verification meta.
- [x] Add Google/Baidu analytics.


[![hexo-image]][hexo-url]
[![bower-image]][bower-url]
[![jquery-image]][jquery-url]

[hexo-image]: http://img.shields.io/badge/Hexo-2.4+-2BAF2B.svg?style=flat-square
[hexo-url]: http://hexo.io
[bower-image]: http://img.shields.io/badge/Bower-*-2BAF2B.svg?style=flat-square
[bower-url]: http://bower.io
[jquery-image]: https://img.shields.io/badge/jquery-1.9-blue.svg?style=flat-square
[jquery-url]: http://jquery.com/
