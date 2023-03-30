# Mesosphere 社区版现在在 AWS 上，接下来是 Google 和 Azure

> 原文：<https://thenewstack.io/mesosphere-community-edition-now-on-aws-google-and-azure-up-next/>

Mesosphere 高管向新堆栈证实，第一个基于集群、面向容器的操作系统 Mesosphere DCOS 的社区版正可供客户部署在亚马逊的 AWS 平台上。作为用于内部部署和混合云部署的商业版 Mesosphere，它退出了公测，进入了正式发布阶段。

“这是没有限制的。“这是一个非常强大的软件包，”中间层高级副总裁马修·特里费罗说，“而且是免费的。我们还接受谷歌云平台和微软 Azure 的早期接入申请。”

Mesosphere 利用 Apache Mesos 调度程序来协调相关和不相关进程在不同服务器集群上的分布。随着 community edition 的首次发布，这种分发将在 Amazon 的服务器上进行，尽管从技术上来说，该系统旨在跨云扩展基于容器和微服务的部署。一旦 Google 和 Azure 许可变得普遍可用，可以想象所有三个公共云都可以被一个集群调度器同时利用。

Trifiro 说，企业版将支持所有三个现成的云提供商，以及使用任何主要 Linux 发行版的内部环境。“它将在 VMware 或 OpenStack 上的虚拟化环境中运行，也将在裸机上运行，”他补充道。

## 提高利用率曲线

Mesosphere 首席执行官 Florian Leibert 说，Kerberos 安全性将首次在企业版中提供。这将增加认证和身份。它还将使 DCOS 能够强制执行限制特定用户访问应用程序和资源的策略。

Leibert 解释说，在极其复杂的部署中，DCOS 的最终 GA 版本将通过使用高级调度算法来提高利用率，从而证明其价值。Leibert 说，这些算法是通过去年 9 月 Mesosphere 收购标准大学教授克里斯特斯·科兹拉基斯的服务而获得的。在斯坦福大学期间，Kozyrakis 教授领导了其[多尺度架构和系统团队](http://web.stanford.edu/group/mast/cgi-bin/drupal/)，Trifiro 表示，这为 Mesosphere 铺平了道路，特别是在将规模资源消耗减少到最少节点数量的能力方面。

“在当今典型的数据中心中，所有不同的集群平均只能获得 8%到 15%的利用率，”Trifiro 说道。“低得可怜。您的服务器中可能有 80%到 85%被完全浪费了，因为您为峰值负载过度调配了它们。任何多余的容量都没有得到利用，因为所有的东西都在静态分区中。”

他说，这个问题在 DCOS 得到了解决，通过使用部分源自 Kozyrakis 工作的调度和分配算法，最大限度地利用了现有资源。他说，当工作负载具有所需的 SLA 目标时，必须确保资源在需要时的可用性，而群集中的其他工作负载可能会在较低优先级、尽最大努力的基础上处理，例如，无论如何预计会消耗 24 小时的分析作业。

Trifiro 解释说，有了 DCOS，一个较低优先级的进程可以被分配在全天可用的空闲容量上运行，并且每当一个较高优先级的工作负载需要满足 SLA 承诺时就会暂停。这个概念被称为“过度订阅”(不可避免地，某处的一些系统构建者将它比作超频)。“它允许您在群集上运行比理论上您的群集在给定保证的情况下所能处理的更多的工作负载。

“因为我们的调度器和分配器实时知道实际使用的是什么，”他继续说道，“任何空闲容量都可以用于这些尽力而为的工作负载。”他说，他看到 DCOS 调度的集群的利用率是传统工作负载分配的三倍，尽管添加超额订阅功能可以将典型利用率从不到 15%一直提高到 90%以上。

“我们有一个客户经常以 95%的利用率运行，”他指出。

Leibert 说，在过去的一年里，Kozyrakis 教授开发了一种机器学习算法，利用运行进程和工作负载的历史性能数据，来预测它们未来的行为和使用模式..这是对底层 Mesos 层使用的“加权主导资源公平性”算法的补充。

“批量分析工作负载可能永远不会是高优先级的，”他说，“因为它是面向用户的，比如你的 Web 层。我们将为两者分配不同的权重，这意味着，如果到了紧要关头，您不得不放弃一个工作负载，因为您刚刚用完容量，实际上资源调配不足…您需要制定某种行动计划。在我们的案例中，该行动计划归结为对不同类别的应用程序进行简单的权重分配，因此您可以关闭您的分析集群，以便启动更多的 Web 层。您可以随时在以后运行分析。”

## 填补安全漏洞

Leibert 为增加的 Kerberos 安全层提供了一个用例:

假设客户是一家对冲基金，其办公室运行专有交易算法。公共云或混合部署可能会将这些算法的神圣性置于风险之中。

对于集群操作系统，理论上存在这样的能力，即集群之外的服务器看起来已经加入了集群，并且暴露了算法背后的数据结构。从那以后，对于一个聪明的开发人员来说，倒推公式来提取算法本身可能是微不足道的。

“因此，当你需要提高安全级别时，我们允许你插入 Kerberos，在那里你基本上拥有所有可用机器的注册，”Leibert 向我们解释说。“所有人都有一个秘密，他们可以授权自己。现在，DCOS 只允许你的个人电脑在获得授权的情况下加入群体。”

这位首席执行官随后分享了他亲身经历的另一种情况，默认情况下，Hadoop 集群只允许添加节点，而不会怀疑是谁或什么在添加节点。[换句话说，不管出于什么疯狂的原因，Hadoop 在默认情况下并不安全](http://hadoop.apache.org/docs/r2.7.0/hadoop-project-dist/hadoop-common/SecureMode.html)。因此，Mesosphere 有效地将受限访问的能力重新插入到 Hadoop 进程中。

“你现在可以授权谁可以运行哪个应用程序，或者谁甚至可以成为 DCOS 集群的一部分，”Leibert 说。

Matt Trifiro 解释说，为了正确地自动化调度决策，编排者每次都必须根据具体情况权衡这些和其他几个属性:例如，功耗限制、硬件的现有相对利用率水平、工作负载及其数据的首选位置、使用加速器芯片的硬件的首选位置、与本地数据的首选接近度，以及参与集群的数据中心的确定安全级别。他说，这些决定最好留给别人，而不是人类。

“人类实际上非常不擅长大规模和实时的推理，”特里费罗说

通过 Flickr Creative Commons 的特色图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>