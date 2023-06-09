# 可观察性:5 年回顾

> 原文：<https://thenewstack.io/observability-the-5-year-retrospective/>

[](https://www.linkedin.com/in/charity-majors/)

 [慈善专业

慈善是 Honeycomb.io 的联合创始人兼 CTO，这是一款帮助软件工程师理解当他们的代码遇到生产时会发生什么的工具。查里蒂在 Parse 经营基础设施，是脸书的工程经理。她创建了 Honeycomb，为工程师们带来分布式系统时代所需的可观察性工具。Charity 是《数据库可靠性工程》(O'Reilly)的合著者，致力于创造一个每个工程师都随叫随到，没有人觉得随叫随到很烂的世界。](https://www.linkedin.com/in/charity-majors/) [](https://www.linkedin.com/in/charity-majors/)

两年前，我写了一篇[长的《可观察性回顾》](https://thenewstack.io/observability-a-3-year-retrospective/)三周年纪念。它包括仪器仪表和遥测技术的历史，技术规范的详细解释，以及为什么整个“三大支柱”的事情是无意义的。在那个时候，这是将谈话从关于数据类型的愚蠢的兔子洞引回到重要的问题上所需要的:我们如何理解我们的系统。

两年后，可观察性言论变得更加过热。每隔一天，我都会听说一个新的“x 的可观察性”创业公司得到了资助。在某种程度上，这很酷，但我担心这个术语的模糊化。“可观察性”开始被用来表示任何人的任何东西，只是你贴在产品侧面以适应时代精神的一个标签。

今年，当他们总结 2021 年的学习趋势时，O'Reilly 说得最好:

过去一年中，可观察性增长最快(128%)，而监控仅增长了 9%。虽然可观察性是比监控更丰富、更强大的能力——可观察性是找到分析或调试软件所需信息的能力，而监控需要提前预测哪些数据将是有用的——但我们怀疑这种转变在很大程度上是装饰性的。“可观察性”有可能成为监控的新名称。还有就是[](https://www.honeycomb.io/blog/observability-whats-in-a-name/)**。* ***如果你认为可观察性仅仅是监测的一个更时髦的术语，你就错过了它的价值*** *。*(重点地雷。)*

 *我们不能忽视这个价值。我们负担不起。这不仅仅是一个供应商为了他们自己的利益争论定义营销术语的故事。人们每天因为无法理解自己该死的制度而忍受的痛苦和煎熬，太真实了。长时间的工作，辛苦的工作，油腻的技术债，熬夜，失眠，筋疲力尽。痛苦是真实的，解决方案也是具体的。我们需要具体的、有意义的技术术语来帮助用户导航未来，找到解决方案。

Christine 和我在尝试了世界上所有的监控和日志记录解决方案后创建了 Honeycomb，并意识到它们在回答简单的已知未知问题时很好，但在回答未知未知问题时却非常糟糕。可观察性极大地改变了我们的生活(和睡眠时间表)，改变了我们使用系统的方式，使我们成为更好的工程师，并使我们想要为我们的整个行业做出贡献。

现在是时候进行另一次回顾了。我们学到了什么？作为一个行业，我们在哪里出了问题？

## 从推特用户的口中:可观察性与监控

有一天，我打开推特，发现科里·奎因在我面前晃来晃去地放着一些推特诱饵，这条被引用的转发只是简单地说，“讨论！”：

天啊，我们做到了。引发了大量关于可观察性的定义(以及对彼此定义的争论)。

首先，我说过可观察性是由结构化事件定义的。

然后，亚历克斯·伊达尔戈反驳说不是。

亚历克斯似乎呼应的观点是，可观测性只是遥测或洞察力的通用同义词。你身边有没有旧的图表、仪表盘或测量工具？那就是可观察性！🙄那个你还没搞定的老 nagios3 实例？可观察性！🙄🙄🙄

在这种情况下，可观察性只是“理解系统”的另一个通用词一个密切相关的观点是，可观察性有三个支柱:度量、日志和踪迹。如果你也接受这个定义，那么我可以理解为什么你会抱怨用可观测性来定义一套远远超出监控的技术能力会抹杀“几十年的工作”。

我*不*接受三支柱的定义。对于现有的数据类型，这个世界不需要另一个分类词。它不需要“遥测”或“洞察”的另一个同义词

但是，有一套连贯的实践在大约五年前开始出现，以应对我们如何构建现代系统(尤其是微服务)的变化。那些实践是从他们使用度量和日志的传统中相当不连续的跳跃。事实上，一些最佳实践与监控正好相反，并且各自使用的数据格式完全不兼容。那些做法*确实需要*一句话。

我陷入定义之战已经有一段时间了。我告诉自己我不会再这样做了。但似乎我们无法停止迷失在杂草中，除非我们这样做，否则我们不会让事情回到有用的轨道上。

我们开始吧。

## 可观测性定义的历史分类法

**1960-2015:** 对于机械工程师和控制系统理论家来说，可观测性意味着可控性的数学对偶——仅仅通过从外部观察，你能多好地理解一个系统的内部运作？这个术语在计算机行业很少听到，除了 Twitter 的“[可观测性工程](https://blog.twitter.com/engineering/en_us/a/2013/observability-at-twitter.html)”团队。然而，他们把它作为遥测技术的通用同义词。

2015 年:我们开始打造蜂巢，并为如何谈论我们正在打造的东西而大伤脑筋。那年 7 月，我谷歌了一下可观测性的定义，它与我产生了强烈的共鸣。这正是我们试图建立的——理解任何内部系统状态的能力，无需事先了解或警告，只需从外部询问即可！当时，我写了大量关于这个定义的技术前提和含义的内容。

**2017:** 在参加完一次追踪峰会后，Peter Bourgon 写了一篇[极具影响力的博文](https://peter.bourgon.org/blog/2017/02/21/metrics-tracing-and-logging.html)声称可观察性有三大支柱:度量、日志和痕迹。

**2018:** 来自日志、度量和跟踪公司的厂商(不出所料)*喜欢这个定义*，并热情地采用了它。“三大支柱”营销内容用定向广告打击你。我写了我的回顾展。[本·西格曼](https://dzone.com/articles/three-pillars-with-zero-answers-a-new-scorecard-for-observability)也写了一篇精彩的反驳文章。一家大型现任监控供应商推出了他们的“可观察性”平台，淘金热开始了。度量、日志、跟踪、监控和 APM 类别的供应商——甚至某些数据库公司——都开始将自己重新标榜为可观察性公司。公司被收购，产品在后台整合，营销资金源源不断。

2020 年:我个人决定不再谈论太多关于可观察性的技术定义，而是把重点放在能力上。重要的是技术如何改变我们作为一个行业的实践，对吗？

**2021:** 当下。很多人都在抱怨可观测性，但概念上却很少一致。

随后的 Twitter 帖子揭示了可观察性的许多冲突和/或互补定义中的一些——其中一些我完全可以接受和认同。我觉得别人(往好里说)对用户没用或者(往坏里说)有害。

让我们检查一下在这个线程中提供的关于可观察性的一些定义。提示我内心的学究！

*(一条已删除的推文):任何能让你洞察一个系统的东西都算可观察性。*

不。这个标准太低了。有什么能提供见解的吗？你是说我的那本《[Unix 环境下的高级编程》](http://www.apuebook.com/)算可观测性？再试一次。

*[Lorin Hochstein](https://twitter.com/norootcause/status/1415143107117555713?s=20) :可观测性是关于故障定位的。*

真的！可观察性不是调试你的代码。它是关于找出在系统中的确切位置来寻找你需要调试的代码。这一简洁的观点是正确的，但它可以使用更多的细节。

*[@austinlparker](https://twitter.com/austinlparker/status/1415134624116846593?s=20) :监控是监视器告诉我婴儿在哭，但可观察性告诉我为什么。*

伟大(如果怪异)的类比！它赞同视角的转变，即监控主要是运行第三方检查，而可观察性是第一人称叙述者。

萨姆·科伦:可观察性是建立系统和流程，以确保存在准确和可操作的数据来衡量绩效和诊断问题。它是关于训练人们知道如何检测他们的应用程序或者如何创建好的工作流来帮助他们解决实际问题。

当然，我想。但是像这样的定义也是有害的。实际上，这与监控有何不同？

*[道格·奥德加德](https://twitter.com/dodegaard/status/1415123092980977665):可观察性是一种关联的方式，可以减少人为关联的时间(用手仔细研究或查阅日志)。找到一个问题，然后深入研究另外两个问题。这是一个数据解决方案，也是 UX。*

哦，听起来像道格花时间与一个真正的观察工具！这确实是实践中最常见的可观察运动之一。

*[@Network_Guy](https://twitter.com/Network_Guy/status/1415124840860708870) :可观察性让我能够在比单个实体监控更深的层次上理解我的应用在做什么。*

没错。但是…怎么做？为什么？

*[凯文·帕森斯](https://twitter.com/KevinOfComputer/status/1415140912770912260?s=20):监控和 Nagios 这种无聊的老东西联系在一起。可观测性更亮更酷。它们都是流行语，我看不出它们之间有什么有意义的区别。*

这是我为什么需要写这篇文章的一个极好的例子。凯文，我希望你在看书！

然后 Liz Fong-Jones 也加入了进来。

*[Liz Fong-Jones](https://twitter.com/lizthegrey/status/1394697228178972676?s=20) :可观测性不是二元状态；这需要长时间的努力。这是一种快速展现相关数据以解决性能回归、了解系统工作方式或代码行为以及解决事件的能力。可观察性使用仪器来帮助提供上下文和洞察力，以帮助监控。虽然监控可以帮助您发现问题，但是可观察性可以帮助您发现原因。*

优等生回答，莉兹！

(一条已删除的推文):可观察性不是关于任何特定的工具或数据结构，而是关于对系统的洞察。

我特别想和最后一个人说话。因为这是真的。但它也含糊得可笑。可观察性是关于*成功*洞察系统。这就是我们如何达到目标的*方式——这就是可观察性的重要之处。*

## 可观察性是由你实际能做什么来定义的

阅读上面的各种观点实际上对我来说是鼓舞人心的，因为绝大多数的回复者已经将两件重要的事情内在化了:

1.  可观察性本质上不同于我们的监控传统，并且
2.  它是不同的，因为它帮助你解释和理解系统的内部运作。

有几十种，也许几百种不同的方法来创造细微差别，以达到对你有用的定义。同样，DevOps(至今！)与这个术语没有真正公认的定义这一事实作斗争。因此，一个团队的实践是 DevOps，而另一个团队的实践(看起来*一点也不像*第一个团队的)仍然是 devo PS——这让任何旁观者都感到困惑。然后，供应商可以很容易地在任何东西上贴上 DevOps 标签，显然没有人知道。毕竟还是 DevOps！

与其描述所有不同的方面和实现，这可能是无益的模糊或弊大于利，不如我们把重点放在功能上？你能用可观察性做哪些*实际上做不到的事情？*

这是我对可观察性的定义，值得一提的是:

> 可观察性让你找到未知应用问题的答案。如果您可以从外部询问系统的任何问题，了解系统进入的任何状态，无论多么离奇或新奇，而不需要发送任何新的定制代码来获得答案，那么您就拥有了可观察性。

我喜欢这个定义，因为它与机械工程和控制理论的定义非常接近:

*可观测性是通过检查系统的输出来测量系统内部状态的能力。如果一个系统的当前状态可以仅通过使用来自输出的信息来估计，则该系统被认为是“可观测的”。*

想象一下:你刚刚部署，一些奇怪的事情正在发生。这个异常看起来不像你以前遇到过的任何问题。你能迅速弄清楚发生了什么吗？你能在不进入机器的情况下做那件事吗？您能在不添加任何新的定制指标的情况下做到这一点吗？您能做到这一点而不在新的变更和重新部署周围喷洒一堆万福玛利亚日志行吗？

如果您用来理解该系统的工具是指标、静态仪表板和日志聚合器，那么可能不是。这些工具是为了根据已知的好或坏的状态来测量您的系统，并告诉您现在生产中是否发生了好或坏的事情。

它们不是为了调试全新的问题而构建的，你甚至不知道通过系统地跟踪线索，通过切片和切块遥测数据在多个维度上进行比较，以及通过挖掘实时发生的事情来识别异常值并找到相关性可能会出现的问题。

我喜欢关注定义可观察性的能力的原因是，如果你接受了寻找未知答案的定义，那么你不可避免地也必须接受实现这个目标有一定的技术前提。为了理解任何未知的内部状态，任何[可观测性工具也必须支持](https://www.honeycomb.io/blog/so-you-want-to-build-an-observability-tool/):

1.  **任意宽度的结构化原始事件**:一个如此精细的构建模块，你可以在任何需要的维度上分割你的遥测数据，以找到系统异常的最小共性。
2.  **上下文通过执行路径**持久化和排序:您需要检测您的代码，以便您持久化唯一的请求 id、跟踪 id 和从服务到服务的任何重要上下文，以便您可以跟踪请求，以便稍后在切片和切块时，您将能够关联请求之间的模式。
3.  **没有索引或模式**:因为你不能为你不知道将来要寻找的东西预定义优化——数据检索必须在任何时候对所有数据都是快速的。([你几乎必须有一个柱状商店](https://www.honeycomb.io/blog/why-observability-requires-distributed-column-store/)才能实现可观察性。)
4.  **高基数和高维度**:因此，您可以无限制地分割数据。您必须能够不受大多数传统数据库的约束来处理数据。
5.  **客户端动态采样**:因此，对于规模最大的用例，典型的遥测数据涓涓细流可能很快变成汹涌的洪水，您可以在保持足够的可观测性数据以进行适当调试的同时，不破坏您的底层系统。
6.  **一个探索性的视觉界面，可以让你任意切割和组合尺寸**:人类是视觉动物，我们天生就能在茫茫噪音中找到模式。视觉界面帮助我们在探索未知问题时快速筛选出重要的信号。
7.  **接近实时**:您必须在几秒钟内得到答案，因为当生产服务停止时，没有人有时间等待几分钟的结果。

我会第一个承认:也许我错了！也许不需要很高的基数就能得到未知——未知问题的答案。也许您不必使用任意宽的结构化数据 blob 来关联一组事件之间的上下文细节。也许你知道该怎么做。

太好了！我很想听听这件事！来推特上找我吧。

这难道不是一个更有用的论点吗？我们怎样才能达到这些效果呢？我们如何在这些新方法的基础上构建更多来理解我们的系统？

## 可观察性必须是一个明确的概念

许多人似乎已经得到了这样一个备忘录:可观测性是关于理解你的系统。太好了！现在，他们只需要对所需的能力有足够的了解，这样他们就能看穿那些在瓶子上贴着“可观察性”标签，却没有实际方法来实现它的人。

(我也在看你，“可观测性工程”团队旋转了普罗米修斯，添加了一些日志和仪表板，然后就收工了。我每周都收到你们软件工程师绝望的来信。仅仅因为你称之为可观察性并不意味着它就是可观察的。)

当把可观察性作为一组能力来讨论时——仅仅通过分析系统发出的数据来理解任何新的、奇怪的和以前未知的故障——你就可以开始明白为什么可观察性如此受欢迎了。

系统过去常常以相当可预测的方式失败。在存储之前，指标剥离了所有的上下文，或者您不能深入仪表板并询问“*…然后呢？然后呢？*“您无需深究就能理解故障可能发生在哪里。你可以通过从外部监控情况来检查问题。

你有应用程序、网络和数据库。绝大多数的复杂性存在于应用程序中。如果所有这些都失败了，你可以把 gdb 附加到应用程序上，然后一步一步地通过它。那时，我们知道去哪里寻找问题。

但是微服务将许多复杂性从应用中挤出，进入系统空间。现代系统现在是数据库和存储类型、无服务器功能和第三方 API 的大杂烩。在当今的应用程序体系结构中，新奇而怪异的局部故障并不罕见。你有未知的-未知的早餐。

在当今世界，我们需要改变我们系统地寻找问题真正根源的思维方式。几十年来，我们告诉自己这就是我们正在做的。但事实证明，我们的大多数“调试”都是通过直觉完成的，或者通过可能潜伏着故障的半打组件进行推理。

现在吗？忘记将 gdb 附加到应用程序。你甚至不知道这个集群中的几十个短暂的应用实例中的哪一个会遇到问题。或者它是这个实例上游或下游成百上千个实例中的一个。

这就是为什么“可观察性”很重要。我们需要一个术语来概括所有这些更新的、非常现代的工具和最佳实践，这样人们就可以找到他们真正需要的工具。我们不需要遥测、监控或任何我们已经使用了几十年却无法解决当今问题的工具的另一个同义词。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*