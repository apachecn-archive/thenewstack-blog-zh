# 如何简化 Kubernetes 更新并降低风险

> 原文：<https://thenewstack.io/how-to-simplify-kubernetes-updates-and-reduce-risk/>

使用 Kubernetes 运行您的基础设施的一个优点是，它使应用程序保持最新变得相对简单。所以讽刺的是，保持 Kubernetes 的更新被认为是一个更大的问题。

更新本身并不是一个问题。有些软件，比如 Mirantis Container Cloud，甚至会帮你做更新。但这并不意味着更新本身没有风险，也不意味着需要投入一些最昂贵的人的时间来防止灾难。

简而言之，Kubernetes 的更新意味着多个应用程序可能会崩溃，因此自然地，每个人都参与到防止这种情况发生的工作中来——开发人员、团队领导、操作员和安全人员。在更新完成之前，其他一切都会停止，这确实会占用您的带宽。

## 让我们看看为什么 Kubernetes 更新会成为这样一个问题

Kubernetes 项目网站提出了更新集群的基本操作顺序:

1.  升级控制平面。
2.  升级集群中的节点。
3.  升级客户端，如 kubectl。
4.  根据新 Kubernetes 版本附带的 API 变化调整清单和其他资源。

这似乎是一个简单的过程，但每一步都可能充满危险。Kubernetes 是一个快速发展的项目，有时会引入突破性的变化——例如，取消功能、扩展 API 和引入新的最佳实践，包括新的软件组件等等。这些变化会对集群的工作方式产生广泛的影响。变更会影响:

*   集群如何在基础设施(主机操作系统和网络)上运行。[参见本文](https://www.mirantis.com/blog/networking-problems-after-installing-kubernetes-1-25-or-after-upgrading-your-host-os-this-might-be-your-problem)了解去年 9 月发布的 Kubernetes 版本 1.25 中的一个错误示例，该错误会使 Kubernetes 工作节点无法通过网络进行通信。
*   集群如何与云提供商 API、DNS、入口、服务网格、存储、备份等其他服务和资源协同工作。
*   集群如何与特定于应用程序的资源一起工作，这些资源用于帮助 Kubernetes 编排您在其上构建和托管的内容。
*   最后，当这些组件发生变化时，Kubernetes 更新可能会破坏应用程序本身。

因此，更新 Kubernetes 集群是一个深刻的、潜在可怕的、也许是昂贵的提议。如果作为您业务核心的应用程序出现故障，您将处于停滞状态。你能承受这一切吗？有人能吗？多长时间？

为了防止这种情况发生，首先你需要你的技术人员详细阅读发行说明，并标出任何会破坏的东西。这些更改可能会立即阻止您，在这种情况下，您需要在更新之前调整您的实现和/或应用程序。

然后你需要在做之前测试你计划做的每一件事。在实践中，这意味着您需要构建一个(可能是相当大的)测试集群，在尽可能多的方面(理想情况下是所有方面)复制您当前的环境。您需要在上面安装最新版本的应用程序，进行集成，并确保一切都“像在生产中一样”工作

然后，您需要小心翼翼地执行更新过程，同时在进行过程中测试问题，以便在发现问题和修改资产(清单和资源)以适应 Kubernetes 的新版本时暂停和回滚；然后重试更新，直到您可以顺利完成更新。

随着集群规模和复杂性的增加，随着 Kubernetes 之外的产品成为重要的依赖项，这些操作的复杂性也随之增加。随着您运行的应用程序以更复杂的方式进行配置，事情也会变得更加困难。

## 简化流程和降低风险的方法

管理这种复杂性的最佳方式是通过自动化，尽管令人惊讶的是，许多 Kubernetes 用户只使用非常基本的自动化来部署集群。Monolithic automation 可能能够将单个目标集群(以及潜在的托管和周围基础设施)转移到新的期望状态，但它可能无法完成分几个阶段更新集群的复杂任务，这些阶段中穿插着测试(和回滚等)。

您可能需要编写和测试定制自动化来管理您的特定更新过程，这将成为每次更新都需要测试的内容。

所有这些都涉及到运营商、架构师、DevOps 工程师和应用程序开发人员之间的合作，所有这些人都必须从他们的主要职责中抽出时间，直到更新成功完成。

另一种选择是与合作伙伴和提供商合作，如 ZeroOps 从业者，他们将为您卸下这一负担。Kubernetes 更新的“去风险化”本身实际上是一个复杂的过程。依靠关键路径 Kubernetes 运营合作伙伴:

*   **帮助您规划软件开发和运营**，做出决策并构建您的 Kubernetes 集群模型。可以从一开始就对最佳实践进行编码——在如何部署 Kubernetes 集群以及如何为它们构建应用程序和服务方面——以预测和防止依赖性的发展。
*   **计划更新，执行必要的测试，并使用预正式发布项目软件资产构建占地面积有限的概念验证集群**。如果合作伙伴正在积极维护和支持您使用的 Kubernetes 发行版，这种方式最有效，这意味着远离 Kubernetes 更新的绝对“前沿”,同时仍然保持您的实现是当代的(当然，完全支持)。
*   **提供并支持不断发展和改进的自动化**——不仅部署和管理整个集群，还自动化整个更新过程，以便在短维护窗口内可靠地完成更新。原则上，目标是使更新无缝和连续，完全不中断正在运行的应用程序和进程。
*   **扩展您的软件开发和运营团队，使其具备解读更新通信所需的深厚专业知识**。与 Kubernetes 社区合作，确定潜在的影响，并充分了解您的操作和应用程序，以便尽早发现“陷阱”。制定补救计划——不断改进您的工作方式，以越来越摆脱危险的依赖关系，并越来越便于更新。

简而言之，虽然理论上 Kubernetes 的更新应该是简单明了的，但它们不能是“置之不理”的提议。休息的可能性太大了。无论您是与 ZeroOps 合作伙伴一起使用还是单独使用，Kubernetes 的更新都应该小心谨慎地执行，即使这意味着所有的工作都要停下来，直到完成。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>