---
layout: post
title:  "如何优雅地配置Mac开发环境"
date:   2017-07-13 12:40:09 +0800
categories: tools
---

拿到新Mac机，要为程序开发来配置开发环境。这是个特殊的事，新手和老鸟感觉不同。新手不知道要做什么、怎么配置，什么都很困难、也很新鲜；老鸟轻车熟路，却觉得一步步操作很烦人。我看了[李笑来](http://lixiaolai.com/2016/06/16/makecs-basic-dev-env-settup/)、[nicolashery](https://github.com/nicolashery)、[donnemartin](https://github.com/donnemartin)三位前辈的配置说明，从新手的视角谈谈，怎么能把这事做得优雅。

## 有什么“不优雅”吗

给计算机安装软件工具包，这么简单的事情，还谈什么优雅？嗯，是的，因为我觉得自己之前做得不够优雅，表现如下：

### 不知轻重，闷头赶路

跟着全栈营公开课的指导，[安装Xcode](https://fullstack.xinshengdaxue.com/posts/8)，又[安装Command Line Tools](https://fullstack.xinshengdaxue.com/posts/9)，据说后者是Ruby的Library。

其实如果不是要开发Mac或iOS的app，没有必要安装几个G的Xcode（后续不时被App Store提示更新），可以只安装它下属的Command Line Tools就可以了。

全栈营的步骤冗余，说法有误。我不懂，也没查，听一家之言，给我我就抱着，先往前跑，赶路要紧。

### 不看文档，粗浅使用

全站营要求我们下载使用Atom，没有理由，就说新手推荐用Atom。我们的课程交流也都是Atom截屏。

李笑来老师没讲理由，但是给了以身作则的榜样。在编辑器部分，他让我们不要参与哪个编辑器最强的论战，不如节省时间和精力把能力练强。他建议我们在Atom体系下，做三件事：

1. 第一步读官方文档 [Atom Flight Manual](http://flight-manual.atom.io/) ，至少应该先认真阅读第一章。这是了解工具的能力。不至于把冲锋枪当做砍刀来用。
2. 上网搜Atom的[Cheatsheet](http://d2wy8f7a9ursnm.cloudfront.net/atom-editor-cheat-sheet.pdf)，好好读一读，或者打印出来。这里的半小时，省的是一辈子的时间。因为你也不知道跟这个工具要打多少交道，也许就是一辈子。
3. [积累自己的自动填充](http://lixiaolai.com/2016/06/17/makecs-atom-advanced/)Snippets集，为今后自己学习的每一种语言（Atom的Snippets有Scope功能），自己搜集和改造自动填充段子。这里强调“自己”，是因为只有知道“有”，才知道“用”啊。

你看，我没有耐心读官方文档，也没有好奇心去Google

> - Atom cheatsheet
> - favorite atom packages
> - most popular atom packages
> - must have packages for developer

更没有严肃认真地使用snippets功能。全栈营三个月来，敲html代码无数，都是`<%  %>`这么敲过来的。浪费这个时间是不是有必要？或者这个“笨功夫”，应该花在读文档上面？

### 有用没用，都想装装

前天为了建静态网页，需要安装jekyll。[Jekyll的官方安装指导](https://jekyllrb.com/docs/installation/)中说，前提要求是安装有GCC和Make。我就去找GCC来装。[GCC官网去看](https://gcc.gnu.org/install/)，字号好小，字数好多，怎么下载，怎么安装，老半天讲不到重点。第二天我还是下载到了，但是没有安装，因为没耐心了。我看[阮一峰大哥的建站指导](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html)，没有特别提到有“GCC这一难”呢。

果然不用装，也正常运行jekyll了。我真想骂人，官网随口一句话，给我这样的菜鸟挖大坑啊。

今天看到[nicolashery](https://github.com/nicolashery)、[donnemartin](https://github.com/donnemartin)二位的指导repo，一个娓娓道来，一个刷刷自动，让我佩服得五体投地，同时生发一种冲动：既然这么简单，不如把十八般武器都装到身上！多亏我有个毛病：看热闹行，执行力差，才没有让电脑和我自己都被拖累死。

## 什么是我心中的“优雅”做法

类比家里或办公室装修，在配置环境这件事上，我认为要把握三个问题：

1. 在这环境里做什么事？
2. 环境怎样和人互动？
3. 怎样良性发展，提升人与环境的和谐感？

具体落实到给Mac配置环境这件事情上，如果我拿到表弟的新电脑，我会做一下三件事：

1. 问他想开发什么东西，用什么语言？然后就只装现阶段必要的东西。
2. 给他看成熟程序员都做什么事情，用什么工具，让他自己读最常用工具的文档。
3. 为了做好事情，如何与工具相互磨合，给他一些建议。

上面三点，从空间方面看是留白，从感情方面看是尊重，从时间方面看是和谐。也许这就是我心中的“优雅”。

---

2017年7月13日，周四，19:32初稿。