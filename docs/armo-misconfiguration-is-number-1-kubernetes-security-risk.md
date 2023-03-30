# ARMO:配置不当是库本内特公司的头号安全风险

> 原文：<https://thenewstack.io/armo-misconfiguration-is-number-1-kubernetes-security-risk/>

开源 Kubernetes 安全平台的开发者 ARMO 发布了一项研究结果，表明配置不当是 Kubernetes 安全的最大问题。

ARMO 进行了八个月的内部研究，扫描了 10，000 个集群，发现 100%被扫描的集群至少有一个错误配置。他们使用该公司的 Kubernetes 安全平台[kubiscape](https://www.armosec.io/blog/kubescape-the-first-tool-for-running-nsa-and-cisa-kubernetes-hardening-tests/)来扫描集群。

[ARMO 首席执行官兼联合创始人 Shauli Rozen](https://www.linkedin.com/in/shaulirozen/?originalSubdomain=il) 表示，由于运行和管理的复杂性，在 Kubernetes 集群中发现错误配置并不奇怪，因为 Kubernetes 用户在整个软件开发生命周期(SDLC)中都在与错误配置和漏洞作斗争。然而。他说，Kubescape 安全平台提供了一个多云 Kubernetes 单一窗口解决方案。它提供风险分析、安全合规性、基于角色的访问控制( [RBAC](https://www.armosec.io/blog/a-guide-for-using-kubernetes-rbac/) )可视化工具，以及图像漏洞扫描。

Kubescape 扫描 [Kubernetes 集群](https://www.armosec.io/glossary/kubernetes-cluster/)、YAML 文件、舵图、工作节点和 API 服务器，根据多个框架(如 [NSA-CISA](https://www.nsa.gov/Press-Room/News-Highlights/Article/Article/2716980/nsa-cisa-release-kubernetes-hardening-guidance/) 、[米特里·ATT&CK](https://attack.mitre.org/)等)检测错误配置、软件漏洞以及整个 SDLC 的 RBAC 违规，计算风险得分并显示一段时间内的风险趋势。

## 评估调查结果

ARMO 在四个框架中评估了其发现，包括 ArmoBest、米特 ATT、CK、NSA-CISA 强化指南和 DevOps 最佳实践。

对于每项评估，100 代表最高风险，0 代表最低风险。对于组织来说，最佳实践是将他们的风险分数保持在 30 分以下，60 分以上的分数使他们处于最差的 5%中。ARMO 负责营销和业务发展的副总裁 Jonathan Kaftzan 说，风险分数低于 10 分的组织处于最好的 10%中。

## 五大安全错误配置

扫描发现，除了 100%的集群包含至少一个错误配置之外，65%的集群还包含至少一个严重错误配置。50%的集群有 14 个或更多失败的安全控制。以下是在 Kubescape 扫描过程中发现的 5 大错误配置列表:

*   运行特权容器

具有运行权限的容器可能会创建对主机信息的意外访问，通常应该配置为以非 root 用户身份运行。

具有集群管理员角色的用户可以对任何资源执行任何操作，这给实现留下了相当大的漏洞。

*   缺少资源策略

63%的集群的工作负载没有适当的资源限制。资源策略可以控制对 pod 规范的安全敏感方面的访问。未能正确配置资源策略会暴露您的系统并导致代价高昂的违规。

*   不可变容器文件系统

在容器内获得执行权限的网络攻击者可以创建文件、下载脚本和修改应用程序。利用不可变的容器配置可以防止损坏，但如果管理不当，也可能导致应用程序功能复杂化。

*   入口和出口被封锁

63%的集群具有集群外部的工作负载，但没有阻止适当的入口。使用入口和出口过滤来保护网络接入点至关重要。

## 遵循最佳实践

“人们仍然在不需要的时候运行特权容器和根容器，有时你不得不这样做，但我们看到大约 60%的工作负载，这远远超过了在特权模式下运行的需求，或者作为容器内的根用户运行的需求，或者两者兼而有之。在我看来，这是我们需要走出去的最大的最佳实践，”罗森说。

此外，ARMO 发现的另一个问题是用户没有在 Kubernetes 上运行的工作负载上使用资源限制。

“我不认为这很重要，但它非常普遍，”罗森说。“因此，虽然 Kubernetes 让您能够限制内存使用或工作负载的 CPU 使用，但很少有人真正使用这些功能。实际上，这在安全性方面并不重要。但这是一种非常非常非常糟糕的做法。”

同时，总的来说，ARMO 的研究表明:

*   63%的集群的工作负载没有适当的资源限制
*   37%的集群的应用程序在配置文件中有凭据
*   23%的集群运行的应用程序具有危险的 Linux 功能
*   35%的集群的工作负载运行时功能不安全
*   100%的集群配置错误

## 了解你的集群的姿态

“在这种环境下，对于开发人员和 DevSecOps 来说，最紧迫的问题是，首先要了解您的群集的状况—我的群集中有什么级别的风险。”罗赞说。

因此，ARMO 构建了 Kubescape 来扫描集群的配置，以及扫描集群中的漏洞，基于角色的访问和集群供应，并将所有这些整合到一起，以了解集群中的情况。

该公司于 2021 年 8 月推出了 Kubernetes，此后它扫描了超过 10，000 个 Kubernetes 集群。ARMO 汇总了数据并做了一些分析，以突出显示关于 Kubernetes 安全、风险和合规性状态的重要统计数据。

## 错误配置是根本原因

[据 Gartner](https://venturebeat.com/2021/08/12/takeaways-from-gartners-2021-hype-cycle-for-cloud-security-report/) 称，到 2025 年，超过 99%的云漏洞都是由客户错误配置或失误造成的。这补充了来自 [Gartner 的 2021 年云安全宣传周期报告](https://www.gartner.com/en/documents/4004061)的发现，该报告显示 59%的已知原因的安全事件是由检测到的错误配置引起的。ARMO 官员表示，当被问及哪些风险最让云领导者担心他们的容器和 K8s 环境时，大多数受访者认为错误配置是他们的头号担忧。

“我们从错误配置开始，然后转向漏洞和基于角色的访问控制，我们正在前进，”Rozen 说。

## ARMO 路线图

然而，ARMO 路线图上的下一件事——基于用户反馈——是给平台带来更多的 CI/CD 功能。

“因此，我们将这些能力中的一部分更多地放在左边，以便更早地发现问题，”Rozen 说。“然后我们听到的第二件事是关于添加准入控制器，基本上实现了我们在 Kubernetes 中发现的实施。当新的工作负载出现时，会有不同的准入控制器。而且，由于我们已经创建的功能，我们的许多用户一直在询问我们何时以及如何才能向 Kubernetes 引入准入控制器。”

Kubernetes 准入控制器是管理和执行集群使用方式的插件。

与此同时，Rozen 说，ARMO 添加到 Kubescape 的一个功能是，不仅可以找出关键漏洞，还可以过滤掉那些可以远程利用的漏洞。另一个正在开发的功能是为用户提供一种方式，让他们可以对使用该平台发现的问题进行优先排序。

## 开发者之爱

ARMO 的目标是赢得开发者对其技术的热爱，要实现这一目标需要做一些不同的事情。

“首先，如果你想让开发者使用它，你需要从左到右，你先解决问题的左边，然后再解决问题的右边，”Rozen 说。"右边，我指的是运行时高级功能."

第二件事是为开发者提供一些他们可以在三到五分钟内使用并获得价值的东西。

“我认为这是我们成长的一部分，”罗森说。“因为现在，一个开发人员上了我们的 GitHub，五分钟后将在他的集群上运行他们的第一次扫描。

获得开发者喜爱的第三件事是开源。

“因为首先，我们希望社区给我们反馈，”Rozen 说。“社区在给你反馈和帮助你开发产品方面更加有效，而且实际上也致力于开发工作。你知道，我们的一些第三方扩展是由我们的社区创建的。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>