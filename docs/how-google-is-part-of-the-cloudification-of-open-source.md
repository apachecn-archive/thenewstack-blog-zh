# 谷歌如何成为开源云化的一部分

> 原文：<https://thenewstack.io/how-google-is-part-of-the-cloudification-of-open-source/>

选择“同类最佳”开源数据库作为托管服务是对开源和 AWS 之间持续对抗的回应，具有实际和商业优势。但谷歌也在利用开源软件向云的转变，以满足企业客户的需求。新的堆栈与谷歌合作的开源组织的领导人进行了交谈，以了解这是否不仅仅是联合销售。

正如谷歌负责技术基础设施的高级副总裁[Urs hlz le](https://ai.google/research/people/author79)在上个月的[谷歌 Next](https://cloud.withgoogle.com/next/sf/) 活动上告诉我们的，开源已经成为许多企业 IT 的重要组成部分，但它没有跟上云的采用。“开源软件的更大范围已经在企业中获得了认可、相关性和重要性，我们认为这不会在云时代结束。今天，许多非常传统的企业实际上深深地投资于开源；他们的书库里到处都是。如果云是未来，那么开源就需要云中的未来。”

但他指出，开源通常比云的托管服务需要更多的运营参与。“这是一个复杂的问题，因为云确实改变了开源消费的本质。以前是‘你下载，你安装，你自己运行’；对于云，这是一件奇怪的事情。您希望将它作为一项服务来消费。”

## 没有 Ops 的开源

“企业的两大趋势是开源和云，这两个东西如何结合的故事还没有得到很好的解决，”基于开源的流媒体平台 Confluent 的首席执行官兼联合创始人 Jay Kreps 说。这就是谷歌的方法试图改善的地方。

“这是关于采用开源平台，并将它们重新想象为云原生系统，这是一个灵活的、按需付费的系统，您可以在几秒钟内访问它。我认为，对于在云中开源的人来说，这并不是普遍的体验。这些是公司想要围绕其建立的平台；他们喜欢没有锁定的事实，他们喜欢这些项目周围的开放生态系统，但这是为了让它们现在成为真正的云系统，”克雷普斯说。

这种方法特别适合现代的 NoSQL 数据库， [Redis Labs](https://redis.com/) 的首席执行官兼联合创始人 Ofer Bengal 向我们解释道。所有这些数据库都是以这样一种方式构建的，即需要更少的持续操作，数据库的持续操作是完全自动化的企业也在使用多个数据库，而以前他们可能只选择一个商业 DBMS。“您不仅可以在同一组织中找到多个数据库；您会发现多个数据库支持一个应用程序。”

但是同样的趋势使得包括 Redis 在内的开源提供商日子不好过。“云提供商比开源计划更强大；他们把它们捡起来并把它们货币化。如果没有像谷歌这样的倡议，开源最终可能会消亡，因为云提供商消耗了围绕开源的整个市场机会，没有什么留给做项目的公司。”

Bengal 认为，这对于较小的工具和插件来说问题不大，但对于开源基础设施项目来说尤其痛苦。“数据库是一个大规模的开源项目；它通常有几十万行代码。这不是单个开发人员就能完成的，你需要一个大型团队，因为这是堆栈中的最低层，它与应用程序堆栈中的所有东西都有联系，而且成本非常高。你在开发一些东西时付出了所有努力，希望你能够以某种方式将其货币化，然后云提供商比开源倡议更强大，所以把它们捡起来并货币化，只给开源开发者留下很少的东西。”

他指出，Redis 的开源版本可以从所有的云提供商那里获得。“AWS 有 ElastiCache，它基本上是一个自动化的开源完全托管的 Redis 服务。微软有 Azure Cache，甚至谷歌云也有云内存商店。”

Bengal 说，提供比开源版本功能更多的商业版本还不足以与那些云服务区分开来。“我们认为像 Redis Enterprise 这样在功能上更好的产品可以解决这个问题；显然不是！”

## 云尺度

像 AWS、Azure 或谷歌这样的超大规模云自然会比 Redis Labs、Elastic 或 MongoDB 这样的单一开源公司拥有更多客户和更多资源。正如分析师 Charles Fitzgerald 在一篇有点像 T2 半开玩笑的文章中指出的那样，谷歌上的托管数据库服务可以利用比任何单一供应商运营的相同服务多得多的资本支出投资，并且他们可以提供组织需要的所有其他服务，无论是 IaaS、PaaS 还是其他开源数据库。

谷歌的霍尔兹勒指出，云提供商能够提供的一致性让客户的生活变得更简单。“如果一家公司使用 17 种不同的开源软件包，他们就不会有七套不同的规则以及安装、配置和管理它们的方式，而是只有一套规则。”如果你使用的是开源技术的商业版本，不必为每项新技术建立一个新的计费账户，这对企业来说要方便得多。“如果我使用 17 个不同的软件包，让我在同一个计费分析中看到所有这些软件包，这样我就不必从它们、它们和您那里下载 Excel 文件……”

[时间序列数据库公司](https://www.linkedin.com/in/kaplanevan) [InfluxData](https://www.influxdata.com/) 的首席执行官埃文·卡普兰同意这一观点:“(在云平台上)服务的聚合实际上对客户来说是一件非常有用的事情。”

据 MongoDB 董事会成员 Tom Killalea(该公司已经与谷歌合作了两年)称，MongoDB[被设计为云就绪。他说，随着谷歌云平台(GC)增加区域，“你可以让你的数据在你想在的任何地方，并在司法上符合你想保存数据的地方”。](https://twitter.com/tomk_)

如果你想在数据库中使用的数据已经存储在云上，另一个好处是“数据有引力”，他说，图形数据库提供商 [Neo4j](https://neo4j.com) 的首席执行官&联合创始人[埃米尔·艾弗雷姆](https://www.linkedin.com/in/emileifrem)指出。

他指出，与 TensorFlow 等谷歌工具的合作是 Neo4j 的绝佳品牌。“对于更大的云供应商谷歌来说，这是一个很好的战略，符合开源社区的战略。我们得到的是一个 Oracle、DB2、SQL 数据库基础架构 20 年的分解，分解成有针对性的、马换课程的孤立数据库，如图形数据库、搜索数据库或时间序列。这感觉像是在正确的时间进行了正确的干预。”

如果托管服务方法对最初的七个合作伙伴有回报，他们的商业服务与谷歌自己的服务处于同一水平，谷歌会进一步扩展该计划吗？鉴于所有开源公司提到的优势之一是在服务列表中脱颖而出，而不是隐藏在有成千上万竞争对手的市场中，也许不是。“我认为他们会将自己局限于数据库等同类最佳的产品，而不是随便找个人；那会扼杀整个概念，”Bengal 告诉我们。“我不认为他们会有 50 种或更多的产品在这个项目下。”

如果事实证明这是将开源引入企业的正确模式，那么这种程度的集成也不会只属于 Google。“我们肯定会与其他云提供商合作，”Bengal 告诉我们；“我认为这是正确的方法。”

正如企业 Cassandra distribution [的首席执行官 Billy Bosworth](https://www.datastax.com/) 所说，“我们将继续与亚马逊和 Azure 合作，开发他们的最佳技术；这只是一个新世界，每个人都必须适应它。”

流入数据是新堆栈的赞助商。

来自 Pixabay 的 Vane Monte 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>