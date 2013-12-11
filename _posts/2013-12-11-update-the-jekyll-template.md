---
layout: post
title: "update the jekyll template"
categories:
- 
tags:
- 


---
  原来的模板在本地试运行时，经常会出现一些不兼容中文的warning。而我对ruby又不熟悉，自己试着找了几次，也没有找到合适的解决方案，就也推迟了更新。

今天google到一个看起来比较清爽的blog[http://webfrogs.me/](http://webfrogs.me/)，而且里面还有一篇怎么clone他人blog的文章：[http://webfrogs.me/2012/12/20/use-jekyll/](http://webfrogs.me/2012/12/20/use-jekyll/)，于是按照做法把webfrogs的blog克隆下来，再把site name等个人信息换掉。本地再运行时果然没有了原来的错误，而且排版什么的看起来都比原来清新许多。Thanks to [webfrogs](http://webfrogs.me/).

USACO一直有在做，不过最近卡在了USACO上最杀脑细胞的一道题[Packing Rectangles](http://www.nocow.cn/index.php/Translate:USACO/packrec)。题目是IOI 95的一道题，相比前面思路直接，简单模拟即可搞定的题目，这道确实要难了许多。

不过征途不会停止。

---
12月11日更新：

本来9日就已经提交，但查看github的blog却没有任何更新。去rep上看，也发现内容已经更新了，orz。

后来才发现github会给注册邮箱发邮件通知build失败，并且会给出失败的详细信息。而我犯的错误则是在提交新模板的时候，把**CNAME**文件也一起提交上去。**CNAME** 文件的作用是指定url。如果两个人采用相同的**CNAME**文件，则会出现url冲突的问题。

于是直接在github的网页上，把**CNAME**文件删除，blog顿时清新了，:)。