# DevSecOps 迎来了它的“OK Boomer”时刻

> 原文：<https://thenewstack.io/devsecops-is-having-its-ok-boomer-moment/>

[](https://www.linkedin.com/in/talmklein/)

 [Tal Klein

Tal 是 Rezilion 的 CMO，业界领先的自主云工作负载保护平台。他在 IT 和信息安全行业拥有 20 多年的经验，与云安全、客户端虚拟化、网络和数据通信领域的领导者和令人兴奋的新兴供应商合作。](https://www.linkedin.com/in/talmklein/) [](https://www.linkedin.com/in/talmklein/)

DevOps 资深人员已经知道，传统的软件合规性和安全性方法弊大于利，通常涉及耗时且需要手动流程和工作流的预防性控制。像访问政策、程序、标准和网络防火墙这样的东西已经过时；它们是为瀑布开发方法设计的，并且依赖于长时间周期，这与 DevOps 不兼容。

这些天的争论是关于如何将 DevOps 的牛与宠物原则应用于法规遵从性和安全性，这些原则支持不可变的基础设施。我一直大力支持 Gartner 的建议，即使用其[持续自适应风险和信任评估](https://www.gartner.com/en/webinars/3891406/the-7-imperatives-of-continuous-adaptive-risk-and-trust-assessme) (CARTA)方法来支持开发运维，因为在云工作负载中，风险是流动的，而不是静态的。它需要被发现、持续评估和缓解。

## **你想要的状态是什么？**

这是安全室中的大象:弹性被嵌入到每个不可变的应用程序或服务中。也就是说，在组件或代码更新的情况下，如果您的最佳实践是用应用程序的更新版本创建一个新的容器，并删除旧的容器，那么在每次更新之后，您将拥有一个新的实例。如果存在漏洞或试图注入漏洞，它们将在更新期间被清除。

对于大多数人来说，实现一个不允许在生产系统上进行配置更改、修补或软件更新的运营模式还不太现实。总有一天，所有补丁和更新都将应用到“黄金”映像和层，然后生产工作负载将普遍从这些映像中全新构建并被替换，而不是被服务。在这样一个基础设施不可改变的世界中，云工作负载保护策略将转向关注应用程序控制和运行时所需的状态实施。

今天，我们已经看到补丁和漏洞管理的世界陷入混乱，因为代码更改的速度和对第三方或开源组件的依赖超过了大多数安全和合规团队所能跟上的速度。

所需状态强制实施解决方案分析 CI/CD 管道，并将代码转换为白名单，建立一个自动策略来强制实施开发人员意图或所需状态。期望的状态执行的关键是依靠代码的声明性来驱动策略，而不是试图建立启发式分析或试图使用机器学习从坏中学习好的东西——因为这些方法学跟不上现代 DevOps 环境中变化的速度和规模的步伐。基线已经成为过去。

现代开发语言、现代框架和现代体系结构的声明性本质上为每个服务创建了一个白名单。食谱或烹饪书基本上是一种策略——它是一种架构策略，告诉代码它能做什么和不能做什么。为什么我们不能对保护适用同样的原则？烹饪书和食谱是理想状态的完美写照——为什么不使用它们来填充和构建白名单，或者如果您更喜欢在运行时使用现有的不变性机制来强制执行的策略呢？

## **云工作负载保护已经在您的代码中**

云工作负载保护有两个基本优势:

### 1.理想的国家治理

了解什么应该和不应该在生产环境中运行有助于创建更好的建筑卫生模型。集装箱装运了大量不必要的过剩货物，这些货物经常被投入生产。这种“继承的”代码经常遭受膨胀(比需要或有用的代码更多)。旧代码往往会保留下来，因为很难判断是否有任何东西或任何人需要它。把它放在里面更安全，对吧？除了识别谁写的和何时写的问题之外，臃肿的服务有直接的安全影响，因为更多的代码=更大的攻击面。

旧代码通常都有漏洞，部分原因是由于安全环境的不断变化以及针对旧代码的新攻击经常出现。此外，旧代码的安全上下文可能会随着应用程序的发展或代码的移动而改变。因为声明性体系结构可以分解成关系、依赖和动作，所以期望的状态执行可以可靠地识别生产中实际需要哪些工件，以及哪些组件仅仅是操作膨胀。

### 2.期望的国家执行

在今天的开发环境中，我们可以利用现代开发语言、现代框架、现代架构以及基于微服务、API 和容器的云原生架构的声明性。那里有很多声明性的信息。我们可以利用所有这些声明性意图来构建我们正在讨论的白名单——它可以是我们的策略。

在我最近与 Gartner 著名副总裁兼分析师 Neil MacDonald 举办的[网络研讨会](https://www.rezilion.com/a-carta-based-zero-trust-approach-to-workload-security/)中，我们讨论了如何使用期望的国家强制措施将安全性无缝、透明地引入开发运维工作流。想法是:让开发者做他们的事情。安全团队的责任是将保护集成到开发人员的世界中，而不是使其复杂化。正如 Neil 所说，“我们不会要求开发人员去某个安全控制台，或者去编写所有应该在该服务器上的应用程序的清单。他们想写代码，他们想快速完成，他们想把代码送到你的客户手中。我们不能让他们慢下来，这需要成为一个指导原则。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>