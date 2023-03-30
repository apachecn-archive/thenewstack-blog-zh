# 借助 Tinkerbell 配置和管理让裸机飞起来

> 原文：<https://thenewstack.io/making-bare-metal-fly-with-tinkerbell-provisioning-and-management/>

[Equinix](https://metal.equinix.com/) 赞助本帖。

 [丹·芬纳兰

Dan 是 Equinix Metal 的高级开发工程师经理。](https://www.linkedin.com/in/daniel-finneran-81a5b04/) 

几年前，每个人都义无反顾地走向公共云。这是有充分理由的:亚马逊网络服务通过让使用声明式 API 构建、部署和运行任何规模的应用成为可能，并不亚于一种“随用随付”的模式，开启了一场革命！但我们在过去几年中了解到，云并不适用于所有用例，我们正在见证混合云的兴起以及对边缘的日益关注。

随着混合多云成为数字企业的首选架构，挑战与机遇并存。其中包括推动提高性能和降低延迟，以及提高安全性和降低成本。

考虑到这些因素，并在云原生和开源概念的支持下，裸机正以我十年来从未见过的方式上升到基础架构对话的顶端。

## **为什么是裸机？**

裸机只是专用物理基础架构的一个花哨名称。如果说专用基础设施在 2010 年代有什么名声的话，那就是资本支出大、部署慢、难以管理、运营不灵活。为什么选择 metal 而不是看起来更简单(无处不在)的公共云选项？

一句话:控制。

裸机提供了终极控制。根据你想变得多书呆子，有了裸机，你可以控制你的基础设施的几乎每一个方面:硬件规格，当然，还有租用和在机器上运行的软件的所有方面。超越虚拟化层，考虑 BIOS、SGX 和 SR-IOV 等元素。

大多数人投资裸机是为了获得两个结果:更低的价格和更好的性能。单租户是其中每一个的主要驱动因素，导致更稳定的应用程序可以消耗 100%的硬件资源。当然，直到您的用例达到一定的合理规模，这种优化才是必要的，但是当它达到一定规模时——哇，它真的会产生影响。

越来越多的领先公司转向裸机以获得更明显的优势，特别是在硅的最新和最大进步方面。从新芯片和 ML 卡到 SmartNICs 和更快的内存，接触尖端技术可以带来难以置信的好处。只要想想我采用优化的苹果芯片的新 Macbook，我就很容易明白为什么对你的电脑有更多的控制可以带来令人难以置信的结果——特别是在大规模的情况下。

## 部署物理硬件很难

过去，在我的家用电脑上安装软件需要一堆软盘(或光盘)和几个小时的空闲时间。当我不得不在一台计算机上完成这项工作时，这并不好玩，但想想在一个数据中心有几百台服务器会有多难，那就更痛苦了。难怪我们都如此渴望迁移到云！

不幸的是，在过去的几十年里，管理物理服务器的技术堆栈并没有改善多少。

让我们只考虑在服务器上安装一个操作系统，抛开所有其他烦人的事情——比如固件管理和获取 IP 地址。你需要的第一项技术(DHCP)是在 1993 年推出的……同年，英特尔推出了第一款奔腾芯片，比尔·克林顿成为美国总统。第二项技术(PXE，或预启动执行环境)是在 20 世纪 90 年代末推出的。

这表明我们使用相同的旧技术管理服务器已经有多长时间了。

## 让硬件感觉像云

Packet(现在的 Equinix Metal)的愿景一直是帮助更多的人利用物理基础设施。故事的很大一部分是基于他们相信未来将建立在越来越多样化的硬件上，在更多的地方。主要的工程挑战是让它 100%自动化，这样开发者——或者更可能是她写的软件——就可以使用它。

基本上，Packet 希望为物理基础设施提供“类似云”的体验，无论它看起来是什么样子，位于何处，或者由谁拥有。异构性意味着团队需要一种真正灵活且可扩展的方式来规范和自动化物理硬件的整个生命周期。这就是 [Tinkerbell](https://tinkerbell.org) 及其相关组件如何诞生(运行 Packet 和现在 Equinix 的[裸机即服务](https://metal.equinix.com))，以及为什么我们去年在新堆栈中宣布它[，然后在 2020 年](https://thenewstack.io/why-open-source-matters-more-for-bare-metal/)5 月[开源该项目。](https://metal.equinix.com/blog/open-sourcing-tinkerbell/)

目标很简单:为大规模的生命周期多样化物理基础设施带来现代化的云原生方法。通过使现有技术现代化，并通过 API 公开它们，Tinkerbell 帮助新一代开发人员以编程方式释放硬件的价值。

## 为什么这还是个问题？

我一直相信，在你可以自动化或改进某样东西之前，你需要了解它是如何工作的。虽然让服务器打开和关闭并不是火箭科学，但这是相当利基知识。

Alex Ellis 在去年 4 月的一篇 TNS 帖子中做了大量工作，分解了关键术语和流程:“[云原生世界中的裸机](https://thenewstack.io/bare-metal-in-a-cloud-native-world/)请特别注意 DHCP、TFTP 和 PXE。虽然表面上并不复杂，但实际上，由于几个关键原因，这是一个脆弱的过程。

首先是各种硬件带来的混乱。通过使用完全相同的系统，可以缓解许多挑战。多样性使这变得复杂。硬件组件或配置(更不用说固件、操作系统和其他软件方面)的每次变化都会带来新的“工作流程”。

第二，与基于软件的环境不同，我们与物理系统交互。电源线被拔掉，磁盘驱动器出现故障，当你在几千英里之外时，很难按下“重置”按钮。这是一个范式的转变，它要求开发人员“期待意料之外的事情”并以一种更容易失败的方式编写软件。

## 小叮当是如何工作的

Tinkerbell 改善了这种状况，主要是通过将云原生方法引入 DHCP 等基础技术，同时添加了一个工作流引擎，帮助拥抱和规范各种硬件。

Tinkerbell 有五个组件，它们会在安装过程中自动部署:

*   [**Boots**](https://github.com/tinkerbell/boots)–Boots 在 Go 中重新映像远程“启动”服务器所需的组件:主要是 DHCP 和 PXE；还有 tftp 和 iPXE。
*   [**OSIE**](https://github.com/tinkerbell/osie)——OSIE 代表操作系统安装环境。它由一个基于 Alpine Linux 的 netboot 映像组成，该映像获取一个预构建的 Ubuntu 容器，该容器执行操作系统的实际安装。
*   [**Tink**](https://github.com/tinkerbell/tink)–Tink 是一个工作流引擎，由服务器和 CLI 组成，通过 gRPC 进行通信。CLI 用于创建工作流及其构造块:模板和目标硬件。基本上，一旦 OSIE 开始运行，它就会联系 Tink，看看它需要做什么。然后 Tink 服务器会发送一个声明性的 YAML 文件，告诉它要运行什么。
*   [**黑格尔**](https://github.com/tinkerbell/hegel)——全新服务器的问题在于，当它们“活”过来时，它们不知道自己是谁，还能和什么对话，甚至不知道自己的 IP 地址是什么。Hegel 是一个简单的元数据服务，一旦服务器启动，它就将这些信息返回给服务器。
*   [**PBnJ**](https://github.com/tinkerbell/pbnj)–电源和引导命令由“PBnJ”服务处理，它与 BMC(基板管理控制器)对话以执行这些关键操作。

这五个微服务协同工作来配置一台裸机。要想了解深度潜水，请查看 Gianluca Arbezzano 和 Jeremy Tanner 的现场直播。

## 进入沙盒

Tinkerbell 最近作为一个沙盒项目进入了云原生计算基金会。这是该项目的一个重要举措，因为它扩大了社区，并显示了我们对治理和透明度的承诺。我们希望并期待这将邀请更多的开发者和公司加入到这个项目中来，在这个过程中加入他们的用例、问题和贡献。

但是不需要等待！Tinkerbell 现在都是开源的，虽然这个项目还很年轻，但它周围的社区很强大。除了上游版本，小叮当还有一个[沙盒](https://github.com/tinkerbell/sandbox)供你玩。它是使用 Docker 组件构建的，并作为一项完整的服务为您启动一切。

需要帮助或有问题吗？加入 [Tinkerbell Slack](https://tinkerbell.org/community/slack/) 与 Equinix Metal 团队和其他贡献者一起努力，或者通过[提交提案](https://github.com/tinkerbell/proposals)给我们一些反馈。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>