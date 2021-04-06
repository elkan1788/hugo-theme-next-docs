---
title: "快速开始"
description: "有关于快速体验 Hugo NexT 主题的步骤。"
date: 2021-03-30T08:13:25+08:00
enableToc: true
weight: 1
---

### 1. 安装 Hugo 环境

开始前您需要在本地环境中安装 `Hugo Extended` 版本，实际上 `Hugo` 的安装非常简单，只是配置个环境变量即可，不同操作系统环境的安装可参考官方文档[`Installing`](https://gohugo.io/getting-started/installing/) 。使用如下命令测试安装成功与否：

```bash

$ hugo env
Hugo Static Site Generator v0.80.0-792EF0F4 windows/amd64 BuildDate: 2020-12-31T
13:37:57Z
GOOS="windows"
GOARCH="amd64"
GOVERSION="go1.15.1"

# 或者

$ hugo version
Hugo Static Site Generator v0.80.0-792EF0F4 windows/amd64 BuildDate: 2020-12-31T
13:37:57Z

```

### 2. 创建站点

使用 `Hugo` 命令创建个空站点，会包含站点运行时所需要各文件夹（不建议进行调整），参考如下：

```

$ hugo new site myblog
Congratulations! Your new Hugo site is created in /myblog.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.

```

### 3. 添加 NexT 主题

您可以选择在Github站点直接下载[Release版本](https://github.com/elkan1788/hugo-theme-next/releases)，或是直接使用下面的`git clone`命令来下载：

```

$ cd myblog/

$ git init
Initialized empty Git repository in /myblog/.git/

$ git clone https://github.com/elkan1788/hugo-theme-next.git themes/hugo-theme-next
Cloning into 'themes/hugo-theme-next'...
remote: Enumerating objects: 1849, done.
remote: Counting objects: 100% (1849/1849), done.
remote: Compressing objects: 100% (729/729), done.
remote: Total 1849 (delta 948), reused 1694 (delta 794), pack-reused 0
Receiving objects: 100% (1849/1849), 992.47 KiB | 130.00 KiB/s, done.
Resolving deltas: 100% (948/948), done.

```

考虑到后续持续更新主题，建议还是使用 `git submodule` 功能会更加方便些。

```

$ git submodule add https://github.com/elkan1788/hugo-theme-next.git themes/hugo-theme-next
Adding existing repo at 'themes/hugo-theme-next' to the index

```

### 4. 运行示例

主题中默认自带有 `Hugo` 的官方示例语法测试站点，您也可以在本地启动及体能 `NexT` 主题的效果。

```

$ cd themes/hugo-theme-next/exampleSite/

$ hugo server -t ../..
Start building sites …

                   | ZH-CN | EN
-------------------+-------+-----
  Pages            |    35 | 34
  Paginator pages  |     0 |  0
  Non-page files   |     0 |  0
  Static files     |    26 | 26
  Processed images |     0 |  0
  Aliases          |    13 | 12
  Sitemaps         |     2 |  1
  Cleaned          |     0 |  0

Built in 297 ms
Watching for changes in /myblog/themes/hugo-theme-next/{archetype
s,exampleSite,i18n,layouts,static}
Watching for config changes in /myblog/themes/hugo-theme-next/exa
mpleSite/config/_default, /myblog/themes/hugo-theme-next/exampleS
ite/config/development
Environment: "development"
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableF
astRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop

```

### 5. 拷贝配置文件

本主题使用配置文件分类管理，共有4类的配置文件，如下：

- [config.toml]： `Hugo` 默认的配置文件
- [languages.toml]： 站点语言设置相关的配置
- [menu.[].toml]： 导航栏工菜单的相关配置
- [params.[].toml]： 站点参数的相关配置

更加具体的信息描述，可详见[配置文件信息](/docs/configuration/configfiles/)。

您可以直接将主题根目录下的 `config` 文件夹拷贝到您站点的根目录，并根据实际情况进行调整。

### 6. 发表文章

默认文章是创建在 `content\[]\post` 下面，文章头部请遵循如下的格式要求：

```
title: "文章标题描述"
url: "2021/04/05/first-article.html"
date: "2021-04-05T11:48:53+08:00"
categories:
 - "安装"
tags:
 - "安装"
toc: true
```


### 7. 启动站点

准备好文章后，便可以使用 `hugo server` 命令启动站点运行，并在本地浏览器预览效果。

### 8. 更新 NexT 主题

若您使用的是 `git submodule` 更新就会很便捷啦，只要使用如下的命令：

```

$ cd /myblog

$ git submodule update --remote --merge

```

其他方式安装本主题，那就需要手动操作对应的目录和文件进行替换。


