# Kubernetes 与亚马逊 EKS 运营的 5 个实践

> 原文：<https://thenewstack.io/5-practices-for-kubernetes-operations-with-amazon-eks/>

在过去的几年中，各种规模和垂直行业的组织都使用由 Kubernetes (K8s)和云协调的容器化应用程序来帮助加速他们的 IT 开发管道。但是，为了实现最佳效率，这些组织中的许多都在寻求添加其他管理服务。

 [凯尔·亨特

凯尔是拉菲系统公司的产品营销主管。他在信息传递和定位、竞争差异化、走向市场战略和思想领导力方面有着出色的表现。](https://www.linkedin.com/in/kylehunter) 

受管理的 Kubernetes 最受欢迎的选择之一是[亚马逊弹性 Kubernetes 服务(EKS)](https://aws.amazon.com/eks) 。但随着组织扩大对亚马逊 EKS 的采用，K8s 集群和应用的数量可能会导致重大的运营挑战，包括可观察性、升级管理、安全性和开发人员的生产力。

为了应对这些挑战，平台/站点可靠性工程(SRE)团队必须寻找可扩展的方法来安全地管理所有客户和地区的所有 EKS 集群。

无论是基于现场的工人节点供应、[亚马逊 EKS 发行版(EKS-D)](https://aws.amazon.com/eks/eks-distro/) 还是跨配置有私有端点的多个 EKS 集群的安全应用部署，平台团队都需要集中管理，以创建一种在 AWS 上操作 Kubernetes 集群的整体方法。

这篇文章介绍了团队如何简化亚马逊 EKS 的使用，并最大化这个健壮的 Kubernetes 管理解决方案的好处。

## 填补 Kubernetes 的运营空白

试图扩展现代应用程序的企业经常会遇到 Kubernetes 战略所能实现的和他们的组织蓬勃发展所需要的之间的“操作差距”。

这种运营差距主要由三个常见因素造成:

*   集群规模，随着集群数量的增长，标准化变得越来越复杂和具有挑战性。
*   在集群地理中，可用性区域和 AWS 区域的数量不断增加，使得管理应用程序和基础架构变得越来越困难。
*   确保适当的访问随着组织中更多的人看到 K8s 的好处并希望使用它，按集群配置和维护访问控制变得不可扩展。

对于使用 Kubernetes 或像 EKS 这样的托管服务的大型企业来说，启用以下功能以充分利用平台并帮助弥合这些运营差距至关重要。让我们从探索这些核心领域以及随之而来的重要问题开始:

## 自动化

早期要问的关键问题是:“我们如何简化所有集群和应用程序部署，以满足业务需求？”

运营多个集群的企业经常遇到并行管理机群生命周期的共同挑战。关键是为自动化集群和应用程序部署、Kubernetes 升级和管理任务创建操作实践。这将减少错误，提高生产率，并加快现代应用程序的上市时间。

首先，从一个 [GitOps 操作模型](https://rafay.co/platform/gitops-pipelines/)(实现一个版本控制系统)中启用持续部署的能力，以自动将更改部署到 Kubernetes 集群。能够创建任意数量的由多个阶段组成的管道，这些阶段可以依次执行，这有助于集中管理运营和开发过程的每个方面。

第二，在亚马逊 EKS 或亚马逊 EKS-D 集群上实现升级 Kubernetes 版本的最简单过程，无论需要就地升级还是迁移到新的集群。专注于自动化预检、集群升级和更快地验证更改，以帮助简化和标准化应用程序生命周期管理。通过自动化日常任务，管理员可以降低人为错误的可能性，提高整体工作效率，并让他们的团队专注于创新。

## 安全性

下一个重要问题是“我们如何保护跨多个 AWS 区域和地区的所有集群和应用程序，以限制正确的人使用，确保所有操作都可以被审计？”大多数大型 IT 组织对业务应用程序使用身份管理和访问控制，但是在多集群环境中，创建和维护角色变得至关重要，在多集群环境中，为了提高效率，可以将一个 AWS 管理员分配给一组集群。如果攻击者通过一个帐户访问其中的所有群集，这可能会产生固有的安全风险。

考虑使用基于角色的访问控制和零信任访问来提高您的安全状况，这可以通过策略进行管理，并与您公司的单点登录解决方案相集成。这有助于确保所有应用程序都需要强身份验证和安全凭证，并将所有网络连接视为不可信，除非证明并非如此。

目标是允许适当的用户从任何地方访问群集，甚至从防火墙后面访问，同时维护用户和执行的命令的完整审计跟踪。

## 能见度

Kubernetes 的一个伟大之处在于，它允许您跨多个地区、可用性区域和云运行应用程序。为了确保跨多个客户、集群和 AWS 区域有效地使用和管理资源，平台/SRE 团队需要全面了解其整个基础架构，包括内部和远程/边缘位置，无论采用哪种 K8s 分布。

通过详细、一目了然的仪表板视图了解每个亚马逊 EKS 和亚马逊 EKS D 集群的状态和运行状况对于生产工作负载至关重要。拥有所有集群和应用的单一视图使集群管理员更容易主动可视化、诊断和解决事件，并充分利用亚马逊 EKS，尤其是在内部 Kubernetes 采用率增加的情况下。

## 管理

确保符合内部政策和行业法规，如 HIPAA、PC 或 GDPR，是新运营的 Kubernetes 基础架构的基本要求。为集群和应用程序生成具有标准化且经过批准的模板的自动化工作流至关重要。

当通过策略管理 Kubernetes 的使用时，一致性是关键，特别是对于整个 K8s 基础架构中的安全性、存储和可见性等元素。理想情况下，不同的内部团队可以在不同的开发阶段使用多组预先批准的集群配置。这样做不仅简化了管理，而且有助于最大限度地降低管理不善和漏洞的风险。这包括能够快速检测、阻止和通知企业管理员群集和应用程序配置中的任何更改，以消除越界群集和潜在的安全和支持问题。

## 资源

从概念上讲，Kubernetes 允许内部和外部客户经济高效地使用更容易、更快和可任意使用的集群。然而，要从这些快速灵活的集群中受益，企业需要实施新的流程来构建、集成、访问、维护和升级 K8 集群。

这需要雇佣难以找到和留住的 K8s 专家，因为对人才的需求很高，而供应很低。拥有一个降低复杂性并允许简化操作的集中平台成为成功部署大规模 Kubernetes 环境的关键要素。

Kubernetes 越来越成为希望提高 IT 组织运营速度和规模的企业的热门选择。但是，随着组织利用亚马逊 EKS 等工具扩展其 Kubernetes 实践，以在云中蓬勃发展，更深入的集成可以成功填补 Kubernetes 的运营缺口，并帮助您从云投资中获得最大收益。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>