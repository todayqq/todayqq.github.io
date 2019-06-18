---
layout:     post                    # 使用的布局（不需要改）
title:      PDF、PPT、Excel、Word、视频等格式文件在线预览               # 标题 
subtitle:   PDF、PPT、Excel、Word、视频等格式文件在线预览
date:       2017-11-26              # 时间
author:     Angkee                      # 作者
header-img:    #这篇文章标题背景图片
catalog: true                       # 是否归档
tags:                               #标签
    - Git
---

> 最近项目中用到了文件在线预览功能，文件类型大概有图片、视频、PDF、PPT、Excel、Word 等等，总结梳理了一下，分享给大家。

### PDF 文件类型

1. [jquery.media.js](https://github.com/malsup/media)

在线文档：http://jquery.malsup.com/media/

2. [pdf.js](https://github.com/mozilla/pdf.js)

推荐使用 `jquery.media.js`，简单易用。

### PPT、Excel、Word文件类型

不需要使用任何第三家扩展，使用 Office 官方提供的 Office Web Viewer 即可. 

`https://view.officeapps.live.com/op/view.aspx?src={yourFileOnlinePath}`

### 视频

常见的视频格式有：mp4、flv、avi、mpge、3gp、h264 等等，这些格式的区别就不再赘述了。

而 H5 原生的的 `video` 元素支持三种视频格式 `Ogg`、`MPEG 4`、`WebM`，所以我们需要更强大、支持更多视频在线播放，第三方扩展库。

在这里推荐使用 B 站开源的视频播放插件 [flv](https://github.com/Bilibili/flv.js)，一个轻量级、纯 `JavaScript` 的视频播放插件。

> flv.js  An HTML5 Flash Video (FLV) Player written in pure JavaScript without Flash. LONG LIVE FLV!

支持的浏览器: Chrome, FireFox, Safari 10, IE11 and Edge.

### 图片

H5 的 `img` 标签足以支持 png、jpeg、jpg、gif 格式的图片，但是关于图片，我们都可以经常看到这样的功能，点击图片，弹出图片放大的模态窗口。

给大家推荐一个非常好用的插件，[Bootstrap Lightbox](http://ashleydw.github.io/lightbox/)

> A lightbox module for Bootstrap that supports images, YouTube videos, and galleries - built around Bootstrap's Modal plugin.
> lightbox 组件是构建于 Bootstrap's Modal 组件之上，支持图片、YouTube 视频以及画廊（幻灯片效果）。

如果你也有什么文件预览的奇淫巧技，来一起分享 
