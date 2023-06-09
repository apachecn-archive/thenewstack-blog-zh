# 用混沌工程故意破坏无服务器

> 原文：<https://thenewstack.io/breaking-serverless-on-purpose-with-chaos-engineering/>

随着混沌工程成为主动寻找系统弱点的一种更主流的方式，我们看到它被应用于日益复杂的环境和各种规模团队的[](https://thenewstack.io/safe-to-fail-reinforce-distributed-systems-with-chaos-engineering/)。

其中一个领域是无服务器。毕竟， [无服务器计算](https://thenewstack.io/serverless-101-how-to-get-serverless-started-in-the-enterprise/) 是一种语言无关的、现收现付的方式来访问后端服务。这使得它是多租户、无状态、高度分布式的，并且严重依赖第三方。有这么多事情超出你的控制，很多事情都会出问题。

从更高的粒度到扩大攻击面再到新的故障类型，无服务器有如此多的潜在故障点，注明[](https://www.thundra.io/thundra-overview)桑德拉 [艾姆拉·萨姆丹](https://twitter.com/emrahsamdan)at[chaos conf](https://www.chaosconf.io/)，主持 [Gremlin](https://www.gremlin.com/) 。混沌工程是在这些潜在故障影响你的运营之前找出它们的一种方法。

## **什么混沌工程不是**

如果今年的 ChaosConf 有一个潜在的主题，那就是定义什么是 [混沌工程](https://thenewstack.io/chaos-engineering-can-give-distributed-systems-stability/) 。因为，即使在纵火专家中，解释这个概念既是科学也是艺术。

对萨姆丹来说，这不是为了惩罚而暴食，因为你喜欢而打破你的系统。这不是要责怪谁。

对他来说，混沌工程就是问:“如果呢？”

萨姆丹说，“你需要问你的系统:如果你的数据库变得不可达怎么办？如果你的整个地区都垮了呢？如果我的下游 Lambda 超时了怎么办？任何类型的故障都可能发生在您的系统中。混沌工程回答了这些问题。”

他说，你需要回答这些问题，以确定你的系统的可接受极限。他将其比作疫苗，每次都给你的系统注入更多的弹性和信心。

> “混乱不是一个坑。混沌是一架梯子。”—桑德拉埃姆拉·萨姆丹

## **如何入门混沌工程**

Samdan 呼应了 ChaosConf 的另一条信息，提醒我们混沌工程并不仅仅适用于大型流媒体公司。任何人都可以做到这一点，你可以从小处着手。他甚至建议一开始就避免在生产中这样做。

“你可以在筹备的时候就开始。从小处着手。开始注入一个相对较新的服务，但把你的工具放进去，通过混沌实验变得更强大，”他建议道。

从测量你的稳态开始——系统的起伏。他建议使用一个可观察性工具来完成这个任务。

[典型的系统级指标](https://thenewstack.io/googles-formula-for-elite-devops-performance/) 包括:

*   内存使用量
*   99%的延迟
*   CPU 使用率
*   恢复服务的时间

Samdan 表示，典型的业务级指标包括:

*   **Apdex score** ，其中 [根据 New Relic](https://docs.newrelic.com/docs/apm/new-relic-apm/apdex/apdex-measure-user-satisfaction#:~:text=The%20Apdex%20score%20is%20a,as%20half%20a%20satisfied%20request.) ，是被满足和容忍的请求数占总请求数的比值。每个满足的请求计为一个请求，而每个容忍的请求计为半个满足的请求。
*   **交易笔数**，成功与否。

为每个指标设置可接受的限制。然后发展一个假设:如果发生这种情况会怎么样？一些例子可以是:

*   如果我在我的架构中给每个 Lambda 函数注入平均 300 毫秒的延迟会怎么样？SLA 承诺:我的响应仍然在可接受的延迟范围内。
*   如果我的 DynamoDB 表变得无法访问怎么办？SLA 承诺:我的系统将继续执行优雅的服务降级。

你可以问一些大问题，但是只从小的部分开始实验。Samdan 提醒您，只将失败注入到系统的受控部分，就像只向一个功能注入延迟，而不是整个架构。你想保持较小的爆炸半径。

这也是你一次只做一个实验的原因。然后你可以继续，在二、三、四个函数中注入延迟。他说你要坚持下去，直到有东西坏掉。

“当出现问题时，您应该停止，即使您没有在生产中运行它。你应该停下来，只是为了理解当这种事情发生时，你将如何回滚，”萨姆丹说。

他重复了 Liz Fong-Jones 在她的混沌演讲 中所说的话:当你进行混沌实验时，你绝对应该有意识地计划，并让每个人提前知道。

“你不需要让别人吃惊。不需要给其他部门惊喜。最重要的是，在生产过程中，你的客户应该了解这一点，”他说。

因此，如果事情变得非常糟糕，他们并不担心，因为你提前谈过了，而且你已经有了一个回滚的计划，并且你也和他们分享了这个计划。

## **混沌工程在无服务器中的不同工作方式**

在高度分布式和 [事件驱动](https://thenewstack.io/gwen-shapira-on-the-power-of-event-driven-architecture/) 的无服务器环境中，混乱变得更加复杂。无服务器的风险往往来自你无法洞察或控制的服务。本质上，无服务器在本质上是混乱的。

在无服务器的情况下，您会继承许多资源中的一系列全新故障，包括:

*   耗尽内存，因为你只有有限的内存。
*   功能可以直接停止。
*   某个功能可能运行太慢，然后超时。
*   您可以达到并发执行限制。
*   错误配置的访问权限可能会阻止您的功能运行，或者授予某人超出其应有权限的访问权限。
*   [有毒事件可能发生](https://blog.thundra.io/what-makes-serverless-difficult-and-how-thundra-can-help)——类似有毒消息让你的 Lambda 函数重试数百次，直到数据过期。

萨姆丹说，如果你只是与另一个系统同步通信，等待响应，这些都是定时炸弹。

在无服务器中，您也可能会遇到一些故障，例如:

*   与无响应的下游服务同步通信。
*   错误从云服务或其他第三方级联到用户。
*   不良的编码实践，比如递归，会一次又一次地导致你的应用程序超时。
*   从以前的开发者那里继承的错误。

但是所有这些缺陷都很容易让你用混沌实验来审问，比如:

*   你可以将失败注入到你的 Lambda 函数或其他服务交互中。
*   您可以将延迟注入这些相同的功能或交互中。
*   你可以玩 Lambda 函数的并发性。
*   玩转 [IAM 权限](https://aws.amazon.com/iam/features/manage-permissions/) 。
*   看看当下游服务变得不可达时会发生什么。

一切都遵循相同的模式:

1.  观察
2.  假设
3.  实验
4.  暂停
5.  测量
6.  学

Samdan 说，延迟是最重要的无服务器测试指标，因为在无服务器测试中，如果响应延迟，这通常是服务中断的迹象。

他说，无服务器问题的一个常见解决方案是尽可能实现异步通信，然后适当调整同步超时。

其他无服务器修复包括将断路器放置到位，并使用 [指数补偿](https://en.wikipedia.org/wiki/Exponential_backoff) 来找到可接受的调步重传速率。

萨姆丹说，混沌工程是关于学习当某些事情发生时，你的系统应该如何运作。它还能让你制定一个如何作为一个团队应对问题的计划:

*   警报系统和谁被侦测到。
*   冲击测量。
*   您的回应。
*   如何以及何时通知用户。

这种系统的、持续的实验不仅仅是改善你的系统。Samdan 提醒我们，这也改善了团队沟通。

> “你只需要让你的系统为混沌工程做好准备，因为如果它是一个无服务器系统，你就永远不应该停止运行实验。”—桑德拉埃姆拉·萨姆丹

“你永远不应该让你的团队变得更困难。你不应该停下来拥抱行动。事故可能会发生。我们在这里是为了提高自己，而不是伤害他人，”他说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>