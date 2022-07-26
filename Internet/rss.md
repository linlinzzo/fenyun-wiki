# 订阅中的不同名词

这里，我们搜集了不同网站关于 RSS、Atom 和 Feed 的描述。国内关于这些东西的描述很少，维基百科上的一些相关页面也没有翻译，以至于整理到最后连自己都懵了（尤其是对 Feed 的概念）。

## RSS

根据网络整理出以下信息：[^1][^2]

|name|content|
|---|---|
|全称|RDF Site Summary、Rich Site Summary 或 Really Simple Syndication|
|中文翻译|简易信息聚合 或 聚合内容|
|实质|一种消息来源格式规范|
|功能|将多个网站更新的内容进行整合并以摘要的形式呈现|
|好处|有助于订阅者快速获取重要信息并选择性地点阅查看|
|目的|将新闻标题、摘要（Feed）、内容按照用户的要求，推送至用户的桌面|

备注：RDF Site Summary、Rich Site Summary 和 Really Simple Syndication 都是指同一种联合供稿（Syndication）的技术。

此处，我们从一个博客网站的 HTML 源码中找到例子：

```html
<link rel="alternate" type="application/rss+xml" title="RSS 2.0" href="/feed/" />
<link rel="alternate" type="application/rdf+xml" title="RSS 1.0" href="/feed/rss/" />
```

[^1]:[《知道RSS的人越少，我就越希望它能被人知道！》](https://zhuanlan.zhihu.com/p/349349861)第一节
[^2]:[RSS - 维基百科，自由的百科全书](https://zh.wikipedia.org/zh-cn/RSS)

## Atom

Atom 可以简单地理解成 RSS 的替代品，它采用 XML 格式。[^3][^4]

### Atom 与 RSS 的比较

Atom 克服了 RSS 2.0 的一些问题，大致包括：[^4]

- RSS 2.0 可能包含文本或经过编码的 HTML 内容，同时却没有提供明确的区分办法；相比之下，Atom 则提供了明确的标签（也就是`typed`）。
- RSS 2.0 的`description`标签可以包含全文或摘要（尽管该标签的英文含义为描述或摘要）。Atom则分别提供了`summary`和`content`标签，用以区分摘要和内容，同时 Atom 允许在`summary`中添加非文本内容。
- RSS 2.0 存在多种非标准形式的应用，而 Atom 具有统一的标准，这便于内容的聚合和发现。
- Atom 有符合 XML 标准的命名空间，RSS 2.0 却没有。
- Atom 通过 XML 内置的`xml:lang`，而 RSS 采用自己的`language`标签。
- Atom 强制为每个条目设定唯一的`ID`，这将便于内容的跟踪和更新。
- Atom 1.0 具有在 IANA 注册了的 MIME 类型，而 RSS 2.0 所使用的`application/rss+xml`并未注册。

类似的区别还有很多。根据这些区别，我们可以得出 Atom“更明确、更方便”的优点。

此处，我们从一个博客网站的 HTML 源码中找到例子：

```html
<link rel="alternate" type="application/atom+xml" title="ATOM 1.0" href="/feed/atom/" />
```

[^3]:[订阅基础：RSS、ATOM、FEED、聚合、供稿、合烧与订阅 - 郑文亮 - 博客园](https://www.cnblogs.com/zhwl/p/3645383.html)
[^4]:[Atom (标准)- 维基百科，自由的百科全书](https://zh.wikipedia.org/zh-cn/Atom_(標準))

## Feed

Feed 是 RSS（或 ATOM）中用来接收该信息来源更新的接口，它在 RSS（或ATOM）和订阅用户起到类似于“中间商”帮忙批发传递信息的作用。[^3][^5]ATOM、RSS 和 JSON Feed 是 Feed 的常见格式。[^6]

[^5]:[Feed（RSS中用来接收该信息来源更新的接口）_百度百科](https://baike.baidu.com/item/Feed/15181)
[^6]:[Web feed - Wikipedia](https://en.wikipedia.org/wiki/Web_feed)