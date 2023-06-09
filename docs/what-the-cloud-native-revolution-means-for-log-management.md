# 云原生革命对日志管理意味着什么

> 原文：<https://thenewstack.io/what-the-cloud-native-revolution-means-for-log-management/>

[LogDNA](https://logdna.com/) 赞助本帖。

 [克里斯·托奇

Chris Tozzi 曾经做过记者和 Linux 系统管理员。他对开源、敏捷基础设施和网络有着特别的兴趣。他是 Fixate IO 的内容高级编辑和 DevOps 分析师。他的最新著作《为了乐趣和利润的 T2:自由开源软件革命史》于 2017 年出版。](http://christozzi.com/) 

曾几何时，日志管理相对简单。日志的数量、类型和结构都很简单且易于管理。

然而，在过去的几年里，这种简单性已经荡然无存。由于向云原生技术的转变——例如松耦合服务、微服务架构以及容器和 Kubernetes 等技术——过去的日志管理策略不再适用。在云环境中成功管理日志需要从根本上改变日志的聚合、分析等方式。

下面是云原生革命如何改变了日志管理的本质，以及 IT 和 DevOps 团队可以做些什么来继续有效地管理日志。

## **是什么让云原生日志记录与众不同**

乍一看，云环境中的日志管理似乎与传统的日志记录没有什么不同。云原生基础架构和应用程序仍然会生成日志，并且日志管理流程的基本步骤(收集、聚合、分析和循环)仍然适用。

但是，如果您开始尝试监控云原生环境，很快就会发现高效和有效地管理日志要困难得多。有四个主要原因。

### **更多日志**

首先，有更多的日志需要处理。

在云原生时代之前，大多数应用程序都是运行在独立服务器上的单体。每个应用程序通常只生成一个日志(如果它甚至创建了自己的日志；有时，应用程序会将数据记录到系统日志中)。每个服务器通常只生成少量日志，主要是 Syslog 和 auth。因此，要管理整个环境的日志，您只需要处理几个日志。

相比之下，在云原生环境中，您通常使用微服务架构，其中可能有十几个或更多不同的服务在运行，每个服务提供组成整个应用程序所需的不同功能。每个微服务都可以生成自己的日志。

不仅如此，基础设施还有更多层；所以推而广之，更多的日志。您不仅拥有底层主机服务器及其生成的日志，还拥有位于应用程序和底层基础设施之间的抽象层创建的日志，比如 Docker 或 Kubernetes，或者两者都有，这取决于您如何使用它们。

简而言之，向云原生的转变意味着 IT 团队已经从为他们支持的每个应用程序处理几个单独的日志，变成了十几个甚至更多。

### **更多类型的日志**

不仅总体上有更多的日志，而且日志的类型也更多。除了服务器日志和应用程序日志之外，您还拥有云基础设施日志、Kubernetes 或 Docker 日志、身份验证日志、Windows 和 Linux 日志(因为现在在同一家商店同时使用两种操作系统越来越普遍)等等。

这种多样性增加了复杂性，不仅因为要管理更多不同类型的日志数据，还因为这些不同类型的日志通常以不同的方式格式化。因此，很难使用正则表达式匹配或其他类型的通用查询一次解析所有日志。

### **多样化的测井架构**

随着日志数量和类型的增加，在应用程序环境中公开日志数据的方式变得更加复杂和多样。

Kubernetes 就是一个最好的例子。Kubernetes 提供了一些内置的功能，用于在节点级别收集日志；它收集数据的确切方式取决于环境变量。例如，它在安装了 systemd 的系统上记录到 journald，但在其他情况下直接写入。/var/log 中的日志文件。

让事情变得更复杂的是，Kubernetes 没有对集群级日志记录的本地支持——尽管也可能有多种方法。您可以使用在每个 Kubernetes 节点上运行的日志代理来为集群生成日志数据，或者您可以在 sidecar 容器中运行日志代理。或者，您可以尝试直接从应用程序生成集群范围的日志数据，前提是您的集群架构和应用程序允许这样做。

这里的底线是，即使在相同的平台上，日志记录架构的设置方式也有相当大的可变性。因此，在云原生环境中，设计一个统一的日志管理流程变得越来越困难，该流程可以在 it 需要支持的所有应用程序或平台之间保持一致。

### **非持久性日志存储**

云原生日志记录的最后一个挑战来自于这样一个事实，即一些云原生应用程序缺乏持久的数据存储。容器是最好的例子。

当容器实例停止运行时，容器中存储的所有数据都将被永久销毁。因此，如果日志数据存储在容器中(默认情况下，通常是这样)，它将随容器一起消失。因为容器是短暂的，实例会暂停并被删除，而新的实例会自动运行，所以在容器关闭之前不会询问管理员是否要保存日志数据。它会自动关闭并被删除，并带走您的日志数据，除非您事先将这些数据移动到了其他地方。

如果您只关心实时处理日志数据，这种短暂性可能没问题。但是，如果您需要将历史日志保留一段时间，当容器停止运行时丢失日志数据是不可接受的。

## **云本地日志管理的最佳实践**

为了应对在云原生世界中登录的这些挑战，团队可以使用以下指南。

### **统一日志收集和汇总**

有这么多不同类型的日志格式和架构需要支持和记忆，试图分别管理每个系统的日志是不可行的。

相反，实施一个统一、集中的日志管理解决方案，自动从您环境的所有部分收集数据，并将其聚合到一个位置。

### **采用灵活的日志管理解决方案**

您的日志管理工具和流程应该能够支持任何类型的环境，而不必重新配置环境。

例如，如果您有一个 Kubernetes 集群以一种方式公开日志数据，而另一个集群以不同的方式记录日志，那么您应该能够收集和分析来自两个集群的日志，而不必改变任何一个集群处理日志的方式。同样，如果您在一个公共云上运行一个应用程序，而在另一个不同的云上运行另一个应用程序，那么您不必为了从一个中心位置管理其日志而修改任何一个云环境的默认日志记录行为。

### **实时收集日志**

确保没有持久存储的环境中的日志不会消失的一种方法是实时收集日志数据，并将其聚集在一个独立的位置。这样，日志数据一产生就保存在持久日志管理器中，并且即使容器关闭也仍然可用。

这种方法比试图只在固定的时间间隔从容器内部收集日志数据更可取，如果容器比预期的更早关闭，这将使您面临丢失一些日志的风险。

### **使用定制日志解析器**

与其忽略传统分析工具不支持的日志结构，不如利用[定制日志解析器](https://docs.logdna.com/docs/custom-parsing)来处理任何格式的数据。这样，您就不会有错过来自非标准日志的重要见解的风险。

## **结论**

云原生日志管理从根本上不同于传统的整体应用程序的日志数据管理。这不仅仅是因为日志数据的规模增加了(尽管事实如此)，还因为日志数据的记录、结构化和公开方式更加多样化。面对这些挑战，有效地管理日志需要一个日志管理解决方案，它能够完全集中和统一来自您支持的任何和所有系统的日志数据，同时还能够从非标准日志类型中获得洞察力。

这篇文章是一个更大的系列的一部分，叫做“开发工具时代的记录:从整体到微服务及其他”[下载完整电子书](https://go.logdna.com/logging-in-the-age-of-devops)。

*目前，新堆栈不允许在该网站上直接发表评论。我们邀请所有希望讨论某个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。*

来自 Pixabay 的 Akil Varman 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>