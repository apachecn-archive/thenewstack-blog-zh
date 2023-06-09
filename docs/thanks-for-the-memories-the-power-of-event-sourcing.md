# 感谢回忆:活动采购的力量

> 原文：<https://thenewstack.io/thanks-for-the-memories-the-power-of-event-sourcing/>

[](https://milendyankov.com/)

 [米伦·迪扬科夫

米伦·迪扬科夫是 AxonIQ 的一名开发人员倡导者，他的使命是帮助全球的 Java 开发人员设计和构建干净、模块化和经得起未来考验的软件！在为领先的欧洲公司开发、设计和咨询各种解决方案超过 15 年后，他目前将大部分时间用于支持社区和组织，在世界各地的会议上发言，并围绕 Java 模块化、μ服务、分布式系统架构和软件工艺研究他最喜欢的主题。](https://milendyankov.com/) [](https://milendyankov.com/)

有很多关于领域驱动设计(DDD)、命令-查询责任分离(CQRS)和事件源(es)的书籍、文章、演讲、博客和视频。这三个概念相辅相成，因此几乎所有涉及其中一个的资源都会至少提到另外两个。这篇文章也不例外，但是它将尝试用不同的方式来处理事情。代替图表和过于简化的代码样本，它会给你一些类比，帮助你建立一些有用的心智模型，以更好地理解上述概念(尤其是 es)的适用性。

先来一部好的电影参考怎么样？以心理惊悚片《记忆碎片》为例，片中一名男子努力寻找杀害他妻子的凶手。棘手的是，他患有严重的疾病——他无法形成新的记忆。这种情况实际上并不完全是虚构的。早在 1953 年，亨利·莫莱森就因为脑部手术而无法形成新的记忆，该手术原本是为了帮助控制他的癫痫症。

![](img/632c899cad2b3114e5e54e9d137c4959.png)

想一想。想象一下，你知道所有对你正常运作必不可少的东西，但是对过去的几天、几周、几个月、几年没有任何记忆(包括书面的)。想想它会如何影响你执行日常任务的能力。由于无法形成新的记忆，一个人必须完全依靠状态。

也就是说，要根据自我的实际状态和周围环境的当前状态来做决定。不可能说出这些国家是如何形成的。唯一已知的是在那一刻可以观察到的东西。

让我们考虑一个选择飞机座位的简单例子。你有飞机上所有座位的地图，每个座位都被标记为有人或可用。这是任务的输入数据。除非您随着时间的推移有意地、持续地扩展和更新您的状态(例如，通过写下相关的注释)，否则它不会包含任何更多与上下文相关的信息。然而，输入数据足以执行“挑选座位”动作。缺乏记忆并不会使任务无法完成。

然而，(在没有记忆的情况下)不可能的是利用先前经验的结果来影响决定(例如，“不要坐在厕所旁边”，“避免中间的座位”，“更喜欢窗户而不是小巷”)。只有通过分析记忆，才能获得决策过程中的质量提升。

无法形成记忆的一个解决方法是不断扩展和更新状态。然而，这种方法有一个明显的局限性。它要求你现在就知道你将来需要做什么决定(也许在不同的环境中)，这样你现在就可以收集所有相关的信息并相应地更新状态。你现在跳过的任何一条信息都将永远丢失。

## 软件系统应该有记忆吗？

我们人类被情感和故事所驱使，就像上面那些，让我们试着想象我们会有什么感觉。但这与感情无关。它是关于数据处理能力和局限性，决策约束，以及状态和记忆(或者日志——用更专业的话来说)如何互补。暂时把情绪放在一边，只关注具体细节，你会很快意识到这与软件系统是多么相关。

似乎很多应用程序只需要知道当前状态就能正常运行。这就是它们的设计方式。以一个简单的产品目录系统为例。它能很好地告诉你现在有什么产品，并向你展示它们的所有细节。它不关心产品如何出现在目录中，或者如何以及何时被修改(除非有审计需求)。目录系统可能比仅仅是数据的代理更复杂。它可以有特定的业务逻辑(过滤与用户性别、位置和当前天气相关的产品)，甚至可以根据一些规则进行自我更新(如果产品 A 和 B 可用，则 C 也可用)。它可以有很多更高级的行为，并且仍然仅仅基于它的当前状态。事实上，许多复杂得多的系统都是这样构建的，因此它们需要维护大型状态(例如，以关系数据库中数百个相互连接的表的形式)。

类似上述产品目录的系统无法形成新的记忆。但是他们(或者更确切地说，他们的作者)并不认为这是一个限制或约束。至少直到有人问——上周有什么产品？如果没有记忆，无论你如何修改系统，它都无法回答这个问题。

这里可悲的讽刺是，当你意识到你需要记忆的时候，已经太晚了。如果这个例子让你相信你的系统会从拥有内存中受益，你现在很可能在想增加内存的成本和工作量。坚持这个想法。

## 不是你在寻找的记忆

![](img/45814477e140ad7beeb9dc74aabdcfbd.png)

不管你是否这样想，实际上大多数软件系统都有一些记忆。我们通常称之为日志。它们本质上是存储在文件、数据库、专用工具等中的一长串过去的事件。它们包含了系统中过去发生的事情的信息，这些事情在某种程度上是重要的。很难想象一个没有某种日志系统的现代软件系统。对开发人员来说，记录事情通常是超级无聊的，对维护人员来说是一些额外的工作，经常被利益相关者忽视，但是当事情出错时却变得非常有价值。

这难道不是一个惊喜吗？大多数系统都有记忆……这样的记忆对它们自己没有任何用处。让它深入人心。想象自己无法形成记忆，带着录音设备，记录重要事件的笔记。现在意识到你不能回放那些录音。他们存在的唯一目的就是让别人评价你的行为。再次强调，从你的感受中抽象出来，关注错过的机会。这些笔记可能会帮助你做出更好的决定。你已经尽了努力去收集它们，但是你不能利用它们。更糟糕的是，除非你行为不端，否则没有人会利用它们。

当然，不是所有的软件系统都是这样设计的。您可能会惊讶地发现，关系数据库——有点痴迷于状态一致性的系统的标志性代表——实际上很好地利用了自己的内存。大多数数据库都维护一个事务日志，其中包含导致任何类型的状态修改的每一个过去的事件。当客户端与数据库交互时，根本不会使用该事务日志。但是它在数据复制和数据恢复场景中是非常宝贵的。它允许数据库节点从任何以前的备份中恢复，并通过重新应用事务日志中备份后发生的所有事件来构建当前状态。

## 状态是记忆的函数

现在让我们把这个概念延伸到另一个极端。每次需要时，我们使用系统的内存(事务日志)从头(重新)构建它，而不是不断更新状态，怎么样？显然，对于像关系数据库这样的系统来说，这不是一个非常明智的举动。这不仅仅是因为处理大量事务和在内存中处理万亿字节的数据是一个糟糕的想法。更重要的是，关系数据库有明确定义的、预先已知的、有点通用的功能范围。他们所拥有的数据的一致状态是他们主要关心的问题，他们对这种状态是如何形成的记忆很难以任何有意义的方式丰富正常的操作。

但是其他系统呢？比如我们很多人花费宝贵时间构建的以业务为中心的应用程序。我们已经看到记忆是如何增强决策和任务完成的。这就是那些业务应用程序通常做的事情——做出决策和完成任务。给他们形成记忆的能力非常有意义，不是吗？但是，他们也需要维护状态吗？也许不是，因为他们可以在需要的时候从记忆中判断自己的状态。

如果这个想法对你来说听起来很荒谬，不要放弃它。可以肯定的是，如今大多数快乐地应用它的人，曾经也认为它很可笑。而是试着回答这个问题“你现在钱包里有多少钱？”如果你和大多数人一样，你脑子里不太可能有那个数字。但是你可能记得在某个值得纪念的时间点你有了 X，然后在另一个值得纪念的时间点你得到/花了 Y，在你意识到之前你从一系列事件中构建了你钱包的状态。

一点也不难，是吗？请注意，你是如何自动地、下意识地忽略了在同一时间段收集的一堆记忆，但这些记忆与钱包的背景无关。恭喜你，你刚刚发现你的思维在寻找事件来源。

## 上下文是为国王准备的

试着告诉你的团队(先不解释事件来源)你的计划是从过去的事件中不断(重新)构建状态，你肯定会让他们担心你的心理健康。这是因为他们可能会把这个州看作一个整体。比如整个应用程序的状态。按需重建的可怕程度不亚于将整个数据库加载到内存中的想法。

实际上，与数据库不同，大多数业务应用程序不需要整个状态来执行任务。事实上，他们通常只需要其中的一小部分。并且通常状态的这一部分可以由少数事件(重新)构建。就像你的大脑对你钱包的状态所做的一样。这就是聚合的概念(以及一般的领域驱动设计)非常方便的地方。根据定义，它是一个构造块，将一组域对象组合在一起并封装起来，对于给定上下文中的状态修改，必须将这些域对象视为一个整体。这给了你清晰的界限。您只需要(重新)生成聚合的状态，以便执行所需的操作。在这种情况下，系统其余部分的状态无关紧要。

上面那段有没有把你放到“等一下！我有一大堆需要整个状态“战斗模式”的用例。如果是这样的话，很可能它是在查询你脑海中的状态，而不是修改它。当然，能够根据需要提供跨上下文数据是所有系统的基本要求。但是，没有必要在每次查询时都(重新)生成整个状态。对于大多数查询目的，状态的投影(或者您喜欢的话，状态的子集)就足够了，它包含了某人可能感兴趣的数据。这让我们明白了为什么命令-查询责任分离架构模式经常出现在图片中。明确地将命令从查询中分离出来，使得应用程序内存(事件日志)成为唯一的事实来源。完全相同的事件在命令端按需(重新)构建聚合的状态，并在查询端更新相关的投影。

## 无价之宝的价格

将 ES 与 DDD 和 CQRS 结合起来，不仅能给你的应用程序留下记忆，还能帮助你充分利用它们。那么，需要做些什么呢？一开始，从头开始实现这一点似乎是一项微不足道的任务。不是的。存储和检索数据似乎也很简单，但是你不会尝试实现你自己的数据库，对吗？一如既往，细节决定成败。

幸运的是你不必。工具和框架已经存在，可以为您完成繁重的工作。例如，对 Java 世界中的上述概念的更深入的探索，将不可避免地将您引向 Axon Framework——一个免费、开源、非侵入性的框架，为构建基于 DDD、CQRS 和 ES 的应用程序提供了所有必要的工具。虽然一开始将内存存储在数据库中非常好，但开发人员迟早也会发现 Axon Server 的强大功能——事件存储和消息总线的高效结合。这些只是最成熟的工具中的两个。肯定还有更多。探索、学习、试验，亲眼看看他们带来了什么。你可能会惊讶拥有无价记忆的代价是如此之低，以至于有一天你的应用程序可以最终回答“我们是如何来到这里的？”以及今天所有其他“不重要”的问题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>