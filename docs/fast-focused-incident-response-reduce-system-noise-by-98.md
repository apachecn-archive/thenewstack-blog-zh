# 快速、集中的事件响应:将系统噪音降低 98%

> 原文：<https://thenewstack.io/fast-focused-incident-response-reduce-system-noise-by-98/>

今天的组织陷入了困境。绝大多数人希望接受数字化转型，以提高工作效率，并提供客户和员工渴望的体验。但是，这种项目带来的 IT 复杂性会将技术团队推向极限，让他们筋疲力尽，沮丧不已。

这就是 AIOps 和自动化能够带来巨大成功的地方。然而，要知道在哪里以及如何交付价值，或者应该部署哪些工具，并不总是那么容易。

降噪是数字操作团队可以开始获得一些快速胜利的一个领域。有效地应用[机器学习](https://thenewstack.io/key-concepts/machine-learning/)能力来关联警报可以帮助抑制噪音，并显著增强响应者快速高效地完成工作的能力。

## **喧嚣的世界**

AIOps 的基本目标是帮助开发人员和工程师轻松发现并快速解决问题，以最大限度地减少 IT 停机时间。但是当被大量的警报淹没时，他们就做不到了。底线是事件响应者淹没在信息中。研究表明，69%的 DevOps 和 ITOps 团队每天都在与[的](https://www.pagerduty.com/digital-pressure/)[警报噪音](https://thenewstack.io/fight-alert-fatigue-how-to-wake-up-your-alerts-strategy/)作斗争。

为了提供帮助，组织可以求助于几种工具和技术。如今，人们对重复数据删除(“dedup”)有了很好的理解，它通过 API 集成来处理服务。它允许用户使用重复数据消除密钥轻松地将触发同一问题的多个事件分组。

然后是[抑制](https://thenewstack.io/take-the-human-out-of-3-a-m-incident-responses/)，这是有效的前置规则，可用于抑制任何不可操作的事件。服务路由是另一个有用的工具，确保进入的事件是可操作的，并映射到每个代表特定区域或应用的服务。

噪声抑制最不为人所知的领域可能是使用机器学习和试探法将多个警报分组到一个事件中。总之，这些功能可以将系统噪音降低多达 98%。让我们仔细看看它是如何工作的。

## **检测和暂停瞬时警报**

短暂的警报令人沮丧。应急人员经常被迫改变他们正在做的事情来进行审查，结果发现警报很快通过集成自动解决。他们甚至可能在半夜醒来看一眼。然而，历史数据可以很好地预测瞬时警报。

根据这一假设，我们设计了一个针对瞬时警报的预测模型。它从定义和发现开始——决定什么是[瞬时警报](https://thenewstack.io/running-more-low-severity-incidents-is-improving-our-culture/)，然后用历史数据创建一个带标签的数据集来训练和验证模型。任何通过集成解决的警报都被认为不需要人工操作。

接下来是第二阶段:在线和离线测试预测模型。这导致了两个模型的开发——一个预测模型和一个实时滚动计数算法，它们在早期访问计划期间的 A/B 测试中运行。

基于性能和准确性，我们选择了一个赢家:预测模型。它明显优于实时滚动计数，为 66%的服务记录了更高的准确性。这种解决方案可以帮助用户自动消除波动警报中的不必要噪声。但这不是机器学习帮助压力事件响应者的唯一方式。

## **智能分组告警**

可以说，来自重复或非常相似的警报的噪音甚至比瞬时警报的问题更常见。这意味着响应者会因为本质上相同的问题被一遍又一遍地检测。但是它可以通过使用机器学习来寻找传入警报摘要中的文本相似性的功能来缓解。

然后，它会将这些警报聚集到同一个事件中。此外，可以获取用户对错误的反馈并从中学习，以改进将来的分组活动。

还可以通过分析警报到达的时间来减少重复警报噪声。机器学习用于评估最佳截止点，在该点之后，不能再向特定组添加更多警报。同样，它基于历史数据处理来检查特定服务的警报到达时间间隔。

当然，这样的设置也可以手动应用，并且在某些情况下，响应者将很好地洞察什么是最好的。但是智能算法的力量在于发现人眼通常忽略的数据模式，帮助优化警报压缩等事情。

这就是 [PagerDuty 的](https://www.pagerduty.com/?utm_content=inline-mention)智能提醒分组解决方案的工作原理。但是组织可以通过几个简单的步骤进一步加强对这些工具的使用。

因为它们部分地通过分析文本相似性来工作，所以组织在命名服务资源和实体时应该尽可能地保持一致。例如，一个警报中的一个资源名为“login database ”,而另一个警报中的一个资源名为“login db ”,这可能不会立即被识别，并且会降低长期准确性。服务资源和实体的人类可读名称也有助于提高分组的准确性。

这些建议并不是 AIOps 降低警报噪音能力的详尽列表，但它们确实有望说明事故响应团队能够取得的成功。它最终归结为更高效、更有效的响应者，更少的干扰和更好的客户体验。

通过减少消防时间，将更多时间用于创新，AIOps 可以帮助工程师和开发人员为他们的组织带来更大的战略收益。

在一个以激烈竞争为特征的数字时代，这是一个令人信服的理由来看看。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>