# 如何解决 Web 级应用的性能挑战

> 原文：<https://thenewstack.io/how-to-solve-the-performance-challenges-of-web-scale-applications/>

Web 规模的应用程序需要高性能和巨大的可伸缩性，以支持大量用户和出色的用户体验。它们必须能够按需扩展，以服务于快速增长的用户群，同时提供出色的性能、敏捷性和弹性。Web 级应用程序越来越多地用于金融服务、医疗保健、在线业务服务、媒体、电信和其他行业，这些行业的系统用户数量不断增长，他们的需求也在不断变化。

开发 web 级应用程序的一个挑战是依赖传统的基于磁盘的数据库。这些数据库带来了无法接受的大规模延迟。此外，将数据从运营数据库移动到分析数据库的提取、转换和加载(ETL)流程意味着数据在分析之前就已经过时。如今，消除基于磁盘的数据库造成的延迟的最简单、最高效和最具成本效益的策略是部署内存计算(IMC)平台。

## 内存计算 101

 [尼基塔·伊万诺夫，GridGain 系统公司首席技术官

GridGain Systems 的创始人兼首席技术官 Nikita Ivanov 领导 GridGain 开发了先进的分布式内存数据处理技术。Nikita 在软件应用程序开发、构建 HPC 和中间件平台方面拥有 20 多年的经验，并为其他初创公司和知名公司做出了贡献，包括 Adaptec、Visa 和 BEA Systems。1996 年，他为欧洲最大的系统集成商之一工作，是使用 Java 技术进行服务器端中间件开发的先驱。Nikita 是 Java 中间件社区的活跃成员，也是 Java 规范的贡献者。在过去的 5 年里，他还经常在国际上发表演讲，在各种开发者大会上发表了 50 多次演讲。](https://www.gridgain.com/) 

内存计算基于跨分布式计算集群的大规模并行处理，该集群共享集群中所有可用的内存和 CPU 能力。可以使用商用服务器构建集群，并通过添加新节点进行扩展。当添加新节点时，系统会自动跨节点重新平衡数据，从而提供极高的可扩展性和数据冗余。与直接建立在基于磁盘的数据库上的应用程序相比，IMC 平台的处理速度可以提高 1000 倍或更多。一些 IMC 平台支持 ANSI-99 SQL 和 ACID 事务，这使得将 IMC 平台集成到现有的 web 级应用程序中变得更加简单，并且可以允许内存计算平台充当应用程序的记录系统。

IMC 平台的速度和可扩展性支持混合事务/分析处理(HTAP)(也称为混合操作/分析处理(HOAP)或跨分析处理)。HTAP 是在不影响系统性能的情况下对大规模运营数据集运行分析的能力。基于 HTAP 解决方案(如内存计算平台)构建的网络规模应用程序允许公司实时洞察用户行为，并对行为变化带来的任何机会或威胁做出实时响应。

整合营销传播平台的主要功能和特征包括:

### 现有应用程序的内存数据网格

对于现有的应用程序，IMC 平台被用作插入在应用程序和数据层之间的内存数据网格(IMDG ),而无需拆除和替换底层数据库。底层 RDBMS、NoSQL 或 Hadoop 数据库中的数据被加载到 IMC 集群的 RAM 中。集群节点上的并置、大规模并行处理提供了巨大的性能提升。如果 IMDG 支持 SQL，那么与数据网格通信就像使用标准的 SQL 命令来操作和分析数据一样简单。

### 面向新应用的内存数据库

对于新的或重新架构的应用程序，一些 IMC 平台可以作为独立的内存 SQL 数据库(IMDB)。为了防止内存中的数据在重启或断电时丢失，一个经济有效的策略是使用“持久性存储”这将在下一节讨论。

### 持久存储

“持久存储”功能可以添加到分布式 ACID 事务和 ANSI-99 SQL 兼容磁盘存储中，部署在旋转磁盘、固态驱动器(SSD)、闪存、3D XPoint 或其他存储级内存技术上。对于 IMDBs，持久性存储可以在重启或断电时保存数据，并允许应用程序访问整个集群 RAM 中可以容纳的更大的数据集。对于 IMDGs，持久性存储使组织能够通过在磁盘上保留完全可操作的数据集，同时在内存中仅保留数据集的子集，来平衡基础架构成本和应用程序性能。持久性存储的一个重要优点是，它可以在服务器重新启动后立即处理数据，而无需等待所有数据重新加载到内存中。

### 机器学习

一些 IMC 平台现在具有集成的完全分布式机器学习(ML)和深度学习(DL)库，这些库已经针对大规模并行处理进行了优化。这使得每个 ML 或 DL 算法能够针对驻留在 IMC 集群的每个节点上的内存中的数据在本地运行，这允许在不影响性能的情况下连续更新 ML 或 DL 模型，即使在 Pb 级。

### 与其他应用程序的集成

IMC 必须作为完整架构堆栈的一部分运行，并且必须能够与其他有用的解决方案轻松集成。例如，以下开源解决方案全部无缝集成:Apache Ignite 内存计算平台、Apache Kafka 流处理平台、Apache Spark 分布式通用集群计算框架和 Kubernetes 开源容器编排系统。

### 开放源码

上述所有解决方案都是开源的，这并不奇怪。开源解决方案对于启动数字化转型和全渠道客户参与计划的企业来说已经变得至关重要，并使开发网络规模的应用程序对于各种规模的组织来说变得切实可行。开源为开发应用程序提供了一个可靠的、经过验证的策略，前期投资要低得多。它为组织提供了对自己命运的更大控制，因为大多数开源项目的基于标准的方法减少了供应商锁定。开源项目比传统的专有供应商模式更快地交付更多的创新。

为了让 web 级应用程序实现预期的优势，组织必须实现大规模的实时应用程序性能。IMC 为实现这一目标提供了唯一实用、经济高效的途径，这反映在 Gartner 的一项预测中，该预测称，到 2019 年，75%的云原生应用程序开发将使用内存计算或使用 IMC 的服务，使主流开发人员能够实施高性能、大规模可扩展的应用程序(Gartner: " [预测 2018 年:随着采用率的增长，](https://www.gartner.com/doc/3840569/predicts--inmemory-computing-technologies)"，内存计算技术仍将无处不在)。了解 web 级架构对数据中心未来的重要性的架构师、开发人员和首席技术官应该立即开始研究内存计算解决方案的能力、灵活性和可扩展性。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>