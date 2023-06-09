# 吃点蛋糕:新的(有状态的)无服务器堆栈

> 原文：<https://thenewstack.io/have-some-cake-the-new-stateful-serverless-stack/>

这是 10 月 24-28 日 KubeCon + CloudNativeCon 系列文章的一部分。

无服务器的应用程序栈陷入了一个难题:大多数应用程序需要某种状态存储，但大多数状态存储不是无服务器的。支付应用程序、在线购买/店内提货服务和实时在线体育博彩等丰富数据应用程序与完全无服务器架构不兼容，因为在某些时候，数据库会成为瓶颈。

对于无服务器应用程序，您的可伸缩性取决于您的云提供商在您的负载增长时旋转更多节点的能力。如果没有一个可伸缩的数据库来接收来自应用程序的负载，在某种程度上，就没有足够的数据处理能力来容纳当前的流量。当这种情况发生时，瓶颈直接转移到数据库，数据流受到损害，甚至完全停止，这可能会带来灾难性的后果。

当然，分布式数据库可以自动扩展以满足不断增长的需求。问题？几乎地球上所有的分布式国有商店都有一个最小的运营规模。对于已经知道自己有大规模问题的用户来说，这很好。但是，当您刚刚起步时，当您最需要的是尽可能快地构建最小可行产品(MVP)时，确保您的应用程序可以在以后扩展的时间和金钱成本是令人望而却步的。

在构建一个有状态的、全新的无服务器应用程序时，要解决扩展与启动之间的两难问题，需要一个具有真正“零扩展”能力的无服务器分布式数据库。它可以自动扩展和缩减以适应工作负载需求，同时仅根据实际消耗的计算量收费。第一个提供以完全无服务器的方式构建完全有状态的应用程序的是 CockroachDB Serverless。

## 你好，蛋糕堆

构建完全有状态的无服务器应用程序需要一种新的应用程序堆栈方法，所以今天我们介绍蛋糕堆栈。

**C** — **C** ockroachDB 无服务器
**A** — **A** 授权、认证、会话和用户管理
**K**—**K**ubernets
**E**—**E**事件驱动的无服务器平台

### c 代表 CockroachDB 无服务器

为了支持这些下一代无服务器应用，我们需要一个数据库来解决您的纵向扩展*和纵向缩减*问题。它需要是一致的数据存储，以便您可以将其用于最关键的业务应用程序。CockroachDB serverless 可以做所有这些事情，甚至更多，同时通过您的工作负载无服务器产品为您提供一个慷慨的免费托管规模。

### a 代表 Auth

为了让所有这些不同的终端拥有共同的访问控制，我们还需要下一代授权、认证、会话和用户管理。像 [Keycloak](https://www.keycloak.org/) 和[authentic ed](https://www.cockroachlabs.com/blog/authzed-and-cockroachdb/)这样的平台支持分布式会话管理，以一种容器本地的方式集中多个前端的访问。当使用 CockroachDB 作为后备存储时，它变得具有跨实例的弹性和冗余性，不需要潜在复杂的后端配置更改。

### k 代表 Kubernetes

分布式系统本来就很复杂，所以我们需要一种方法来协调所有移动的部分。我们新的有状态无服务器堆栈的核心是 Kubernetes，因为大型 K8s 供应商正在为我们的编排层提供动态、低摩擦的扩展机制。这使我们能够摆脱任何会将我们局限于特定基础架构即服务的无服务器平台。相反，它为我们的堆栈提供了跨数据中心、云区域甚至云提供商的完全可移植性，因此我们可以在尽可能靠近用户的地方部署资源。

### e 代表无服务器框架

当然，我们需要托管和部署我们的无服务器、事件驱动的架构。在堆栈的这一点上，有两个移动的部分可供选择:无服务器前端和后端框架。对于我们的表示层，我们需要一个分布式托管和内容交付平台来操作我们的数据，并通过 API 使其易于使用。像 [Directus](https://directus.io/) 或 [Vercel](https://vercel.com/) 这样的平台(这两个平台最近都在其产品中添加了原生 CockroachDB 支持)可以跨多种消费模式(原生应用、web、移动、物联网等)实现集中式数据访问。—内置无服务器功能。换句话说，它使针对数据库中的数据进行编码变得容易，而不是让我们所有的微服务直接与数据库对话。

在后端，像 [Knative](https://knative.dev/docs/) 这样的平台支持我们的无服务器部署工作流，允许单个事件处理管道和功能根据需要弹性扩展，以满足用户需求。不再有紧密耦合的应用整体，甚至不再有仍然需要干预才能扩展的复杂服务。现在，每个原子功能或工作流都可以根据需要放大或缩小。不再过度配置突发事件，也不再为未使用的容量付费。

### (M 代表模块化)

蛋糕堆栈的伟大之处在于它完全模块化。不喜欢 Knative？使用 Lambda 或云函数。不喜欢奇克洛吗？与您喜欢的身份验证平台集成。既然我们已经有了真正无服务器数据库的缺失环节能力，我们可以释放完全无服务器应用程序的全部潜力。让我们看一个例子。

想象一下，你正在建立一个平台，使花店能够与当地的送货司机合作，为当地的家庭和企业提供新鲜的花束。这项业务非常具有突发性:情人节将带来高峰工作量，就像大多数工作日的早上一样。但是你真的不需要太多的通宵跑步。

一开始，你可能只是在一个城镇里和一些司机和花店老板一起工作。你的 MVP 当然不需要基础设施在你的初始发布阶段在全国范围内运行。但是，如果您没有从一开始就这样构建，那么当您的业务从东海岸发展到西海岸，并且您需要向外扩展时，您将不得不重新构建。然而，使用蛋糕堆栈意味着您的应用程序、数据和位置都可以随着您的业务和使用情况而扩展—所有这些都是实时的，无需干预，也无需运行一堆您目前还不需要的基础架构。

从一开始就设计一个可扩展的应用程序意味着在现在快速启动和以后快速扩展之间做出选择。要么在拥有第一个客户之前就承担分布式架构的复杂性和成本，要么一开始就背负大量的技术债务，一旦客户开始涌入，这些债务可能会导致您无法扩展，要么需要大规模的重新架构。

然而现在，无服务器世界已经成熟到可以从满足长期需求的配置开始。我们在这里命名的蛋糕堆栈的所有元素甚至可以免费开始，一旦您的使用量增加，最终会产生成本，而不是必须预先支付一堆休眠的基础架构。使用蛋糕堆栈构建应用程序意味着性能和成本的扩展，因此您可以专注于最重要的资产:您的客户。

*要了解有关云原生话题的更多信息，请参加 10 月 24 日至 28 日在底特律举行的 KubeCon + CloudNativeCon 北美 2022(和虚拟)会议上的云原生计算基金会和云原生社区。*

![](img/25bc05722c52e80806074bddd7e413fd.png)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>