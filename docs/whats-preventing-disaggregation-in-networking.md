# 是什么阻止了网络的分解？

> 原文：<https://thenewstack.io/whats-preventing-disaggregation-in-networking/>

[](https://www.snaproute.com)

 [亚当·卡塞拉

亚当·卡塞拉于 2015 年 8 月联合创立了 SnapRoute，负责设定技术方向，确保始终看到运营者的视角。Adam 作为供应商支持网络产品的背景，加上他运行大规模数据中心网络的运营经验，使他对如何构建可靠、灵活且易于使用的产品有着独特的见解。Adam 是分散式和传统网络技术方面的权威，尤其是它们在超大规模主干/分支 CLOS 设计和拓扑中的应用。在创立 SnapRoute 之前，Adam 负责在苹果设计和构建超大规模数据中心网络。在苹果之前，Adam 是思科局域网和数据中心交换团队 TAC 的首席工程师，这使他对硅管道、硬件和软件架构有着深刻的见解，并在调试和解决复杂、多方面的技术问题方面有着丰富的经验。](https://www.snaproute.com) [](https://www.snaproute.com)

众所周知，白盒和分散网络永远不会取代提供紧密结合的硬件和软件的传统 OEM 厂商。这种说法认为，正常运行时间、可靠性和 SLA 只能通过网络设备和紧密耦合的硬件/软件堆栈来实现。人们认为，分解会使系统不太可靠，更复杂，更难管理，最终成本几乎与传统产品相同，有时甚至更高。

但是这些担忧的真正根源是什么呢？从本质上讲，这是企业对构成基础设施的软件和硬件的信任表现。大多数网络运营商都不愿意承担风险，即使改变网络硬件和软件的采购方式有明显的好处。

然而，云和服务提供商从分解中获益的方式与市场中的其他提供商有着明显的区别。超大规模公司——如脸书、谷歌和微软——多年来一直受益于分拆。结果，传统的 OEM 厂商被迫通过增加他们的产品套件来应对。

并非每个人都能感受到分解的好处——这些产品通常是应超大规模者的要求提供的，并不面向普通大众。业内的其他人只能靠自己来解决分类问题，这使得他们很难清楚地看到自己的业务从现在的位置到未来的位置。除此之外，从白盒硬件中产生的任何预期节约都被网络操作系统(NOS)软件和支持所吞噬，通过分解节约成本的承诺是一个谬论。这使得运营商处于艰难的境地，既要保持正常运营，又要努力适应现代应用的需求。

## 那么，我们如何打破这一僵局呢？

第一步是将网络从原始设备制造商使用了 30 多年的遗留模式(技术上和财务上)中移除。到目前为止，分解已经失败，因为白盒 NOS 供应商只是试图重新实施传统的 OEM 模型，但将硬件和软件分开。这种想法是被误导的，类似于组织将应用程序从内部“叉车式”转移到公共云中，并且是随意的。因此，它导致了成本飙升、不合适的管理工具集以及缺乏对应用程序性能的可见性，这是在向云迁移的过程中不小心时常见的陷阱。

Gartner 的分析师已经开发了一个定义良好的战略，称为[五个“R”](https://www.gartner.com/doc/3893681/decision-point-choosing-cloud-migration)，该战略指导决策者完成云迁移过程，以防止传统环境的包袱束缚云。尽管在这些策略上投入了如此多的思考和关注，为什么网络没有从中吸取教训呢？我们知道将过时的架构从一个环境“移植”到另一个环境很少是最佳策略，为什么分解网络没有应用这些原则呢？用于构建网络操作系统的传统模型不适用于分散的网络，也不适合当今的云原生环境。

## 那么什么是传统网络模型呢？

专有的、封闭的、整体的、二元的 blobs 这是传统的网络模型—网络行业已经使用了 30 多年。虽然应用程序已经从裸机发展到虚拟机，并最终发展到云原生容器，但网络一直停滞不前，原始设备制造商提供系统和工具，以越来越过时的方式构建和管理基础架构。网络运营商已经习惯了封闭的专有网络，这些网络是手动管理的，不能自动进行第二天的操作。

这自然会导致应用程序所有者无法使用他们拥有的网络，而不得不变通使用。我们在 SDN 的早期采用中看到了这一点，当时覆盖层用于传统网络基础设施之上。当这还不够时，应用程序团队完全绕过内部基础架构，转向公共云。

这种基础架构外包对于许多企业来说已经变得非常必要，因为传统的网络模型无法提供他们所需的灵活性、正常运行时间和可靠性。我们生活在一个全球 24/7 的市场中，应用程序可用性的任何损失都会对业务产生长期的连锁影响。我们知道，超大规模和公共云提供商已经转向更灵活的方法来管理他们的网络，因此，正在大量使用分散网络。这是他们能够提供现代应用所需的基础设施的众多原因之一。组织不必自己构建，他们可以简单地利用公共云提供商已经投入的工作。然而，它的价格非常高——看看 Lyft 为 AWS 花了多少钱就知道了。

当您查看超大规模和公共云提供的内容时，他们不会将基础架构视为独立的孤岛。他们创建了一个平台，旨在通过针对第二层到第七层的解决方案来实现更快的应用服务时间。DevOps 人员现在可以部署应用程序，而无需考虑 API 调用之外的底层基础架构。这与 [CNCF](https://www.cncf.io/) 和其他拥抱原生云的人使用的方法相同。

随着对多云和混合云方法的长期采用，云原生方法显然处于最前沿。运营商现在将公共云视为其内部环境的延伸，而不是替代。为了让白盒网络获得牵引力，云原生原则不可忽视，必须接受。这也意味着成本等式也必须彻底改变。行业参与者长期以来一直承诺，白盒/分解的采用将产生显著的成本节约。不幸的是，情况并非如此，这也是缺乏更广泛市场采用的主要原因。网络运营中心供应商通过软件许可和支持吸收了大部分白盒硬件节省，从而创造了这种动态。

运营商不能继续以不同的方式管理其内部和云基础设施，并期望提供客户要求的服务水平。竞争太激烈，基础设施太大太复杂。白盒的采用将继续挣扎，直到它采用云原生方法并大幅降低成本。旧的传统网络模型无法满足要求。

已经存在了几十年的网络行业创新和成本模式需要被打破。将网络基础设施和现代应用结合在一起的云原生联网方法将允许在 Kubernetes 管理层的协调下统一内部部署。

如果没有云原生方法和网络之间的桥梁，即使考虑到与今天的遗留系统相比高达 50%的成本节约潜力，我们也不会看到白盒中的大规模采用。传统的网络模型网络在技术上和经济上都已经死亡。云原生网络及其改进的高效运营模式是未来的发展方向。在白盒中获得采用的唯一方法是从根本上改变网络的业务和运营方式。

CNCF 是新堆栈的赞助商。

图片由来自 Pixabay 的 TanteTati 提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>