# 在云中部署 Apache Kafka 时要考虑的 3 个权衡

> 原文：<https://thenewstack.io/3-trade-offs-to-consider-when-deploying-apache-kafka-in-the-cloud/>

快速生产和处理大量数据的组织，如网飞、Salesforce、Shopify 甚至美国邮政署​(USPS)，都在不断应用和测试新方法来管理云中复杂的数据流。

数据流及其支持的[实时用例](https://www.confluent.io/learn/data-streaming/)已经改变了消费者和企业在日常生活中的运作方式。从实时位置跟踪和个性化内容馈送到智能欺诈分析和运营监控，这样的例子不胜枚举。

工程、运营和数据科学团队期待在今年 10 月的【T2 当前 2022:下一代 Kafka 峰会】上向数据流领域的其他专家学习。在活动开始前，我们与演讲者讨论了在云中使用 Apache Kafka 的各种操作挑战。

在每个行业和业务职能部门，组织都在竞相部署高性能应用、流式管道和分析服务，以增强其最关键的能力。结果，我们如此依赖的数据流经常在混乱中开始和结束。

## 利用流数据应对云集成挑战

公司越来越擅长使用 Kafka 在数据生成后立即投入使用，无论是部署在内部还是云环境中。然而，在云中部署 Kafka 工作负载使组织能够大规模扩展他们的实时能力——也就是说，如果他们的集成架构不碍事的话。

对“快速实现价值”的持续需求无疑带来了成效——实时摄取、处理和可观察性的业务优势已成为增长和竞争创新的关键。这种速度超过策略的方法威胁着长期的运行可靠性。

意大利面条式的架构比比皆是，导致了技术债务，在软件开发生命周期的每一个阶段都会带来未来的麻烦。

## **权衡第一:速度到价值与可扩展集成架构**

![](img/e07a864e272bbd22031dad70894d9836.png)

维克多·加莫夫

加速的交付时间表会使集成测试等基本步骤没有时间。Kong Inc .的首席开发人员 Viktor Gamov 在他的[当前 2022 分组会议](https://2022.currentevent.io/website/39543/agenda/)“用 Testcontainers 测试 Kafka containers:来回往返”中讲述了集成测试的重要性。

按照加莫夫的说法，“卡夫卡从来就不是容易学习的工具。这种体系结构有其固有的复杂性，因为它是一个分布式系统。”在他的会议期间，他计划向与会者展示他们如何使用 Testcontainers 库来评估复杂的数据流堆栈是否已准备好投入生产。

## 努力跨多个来源获取实时数据

在最近的一项调查中， [60%的技术领导者](https://www.confluent.io/data-in-motion-report/)将整合多种数据源的困难列为访问实时数据的最大障碍。据 [Jay Patel](https://www.linkedin.com/in/jaympatel1893/) ，雪花公司 Kafka connector 的软件工程师和技术主管称，随着数据流用例的发展，这一挑战可能会增加。

![](img/6dbfbf43c42f6e674fb4f07919c6850e.png)

杰伊·帕特尔

“流数据适用于大多数行业领域和大数据使用案例。最初，应用程序可能会处理数据流以生成简单的报告并执行简单的响应操作，例如当关键指标超过特定阈值时发出警报，”Patel 说。“最终，这些应用程序将用于执行更复杂形式的数据分析，如应用机器学习算法，从数据中提取更深入的见解。”

在他即将到来的[分组会议](https://2022.currentevent.io/website/39543/agenda/)“雪花汇连接器如何使用 Snowpipe 的流接收功能近实时加载数据”中，Patel 计划演示用户如何加速 Kafka 和 Kafka Connect 环境，以克服延迟和带宽问题，并将数据近实时加载到雪花数据库中。

如今，实时摄取已经成为大多数组织的一项基本功能，但这并不是唯一的关注点。为了提供最大的价值，许多人工智能和机器学习(AI/ML)应用程序不仅需要尽快获得数据，还需要高质量和高完整性的数据。

## **权衡之二:高速数据接收与集中式数据治理**

为了确保这三点，组织需要一个有效的数据治理框架。尽管变更数据捕获和[流处理](https://thenewstack.io/the-rise-of-the-event-streaming-database)等工具可以帮助组织控制数据质量和完整性，但集中式数据团队几乎不可避免地成为瓶颈，因为对他们服务的需求超过了他们的能力。

## 在多区域部署中实现弹性

随着数据流领域的成熟，技术供应商和内部产品团队正在转向更具战略性、可扩展的流治理方法，如 [data mesh](https://thenewstack.io/the-game-changing-appeal-of-data-mesh) 。在这成为现实之前，运营和 DevOps 团队仍然需要确保 Kafka 工作负载的弹性和可用性。

![](img/442285907682500fe45119b33bb12040.png)

桑吉娜·卡翁丁尼亚

管理 Kafka 云部署的数据复制变得越来越复杂，因为许多企业需要在全球部署中复制 Kafka 主题，同时还要遵守数据主权和安全法规。 [Sanjana Kaundinya](https://www.linkedin.com/in/sanjanakaundinya/) ，一位专注于融合的多区域复制和集群链接的软件工程师，将主持一个[会议](https://2022.currentevent.io/website/39543/agenda/)，主题是“无限与超越:跨集群扩展 Apache Kafka 复制协议”

在当今的混合和多云世界中，停机时间变得更加昂贵，也更加难以避免。“当组织的生产流量流经实时关键应用程序时，很难甚至有时不可能引入停机时间来管理运营问题，”Kaundinya 说。

组织可以自动化和修改 Kafka 的复制协议，以针对其特定的操作和灾难恢复要求定制其性能。但是这样做的成本很高，让组织不得不考虑以下利弊:

## **权衡 3:全局弹性与可操作性**

大规模建设一个真正有弹性的卡夫卡架构的开销可能是巨大的。“假设你在加州写了些东西。就此而言，在纽约、欧洲或印度可能会有一些延迟。如何尽可能地减少延迟？您如何在不影响性能、延迟或可用性的情况下，尽可能实现无缝同步？”卡翁丁亚说。“分布式系统非常复杂。当你拥有一个全球分布式系统时，它只会变得复杂 10 倍。”

## 超越卡夫卡:连接数据流生态系统

为了保持创新和开发人员的工作效率，如今使用数据流的组织需要利用云的可扩展性来最大限度地发挥其流数据的价值。这要求在开发、部署和管理云原生应用程序时，尤其是在混合云或多云环境中，仔细权衡运营利弊。

组织如何评估和平衡这些权衡将取决于每个公司独特的业务目标和技术需求。数据流技术的生态系统当然不仅仅由 Kafka 组成——从[其他消息系统](https://www.confluent.io/en-gb/kafka-vs-pulsar/)到数据摄取、集成、监控和开发工具的支持。

了解数据流生态系统中的公司如何在 10 月 4 日至 5 日举行的 [Current 2022](https://currentevent.io/) 大会上应对这些挑战，可以在奥斯汀市中心亲自参加，也可以通过虚拟通行证参加。查看[的活动日程](https://2022.currentevent.io/website/39543/agenda/)，了解 Patel、Kaundinya 和 Gamov 等演讲者带来的主题和讨论。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>