# 跟随数据:关于 SaaS 应用安全的 8 个问题

> 原文：<https://thenewstack.io/follow-the-data-8-questions-about-saas-application-security/>

上个月在 GigaOM Structure 大会上，云研究主管阿沙尔·贝格(Ashar Baig)领导了一个关于云时代应用安全的小组。讨论的要点是，随着云的出现，诞生并存在于云中的 SaaS 应用颠覆了传统的安全模式，企业需要重新评估其整体安全环境，以纳入云应用和服务。

Adallom 首席执行官 Assaf Rappaport 参加了该小组，他的回答与我经常收到的许多云安全问题相关。虽然阿沙尔没有抽出时间来问所有他最初为小组准备的问题，但我请阿萨夫浏览了所有问题，并以书面形式作出回应，因为它们与我一直收到的关于 SaaS 安全领域的问题产生了共鸣。希望你觉得有用。

Ashar Baig (AB) :首席信息官们为什么要关心那些不在公司防火墙后的公司服务器上的应用程序呢？

**阿萨夫·拉帕波特(AR)** :云革命结束了。我们现在正处于云时代，因此我们应该接受企业数据正在被云所吸引这一事实。关闭云不是一个选项，因此首席信息官需要保护云中的数据，因为他们对数据的完整性负责，并在数据泄露时承担责任。

**AB** :为什么传统安全措施不足以保护企业知识产权？

**AR** :云的安全性必须在云端。当用户访问云服务时，他们是在企业边界之外的不受管理的设备上这样做的，因此，在数据中心的防火墙和 IPS 的范围之外，并且无法通过端点保护来预防，这很简单:你不能保护你看不见的东西。

AB:SaaS 有数百个应用程序，同时保护所有这些应用程序对 IT 部门来说是一项艰巨的任务。一个人从哪里开始？什么是低垂的果实？

**AR** :跟随数据。我们经常与首席信息官们谈论 cloudpocalypse:一项审计显示，他们的员工使用了 200 个影子 it 应用程序！但是当我们深入研究时，我们总是发现云中的大多数关键企业数据通常包含在五个或更少的云服务中。这些都是唾手可得的果实-例如，如果您云中 90%的企业数据都在 Salesforce 和 Box 中，那么首先将您的资源集中在这两个应用上，然后处理占您攻击面不到 10%的其他 198 个应用。

**AB** :你能告诉观众保护 SaaS 的各种方法以及这种方法的利弊吗？

**AR** :让我们从陈述显而易见的事实开始:日志和端点代理是无用的，因为第一个被限制在边界上，第二个需要一个受管理的端点。这就剩下代理了——正向代理很麻烦，因为它们需要合作用户——而且正向和反向代理都可以被解释为单点故障。最终，我得出的结论是，任何可以归类为“企业级”的 SaaS 供应商都将提供 API，允许安全生态系统合作伙伴将 IT 权限和安全控制扩展到服务中。

**AB** :机器学习在威胁检测和缓解中扮演什么角色？

**AR** :有些人可能会说，安全的唯一出路是将从金融欺诈防范中吸取的经验教训应用到数据泄露保护中，但我认为这还不够好，因为与金钱不同，在数据泄露之前很难知道数据的真正价值是什么——数据泄露的风险偏好远低于金融欺诈。在 Adallom 之前，我们的研发团队建立了机器学习算法，使用异常活动检测来防止恐怖主义，正如你所想象的，风险偏好为零。

**AB:** 最近在保护 SaaS 应用程序安全方面，您发现了哪些出乎意料的趋势？

**AR** :我一直对大量首席信息官相信云可以被“关闭”或“阻止”感到惊讶——当我开始 Adallom 时，我以为企业领导者会接受云应用程序现在是他们现实的一部分——正如我在开始时所说的，任何不盲目的人都很明显云革命已经结束了。但一次又一次，我们不断遇到它和安全高管，他们宁愿投入更多的金钱和资源来阻止 SaaS，而不是让它。

**AB** :您认为需要什么样的技术创新才能跟上云环境中威胁检测和缓解的发展？

**AR** :我其实觉得更大的问题是教育，而不是创新。我们在云安全方面取得了令人难以置信的进步，但 IT 预算并没有反映出需求。随着数据迁移到云，企业攻击也浮出水面——首席信息官必须将云安全项目纳入他们的预算——技术就在那里，而且非常好——你只需要购买它。

**AB**:SaaS 保护路线图是什么样的？这项技术将如何发展？

**AR** :我们将看到的主要发展是运营控制的商品化，如加密和 DLP，因为 SaaS 供应商将它们作为平台功能来实现。创新必须与内部威胁的自主预防相结合。我还认为安全生态系统在许多方面将成为平台驱动的，一种安全平台即服务，但这还远远不够。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>