# Kubernetes 上的云本机备份、灾难恢复和迁移

> 原文：<https://thenewstack.io/cloud-native-backups-disaster-recovery-and-migrations-on-kubernetes/>

[MayaData](https://mayadata.io/) 赞助本帖。

 [穆拉特·卡尔斯利奥格鲁

Murat 是一名基础架构架构师，拥有存储、分布式系统和企业基础架构开发方面的经验。他是 MayaData 的产品副总裁，也是 CNCF 项目 *OpenEBS* 的维护者之一，还是*Kubernetes——devo PS 食谱大全*的作者。](https://www.linkedin.com/in/muratkarslioglu/) 

数据越来越多地在 Kubernetes 上运行，并且越来越多地以支持云原生架构的方式运行。在最近的云原生计算基金会网络研讨会，[中，CNCF OpenEBS 项目的领导者和 MayaData 的联合创始人 Kiran Mova](https://www.linkedin.com/in/kiranmova/) 解释说，松散耦合的架构支持松散耦合的团队。好处是松散耦合的团队不受阻碍；他们能够在可能的时候进行迭代，摆脱会议、长发布周期、变更控制委员会等等的困扰。

这种松散耦合、基于工作负载的方法(称为**容器附加存储**)的一个含义是备份也必须改变。他们需要改变，因为治理模型正在改变(现在是小团队在负责)，也因为松散耦合工作负载的基础架构不同了。

那么，当数据被部署为大量松散耦合的工作负载，而不是几个集中管理的数据库时，会发生什么变化呢？

## **传统备份面临的挑战**

传统上，备份可以自下而上地执行，例如备份特定卷、Kubernetes 节点或虚拟机上的所有数据。

但是，如果不是一台服务器或一台 ESX 主机上有一两个工作负载，而是有 110 个或更多的 pod，会发生什么呢？这些 pod 中的每一个都运行一个工作负载，并根据需要由 Kubernetes 转移到其他节点？

答案是，如果您只能在集群级别进行备份，那么您的粒度只能是集群的粒度。然而，在您的环境中运行工作负载的小团队并不管理集群；他们管理工作负载。因此，如果他们需要恢复工作负载，他们必须让其他人来为他们恢复整个 Kubernetes 集群。然后，他们需要在该群集中进行分类，以找到他们需要的特定数据和应用程序。这就打破了这些小团队的控制和自主性，让所有人都慢了下来。这是一种共享的依赖关系，会将您的数据置于风险之中。

## **云本地按工作负载备份、灾难恢复和迁移**

相比之下，小型团队在支持容器连接存储的 Kubernetes 环境中运行其工作负载，并通过 MayaData 的 Kubera 提供数据保护。在这种情况下，每个小团队仍然控制着他们的工作量。如果他们觉得他们的工作负载需要被克隆，因为他们想对他们的生产数据的只读副本进行开发，他们可以这样做(假设 Kubernetes RBAC 控制允许)。如果这个小团队认为他们对 PostgreSQL 的特殊使用表明他们应该对主数据库集群进行跨 AZ 部署，并对另一个云进行流式或接近实时的备份，他们也可以这样做。他们还可以为他们的环境创作一个生产 PostgreSQL 的通用模式，并使该存储类成为他们所有部署的默认模式；甚至与他们组织中的其他人分享这种模式。

小团队做出决策和快速迭代的自主权是敏捷的基础。松散耦合的体系结构还需要将工作负载的状态从基础设施中分离出来。您的“每工作负载备份”应该能够将工作负载恢复或迁移到不同的云平台，即使该云平台具有不同的存储平台，否则，您将与底层平台紧密耦合。

此外，在许多组织中，平台团队需要能够看到平台的整体行为。根据我们的经验，平台团队的一些最重要的职责包括保护重要数据、随着数据使用量的增长进行容量规划，以及管理一个或多个底层云或硬件环境。Kubera 为这些平台团队提供了管理整体环境的弹性、容量甚至成本和性能所需的工具。

## **了解更多信息**

MayaData 的 Kubera 有一个免费的永久层。除了本文中提到的按工作负载备份、灾难恢复和迁移之外，您需要运行的只是一个 Kubernetes 集群——Kubera 将连接到该集群，并为您的有状态工作负载、报告和可视化、存储配置等提供预配置的集群外日志记录和警报。

Kubera 现在包括与 Cloudian Hyperstore 的集成，无需额外费用，而且 Kubera 的起价为每个用户每月 49 美元。现在就试试吧，我们期待您的反馈。

*8 月 6 日，我们将与我们的合作伙伴、企业级对象存储领域的领导者 Cloudian 讨论和演示 Kubernetes 对每工作负载备份的新要求，以及数据管理和保护、备份、恢复和云迁移。* *[立即注册了解更多](https://go.mayadata.io/data-protection-for-kubernetes-webinar)。*

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>