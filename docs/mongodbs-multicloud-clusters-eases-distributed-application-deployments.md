# MongoDB 的多云集群简化了分布式应用程序部署

> 原文：<https://thenewstack.io/mongodbs-multicloud-clusters-eases-distributed-application-deployments/>

[MongoDB](https://www.mongodb.com/cloud/atlas/) 赞助本帖。

 [安德鲁·戴维森

Andrew 是 MongoDB 的云产品副总裁。他之前在谷歌从事全球地图业务，拥有物理学背景，并在南亚生活过。](https://www.linkedin.com/in/andrewad/) 

在当今快速发展的商业环境中，灵活性就是一切。没有什么比在您需要时随时随地获得正确的数据更有价值的了。

这是使用多个云的巨大吸引力之一——也就是说，如果开发人员和 IT 团队能够解决跨两个或更多云提供商分发数据和运行应用程序的复杂性。或者只需在指尖获得无缝移动的能力。

为此，需要能够针对不同的工作负载、应用程序或业务需求使用多个云提供商；以及满足任何需求的弹性可伸缩性。这种可修改的弹性已经成为 IT 决策者越来越受欢迎的战略目标——根据最近的 IDG 报告，超过一半(55%)的组织使用多个公共云，21%的组织表示他们使用三个或更多个[。](https://www.idg.com/tools-for-marketers/2020-cloud-computing-study/)

## **多云朵实际指的是什么？**

在实践中，多云通常意味着一家公司可能在一个云中运行一些应用程序，在第二个云中运行其他应用程序，而在第三个云中运行其他应用程序。这可能只是公司内不同团队或业务部门使用这些应用程序的反映，然而不同云中的应用程序并不相互交互，它们服务于不同的最终用户。

重要的是要记住，应用程序传统上是孤立的，仅限于一个云提供商；还没有无缝的跨云共享数据或迁移应用程序的能力。但是，如果情况在某个时候发生了变化，比如您希望整合多个应用程序，或者希望能够灵活地将工作负载迁移到不同的平台，该怎么办呢？

到目前为止，云层之间的屏障相当高，在它们之间移动很困难。您必须为第二个云重写大部分应用程序代码，即使这样，您仍然有孤立的数据集。这是不可接受的，因为互操作性是多云应用开发的基本要求。多亏了 Kubernetes，无状态应用程序的可移植性变得越来越容易。但是，即使在无状态应用程序可以跨多个云进行一致管理的世界中，让数据真正跟上也是一个难题。

## **开发者如何受益**

您需要合适的工具来完成工作，这就是为什么多云对那些希望避免被特定云供应商束缚的组织来说很有吸引力。每个平台都提供优势，各有所长。

事实是，每个云提供商都可能是“最好的”云提供商——尽管是在不同的情况下，面向不同的用户。虽然每个提供商都提供服务组合，但它们在功能或成熟度方面并不相同。开发人员应该能够跨云使用同类最佳的技术——不只是针对不同的应用程序，而是针对同一应用程序。想象一下，你的开发人员能够在一个统一的控制台内利用 AWS Lambda、谷歌云的人工智能平台和微软的 Azure DevOps。

数据治理也至关重要。许多公司必须满足各种法规遵从性要求(如 GDPR、CCPA、HIPAA、GLBA、PCI DSS 和 Sarbanes-Oxley ),而不管数据存储在企业系统的什么位置。满足数据库法规遵从性和安全性要求是至关重要的，否则可能意味着巨额罚款和处罚。这就是基于云的数据互操作性对开发者如此重要的原因。这使他们能够专注于更加差异化的工作，而不是数据管理。

## **多云将使开发人员能够构建更好的体验**

作为开发人员，我们需要正确处理这些问题，因为多云将成为许多企业未来的重要组成部分。如果做得好，多云可以提供许多优势，包括:

*   **灵活性**:一些客户更喜欢某个特定的云供应商，或者根本无法与其他人合作。其他客户希望将传统云系统连接到新的选项。或者内部法规可能要求客户数据保留在特定的国家或公司。事实上，某些国家只由一家云提供商覆盖:比如挪威的 Azure 和印度尼西亚的 Google Cloud。也许一家公司使用一家云提供商承担 99%的工作负载，但它的应用在台湾起步，另一家云提供商在那里有一个区域。你需要为所有的情况做好准备。
*   **高可用性**:云无一幸免于宕机；当事情出错时，麻烦会很快发生。多云降低安全风险暴露。组织可以通过跨多个云分布数据来建立弹性。这样，如果一个 web 服务主机出现故障，业务可以继续运行。在澳大利亚，ARPA 要求金融服务部门制定应急计划，以防云提供商出现故障。因此，一家使用 Azure 的大型银行可能会利用澳大利亚地区的 AWS 和谷歌云来支持业务连续性。
*   **功能**:云工具和服务的创新通常来自三大云提供商，但它们的发展速度并不一致。公司必须能够利用每个云平台的独特优势。正如全球金融服务技术提供商怡安集团架构&数字战略副总裁 Mohan Putcha[对 IDG](https://www.idg.com/tools-for-marketers/2020-cloud-computing-study/) 所说，“我们必须成为本地 AWS，因为他们在分析方面的先进能力，我们必须加入 Azure，因为坦率地说，开发者喜欢那个生态系统。”
*   **移动性:**将应用程序从一个云迁移到另一个云的能力至关重要，尤其是在经历变革的公司中。对于经历过并购并最终在整个组织中使用多个云的公司来说，多云设置很常见。例如，借助多云集群，IT 经理能够避免在多个云中复制整个环境。

今天，我们 MongoDB 的[发布了](https://www.mongodb.com/blog/post/introducing-multicloud-clusters-on-mongodb-atlas)一项新的功能，这项功能历经数年才得以解决这些问题，并在 MongoDB Atlas 上全面推出了多云集群。客户现在可以跨 AWS、Google Cloud 和 Azure 同时部署一个完全托管的分布式数据库。

各种云平台之间有着紧密的协调，因此您可以使用您想要的数据库工具，并在您认为合适的时候转移工作负载，无论您的数据位于何处。例如，谷歌云上的一家德国公司可以利用 AWS 的米兰数据中心扩展到意大利。这种新的多云集群功能解决了上面讨论的每个场景:灵活性、高可用性、功能性和可移植性。

创新从来都不容易。我们必须梦想未来，同时支持现在需要的东西。多云环境支持这两个目标，将为当今业务奠定基础的传统系统与未来发展的途径连接起来。Multicloud 为您的未来提供了一条灵活的道路。但首先，我们必须把它做好，让它变得简单。

*有兴趣在 MongoDB Atlas 上使用多云集群吗？在这里了解更多*。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>