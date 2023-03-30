# 当因密码劫持而损失 10，000 美元是一项不错的投资时

> 原文：<https://thenewstack.io/when-losing-10000-to-cryptojacking-is-a-good-investment/>

几个月前，当我们收到 Heroku 异常高的账单时，我立即知道了根本原因:有人利用了我们的架构，劫持了我们的计算资源。我能猜出发生了什么事，因为我们早就知道这种剥削是可能的。我们仍然允许它。不仅如此，面对类似的选择，作为首席技术官的我会再次做出同样的决定。

为了理解“如何”和“为什么”，我们首先需要谈论一下 [Wilco](https://www.trywilco.com/) 的架构。我们是一个年轻的公司，刚刚成立一年多，希望让开发人员获得和实践技能。我们的独特之处在于我们的工作方式:对工作场所的全面模拟。

Wilco 用户的体验与科技公司的工作非常相似。他们有一个 GitHub 存储库，一个类似 Slack 的企业信使(模拟同事)和一个生产环境:数据、用户、负载——所有的一切。

实际上，这非常具有挑战性。GitHub、Slack 和其他 SaaS 工具是为团队使用而构建的。在我们的例子中，我们需要为每个用户创建一个独立的小型组织。让我们看看我们是如何做到的，为什么它是可利用的。

## Wilco 的工作方式

每个 Wilco 用户都有自己的生产实例。他们有一个可以相互通信的前端和后端的 URL，以及一个保存数据的数据库实例。这样，用户可以测试他们的更改(使用 CI/CD)，我们可以通过发送模拟流量的请求来模拟性能问题。

我们用户的生产环境不能是黑匣子，这一点至关重要。我们需要让他们了解正在发生的事情，调试问题和配置，就像他们在实际工作中一样。

## MVP 的争夺

“原罪”是我们渴望尽快准备好 Wilco 的 MVP，并让它进入真正的用户手中。在投入时间和金钱来构建一个合适的、可扩展的解决方案之前，我们需要测试许多假设，看看是否存在对像我们这样的产品的需求。我们还需要能够快速、廉价地开发和删除功能，同时保持灵活性，以便在证明成功的情况下加倍投入。

最简单的方法是将每个回购连接到两个 Heroku 应用程序，一个用于前端，一个用于后端。通过这种方式，我们能够创建一个组织，但让每个用户只能访问他们的应用程序。我们会把代码推给正确的应用程序，Heroku 会处理剩下的。

除了效率高之外，它还具有成本效益。我们使用 Heroku 的免费层( [RIP](https://thenewstack.io/where-can-heroku-free-tier-users-go/) )免费获得了一个数据库，可以只为用户使用资源的时间付费。因此，如果一个用户一个月只花几个小时在他们的应用上，我们会为这几个小时付费。

## 计算风险

你可能已经注意到了我们计划中的一个问题。Heroku 不是为我们正在做的事情而建造的，所以扩展它会很困难。我们知道这些限制，甚至绘制了它们的地图:

1.  Heroku 没有应用程序级别的授权和角色。如果您被邀请使用某个应用程序，您可以使用该应用程序做任何事情。
2.  同一帐户下可以创建的应用程序数量有限制，即 200 个应用程序。这意味着我们只能在一个组织下支持 100 个用户(每个用户有一个后端和一个前端应用程序)。
3.  开发者习惯的复杂用例是不可能的。微服务、队列、缓存和分阶段部署要么是完全不可行的，要么非常复杂，因为 Heroku 不是为这类场景构建的。

对于每种风险，我们都想了解其影响:

*   没有 app 级授权。如果用户拥有这种控制权，他们可以随意配置。升级应用程序 dynos 或添加附加组件可能会花费我们的钱。不幸的是，Heroku 不支持限制应用程序的花费，或者在超过阈值时发出通知，所以我们需要不断关注这一点。也就是说，这并没有打破孤岛——用户只能影响他们自己的应用。
*   200 个应用程序的限制。每 100 个用户我们就会碰壁，但是作为短期解决方案，我们可以手动创建更多的组织。
*   用例简单性。不是问题；我们现在可以关注更简单的用例。

那么最坏的情况是什么呢？Heroku 的一大笔账单，用户在尝试创建应用程序时收到一个错误。不是很好，但也不可怕。另一种选择，从零开始，似乎更糟。

## 成功失败>失败成功

在 Wilco 成立的前三个月里，我们描述的所有糟糕的场景都变成了现实，你对此有多惊讶？首先来了一个合作伙伴，他想要比我们能提供的更复杂的任务，需要多个服务器。然后，我们的一个活动像病毒一样传播，所以我们需要在几分钟后达到 Heroku 应用程序的上限。上面的樱桃是一个用户，他发现他们可以升级他们的 dyno 并添加插件来滥用我们的计算资源，而我们支付了 10，000 美元的账单。

我们难过吗？当然不是！这是一个巨大的成功！我们获得了牵引力和大量有价值的反馈，而无需构建大量我们自己的基础设施。值得称赞的是，Heroku 好心地免除了一小部分账单。如果我们不得不预先建立一切，实验的成本将比这个法案大得多。

如果你可以这么说的话，我们方法的主要缺点是，我们依赖了几个月我们所知道的临时解决方案。但这里也有一线曙光:我们有时间。在构建基于 Heroku 的 Wilco 时，我们已经在规划我们自己开发的解决方案，并确定了构建它所需的资源范围。

当我们收到账单时，我们已经在深入构建我们的解决方案。大多数工作都是在没有任何紧迫感的情况下完成的，因为事情进展得相对顺利。

## 摘要

在创业公司中，时间是我们需要优化的最重要的事情之一。我们不能浪费时间为可能没人用的东西搭建脚手架。有时候，除了冒险一搏，别无选择。

虽然很难构建一个您知道无法扩展的解决方案，并且可能会花费一大笔钱，但是请考虑一下从长远来看您将节省的时间和这次花费的金钱。我们做到了，这就是为什么我一秒钟都不后悔收到那份账单。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>