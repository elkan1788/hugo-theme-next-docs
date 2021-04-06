---
title: "配置文件信息"
description: "NexT 主题的所有配置文件信息。"
date: 2021-03-30T08:20:15+08:00
enableToc: true
weight: 1
---

### 配置文件目录结构{#file-folder-struct}

参考 `Hugo` 的配置文件写法，并考虑到后期的相关扩展，本主题的配置信息并没有采用汇集到 `config.toml` 单一文件做法，而是使用根据配置文件分类管理的方式，所以请确保在您的站点有如下类似结构的配置文件目录，否则本主题将无法运行。 

```
├── config
│   ├── _default
│   │   ├── config.toml
│   │   ├── languages.toml
│   │   ├── menus.en.toml
│   │   ├── menus.zh-CN.toml
│   │   ├── params.en.toml
│   │   ├── params.toml
│   │   ├── params.zh-CN.toml

```

{{< alert theme="info" dir="ltr" >}}

另外在本地开发（写文章）过程中，为了便于调试或是保证一些账户信息不泄漏，可以在 `config` 目录下创建个 `development` 文件夹使用与 `_default` 文件下同名的配置文件来覆盖默认的配置信息。 比如：

```
├── config
│   ├── development
│   │   ├── config.toml
│   │   ├── params.toml
```

{{< /alert >}}

各个配置文件的具体内容概览如下：

### config.toml{#config-toml}

`config.toml` 是主要的配置文件，设置一些全局或自定义参数。

{{< expand "config.toml" >}}
```:/config/_default/config.toml

Title =  "Loving life and dreams."
BaseUrl = "https://lisenhui.cn/hugo-theme-next"

DefaultContentLanguage = "zh-cn"
LanguageCode = "zh-CN"

Theme =  "hugo-theme-next"

MetaDataFormat =  "toml"

PaginatePath =  "p"
Paginate = 5

DisablePathToLower =  false

PreserveTaxonomyNames = false

PygmentsStyle = "emacs"
pygmentsCodefences = true
pygmentsCodefencesGuessSyntax = true

enableRobotsTXT = true
enableEmoji = true

timeout = 100000
ignoreErrors = ["error-remote-getjson"]

[sitemap]
  filename = "sitemap.xml"
  changefreq = "weekly"
  priority = 0.5

[outputFormats]
  [outputFormats.SearchIndex]
    mediaType = "application/xml"
    baseName = "searchindex"
    isPlainText = true
    notAlternative = true

[outputs]
  home = ["HTML", "RSS", "SearchIndex"]

[minify]
  disableCSS = false
  disableHTML = false
  disableJS = false
  disableJSON = false
  disableSVG = false
  disableXML = false
  minifyOutput = true

```
{{< /expand >}}

### languages.toml{#languages-toml}

`languages.toml` 是多语言的配置文件。

{{< expand "languages.toml" >}}
```:/config/_default/languages.toml

[zh-CN]
  title = "热爱生活与梦想"
  languageName = "中文"
  weight = 1
  contentdir = "content/zh-CN"

[en]
  title = "Loving life and dreams."
  languageName = "English"
  weight = 2
  contentdir = "content/en"

```
{{< /expand >}}

### menus.en.toml{#menu-en-toml}

`menus.en.toml` 英文站点的导航栏配置文件。

{{< expand "menu.en.toml" >}}
```:/config/_default/menu.en.toml

[[Main]]
  Name = "Home"
  Pre = "home"
  URL = "/"
  Weight = 1
[[Main]]
  Name = "Archive"
  Pre = "archive"
  URL = "post"
  Weight = 2
[[Main]]
  Name = "About"
  Pre = "user"
  URL = "about.html"
  Weight = 3
[[Main]]
  Name = "Page404"
  Pre = "heartbeat"
  URL = "404.html"
  Weight = 4

```

{{< /expand >}}

### menu.zh-CN.toml{#menu-zh-CN-toml}

`menus.en.toml` 中文站点的导航栏配置文件。

{{< expand "menu.zh-CN.toml" >}}

```:/config/_default/menu.zh-CN.toml

[[Main]]
  Name = "首页"
  Pre = "home"
  URL = "/"
  Weight = 1
[[Main]]
  Name = "归档"
  Pre = "archive"
  URL = "post"
  Weight = 2
[[Main]]
  Name = "关于我"
  Pre = "user"
  URL = "about.html"
  Weight = 3
[[Main]]
  Name = "公益404"
  Pre = "heartbeat"
  URL = "404.html"
  Weight = 4

```

{{< /expand >}}

### params.toml{#params-toml}

`params.toml` 全局参数的配置文件。

{{< expand "params.toml" >}}

```:/config/_default/params.toml

[TagsCloud]
  Enable = true
  Limit = 10

[Share]
  Enable = true
  AddthisId = ""

[Comment]
  Enable = true
  Module = ""
  LiveReId = ""
  WalineSerURL = ""

[LeanCloud]
  AppId = "Your LCAppId"
  AppKey = "Your LCAppKey"
  ServerURL = "Your LCServer"

[Statis]
  BusuanziCounter = true
  CNNZSiteId = "Your CNNZSiteId"
  BaiduSiteId = "Your BaiduSiteId"
  GoogleSiteId = "Your GoogleSiteId"

[OnlineIM]
  Enable = true
  DaoVoiceId = "Your DaoVoiceId"

[Others]
  RevolverMapId = "Your RevolverMapId"

```

{{< /expand >}}

### params.en.toml{#params-en-toml}

`params.en.toml` 英文站点下的参数配置文件。

{{< expand "params.en.toml" >}}

```:/config/_default/params.en.toml

Description = "Weclome to Elkan's blog site that who is best on program develop, pre-sales and big data."
Keywords =  "Blog, Software, Big Data, Product, Architecture, Java, Kylin"
Subtitle = "Don't stop running forward!"
AuthorImg = "/img/avatar.png"
AuthorName = "Elkan.Li"
Introduce = "Never forget your dreams！"
DateFormat = "2006/01/02"
YearFormat = "2006Y"
MonthFormat = "01/02"

[[Socials]]
  Name = "GitHub"
  Icon = "github"
  URL = "https://github.com/elkan1788/"

[[Socials]]
  Name = "ZhiHu"
  Icon = "globe"
  URL = "https://www.zhihu.com/people/fan-meng-xing-chen-1"

[[Links]]
  Name = "Nutz"
  Permalink = "https://nutzam.com/"

[[Links]]
  Name = "JFinal"
  Permalink = "https://jfinal.com/"

[[Links]]
  Name = "Wendal"
  Permalink = "http://wendal.net/"

[[Links]]
  Name = "LiaoXueFeng"
  Permalink = "https://www.liaoxuefeng.com/"
  
[[Links]]
  Name = "Qybit's Blog"
  Permalink = "https://qybit.gitee.io/"

```

{{< /expand >}}

### params.zh-CN.toml{#params-zh-CN-toml}

`params.zh-CN.toml` 英文站点下的参数配置文件。

{{< expand "params.zh-CN.toml" >}}

```:/config/_default/params.zh-CN.toml

Description = "欢迎来到凡梦星尘空间站，个人主要专注于程序开发，产品，售前及大数据解决方案。"
Keywords =  "博客, 程序员, 架构师, 思考, 读书, 笔记, 技术, 分享, 大数据, 产品"
Subtitle = "没有伞的孩子要学会努力奔跑!"
AuthorImg = "/img/avatar.png"
AuthorName = "凡梦星尘"
Introduce = "再平凡的人也有属于他自己的梦想!"
DateFormat = "2006-01-02"
YearFormat = "2006年"
MonthFormat = "01-02"

[[Socials]]
  Name = "GitHub"
  Icon = "github"
  URL = "https://github.com/elkan1788/"

[[Socials]]
  Name = "知乎"
  Icon = "globe"
  URL = "https://www.zhihu.com/people/fan-meng-xing-chen-1"

[[Links]]
  Name = "Nutz"
  Permalink = "https://nutzam.com/"

[[Links]]
  Name = "JFinal"
  Permalink = "https://jfinal.com/"

[[Links]]
  Name = "Wendal"
  Permalink = "http://wendal.net/"

[[Links]]
  Name = "廖雪峰"
  Permalink = "https://www.liaoxuefeng.com/"
  
[[Links]]
  Name = "Qybit's Blog"
  Permalink = "https://qybit.gitee.io/"

```

{{< /expand >}}
