# 编码器作为会计:无服务器系统设计是基于成本模型

> 原文：<https://thenewstack.io/coder-accountant-serverless-systems-design-based-costing-models/>

计算使用无服务器架构构建应用程序的成本将从根本上改变企业中开发人员和系统架构师的角色。而在过去，技术领导者可能需要在特定的预算参数内设计解决方案，随着[无服务器](/category/serverless/)的出现，这完全颠倒了过来，正在构建的应用程序可能会设定公司未来的预算。

去年在纽约举行的 Serverlessconf 上，一个明确的主题是无服务器架构师和应用程序开发人员在实现之前对他们的系统设计进行财务计算。随着对开发者选择的预算影响的新关注，正如亚马逊网络服务的高级开发者倡导者 [Paul Johnstone](https://www.linkedin.com/in/padajo/) 所说，许多关于无服务器的讨论“实际上是关于好生意的”

越来越多的例子表明开发人员在编程决策中考虑到了成本。

## 函数不是 Webhooks

[auth 0 Extend 的产品管理总监 Glenn Block](https://www.linkedin.com/in/gblock/) 指出，在寻找 API 实时轮询替代方案的企业中，无服务器的使用越来越多。“使用 webhooks，这与构建和维护一个 API 非常相似。因此，在一个大公司里，你需要运营来监控它，需要财政来为它做预算，这涉及到许多复杂的问题，”博克说。

在 SaaS 的供应商中，构建 webhook 功能也受到成本因素的抑制，这促使一些大型公司，如 [Twilio](https://thenewstack.io/twilio-functions-show-serverless-useful-model/) 和 [Okta](https://thenewstack.io/okta-wants-identity-service-developers-not-just/) 在无服务器平台上构建，并允许他们的客户部署所谓的“产品内可扩展性”:在使用开箱即用的 SaaS 功能之前或之后添加功能的能力，同时避免提供 webhooks 基础设施的成本。

> 一个商业教训:为一些 lambda 选择更高的内存利用率可能意味着函数运行得更快，这比与更便宜、更低内存选项相关的处理成本更低。

布洛克的例子更像是一种重大决策，由于成本的原因，某些选择从一开始就不在考虑范围内。因此，技术领导必须考虑其他创造性的解决方案，以在设定的预算内实现目标。

其他无服务器开发人员发现成本结果可能看起来违反直觉。来自 [New Relic](https://newrelic.com/) 的 Clay Smith 和来自德勤的 [Gary Arora 都认为在设计无服务器系统时，成本和架构设计之间往往存在一个最佳平衡点。他们分享的一个性能教训是，为一些 lambda 选择更高的内存利用率可能意味着函数运行得更快，这比与更便宜、更低内存选项相关的处理成本更低。通过运行应用程序任务来测试无服务器消耗计划有助于做出设计决策。](https://thenewstack.io/amtrak-rolls-past-containers-serverless/)

## 三个无服务器成本因素

研究人员 [Gojko Adzic](https://gojko.net/) 和 [Robert Chatley](https://www.doc.ic.ac.uk/~rbc/) 最近 [发表了一项研究](http://www.doc.ic.ac.uk/~rbc/papers/fse-serverless-17.pdf) 表明，由于无服务器平台的可用性，越来越多的架构决策是基于成本做出的。在 2017 年的研究中，他们确定了影响建筑决策的三个因素:

*   **没有预留容量:**在标准架构中，开发人员必须在资源有限的情况下构建应用程序，同时还要考虑提供故障转移能力的需求。研究人员估计成本降低了 99.95%，因为开发人员不再需要在主服务器旁边运行故障转移机器，“因为平台隐含地提供了这一点。”
*   **分布式需求级授权:**由于在无服务器架构中执行的所有功能都是不可信的，并且需要单独的验证和授权，因此没有网守服务器进程的角色，这在客户端/服务器工作流中是典型的，作者说，从而降低了另一个重要的架构成本。
*   **独特的服务利用成本:** Lambdas、EC2 实例、AppEngines 和 Analytics 服务都在无服务器架构中单独收费，并具有不同的利用成本。正如 Smith 的内存利用率最佳点的情况一样，可以采取旨在优化整个应用程序的处理成本的架构决策。作者给出了一个从客户端应用程序通过 Lambda 函数向 S3 上传文件的例子。大文件意味着巨大的成本，因为 Lambda 需要很高的内存限制(以更高的费率收费)。作者建议，一个应用程序设计决策可以是“使用 Lambda 函数授权客户端将特定文件写入 S3，然后将文件直接从客户端应用程序上传到 S3，随后触发 Lambda 函数来处理该文件。这将允许第二个 Lambda 函数使用流数据 API，并在内存限制显著降低的情况下工作。”作者认为这种设计上的改变可以将成本降低“一个数量级”

Block、Smith、Adzic 和 Chatley 的例子可能都是对的，但是 IT 架构师经常被要求在限定的预算内找到技术解决方案，那么为什么这预示着一个根本性的转变呢？尤其是因为无服务器项目，即使在企业的早期采用者中，目前也常常是次要考虑的问题。

越来越明显的是，一些大型企业的开发人员(例如，媒体正在考虑无服务器，因为他们的许多大规模核心业务过于昂贵，无法以任何其他方式管理)正在评估实施成本*在*任何架构设计决策之前，一直到中心。这使得开发人员不仅要提出新计划的建议，还要决定如何使用相关的预算。

## 开发商做成本计算，决定业务方向

软件工程师 [Alex Bielen](https://www.linkedin.com/in/alexbielendeveloper/) 描述了一个案例，一家财富 500 强公司在迁移到无服务器时能够计算出它在基础设施上仅花费了 12.53 美元。管理项目的预算节省下来的钱可以由架构团队分配，以解决无服务器的一些不成熟问题。他们将这些钱再投资于开发新的安全工具。

所有这些例子都表明，在无服务器环境下，开发人员的业务角色正在发生变化。在最佳实践 API 策略和设计中，业务和技术领导更紧密地合作，以构建与业务价值和创收更紧密结合的技术。无服务器甚至更进一步，技术几乎成为业务决策者。在无服务器中，它不是传统的结构化业务组织，在这种组织中，开发人员可以构建在供应成本限制内运行的应用程序。现在，无服务器应用程序决定配置。对于习惯于专注于构建解决方案而不是预测成本的开发人员来说，这是一个巨大的思维转变。

来自无服务器应用性能监控初创公司 [的内特·塔加特](https://www.stackery.io/)说，这是开发者角色的一个根本性变化，随着无服务器系统变得越来越普遍，将需要新的业务决策过程。“这肯定是一项新技能，”内特说。“我的团队纯粹在无服务器环境中工作，因此在这方面，它是世界上最复杂的工程团队，这是我们作为开发人员以前从未考虑过的事情。这种转变的程度有待讨论，但业务和预算责任显然正在从运营转向开发。”

Nate 指出了开发人员制定的新预算决策影响业务决策的几种方式。

在无服务器架构中，一旦服务器开始处理，工作量可能就不那么重要了。与长期配置服务器的成本相比，短期突发工作的成本不会很高。因此，开发人员可以改变批处理等工作负载的运行方式，一次批量完成它们，而不是随着时间的推移缓慢运行。这甚至可能导致业务决策的进一步变化:对数据库进行一系列状态检查——如运行事务更新——需要花费资金，因此开发人员可能会设计出远离运行过于频繁的 cron 作业的解决方案。就像 Smith 和 Arora 给出的内存使用示例一样，无服务器处理架构决策可能会带来规模经济的好处。

正如研究人员 Adzic 和 Chatley 指出的那样，塔加特描述了亚马逊自己的 Lambda 定价结构如何影响开发者的应用程序架构决策。在 Amazon Lambda 中，处理是以 100 毫秒为时间单位来计费的，所以任务运行的时间越长，开销就越大。这意味着运行 103 毫秒的任务的成本是运行 99 毫秒的任务的两倍。因此，当开发人员构建应用程序时，他们将寻找分配工作负载的方法，以便代码在低于 100 毫秒的预算水平下运行。

塔加特说，无服务器应用程序只有在运行时才真正有成本，这意味着企业也可以创建更多的应用程序并进行测试。除了开发时间之外，运行不成功的应用程序的成本也大大降低，因此更多的企业可以加快产品发布周期，试验新的服务，看看什么适合市场。塔加特认为，这可能会为创新和产品设计开辟新的模式。

现在还为时尚早。无服务器仍被用于辅助项目、新颖的实验和特定的生产用例，因此改变开发人员的角色以成为财务决策者的全面影响还不存在。但是，目前帮助支持开发人员做出这些决定的过程是有限的，指导他们承担新职责的培训机会更少。但是有一点越来越清楚:随着无服务器的出现，开发人员所做的决策越来越具有有形的成本和业务影响。

专题图片:Igor Ovsyannykov 在 [Unsplash](https://unsplash.com/search/photos/cash-machine?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的照片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>