# 事件响应向左转移，更靠近客户

> 原文：<https://thenewstack.io/incident-response-is-shifting-left-closer-to-the-customer/>

[](https://www.linkedin.com/in/john3gan/)

 [约翰·埃根

约翰·埃根是致力于客户可靠性的现代事件响应平台 Kintaba 的首席执行官和联合创始人。在加入金塔巴之前，约翰在脸书帮助领导企业产品部门。](https://www.linkedin.com/in/john3gan/) [](https://www.linkedin.com/in/john3gan/)

在科技行业，事故管理和事故响应长期以来都被孤立在现场可靠性工程(SRE)团队中。乍一看，这似乎完全合理——他们的工作是减少故障，提高技术系统的健康。

但是，让我们考虑一下事件实际上是什么——“sev 1”生产中断是任何严重到足以停止您正在做的任何事情的事件。  日常生活中严重事故的一个典型例子是火灾，这一领域的许多知识实际上来自消防部门(稍后将详细介绍)。事实是，对于这些跨公司线的事件，需要有专用的工具和流程——如果您的公司想要真正擅长事件响应，它们不能存在于像 JIRA 这样的任务管理系统中。

那么，在 SRE 团队中，我们为什么要将宣布事故的权力保留在身后呢？事实是，当发生火灾时，任何人都应该能够拉警报。在技术行业中，大多数事件都是在我们的技术系统和 SRE 工具(如监控、警报、AIOps 等)中捕获的，这是一个巨大的神话。事实是，如果您的技术系统能够检测到问题，它们也很可能能够自动修复问题。根据定义，SEV1 事件是独特的黑天鹅事件，需要人的关注和协调。

根据 Atlassian 的 [*事件管理报告*](https://www.atlassian.com/incident-management/2020-state-of-incident-management) 的状态，缺乏跨部门的协调是组织在管理事件时最大的痛点。我们必须停止将事件解决视为 SRE 独有的做法。公关可以有突发事件，法律可以有突发事件。解决这些问题通常需要跨团队的透明度和合作。值得注意的是，即使这些事件是从 SRE 宣言开始的，仍然经常需要多个其他人和团队参与进来。

那次停机是否影响了高优先级客户？营销网站宕机了吗？期望 sre 不仅要处理这些失败，还要协调需要参与的人员流程，这是对他们的过高要求。应该有适当的工具来自动化人类对紧急情况的反应，这正是我们在 Kintaba 正在建造的。

那么，为什么大多数事件响应工具都专注于 SREs 呢？

这是一个有点复杂的问题。一个最大的原因是，SRE 的许多最佳实践来自谷歌，谷歌有着强大的工程文化，是从云基础设施到分布式跟踪的一切领域的领导者。但这里有趣的警告是，如果你真的读过他们关于事故响应的章节，他们会写更多关于协调和人员流程的内容(例如，随叫随到的轮换、事故指挥官、无可指责的文化等。)而不是警报或人工智能。

> 大多数事故都发生在我们的技术系统和 SRE 工具中，这在技术行业中是一个巨大的神话。

但是，随着 SRE 角色的崛起，出现了一系列针对这一人群的事件响应工具，这并不十分令人惊讶。这些工程师每天都在思考故障，他们有仪表盘和警报来让他们了解在线系统的健康状况。从某种意义上说，事故响应是这种机制的延伸，这是很自然的。

经常被忽视的是，即使在谷歌，也有高调的努力来扩展 SRE 的实践，甚至通过他们称为 CRE 的实践与客户共享寻呼机:客户可靠性工程。有了 CRE，谷歌甚至与参与的客户共享寻呼机，允许客户而不是工程团队定义事件何时发生，其严重程度如何，最重要的是:何时结束。

事实上，如果我们暂时离开技术行业，看看最初产生我们许多事件响应实践的行业——航空和消防部门——我们会意识到，这些实践是作为跨职能运营而产生的，不仅直接涉及响应实体的所有部分，还涉及客户。这些人以最高的风险对待失败。当这些行业出现问题时，生命危在旦夕。当打电话给消防部门时，所有其他的预防措施都失效了，人工干预是绝对关键的。

## 航空公司能教给我们什么

自 20 世纪 50 年代以来，航空业已经定义并形成了事故管理的最佳实践。事实上,“现代事件管理”的含义是处理意外灾难的可预测和可重复的方法。作为一个行业，我们从航空业学到了很多东西，不管我们是否意识到自己是技术领导者。

航空业最重要的发现之一是 [*更多的事故导致更少的灾难*](https://www.infoq.com/presentations/postmortem-incidents-resilience/) *。*这可能看起来违背直觉，是不正当激励的一个很好的例子——因为希望事件数量下降当然是很自然的，但是通过试图降低数量，您可能会在事件实际解决之前就将其关闭，或者更糟糕的是没有在第一时间宣布它们。

套用 Charles Goodhart ，**的话，任何创建的指标最终都会成为目标。**因此，如果激励措施旨在减少事故，那么我们将会看到更少记录的遵循最佳实践的事故，而不是经历“隐藏”事故，在最糟糕的情况下，流程的缺乏导致组织无法吸取教训，事故在未来再次发生，只是这次会带来更可怕的后果。

当我们谈到拥有 [积极的事故文化](https://intellyx.com/2021/09/15/modern-incident-management-evolving-toward-a-positive-incident-culture/) 时，我们指的是接受航空知识，让更多的人参与到这个过程中来，降低申报的门槛。事件不再被认为是应该避免的事情，而是成为应该接受并从中学习的事件。这种思维模式的转变意味着提交更多的事故实际上是一种激励，而这些指标从来不会被用作惩罚行动的理由。这种方法创造了商业航空史上最安全的十年，超过 120 亿乘客出行，没有致命事故。

## 下一步:客户成功

最终，我认为现代事件管理需要在未来五年内成为全公司的实践。实际上，我认为在 SRE 之外最明显的下一步是客户成功团队。

自 2000 年代中期以来，客户成功一直是科技行业中一个快速增长和采用的原则，SaaS 提供商在客户获取方面投入了大量资金和精力，但 SaaS 产品的复杂性最终会导致这些客户流失。作为回应，许多公司开始通过“潜水和捕捉”团队积极瞄准风险客户，旨在通过帮助客户从他们的产品中获得更多价值来增加保留率。据麦肯锡在其名为 [*介绍客户成功 2.0:新增长引擎*](https://www.mckinsey.com/industries/technology-media-and-telecommunications/our-insights/introducing-customer-success-2-0-the-new-growth-engine) …

许多企业创建了正式的客户成功功能，以采取更主动的方法来减少客户流失。这些努力有助于将客户成功转化为软件行业中的新兴学科，包括新的工具和方法。公司还创造了额外的角色来支持这一功能，最著名的是客户成功经理(CSM)。根据麦肯锡的一项研究，收入排名前四分之一的 SaaS 供应商通过加大旨在减少客户流失的客户成功计划的投资，取得了强劲的业绩。

客户成功经理(CSM)的崛起并不令人惊讶，尤其是在科技创业领域。失去哪怕一个客户对一家初创公司来说都是毁灭性的，所以企业领导人知道，如果客户不高兴，那就是一个大问题。它指示的是严重级别 1，而不仅仅是来自监控仪表板的警报。正如我前面所说的，事实是大多数事件都是以客户为中心的，通常是由客户自己触发的，而不是我们的技术系统。

通过与各种组织的客户成功团队交谈，我们发现响应这些事件的工具仍然很差，而且各不相同。他们通常不得不通过电子邮件、电话或 slack 来解决客户投诉，然后将投诉升级到另一个团队，该团队通常拥有像 Zendesk 这样完全独立的工具，而 CSM 通常甚至没有席位。此外，宣布事件的权力仍然完全掌握在 SRE 团队手中，客户自己和相应的 CSM 都很难掌握事件解决的最新进展。

行业需要将事故响应的重心转移到离客户更近的地方。为什么不让客户自己声明事件呢？为什么不同的团队应该有不同的工具来协调和缓解同一个事件？

我们需要转移到一个事故管理被认为比 SRE 工具更广泛的地方。不幸的是，所有的努力似乎都是为了让技术系统更接近事故响应。一个很好的例子是最近宣布事件响应解决方案的一系列可观察性参与者。但是在我看来——这是错误的方法。现代事件管理需要[突破 SRE 的筒仓](https://www.kintaba.com/)才能真正有效。

*如果你对现代事件响应感兴趣，请查看来自*[*IRConf*](https://www.irconf.io/%23session-videos)*的谈话录音——这是有史以来第一次专门讨论事件响应的会议。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>