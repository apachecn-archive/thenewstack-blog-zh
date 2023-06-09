# ai ops:devo PS 为人工智能的注入做好准备了吗？

> 原文：<https://thenewstack.io/aiops-is-devops-ready-for-an-infusion-of-artificial-intelligence/>

本文是关于将持续集成和部署(CI/CD)实践引入机器学习的系列文章之一。为将来的分期付款检查回新堆栈。

随着流程编排和监控在 DevOps 中扮演如此重要的角色，使用人工智能(AI)来支持甚至自动化运营角色的新兴趋势，通过提供关于基础设施中正在发生的事情的实时见解，似乎是一个显而易见的选择。

DevOps 是关于提高敏捷性和灵活性的； [AIOps](/machine-learning-for-operations/) 应该能够帮助实现从开发到生产的自动化，预测部署对生产的影响，并自动响应生产环境执行方式的变化。当微服务、混合云、边缘计算和物联网等趋势增加了应用基础架构的复杂性时，这一点尤其如此，这增加了您可能需要查看的日志数量，以找到问题的根本原因，以及需要参加电话会议或聊天室的人数，以跟踪出了什么问题以及如何解决问题。

AIOps 依赖于聚合来自多个系统的数据，DevOps 依赖于集成以前孤立的系统。AIOps 需要与 DevOps 相同的文化变革，因为这意味着着眼于整个系统，而不是特定的技术或基础设施层，并适应高度自动化。

AIOps 的承诺是，它可以检测异常情况，预测性能问题和与基线的偏差，提出优化建议，跨多个平台关联信号以进行故障排除，进行根本原因分析，如果您愿意，甚至可以自动修复。

“机器学习和人工智能技术将有助于为团队提供指导，让他们将精力集中在优化工作流程上，并提供对性能和需求波动的见解，”[Splunk](https://www.linkedin.com/in/joshatwell/)的高级技术倡导者 Josh Atwell 告诉新堆栈。“结合早期的问题检测，人工智能和机器学习(ML)将允许团队优化资源，提高部署速度，并提高站点可靠性。”

## 保持传统

但是，尽管有大量针对传统运营团队的 AIOps 工具，并且对它们有很大兴趣，但很难找到专门为开发运维设计的选项。当涉及到构建、测试和推送代码时，很大一部分 DevOps 管道可能是自动化的，但决策仍然主要取决于人类查看错误代码、日志或可视化工具，如[新遗迹](https://newrelic.com/)的 [Kubernetes 集群浏览器](https://blog.newrelic.com/product-news/kubernetes-cluster-explorer/)。

一些 DevOps 工具开始添加机器学习支持的分析。如果你正在使用 Azure Application Insights 服务监控 web 应用程序，当其机器学习检测到异常数量的失败请求或响应或页面加载时间的性能异常时，[智能检测功能](https://docs.microsoft.com/en-us/azure/azure-monitor/app/proactive-diagnostics)可以向你发送电子邮件。

许多为传统操作设计的 AIOps 工具也可以覆盖一些关键的 DevOps 系统；[科学逻辑 S1](https://sciencelogic.com/sl1/platform) 监控内部和云系统，而 [BMC TrueSight](http://www.bmc.com/it-solutions/truesight.html) 和 [OpsRamp](https://www.opsramp.com/) 可以监控跨多个云的基础设施。对于 OpsRamp，这是 Kubernetes 的服务，如 AKS、EKS 和 GKS，下一个版本将支持更多的[云本地计算基础](https://www.cncf.io/)项目，用于容器管理和其他 Kubernetes 服务。

> AIOps 需要与 DevOps 相同的文化变革，因为这意味着着眼于整个系统，而不是特定的技术或基础设施层，并适应高度自动化。

[Nastel 的 AutoPilot](https://www.nastel.com/application-performance-monitoring/) 应用性能监控使用 ML 来关联来自混合云、内部和移动系统的多个系统的事件和数据，监控用户体验以及交易和性能，并且它可以连接到 GitHub repos。思科正在开发一个 [AppDynamics 无服务器代理](https://blog.appdynamics.com/product/serverless-agent-aws-lambda/)，用于从运行在 AWS Lambda 中的 Java 微服务收集指标和事件，但它仍处于私人测试阶段。

“在 DevOps 世界中，很少有工具能够利用任何可识别为 AIOps 的功能，” [Moogsoft](https://www.moogsoft.com/) 首席技术官 [Will Cappelli](https://www.linkedin.com/in/will-cappelli-7293132/) 告诉新堆栈。“DevOps 团队正在获得遥测技术，最多应用一些可视化软件；他们的分析很大程度上是用自己的眼球做出的。”

部分原因是传统的运营界更容易成为目标。“IT 运营界有了更大的紧迫感；他们更清楚这些问题，因为他们一直在处理大型复杂混乱的基础架构，他们直接看到底层基础架构的复杂性，这已经变得无法忍受。DevOps 团队往往非常关注堆栈的上层，他们往往只关注那些与他们交付的应用程序直接相关的基础架构元素。”

Cappelli 认为，基础设施影响应用程序性能的方式，或者应用程序影响基础设施另一部分性能的方式，不会持续太久。“随着开发运维变得越来越普遍，忽略他们所提供功能的整体环境的能力将会下降，而部署 AIOps 的紧迫性将会增加。”

## DevOps 还不够痛苦

Atwell 说，在 DevOps 中，AIOps 肯定有潜力，首先是它为传统 Ops 提供的相同的警报和通知整合。“人工智能在 DevOps 中的最大趋势是围绕减少软件开发过程中的数字废气中的噪声。这使得开发、平台和 SRE 团队能够将精力集中在问题预防和环境优化上，而不是手动尝试理解所有传入的数据。”AIOps 承诺的实时洞察力也非常适合频繁部署。

下一步将是更积极主动的建议。“他们将能够就代码或环境中应该进行的更改提供智能指导。这将基于对来自环境和测试工具的数据的评估。该系统将审查历史数据，以制定基准，并根据这些基准定期评估系统。”

OpsRamp 产品开发和云运营副总裁 [Bhanu Singh](https://www.linkedin.com/in/bhanu-singh-ab888810/) 告诉我们，对于测试来说，机器学习可以通过检查代码库中使用的组件中的漏洞并将其替换为修复问题的更新版本，来消除在代码签入时运行静态代码分析的误报。

它还可以减少每次代码推送所需的代码测试量。“如果你有一个包含成千上万个测试用例的复杂系统，你的整个测试套件可能需要两个小时才能运行，但机器学习可以决定运行哪个测试，不运行哪个测试，这样你就可以更快地将你的改变投入生产。根据即将到来的变化，它确切地知道哪些模块和微服务受到了影响，它挑选了客户常用的五个用例，运行相关测试，如果没有发现任何问题，它可以将构建推向下一阶段。”

AIOps 还可以监控代码推送的结果。“也许测试用例通过了，但在生产中，它会导致两个微服务之间出现延迟问题，或者日志中出现超时或警告消息。系统可以从这些异常中学习，下一次它将拒绝构建。”

卡佩里认为，AIOps 还可以提高运行手册的自动化。“在 DevOps 流程中有大量最终确定性的自动化，因为它复杂而严格，所以容易出错。环境在不断变化，操作手册会过时。”让 AIOps 工具分析传入的遥测数据并修改操作手册以使其具有上下文感知能力可以消除部署瓶颈和错误来源。

## 可供学习的正确数据

其中一些类似于现有的 AIOps 特性，只需要已经可用的数据。但是进一步识别关键异常和理解因果关系将需要更多关于开发人员行为和遥测技术的知识，这些知识通常不会从生产环境中收集，Cappelli 说。

Atwell 指出，今天完成的应用程序日志主要是告诉开发者正在发生什么。“今后，必须生成日志，以便更好地为运营和支持提供信息。在 AIOps 早期，最有价值的数据是系统性能指标和日志记录。这些信息提供了基准，并提高了预测潜在停机的能力，同时也增加了信心。记录值将与记录质量相关联。根据这些数据，Atwell 预测 AIOps 将通过“价值流优化、自动化、工作负载管理以及更快的安全性和缺陷识别”来支持 DevOps

该列表涵盖了 DevOps 的全部内容，因为正如 Cappelli 所说，AIOps 正在做的是“超越自动化，实现自动化洞察”。随着 DevOps 变得越来越主流，对提供这种功能的工具的需求也会越来越大。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>