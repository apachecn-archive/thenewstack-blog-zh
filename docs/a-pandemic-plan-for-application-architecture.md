# 应用程序架构的疫情计划

> 原文：<https://thenewstack.io/a-pandemic-plan-for-application-architecture/>

[Citrix](https://www.citrix.com/networking/microservices.html) 赞助了这篇文章。

 [潘卡伊·古普塔

Pankaj Gupta 是 Citrix 云原生应用交付解决方案高级总监。Pankaj 为客户提供混合多云微服务应用交付策略建议。在思科任职期间，他领导了网络、安全和软件产品组合的战略营销计划。Pankaj 热衷于与 DevOps 社区就基于微服务和 Kubernetes 的应用交付的最佳实践进行合作。](https://twitter.com/PankajOnCloud) 

在不可预见的事件中保持业务运营至关重要，而这一点的关键是一个可靠的业务连续性计划。当前的新冠肺炎疫情正在测试这样的计划，并将应用程序的可扩展性扩展到最大，迫使公司重新思考他们提供和管理保持运营所需的应用程序的方式。

冠状病毒迫使大众在家工作。如果您和许多人一样，您正在努力确保您的员工能够访问他们工作所需的应用程序和数据。更不用说提供卓越的应用程序用户体验，让他们保持专注和高效。毕竟，应用体验、生产力和业务可持续发展有着内在的联系。

为了实现这一点，您需要确保拥有正确的应用程序架构和交付策略。使您能够交付应用程序性能的策略；因为如果性能不佳，应用程序再好也没用。该战略还必须提供可扩展性，因为如果您不能自动扩展您的 it，那么您就无法扩展您的业务来满足对 IT 的需求。

## 微服务是为业务连续性而构建的

如果您正在考虑为云时代更新您的应用程序，当前的疫情可能是您需要的最后推动力。根据定义，基于微服务的应用旨在实现业务敏捷性，并为您提供坚实的基础，以确保您的业务在不可预见的事件发生时继续运营。

现在，空前多的人在家工作，给应用程序带来了极大的压力。这一点在工作效率和协作应用领域表现得最为突出。2020 年 3 月的 Webex 会议量在 2 月增长了 [250%,该应用程序每天交付超过【2020 万次会议](https://www.bloomberg.com/news/articles/2020-03-23/cisco-sees-video-demand-surge-for-webex-zoom-s-larger-rival)。同样，Zoom 每天接待 [2 亿名会议](https://www.reuters.com/article/us-health-coronavirus-zoom-idUSKBN21K1C7)参与者，比三个月前的 1000 万人有所增加。

这产生了如此大的影响，以至于 GoToMeeting 建议其客户将他们的会议开始时间从整点的[错开](https://join.gotomeeting.com/)，以缓解基础设施的压力并提供更好的体验。任何应用程序最大的压力通常出现在初始启动阶段。用户需要被认证，资源被分配，服务被加载到服务器的内存中。很自然，如果很多人同时这样做——比方说，在整点钟——那么应用程序就会陷入困境。就像排队等超市开门一样。最初几分钟很紧张，但随后就平静下来了。开门十分钟后到达通常是更好的体验。

这些例子代表了按需扩展应用的需求，而这正是基于微服务的应用所能有效做到的。微服务允许您增加或减少实例数量，以应对不断变化的需求。这种模块化还使得更新、修复或向应用添加新功能变得更加容易。类似地，您可能有导致应用程序瓶颈的服务。您可以单独扩展特定的微服务，而不是整个应用程序，这样可以更好地利用资源。Kubernetes 实现了自动化。

当不可预见的事件发生时，您需要扩展到新的环境以获得弹性或规模，容器化的微服务提供了终极的可移植性。因为微服务的运行时代码和所有依赖的二进制库都保存在容器中，所以它可以让您的应用程序迁移到云(或云之间)变得极其简单和快速。

全面的业务连续性不仅意味着规划内部开发的应用程序的可扩展性，还意味着与您的 SaaS 供应商核实他们将如何应对不可预见的事件。向您的 SaaS 应用供应商询问的关键问题:

1)他们的服务是否旨在随着负载的增加而扩展？

2)它们是基于微服务的吗？

保持应用交付基础设施的运营一致性也至关重要，这样当您需要扩展或溢出时，就可以快速转移工作负载。保持跨平台的一致性非常重要。它缩短了学习曲线，让您确信您的安全状况和应用程序交付不会受到影响。

当您扩展工作负载时，您必须扩展相关的应用交付控制器(ADC)以满足增加的流量负载。选择具有突发许可的 ADC 将确保您可以放心地应对瞬态尖峰。当您需要做出更大的改变时，您需要确保您的 ADC 具有灵活的许可。一种有效的方法是建立一个容量池，允许您将 ADC 容量快速移动到您需要的地方——内部部署到云，或者在云之间移动。

ADC 应该是应用交付策略的支柱。您的企业依靠他们为您的用户提供最佳体验。你不能让他们失望。开源产品有利于开发，但是当涉及到生产环境时，您需要让事情一直保持运行。此时，最好知道您有 SLA 管理的支持合同的支持，而不是依靠论坛和社区的最大努力在不可预见的事件中让您的业务正常运行。

当你不得不走出“正常”时，很容易迷失。你需要知道事情有多糟糕，什么坏了，怎么修。很快。这就是为什么你有现场可靠性工程师(SREs)；它们帮助你量化表现，并能指出你需要多少反应来纠正它。

在下一篇文章中，我们将看看 SREs 在业务连续性环境中的作用。

来自 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>