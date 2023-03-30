# Atlassian 的指南针统一了工具和代码蔓延

> 原文：<https://thenewstack.io/atlassians-compass-unites-tool-and-code-sprawl/>

根据 Atlassian 最近的一项调查，从单一软件架构到微服务的转变不仅意味着代码库中更多的移动部分，还意味着工具。该公司的[Atlassian State of Developer Survey](https://www.atlassian.com/blog/software-teams/state-of-the-developer-2022)最近发现，大多数接受调查的开发人员表示，所需工具的数量在增加，他们职位的复杂性也随之增加。

为了应对这些日益增长的趋势，Atlassian 正在 alpha 中推出一款名为 [Compass](https://www.atlassian.com/software/compass) 的新产品，以帮助开发人员跟踪和管理他们日益复杂的工作环境和软件架构。Atlassian 的产品经理 Taylor Pechacek 描述了软件开发人员的现状以及 Atlassian 希望如何解决他们的问题。

“现代软件本身的复杂性在工具的数量和人们构建东西的方式上有了显著的增长。这来自于所有的分布式，将它们的整体分解成微服务、共享库、ML 模型、移动应用、背后的 API。Pechacek 说:“这种复杂性真的开始不仅仅是编写代码，而是围绕代码的许多事情。“开发人员能够启动自己的基础设施，在其上运行自己的应用程序，所有这些都基于微服务，这使他们进入了一种‘你构建它，你运行它’的模式，因此他们不仅仅考虑‘我如何构建、设计和交付这个东西？’但是“我有责任也有义务经营它”。"

## 驯服蔓延

Pechacek 解释说，Compass 通过三种主要方式为开发人员提供更好的清晰度和组织性。首先，Compass 将一个软件的各个部分组织到一个组件目录中，这提供了一个单一的地方，开发人员可以在这里访问共享的组件、文档和其他与他们的代码库和过程相关的信息。第二，Compass 分析软件，并根据可定制的、用户定义的标准提供记分卡。第三，Compass 提供了一个扩展性引擎来与其他工具集成，并从 Compass 之外的其他地方引入关于项目的信息，无论是 Atlassian 工具还是其他工具。

“它本质上是一个开发者协作门户，旨在帮助团队驯服软件蔓延，并真正思考他们如何在这些事情上导航的体验，”Pechacek 解释道。“他们将能够在一个地方实时查看对其软件架构所做的更改、其影响以及所有这些组件的当前运行状况。这将使他们更加敏捷，这将帮助他们平衡他们在 JIRA 软件、Bitbucket 和 GitHub 中所做的创新，并建立他们需要的围绕运营和事件管理的稳定性。”

Compass 用户将能够直接从他们的存储库中导入软件，并将他们与组件目录中负责的团队联系起来，这将能够提供 Pechacek 提到的一些事件管理。组件目录还能够确定依赖项和其他相关组件，这些组件将显示在这个单独的位置。

同时，当这些存储库被导入时，Compass 将立即开始分析软件，以更新适用的 DevOps 记分卡，并为开发人员提供他们健康状况的总体视图，Pechacek 提供了一些例子。

“健康意味着什么？我的公关周期低于三天吗？我经常部署吗？想想经典的 DORA 指标，然后走得更远，将安全性、合规性、可用性和 MTTR 结合起来。你会得到一个健康的模型，然后问，我们的建筑健康吗？我们正在以一种稳定、健康的方式运营这件事吗？”佩查切克说。

## 可定制可扩展

虽然 Compass 将从记分卡指标的一些预设配置开始，但它们也是完全可定制的，可用于确定数据保留要求或团队内的简单流程等事项。

Compass 的最后一个方面，即扩展它的能力，意味着团队将能够在 Compass 内创建定制应用程序 Pechacek 提供了一个 AWS 成本优化应用程序的例子，该应用程序可以在单个微服务组件旁边提供定制建议-并进一步统一工具和代码蔓延的日益分散的体验。

目前，Compass 正在发布 Alpha 版本，Beta 版本即将推出，Pechecek 提供了一些关于该产品下一步发展方向的见解。

“许多不同的公司都在思考这个问题，因为它们开始分解，变得更加分散。我们的下一步是，随着我们进入测试版，这无疑是一个信号，表明我们对产品有了更多的信心，并完成了一些关键功能，”Pechacek 说。“但对我们来说，这实际上是继续共同创造和缩小围绕记分卡的明确用例，为目录提供更大的灵活性，以他们想要的方式映射数据模型，在这些 DevOps 工具中加入一些通知，一些自动化，以及一些更好的搜索，以便您可以识别，“我的架构哪里出错了？”"

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>