# 动物群旨在为开发者简化数据管理

> 原文：<https://thenewstack.io/fauna-aims-to-simplify-data-management-for-developers/>

2020 年，我们第一次[看了一下](https://thenewstack.io/fauna-and-its-client-serverless-application-model/)T2 动物群，一个打包成云 API 的数据库。将自己描述为一个“分布式文档关系数据库”，vana 的目标是让开发者能够更快地构建现代应用程序并快速扩展。为了了解这个无服务器数据库的进展情况，我们采访了动物界首席执行官[埃里克·伯格](https://www.linkedin.com/in/epberg)。

作为第一批用于数据库的客户机-无服务器应用程序模型之一，Fauna 进入了市场。Berg 说:“文档关系数据库允许你以一种开发人员感到舒适和熟悉的方式存储数据，坦率地说，它更适合你今天在应用程序中拥有的数据类型。”“我们将它与强大的关系特性、外键、视图和连接结合起来。我们的目标是在关系端实现人们开始依赖并真正喜欢的 [SQL](https://www.microsoft.com/en-us/sql-server/sql-server-downloads) 、 [Oracle](https://www.oracle.com/index.html) 和 [Postgres](https://www.postgresql.org/) 的一致性。通常，这两种东西不会在一个特定的数据库中找到。”

他进一步解释了作为一个平台竞争者，动物群与其他数据库的不同之处。“在底层，我们将 NoSQL、文档数据库[和]关系数据库结合在一起，因此命名为文档-关系数据库。除此之外，我们还提供了传统关系数据库的可靠性，以及这种文档数据库的灵活性和开发人员友好性。所以[我们]在建筑上将这两者结合在一起。然后，从交付的角度来看，当我们说作为云 API 交付时，它实际上是将数据库作为服务，并将其提升到下一个抽象级别。”

## **企业开发者采用客户端-无服务器技术**

“堆栈现代化”是指将公司的数据库从传统模式改造为更现代的模式。现代数据堆栈是云原生的，至少由数据收集、存储和分析组成。许多组织正在对其体系进行现代化改造，以便扩展、满足合规性要求或简化流程。

根据 Berg 的说法，建立动物群是为了尽可能容易地从现有的数据平台进行转换。例如，Fauna 与 GraphQL 的集成没有任何问题，graph QL 是企业客户的热门选择。“大型组织正试图将前端和后端分开，以使开发更容易，”他说。“我们在 Fauna 中有一个原生的 GraphQL 接口，所以我们可以非常容易地插入这些架构。”

动物群的最新更新包含专为广泛的企业采用而设计的功能。新的数据导入工具允许用户使用命令行界面导入 JSON 和 CSV 文件。“企业从现有的数据库开始，然后迁移到动物群，”Berg 说，“因此，为他们创建一种产品化的方式来导入这些数据对我们来说非常重要。”

数据导入工具还可以执行“试运行”,以确认导入的数据没有任何错误。此外，现在还有备份和恢复功能。

最后，福纳已经获得了 [SOC 2 Type II](https://us.aicpa.org/interestareas/frc/assuranceadvisoryservices/aicpasoc2report) 认证，这是“企业的一个重要里程碑”，伯格说。诚然，企业客户总是关心数据合规性和安全性，这是理所当然的。随着“大数据”的增长，伴随着高额罚款(甚至更糟)的法规对组织的约束越来越紧。SOC 2 Type II 框架是一个内部审计程序，它向服务组织的客户保证正在采取适当的措施来保护他们的隐私和数据。

## **减轻开发商压力**

在编程社区中，开发人员经常被期望处理任何抛给他们的事情。大多数技能，如数据库构建和管理，都需要时间磨练。Berg 说，“许多开发人员正在构建这些面向用户的新应用程序，他们没有丰富的数据库经验，但他们需要一个数据库来构建和扩展该应用程序。”

承担管理数据库的任务并不容易；如果一个开发人员不小心，它可能会压倒他们的其余时间。Berg 说，对开发人员来说，拥有一个强大的数据库而不需要亲自动手创建或维护是很有吸引力的。

“真正引起人们共鸣的是:在内部，他们认为我的工作是构建一个应用程序来推动业务发展，而不是在操作和扩展数据库方面成为世界上最好的，对吗？所以是那些过去有过那些伤疤的人。他们将动物群视为以下两者的结合:a)文档数据库的灵活性，以及 b)他们在关系数据库中以一种他们不必管理的方式了解和信任的一切。”

根据 Berg 的报告，清理工作流中的空间是各种规模的团队中开发人员的一个共同痛点。“对开发人员的好处是，这只是一个 API 调用。当他们使用 Twilio 发送消息或使用 Stripe 处理支付时，他们不必担心管理 Twilio 或 Stripe 下的服务器。对于动物群也是一样——当您想要调用数据库并运行查询时，您不必担心这些。我们会帮你处理的。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>