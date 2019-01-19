# 这个项目已经死亡很久了，但这并不表示我放弃了它：新的更小、更快、依赖更少的 [manga](https://github.com/Hentioe/manga-rs) 继续在这里成长！

# Manga

Online comic offline export tool, implemented using Elixir!

## 说明

将漫画网站的资源直接导出为离线阅读文件（EPUB/MOBI/PDF）。 ~~此项目正处于开发阶段：）~~ 最新状态：此项目基本停止维护，新的[替代品](https://github.com/Hentioe/manga-rs)正在开发中，当新项目成熟以后会关闭此项目：(


需要注意的是，这是一个使用 Elixir 实现的项目。它的运行需要依赖 [Erlang]()，就像 Java 软件需要 JRE 那样 :)

PS: 如果你从 [RELEASE](https://github.com/Hentioe/manga.ex/releases) 页面下载使用本软件，请务必安装 21.0 或以上的 Erlang/OTP 版本。

## 演示

![show](https://raw.githubusercontent.com/Hentioe/manga.ex/master/.github/show.gif)

## 说明


正如你所看到的，这个软件可以从 CLI 交互中选择平台导出(漫画)资源，也可以直接粘贴资源的 URL(会识别是否支持)进行导出。


当前 Manga.ex 支持 11 个以上的漫画平台，下面会列举出来。不过我从来不吝啬多支持几个(暂时只接受 Web 在线网站，不接受 APP)，所以欢迎你向我提交你想支持的网站 :)


Manga.ex 导出格式有三种，分别是 EPUB/MOBI/PDF，其中 EPUB 是基本格式，被直接支持。而 MOBI 和 PDF 需要安装 [Calibre](https://calibre-ebook.com/download) 在基本格式 EPUB 资源模板的基础上进行转换。

PS: Calibre 是一个开源的电子书工具箱， Manga.ex 和 Calibre 的交互对用户而言是透明的。


由于很多网站都使用各种怪异的 Javascript 函数来混淆资源地址，分析函数并重新在 Elixir 上实现是一件非常消耗精力的事情，我并不打算这么做。所以，想让本软件工作需要在系统上安装 [Node.js](https://nodejs.org/zh-cn/download/) 以作为 Javascript 的 Runtime 支持(Manga.ex 会将那些奇奇怪怪的 JS 函数扩展为解密所需的代码块，然后交给 Node.js 去执行)。

PS: Node.js 是一个 Javascipt 运行环境。与 Calibre 不同的是，前者缺失会导致输出格式受限，而后者不被允许缺失，也就是说 Node.js 是必装的。


## 用法


暂时懒得写（GIF 已经展示出核心功能了）。


## 支持的平台


状态 | 平台名称       |    说明          | 长期支持
-------|------------|-------|----------------|
✔   | 动漫之家 | 推荐（日漫）| 是
✔   | 漫画柜 | 推荐| 是
✔   | 动漫屋 | 推荐| 是
✔   | 漫画人 | 推荐| 是
✔   | 動漫狂 | 推荐 | 不一定
✔   | 非常爱漫 | 让我想想| 不一定
✔   | 新新漫画网 | 让我想想| 不一定
✔   | 漫画台 | 让我想想| 不一定
✔   | 古风漫画网 | 让我想想| 不一定
✔   | 汗汗漫画 | 让我想想| 不一定
✔   | 风之动漫 | 不推荐（慢，经常死）| ~~否~~
✖   | ~~517漫画网~~ | 编码问题暂时未整合| 不一定
✖   | ~~青空漫画~~ | 编码问题暂时未整合| 不一定


**长期支持**：即使目标平台进行了大的变化导致适配成本增加也会尽可能的继续支持

**不一定**：根据目标平台变化而导致的适配难度而选择继续支持或删除

**否**：低质量的平台产生有一定成本的重新适配将直接删除


## 目的和目标


本软件最初的目的是为了方便我个人。我经常需要找 EPUB 格式的漫画资源，放进我的电子书阅读器（类似 Kindle）中阅读。现在因为想开源并造福更多的用户，所以对大量的我并不需要的网站和平台进行了支持。


当前还是 Alpha 版本，在 1.0 TODO 全部完成以后会进入 Beta 阶段，并期待早日出现足够完善的正式版本（所以我需要你们向我提 BUG）。  
2.0 版本的主要目标是并发抓取和下载，并对分布式进行支持。


## TODO(1.0)

- [x] 基础资源爬取功能
- [x] 下载模块基础实现
- [x] 图片合并为 .epub
- [x] 基于 URL 参数类型识别的 CLI 导出功能
- [x] 基于手动交互的 CLI 导出功能
- [x] 改善输出格式
- [x] 增加抓取延时和下载延时参数
- [x] 索引列表对查看更多的支持
- [x] 更多的导出格式支持
- [x] 列表支持区间以及多项选择
- [x] 更多的资源来源支持
- [ ] 针对 Windows 去掉输出的 ANSI 颜色（不兼容）
- [ ] 读取配置文件启动任务

## TODO(1.0-RELEASE)

- [ ] v1.1: 增强导出选项
- [ ] v1.2: 混合搜索功能
- [ ] v1.3: 发送至 Kindle
