# GitBook 使用教程


> 想趴几本金庸小说的做成电子书自己阅读，在博客上尝试了一下整理了 6 本中短篇小说就开始感觉博客臃肿，于是找到 gitbook 前来一试。
写完这篇文章开始实际操作，我发现还不如用 hexo 来写小说，遂放弃！Gitbook 用来写相关文档介绍还差不多。

<!--more-->

# GitBook 简介
- [GitBook 官网](https://www.gitbook.com)
- [GitBook 文档](https://github.com/GitbookIO/gitbook)

> Gitbook 的作用和 Hexo 有点像，也是把 md 渲染成 html, 也见到有人用这个来写博客的。  
GitBook 是一个基于 Node.js 的命令行工具，可使用 Github/Git 和 Markdown 来制作精美的电子书，GitBook 并非关于 Git 的教程。  
GitBook 支持输出多种文档格式：  
- 静态站点：GitBook 默认输出该种格式，生成的静态站点可直接托管搭载 Github Pages 服务上；
- PDF：需要安装 gitbook-pdf 依赖；
- eBook：需要安装 ebook-convert；
- 单 HTML 网页：支持将内容输出为单页的 HTML，不过一般用在将电子书格式转换为 PDF 或 eBook 的中间过程；
- JSON：一般用于电子书的调试或元数据提取。
使用 GitBook 制作电子书，必备两个文件：`README.md`和`SUMMARY.md`

# GitBook 安装步骤
## 安装 node.js
GitBook 是一个基于 Node.js 的命令行工具，下载安装 [Node.js](https://nodejs.org)（我以前搭建 hexo 的文章里也有介绍），安装完成之后，你可以使用下面的命令来检验是否安装成功。
```bash
node -v
```

## 安装 GitBook
```bash
npm install gitbook-cli -g
```
检验是否安装成功
```bash
gitbook -V
```

[参照 GitBook 安装文档](https://github.com/GitbookIO/gitbook/blob/master/docs/setup.md)

## gitbook 初始化
和`hexo init`类似，GitBook 准备工作做好之后，我们进入一个你要写书的目录（比如新建 mybook 文件夹），输入如下命令初始化
```bash
gitbook init
```
初始化后可以看到他会创建`README.md`和`SUMMARY.md`  这两个文件，README.md 应该不陌生，就是说明文档，而 SUMMARY.md 其实就是书的章节目录，其默认内容如下所示：
```
# Summary

* [Introduction](README.md)
```

## 启动服务器
和`hexo serve`类似，我们使用`gitbook serve`命令，然后在浏览器地址栏中输入侧 http://localhost:4000 便可预览书籍。  
运行该命令后会在书籍的文件夹中生成一个_book 文件夹，里面的内容即为生成的 html 文件。  
也可以修改端口 
```bash
gitbook serve --port 5000
```
![](images/1.png)

我们可以使用`gitbook build`命令来生成网页而不开启服务器。这个类似于 hexo 的`hexo g`命令。  
当然，build 命令可以指定路径：
```bash
gitbook build [书籍路径] [输出路径]
```
你还可以生成 PDF,epub,mobi 格式的电子书：
```bash
gitbook pdf ./ ./mybook.pdf
gitbook epub ./ ./mybook.epub
gitbook mobi ./ ./mybook.mobi
```
如果生成不了，你可能还需要安装一些工具，比如 ebook-convert。或者在 Typora 中安装 Pandoc 进行导出。

# 目录结构
```
.
├── book.json
├── README.md
├── SUMMARY.md
├── chapter-1/
|   ├── README.md
|   └── something.md
└── chapter-2/
    ├── README.md
    └── something.md
```
## book.json
该文件主要用来存放配置信息。

## SUMMARY.md
这个文件主要决定 GitBook 的章节目录，它通过 Markdown 中的列表语法来表示文件的父子关系。

## 更多
[更多详情介绍](https://www.jianshu.com/p/421cc442f06c)
