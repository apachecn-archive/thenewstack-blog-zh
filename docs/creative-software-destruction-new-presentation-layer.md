# 创造性软件破坏和新的表示层

> 原文：<https://thenewstack.io/creative-software-destruction-new-presentation-layer/>

> “改进就是改变，所以完美就是经常改变。”——温斯顿·丘吉尔

因此，大约每十年，技术行业都会根据新的系统、功能和期望的结果来重新思考应用程序架构。目前，我们正处于另一个平台转变的早期阶段，这将在整个技术领域产生巨大的连锁反应。现有企业的重要性将会减弱，新进入者将会在新的类别中占据一席之地。数千亿市值岌岌可危。

这种创造性破坏过程往往始于基础设施部门，但最终会对整个堆栈产生广泛影响。近年来，大部分注意力都集中在通过采用容器和微服务来改造后端。移动技术已经给表示层带来了变化，但是表示层架构发生更根本变化的时机已经成熟——而且这种变化的种子已经开始萌芽。

## 我们从哪里来？

 [罗宾·瓦桑

罗宾·瓦桑是一位经验丰富的早期风险投资人，也是一位前创业者。他的专业知识涵盖了建立和扩展公司的整个生命周期，主要投资于应用程序、云计算、开源、虚拟化和安全性。在 1999 年加入梅菲尔德之前，Robin 是金融科技领域几家成功公司的创始人和工程主管:C-ATS Software、Infinity Financial Technology(IPO)和风险管理解决方案。他过去成功的投资包括 Marketo (IPO)、Trigo(被 IBM 收购)、Global Logistics(被甲骨文收购)、Akimbi(被 VMware 收购)和 webMethods (IPO)。目前，他的投资重点是大数据、复杂分析和分布式系统，包括:Alfresco、Big Panda、Centrify、Couchbase、HashiCorp 和 InfluxData。Robin 拥有哈佛商学院的工商管理硕士学位和斯坦福大学的工业工程和经济学学士双学位。](https://www.linkedin.com/in/robinvasan/) 

在 20 世纪 80 年代后期，业界围绕客户机-服务器模型进行了整合。虽然有挑战者，但最终 Windows(直到 3.1 版！)成为主导的最终用户客户端环境。这个时代的应用程序相对较小，特定于单个操作系统，通常是为数百或数千用户构建的。在设计这些应用程序时，真正的选择是将业务逻辑直接放入客户端应用程序还是下推到数据库中。Unix 系统成为主要的服务器平台主要是基于数据库性能要求。

互联网的出现和浏览器的诞生——谢谢你，马克·安德森——极大地简化了跨平台的客户端开发。然而，这些新的应用程序现在必须支持多几个数量级的用户。因此，架构中增加了几个新的层:web 服务器和应用服务器。web 服务器和相关的代理以及负载平衡器提供了一个无状态层来处理表示层。应用服务器成为业务逻辑和管理与(通常是关系型)数据库服务器交互的明显场所。

结果，开发人员面临着从 UI 代码到面向对象编程模型再到底层数据模式定义的挑战。事实上，在过去十年或更长时间里，编程框架和库的大部分发展都是为了解决这种不协调。最后，这些平台要么纵向扩展极其昂贵，要么横向扩展在运营上极具挑战性。

## 我们现在在哪里？

IT 内部的权力显然已经从基础架构团队转移到了应用程序团队。开发人员和架构师更喜欢考虑服务，他们希望基础设施是可编程的、廉价的、有弹性的和安全的。他们不再担心基础设施管理的底层问题，相反，他们希望获得顺畅、无限的功能，然后访问其他服务的 API 来帮助他们编写应用程序。相对于以基础设施为中心的方法，我们正朝着以应用程序或服务为中心的模式发展。

事情仍在发展，但这种新的“云原生”架构的一些元素似乎很清楚，包括:

*   **云**。公共或私有云基础架构提供计算、存储和网络的基础服务。AWS、Azure 和 Google 都在竞相添加越来越多的基础设施和应用服务——尽管架构师应该积极考虑找到让它们具有可移植性的抽象。
*   **容器:**容器提供了如何构建和部署软件组件的打包格式。在前几代，我们被迫在更大的结构中思考。exe 或 jar 文件),它们有时与底层硬件、操作系统或运行时相关联。
*   **微服务**:微服务是具有良好定义的 API 接口的组件。这允许系统的不同部分更加频繁地发展，并且独立地扩展。它还包括将第三方运营的服务用于通用组件，如身份/认证、支付等。
*   **应用管理**:应用服务器已经被像 Kubernetes 这样的集群管理解决方案所取代。虚拟化是通向更灵活的分布式系统的中间步骤。通过利用新的集群调度器，系统可以更容易地构建成具有水平可伸缩性和弹性。
*   **多语言数据**:根据不同的数据类型和访问方式，选择尽可能多的不同数据解决方案。显然，基于 SQL 的关系数据库和分析数据库仍然很重要，但非常常见的数据结构和访问模式现在包括:键/值缓存、文档/JSON、搜索、对象、指标/时间序列，也许还有其他一些。所有这些新的数据库解决方案都必须是本地分布式系统，并且在任何规模下都易于操作。

这些方面都涉及后端应用程序服务和数据的架构。在这一转变中，开源软件非常流行，并在每一类基础设施软件中扮演着重要角色。由于这些开源解决方案是专门为云部署和水平可伸缩性而构建的，因此企业对开源的采用大幅增加。

## 下一步是什么？

说每个公司都在成为软件公司是老生常谈，但却是事实。这种对数字化转型的关注意味着企业正在将应用和体验作为与客户的主要界面。迄今为止，大部分重点都是解决数字化转型的后端服务。但作为一个行业，我们还没有重新考虑前端表示层架构，这是新客户界面的一个重要部分。

我们现在生活在一个廉价计算和存储、云/边缘能力以及普遍快速和普遍的网络覆盖的世界。因此，似乎是时候大幅改进表示层了。例如，在这个世界上，运行传统的 web 服务器和 web 内容管理系统可能不再有意义。让一个 web 服务器与一个内容管理系统对话来获取信息、创建一个响应页面并将其发送回用户，这是非常低效的。[无服务器](/category/serverless/)在后端架构方面越来越受关注，那么为什么不在表示层应用类似的方法呢？

对于开发人员来说，表示层语言和框架领域一直在快速发展。有了脸书([的支持和固定的开源许可！](https://thenewstack.io/facebook-re-licenses-graphql/))，React 可能最终统一移动和 web 客户端开发。开发人员也积极采用 API 驱动的无头 CMS 解决方案。另一项名为 GraphQL 的脸书技术可以为后端数据和服务提供统一的抽象。

基于这些新技术，我们似乎可以迁移到一个新的无服务器表示层架构，其中预构建的 JavaScript 代码从云/边缘缓存直接与后端或第三方微服务对话。Web 和内容管理服务器不再是运行时组件，取而代之的是一个构建和部署静态或预编译体验的过程。这种新的无服务器体系结构在当前方法的基础上提供了许多显著的改进，包括:

*   性能:页面加载速度更快，因为它们由缓存提供服务，缓存在地理上是理想的分布。
*   **安全性**:攻击面大大减少了，因为你不再有运行时 web 和 CMS 组件会受到攻击。
*   **成本**:成本是完全可变的，并与使用直接相关，而不是必须为峰值容量进行调整和付费。
*   **可伸缩性**:表示层是完全弹性的，不需要干预就可以伸缩。
*   **操作**:没有需要管理的服务器。
*   **敏捷**:对用户体验的迭代过程大大加快。设计师、开发人员和团队能够利用一套熟悉且紧密交织的工作流和管道:从源代码管理到所需的云平台。

这个谜题还有很多部分需要解决，但是形状开始变得清晰了。最终结果应该是设计、构建、测试和部署新用户体验的简化流程。最终的应用程序应该更快、操作更简单、运行更便宜、更安全。

> “有些人不喜欢改变，但如果改变是一场灾难，你需要拥抱改变。”——埃隆·马斯克。

*披露:作者罗宾·瓦桑是 Couchbase、HashiCorp 和 InfluxData 的董事会成员和早期投资者。*

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>