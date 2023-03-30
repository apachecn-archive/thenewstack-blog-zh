# 托管 Kubernetes 服务使 K8s 对平台团队和应用程序开发人员来说变得简单

> 原文：<https://thenewstack.io/managed-kubernetes-services-make-k8s-simple-for-platform-teams-and-app-developers/>

对于开源项目来说，这并不是一个罕见的问题——尽管 vanilla Kubernetes 可供任何人免费下载并在其环境中安装，但对于大多数企业来说，配置、更新和一般管理 T2 太具挑战性了。不仅 Kubernetes 的开发者体验不够理想，而且在大多数公司中，还存在严重的技能差距。

好消息是，随着 Kubernetes 应用的增长，企业发行版和托管 Kubernetes 提供商的数量也在增长，他们认识到大多数公司需要比普通 Kubernetes 提供的更高级的功能和支持。所有托管服务卖点的一个关键部分是更好的开发人员体验。

Kubernetes 发行商 Rancher 的首席营销官[彼得·斯梅尔斯](https://www.linkedin.com/in/peter-smails-21576a/)说:“我们对这项工作的看法是，你要想在 Kubernetes 取得成功，首先，你必须在任何地方运行经过认证的 Kubernetes 发行版。“第二，您需要能够以简单、一致的方式管理所有这些集群。如果开发人员的体验太复杂，如果你花太多时间管理 Kubernetes 而不是写代码，那么你的整个战略就会失败。”

## 托管服务介入

Kubernetes 是一种非常强大和灵活的技术，但是对于一个没有经验的开发人员来说，这种近乎无限的可能性可能会令人望而生畏。实际上，大多数开发人员都没有使用 Kubernetes 的经验。它太新了，没有人有超过五年的经验，甚至需要 12 到 18 个月才能在生产中、在面向客户的应用程序中基本熟练地使用 Kubernetes。

托管服务提供商必须在保持使 Kubernetes 成为如此强大的工具的灵活性与坚持己见和规范性之间取得平衡，从而消除从配置到第二天操作手动处理一切的认知负荷。

“你实际上并不想熟悉一个平台中存在的所有旋钮，”谷歌基于 Kubernetes 的多云平台 [Anthos](https://cloud.google.com/anthos) 的工程总监[陈戈德堡](https://www.linkedin.com/in/goldbergchen/)解释道。“您是否希望每次都有一套不同的最佳实践？大概不会。”

任何托管 Kubernetes 服务的核心目标本质上都是一样的:通过照顾每个开发人员的需要，同时在平台中留下尽可能多的灵活性，来简化开发和运营流程。这既是为了在个人层面上使事情变得更容易，也是为了在拥有数十、数百或数千名开发人员以及需要一致性和严密监管的严格安全、治理和合规性要求的组织中大规模运行 Kubernetes 变得可行。“谷歌 Anthos 的目标是在不增加风险的情况下提高敏捷性，”戈德堡说。"它通过对最佳实践的固执己见来做到这一点."

“就像任何复杂的软件一样，它可能很难维护，特别是在大规模的情况下，”托管 Kubernetes 提供商[平台的首席技术官 Roopak Parikh](https://platform9.com/) 解释道。“如果您想在生产中运行它，我们需要确保有很高的正常运行时间，我们可以修补它，当新功能发布时它会升级，并且有监控功能。”

托管服务提供商固执己见:他们根据自己确定的最佳实践，自动完成配置工作。他们都试图在为开发人员做决策和保持尽可能多的灵活性之间找到平衡。

## 平台开发人员与开发人员

Kubernetes 是一个基础设施工具，所以在某些方面，开发人员的经验应该是无关紧要的——如果我们谈论的是工作是编写代码和部署新应用程序的开发人员。“开发商不关心 Kubernetes，”戈德堡说。“他们只想在他们的 IDE 中工作，点击一个按钮，获得他们的源代码，进行构建、测试和部署，并获得反馈。”

在 Kubernetes 中讨论开发人员体验的一个挑战是,“开发人员”可以有很多不同的含义。要对开发人员的体验进行连贯的讨论，需要清楚地定义我们在谈论谁的体验。根据 CNCF 应用交付特别兴趣小组主席的说法，创建这些通用定义是社区需要解决的核心挑战。

随着公司转向 Kubernetes，平台开发人员或基础设施团队可能会看到他们的工作发生更大的变化，他们确实是托管 Kubernetes 服务的目标“最终用户”。无论他们使用 Kubernetes 还是其他什么，平台团队的目标都是为他们组织中的应用程序开发人员提供无缝的开发体验。Intuit 产品开发副总裁 Pratik Wadher 表示，应用程序开发人员需要的 Kubernetes 知识越少越好。问题是基础设施团队很难提供足够的抽象来实现这一点。

## 简化复杂

如果目标是为基础设施工程师、平台开发人员或基础设施开发人员提供所需的工具，以便为应用程序开发人员提供无缝体验，那么许多托管服务提供商可以让这变得更容易。例如，Rancher 在 2019 年发布的开源项目 [Rio project](https://github.com/rancher/rio) ，使得只需一个命令就可以启动并运行一项服务。像 Google Anthos 一样，Rio 也是基于复杂性的假设——公司将跨公共云和私有云运行多个集群。

Platform9 的托管 Kubernetes 服务也有相同的基本目标:不仅简化复杂的基础设施，还简化公司用来获得其 Kubernetes 集群可见性和管理运营的工具套件。“我们看到开发人员部署应用程序的许多痛点，他们希望越来越多的可见性，”Parikh 说。

## 在开发人员所在的地方与他们会面

Goldberg 说，托管服务最重要的作用之一是找到一种方法，在开发者所在的地方与他们见面。这既包括提供工具，使应用程序和平台开发人员能够更容易地使用 Kubernetes 取得成功，而无需大量的学习曲线，也包括了解大多数企业 it 环境的现实。她说，Anthos 使基于 Kubernetes 的工作负载与基于 VM 的工作负载集成成为可能。

“根据我们的经验，没有客户，他们喜欢 Kubernetes 带来的灵活性，”Parikh 说。“他们还喜欢这样一个事实，即他们可以使用 Kubernetes，而不用担心私密的细节。”

Mabel Amber 的特写图片，仍然匿名…来自 Pixabay。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>