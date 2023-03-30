# 新的堆栈制造商:阿德里安科克罗夫特对太阳，网飞，Clojure，去，Docker 和更多

> 原文：<https://thenewstack.io/the-new-stack-makers-adrian-cockcroft-on-sun-netflix-clojure-go-docker-and-more/>

我对阿德里安·科克罗夫特的采访的第二部分涵盖了阿德里安早期对学习事物如何工作的兴趣，以及他和他的职业生涯的方向。此外，他还对云计算、热门话题(如 Go、Docker 和 Clojure)等有一些见解。下面是[第一部分](https://thenewstack.io/the-new-stack-makers-an-interview-with-adrian-cockcroft-of-battery-ventures/)供参考。

**亚历克斯:有很多关于云计算和云技术复杂性的营销。**

**阿德里安**:这里有一些评论。一个是不熟悉的比难的多。所以不要把不熟悉和复杂或者难做混为一谈。而且人们很难分辨。像 NoSQL 对大多数人来说是陌生的。它有一些不同的概念。一旦你学会了怎么做，那就简单得可笑。比 MySQL 什么的简单多了。它几乎没什么可学的，但它包含了一些不同的概念。一旦你明白了这一点，“这就是全部吗？好吧。”就像是，“难道它没有别的功能了吗？”“没有，就这些。”但是它还有其他属性，可以扩展，但是非常非常简单。您已经在查询复杂性和一致性模型之间进行了权衡，以获得可伸缩性，然后您必须处理某些其他级别功能的缺乏，在您自己的代码中做更多的工作，并了解一些不同的工作方式。这是一个关键的区别。

这比 2009 年容易多了。这真的是最有趣的部分。我们读了亚马逊的白皮书，读了谷歌的白皮书，然后编造了一些东西。我们有一些以前做过分布式系统的非常有经验的人，我们有很大的争论，我们尝试了一些东西，找到了一些有用的东西。大多数 PaaS(产品)都以这样或那样的方式解决了这个问题。那时没有卡桑德拉，当然是以可用的形式。分布式系统现在已经成熟和稳定。你可以用动物园管理员之类的。

人们说这是必要的，但没人相信。

阿德里安:的确有人在构建这些系统，但他们大多是专有的。甲骨文有一致性。你可以购买许多软件层，它们是分布式系统层。但它们大多是现成的商业软件，你进入了这个体系结构，你有点被困在这个体系结构中，也许它做了你想要的，也许没有。开源软件的可塑性更强。网飞把人放在项目上并改变它，直到它做了我们想要的，其他人也做了同样的事情。

**你基本上必须建立路径。**

阿德里安:是的。

**现在人们可以走这条路了……**

阿德里安:如果你想卖软件，问题是你必须让软件进入一个广阔的市场。很难有真正了解人们需要什么的纯净度。然而，如果你确实有真正的问题，你可以改变产品以满足你的需要，你有足够的能力去做，你有合适的才能去做，你实际上可以得到你的问题的真正解决方案。

**在你的成长过程中，你是如何对科技感兴趣的？是大学之前，还是大学期间？**

**阿德里安**:不，是以前。我爸爸真的是最重要的。他是一名大学统计学讲师，但他在 20 世纪 60 年代从事编程工作。

那是在哪里？

阿德里安:那是在英国。我很小的时候他就上了大学，他获得了统计学学位，然后找到了一份讲师的工作。但是用统计学，你需要计算机把数字加起来。所以他有这些加法机，他会做统计。他有手摇加法机和计算器之类的东西。所以他们总是在附近。我去的学校离他工作的大学很近。但是学校里有一个终端，当我 12 岁的时候，你可以把你的名字写在一个名单上，在午餐休息的时候，你可以花半个小时玩把 BASIC 输入 DEC 系统-10，玩月球着陆器之类的游戏。所以我在 12 岁的时候学习了编程，这在 1972 年是相当不寻常的。我出生于 1960 年。

**1972 年你在编程什么？**

阿德里安:DEC system-10 是当时哈特菲尔德理工学院(现在的赫特福德郡大学)的一个像盒子一样的大型主机。

**你们对物理有共同的兴趣，还是有交集？**

阿德里安:我对事物如何运作很感兴趣；我现在也是，我有点喜欢把东西拆开。物理学是“事物如何工作”的终极从基本原则出发，找出事物的工作原理。如果你有一些物理背景，这就是他们教你做的。所以把物理定律应用到事物上，并把它解构为行为规则的科学方法，是我应用到计算机事物上的东西。我获得了物理学学位，在电子学中研究应用物理学，我做了一些东西。所以我在一家咨询公司找到了一份工作，建立实时嵌入式系统和信号处理控制系统。

我学过物理学中的信号处理控制理论，所以我知道你试图控制的东西是如何工作的，因为这就是物理学。我知道信号处理控制理论，一些编程，以及如何给微处理器编程。这就是我的工作，我做了几年。我们使用 Sun 工作站作为开发机器。

这是在哪里？你为谁工作？

阿德里安:剑桥咨询公司。现在还在，R & D 公司在剑桥(英国)。我们是 Sun 工作站的首批用户之一。在那之前我们用的是 PDP-11。这是 20 世纪 80 年代初。然后我在 1988 年加入了 Sun，因为他们在附近开了一个销售办事处。我最想知道的是接下来会有什么机器。

**因为你一直在用这些 Sun 工作站工作？**

**阿德里安**:是的，我一直在做这些最新的，我想，“你接下来要做什么？”他们不会总是告诉我接下来会发生什么，所以如果我去那里工作，我就能知道接下来会发生什么。我一直在寻找未来一代的东西。在 20 世纪 80 年代的某个时候，我遇到了比尔·乔伊，我意识到他生活在未来五年，而我也想成为那样的人。

…嗯，我想成为比尔·乔伊。但我想以某种方式获得他对未来的观点，他可以看到事情将会如何发展。那是那些形成的时刻之一。比尔上世纪 80 年代在 Sun 公司所做的这一方面很有趣。当我在 Sun 工作时，我并没有真正了解他。我没有和他一起工作。加入风投公司意味着我可以看到几年内不会发生的事情，因为人们还在梦想这个想法。

**在 Sun 公司，你是否也梦想着几年内都不会发生的事情？**

阿德里安:是的。从设计芯片开始，高端服务器的制造需要 5 年时间。你花了几年时间制造芯片，然后制造机器。从第一次运行——其中一台 E10K 类型的服务器或工作站——从第一次在内部运行到外部产品发布可能需要一年时间。但是在那之前，你可以接触到人们谈论它是如何工作的。

**那么离开孙之后，你的事业进展如何？**

**阿德里安**:好吧，让我们用四分钟总结四十年。

我在剑桥咨询公司做的是相当高端的嵌入式系统:后来的 68000 CPU 板用 C 处理——真正高端的嵌入式系统，信号处理，控制理论的东西。然后我们开始研究晶片机，然后是并行计算算法之类的东西，作为另一组项目。晶片机是 20 世纪 80 年代英国为一种微处理器设计的，一种大规模并行微处理器，这是一件大事。那时候 MPP 机很大。英特尔超立方体就是其中之一。有一堆 MPP 系统，像思维机器和连接机器。所以我在那个空间呆了一会儿。因此，当我加入 Sun 时，我对算法、开发和性能有相当多的了解，我会调整我的代码，所以我了解性能调整。我还为 CCL 的机器做了一周一天的系统管理员。所以我是 DevOps，如果你喜欢的话。我每周有四天是开发人员，一天是运营人员。我是 Sun 的联系人，负责升级这些机器并保持它们运行，确保我们有备份，从 UNIX 的角度管理它们。所以我是 UNIX 系统管理员。其他人是总的系统管理员，好像这是他真正的工作。我负责 UNIX，因为他负责管理虚拟机和他们拥有的任何东西。

因此，当我加入 Sun 时，我是一名相当有经验的 Sun UNIX 系统管理员，也是一名能够处理这个领域的开发人员。这很有趣，因为我发现在整个 Sun 社区中，我比大多数人更了解性能调优。然后我会做一些更技术性的项目，他们需要有人帮助调整一些代码或其他东西来赢得基准测试，所以我会参与这种基准测试。然后随着我们从工作站转移到服务器，机器变得越来越大，问题也越来越多，我从未真正成为一个完整的数据库管理员。但是我有时会调优运行数据库的机器，并构建一些性能工具。在我昨天早上的演讲中，我强调了我 20 年前做的一件事，叫做“虚拟阿德里安”，这是一个你在 Solaris 机器上运行的脚本，告诉你它有什么问题；它写于 90 年代中期。所以现在许多运行 Solaris 机器的人仍然在运行它。如果你能找到一个大的 Solaris 机器，它可能还在运行虚拟 Adrian。

我成为了 Sun 的容量规划和性能专家，并写了一本书, *Sun Performance and Tuning* 。大多数曾经照看过 Sun 机器的人都会得到这本书的副本。这不是一个很大的社区，但我卖了相当数量的书。然后我成为了 Sun 公司的一名杰出的工程师。我是性能和容量规划以及性能工具方面的专家，这也是为什么这次会议是我的天然栖息地。这对我来说是一次“返璞归真”。然后在 Sun 做了几份不同的工作:我在性能团队工作，负责应用程序和操作系统的性能调优。然后我加入了高性能计算团队。十年前，我是高性能计算的首席架构师，担心互连、InfiniBand 和万兆以太网。

然后在 2004 年，Sun 解雇了整个团队，因为它在收缩——你知道，这是它的收缩之一——我们都离开了。我在那时加入了易贝公司——早在 1999 年，他们有一次大停电，在 1999-2000 年，我是帮助易贝重新运转的团队的一员，我和他们谈了很多关于如何进行容量规划和设置一些流程的问题。四年后，他们仍在运行这些程序，我一直保持着联系，所以当我需要一份工作时，我就给易贝打电话。所以我去那里工作了几年。两三年后，网飞出现了。网飞正处于开始需要扩展的阶段，我发现我在 Sun 做的性能工作和我在易贝学到的可扩展性的结合——基于消费者的、网络规模的东西——对网飞很有兴趣。这就是我加入网飞的原因。

**这个角色最初是帮助他们进行容量规划？**

**阿德里安**:没有。在网飞，我负责管理个性化工程团队。所以我实际上是在管理开发团队，这是我想做的事情。但是算法必须扩展。因此，它是弄清楚如何让算法和它们周围的系统规模化。但是当时网飞仍然很小:工程师人数很少，部署也很少。那是几十台机器。然后，随着流媒体技术在那个时候开始兴起，我们开始快速发展。因此，大约两三年后，我带着我当时管理的团队，增加了一些额外的人员，进行了云迁移。然后，我转换了角色，成为云平台团队中的云架构师。

一旦我们采取行动，网飞创建了一个团队来做云平台。他们雇佣了一个经理，Yury Izrailevsky，他决定他需要一个能从技术角度弄清楚所有东西如何工作的架构师，我向他解释了它是如何工作的，因为我一直在领导团队设计它。网飞的经理基本上也是建筑师，这就是我的角色。所以我转到他那里，作为建筑师为他工作，不再关注个性化的东西。其他人接手了。所以这是一个横向转移，我这样做了三四年。

**现在你已经进入了这个新的角色，你和很多人交谈，你出去走动……**

**阿德里安**:我把我在网飞业余时间做的大部分事情都当成了我的日常工作，我的主要工作，所以这就是真正的翻转。事实上，我在网飞花了越来越多的时间推广开源项目，试图了解那里发生了什么，并帮助外部的人们，还与风投谈论正在开发技术的有趣公司，这些公司可能会引起网飞的兴趣。所以这些对话其实没什么不同。对我来说，它实际上是一个小得多的公司，所以在一个几十人而不是一千多人的团队中感觉很好。但是我每天做的事情有点不同。我在和一群略有不同的人交谈，他们感兴趣的东西要广泛得多。所以这也很好。

**今年年中，你在这广阔的前景中看到了什么？你有这样的事件(monitor ama)；这是一个有趣的事件，有一个社区正在围绕这种理解容量和性能的能力发展。**

**Adrian** :我认为它一直存在，这个事件刚刚出现，并抓住了人们对这个领域开源工具的想象力，这是一个很好的子集。这主要是实践者——人们在做这件事。有一些供应商支持，但不是由供应商驱动的。这个领域的大多数会议都是由供应商驱动的。

这一领域有许多问题需要解决，这些问题就是我在主题演讲中谈到的:在基于云的云原生环境中进行监控的挑战，在这种环境中，您已经实现了非常复杂的自动化来部署一切，并开始自动扩展一切。然后你实际上想要测量正在发生的事情，并自动对其做出反应。一旦你关闭了反馈回路，你就在做控制系统的事情。大多数监控工具都无法做到这一点。他们有一个人盯着会做出改变的东西，对吗？所以系统管理员是控制循环的一部分。

网飞所做的是不让系统管理员成为控制的一部分。他们正在自动化整个循环。当你这样做的时候，你的监控系统必须比它所监控的东西更可靠。否则，它只会把你搞得一团糟。每次它坏掉都会破坏你的环境，因为它会随机地做错误的事情，因为它看到了错误的输入。这就像如果你有一个汽车发动机，你解开其中一个传感器，它会运行不平稳。如果你有一个坏的传感器，你的爆震传感器，或者你拔掉一根电线，它可能仍然会运行，但它不会高兴。所以这些是我认为有趣的问题，这也是我向这里的人们强调的。所以人们对此很感兴趣。整个大数据分析意味着您可以做更多的分析。而且有更多的计算能力。所以你现在实际上可以做的比以前多得多。越来越多的东西作为开源，作为社区构建的东西被构建出来。所以我认为这是一个尝试建造这些东西的有趣时代。

> 在过去的几年里，显而易见的是，开源产品是最具扩展性和可靠性的产品。

你知道，那些可能有一个公司照顾他们，但它并没有真正完全控制他们。因此，你可以通过 Datastax for Cassandra 获得一个可靠的分布式系统数据存储，或者通过 Basho for Riak 或其他方式。也许 IBM 在这个领域有产品，但不是真的，如果他们有，他们会想要很多钱。因此，这些产品正在被大规模的用户塑造。这是一个有趣的转变，现在有趣软件的主要来源是网飞的 GitHub 网站，Twitter 的 GitHub 网站，LinkedIn，脸书，谷歌，大部分都在 GitHub 上。你去从网络规模的公司那里获得你的开源软件，这些公司投资并让最好的人为他们工作来解决这些分布式系统的问题，然后你用这些来组装你的代码。你有 Hadoop，卡夫卡，卡珊德拉等等。你把这些不同的碎片粘在一起。你是一家初创公司，你有三个人，你刚刚利用了大量的智囊团，你可以免费做这件事。您可以购买对其中一些的支持，但这只是在最近几年才真正变得明显。这是目前完成工作的最高水平。大型供应商已经设计好了，他们正试图通过收购这些公司来让自己与这种对话相关联。我认为，随着大型 IT 供应商变得越来越边缘化，他们会开始买东西。

例如，你对 Docker 有什么想法吗？这似乎是你所说的结果。

**阿德里安** : Docker 很有趣。这是一个很好的例子，在正确的时间用正确的名字得到正确的东西，然后像病毒一样传播。

这是一个比喻。

**阿德里安**:你得到了一个比喻。这是一个概念上简单的想法，有一个匹配的名字，一个好的标志，这有点像营销点击，每个人都去，“我明白了。”实际上还有其他一些东西也有这种功能，它们已经存在了一段时间，但没人听说过，也记不起它们的名字，而且已经失传了。这甚至可能不是最好的技术，但他们按下了所有正确的按钮，并取得了成功。事实证明，命名很重要。

**命名*和*有关系吗？**

阿德里安:很多公司都选择了非常愚蠢的名字。差别很大。

但是这个比喻是对的。

阿德里安:从概念上来说，是的。所以你可以把东西打包，然后在这个容器里移动。集装箱化是十年前的事了。十年前，Sun 公司的 Paul Strong 正在研究 Solaris 容器。他现在是 VMware 的首席技术官。他在那里有一段时间了，是我的一个老朋友。从概念上来说，这些都不是新的，但是可以打包的想法是好的。每个人都采用了 Docker，所以真正的问题是，“制造 Docker 的公司会从中赚钱吗？”或者其他人会说，“好吧，我们已经做到了。”我不确定。这很有趣。

关于 Go 作为一种编程语言，有很多讨论。

**Adrian** :我看到的真正酷的东西正在构建中，其中一些在 Go 中，另一个是 Clojure。我所知道的许多最好的程序员和最有生产力的程序员都用 Clojure 写所有的东西，并发誓遵守它，然后在很短的时间内生产出复杂得可笑的东西。程序员的生产力很重要。这很有趣。Go 很有趣，因为它正在取代 C 和 C++成为系统编程语言，很多东西现在都是用它编写的。就我个人而言，我很高兴，因为最初我是一名 C 程序员，回到 80 年代，我也是一名 occam 程序员，而 Go 基本上就像 C 和 occam 融合在一起。它有基于渠道的沟通模式。它现在还不是一种非常有名的语言，但是如果你看了它，你会说，“哦，是的，我能看出 go 是从哪里来的。”这是相同的基于通道和并行的模型，CSP 也是如此。从技术上讲，有一种叫做π演算的东西，它是基于东尼·霍尔的 CSP。沟通顺序过程是它背后的理论，那是在 70 年代。

我听说过并发性和并行性之间的区别。随着这些基础设施变得越来越……

阿德里安:你可以为标签争论。有不同的编程模型。我们现在处于众核时代。你有一台笔记本电脑，它有四核或八核；你的手机有，对吧？所以如果你不知道如何使用它，那么你的程序就不会运行得很好。所以问题是你如何用程序员能理解的并行方式表达事情。围棋似乎已经获得了足够的牵引力，变得有趣起来。

**你在尝试考虑其他服务。也许你可以在现在引起共鸣的隐喻的背景下结束这次采访，当我们展望未来六个月、十二个月和十八个月时，这些隐喻意味着什么。我们有有趣的“运输”隐喻，这是一个很大的对比……**

**阿德里安**:回到开发速度:就像我说的，没有哪个高管希望他的公司在产品开发上慢一些。因此，如果你考虑如何真正加快速度，你必须在这个过程中放手。所以每次你让一个团队给另一个团队一些东西——从开发到 QA 到运营等等——每一个都是一个同步点，让一切都慢下来。如果你能避免这种情况，那你就省了很多钱。所以速度很重要。为大公司采取这些措施意味着你真的要重组，因为这就是 DevOps 的意义所在。如果采用 DevOps 不涉及重组，那么你做得不对。所以这也是为什么很难采用的原因之一。但是，一旦你了解了这一点，你就会意识到你正在做的事情是精简事情，你必须将各个小组粉碎在一起，以便开发人员可以自己操作，操作人员、开发和 QA…你消除了人为障碍，在操作中，你消除了存储人员、网络人员、数据库人员和系统管理员的烟囱式领地。所以你必须把这些东西重新混合在一起，以提高效率，也就是提高交付速度。他们因优化成本而非速度而变得孤立。所以这是一个成本和速度的问题。钟摆从成本摆回到速度。因为基础设施的成本如此之低，以至于现在开发一个东西所花的时间是最大的问题，所以你必须加快速度。因此，这导致人们以不同的方式思考问题，不同的产品出现，人们处理事情的规模，以及“软件吞噬世界”这种想法，即每个公司现在都必须成为软件公司。你不可能不是一家软件公司，因为某个地方的每个产品都有软件。你所做的一切，无论是营销还是销售，都是在为广告进行实时竞价。

硬件正在被抽象化。

阿德里安:是的。但是现在几乎不可能有一家公司不用处理，以某种方式，所有这些高科技软件和软件开发和技术。你不能把它抽象化，然后说，“我只是把它放在一个角落里，它就会自己解决。”工资单或其他什么的，现在是业务的基础。这也正是凤凰计划书的内容:将 IT 从边缘活动转变为业务的核心。这是一个巨大的变化，人们正在处理和应对它。我认为，许多总部位于 SaaS 的老牌公司正在尝试将他们在该领域看到的棘手问题自动化，并试图找出“最大的棘手问题是什么？”以及“你如何向这些人销售？”这就是我现在的日常工作——主要关注早期企业 IT 初创公司，他们正在寻找一个痛点，并试图找出“这是一个真正大的可扩展痛点，还是只是其他东西的一个功能？”你不会真的想投资一个六个月后就能拿到手的东西。你总是在努力寻找一家三年后会有 10 亿美元首次公开募股的公司。这就是游戏。

**我们必须越来越多地在“速度、速度、速度”的框架内思考，以找到这些类型的公司。**

**阿德里安**:是的。但是已经散开了。因此，许多过去不需要速度的公司现在如果不明白这一点，就会倒闭。这就是在中西部或其他地方制造小配件的广大市场上正在发生的事情。这些人现在必须找出如何快速开发软件。

我的一个类比是:恒温器通常是倾斜的——老式恒温器。这是一个双金属片，它倾斜一个水银倾斜开关。当它变热时，它倾斜并打开它，当它变冷时，它向另一个方向倾斜并关闭它。这是你的恒温器。几十年来，你一直在制造恒温器，只要你能便宜地买到水银，你就没事。也许在路上的某个地方，你有一个液晶显示屏和几个继电器。然后 Nest 出来了，你会问，“什么？”这个东西有一个 iPhone 应用程序和所有的电子设备，它基本上是一个挂在墙上的电话。这已经够糟了，然后谷歌就收购了他们。历史上你是一个水星倾斜开关制造商，现在你的主要竞争对手是谷歌，这不是一个舒适的地方。公司正试图解决这个问题。我的意思是，这是一个极端的例子，但物联网这种东西正导致许多公司不得不处理这种东西。从广泛采用的角度来看，这很有趣。我认为物联网真的开始发生了，并开始推动许多活动，许多人都在围绕它进行建设。所以这可能是下一波将要发生的事情。我在那个领域有些人脉。我的第一份工作是用计算机构建嵌入式实时系统。回到过去的日子。

阿德里安，这是一次精彩的采访。非常感谢您抽出时间来到我们的城市波特兰参加 Monitorama。

**阿德里安**:感谢并祝贺*发布新堆栈*。我正在阅读我 RSS 订阅的所有文章。很高兴看到不同于 GigaOM 或 TechCrunch 的观点。因此，这是对正在发生的事情的一种赞赏和有益的补充。

好的，谢谢你，我们稍后再聊。

阿德里安:是的，谢谢。干杯。

我们的播客制作人兼文字编辑卢克·勒弗勒(Luke Lefler)参与编辑了《阿德里安访谈》。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>