---
title: 使用PicGo和GitHub搭建个人图床
date: 2019-05-03 21:50:00
tags: Hexo博客
category: 使用技巧总结记录
toc_number: false
---



> 一直苦于一些图片没地方保存，如果图片能够上传到一个地方而且能够直接通过地址访问就好了。无意间在GitHub上看到有人利用GitHub做图层，于是就有了试一试的想法。最终利用PicGo和GitHub成功搭建个人图床

<!--more-->

## 1.GitHub仓库设置

### 1-1.新建仓库

仓库选择public

![](https://raw.githubusercontent.com/hyman213/FigureBed/master/2019/20190501225624.png)

### 1-2.创建token



token用于后面PicGo操作Github仓库。

访问[https://github.com/settings/tokens](https://github.com/settings/tokens) 或者个人头像/Settings/Developer settings/Personal access tokens

![](https://raw.githubusercontent.com/hyman213/FigureBed/master/2019/20190501225737.png)

把repo的勾打上即可。然后翻到页面最底部，点击`Generate token`的绿色按钮生成token。

![](https://raw.githubusercontent.com/hyman213/FigureBed/master/2019/20190501225802.png)

**注意：**这个token生成后只会显示一次！你要把这个token复制一下存到其他地方以备以后要用。

## 2.PicGo

PicGo是一款免费开源的图片上传和管理工具。

[官方网站https://molunerfinn.com/PicGo/](https://molunerfinn.com/PicGo/)

### 2-1.PicGo应用说明

PicGo在上传图片之后自动会将图片链接复制到你的剪贴板里，可选5种复制的链接格式。

PicGo目前支持了,目前最新版本为2.1.0

- 微博图床 v1.0
- 七牛图床 v1.0
- 腾讯云COS v4\v5版本 v1.1 & v1.5.0
- 又拍云 v1.2.0
- GitHub v1.5.0
- SM.MS v1.5.1
- 阿里云OSS v1.6.0
- Imgur v1.6.0

### 2-2.下载安装PicGo

按照PicGo官网[文档说明](https://picgo.github.io/PicGo-Doc/zh/guide/#%E4%B8%8B%E8%BD%BD%E5%AE%89%E8%A3%85)下载安装PicGo

macOS用户请下载最新版本的`dmg`文件，windows用户请下载最新版本的`exe`文件，linux用户请下载`AppImage`文件。



### 2-3. 快速上手

- Mini窗口上传

![](https://raw.githubusercontent.com/hyman213/FigureBed/master/2019/20190501221954.png)

1)直接拖拽图片到mini窗口上传

2)将图片复制到剪贴板，然后右键mini窗口，选择剪贴板上传

- 主窗口上传

### 2-4.配置说明

PicGo配置文件在不同系统里是不一样的

- Windows：`%APPDATA%\picgo\data.json`
- Linux: `$XDG_CONFIG_HOME/picgo/data.json` or `~/.config/picgo/data.json`
- macOS:` ~/Library/Application\ Support/picgo/data.json`

我的配置文件是在C:\Users\idobe\AppData\Roaming\PicGo\data.json

默认配置如下,

```json
{
  "uploaded": [],
  "picBed": {
    "current": "weibo"
  },
  "settings": {
    "shortKey": {
      "upload": "CommandOrControl+Shift+P"
    },
    "showUpdateTip": true
  },
  "needReload": false,
  "picgoPlugins": {}
}
```

在PicGo界面还可以有多种个性化设置，我在这里设置了时间戳重命名，上传的图片会自动按时间戳重命名后上传。

![](https://raw.githubusercontent.com/hyman213/FigureBed/master/2019/20190501223804.png)

### 2-5. 配置GitHub图床

![](https://raw.githubusercontent.com/hyman213/FigureBed/master/2019/20190501222516.jpg)

仓库名：格式-用户名/仓库

分支名：master

Token：GitHub 生成的Token

指定储存路径：注意格式**2019/**，不要写成**/2019/**。仓库下的路径名,注意GitHub上该目录必须存在

自定义域名不用设置。



至此，使用PicGo和GitHub创建个人图床已经完成。可以愉快的上传图片了。

参考：

1.https://github.com/nnngu/FigureBed

2.https://blog.csdn.net/yefcion/article/details/88412025

3.另外一款图床工具感觉也不错。https://github.com/xiebruce/PicUploader



