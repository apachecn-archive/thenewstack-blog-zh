# 5G 和公共云将如何塑造应用的未来

> 原文：<https://thenewstack.io/how-5g-and-public-clouds-will-shape-the-future-of-applications/>

[蟑螂实验室](https://www.cockroachlabs.com/)赞助了这篇帖子。

 [斯潘塞·金博尔

斯潘塞是蟑螂实验室的联合创始人兼首席执行官，他在对分布式系统编程的热爱和帮助公司平稳发展的兴奋之间保持着微妙的平衡。他在互联网全盛时期开始涉足数据库领域，并在谷歌十年的发展历程中一直坐在前排。](https://www.linkedin.com/in/spencerwkimball/) 

今年二月，在疫情被认为是疫情和纽约市还在嗡嗡作响之前，像往常一样，我坐在蟑螂实验室总部谈论[应用程序开发中数据](https://www.cockroachlabs.com/webinars/the-future-of-data)的未来。这是一个广泛的话题，也是一个即将经历根本性和不可改变的转变的话题。我们一会儿就会知道原因。

在那次谈话后的三个月里，世界发生了很多变化。新冠肺炎使得远程工作成为一种必然。这导致了前所未有的互联网使用水平。它将给经济和科技领域带来的持久变化尚未到来。但是，新冠肺炎并没有重新规划或改变数据的未来发展方向，而是仅仅充当了已经开始的变革的催化剂。

在疫情之前，两个技术板块不可阻挡地向对方靠拢。第一:持续的[改进和公共云的可访问性](https://www.cockroachlabs.com/guides/2020-cloud-report/)。第二:5G 即将推出。这两项功能将打破以前只有财富 500 强公司才有的延迟水平。随着这些延迟级别变得越来越普遍，用户将开始期待它们。在前疫情时代，这样的延迟水平是很不错的。但在大流行后的世界里，它们将是必备的。

这是转型的样子，以及应用程序开发人员和应用程序用户在 5G 世界中可以预见的情况。

## 全球应用和 100 毫秒规则

如今，人们认为利用公共云是一种跨不同数据中心和可用性区域复制数据以增强弹性的方法。但是这种策略不一定能解决延迟的问题。众所周知，延迟开始变得越来越重要。如果澳大利亚用户的请求必须一路跳到弗吉尼亚才能与数据库对话，然后再一路返回给澳大利亚的用户，那么你无法为他们提供足够的延迟，这是一个巨大的问题。事实上，你不可能在不到几百毫秒的时间内完成。这就引出了 100 毫秒法则。

我遇到的第一个提到 100 毫秒规则的人来自国防部。他们对命令和控制系统做了一项研究，在研究中他们问了这样一个问题:从用户做出某种动作到该动作产生可见效果的最大延迟是多少？例如，当用户敲击键盘上的一个键时，你应该在什么时候保证屏幕上出现一个字母？根据国防部的说法，答案是 100 毫秒。当你超过 100 毫秒时，你就引入了一个人类可以察觉的延迟。这种延迟可能会使应用程序体验变得混乱，这种体验应该是即时的、非虚拟的。

如今，许多公司都试图通过主要部署在单一可用性区域中的应用程序来为全球受众提供服务。他们把地球上的每个人，不管在哪里，都送到那个地方。这是旧模型，无法满足全球(甚至是双海岸)用户群的 100 毫秒规则。

全球应用程序是向全球受众提供本地体验的应用程序。要理解全球应用程序，你只需要看看构建它们的公司:谷歌、脸书、网飞、苹果和 HBO。这类公司已经找到了全球性的应用。但是如果我们要衡量工程师们在构建数据架构上花费的时间，那将会是几个世纪甚至几千年的工程时间。

这就是构建全球应用程序所需要的。如果你想将其归结为一句话，他们在那几个世纪里取得的成就是拥有全球客户群，这种客户群给人的感觉就像是本地体验。

## 本地经验是下一个大机会

现在，当你点击你的移动设备，在你期待的事情发生之前等待几秒钟，这并不罕见。我们已经习惯了。与此同时，我们无处不在地沉迷于这些移动设备。在曼哈顿，每个人都在互相碰撞，因为他们低着头走来走去，看着 Slack、Instagram、Twitter、Youtube、抖音或其他一些我太老了不知道的新热点。

普通人现在花在这些虚拟现实中的时间令人难以置信，忍受着潜在的体验，这对下一代应用程序开发人员来说是一个不可思议的机会。

人们总是想知道，“下一个重大的平台转变会是什么？”“下一代 iPhone 是什么？”“会是苹果手表吗？”(没有！)这是一个开箱即用的基础设施，使开发者能够向全球受众提供本地体验——这是一个面向人民的平台，具有网飞、脸书、Twitter 和 HBO 花了几个世纪的工程时间积累起来的全球能力。

## 5G 是网络延迟的历史性飞跃

想象一下你在一个拥挤的房间前讲话，或者，今天更有先见之明的是，在一个有数百人收听的 Zoom 电话前讲话。想想你如何解读听众的表情。想想你用来评估经历的所有微妙的线索。“她打呵欠，她很无聊，我很糟糕。”“哦，他在点头，我一定很开心——或者他只是在示好？”现在想象在应用程序交互中构建这种人际关系的细微差别。当互动发生在接近实时的时候，你能重新想象脸书或推特吗？下一代应用将利用公共云资源和 5G 的能力，为用户提供难以置信的低延迟和最终近乎实时的体验。新的应用程序将彻底改变人们醒着的时候花一半时间消费的用户体验。

5G 听起来像是蜂窝网络的一个渐进的进步。但在我看来，从 4 到 5G 的整数跳跃是一个历史性的飞跃。在电信网络中很少出现像这里预期的延迟下降。这将对人们重新想象当今价值数十亿美元的用户平台的方式产生巨大影响。上一次我们看到这样的速度转变是在我们从拨号上网转向 DSL 的时候。对于当时在场的任何人来说，这都是惊人的。这种转变带来的应用是巨大的。我们从基于文本的游戏发展到多用户互动应用。现在我们在堡垒之夜。但是堡垒之夜之外还有一些东西。5G 将帮助我们实现这一目标。

## 新的消费模式将增强开发者的能力

更重要的是，这种新一代的应用程序不会只来自拥有数百万风投资金的大公司。这是因为从脸书和谷歌等地吸取的经验教训正被迅速浓缩并打包到通用系统中。承担这项工作是一项艰巨的挑战。但它正在发生。

我们在蟑螂实验室亲眼见过。许多使用 CockroachDB 的初创公司都是由前谷歌、前优步和前脸书的工程师运营的。这些工程师带着与五年或十年前加入谷歌、脸书或优步时截然不同的态度开始了他们的下一个项目。这一代工程师经历了范式转变。他们了解分布式系统。他们使用公共云、微服务和现代数据库技术。

工程师们不会从那些必须一次又一次重新搭建平台的基础设施开始。他们将要求他们在谷歌、脸书和优步看到的能力。各公司正争相通过提供托管服务软件和基础设施即服务来填补这一空白。

## 应用程序开发的未来

应用程序开发已经处于巨大转变的边缘。然后新冠肺炎出手了。消费者对低延迟技术及其带来的交通体验的需求比以往任何时候都高。对感觉像真实生活的缩放游戏场所、真正身临其境的 MMORPG 游戏以及我们甚至还没有想到的新用例的渴望正在高涨。5G 的完美风暴、改进的公共云和托管服务软件将使这一切成为现实。

地平线上是一个美丽的新世界。在这个世界里，以前不可想象的应用程序将被开发出来，而不是由 Facebooks 和世界各地的谷歌，而是由个人开发者和小团队。冠状病毒疫情正在使我们的世界比以往任何时候都更加分散——应用程序开发即将发生的变化将使我们准备好迎接这一现实。

来自 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>