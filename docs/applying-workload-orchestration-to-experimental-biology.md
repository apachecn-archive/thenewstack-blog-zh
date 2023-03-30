# 工作量协调在实验生物学中的应用

> 原文：<https://thenewstack.io/applying-workload-orchestration-to-experimental-biology/>

[HashiCorp](https://www.hashicorp.com/?TheNewStack) 赞助本帖。

 [Dhasharath Shrivathsa

Dhasharath 是 Radix 的创始人兼首席执行官，他花了数年时间为麻省理工学院媒体实验室进行研究。在他的空闲时间，你会发现他在阐述现代计算机有多神奇，在远足，在看科幻小说。](https://radix.bio/about-us/) 

对于许多生物学研究人员来说，从小型学术实验室到大型制药公司，物理运行和记录实验的过程几乎和生物学本身一样复杂。博士生物学家花 40%的时间做重复性的机械任务，这分散了他们对设计和分析实验等更有影响力的工作的注意力。手动过程也存在实验室中人为错误的风险。

在冠状病毒疫情期间，这个问题成为公众意识的焦点。研究 COVID 的实验室在尝试调整适当数量的机器和人员以最大限度地提高日常测试能力时遇到了瓶颈。此外，由于工作限制，不以 COVID 为重点的实验室停止了工作。无论您是在生产流水线上工作还是在疫情上工作，弄清楚如何分配资源和安排工作流程都是一个常见的问题。

几个具有前瞻性思维的组织正在将这重新定义为一个计算问题——特别是，他们意识到构建一个下至生物学实验室的编译器将使生物学家能够自动使用抽象和优化。这将解决生物技术公司的关键业务和根深蒂固的组织问题。

操作系统背后的核心理念——共享资源上的进程、内存和存储抽象——也适用于生物实验室。这些抽象正是 Radix Labs 正在构建软件来完成的。

## 孤岛式基础架构阻碍了实验室扩展之路

Radix 团队从第一原理着手。我们开发了一个完整的工具链——包括编程语言、编译器和(分布式)运行时——将实验室协议编译成机器人动作或(人类)实验室技术人员指令。研究人员可以通过直观的界面自动设计、运行和分析实验。不同的实验室设备可以在一个控制平面下进行协调。使用我们的工具的实验室可以在更短的时间内运行更多的测试，获得关于扩展和容量规划的可行建议，实现按结构纠正合规性，等等，所有这些都在我们的高级语言中自动公开和优化。

然而，这并不是一条容易的路，我们在集中实验室数据和工作流程方面面临着一些挑战。

*   **数据孤岛**:实验室设备，如 DNA 测序仪和移液器，通常不会共享或集中它们的数据。每台设备都在自己的本地裸机节点上运行。这排除了网络共享，而网络共享是自动化实验室的关键。
*   **机器隔离**:在典型的生物实验室中，没有集中的平面来远程访问设备。设备通常分散在几个组织单位中，远离用户可能需要的容量。随着实验室规模的扩大，工作流程变得更加低效——当你来到一家制药公司时，这种规模的资源重复令人震惊。
*   **手动干预**:当前的设置通常需要人们亲自前往每台设备，手动访问数据或结果。在实验重新设计期间，他们必须手动重新编程设备。研究人员在设备前花费的时间比他们在研究和分析上花费的时间还多。

我们需要的是一种简单的方法来协调这些不同的实验室机器。本质上，这是大计算的相反问题:生物实验室有太多的计算机，而不是太少。我们的目标是为用户提供支持，并使其软件尽可能易于访问，因此我们需要一种工具，它可以轻松地安装和部署在实验室现有的内部基础架构上，通常是带有传统机器的空气隙裸机 Windows 环境。

## 统一实验室工作流程

我们最终选择了 [HashiCorp 的 Nomad 工具](https://www.nomadproject.io/)作为我们的编排解决方案，它帮助我们在不到一周的时间内完成了我们运行时系统的早期草图——并随着时间的推移而不断发展。Nomad 灵活的工作负载支持和轻松的内部部署使我们能够支持各种应用程序，以满足任何现有配置。我们的系统运行几个 Docker 容器以及访问硬件资源并需要 root 的 Java 应用程序。Nomad 可以通过 exec 驱动程序进行指纹识别，然后推出更多特定的驱动程序，从而轻松添加像质谱仪这样的机器。这为我们提供了一个统一的控制平面，支持使用供应商的驱动程序部署硬件和驱动程序，无论是离心机、培养箱还是质谱仪。

我们通常只是为了添加新的物理设备(如 DNA 测序仪)而添加节点，DNA 测序仪通常直接从 Apache Kafka 读取数据，并且 Kafka 在 Nomad 中运行。所有这些都很好地集成在一起，对用户隐藏起来，在后台无缝运行。核心服务在三节点 Consul/Nomad/Vault 集群中运行，而不是在驱动程序端点上运行。

## 研究人员可以专注于实验

工作流程编排是我们为客户提供更好的实验室和科学实验管理方法的核心要素。太多的生物学家将实验室设备和机器视为“宠物”，必须手动管理和更新。我们正在努力做的事情之一是鼓励生物学家像对待“牛”一样对待实验室资源——一个没有人类干预的分布式资源库。编排在减少浪费和更好地分配资源方面起着关键作用，尤其是对于机器利用率在 10-30%范围内的生物实验室。

研究人员本身不需要担心计算方面的问题。他们看到的只是他们的实验在运行——像单个节点故障和动态故障检查这样的事情是看不见的。数据只是为了进一步处理而出现。从他们的角度来看，他们正在添加质谱仪，或者运行需要基因测序仪的标准流程——我们的操作系统在后台工作以使其成为可能——并且非常高效。

因此，研究人员可以通过一个统一的控制面板，在任何实验室设备上远程部署应用/实验、接收数据和检索结果。需要有限的物理或手动存在，使他们能够减少花费在收集实验室结果上的时间，并将这些时间集中在理解生物学的复杂性上。

实验室研究很难。为其计算机架构配备一个操作系统将使其变得更容易。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

来自 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>