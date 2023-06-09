# 公共云 WAFs 的利与弊

> 原文：<https://thenewstack.io/pros-and-cons-of-public-cloud-wafs/>

随着网络攻击每年迅速增加，每个开发人员和开发团队都知道在他们的应用程序、服务和 API 前面放置一个 web 应用程序防火墙(WAF)是至关重要的。

 [亚历山德罗·法尔·加西亚

Alessandro 是 F5 NGINX 产品部门的高级解决方案工程师。他通过使用最新的 NGINX 技术产品，使工程师在他们的旅程中保持领先。闲暇时，亚历山德罗喜欢旅行(目前暂停)、烹饪和所有户外运动。](https://www.linkedin.com/in/alessfg/?originalSubdomain=es) 

部署和管理 WAFs 过去只是安全运营团队的工作。然后是 Kubernetes，微服务，无服务器，API。

这些新生的应用程序和架构模式将传统的整体分割成数千甚至数万个更小的应用程序，其中很大一部分需要自己的安全性和 WAF。因此，管理和部署 WAF 已经成为每个人的事情——从开发人员到开发人员再到开发人员——因为安全的责任"[转移到了左边](https://www.nginx.com/blog/shifting-security-tools-left-for-safer-apps/)以使团队能够更快地部署应用和代码迭代。

然而，并非所有的 waf 都是一样的。价格、性能、功能、易管理性和其他因素都决定了运营的复杂性和费用。然而，在最基本的层面上，在云计算时代，你对 WAF 的选择总是从一个简单的问题开始:我应该购买我的公共云供应商提供的 WAF 还是自带 WAF？有利有弊，这里我们将深入探讨公有云 WAFs。

## 公共云 WAF 优点

公共云在提供涵盖 80%常见用例的 WAF 解决方案方面做得非常出色。以下是购买云供应商的 WAF 的一些优势:

*   **易于部署** —公共云供应商确保易于部署他们的 WAFs。他们针对在云中运行的应用程序的简单配置进行优化，并设计 WAF 以适应他们提供的现有工作流和工具。部署 WAF 通常摩擦很小，可能非常适合概念验证(POCs ),在这种情况下，您不关心规模、成本或未来证明和可靠性。
*   **初始成本**——保护只有少量规则或访问控制列表(ACL)的小型应用程序的 WAF 成本通常很低——一个舍入误差，一杯咖啡。
*   **与其他服务的集成** —公共云试图使其本机 WAF 与他们提供的其他服务(如日志工具、DNS 管理和负载平衡器或流量整形工具)的集成变得非常容易。如果您正在运行 Kubernetes 或其他容器编排和自动化工具，那么简单的集成尤为重要。对于除了安全之外还有许多其他职责的小型团队来说，这也节省了时间并降低了操作的复杂性。

## 公共云晶圆缺点

不幸的是，当您依赖公共云 WAF 作为您的主要安全解决方案时，缺点可能会超过优点，特别是对于 Kubernetes 驱动的架构和现代应用程序。缺点包括:

*   **有限的扩展** —公共云 waf 往往是“一刀切”的解决方案，无法让您对扩展进行精细控制。例如，您可能需要您的微服务和 API 快速扩展以进行 flash 销售或游戏发布，但仅限于特定的地理区域。或者您可能希望水平扩展 WAF 以匹配您的负载平衡策略。这些复杂类型的配置通常很难通过为普通用例构建的公共云 WAFs 来实现。
*   **可能无法处理复杂的架构** —与扩展问题密切相关的是复杂架构带来的挑战。例如，公共云 WAFs 可能难以甚至无法满足使用案例的要求，例如具有数千个微服务的架构、不仅抵御南北流量还抵御东西流量的防火墙，以及强制执行重要的服务质量(QoS)要求或服务级别协议(SLA)。
*   **复杂的定价和不可预测的成本** —公共云 waf 通常根据多个参数进行定价，例如访问控制列表(ACL)的数量、防火墙规则的数量、防火墙组的数量、区域的数量和处理的请求的数量。这使得预测成本变得极其复杂，并可能在不可预见的事件发生时导致价格冲击，如重大扩展事件或复杂的网络攻击。
*   **不支持多云或混合云** —一个公共云中的 WAF 显然无法保护进入另一个公共云或您的私有云的流量。随着大多数组织选择多云或混合架构，这就产生了巨大的摩擦和规模不经济。您的团队必须掌握特定于每个云的 WAF 的认证方案、管理控制台和规则语法。
*   **锁定** —如果您已经在一个云中构建了复杂的规则和组，当您扩展到另一个云时，导出它们或切换到您自己的防火墙可能会非常复杂和耗时。当然，您可以手动执行迁移，但在微服务组织中，这可能意味着迁移大量防火墙规则，并可能失去大量来之不易的关于哪些规则在哪些条件下有效的机构知识。

## 结论:为工作选择合适的晶圆

概括地说，公共云 waf 对于很多用例都是有用的。具体来说，它们可能非常适合运行简单的应用程序、POC 和更简单的架构。它们在高度可预测的情况下工作得很好，在这种情况下，定价复杂性和价格冲击不太受关注。如果您的组织在一个公共云上标准化所有操作，那么公共云 WAFs 将特别有优势。

公共云 waf 通常无法满足更大的应用程序、更复杂的用例以及不断发展的应用程序架构的要求。特别是，对于 Kubernetes、微服务和无服务器环境来说，公共云 waf 的管理可能会很快变得繁重，这些环境中可能有数千个微服务，而且东西向流量与南北向流量一样令人担忧。

当开发人员或 DevOps 团队需要对扩展范例和规则(水平与垂直)进行更多控制时，公共云可能无法提供足够的粒度。公共云中的管理控制台自动化并简化了 ACL 和规则的管理，但它们通常无法跨云或在混合云环境中工作，除非您运行公共云的内部解决方案。

底线呢？考虑您的用例、您的应用程序的行为和需求，以及未来会带来什么。中途切换 WAFs 是痛苦的，会影响性能和成本。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>