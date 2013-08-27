---
layout: post
title: "设置OCTOPRESS博客"
date: 2013-08-27 20:22
comments: true
categories: [tool]
tags: [config, octopress]
---
## 引言
可以登录<caiqinghua.github.com>查看设置效果
[查看本博客的配置文件](https://github.com/caiqinghua/caiqinghua.github.com/blob/source/_config.yml)

## 设置博客标题
打开octopress/_config.yml文件，设置如下内容。
url: http://caiqinghua.github.com *设置后没效果，还是会跳转到.io*
title: 分享控 *整个博客的标题，一般设置为xxx的个人博客*
subtitle: 分享让我们拥有更多 改进让我们效率更高 *副标题*
author: 蔡清华 caiqinghua@126.com *显示在页脚*
simple_search: http://google.com/search *默认搜索引擎*
description: 分享一切 share everything

## 设置首页
打开octopress/source/index.html文件，设置如下内容。
---
layout: default
description: "蔡清华的技术博客" 
keywords: web app, phone app, php, ruby, python, meteor, git, github, dos, bat, yii, ruby on rails, bootstrap, bsp(board support package), makefile, vxworks, linux, cooking
---

## 设置菜单栏
打开octopress\source\_includes\custom\navigation.html
按如下设置增加About Me菜单
<ul class="main-navigation">
  <li><a href="{{ root_url }}/">首页</a></li>
  <li><a href="{{ root_url }}/blog/archives">博客</a></li>
  <li><a href="{{ root_url }}/aboutme">About Me</a></li>
</ul>

## 设置不跳转
caiqinghua.github.com会自动跳转到caiqinghua.github.io
如何设置为不跳转，还木有找到答案。

## 设置侧边栏
### 增加新浪微博
### 添加豆瓣
### 添加标签云
### 添加其他个性化服务
侧边栏设置还未实践，等实践后补充。

## 增加页面
待补充