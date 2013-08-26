---
layout: post
title: "在github pages上部署octopress搭建个人博客系统"
date: 2013-08-26 22:21
comments: true
categories: [tools, opensource]
tags: [octopress]
---

## 引子

上一篇博客已经说了为什么要搭建这个博客系统，本文不在啰嗦，单刀直入，说以下主题。
1. Octopress是什么
2. Github Page是什么
3. 部署Octopress到Github Pages的过程
4. 部署中遇到的问题

## 理解本文的基本知识

1. windows命令行基本使用方法（运行中输入cmd，输入enter)
2. git(学习资料: Pro Git 简体中文版，请自行google下载)
3. github(github.com)
4. ruby(本文只要会安装，会用几条命令即可)

## 什么是octopress?
自动化创建静态博客工具，包括一些模板和一些批处理工具。
用ruby和sass实现的，作者imathis也是compass的作者，compass是什么不是本文的关注点，请读者自行google了解。

## 什么是github pages? 
github静态页面，为项目做宣传主页之类的用处。

## 为什么部署到github pages?
github pages免费空间，免费流量，每次的博客改动和博客模板的改动都由git跟踪。没有理由不选择。

## step by step 部署Octopress到Github Pages

### 准备
系统：Windows 7

Git：[下载地址](http://msysgit.googlecode.com/files/Git-1.8.1.2-preview20130201.exe)

Ruby：[下载地址](http://rubyinstaller.org/news/2013/05/16/rubyinstaller-1-9-3-p429-released/)
**注意**: 部署octopress到github之前我已经安装过ruby on rails，所以我没有安装上面的ruby 1.9.3。
我安装是[railsinstaller-2.2.1](http://rubyforge.org/frs/download.php/76862/railsinstaller-2.2.1.exe)，详情请查看：<http://railsinstaller.org/en>
所以下面的安装过程出很多问题也许和此有关，所以还是建议直接安装ruby 1.9.3，不要安装railsinstaller。

DevKit：[下载地址](http://cloud.github.com/downloads/oneclick/rubyinstaller/DevKit-tdm-32-4.5.2-20111229-1559-sfx.exe)

Octopress：git://github.com/imathis/octopress.git

### 安装软件
安装Git
Windows下安装Git很简单，一路next就可以了。

安装Ruby
Ruby的安装也是一路next就可以，不过记得勾选“Add Ruby executables to your PATH”，将Ruby的执行路径加入到环境变量中，如果忘记勾选，也可以手动设置。安装完后可以在命令提示符中输入ruby –version 来确认是否安装成功。

安装DevKit
DevKit下载下来的是一个自压缩文件，我们将其解压到D:/DevKit，有两点需要注意：

1. 解压目录中没有有中文和空格；
2. 必须先安装Ruby，而且Ruby需要是RubyInstallser安装。

解压DevKit后，在命令行输入以下命令来进行安装：

```
cd /d D:\DevKit
ruby dk.rb init
ruby dk.rb install
```

### 用Git下载octopress源代码到本地
```
cd /d D:\ruby
git clone git://github.com/imathis/octopress.git octopress
```
下载完成后会在D:\ruby文件中生成octopress文件夹，下面的操作都是基于这个文件夹。

### 安装Octopress依赖项
```
cd octopress
gem install bundler
bundle install
```

### 安装octopress默认主题
```
cd octopress
$ rake install
```

###  创建第一篇博客
```
$ rake new_post["My first octopress blog"]
```

### 本地预览生成的博客系统和博客
```
$ rake preview
```
打开浏览器访问 http://localhost:4000/，你的第一篇博客将呈现在眼前。

以上已经把octopress博客系统和第一篇博客生成了，接下来要把生成的博客系统和博客部署到github pages。

### 创建git repository
<https://github.com/> Create a new repo
输入名称 username.github.com，注意username改为你的username，不能省略后面的github.com。
eg. caiqinghua.github.com

### 设置刚刚创建的repository路径到本地

```
$ rake setup_github_pages
Enter the read/write url for your repository
(For example, 'git@github.com:your_username/your_username.github.com)
Repository url: 
```

请输入：```git@github.com:yourname/yourname.github.com.git``` (将yourname替换成你的github登录名)

**注意**:这一步不要输入提示中提示的以io结束的地址。

### 设置SSH
设置步骤自行google解决
也可以不设置SSH,每次输入githib密码上传，请自行google解决

### 部署你的博客

```
rake generate
rake deploy
```
一面的deploy只是把_deploy目录上传到你的repo的master分支，即只是把生成的静态博客站点上传到github pages了。下面还需要把生成这个静态站点工具上传到repo的source分支

### 提交的source目录

```
cd /d D:\ruby\octopress
git add .
git commit -m "My octopress blog source code"
git push origin source
```

到github.com查看你上面新建的repository，会多一个source分支，记载所有的源文件。

### 安装过程中遇到的问题
1. bundle install 过程中Installing rdiscount (2.0.7.3) 安装失败

猜测原因：DevKit问题
把Ruby200中的DevKit删除，把path中c:\Ruby200\devkit 删除
重新执行bundle install
成功了

2. rake install 错误

```
d:\ruby\octopress>rake install
rake aborted!
You have already activated rake 10.1.0, but your Gemfile requires rake 0.9.2.2.
Using bundle exec may solve this.
```
解决办法：
修改octopress/Gemfiles
gem 'rake', '~> 0.9'
改为
gem 'rake'
再次rake install成功了

3. rake setup_github_pages 'hellip' 不是内部或外部命令

```
d:\ruby\octopress>rake setup_github_pages
Enter the read/write url for your repository
(For example, 'git@github.com:your_username/your_username.github.io)
           or 'https://github.com/your_username/your_username.github.io')
Repository url: git@github.com:caiqinghua/caiqinghua.github.io
Added remote git@github.com:caiqinghua/caiqinghua.github.io as origin
Set origin as default remote
Master branch renamed to 'source' for committing your blog source files
rm -rf _deploy
mkdir _deploy
cd _deploy
Initialized empty Git repository in d:/ruby/octopress/_deploy/.git/
'My Octopress Page is coming soon
'hellip' 不是内部或外部命令，也不是可运行的程序
或批处理文件。
[master (root-commit) 7e72dcf] Octopress init
1 file changed, 0 insertions(+), 0 deletions(-)
create mode 100644 index.html
cd -

---
## Now you can deploy to git@github.com:caiqinghua/caiqinghua.github.io with `ra
ke deploy` ##
```

google: 'hellip' 不是内部或外部命令，也不是可运行的程序
http://pythonee.github.io/blog/2012/08/10/how-to-octpress/
这个错误无关痛痒，无需解决。

4. rake deploy

```
## Pushing generated _deploy website
Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```
解决办法：设置ssh，前面已经提及

5. 再次rake deploy，发生以下错误

```
## Pushing generated _deploy website
Enter passphrase for key '/c/Users/Lin/.ssh/id_rsa':
ERROR: Repository not found.
fatal: Could not read from remote repository.
```
问题原因：rake setup_github_pages 中 git@github.com:caiqinghua/caiqinghua.github.io设置错误，应该设置为 git@github.com:caiqinghua/caiqinghua.github.com.git
解决办法：
查看octopress\_deploy\.git\config

发现url错误，修改后，重试，部署完成
```
[remote "origin"]
     url = git@github.com:caiqinghua/caiqinghua.github.io
```
修改为
```
[remote "origin"]
     url = git@github.com:caiqinghua/caiqinghua.github.com.git
```

**注意**: octopress\.git\config 中的url也生成错了。
```
[remote "origin"]
     url = git@github.com:caiqinghua/caiqinghua.github.io
```     
应该修改为
```
[remote "origin"]
     url = git@github.com:caiqinghua/caiqinghua.github.com.git
     fetch = +refs/heads/*:refs/remotes/origin/*
```
重新执行rake gen_deploy执行成功了

立即访问 caiqinghua.github.com，提示404 页面未找到错误
10分钟后访问，可以看到本地预览的博客了。
到此部署octopress到github pages总算完成了。

### 后记
octopress中用markdown格式撰写博文，关于markdown语法，如何撰写博客，如何个性化设置博客，且听下文分解。