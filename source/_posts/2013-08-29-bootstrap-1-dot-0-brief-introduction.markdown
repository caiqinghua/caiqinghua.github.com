---
layout: post
title: "bootstrap 1.0 brief introduction"
date: 2013-08-29 00:43
comments: true
categories: 
---

## 前言
本文翻译twitter官网的Bootstrap介绍，英文原文链接：<https://dev.twitter.com/blog/bootstrap-twitter>
本文在translate.google.com的帮助下完成，纠正了google translate翻译不准确的地方和一些语法错误。

## 1. 发布

我们很高兴发布Bootstrap，Bootstrap是一款快速开发Web应用程序的前端工具包。Bootstrap是一系列CSS和HTML规范的集合(翻译为**规范**似乎不妥，期待读者反馈贴切的翻译)。它使用了一些最新的浏览器技术，在一个仅为6K的超级微小的gzip压缩文件中，为您提供时尚的排版，表单，按钮，表格，网格，导航和其他你需要的一切。 
下载地址：[从Github检出Bootstrap](https://github.com/twbs/bootstrap)。
**注意**：官方下载链接已经无效，Bootstrap开源项目已经由原来的地址转移到<https://github.com/twbs/bootstrap>

## 2. 简史

Twitter早期，工程师们使用他们熟悉的任何库，来满足前端需求。各个应用程序之间的不一致，难以扩展和维护他们。为解决这些挑战，在Twitter的第一个黑客周期间，我们快递启动了Bootstrap项目。在黑客周结束时，我们已经有了一个稳定的版本，工程师可以在整个公司使用这个版本。

在许多工程师的帮助和反馈下，Bootstrap获得了快速发展，不仅包括基本的风格，也有更加优雅和耐用的前端设计模式。此版本就是我们的第一个公开的1.0版本，并且我们开源了多个月艰苦工作完成的作品。

## 3. 为什么使用Bootstrap

Bootstrap的核心是CSS，它基于Less构建，Less是一个灵活CSS预处理器，相比普通的CSS，它更强大，更灵活。Less提供了一系列的功能，如嵌套声明，变量，混入，操作，和颜色函数。此外，通过Less编译完成后，Bootstrap是纯粹的CSS，由此我们获得了两个重要的好处：

首先，Bootstrap很容易实施，只要放到你的代码中即可。编译可以通过一个Javascript工具完成，它是一个非官方的Mac应用程序，或者，你也可以通过Node.js来编译Less，[从Less网站可以了解更多Less信息](http://lesscss.org)

其次，一旦编译完成，Bootstrap只包含CSS，这意味着有没有多余的图片，Flash，或Javascript。剩下的就是简单和更强大的CSS，来满足你Web开发的各种需求。

## 4. Bootstrap压缩文件包含些什么

当你仔细看Bootstrap时，你会注意到我们把开发文件分为了七个不同的文件：

1.reset.less
一个CSS复位功能文件，最初由埃里克迈耶的供我们使用和修改，用来删除不必要的元素
2.preboot.less
颜色变量和混入，给渐变，透明胶片，和过渡简化vendox前缀的CSS块一行代码
**注意**：未理解透彻，翻译不好。
3.scaffolding.less
样式生成网格系统，结构布局，和页面模板
4.type.less
标题，正文，列表，代码，和一个多功能和持久的排版系统
5.patterns.less
重复的界面元素，如导航，情态动词，popovers和提示，带你超越默认脚手架样式
6.forms.less
耐用的风格，各种输入类型，表单布局和控制状态。
7.tables.less
风格多样的表格数据显示方式
我们把CSS拆分为更好管理的块，这些块更易于组织和迭代。通过Less编译这些文件为一个文件，你最终只要包含一个CSS文件。

## 5. 它的工作原理

Bootstrap提供一个干净的和统一的解决方案，给开发者遇到最常见的，日常的界面任务。在Twitter，Bootstrap已迅速成为我们启动新的应用程序和网站的前端工具之一。对于许多独特的设计需求，它即好扩展，也足够灵活。

今天，你可以使用Bootstrap拼凑快速原型​​或指导执行更复杂的设计和较大的工程。换句话说，Bootstrap是一个非常简单的方式，以促进开发快速，干净和高度可用的应用程序。

我们期待着与开源社区合作，来使Bootstrap进化。

## 6. Bootstrap发展方向

我们要继续努力保持Bootstrap足够小，同时增加了它所涵盖的广度。一如以往，我们很想能收到你的反馈意见，并希望你觉得它有用。如果你想帮助Bootstrap变得更好，自由的在Github上fork Bootstrap，提交问题和观看Bootstrap的进展。


## english version

@mdo Mark Otto
Posted on Fri, 2011-08-19 11:19
We are happy to announce Bootstrap, a front-end toolkit for rapidly developing web applications. It is a collection of CSS and HTML conventions. It uses some of the latest browser techniques to provide you with stylish typography, forms, buttons, tables, grids, navigation and everything else you need in a super tiny (only 6k with gzip) resource. Check out Bootstrap on Github.

## A brief history

In the earlier days of Twitter, engineers used almost any library they were familiar with to meet front-end requirements. Inconsistencies among the individual applications made it difficult to scale and maintain them. Bootstrap began as an answer to these challenges and quickly accelerated during Twitter’s first Hackweek. By the end of Hackweek, we had reached a stable version that engineers could use across the company.

With the help and feedback of many engineers, Bootstrap has grown significantly to encompass not only basic styles, but more elegant and durable front-end design patterns. This release represents our first public 1.0 release and the open sourcing of many months of hard work.

## Why use Bootstrap

At its core, Bootstrap is just CSS, but it's built with Less, a flexible pre-processor that offers much more power and flexibility than regular CSS. With Less, we gain a range of features like nested declarations, variables, mixins, operations, and color functions. Additionally, since Bootstrap is purely CSS when compiled via Less, we gain two important benefits:

First, Bootstrap remains very easy to implement; just drop it in your code and go. Compiling Less can be accomplished via Javascript, an unofficial Mac application, or via Node.js (read more about this at http://lesscss.org).

Second, once complied, Bootstrap contains nothing but CSS, meaning there are no superfluous images, Flash, or Javascript. All that remains is simple and powerful CSS for your web development needs.

## What's inside

When you take a closer look at Bootstrap, you will notice we have separated the development files into seven distinct files:

reset.less A CSS reset originally made by Eric Meyer and modified for our use to remove unnecessary elements
preboot.less Color variables and mixins for things like gradients, transparencies, and transitions to simplify vendox-prefixed CSS blocks to one line of code each
scaffolding.less Basic and global styles for generating a grid system, structural layout, and page templates
type.less Headings, body text, lists, code, and more for a versatile and durable typography system
patterns.less Repeatable interface elements like navigation, modals, popovers, and tooltips to take you beyond the default scaffolding styles
forms.less Durable styles for various input types, form layouts, and control states.
tables.less Styles for tabular data in a number of varied displays
Since we opted to break our CSS into more manageable chunks for easy organization and iterations, compiling these files with Less means you end up with just one CSS file to include.

## Why it works

Bootstrap works by providing a clean and uniform solution to the most common, everyday interface tasks developers come across. At Twitter, Bootstrap has quickly become one of our many go-to front-end tools when starting new applications and sites. This is because while it is very extensive, it’s flexible enough to work for many unique design needs.

Today, you can use Bootstrap to throw together quick prototypes or guide the execution of more sophisticated designs and larger engineering efforts. In other words, Bootstrap is a very simple way to promote quick, clean and highly usable applications.

We look forward to working with the open source community to evolve Bootstrap.

## Where Bootstrap is heading

We want to keep working on slimming down Bootstrap’s already tiny footprint while also increasing the breadth of what it covers. As always, we’d love your feedback and hope you find it useful. If you'd like to help make Bootstrap better, feel free to fork it, file issues and watch its progress over on GitHub.