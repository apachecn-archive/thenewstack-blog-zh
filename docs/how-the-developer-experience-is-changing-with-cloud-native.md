# 开发人员体验如何随着云原生而改变

> 原文：<https://thenewstack.io/how-the-developer-experience-is-changing-with-cloud-native/>

[](https://www.linkedin.com/in/danielbryantuk/)

 [丹尼尔·布莱恩特

丹尼尔·布莱恩特是大使实验室(前身为 Datawire)的开发者关系总监。Daniel 是一名 Java 拥护者，是 TechBeacon DevOps 100 的影响者，并为几个开源项目做出了贡献。此外，Daniel 定期为行业出版物撰稿，并经常在 KubeCon、QCon 和 JavaOne 等国际会议上发言。](https://www.linkedin.com/in/danielbryantuk/) [](https://www.linkedin.com/in/danielbryantuk/)

基于 Kubernetes 的云原生软件交付的复杂性和速度使得传统上分离的角色(开发人员、运营人员和站点可靠性工程师(SREs))之间的协作至关重要。

更多的协作和传统角色的重新定义有助于推动云原生软件开发向前发展，打破孤岛，促进开发人员对整个生命周期的所有权，并实现更快、更安全的软件交付。

这个由三部分组成的系列，通过与开发人员、sre、平台架构师和领导层的一线访谈，探讨了开发人员的体验是如何变化的，在一定程度上受到运营和站点可靠性团队不断变化的体验的影响，以及对云原生开发领域中每个角色的期望。

让我们从开发商开始。

## 开发者的新常态

开发人员的体验正在从“编码并忘记”转变为拥有全面的服务。这创造了一种开发者体验，开发者负责编码、运输和运行他们自己的应用程序。当然，开发人员并不孤单，这种新体验的一部分是与 SREs 和 ops 的合作。这种关键的协作是不断变化的开发人员体验的核心，通过创建集中的自助工具、教育和支持来实现和增强开发人员的所有权。

对于开发人员来说，这种云原生的“新常态”依赖于组织范围内对左移思维和开发人员拥有的全生命周期所有权概念的支持。它还要求一种完全不同的协作方法，即开发人员与 SRE 和运营团队合作的方式发生演变，以更多地关注围绕发货软件的战略目标，而不是事后救火和临时请求。团队合作得越多，开发人员承担整个生命周期所有权的工作就变得越容易，软件也能更快、更安全地交付给最终用户。

## 淘汰旧的

在很大程度上，传统的开发工作流允许“编码并忘记”的开发体验。这不是云原生开发的工作方式。微服务驱动的开发引入了重大变化，包括新技术和工作流。突然之间，“内部开发循环”，即开发人员花费大部分时间的领域，开始看到与“外部开发循环”和其他领域的耦合增加，在那里存在各种不熟悉的“船”活动、依赖性和复杂性。在许多方面，由于这种复杂性，云原生空间仍然是未知的领域。已经涉足原生云领域的组织存在着非常不同的成熟度，这使得标准的整体将继续与原生云并行存在，并且开发人员最终将涉足两个领域。

对于那些已经进入云原生甚至部分进入云原生的组织和团队来说，云原生开发生态系统在构建、运输和运行分布式系统方面推动了一定程度的复杂性，这是开发人员特别需要管理或理解的。周围的生态系统通过创建许多支持工具做出了响应，但这导致了“工具蔓延”与此同时，随着这些工具的激增和复杂性的增加，开发人员被要求拥有完整的软件开发生命周期，尽管他们对运送-运行交付等式的重要方面并不熟悉。如果不改变开发人员、sre 和 ops 之间的关系，打破现有的孤岛，同时改变这些团队的工作范围，云原生应用程序开发所承诺的速度就有可能丧失。

## 在新的

这些新的关系看起来像什么，开发人员如何调整他们的工作方式，不仅是新的开发范式，还有支持他们工作的 SRE 和运营团队？采用这些新的工作关系如何帮助开发人员、sre 和运营团队利用云原生开发的灵活性和优势来成功交付云原生应用？

从[开发人员的角度来看](https://www.getambassador.io/developer-control-plane/developer-control-planes-a-developers-point-of-view/)，“基础设施真的非常非常难。”在需要严格控制资源的组织中，让开发人员能够亲自了解基础架构并运行他们自己的应用程序会使整个组织受益。这一策略提升了开发人员的技能，使他们更加灵活，释放了现有的 SRE 和运营资源，并在事故期间更快地获得洞察力。

从 [SRE 的角度来看](https://www.getambassador.io/developer-control-plane/developer-control-planes-an-experienced-sres-point-of-view/)，SRE 团队应该支持开发人员教育，并帮助文化发展到拥抱“你构建它；你经营它”的方法。SREs 应支持交互式自助服务和事件理解，而不是在事件发生时“挺身而出”救火。“如果开发人员了解整个代码运行之旅，我就不会被要求去扑灭他们能够控制的火灾。”

从[运营和平台的角度来看](https://www.getambassador.io/developer-control-planes/developer-control-planes-a-platform-architects-point-of-view/)，运营的职能是帮助平衡开发人员的自由和责任，运营团队通过确保正确的技术完全嵌入到开发人员的体验中来促进这一点。为开发人员定义一条“铺平的道路”可以简化他们的准备工作，有助于对抗工具泛滥，并支持开发人员的所有权，这是快速安全地交付软件的关键。

## 总结:达成共识

虽然没有统一的开发人员体验，但大多数以云为本的组织，无论其成熟度如何，都经历了可归结为两个要点的共性:

*   **跨职能协作:**对于开发人员来说，与 SRE 和运营团队的跨职能协作至关重要。这些合作伙伴功能可以减轻开发人员工作的复杂性，并有助于确保无缝和快速地将软件功能安全地交付到用户手中。
*   **赋予开发人员所有权:**开发人员控制平台的集中化和自助式方法是关键的云原生最佳实践。支持增强开发人员所有权，提供清晰的自助服务选项和集成工具，有助于推动整体工程、组织、成功和目标的实现。

开发人员的体验正在变得更好，增强了协作并建立在云原生软件开发所能实现的基础上。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>