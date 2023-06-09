# 开发人员职业的未来

> 原文：<https://thenewstack.io/the-future-of-developer-careers/>

[](https://www.linkedin.com/in/christineyen/)

[Christine Yen](https://www.linkedin.com/in/christineyen/)

[Christine 是 Honeycomb.io 的联合创始人兼首席执行官，honeycomb . io 是工程团队通过可观察性了解其生产系统的工具。她喜欢作为一名开发人员呆在一个满是运营人员的房间里，并且非常关心通过技术和文化的改进来弥合开发人员和运营人员之间的差距。在 Honeycomb 之前，她在 Parse 和脸书建立了分析产品。](https://www.linkedin.com/in/christineyen/)

[](https://www.linkedin.com/in/christineyen/)[](https://www.linkedin.com/in/christineyen/)

虽然 JavaScript 框架来来去去，但在过去的几年中，一种变化正在酝酿，这种变化将永久地改变对现代开发人员的意义:我们的代码如何从我们的笔记本电脑转移到野外。容器、微服务和流程编排的广泛采用使得开发一个小软件并把它推到用户面前变得比以往任何时候都容易——这样做的同时，把一大堆舒适的任务(调试、分析)推到了不舒适的领域:生产。

我讨厌带来坏消息(不尽然)，但是对开发人员来说，现实是确保你写的代码仍然工作只会变得越来越复杂。承担您编写的代码的操作责任正在成为开发人员角色中越来越大的一部分——即使“它运行的地方”离“它编写的地方”越来越远

开发运维的第一波浪潮主要体现了运维人员学习如何开发:通过代码“自动化一切”。自然，第二波是关于开发人员学习如何操作的:现在，我们拥有在生产中运行我们的代码。但是，尽管这两种转变通常在跨职能开发运维团队中同时出现，但“理解生产”在历史上一直带有严重的运维偏见。

这几乎是讽刺，真的——平台抽象的最新趋势已经把一切都变成了代码。(嗨，无服务器！谢谢你，赫罗库。)那个*应该有*的意思是*理解*生产中发生的事情对开发者来说会更容易，而不是更难。让我们来看看为什么没有出现这种情况，以及应该如何改变。

## 将开发人员硬塞进运营部门:会出什么问题？

领先的软件工程组织越来越多地要求开发人员在生产中拥有他们的代码。软件工程师被要求[加入随叫随到的轮岗](https://copyconstruct.medium.com/on-call-b0bd8c5ea4e0)，得到不同程度的支持。

然而，传统的“生产监控”工具天生就对开发人员思考和处理代码的方式怀有敌意。理解“生产”的传统方法依赖于应用程序的底层基础设施。CPU 利用率、网络吞吐量或数据库负载等数据图表是以基础设施为中心来了解世界的方式。仅仅因为开发和运营之间的界限继续模糊，并不意味着我们简单地转移到以前的思维模式上，开发运维的目标不是简单地交换职责。转移到 DevOps 的目标是最大限度地利用构成这些新的跨职能团队的各种技能、背景和心态。

传统的生产监控工具是在开发运维时代之前很久编写的——它们说的是运维语言，而不是开发语言。不幸的是，这给开发者设置了一个人为的障碍，让他们认为生产是他们拥有的*。我们没有做任何事情来帮助开发者看到他们在生产中的世界。开发人员经常会得到一个仪表板，上面满是 Cassandra 读/写吞吐量图、线程数和内存表大小，好像这样就能让他们加入产品所有权俱乐部。*

 *当然，这些指标和图表看起来很酷——但是通常没有办法将这些信息与代码、业务逻辑或软件开发领域的客户需求联系起来。当问题发生时，在看到这些信息并将其与“实际发生的事情”联系起来之间存在着一个巨大的心理跳跃。即使这种跳跃可以以某种方式实现，也肯定没有任何途径可以复制任何观察到的现象，更不用说编写代码来修复它了。

传统生产监控工具要求开发人员进行的认知飞跃没有得到太多关注，因为对于运营工程师来说，这只是简单的做事方式。在工程的某些方面，开发人员现在不得不做出这样的飞跃，这是一种自鸣得意的满足感。感受我们的痛苦，德夫斯！你怎么不知道当这两条线都下降，图形变成红色，这意味着你的应用程序已经用完了内存？欢迎来到制作现场。

这种漫不经心的态度强化了传统监控工具所反映的敌意。在实践中，这种方法无意中导致了这样的情况:开发人员只是简单地跟着面包屑走，尽最大努力复制他们并不完全理解的生产调试模式。从文化上来说，它在 Ops 重视的方法和 Dev 重视的方法之间创建了一条护城河——并且强化了生产对开发人员来说是一个充满敌意的地方的错觉。

## 增强现有的开发行为

相反，一种更受欢迎的方法是利用我们开发人员在调试时自然做的事情:允许我们快速比较预期结果和实际结果(例如，这段代码应该处理 10K 请求/秒，但似乎只处理 100 请求/秒)。开发人员与他们的行动伙伴分享这部分调查旅程。然而，当深入理解*为什么*会出现偏差时，运营和开发模式就会出现偏差。

对于开发人员，我们在测试套件中一直比较“预期”和“实际”。调查测试失败意味着挖掘代码，遍历逻辑，并质疑我们的假设。能够在生产中捕获业务逻辑级别的元数据(通常基数较高，通常跨越多个维度)是能够利用开发经验解决生产问题的基本要求。

我们需要一个特定的可复制的测试案例。能够利用自定义属性(如 userID、partitionID 等)的特性，使生产感觉像是开发和测试工作流的扩展，而不是一些新的陌生和敌对的环境。

## 开发人员的生产方式

随着 PaaS、IaaS 和无服务器的出现，我们的世界越来越抽象化基础架构。这为两次 DevOps 浪潮铺平了道路，也为重新定义优先级腾出了空间。对于拥有在 prod 中运行代码的软件开发团队来说，这意味着他们已经转向将他们对成功运营的定义与最终对业务重要的东西结合起来——该软件的用户是否有良好的客户体验。

对于习惯于让函数、端点、客户 id 和其他业务级别的标识符自然地存在于他们的各种测试中的开发人员来说，这种转变非常有效。在调查和理解生产系统的行为时，这些类型的标识符只会变得越来越重要。(相比之下，传统监控系统关注整个系统的总体行为，几乎从不包括这些类型的标识符。)

开发人员*应该*询问的关于生产的所有问题都可以归结为两种基本形式:

*   我的代码首先运行了吗？
*   我的代码在生产中的表现是否符合预期？

作为一名经常进行部署的开发人员，我想知道的关于生产问题的头几件事是:它是什么时候开始发生的？哪栋建筑现在或曾经是活？当时哪些代码变化是新的？我的代码运行的条件有什么特别的吗？

将某些信号与特定的构建或代码发布相关联的能力对于寻求产品的开发人员来说是至关重要的。并非巧合的是，“build ID”正是传统监控工具警告不要包含的那种“无限源”元数据。在基于指标的监控系统中，这样做会导致捕获无限增加的指标集，对监控系统的性能产生负面影响，并且会带来额外的“好处”,即向监控供应商支付更多费用。

特征标志——以及当多个活动特征标志交叉时可能参数的组合爆炸——为回答问题 1 增加了额外的麻烦。然而，功能标志仍然存在；所以我们的工具和技术必须升级以支持这个更加灵活定义的世界。

另一方面，问题 2 是我们每次运行测试套件时都会问的同一个问题:“我的代码的实际执行与我期望的匹配吗？”当我们挖掘失败的测试用例时，对我们有用的相同信号帮助我们理解、再现和解决在生产中识别的问题。

开发人员调试 prod 的方法意味着能够通过端点、功能、有效负载类型、响应状态或任何其他用于定义测试用例的任意元数据来隔离代码的影响。开发人员应该能够利用这些片段，了解他们的系统处理的真实工作负载，然后[相应地调整他们的代码](https://thenewstack.io/a-next-step-beyond-test-driven-development/)。

## 前进的道路:对开发者友好的产品

开发职业的未来不在于拥有不同的定制方法来调试您的生产环境。DevOps 旨在充分利用您的新跨职能团队，幸运的是，当涉及到使用工具来获得您在生产中关心的问题的答案时，我们有机会达成一致。无论你的团队自称是开发人员、运营人员、开发人员还是 SRE，你都可以使用说同一种语言的工具。

在当今的抽象世界中——一个充满短暂实例、瞬时容器和无服务器功能的世界——传统的基础设施指标正在迅速过时。这一切发生得如此之快，以至于它甚至让人质疑[未来的行动职业](https://thenewstack.io/the-future-of-ops-careers/)。对每个人来说，从根本上更好地理解生产是必要的。

良好的第一步是将注意力从 CPU 和内存等指标上转移，转而采用红色指标作为服务健康的主要信号。这可以大大降低大多数开发人员进入生产环境的门槛。然后，通过用客户 ID、API 端点、资源类型、客户行为等标记这些指标，开发人员可以用必要的元数据来理解任何给定图表的影响。它弥合了在 prod 中捕获指标和将它们绑定到代码和测试之间的差距。

更好的一步是，可观察性的流行程度出现了爆炸式增长。可观察性[不是监控](https://www.honeycomb.io/blog/observability-whats-in-a-name/)的同义词。可观察性采用基于事件的方法，仍然允许您[结合基础设施指标来理解您的生产系统的行为](https://www.honeycomb.io/blog/getting-metrics-into-honeycomb/)。对于以运营为中心的监控世界来说，这是一种完全不同的方法，可以理解生产系统的行为，使来自所有背景的工程师都可以访问它们。

开发职业的未来应该通过努力理解传统监控工具之间的相互关系以及它与您的代码的联系来定义。通过脱离传统的监控工具，开发职业的未来变成了理解 prod 中发生的事情就像理解代码在开发或测试环境中失败的原因一样自然。

在过去的十年和变化中，作为一个行业，我们都非常擅长获取代码并将其交付给用户。毕竟，这是 Heroku 的承诺:简单而神奇地将生产环境与开发人员的自然工作流程挂钩。正因为如此——因为我们已经将生产与开发环境紧密地联系在一起——开发人员的技能组合*必须*遵循同样的轨迹……否则就有被落在后面的风险。

*在 **[Honeycomb 的《开发可观察性文化指南](https://www.honeycomb.io/developing-a-culture-of-observability/?&utm_source=tns&utm_medium=blog-links&utm_campaign=referral&utm_content=developing-a-culture-of-observability-tns)** 中，了解更多关于让开发人员和运营人员更容易接近产品的信息。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*