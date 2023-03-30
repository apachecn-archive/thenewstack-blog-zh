# 为什么大家都忽略了第二天 Kubernetes 的问题？

> 原文：<https://thenewstack.io/why-is-everyone-ignoring-the-day-2-kubernetes-problem/>

Haseeb Budhani 目睹了一次又一次的发生。

一个组织着手采用[云原生](https://thenewstack.io/category/cloud-native/)技术并实施 [Kubernetes](https://thenewstack.io/category/kubernetes/) 。

然后事情开始变得…有趣。

集群成倍增长。变化激增。访问需求越来越多。云成本飙升。

Kubernetes 运营平台 [Rafay](https://rafay.co?utm_content=inline-mention) 的首席执行官兼联合创始人 Budhani 告诉 New Stack:“无论你是与高科技公司、金融服务公司、医疗保健公司还是在边缘运行应用程序的零售商交谈，问题都是一样的。

“我如何管理对我的群集的访问？我将在我的所有环境中使用什么策略模型？在我的生产集群的标准蓝图中，我必须有哪些附加组件？我部署属于多个业务部门的应用程序的策略是什么？我必须尽快升级我的所有集群，因为我已经落后了三个版本，我该怎么做？”

这些问题都可以归入“第二天”的标题下第二天可能意味着站点可靠性工程师(SRE)和 IT 运营工程师永无止境的头痛。

“我们必须诚实面对这里的痛苦，”布哈尼说。"这个行业需要一个宣泄的时刻。"

## 为什么第二天这么痛苦？

Budhani 说，疼痛有许多根本原因。首先，存在技能差距问题 Kubernetes 时代已经过去八年了，仍然没有足够多的工程师对 K8s 生态系统有足够的了解。

根据 Canonical 去年 6 月发布的一项调查，缺乏内部技能是公司在采用容器和 Kubernetes 时遇到的最大挑战。

然后是云原生生态系统中的[大杂烩工具](https://landscape.cncf.io/)，您的组织使用这些工具来运营 Kubernetes，其中的每一个工具也定期需要升级和关注。

“所有这些工具都有自己的生命周期。每隔一段时间，这些工具中的每一个都需要在所有集群中更新，”Budhani 说。“因此，当新的内部团队部署更多应用程序时，您必须管理您的 Kubernetes 群集的生命周期、每个工具的生命周期、您的应用程序的生命周期、集中式策略和访问管理、每个应用程序的灾难恢复策略、按存储容量使用计费策略等等。”

“这是第二天。第 2 天是关于在底层技术都需要以完全自动化的方式为其治理、运营安全和可见性定制策略时，需要发生什么来保持正常运行。”

他看到的一个首要问题是，没有足够多的企业使用他所谓的“自动化与治理”——云原生架构承诺的开发人员速度和免于不必要的辛劳，以及组织控制对关键数据、应用程序和基础架构的访问以及控制云成本所需的制衡。

“我们没有向北极看齐，而我们都同意这样做是正确的——自动化，”Budhani 说。“根据定义，如果你一次又一次地构建它，你就没有遵循 DevOps 的第一条规则:自动化一切。”

## Kubernetes Ops 的第二天是什么样的？

在持续的基础上，管理您的 Kubernetes 操作需要跟踪许多事情。对于需要部署到多云或混合环境中的组织来说，这种复杂性以及跟踪所有移动部分的挑战变得更加复杂。事实上，对处理这种复杂性的恐惧可能会阻止组织从一开始就转向云计算解决方案，并可能导致供应商锁定，从而阻止组织实现其业务目标。

但是，无论您将应用程序部署在哪里，需要注意的关键领域都是一样的。根据 Budhani 和其他专家的说法，这里有 Kubernetes Ops 的五个支柱:

### 集群标准化和生命周期管理

“你知道你的集群今天是什么样子，当你建立它的时候，”Budhani 说。“但你怎么知道一个月后会是什么样子？”他指出，即使你不再接触集群，“一个拥有足够高权限的已安装插件可能会在你不知情的情况下改变基本配置。”

您需要跟踪您的集群的整个生命周期，包括它如何受到其他工具和与之交互的用户的影响。为在整个组织内创建和更新集群设定标准，同时确保一组经批准的附加组件始终在集群中运行，这有助于简化在出现异常时识别异常的第 2 天任务。

### 安全访问和隔离

在 Kubernetes 的帮助下，完全或部分在云上运行的分布式网络[需要一种全新的方法来实现运营商/开发者访问和安全性](https://thenewstack.io/securing-access-to-kubernetes-environments-with-zero-trust/)。无处不在的网络在任何地方都容易受到攻击。(今晚睡个好觉，亲爱的读者！)

在已经或正在向云迁移的组织中,[零信任安全方法](https://thenewstack.io/what-is-zero-trust-security/)已经占据了一席之地。零信任拒绝旧的“城堡和护城河”安全模式，而是使用精细、自动化的身份验证和授权权限来保护重要的基础架构和数据，无论它们位于何处。

但是，当涉及到访问控制时，许多(如果不是大多数)组织仍然在努力解决基本问题。在一月份由 [strongDM](https://www.strongdm.com/?utm_content=inline-mention) [发布的一项调查中，80%的参与者表示他们的组织今年将致力于访问管理](https://thenewstack.io/why-access-management-is-step-one-for-zero-trust-security/)；只有 30%的人说他们的计划中有零信任项目。(在同一项研究中，三分之一的受访者认为 Kubernetes 是他们工作中最具挑战性的技术。)

保护对 Kubernetes API 服务器的访问有助于防止未经授权的探测。当某个特定的 Kubernetes 集群出现问题时——例如恶意软件的注入——需要隔离该集群或微服务以避免问题扩散。

### 可观察性和可见性

Kubernetes 集群的管理员需要对所有环境有足够的了解，以及必要的警报和监控级别，以便在问题出现时进行分类。Rafay 的 Kubernetes 运营平台等解决方案提供了开箱即用的功能。访问长期指标和警报数据确实有助于 SRE 和 IT 运营了解其集群设备的趋势，从而帮助进行规划和预测。

### 治理和合规

当然，Kubernetes 是开源的——完全开放，就像狂野的西部一样。使用它的公司通常很难添加关键的治理和法规遵从性功能，如日志记录、漂移检测和可审计性。

集中式可执行集群配置模型有助于企业范围的集群标准化。拥有一种方法来确保部署所有强制的安全和操作附加组件有助于确保符合企业策略。此外，拥有一种方法来检测集群何时偏离企业策略，并在出现问题时进行补救，这也是一项关键要求。

Rafay 的 Kubernetes 操作平台提供了集群蓝图、附加版本控制、策略执行和违规报告等功能，以及漂移检测逻辑，可阻止对入口控制器、运行时安全工具等集群范围资源的更改。以及对集群活动的端到端审计跟踪。

### 第三方集成和维护

让所有的服务和工具无缝运行并很好地协同工作是一件棘手的事情。主要的云提供商通常有一套工具来帮助管理 Kubernetes，但是如果你走出云提供商的世界，也许是部署到多个云，在内部环境中，或者在某些情况下，在边缘，这些工具并不总是很好。

这就像一个组件的拼图游戏，需要不断地组合在一起，即使每个拼图块都有自己的生命周期需要管理。开源工具和组件会带来它们自己的问题:漏洞[，比如 2021 年末用 Log4j](https://thenewstack.io/log4shell-we-are-in-so-much-trouble/) 发现的那些。或者仅仅是每个季度更新 Kubernetes 版本的辛苦工作。

过时的工具会导致计划外停机，这会直接影响最终客户，最终影响业务。

## 构建 K8s 平台的持续成本

第 2 天 Kubernetes 的负担不仅仅是云支出。运营和维护 Kubernetes 还会让团队成员远离直接为公司创造收入的产品和应用。

一些会增加第二天头痛的事情源于缺乏标准化。它们可能包括当具有独特配置的群集出现故障时复杂的分类和支持成本，或者由控制器和群集之间的自定义访问和联网导致的安全风险。缺乏 kubectl 访问控制还会使企业面临法规遵从性和治理风险。

“经理们有时不愿意在 Kubernetes 之旅的早期提出第二天的问题，”Budhani 说，因为“他们不想扰乱开发人员的思维。”

他补充说，这种沉默是被误导的:开发人员已经知道他们的工作量因为 Kubernetes 第二天的问题而失去平衡。

“当我与真正的开发者交谈时，他们说，‘我不知道为什么我要写掌舵图而不是我的应用，’”bud Hani 说。“‘是的，我想用 Kubernetes 做实验。我有点喜欢这项新技术。当我第一次接触它时，我喜欢学习它。但是，我的上帝，我有工作要做。"

他说，c 级高管、DevOps 经理和开发人员都想要同样的东西:一种运送更多更好的代码并为企业创造更多收入的有效方式。但是，他指出，“他们说的不是同一种语言。在此过程中，这些大型企业的交付进度远远落后于计划。”

## 解决 Kubernetes 第二天的问题

Budhani 说:“为了让您的团队和组织做好准备，长期致力于监管基于 Kubernetes 构建的云架构，重要的是要准确了解您的组织正在进入的领域。

他敦促道，在你开始一个包括运营 Kubernetes 的云原生项目之前，想想你的组织想要完成什么。

Budhani 说，首席信息官和其他高级管理人员“过去常常要求他们的团队做更多的事情，进行更多的实验。”他说，现在的问题应该是，“你为什么要试验 Kubernetes 的附加产品？证明给我看，在你进行实验之前，你需要在现成的东西之外建立一些东西。”

K8s 标准化的真正成本包括定价模型、实施和维护。要问的问题包括:

*   您将如何确定哪些工具最适合您的用例？
*   你将如何跟上开源的变化？
*   工具集成方面会有持续的投资吗？
*   当互操作性问题和操作问题出现时，谁来解决它们？
*   您能否以足够快的速度雇佣足够多具备云原生技能的人员，或者培训您已经拥有的团队成员？

最重要的是，考虑与其他已经跨越鸿沟并实现了 Kubernetes 的组织交流。

“首先，了解其他人是如何做事情的——因为这让你感觉到这个问题有多难或多简单，”Budhani 说。“从失败中学习很好，但这是以时间为代价的。当你可以向同龄人学习时，为什么要走这条路？Kubernetes 社区的美妙之处在于，人们非常乐于分享他们的经验和观点。”

他总结道，“在 2022 年，你不是唯一一家致力于 Kubernetes 的公司。许多其他公司已经走过这条路，或者正在走这条路。我们有足够的资源来做好这件事。找找他们。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>