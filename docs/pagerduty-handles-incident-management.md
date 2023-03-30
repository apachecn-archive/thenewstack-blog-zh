# 不要惊慌:PagerDuty 如何处理事件管理

> 原文：<https://thenewstack.io/pagerduty-handles-incident-management/>

在这部关于阿波罗 13 号飞船近乎灾难性的返回大气层的电影中，由埃德·哈里斯扮演的任务控制中心的首席工程师愤怒地宣称“失败不是一个选项”虽然这样一个振奋人心的声明可能会让电影观众感到兴奋，但在美国宇航局工程师决定返回宇航员的最佳路线的实际时刻，[他们保持冷静和镇定](https://www.youtube.com/watch?v=KWfnY9cRXO4)。

对于 [PagerDuty 的](https://www.pagerduty.com/) [Rich Adams](https://twitter.com/r_adams) 来说，当事件发生时要记住的主要事情是保持冷静。“[不要慌！“T7”是道格拉斯·亚当斯在《银河系漫游指南》中给出的关于太空旅行的第一条建议，它也适用于 it 事故应对。亚当斯指出，在周四该公司召开页面责任峰会的前一天举行的一次教育会议上，抓狂对任何人都没有帮助，反而会吓到其他相关方。](https://www.youtube.com/watch?v=WB8XDk3sQBc)

PagerDuty 提供了一种服务，用于在 IT 级别自动管理事件，并且越来越多地用于其他业务功能。该服务与加快开发周期的 DevOps 实践完美结合，允许管理员团队利用自动化工作流来加快受损服务的恢复，而不会因不必要的凌晨 3 点叫醒电话而耗尽员工的精力。

亚当斯解释说,“事件响应”是指一个组织为处理出现的一些问题而做出的任何协调努力。这个想法不仅仅是为了消除问题，也是为了限制损失，减少恢复时间和成本。

“你需要一种自动化的方式来触发这一事件过程，”亚当斯解释道。

PagerDuty 自己的服务处理事故管理流程的日常任务。它对来自监控系统的信息进行排序，组织将参与补救过程的人员，通过多个通信渠道向适当的人员发出警报，允许利益相关方设置和更改事件的优先级，并提供空间和相关数据来进行事后分析。

尽管 PagerDuty 基于云的技术可能是最前沿的，但该公司[遵循一套围绕如何处理和管理危机的明确定义的程序](https://Response.pagerduty.com)，借鉴了美国政府[国家事故管理系统](https://www.fema.gov/pdf/emergency/nims/nimsfaqs.pdf) (NIMS)，这是一套于 20 世纪 70 年代首次开发的通用规则，用于涵盖各种灾难。

PagerDuty 有专门的方法来处理事故。公司里的任何人都可能引发事故。“人类擅长挑选即将发生的故障，”亚当斯指出。这一过程的关键是为每个事故指派一名“事故指挥官”(IC)。

IC 的作用不能被高估。一旦选定，集成电路将控制局面。他或她主导与事件相关的所有电话或聊天会话——即使是首席执行官也不能篡夺 IC 设定的议程。

值得注意的是，IC 实际上并不能解决问题本身。那个人只负责协调其他人的努力。IC 做出所有决定。这就是为什么公司的任何人都可以成为事故指挥官。目前，这项工作是由志愿者推动的；你不需要成为一个工程师就能成为一个集成电路，即使问题本质上是技术性的。

![](img/cef0a8c0f3247c1780d78e3986219cee.png)

其他角色也被分配。每个事件还有一个代理或备用 IC。一名记录员被指派记录所有发生的互动，无论是闲聊还是电话会议。外部联络员负责所有面向客户或面向外部的通信，向外界表明服务已关闭。内部联络员，负责公司内部的沟通(在较小的组织中，这些角色可以合并)。

最后，还有主题专家(SME)。这些是工程师和操作人员，他们知道系统实际上是如何工作的，能够诊断问题并修复它。IC 将与 SME 密切合作，确定问题的特征，然后找出解决问题的方法。

亚当斯强调，IC 不应该是解决问题的人。通常情况下，看似简单的问题可能会变得更加复杂，突然之间，IC 将扮演两个角色——修复问题和向其他人报告状态。

## “我很有钱，我是事故指挥官”

良好的沟通对集成电路至关重要。亚当斯解释说，ICs 应该清楚地表达自己的观点。清晰比简洁更好——尽量避免缩写。这个想法是问问题，估计情况，然后想出下一步，快速评估将涉及的风险。您是否会让服务离线以重新启动服务器，从而可能更快地解决问题？还是滚动重启，这可能需要更长时间，但不会中断服务？风险评估是这项任务的重要组成部分。

亚当斯指出，做出错误的决定可能比根本不做决定要好，因为做出错误的决定会带来更多的数据。“不要鲁莽，但也不要犹豫不决，”他说。每项任务都应该分配给特定的个人，而不是团队(尽管个人可以将子任务分配给团队中的其他人)。在做出每个决定之前，询问是否有人有任何“强烈的反对意见”，强调“强烈”这个词，以灌输这种想法，即这些是不寻常的情况，所以任何反对意见都应该是严重的。一旦任务达成一致，IC 应该给任务负责人一个明确的期限，比如 20 分钟或一个小时。

关键是 IC 要继续负责事件。在某种意义上，ICs 的角色是保持冷静，这向其他参与者和观察者传达了一种目的和秩序感。工作的一部分是维护国际刑事法院的权威。通常，事件响应团队会遭受 Adams 所说的“执行突袭”，或高层老板加入呼叫发出命令，试图重新评估事件的严重性，或要求额外的文档(“包含所有受影响客户的 Excel 电子表格”)，所有这些都会扰乱整个流程。在这些情况下，IC 应询问高管或任何其他破坏者，他们是否愿意接管 IC。亚当斯指出，他们总是会拒绝。

Adams 还提供了一些他们发现在这种 IC 设置中不起作用的规则:

*   **不要给每个人打电话**:每次 PagerDuty 发生事故，“我们都会给每个工程师打电话，”亚当斯说。当公司有 5 名工程师时，这很好，但当公司有 60 名工程师时，这就不好了。让不必要的员工参与进来会扰乱工作和家庭生活，还会让员工不高兴。
*   **限制集成电路的“控制范围”:**向集成电路汇报的人数不得超过八人，尽管每个人都可以有小组。
*   **限制状态更新的频率**:花太多时间发送状态更新会占用实际解决问题的资源，尤其是当没有重要的更新要传达的时候。当对话暂停时，试着更新状态。
*   **不要认为沉默意味着没有进展**:在许多情况下，当电话或聊天室里没有声音时，就有重要的工作正在进行。
*   **不要强迫每个人都留在电话上**:如果你确定一个问题，比如说，在一个应用程序中，那么就没有理由让现场可靠性工程师(SRE)留下来。当明显不再需要其他人时，解雇他们。

最后，亚当斯指出，不要忘记事后检查。可以记录和回放整个事件管理，以供以后分析。

[page duty](https://www.pagerduty.com/)是新栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>