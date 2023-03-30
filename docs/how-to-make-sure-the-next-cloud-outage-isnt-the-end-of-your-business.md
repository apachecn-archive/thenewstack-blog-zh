# 如何确保下一次云中断不会终结您的业务

> 原文：<https://thenewstack.io/how-to-make-sure-the-next-cloud-outage-isnt-the-end-of-your-business/>

对于云服务提供商和依赖他们的企业来说，这几个月过得很艰难。Salesforce、LinkedIn 和 Twitter 的中断中断了销售和营销业务。Stripe 最近的宕机影响了数百万的销售额。然后是 Google 和 CloudFlare 宕机，影响了许多在云中运行部分或全部关键业务软件的企业。

即使您的业务还没有在云中运行，与您合作的供应商和提供商仍然可以让您的业务流程随之中断。

## 接受不可避免的事实:一切最终都会破碎

 [詹姆斯·伯恩斯

从网络负载平衡器到 FPGAs 到 ASICs 到嵌入式安全再到大规模的云操作，James 目睹了系统如何工作，但更有趣的是，他们是如何失败的。他热衷于分享他所学到的东西，以提升团队水平，让开发人员更开心，并改善客户体验。他认为,“如果它没坏，那就坏了，这样你就知道如何修复它”,这应该是各地开发人员、DevOps 和 SREs 的座右铭。在 Twilio 和 Stitch Fix 工作期间，James 直接与大型云服务提供商的工程团队合作，快速找出影响客户的问题的根源。作为 LightStep Research 的负责人，他能够公开分享实现这种密切合作的工具和技术。](https://www.linkedin.com/in/james-burns-7816a82/) 

不仅仅是云服务提供商出现中断，还有如何发现中断。你可能会从你的客户那里了解到一些东西坏了，他们突然不再能够访问你的服务。因为状态页面并不总是最新的，所以你可以从 Twitter 上找到什么东西坏了(如果它还在的话)。当你的企业亏损时，刷新 Twitter 搜索页面不是任何人的好主意。

理想情况下，云服务不会出现故障，这就是您所支付的费用，对吗？不幸的是，现实是，没有一笔钱可以提供 100%的正常运行时间，即使非常接近也比大多数人愿意支付的要多得多。

一旦我们接受云服务将会停机，我们就可以开始构建技术和业务解决方案来最大限度地减少停机时间。我们使用云服务提供商来卸载对我们公司的价值主张不核心的专业知识，并利用技术专业知识。即使云服务允许您不必运行非常复杂的分布式系统，您的团队仍然需要建立可观察性，以允许您了解他们的工作做得有多好。如果他们没有做好自己的工作，你的服务或业务因此受到损害，那么你与他们进行一次艰难的对话是至关重要的。

接受东西会坏掉并不等于服务质量差也没问题。

## 可观测性:最佳不完美解决方案

为了了解云服务的健康程度，您需要能够衡量:

*   你要求云服务为你做一些事情。
*   做那件事花了多长时间。
*   它是否成功地做到了。

例如，如果您将宠物店客户的猫的照片保存在一个云对象存储中，您会想知道它们具体存储在哪里、在哪里被检索、每个操作需要多长时间以及在尝试执行这些操作时是否有错误。然而，你应该被警告，这些测量的结果可能会令人惊讶。云服务经常会变得有点慢，或者有一小组错误。也许您以前认为这些是您自己程序中无法解释的错误，或者只是客户的一些随机投诉，但实际上它们是“小中断”，或者更准确地说，是您必须学会为更大的中断做计划的例行故障。

虽然基本的可观察性将改变您看待云提供商的方式，但这通常不足以了解对您业务的影响。您可以看到 1%的云服务请求失败，但是如果没有业务背景，您不会看到这 1%影响了您最大和最重要的客户。这就是为什么考虑扩展您的可观察性以包括“分布式跟踪”是重要的，这种工具允许您将业务上下文带入您的软件对云服务的使用中。有了跟踪的上下文，您的团队将能够看到 1%的失败是有点烦人还是一个关键的业务问题。

## 增加业务流程的弹性

提高您的企业对云服务故障的恢复能力的另一种方法是在您的所有业务流程中创建故障响应。这些响应可以涵盖范围广泛的行动:

*   “我尝试使用此服务，但失败了，我打算等一会儿再试一次”
*   “这对于我的业务来说是一项至关重要的交易，所以我将把它存储在三个不同的地方，始终交叉检查它们，如果它们不匹配，就立即呼叫某人”
*   “如果我们的提供商停机超过 15 分钟，我们将改变我们的网页，并要求人们打电话给我们，让他们继续与我们做生意。”

当然，具体的正确步骤取决于您使用的提供商和您的业务流程。

一旦你对失败做出反应，就像其他事情一样，它们需要被测试。为什么？因为一个未经测试的计划不太可能成功。复杂的事情发生了，人们可能没有执行计划所需的信息或权限。以尽可能现实的方式练习应对失败将会提高你的企业和团队的应变能力。你会对自己优雅地处理各种情况的能力充满信心。(参见:混沌工程)

为您的云提供商实施可观察性和故障测试的最终结果是，确信下一次重大停机对业务的影响将是最小的。通过使用[分布式跟踪](https://lightstep.com/)，您将能够立即了解每一次失败的业务背景，从而做出明智而慎重的选择，增强客户对您业务的信心。当下一次云宕机发生时，您将准备好管理并从该过程中学习。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>