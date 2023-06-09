# 威瑞森领域中间层的 DCOS 部署更灵活的应用

> 原文：<https://thenewstack.io/verizon-deploys-mesophere-dcos-make-applications-nimbler/>

电信巨头威瑞森正在测试 Mesosphere 的[数据中心操作系统](https://mesosphere.com/product/)，作为管理可扩展应用程序的潜在新方法。

DCOS“是我们如何在内部集群上编排容器的基础软件，”威瑞森实验室架构和基础设施主管[劳伦斯·劳](https://www.linkedin.com/in/larry-rau-620831)说。根据 Rau 的说法，DCOS 在美国威瑞森的许多数据中心运行。

该公司计划在容器内运行各种工作负载，如移动应用和物联网类型系统的后端支持、视频服务以及数据处理和分析。

Rau 说，推动向容器转变的是“更快速地提供新解决方案”的愿望。

迄今为止，该公司已经有了多种构建和部署应用程序的环境。应用程序开发团队必须在数据中心内找到一些硬件来运行他们的创作。开发人员还必须为应用程序规划一个增长周期。“所有这些计划都必须进行，”劳说。

这导致相同的应用程序通过相同的进程运行，这非常耗时。如果你退后一步，能够让所有这些变得通用，应用团队就能更专注于他们需要提供的解决方案，”Rau 说。“我认为整个行业正朝着这个方向发展。”

在调查 Mesos 的同时，威瑞森还试图尽可能地标准化其数据中心的硬件，以支持可扩展的工作负载。Rau 说，通过这种努力，“你可以全面地审视一系列应用程序的需求”。

威瑞森不必担心多租户——当然，它的工作负载填满了整个数据中心——“所以我们不想产生虚拟机的成本，”Rau 说。“运行虚拟机只是另一件需要管理的事情，因此如果您消除了复杂性以及软件开销，这是一件好事。”

因此，在威瑞森的服务器运行 Linux 的地方，容器可以为可扩展的工作负载提供基础。Rau 说，容器具有“足够好的”隔离和运行内部应用程序的功能集。Docker 提供了一种通用的图像格式，以及一种移动图像的标准方式。

下一个问题是如何协调许多容器的部署和管理。在这里，该公司研究了 DCOS 的基地 Mesos。这是在 [Kubernetes](/category/kubernetes/) 达到其 1.0 里程碑之前。Docker Swarm 甚至还没有发布。

Rau 说，即使在早期，从加州大学伯克利分校开发的早期开始，Mesos 在基本功能方面已经“相当成熟”。"它有很好的概念基础."该软件与威瑞森的硬件计划以及它希望如何管理其应用程序非常吻合。另一个标志是一些组织已经大规模部署了 Mesos。

只有在威瑞森开始使用 Mesos 之后，它才联系了为软件提供支持的 Mesosphere，并将威瑞森升级到完整的 DCOS 套件，该套件提供了许多额外的功能，特别是通过[马拉松](https://mesosphere.github.io/marathon/)调度程序，如服务发现和高级网络支持。

本质上，威瑞森和其他 DC/操作系统用户不必像早期的 Mesos 用户那样为了从 Mesos 进入一个功能系统而重新发明轮子，”Mesosphere 高级分析师 Derrick Harris 在后续的电子邮件中指出。

在威瑞森还有很多其他地方可以使用 DCOS，尽管 Rau 怀疑它是否会成为这个电信巨头管理所有应用程序的单一点。“我不能说任何一个解决方案将是整个威瑞森事实上的解决方案，”劳说。

英特尔赞助了这个故事。中间层是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>