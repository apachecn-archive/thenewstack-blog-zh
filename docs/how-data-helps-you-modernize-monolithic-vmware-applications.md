# 数据如何帮助整体式 VMware 应用程序实现现代化

> 原文：<https://thenewstack.io/how-data-helps-you-modernize-monolithic-vmware-applications/>

[LogDNA](https://logdna.com/) 赞助本帖。

随着云原生应用变得越来越普遍，企业正在寻求将类似的架构和服务引入其传统的单片应用。将单一应用程序容器化在许多方面有利于 IT 组织，包括更容易与微服务集成、扩展能力以及最终更好的最终用户体验。像集中式日志管理这样的 DevOps 工具对于帮助用户管理现代化应用程序带来的大量数据至关重要。

## 什么是单片应用程序？

整体应用程序是一个系统，它将核心业务逻辑、用户界面、数据层、API 和应用程序的所有其他方面结合在一个紧密耦合的生态系统中的同一个堆栈上。这种类型的应用程序通常在虚拟机或裸机服务器上运行整个堆栈，有时作为一台机器上的单个租户。虽然 monolith 可以部署在基于云的平台上，但与云原生架构相比，它的性能通常很差。

## 原生云:微服务及其他

微服务架构是一个完整的生态系统，其中应用程序的每个组件(服务)都解决业务需求或功能，而不是根据其在系统中的用途来定义。因此，在讨论微服务时，我们通常指面向业务的 API，或者用业务术语定义的 API。像 OpenShift 上的 VMware 这样的容器化架构本质上是一种微服务架构，专注于为每个服务提供轻量级环境。无服务器架构更进一步，将应用程序简化为定义核心业务逻辑的功能。所有这些架构统称为云原生架构。

## 为什么选择云原生？

 [劳拉·圣马利亚

作为 LogDNA 的开发者倡导者，劳拉·圣马利亚喜欢学习和解释事物是如何工作的。她在外部开发人员、sre 和内部工程团队之间架起了一座桥梁。](https://www.linkedin.com/in/lauraasantamaria/) 

云原生系统有很多好处。首先，您可以在整个生态系统中一致地重用组件，而不是仅仅重用代码库中的函数或类。结果，代码库缩小了，整个系统变得更加灵活(尽管不一定更简单)。其次，由于能够在服务级别添加冗余，您可以在对生态系统其余部分影响最小的情况下重启服务，尤其是在系统内部和周围的数据流方面。这种能力也支持更快的扩展。第三，您有了一个更快的发布和部署路径，因为您已经有了一个绘制出来的数据流框架。在一个容器中，您所要做的就是确保传入和传出的传输是匹配的。最后，云原生架构经过了更好的优化，可以针对整个系统中的每个用例使用最佳的堆栈类型，从使用针对数据库的快速读写而优化的计算系统，到使用针对归档的大小和成本而优化的冷存储。

 [马修·约翰逊

Matthew 是 IBM Cloud for VMware 解决方案的产品经理。](https://www.linkedin.com/in/matthew-johnson-956a855b/) 

关于从单一架构迁移到云原生框架，要记住的一件大事是理解数据是如何在系统中流动的。您可以认为这是您的业务需求，但实际上这是关于了解数据来自哪里，它需要如何从一个逻辑步骤转换到另一个逻辑步骤，它何时需要保持在一种状态并持续多长时间，以及当它离开应用程序时需要什么样子。这种思想上的根本转变可能是从 monolith 到 cloud native 的转变如此令人生畏的原因——除了纯粹的工作量。

## 从巨石开始

理解数据在你的 monolith 上的流动从检查你的日志开始。当查看 VMware 上单一应用程序的日志时，您可能会看到来自应用程序、平台和系统的日志，从操作系统一直到硬件堆栈。从应用程序开始，堆栈的每一层都保持其数据与其他层完全隔离，只传递关键的数据。过去，您必须安装 vRealize LogInsights 并在 VMware 上自行管理，才能查看这些应用程序日志。

## 转向集装箱化

从整体架构转移到容器化架构需要制定一个计划，通过删除旧组件和识别新组件来优化您的系统，然后部署和维护您的堆栈。既然你已经理解了数据在你的 monolith 上的流动，你可以从一个计划开始。

### 想办法

在这一点上，您可能已经很好地意识到您的整体中的哪些元素可能是服务，但是如果您不知道呢？当您从单块应用程序中打开日志时，您应该开始看到随着时间的推移，在特定时间点流入和收集的数据的模式。当你看到这些收集点时，确定这些点是否映射到商业价值，它们是否一次又一次地做同样的事情，以及它们是否是数据流中的自然中断。假设它们是，您可能已经确定或验证了哪些元素将被视为服务的假设。

### 例子

假设您正在将一个单片 VMware 应用程序迁移到 IBM Cloud 上的微服务架构中。您可以在 monolith 中使用 vSphere 来确保应用在开发人员发布新更新时能够顺利运行。由此，您确定业务需求是系统监控，并找到满足该需求的云服务——比如 IBM Cloud Availability Monitoring。

### 开发新功能

一旦创建了数据模式的映射，就需要考虑新的架构可能如何删减组件，或者需要向多少新的 API 公开服务。您从日志中收集的数据应该确定新服务的入口和出口在哪里，以及它们需要如何访问数据，就像您的 monolith 可能如何将数据暴露给外部世界一样。

让我们看看我们的示例应用程序。您将需要设置一个 API 来连接到您的数据库容器及其永久存储卷。OpenShift 通过允许您公开内部服务，使入站和出站连接变得简单，内部服务不同于外部路由，因为它们只能在应用程序的生态系统中使用。

### 部署和维护您的新系统

现在你可以开始使用这个新系统了。部署和维护新容器化的应用程序与单一的应用程序略有不同。您将不再需要仅为您的应用调配虚拟机管理程序和启动虚拟机。除了持久存储之外，您将不再拥有长期运行的系统。例如，不需要进入虚拟机管理程序来更新操作系统，您通常只需重新启动容器，跳转到下一个最新的可用服务器。

因此，你的日志看起来也会有很大的不同。您需要更多地依靠您的应用程序日志。如果您可以访问您的那部分集群，您就可以访问您的 OpenShift 日志。然而，您不太可能看到那么多的操作系统日志，因为您自己不会维护这些日志。这种维护由您的云提供商负责。但是，您需要的一件事情是日志聚合和管理。您将突然拥有更多的信息，因为您现在有多个运行在装满容器的容器上的服务——所有服务都在它们之间不断传递数据。像 IBM Log Analysis with LogDNA 这样的服务可以帮助您维护集群，当您很忙的时候，可以更容易地搜索您的日志，并且当出现新的部署配置时，可以看到系统数据流是如何重新构造的。

## 结论

现代化您的 VMware 应用程序使您能够轻松集成许多云原生工具，从而更好地了解您的环境。像 IBM Log Analysis with LogDNA 这样的 DevOps 工具可以帮助您理解数据是如何在系统中流动的，这样您就可以放心地开发和调试新容器化的应用程序。

VMware 是新体系的赞助商。

来自 Pixabay 的 8926 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特(Twitter)或脸书(T2)与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[反馈@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>