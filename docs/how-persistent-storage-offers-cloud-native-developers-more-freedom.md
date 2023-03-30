# 持久存储如何为云原生开发者提供更多自由

> 原文：<https://thenewstack.io/how-persistent-storage-offers-cloud-native-developers-more-freedom/>

[红帽](https://www.openshift.com/)赞助本帖。

 [迈克尔·圣让

Michael 是 Red Hat 的首席营销经理，主要负责混合云的数据解决方案。他在全球联盟、企业和技术营销、产品管理和技术培训方面拥有丰富的经验，带来了企业存储方面的专业知识。凭借丰富的行业经验，Michael 为当今许多新兴的数据驱动型工作负载提供了现实世界的解决方案。](https://www.linkedin.com/in/mdstjean/) 

许多组织越来越倾向于让 DevOps 团队支持业务目标和策略。在从事务性和操作性更强的方法向战略性更强的软件开发焦点的转变中，开发团队在区分服务产品甚至干扰并最终转变他们的行业方面发挥着关键作用。

因此，应用程序架构师不太关心封装在整体应用程序中的大规模工作流。相反，今天的问题通常围绕着 DevOps 团队必须做些什么，才能通过大规模使用云原生平台以不久前闻所未闻的速度部署软件来实现所需的敏捷性水平。

由于敏捷实践和云原生基础设施的全新世界，开发人员团队可以每天多次部署代码，而不是几个月一次，在许多情况下，甚至更长时间。

## 云原生应用开发的优势

与使用传统的整体应用程序开发实践开发的应用程序不同，云原生应用程序由于其多功能性，可以更小、更灵活，并且易于与其他应用程序和服务集成。许多开发人员也可以开发更大生态系统中的应用程序或服务。

目标是让部署持续快速和健壮。最终的考验是，这些敏捷部署是否能满足最终用户的大规模需求，是否优于竞争产品。在无状态容器环境中快速一致地进行部署时，可能会出现无法预料的问题；因此，组织必须优先考虑在云环境中高效管理和扩展数据和网络。

## 管理容器中的持久存储

我经常发现组织在进行云原生迁移时面临的一个突出的绊脚石是如何在短暂的容器环境中管理有状态应用程序的数据。

在为云原生架构开发和部署软件时，开发人员必须了解他们创建和分发的代码将如何在组织的运营中进行交互。容器和微服务为开发人员提供了难以置信的部署多样性。由于其底层架构的无状态性，他们可以即时扩展和缩减代码部署。然而，当涉及到数据放置时，维护数据持久性、稳定性和安全性可能会带来挑战，特别是当应用程序架构师使用可能存在于多个位置的代码和微服务时。

在最初使用容器的新兴 DevOps 环境中，一个简单的策略可能是为他们的 [CI/CD 管道](https://blog.openshift.com/deploy-jenkins-pipelines-in-openshift-4-with-openshift-container-storage-4/)、Git 存储库或应用程序附加一个网络文件系统(NFS)。然而，正如我们将在下面看到的，数据可移植性、弹性和动态供应/取消供应可能会使这一路线变得繁琐和不合标准。使用不可共享且存在潜在故障点和数据安全性的专有云存储基础架构也会产生类似的问题。

简而言之，在您的云原生之旅开始之前，拥有一个持久存储层可以让组织省去头痛的问题，并减少原路返回。我们将在下一节中详细解释这是如何实现的。

## 持久存储应该如何工作

在无状态且通常多样化的环境中，解决应用程序开发和部署的持久存储难题的一种方法是采用与容器平台集成的存储层。

当开发人员使用 Kubernetes orchestrator 时，他们可以更容易地为项目创建资源，持久存储层应该理想地包含一个动态存储平台。开发人员应该相信，存储层也符合他们对应用程序部署的数据安全性和弹性要求。

借助可行的软件定义的存储平台，开发团队可以动态定义和调整项目的数据要求，而不是使用 NFS 装载等方式手动完成这一过程。他们不需要依靠存储管理员来代表他们调配存储资源；他们可以根据需要更改存储配置。

同样，对于以块协议存储数据的应用程序，如 SQL 或 NoSQL 数据库，一些组织可能会倾向于采用服务提供商的专有解决方案。然而，该选项限制了跨不同多云或区域区域提供存储可用性的能力，并且会将开发人员局限于单一提供商的解决方案。

开源软件定义的存储允许跨许多不同类型的基础架构(包括裸机、虚拟机(VM)以及公共云和私有云环境)进行持久和可移植的存储。数据联合可以跨混合和多云环境进行，因此开发人员可以将敏感数据放在需要的位置，并集成来自各种多云部署的应用和微服务。

对于人工智能(AI)和机器学习(ML)工作负载等大规模分析应用程序，数据科学家必须经常管理来自多个位置和设备的大量数据。另一个例子是来自边缘设备和物联网来源。从设备边缘到远程转移到核心系统的数据聚合和传播必须在整个数据生命周期中无缝交付。通常，对于不同类型的事件，需要不同的存储协议，从对象到数据块到文件。持久存储层功能必须能够处理这些非常动态和多样的存储需求。

最终，开发团队必须能够依靠一个标准化的平台，通过一个 API 在通常多样化且要求苛刻的环境(包括多云、裸机和虚拟机)中实现存储管理自动化。当开发人员需要根据需要缩减或重新部署时，存储层还应该提供明显的故障转移优势。它还需要非常敏捷，这样开发人员就可以通过近乎零延迟的配置来定义他们的需求。

云原生持久存储提供了许多这些功能，并为开发运维团队提供了显著的灵活性和可移植性。它可以为云原生环境中的软件部署带来灵活性，同时让开发人员能够自由管理自己的存储需求。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>