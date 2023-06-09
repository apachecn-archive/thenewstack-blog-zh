# 第 1 部分:操作化企业开发人员

> 原文：<https://thenewstack.io/operationalize-the-enterprise-developer/>

[](https://www.linkedin.com/in/johnmarkwalker/)

 [约翰·马可·沃克

约翰是第一资本公司开源项目办公室的主任。在加入 Capital One 之前，John 是开源协作的长期实践者和倡导者，在 Red Hat、EMC、Gluster、Hyperic 和 SourceForge 领导开源工作。](https://www.linkedin.com/in/johnmarkwalker/) [](https://www.linkedin.com/in/johnmarkwalker/)

开发商，开发商，开发商！

自从技术供应商在技术领域变得越来越有影响力以来，他们就一直在尖叫着要更多的开发人员。是微软在 20 世纪 90 年代创造了“开发者生态系统”这个词。这种开发者环境成为推动微软发展的基础，使其成为全球科技公司羡慕的巨头。从那时起，每一家大型技术公司都梦想拥有开发者空间，以及随之而来的影响力和塑造企业平台未来的重心。

许多公司已经将这种屡试不爽的策略转化为成功。微软创建了一致的 API 和丰富的开发人员文档，以便成千上万的顾问和独立软件供应商能够在微软巨大的操作系统市场份额上建立客户基础。 [VMware](https://tanzu.vmware.com?utm_content=inline-mention) 为开发人员创造了一种简单的方法，让他们可以直接从工作站构建和部署应用，而无需吝啬的运营人员的干预。苹果创造了世界上最成功的小型设备操作系统 iOS，并利用其杠杆作用将其第三方市场转变为维持其持续增长的市场力量。亚马逊创建了一个大规模的计算基础设施，让开发者对他们的软件开发生命周期有更多的控制权，建立了一个充满活力的科技园，一百万家初创公司在这里成长。所有这些例子都有一些共同点:

*   他们利用开发者来围绕他们的领先平台建立一个不断增长的重心
*   他们帮助解决了开发人员最大的痛点
*   他们允许开发人员为各自的雇主缩短价值实现的时间——并且他们运营第三方开发人员

## “可操作化”在这种情况下意味着什么

对于任何开发者关系项目来说，关键的问题都很简单:开发者能使用你的工具在更短的时间内交付更多的价值吗？

这个问题看起来比较简单，但是我们来考察一下它没有问什么。许多供应商为开发人员开发了时髦的、令人惊叹的工具，但最重要的因素是一个引人注目的平台(开发人员实际上想要使用的)和更短的价值实现时间。在这些情况下，平台吸引了开发者，他们以一种共生的关系推动平台的增长，这种关系形成了一个正反馈循环。

作为一家没有开发者的科技公司，你能成功吗？当然，但是上面的例子展示了巨大的成功——如果没有强大的开发者社区，很难想象会有这样的成功。可以肯定地说，你对开发人员的操作能力意味着是适度成功还是大大超出预期。开发者的重要性显著增加；在技术王国的世界里，企业开发人员是国王的创造者。

这就引出了一个问题:企业开发人员想要什么？

企业开发人员想要强大和简单。他们希望工具能够减轻他们的痛苦，并允许他们专注于编写代码，而不会有太多的开销。但是，2021 年的企业开发人员面临着太多的选择、越来越多的复杂性和太多的开销。

今天的开发者市场是开发者体验雷区中平台和工具的有趣组合。今天的企业开发人员使用旧的软件库，因为尽管存在潜在的漏洞，这些旧的库仍然可以工作。因为每个人都采用了 DevOps 原则，所以他们都背负着长期维护应用程序的重担，结果处理了大量开销。

在“你构建它，你拥有它”( YBYO)的世界中维护他们的应用程序的同时，他们还解决了与其他数百个独立团队同时解决的公共库相同的问题。例如，每个受特定库中的错误影响的开发团队将花费时间手动修补和修复软件。

因为供应商没有解决开源的可持续性问题，他们没有优先考虑上游的修复——大多数大公司还没有想出如何将上游的修复集成到他们的日常工作流程中。“写一次，到处跑”的口头禅变成了“写一百次，部署一百次，修复和补救一百次。”选择的悖论将企业开发人员引上了一条他们既崇拜又厌恶的道路。

复杂性通常与大规模计算密切相关，但是可以做很多事情来改善开发人员的体验。

## **实施这个**

让我们回到中心论题:如何操作企业开发人员。回到之前的理论，一个引人注目的平台和开发者生态系统会带来巨大的成功，那么一个成功的开发者平台会是什么样的呢？它将:

*   自动化开源库的使用和维护。开源库已经存在。不可否认，它促进了开发的速度，并提供了一种简单的方法来减轻许多贡献者的风险。
*   提供一组通用的构建块和平台。说起来容易做起来难，对吧？有两种基本方法:要么创建一个为开发者提供兼容层的抽象，要么推出一个赢得市场的核心平台。历史告诉我们，后一种方法更成功。在当今时代，任何不包含或不基于亚马逊网络服务的应用构建模块都面临着巨大的挑战。
*   为大规模管理应用程序提供通用框架。是类似[临界栈](https://www.capitalone.com/tech/solutions/container-orchestration/)的 Kubernetes 变种吗？

看看现在的计算环境，任何给定的解决方案都可以减轻开发人员的痛苦，同时允许他们更快地交付价值。看起来最简单的途径是一个利用云基础设施的平台，通过无缝集成到他们现有的工具和工作流中来赢得开发者的心。简而言之，赢家将是云加速器。

考虑到缺乏全面的开发人员体验解决方案，甚至没有一套可靠的构建模块来快速组装解决方案，我们能做什么？*我将在我的下一篇文章中讨论这个问题……*

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>