# 充分利用您的数据的 5 种方法“湖畔小屋”

> 原文：<https://thenewstack.io/5-ways-to-make-the-most-of-your-new-data-lakehouse/>

在过去几十年中，数据生态系统发生了巨大的变化——从 20 世纪 80 年代的数据仓库到 21 世纪初的企业数据湖，再到今天结合了两个世界的精华的 Lakehouse 概念的兴起。正如[在最近的 Databricks 博客条目](https://databricks.com/blog/2020/01/30/what-is-a-data-lakehouse.html)中所描述的，Lakehouse 是“一个新的、开放的架构，它结合了数据湖和数据仓库的最佳元素……它们是你在现代世界中不得不重新设计数据仓库时会得到的，现在廉价且高度可靠的存储(以对象存储的形式)已经可用。

这里有五种方法可以成功利用湖边小屋，并实现大规模的数据和人工智能(AI)来转变您的组织。

## 建立实施目标和业务价值

 [克里斯·达戈斯蒂诺

Chris D'Agostino 于 2020 年 1 月加入 Databricks，担任全球首席技术专家。在这个职位上，Chris 为我们全球主要客户的高管提供思想领导和指导。Chris 是一名经验丰富的工程管理人员和企业家，在金融服务行业和美国情报界都有着成功的记录，服务的公司从初创阶段到财富 100 强不等。](https://www.linkedin.com/in/chrisdagostino1/) 

当开始人工智能驱动的数字化转型之旅时，大多数组织通常会建立一个首要目标，即成为机器学习第一的公司。这是一个巨大的目标，需要管理层的认同和支持，通常是在 CEO 和董事会层面。

一旦您收到这些利益相关方的签字认可，您就可以通过实施现代云数据架构来开始转型，以保证您的投资经得起未来的考验，并在云上全力以赴。以前，组织关注主要的云供应商，但考虑到当前的限制、法规遵从性要求和竞争格局，越来越多的公司正在转向多云解决方案，以便在他们选择的云环境中分发和运行工作负载。

专注于技术变革并不足以巩固变革——你还需要改变团队的工作方式。通过统一组织中存在的各种角色(数据科学家、数据工程师、业务分析师和领域专家)，您可以让他们针对同一组数据一起工作，通过关键用例来推动业务价值。这种文化转变让公司变得更加数据本地化。

## 确定高价值用例并确定其优先级

为了确保您的数据团队利用最高价值的用例，您需要在数据平台架构、人工智能目标和道德规范、技能组合的正确组合以及对正确数据的访问上保持业务和技术领导力的一致。

正确的优先级划分是进攻和防御用例之间的微妙平衡。进攻性策略旨在增加收入和客户获取，同时降低运营成本。一个进攻性用例的例子是使用人工智能来推动客户营销细分，以增加可能转化的客户群。另一方面，防御性用例是为了防范和保护您的组织免受风险增加的影响，并确保合规性——例如使用人工智能来监控来自移动和 web 应用程序的点击流事件，以识别欺诈。

通过定期使用记分卡来度量正在使用的用例，您可以确定它们的战略重要性、可行性和 ROI。需要注意的是，并非每个用例都具有相同的优先级，即使具有相同的业务价值，因为有些用例更难实现，或者需要不同的数据集，这些数据集可能不容易获得。为了在数据和人工智能方面取得成功，你需要寻找快速的胜利，并从那里建立势头。

## 简化数据治理和合规性

Lakehouse 体系结构使您能够创建单个计算层，从而以更加高效和一致的方式执行数据优化和治理。通过使用一组标准的编程 API，您可以实现自助式数据注册，并自动执行创建强大的数据目录和细化数据所需的许多手动且容易出错的步骤。在大型企业中，自助服务功能尤其重要，因为在这些企业中，数据团队往往会因为与数据治理和法规遵从性相关的官僚流程而变慢。

数据质量也很重要—目标是集中数据质量规则，以便团队能够在数据到达湖中时尽快执行。例如，如果系统中输入的新数据点是出生日期，它不能被列为未来日期，因为这意味着该人还没有出生。另一方面，它也不能被列在过去 140 年，因为这个人已经不在人世了。在一个能够自动执行这些类型的企业级数据质量规则的平台上设置这些规则是关键。

## 让高质量数据的访问民主化

为了确保数据的高质量，数据团队还必须考虑其“时间价值”。当数据项第一次到达您的组织时，它在创建的那一刻就具有非常高的价值。例如，如果您可以立即对单个数据采取行动，例如可疑的信用卡交易，您就可以做出实时决策并检测欺诈。虽然单个数据项的价值会随着时间的推移而下降，因为它不再相关，但聚集的旧数据会再次变得有价值，因为它可以揭示关键趋势或帮助您训练模型以改进欺诈检测或类似流程。

为了使对高质量数据的访问民主化，您需要最大限度地减少生态系统中数据的副本数量。数据团队经常在既有数据湖又有企业数据仓库的分离环境中工作，这导致相同数据的副本驻留在不同的平台上。我不推荐这种方法，因为创建额外的数据副本会增加风险，而且很难保持所有数据同步。通过利用 lakehouse 方法，您可以将所有数据放在一个地方，最大限度地降低成本，并需要更少的工具来完成工作。

## 做出明智的构建还是购买决策

一旦你有了正确的解决方案，你需要权衡选择供应商产品和“自己开发”解决方案的利弊。任何时候，当您决定部署工程资源来构建您自己的解决方案时，您实际上就成为了您自己的软件供应商，并承担了随之而来的所有责任。有利的一面是，您将能够控制整个产品/平台路线图，并确定下一步要构建的特性的优先级。缺点是您需要在简化 CI/CD 渠道方面进行大量投资，以确保可以快速部署更改和修复，并为板载用户和新开发人员提供详细的文档和培训，同时牢记 DevOps 模型的成本支持。

从我个人的经验来看，你的商业伙伴和其他依赖平台运行和分析用例的团队不会太关心平台从何而来，如何构建。他们更关注它多快可以得到，它是否支持他们的用例，以及它是否可靠。

## 利用湖边小屋架构获得改变游戏规则的洞察力

现在，每家公司都在从事风险管理业务，数据是我们拥有的最有价值的货币——推动商业价值，降低成本，防范多种形式的风险，其中一些风险是人工智能本身特有的。在 2020 年，我们已经看到了 Lakehouse 架构的回报，使数据团队能够拥有更高效的数据管道环境、可动态扩展和缩减的计算资源，以及符合您设置的成本和数据治理政策的数据平台。展望未来，一旦组织实施了 Lakehouse 架构，其数据团队就可以更轻松地专注于开发改变游戏规则的洞察力。

大卫马克德皮沙贝。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>