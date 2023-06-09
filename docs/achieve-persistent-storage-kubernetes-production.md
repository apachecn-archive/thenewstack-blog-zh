# 云原生存储的 8 项原则

> 原文：<https://thenewstack.io/achieve-persistent-storage-kubernetes-production/>

谢丽尔·洪(@oicheryl)是前谷歌软件工程师，现在是 StorageOS 的产品经理。她就存储、容器和云基础设施进行编码、写作和演讲。谢丽尔是英国第一位云原生计算基金会大使，创建并运营了云原生伦敦会议。此前，她花了五年时间在谷歌地图上编写 C++，并获得了剑桥大学计算机科学硕士学位。

管理存储的一个关键挑战是处理持久性，这是一个影响整个组织的开发人员、系统管理员、操作人员和开发人员的问题。没有无状态架构这种东西，它要么是外包的，要么是内部管理的，但无论哪种方式，都需要在不同类型的存储之间做出权衡。通过检查云原生存储的原则，组织可以更有效地评估需要什么和正在使用什么。

存储发现自己处于一个微妙的转折点。技术的进步要求组织转向这样的解决方案:服务器更加临时，数据自由流动且轻量级，存储服务于具有多个存储需求的多维应用程序。

随着向临时服务器的转移，组织不想要他们必须精心照顾的“宠物”服务器，他们想要可以像“牛”一样对待的服务器，并且当它们不再服务于某个目的时被丢弃。这反映在对没有长期附件的商用硬件和云解决方案的需求日益增长。至于他们存储的数据，它必须是轻量级的，以便在增长时可以导入或迁移到其他地方。此外，应用程序通常有多个存储要求，这意味着组织可能需要多个存储解决方案。

## 容器的角色

那么如何用容器来解决这些问题呢？Kubernetes 存储模型可以提供一些答案。在 Kubernetes 模型中，管理员在池中注册持久卷(PV ),并让开发人员可以使用它们。开发人员可以选择从池中声明他或她选择的 PV，并在 pod 中引用声明。这为开发人员提供了一个更加灵活的入口，以及一个更加流畅和高效的工作环境。

云原生架构是水平可扩展的，跨服务器分布；没有单点故障；具有弹性和自愈能力；操作员开销最小；并且不需要人工监督，因为一切都是 API 驱动的，并且与底层平台和硬件相分离。

透过容器的镜头来看云原生存储，我们开始明白，虽然容器技术可能已经解决了云中代码的许多问题，但它仍然需要在存储类别中提供完整的解决方案。通过对存储进行更深入的分析，我们可以更好地了解最能满足未来存储需求的选择。

## 云原生存储的八大原则

云原生存储可通过其满足以下八项原则的程度来评估:

它应该**以应用程序为中心，**呈现给应用程序并由应用程序使用，而不是操作系统或虚拟机管理程序；

它应该是**平台不可知的**，能够在任何地方运行，使得升级和扩展不中断；

存储资源应该像应用程序和服务器所需的所有其他资源一样进行**声明和组合**；

资源和服务应该是 **API 驱动的**，使它们易于供应、消费、移动和管理；

存储服务应**本身安全**并集成加密和基于角色的访问控制等安全功能(based

平台应该灵活，能够在不同位置之间移动应用程序数据，根据增长动态调整卷的大小，并制作数据的时间点副本以供保留或促进数据的快速恢复；

存储平台应该是高性能的，能够在复杂的分布式环境中提供确定的性能；

它应该**持续可用**并使用可预测的、成熟的数据模型管理数据分发，以确保数据应用的高可用性、持久性和一致性。

了解了云原生存储的八项原则后，我们可以朝着尽可能多的原则相结合的目标努力。它们可能不是组织需求所必需的，但是它们提供了评估组织需求和使用的方法。

## **还没到呢**

如今的存储环境中部署了多种方法，包括集中式文件系统、专有存储阵列、分布式存储、公共云 SAN 和 API 框架，但没有一种方法能够完全满足云原生存储的八大原则。

目前最接近的解决方案是平台无关的软件定义的协调存储系统，该系统可横向扩展，并提供 Docker 或 Kubernetes 集成，允许组织在生产中运行企业容器化应用程序。它还具有高可用性、高性能和一致性。

从长远来看，一个行业标准“[容器存储接口](https://github.com/container-storage-interface/spec)正在计划中，它将使存储供应商能够开发一个插件，并在多个容器编排系统上运行。同时，组织需要仔细考虑他们的存储需求，并选择符合八项原则的解决方案。

塞缪尔·泽勒在 [Unsplash](https://unsplash.com/search/photos/storage?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>