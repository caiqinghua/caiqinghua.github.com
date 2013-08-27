---
layout: post
title: "how to write and post octopress blog to github pages"
date: 2013-08-27 20:56
comments: true
categories: [tool]
tags: [octopress]
---

## New post
```
rake new_post["how to write and post octopress blog to github pages"]
```
It will generate a post file. \octopress\source\_posts\2013-08-27-how-to-write-and-post-octopress-blog-to-github-pages.markdown

## Edit the post file

1. use a text edit tool open the markdown file: \octopress\source\_posts\2013-08-27-how-to-write-and-post-octopress-blog-to-github-pages.markdown.
I recommend using the Sublime Text. I like it. I think you will like it.
2. edit it by markdown syntax.
3. [Open the markdown file of this blog,](https://github.com/caiqinghua/caiqinghua.github.com/tree/source/source\_posts\2013-08-27-how-to-write-and-post-octopress-blog-to-github-pages.markdown), you will know the markdown syntax.
4. For more infomation
Markdown is available at http://daringfireball.net/projects/markdown/
and [there is a simple markdown syntax in the wenku.baidu.com](http://wenku.baidu.com/view/5e737dec102de2bd96058843.html)

## Preview your blog in local
```
rake generate
rake preview
```
navigate to http://localhost:4000/

## Send the post to github pages
```
rake gen_deploy
```

you can also use the following cmd.
```
rake generate
rake deploy
```
