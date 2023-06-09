# DevOps 实践的六大核心能力

> 原文：<https://thenewstack.io/six-core-capabilities-of-a-devops-practice/>

编者按:DevOps 实践是一项正在进行的工作，但根据新堆栈的创始赞助商 New Relic 的这篇文章，有一些核心功能需要考虑。这篇赞助文章改编自亚纱美·诺瓦克在新遗迹博客上的一个故事:

[6 Elements of Highly Successful DevOps Environments](http://blog.newrelic.com/2014/06/12/divingintodevops/)

.

DevOps 是一个术语，反映了当看似不同的概念变成一个组合时会发生什么。将开发人员和运营结合成一个概念创造了一种新的动态，改变了人们对 IT 的看法以及开发人员在组织中的角色。

为了清楚地思考这个概念，定义任何 DevOps 环境中最重要的功能是很重要的。我们的研究表明，实际上有六个最重要的因素需要考虑:

*   合作
*   自动化
*   连续累计
*   连续测试
*   连续交货
*   连续监视

开发人员和运营人员在历史上一直是 IT 中独立的组织。由于企业系统实践的约束以及从瀑布到敏捷开发过程的转变，它们在许多方面被分开。在将任何应用程序投入生产之前，都需要对其进行配置，以使其按照用户的预期执行。在生产中，应用程序和支持它的系统需要监控。开发人员可以创建应用程序，但通常由系统团队来管理热点、异常峰值和分布式基础架构中的事务。

但是，开发人员和运营人员比以往任何时候都更需要共享实践。效率很重要，但更大的需求是应用程序开发。需要跨移动和网络平台更快地设计、测试和部署应用程序。

DevOps 在这个复杂的新世界中有很多可以提供的。它提供了一个可以在不影响其他工作和个人生活的情况下实施和重复的过程。

但它也带来了障碍。“导航 DevOps”是一本已经出版的电子书，涵盖了 DevOps 的六项功能，帮助公司掌握他们想要实现的目标。本书中的这些观点有助于为开发运维主题提供一些视角:

## **1。协作**

开发和 IT 运营不是互相指责，而是一起合作(不，真的)。虽然这两个群体之间的脱节为它的创建创造了动力，但是 DevOps 远远超出了 IT 组织，因为协作的需求扩展到了软件交付中的每个利益相关者。正如 Laurie Wurster 等人在最近的一份 Gartner 报告中解释的那样:“成功的开发运维需要业务、开发、QA 和运营组织在应用生命周期的不同阶段进行协调并扮演重要角色。她进一步说:

> 消除孤岛可能很难，甚至不可能，但协作是必不可少的。

## **2。自动化**

DevOps 非常依赖自动化，这意味着您需要工具。你制造的工具。你买的工具。开源工具。专有工具。这些工具不只是随意地分散在实验室中:DevOps 依赖工具链来自动化端到端软件开发和部署过程的大部分。

唯一的警告是:因为 DevOps 工具是如此令人惊讶的棒，有一种倾向认为 DevOps 只是一个工具的集合。虽然 DevOps 确实依赖于工具，但 DevOps 远不止这些。

## **3。持续集成**

敏捷开发的[持续集成](http://searchsoftwarequality.techtarget.com/definition/continuous-integration)原则对于开发团队来说具有文化含义。强迫开发人员经常与其他开发人员集成他们的工作——至少每天——比瀑布开发更早地暴露集成问题和冲突。然而，为了实现这一好处，开发人员必须更频繁地相互交流——这与孤独的天才程序员在模块上工作数周或数月，然后“准备好”将其发布到世界上的形象背道而驰。开放、频繁交流的种子在 DevOps 绽放。

## **4。连续测试**

DevOps 的测试部分很容易被忽略——直到你被烧伤。正如一位行业专家所说，“质量的代价就是失败的代价。”虽然持续集成和交付占据了大部分的覆盖范围，但是持续测试正在悄悄地找到它的位置，成为 DevOps 的一个同等重要的部分。

持续测试不仅仅是一个 QA 功能，事实上，它始于开发环境。开发人员可以简单地把代码扔给 QA，然后说“开始吧”的日子已经过去了。在 DevOps 环境中，每个人都参与测试。开发人员确保在交付无错代码的同时，他们提供测试数据集。他们还帮助测试工程师[配置测试环境](http://sdarchitect.wordpress.com/2012/10/30/understanding-devops-part-4-continuous-testing-and-continuous-monitoring/)以尽可能接近生产环境。

持续测试的回报是值得努力的。DevOps 环境中的测试功能有助于开发人员平衡质量和速度。使用自动化工具降低了测试成本，并允许测试工程师更有效地利用他们的时间。最重要的是，连续测试通过允许在过程的早期进行集成测试，缩短了测试周期。

## **5。连续交货**

用一位评论员的话说，“持续交付不过是将持续集成的概念带到下一步。”DevOps 中的持续集成延伸到整个发布链，包括 QA 和运营，而不是在开发实验室门口结束。结果是，单个版本远没有那么复杂，而且发布得更加频繁。

实际的发布频率根据公司的遗产和目标有很大的不同。例如，一家财富 100 强公司将其发布周期从每年一次提高到每季度一次——与亚马逊每小时数百次的发布相比，这一发布速度仍然显得微不足道。

释放的确切内容也各不相同。在一些组织中，QA 和 operations 对潜在的发布进行筛选:许多直接交给用户，一些回到开发，还有一些根本没有部署。其他公司——Flickr 是一个显著的例子——将来自开发者的一切都推给用户，并依靠实时监控和快速补救来最小化罕见故障的影响。

## **6。持续监控**

考虑到发布的绝对数量，没有办法实现瀑布开发特有的那种严格的发布前测试。因此，在 DevOps 环境中，必须实时发现并修复故障。你是怎么做到的？很大一部分是持续监控。

根据[一位权威人士](http://www.slideshare.net/roidelapluie/devops-andmonitoringowf13)的说法，持续监控的目标是快速确定服务何时不可用，了解潜在的原因，最重要的是，在问题发生之前应用这些知识来预测问题。事实上，一些监控专家主张服务的定义必须包括监控——他们认为这是服务交付的组成部分。

像测试一样，监控从开发开始。监视生产环境的相同工具可以在开发中使用，以便在性能问题影响生产之前发现它们。

欲了解更多 DevOps 相关信息，请访问 New Relic 的 [DevOps Hub](http://newrelic.com/devops) ，在那里您可以找到 DevOps 工具的列表。

*T13*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>