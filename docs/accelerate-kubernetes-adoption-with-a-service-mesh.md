# 通过服务网络加快 Kubernetes 的采用

> 原文：<https://thenewstack.io/accelerate-kubernetes-adoption-with-a-service-mesh/>

[](https://www.linkedin.com/in/ericmurphy2/)

 [埃里克·墨菲

埃里克是 Solo.io 的现场工程师，他喜欢思考软件设计以及技术如何解决业务问题的大图景。在过去，Eric 主持过关于 Kubernetes、Java 和领域驱动设计等主题的研讨会。此外，Eric 是 O'Reilly 的出版作者，并在全球技术会议上发表过论文。](https://www.linkedin.com/in/ericmurphy2/) [](https://www.linkedin.com/in/ericmurphy2/)

多年来，我一直在指导大型组织采用 Kubernetes 和微服务，在此期间，我看到了许多常见的模式。通常，组织希望保守地迁移，但是这会将采用 Kubernetes 的时间从几个月延长到几年。最终，Kubernetes 的全部价值可能仍然没有实现，这些容器也可能是虚拟机(VM)。

为了充分利用 Kubernetes，您必须首先了解 Kubernetes 需要附加软件才能成为完整的解决方案。必须安装和配置额外的组件，例如像 Istio 这样的服务网格。服务网格允许您保护、观察和管理跨 Kubernetes 集群部署的服务之间的流量。另一个缺失的部分是一个 API 网关，以安全、可靠和灵活的方式将流量动态地路由到 Kubernetes。不建议简单地将 Kubernetes 服务暴露给外部负载平衡器。

让我们来看看组织面临的三个常见挑战，并了解相邻技术如何增强 Kubernetes 并帮助加速您的应用程序迁移和现代化。

## 采用 Kubernetes 的三个常见挑战

### 1.不切实际的应用程序现代化和迁移目标

如果您的组织拥有在数据中心运行多年的大型单一应用程序，在几周内将它们转移到 Kubernetes 通常是不现实的。这些单一的应用程序就像老橡树，深深植根于现有的 IT 基础设施和将应用程序连接在一起的中间件。更新、替换或移动这些应用程序可能会很困难，尤其是当存在大量相互交织的“橡树”应用程序时。

简单地将这些遗留的单片应用拆分成微服务并部署到 Kubernetes 是一种经常以失败告终的策略。拿走那棵老橡树，砍掉它的枝干是行不通的，因为那些枝干不能自己生根发芽。最糟糕的情况是，您创建了一个继承了旧问题的分布式整体，并将其与微服务架构的挑战相结合。由此产生的应用程序将是复杂的、不可靠的、缓慢的，并且很可能成为一项糟糕的投资。

应用程序应该针对现代用例进行完全重新设计。通过使用 Kubernetes 重新思考您的应用程序现代化方法，您的组织将更快地获得预期收益，同时降低风险。

一些公司帮助您简化应用程序现代化的方法。例如，使用 Solo.io 的 Gloo Mesh 和 Gloo Edge——基于 Istio 和 Envoy Proxy——您可以在 Kubernetes、虚拟机和服务器上的应用程序之间路由流量。一个技巧是在更新应用程序本身之前更新您的 API，例如将 JSON 转换成 XML 以加速 REST 客户端的采用。专注于易于移动且风险较低的应用程序，慢慢处理更复杂的应用程序。您还可以采用 canary 部署来验证应用程序在投入生产之前的行为是否符合预期。

### 2.无法在全球分发应用程序

连接到另一台服务器上的数据库的 web 服务最简单的形式是分布式应用程序。更常见的情况是，分布式应用程序是从多个数据中心和云中相互调用的微服务的级联。由于许多大型组织拥有全球客户，因此需要通过为每个地区正确划分服务和数据来构建全球分布式应用程序，以获得更好的性能。

对于生产系统来说，让一个微服务直接调用另一个微服务本来就不可靠，尤其是在数据中心和云之间。有些微服务会偶尔中断，也会有网络问题。整个数据中心可能会完全离线—发生故障的可能性是无穷无尽的。您必须考虑如何设计这些系统，并主动设计不同类型的故障，因为它们不可避免地会发生！

在可靠性挑战得到解决之前，高度分布式系统还不能投入生产。在 Kubernetes 上新的全球分布式部署被证明对于生产工作负载是可靠的之前，您可能仍然需要您的遗留系统。

为了再次说明，Gloo Mesh 和 Gloo Edge 带来了更简单的设计和更快部署联盟的信心，即在任何地方跨集群配置一致的路由和服务的能力。还有一个服务复制，以更有效地实现负载平衡和故障转移。您还可以将服务网格组合成一个“网格中的网格”,同时在出现局部中断时仍然能够独立操作每个网格。Gloo Mesh 还可以带来可靠的服务到服务通信，需要处理重试、指数级回退和故障转移的功能，而不必自己编写代码来完成这些工作。

### 3.缺乏安全方面的自动化

DevSecOps 承诺了很多，但是安全的完全自动化可能很难实现，尤其是在要求严格且更改策略的能力有限的环境中。

Kubernetes 通过要求您对安全性和采用 DevSecOps 的整体方法进行现代化来提供帮助，除非您希望维护两套围绕安全性的自动化流程，一套用于 Kubernetes，另一套用于遗留 IT 基础架构。在大多数情况下，拥有两个并行但不同的方法会有内在的风险，并且管理起来更加复杂。

实现微服务安全态势的现代化可能需要数月时间。这不是一件容易编写脚本的事情，可能需要重新思考您的组织如何管理身份验证和授权等功能。在没有首先解决现代化的安全工具和实践之前，应用程序不应该在 Kubernetes 上投入生产。

Istio 的服务网格内置了 DevSecOps。通过采用 Istio，您可以自动化诸如证书管理和保护服务到服务通信等任务。借助 Istio，您甚至可以将您的服务网格扩展到虚拟机，并采用同质的安全解决方案。Solo 的 Gloo Mesh 和 Gloo Edge 具有通过 Kubernetes 自定义资源(CRDs)进行部署的能力，这些资源也用于配置安全性和分发机密。您可以使用 GitOps 工具来实现您的 DevSecOps 方法，通过自动部署更新的 CRD 来修改您的安全状态。

## 结论

我喜欢帮助人们克服他们在采用 Kubernetes 时所面临的挑战。如果您想了解更多关于我们如何帮助您满足特定需求和使用案例的信息，请联系 [eric.murphy@solo.io](mailto:eric.murphy@solo.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>