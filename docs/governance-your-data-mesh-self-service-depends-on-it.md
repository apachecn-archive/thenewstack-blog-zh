# 治理:您的数据网格自助服务依赖于它

> 原文：<https://thenewstack.io/governance-your-data-mesh-self-service-depends-on-it/>

[](https://www.linkedin.com/in/adambellemare/)

 [亚当·贝勒马尔

亚当·贝勒马尔是 Confluent 公司的技术人员，之前是 Shopify、Flipp 和黑莓公司的数据平台工程师。他已经在数据领域工作了十多年，在大数据架构、事件驱动的微服务和在组织中构建流数据方面有着成功的历史。他也是 O'Reilly 书名《构建事件驱动的微服务》的作者。](https://www.linkedin.com/in/adambellemare/) [](https://www.linkedin.com/in/adambellemare/)

这是由四部分组成的系列的第三部分。下面是零件[一个](https://thenewstack.io/the-game-changing-appeal-of-data-mesh/)和[两个](https://thenewstack.io/data-mesh-demands-you-view-and-handle-your-data-in-a-new-way/)。

在正确的人需要时获得可靠的数据是任何成长中的组织面临的永无止境的挑战之一。本系列关于数据网格的第 2 部分解决了这个基本等式中的第一个因素:概述了对域控制的需求和文化心态，即数据必须作为独立和优雅的产品可用，以确保最佳质量的信息。

在第 3 部分中，让我们处理下一个变量，数据交付的及时性。最高效的数据架构允许公司内任何地方的数据消费者在需要时访问实时和历史数据。但还有更多:我们必须确保生产者有创建和管理其数据产品的指导方针和标准，以便消费者能够发现、使用和依赖它们。实现更高易用性的方法是通过精心设计的自助式数据和联合治理系统。

## **构建自助式数据平台**

自助式数据平台应该服务于数据产品的生产者、消费者和维护者。每个人都有不同的需求，这些需求相互重叠。自助服务平台必须提供工具和界面，以简化创建、查找、使用以及可能删除数据产品的生命周期。一些重要的自助服务功能包括:

*   **发现:**用户应该能够浏览、搜索和筛选其组织中可用的数据产品，确定他们需要访问哪些产品来完成工作，并使他们能够直接向领域专家寻求帮助(如通过电子邮件、直接消息或电话)，以帮助他们做出决策。
*   **数据产品管理**:数据产品所有者和生产者应该能够发布他们的数据产品，供其他人发现和访问。发布权限应该根据对联合治理需求的遵从性进行控制。
*   **访问控制:**用户应该能够请求访问敏感数据产品。可以自动授予对较低安全性数据产品的访问权限，而内部代理在授予权限之前审查对较高安全性或更多受限数据产品的访问请求。对每个数据产品的读写权限的完整树可用于绘制依赖关系图并跟踪整个组织的数据沿袭。

拥有自助式数据平台的主要目的是减少，最好是消除访问和使用数据产品的开销工作。实现这一点的方式会有所不同，构建自助式数据平台有多种方式。例如，如果您的公司使用微服务，您也可以将您的自助式数据平台集成到您的自助式微服务平台中，允许用户请求访问数据产品以及计算、存储和监控资源。

但是分析目的呢？使用事件流形式的数据产品的一个主要好处是，您可以轻松地将它用作操作和分析需求的单一真实来源。事件流可以通过使用 Kafka 之类的工具连接事件流中的源数据，并将其写入云存储中的一组文件以进行批量分析，从而为分析数据集提供支持。数据平台团队通常会更进一步，将派生的批处理数据集注册为自己的数据产品，适合在组织中的其他批处理分析中重用。

相关的一点是，特别是如果您的服务或批量分析需要访问整个数据集:从数据网格中消费数据意味着潜在的实时和历史数据。有两种方法可以做到这一点:

1.  第一个叫做*λ架构*。它要求您构建两个独立的系统，一个用于历史数据，一个用于实时数据，并在运行时解决它们
2.  一个更简单，通常也更好的解决方案是 *Kappa 架构*。它始于一个无限期存储流的事件流平台。这使得数据产品的消费者可以选择他们自己用例所需的数据。他们可以从平台上的最新事件开始，或者从时间的起点开始消费，建立自己的特定于业务用例的状态模型。

重要的是，各个领域保持一定程度的自治，并且数据产品可以以非常适合该领域的方式访问。团队必须有足够的自主权来恰当地定义和发布他们的数据产品，而消费者必须有明确定义的标准和期望，以可靠的方式利用其价值。结果是一种平衡，生产者和消费者找到一个共同的中间立场，努力改善所有成员的体验。这将我们引向联合治理。

## **对联合治理的需求**

联合治理是一种平衡行为。虽然数据产品的生产者应该有充分的自主权，以他们认为合适的任何方式构建、填充和发布数据，但他们还必须确保数据产品的形式便于消费者合理地获取和使用。微服务领域和数据网格领域之间有许多相似之处:两者都使用户能够选择最适合其用例的工具和技术，同时提供对技术蔓延、令人困惑的实施和使用困难的抵抗。

例如，微服务平台可能会将开发人员可能使用的语言限制在特定的子集。在数据网格中，类似的类比是限制数据产品的格式，这样只有一两种机制(如事件流及其派生的云存储数据产品)是可用的标准。在这两种情况下，目标都不是让创作者的生活更加困难，而是限制技术蔓延和实现复杂性，特别是在现有技术和标准足以满足产品需求的情况下。虽然探索新的技术和格式是令人兴奋的，但我们必须在可靠性、可维护性和对现有工具集的完全支持之间进行平衡。

## 入门:创建标准和实践组

开始联合治理的最佳方式是创建一个标准和实践小组，帮助为组织的数据产品定义策略，从而促进跨域的互操作性。该小组可以建立诸如数据产品类型、模式类型、变更管理要求、质量水平和服务水平目标等标准。它还应该包括删除和清理策略，以及主题保留时间、压缩和与数据如何随时间变化相关的任何其他属性。

这个小组应该由整个组织的技术专家和领域专家组成，包括数据产品的生产者和消费者。通过对话、辩论和基于原则的讨论，该团队必须就简化数据产品的生命周期和使用达成共识。此外，该团队必须负责不可避免的增量更改，以保持数据网格的最新，例如添加新的“批准”技术，弃用旧技术，以及随着业务和技术环境的变化重新审视标准、格式和操作要求。

联合治理更像是一个正在进行的组织过程，而不是严格的技术问题。它确保拥有网格中所有数据产品的独立自主的团队可以一起工作。如果你想关联不同的数据产品，你不想处理三种不同类型的模式格式(Avro、Protobuf 和 JSON)和访问语义，对吗？你要确保网格的各个组成部分实际上是“网状的”,这样你才能产生真正的网络效果并创造价值。

为数据网格建立一个管理机构是构建一个适用于所有参与者的解决方案的一个极其重要的部分。请记住，即使是治理的形式也会因组织而异，一些组织选择更严格的自上而下的监管，而另一些组织则不那么集中，参与程度也很低。

数据网格设计要求改变组织中的许多活动和过程——理想情况下，是向更好的方向改变。在我们下一篇也是最后一篇文章——第 4 部分——中，我们将探讨这些变化将如何影响您的组织结构。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>