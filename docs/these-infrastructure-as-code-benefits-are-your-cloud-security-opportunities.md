# 这些基础设施即代码的优势是您的云安全机会

> 原文：<https://thenewstack.io/these-infrastructure-as-code-benefits-are-your-cloud-security-opportunities/>

[Bridgecrew](https://bridgecrew.io/) 赞助本帖。

 [盖伊·艾森科特

作为 Bridgecrew 的联合创始人和产品副总裁，Guy Eisenkot 正在为开发人员优先的云安全铺平道路。Guy 热衷于让基础设施安全成为可消费的，并让那些能够产生最大影响的人能够访问到，他对 Bridgecrew 迄今为止的成功起到了重要作用。Guy 住在特拉维夫，之前负责 Fortscale 和 RSA Security 的产品，是一名退休的 IDF 少校。](https://www.linkedin.com/in/guy-eisen-3012a597/) 

随着基础设施即代码(IaC)的采用增加，越来越多的公司开始解决 IaC 安全性问题，我们经常发现自己在讨论 IaC 带来的挑战。

与任何其他新兴技术类似，IaC 可能会在基础设施的供应位置、所有者以及治理方式等方面引入新的模糊性。正如我们所知，这些复杂性会导致安全错误和错误配置，最终导致现实世界的风险。作为安全行业，我们的目标是帮助团队降低这些风险。但我们也希望向团队展示，IaC 不仅仅是风险的来源，也是一个巨大的机会来改变团队保持其基础架构安全的方式。

在本帖中，我们将探讨如何利用 IaC 框架的固有优势，如 [Terraform](https://bridgecrew.io/terraform) 和 [CloudFormation](https://bridgecrew.io/cloudformation) 来保护它们提供的基础设施。

## 一致性

通过将手动基础架构配置转换为机器可读的模板，IaC 使所有计算、存储和网络服务每次都能以完全相同的方式部署。这种跨资源和环境的一致性使您能够以更少的资源更快地调配资源。它还有助于维护高质量标准、安全最佳实践以及遵守行业基准。

编码的基础设施为自动化和测试提供了基础——这两者对 DevSecOps 都是至关重要的。对于当今的多云、多框架团队来说，期望每个基础架构工程师(甚至是您的安全工程师)都了解最新的云安全策略和最佳实践是不现实的。

通过编程式 IaC 扫描实施策略实施为前所未有的安全覆盖深度铺平了道路，并将人为错误的风险降至最低。将扫描引入自动化测试过程和构建管道也是 IaC 的一个好处。通过在开发生命周期的早期实现持续反馈，IaC 能够将以前被动的云安全工作转变为主动的 IaC 安全流程[。](https://bridgecrew.io/infrastructure-as-code-security)

## 节省成本和时间

除了提高一致性之外，IaC 还使跨指数级资源和环境应用配置变得更加容易，从而使工程师可以花更少的时间做重复性的手动工作。借助 IaC，当基础设施不在使用时，也可以更轻松地取消配置，从而降低总体计算成本和维护费用。

这些节省时间和成本的好处也适用于 IaC 安全。

没有 IaC，云安全通常发生在开发生命周期之外；其中云安全解决方案监控部署的资源的错误。当问题浮出水面时，它们会根据新功能和客户请求进行优先排序，然后与其他错误修复一起进行安排。如果您正在为即将到来的 SOC2 审计解决一些问题，这可能并不坏。但是对于拥有健壮的云环境和 CSPM 的团队来说，我们可能在谈论成百上千个需要解决的错误配置。

虽然我们知道反馈和可见性有多重要，但我们也知道补救对工程来说是多么昂贵和耗时。通过将云供应左移，IaC 也可以将云可见性和安全性左移。在部署之前解决错误可以节省您在生产中追踪 bug 的时间。在开发周期的早期解决问题也意味着减少环境切换和工程师的挫败感。

## 安全性和开发运维之间的协作

当云安全转移到左边时，它也变得更容易被工程和开发团队访问。有了 IaC，安全性越来越成为一个软件挑战。随着新基础架构的供应、新功能的构建和新技术的采用，为了保持强大的云安全态势，安全需要协作努力。

IaC 通过引入一种通用语言来鼓励开发者和操作者之间的合作。通过将基础设施治理转移到一个集中的地方，并将一次性配置转化为可重复的组件，IaC 有助于让每个人都保持一致。IaC 还引入了跨云提供商、合规性基准和安全最佳实践的单一事实来源。

它还支持可定制性，这对于跨领域使用基础设施的团队来说是至关重要的。每个工作流都有不同的需求和目标，每个团队都应该能够独立管理这些工作流。

在这一点上，显然 IaC 的采用是不可避免的。尽管我们仍在研究如何充分利用 IaC 来保证我们基础设施的安全，但很明显，它既带来了机遇，也带来了挑战。了解它的风险很重要，但接受它的好处才是云开发成功的关键。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论一个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>