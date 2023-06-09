# 无容器计算:终极服务分解

> 原文：<https://thenewstack.io/containerless-computing-the-ultimate-service-decomposition/>

[KubeCon + CloudNativeCon](https://events19.linuxfoundation.org/events/kubecon-cloudnativecon-north-america-2019/) 赞助了这篇文章，期待 [KubeCon + CloudNativeCon EU](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/) 于 8 月 17 日至 20 日发布。

 [布鲁斯·巴西尔·马修斯

Bruce 是 Mirantis 的高级解决方案架构师。自 2000 年以来，他一直参与开源社区。他是惠普公共云团队的成员，并积极参与了惠普 Helion Openstack 的初始发布。他的新技术爱好是容器化编排平台和服务网格技术，如 Kubernetes 和 Istio。](https://www.linkedin.com/in/bruce-basil-mathews-a91256/) 

当然，没有“无服务器”计算这种东西。计算资源总是要在某个地方运行。该术语源于用户希望摆脱对其实际服务器和基础架构的管理。此外，我们现在看到的是对“无容器”计算的需求——在这种情况下，应用程序开发人员可以专注于他们试图提供的服务，而不是创建和编排这些服务的基础设施。

当然，事情并不总是这样。在 Fortran 和 COBOL 的时代(回到恐龙在地球上漫游的时代)，我们被迫整体考虑应用程序，从数据库开始，一直到前端。这些天情况有所不同；开发人员越年轻，他们越有可能从一开始就学习面向对象编程，这使得他们更容易适应微服务思维。

这是一种调整。

## 为什么要将应用程序分解成服务？

这是一个必要的调整，因为为了创建真正现代的云原生应用程序，我们需要以一种方便、容错的方式将特定的功能容器化和编排。这意味着将总体最终目标按功能、或按操作、或甚至按组织单位分解成单独的服务。

在过去，我们把这些函数写成函数。我们将它们包含在库中，然后导入到应用程序中。在这方面，这不是**的转变。这些库现在基本上是存储在 Docker Hub 等存储库中的容器映像，可以根据需要进行升级。**

但是，这是如何把我们引向“无集装箱”建筑的呢？

这么想吧。我们习惯于认为无服务器计算独立于像 Kubernetes 这样编排容器的技术。两者的区别在于(理论上)当一个功能在无服务器环境中不被使用时，它就不存在，也不占用资源或花费金钱；而在 Kubernetes 环境中，您可以将您的资源缩减到一个容器中，但是即使这个容器没有被使用，它仍然在运行(并且在花钱)。

实际上并不需要那样。已经有很多方法可以在 Kubernetes 上实现无服务器计算。但是，如果我们可以创建一个环境，在这个环境中，我们可以获得 Kubernetes 的优势——比如调度、健壮性、污染和容忍度，等等——而不必为如何实现这一点的细节而打扰用户，那会怎么样呢？

假设您是一名开发人员，正在创建一个应用程序来传输和分析视频。在这个过程中的某个时刻，你将不得不对数据进行编码。在分解应用程序的过程中，您已经决定这是一个单独的服务，因此您创建了一个容器，该容器将原始数据作为请求并返回编码的版本。现在怎么办？

想象一下，您可以将该容器添加到一个安全的注册中心(这样只有您的组织可以使用它)，当应用程序需要编码的数据时，服务就在那里。你不用担心是否有可用的服务器，或者扩展，或者网络，或者其他任何事情。在某种程度上，这就是无服务器计算的定义。但是，作为一种实践，无服务器有一个缺点:它不是标准化的，并把我们带回供应商锁定。

## 基于 Kubernetes 的标准化

如果相反，我们在 Kubernetes 上是标准化的呢？现在，我们能够避免供应商锁定，使用现有技能，轻松创建多集群应用。我们甚至可以创建一个环境，其中一些资源是共享的，而其他资源是私有的，这取决于开发人员的需求。我们还可以使用 Istio 等服务网格技术来管理和分割网络流量。

事实上，让我们更进一步。如果我们能够为这些容器的供应增加智能，那会怎么样？如果神经网络或其他机器学习算法可以预测何时可能需要各种容器，并提前将它们旋转起来，会怎么样？该算法不仅可以扩展容器，还可以扩展基础设施本身——最大限度地降低维护基础设施的成本，同时仍然最大限度地提高性能。

所有这些都可以在可信计算的环境中运行，其中图像存储在可信的注册表中，只能在经过可信平台模块(TPM)等技术验证的服务器和设备上实例化。这实现了分布式计算，同时降低了安全风险。

## 变得复杂的地方

当然不是说这都是独角兽和彩虹。这种新思维方式的另一个重要方面是标准化和安全性。我们现在就需要将这一点规划到架构中，包括内部(其中运行的内容)和外部世界，这样执行中的应用程序就不会受到攻击。在这些领域，公司必须投入大量资金来实现所需的技术进步。例如，为了实现今天所需的灵活性，我们经常不得不以根用户的身份运行容器；这绝对不是长久之计。我们需要一个共享的权威模型，这意味着每个人都必须就方法的工作方式达成一致。行业需要定义权威，以及可信计算如何在所有这些类型的基础架构(如容器、虚拟机和裸机)中和谐工作。

然而，有一点与我们的现状保持一致，即围绕这些技术进步形成的新业务最终将把所有东西——容器、编排、网络甚至硬件——都视为代码。所有新的自动化方法都必须能够跨应用程序自我修复、自我扩展、自我配置，甚至自我自动化。例如，神经网络将需要能够在必要时扩展，预测需求并根据需要改进其模型(和准确性)。

此外，整个技术进步网络需要能够升级和更新，并且不中断服务，这意味着除了软件开发供应商之外，所有硬件供应商都需要参与进来。

换句话说，如果我们要跟上需要的步伐，我们还有很多工作要做，但如果我们现在就开始并共同努力，我们肯定能做到这一点。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>