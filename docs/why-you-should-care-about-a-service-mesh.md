# 为什么您应该关注服务网格

> 原文：<https://thenewstack.io/why-you-should-care-about-a-service-mesh/>

重构和更新应用程序会带来一些挑战。为现代世界更新的应用程序越多，复杂性就越大。让应用程序在容器平台上运行，并让它们相互通信和连接，是通往模块化、灵活的微服务架构的必经之路。 但是微服务的灵活性也引入了复杂性。这就是服务网格发挥作用的地方。

 [罗布·怀特利

Rob Whiteley 担任 NGINX 的首席营销官。他曾领导 Hedvig、Riverbed 和 Forrester 等公司的营销、产品和分析师团队。Rob 利用他与企业 IT 和 DevOps 客户合作的经验来提供思想领导力并推动对现代 IT 基础架构解决方案的需求。](https://www.nginx.com/) 

[服务网格](https://www.nginx.com/blog/what-is-a-service-mesh/) 提供企业所需的集中控制平面，同时仍然支持灵活、基于云的应用程序开发的自由风格。可以将服务网格看作是微服务 API 的专用第 7 层网络。它提供身份验证、授权、安全和性能服务，以优化服务之间运行的“东/西”流量。更重要的是，它为您提供了一个应用这些策略的中心点，而不必将所有这些直接编码到应用程序的业务逻辑中。

## **一个简单的服务网格类比**

服务网络就像一个城市的水管网。您的团队控制管道，根据需要连接管道，并设置所有的流量控制。无论类型或目的如何，无论服务网格支持的应用程序的需求如何变化，数据都可以通过您的系统。

这种流量管理可以在一个中心位置完成，在这里可以构建规则来管理这些互连的数据流。就像天空中的一个巨大的控制室，当农作物需要额外的资源时，你可以给加利福尼亚的土地浇水，或者如果迈阿密目前被雨水浸泡，你可以排干它。最重要的是，这些操作可以自动进行，并且可以动态执行。

### **服务网格是您通向多云的门票**

由于私有云和公共云提供商已经确定了 Docker 容器和 Kubernetes 编排的事实标准，服务网格是独立于平台的。借助这些工具，在 AWS 中构建服务网格并不排除将系统迁移到 Microsoft Azure，或者在 vSphere 私有云内形成网格。

这意味着您的服务网格端点可以在任何基于容器的架构中运行，系统甚至可以在云之间运行。因为服务网格跟踪延迟和性能指标，所以这种跨云能力扩展到跨云服务交付。

### **服务网格增强可靠性和可见性**

服务网格提供智能流量路由，可自动从网络或服务故障中恢复。这允许全栈问题跟踪，甚至跟踪服务间的中断。

如果服务器没有响应，您的服务网格将通过从单个服务或一个活动的、负载平衡的服务池中剔除它来做出响应，将其分流到另一个不断检查生存能力的池中。当该服务器在合理的时间范围内开始响应时，它会被自动推回到主动负载平衡池中。

通过提供对服务级别系统各个方面的可见性，服务网格数据可用于调试和优化您的系统。这就是微服务浑浊的水的问题，解决了。系统可以随着时间的推移进行调整，以扩展功能并满足性能和稳定性需求。

### **服务网格保障服务间的通信**

当您的团队推出应用程序的新版本，或将应用程序托管的群集移动到新的数据中心时，安全团队通常需要重新颁发证书并授权系统中的新服务器。这需要时间和精力，成为推动生产变革的障碍。

使用服务网格，围绕服务到服务通信的安全性由网格处理，将这些问题从应用程序本身抽象出来。服务网格处理关于哪些服务可以相互通信、哪些系统可以访问哪些服务以及哪些用户可以访问哪些服务的所有限制。因此，升级网格内部的应用程序不需要重新分配安全资产。

这也确保了您对网络和服务间通信的安全性关注独立于您内部开发的任何业务逻辑。如果网络组件中出现安全漏洞，服务网格可以处理围绕安全更新的更改，而不是重新设计每个应用程序。这消除了许多与安全更改和更新相关的停机时间。

### **调查大型微服务环境的服务网格**

服务网格有一个(很大的)潜在缺点。它添加了额外的容器。事实上，它让它们翻倍了。大多数服务网格实现使用 sidecar 代理，将一个代理实例与每个绑定到容器的微服务耦合起来。好处远远超过运营成本，但这意味着服务网格对于小型环境来说往往是多余的。

如果您正在管理几十甚至几百个离散的微服务，请考虑服务网格。对于这些大型环境，它们是云应用程序拼图中最后缺失的一块，是将您的整个产业联系在一起的一块——无论是在公共云内部、企业数据中心内部还是在混合云实施中。有了服务网格，您的团队可以跟踪问题，确保服务可用性，并维护路由表的正确分布。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>