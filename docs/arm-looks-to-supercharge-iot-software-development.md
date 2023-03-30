# Arm 寻求增强物联网软件开发

> 原文：<https://thenewstack.io/arm-looks-to-supercharge-iot-software-development/>

芯片设计师 [Arm](https://www.arm.com/) 创建了一个平台，旨在让开发者更容易快速设计和构建物联网(IoT)软件。

芯片设计师的 Arm 物联网整体解决方案是一个多管齐下的计划，包括更快地开发[片上系统(SOC)](https://internetofthingsagenda.techtarget.com/definition/system-on-a-chip-SoC)，基于云的现代开发方法，以及构建周边生态系统的计划，使开发人员能够在高度多样化的物联网硬件中重用软件。

Arm 物联网和嵌入式副总裁[穆罕默德·阿瓦德](https://www.linkedin.com/in/moawad/)表示，目标是创建一个类似于手机的物联网软件开发环境，在这里已经为数千种不同的智能手机创建了数百万个应用。如果开发者不得不购买他们想要部署应用程序的每一部智能手机，那么应用程序会更少，创新会更少，而且会失去很多潜力。

Awad 在与记者和分析师的虚拟简报会上表示，如果该行业没有利用智能手机应用市场的相同能力，物联网经济也会发生同样的情况。

“我们将使全球数百万开发者能够加快上市时间，并采用更现代的软件开发方法，轻松摆脱组成物联网的各种硬件，”阿瓦德说。“要做到这一点，他们不需要成为更好的开发人员。我们将从根本上改变物联网软件的开发方式，并在此过程中改变市场经济。”

## **物联网的发展挑战**

Awad 说，物联网发展迅速，覆盖范围广，设备环境多样，给软件开发商带来了挑战。他说，这包括缓慢的产品设计。从技术发布到产品上市通常需要五年或更长时间，这在很大程度上取决于产品的设计。

此外，缺乏构建可跨多个平台利用的软件和服务的技能，并且物联网软件开发效率低下，因为开发和测试需要物理硬件，而虚拟硬件目标旨在解决这一问题。

阿瓦德说:“如果你是一名软件开发人员，你就必须摆弄电缆、跳线和电线，还要在桌子上放些电路板。“如果你想采用现代开发方法，要么你做不到，要么你必须建立大规模的硬件农场。随着硬件的发展，你必须把它们拆掉，放进一个新的硬件盒子里。这是令人难以置信的低效。”

## **手臂来了**

本周在 2021 年 Arm 发展峰会上推出的 Arm 物联网整体解决方案包括三个要素。第一个是 [Arm Corstone](https://developer.arm.com/ip-products/subsystem/corstone) ，预设计、预集成和预验证的硬件子系统——包括 CPU、MPU(内存保护单元)和系统 IP——该公司直接向硅合作伙伴交付，以加速 SOC 的开发和发布，其中不仅包含 CPU，还包含内存、[GPU](https://thenewstack.io/tutorial-deploy-the-nvidia-gpu-operator-on-kubernetes-based-on-containerd-runtime/)和 I/O 端口等元素。

高能效 SOC 是 Arm 成功的基础，Arm 设计芯片并将这些设计授权给高通和三星等处理器制造商。Arm 因其为移动和嵌入式设备设计 SOC 而闻名，多年来已将其触角延伸到数据中心系统和物联网等领域。根据 Awad 的说法，Corstone 已经被 Arm silicon partners 用来加速超过 150 个设计的开发。

他说:“我们将这一值得信赖的可靠基础作为 Arm 整体解决方案的基础。“这就是我们加倍增加对 Corstone 投资的原因。向前看。这将是我们如何向生态系统交付物联网技术的基础。我们所做的一切，都将从科尔斯通开始。”

## **Arm 虚拟硬件**

另一个元素，Arm 虚拟硬件，是一个基于云的 Corstone 虚拟模型，本质上使开发人员能够在不需要访问物理芯片的情况下创建和测试他们的代码，并推动敏捷开发方法的使用，如持续集成/持续开发和物联网和嵌入式平台的 [DevOps](https://thenewstack.io/category/devops/) 。虚拟 Arm 芯片模型模拟了从内存到外围设备的一切，这将使开发人员甚至能够在物理 SOC 可用之前构建软件。

Awad 表示，它将把产品设计周期从五年缩短到三年，并将通过在硬件被组装之前允许 SOC 上的反馈来帮助 Arm 芯片制造商。

他说:“我们正在把技术交到数百万软件开发人员的手中，而这些人以前是无法获得这些技术的。”。“这项技术只有传统的芯片设计人员和有限的嵌入式开发人员才能使用。通过支持并行硬件和软件协同设计，并为物联网带来新的云原生开发优势，我们使软件开发能够在芯片上市之前就开始。我们正在释放数百万新开发人员的创新。”

Awad 说，这对原始设备制造商和物联网服务提供商来说也是一个福音，他们“不必建立和维护硬件农场来扩展他们在各种设备上的服务”。“他们可以运行持续集成工作流，并在虚拟硬件上验证其算法，从而实现规模化。”

Arm 虚拟硬件可在大型云服务提供商[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)AWS 市场上获得。Arm 官员说，该公司的一些合作伙伴已经在使用它。

## **标准化是关键**

Arm 还通过其 Project Centauri 推动物联网设计的更大标准化，该项目为设备启动、安全和云集成提供设备和平台标准及参考实施。希望能为 [Arm 的 Cortex-M](https://developer.arm.com/ip-products/processors/cortex-m) SoC 设计做点什么——旨在节省成本和功耗，并利用该公司的氦技术来提高计算性能——正如 [Arm 的项目 Cassini](https://www.arm.com/solutions/infrastructure/edge-computing/project-cassini) 为其为更复杂的应用设计的 Cortex-A 处理器所做的那样。

在云领域，Project Centauri APIs 包括对 PSA 认证和 Open-CMSIS-CDI 的支持，这是一种标准的云到设备规范，可减少实现不同云解决方案和实时操作系统所需的工作，从而降低成本，加快上市时间，并扩大规模和提高安全性。

## **快速增长的物联网**

随着更多设备变得越来越智能并产生大量数据，物联网预计将继续快速增长。市场研究公司 IoT Analytics 在上个月的一份[报告](https://iot-analytics.com/number-connected-iot-devices/)中表示，尽管全行业芯片短缺以及新冠肺炎疫情对供应链的负面影响，今年联网物联网设备的数量将比 2020 年增长 9%，达到 123 亿个活跃终端。到 2025 年，物联网连接将超过 270 亿个。

据另一家市场研究公司 Mordor Intelligence 称，到 2026 年，物联网芯片将从今年的近 120 亿美元增长到超过 270 亿美元。

Arm 多年来一直活跃在物联网领域，其硬件设计组合不仅包括 Cortex-A 和 Cortex-M SOC，还包括 Ethos-U microNPUs 机器学习推理处理器和 Mali 图像信号处理器(ISP)，以及软件和开发工具。迄今为止，Arm 合作伙伴已售出超过 700 亿台基于 Cortex-M 的设备。

GPU 制造商 Nvidia 正在出价 540 亿美元收购 Arm，尽管该交易正在受到欧盟和英国监管机构的密切关注，并遭到高通等 Arm 合作伙伴的反对，尽管博通等其他公司支持该交易。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>