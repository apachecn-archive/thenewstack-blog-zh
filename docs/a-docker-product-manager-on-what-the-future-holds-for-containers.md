# Docker 产品经理谈集装箱的未来

> 原文：<https://thenewstack.io/a-docker-product-manager-on-what-the-future-holds-for-containers/>

[旗语](https://semaphoreci.com/)赞助本帖，由[旗语 CI/CD](https://semaphoreci.com/) 平台为您带来。

 [沃伊泰克·奇乔

沃伊泰克正在 Semaphore 把营销和客户关系联系起来。在职业上，他喜欢与现代技术的创造者和动摇者密切合作。在业余时间，他写并表演口语诗。](https://semaphoreci.com/) 

[Gareth Rushgrove](https://twitter.com/garethr) 是一名经验丰富的软件和运营工程师，在 Docker 担任产品经理。此外，他还是 DevOps 社区中最受欢迎的时事通讯之一[“devo PS 周刊”的编辑](https://www.devopsweekly.com/)

在这次采访中，我与 Rushgrove 讨论了他目前在 Docker 的工作，什么是[云原生应用捆绑包(CNAB)](https://blog.docker.com/2018/12/announcing-cloud-native-application-bundle-cnab/) ，CI/CD 管道的重要性以及 2019 年 DevOps 趋势预测(主要关注成本)。

**你的职位是 Docker 的产品经理。这让您(和您的团队)直接支持一个产品的成功，该产品现在是云软件行业的标准。你能让我们知道你的日常工作是什么样的吗？就 Docker 的发展方向而言，你关注的是什么？**

我正式成为 Docker 开发人员解决方案小组的产品负责人。我主要关注开发人员对 Docker 的使用。我不认为有正常的一周或一天。从与工程团队合作以确保他们了解他们正在做什么，到与客户进行大量交谈，我做了所有的事情，因为最终这是关于如何改进我们正在做的事情以及与更广泛的 Docker 用户社区进行交谈的最佳反馈来源。

显然，我们已经有了 Docker Enterprise 的客户，但是我们还有一大堆其他人在使用 Docker 做各种不同的事情。因此，我们花时间参加在布鲁塞尔附近根特举办的[配置管理营 2019 活动，并与这些人见面。就我正在做的事情而言，其中一部分是推出 Docker 桌面企业版，这是很多人使用的 Docker 桌面产品的商业版本。Mac 和 Windows 的 Docker 非常受欢迎——他们每月都有几百万活跃用户。很多工作都是经典的产品规划和商业案例分析。另一方面，我和我的同事们正在围绕](https://cfgmgmtcamp.eu/) [CNAB](https://cnab.io/) (云原生应用捆绑包)开展工作，这是 API 驱动的基础设施的元包格式的新规范。

**你为什么认为 CNAB 值得发展(DX 和商业方面)？难道不就是重新发明轮子，在已经很复杂的云原生工具世界上再增加一层吗？**

CNAB 是通过几条主要路线形成的。其中之一就是我们在内部做的一个叫做 [Docker App](https://blog.docker.com/2018/12/docker-app-and-cnab/) 的工具。这实际上是围绕基于 Docker Compose 的应用程序的共享和重用。Docker Compose 非常受欢迎，在 GitHub 上公开了成千上万的 Compose 文件，毫无疑问，在其他地方还有更多。它只是一个基于源代码的工件，所以它没有很好的重用故事。你可以通过复制粘贴来重用这些东西，这也适用于很多其他的东西——cloud formation 模板和代码。因此，让我们有一个包装版本！Dockerfile 是一个基于源代码的东西，你可以完全共享它们。然而，大多数人实际上使用你用他们构建的图像——木偶有木偶模块，而且是人们重用的木偶模块；Terraform 有 Terraform 模块和注册表。有一个包的模式真的很常见，我们正在开发 Docker 应用程序，以便真正将它组合起来。与此同时，微软的一群人(实际上是创造了 [Helm](https://helm.sh/) 的一些最初的人)正在研究包装的一般模式。特别是，他们从多个工具链的角度来看待它。人们可能会在 Helm 上使用各种资源管理模板，所以与其说你有多种打包标准，为什么我们不能有一种可以处理多种工具的方法呢？

我们聚在一起，结合了双方的最佳想法，我们正在做的和他们正在做的，这导致了 CNAB。对我们来说，它是我们正在构建的实现细节和工具，但实际上，它还具有更广泛的适用性。我们和任何人都可以在其他工具的基础上进行构建。但它并不试图必然地取代某种东西，也不试图解决所有的问题。它首先是 2018 年 12 月在 DockerCon 和 Microsoft Connect()上公布的规范。我们上周开始了第一次社区会议，明天还会有一次，所以一切都很新。

它也不打算成为一个大的消费者类型的事情。不是 Docker，不是 Helm，不是 Terraform。它最终是为那些正在构建这类工具的人准备的，包括那些尚不存在的工具。事实上，如果我们都同意这一点，这些相当低级的位，其中一些实际上是一些元数据的模式、文件系统布局、执行模型，然后是分发模型，其中没有一个以任何方式真正区分，这都是关于这一点的协议。如果您看一下以前的工具集(Chef、Puppet 和 Terraform 就是很好的例子)，所有这些工具都有一些您创建的元数据，所有这些工具都有一个规定的包文件系统布局和一些磁盘上的表示，但是没有一个使用这些工具的人能够正确地告诉您这些是什么。如果你正在使用这些工具中的几个，你最终会有多个注册表，你不能把它存储在一个地方，所以你最终会为一些没人真正关心的东西付出代价。CNAB 是所有关于协议的水平，我们可以共享工具。

在您关于云原生开发人员工作流的一次谈话中，您认为“持续集成是现代软件开发的一项基本实践，并且(…)这是您在精通其他一切之前投资的事情。”你能告诉我们更多吗？

CI 的目标是成为其他工具之间的粘合剂。在不采用自动化的情况下，将基础设施作为代码与您正在使用的任何工具结合起来是不可能的。在某种程度上，CI/CD 已经成为基础架构和应用程序部署的工作流引擎。

**在[你 2017 年的演讲《赞美缓慢(连续交付)》,](https://www.youtube.com/watch?v=ETLxePb9Sxk)中，你描述了企业软件场景(本地等)中连续交付的最佳实践(或缺乏连续交付)。)那次谈话已经过去两年了——你认为有什么好转吗？还是一开始就应该改变？**

这个演讲的背景实际上是关于在由于一些实际的现实约束而不能更快的环境中最终采用持续集成和持续交付模式。我认为，发展不快的大型组织通常不会受到任何物理因素的限制——他们会受到他们认为的发布软件的最佳方法的限制。

如果你想到一个持续交付给一个 web 属性的世界，在这个世界中，概念上只有一个东西处于稳定状态(如果它曾经存在的话)，那么这种脱节通常是不存在的。打包软件是完全不同的，正如你通常推出它的交付机制一样，它是按照消费者的意愿来消费的。大型组织期望尽可能长时间地运行他们自己的软件和第三方软件，而不必改变任何东西。

支持两年、三年、五年或十年是现实的，尤其是当你进入网络资产业务之外的环境时，这在大型组织中是很常见的。我们与在油田、游轮或工业场所部署设备的人员一起工作，实际上，您已经从 CI/CD 中获得了大量的软件和硬件，但是这些模式的实际实现看起来并不像一键部署到 Web 属性。

这类似于这些环境中的测量和度量。如果你习惯了 Google Analytics 是一项免费服务的世界，它使你能够从网络浏览器中获得大量信息，那么开源软件或图形桌面工具或边缘环境中的工具就不同了。从中获取工具和度量标准更加定制化。在某些情况下，连接和网络也不尽相同。这些可能会暂时断开连接，或者由于它们的运行方式，它们永远无法连接到互联网。因此，如何从这些数据中获取数据，并通过 CI/CD 循环，然后对它们进行评估，真的很有意思。

**你正在管理 [DevOps weekly](https://www.devopsweekly.com/) 时事通讯，它拥有成千上万的读者，你还在审查许多会议讨论提案——****这些提案和你的其他活动使你非常接近社区，了解它的困难和解决方案。如果您可以尝试找出 2019 年将在基础架构/开发运维/云原生场景中带来什么，会是什么？**

实际上，我看到越来越多的人谈论的一个趋势是作为基础设施中的一等公民的成本。支出一直都在，但它从来都不是一个超过特定主题的东西。我认为，随着无服务器出现到一定程度(以及更好的工作负载调度)，通过成本进行优化正成为一个有趣的领域。

**完全正确！这就是为什么有了 [Semaphore 2.0](https://semaphoreci.com) ，我们已经脱离了基于固定盒子数量的传统统一定价。相反，它会根据您团队的实际需求进行扩展，当您不使用它时，您不会付费。** **您如何评价这种关注基础设施成本的趋势？**

我们不需要更多的名字，但我听说有些人用好市多。在这个领域，我认为我们现在有技术去做很多新的事情。这有可能再次拉近工程师、开发人员和其他合作伙伴与企业的距离。

我还认为，有了这些好的成本信息，就可以进行一系列关于权衡的非常有力的对话。

这非常有趣，因为它实际上可能会影响公司为工具定价的方式。不是在早期阶段，但你知道在未来的某个时候。

是的，但我更感兴趣的是，这些信息的透明度(通常是非常精细的级别)如何帮助组织做出选择并随着时间的推移而改变。因为实际上，基础架构的大部分成本计算都是基于长期的前期成本模型。它仍然是基于预算过程来完成的，这在较大的组织中可能需要几年时间。

**有意思。所以，一切都是为了钱？**

我们一直在为服务和基础架构付费，但有了这项技术，我们可以将其细分为特定于工作负载的成本计算，并且有了进行这种推理的工具，这就开启了一系列经典的 DevOps 对话，来自组织不同领域的人可以聚在一起；就像(几年前的答案)安全变得越来越重要一样。人们总是关心安全，但是安全人员并不总是在房间里。我认为许多组织都在改变这种情况。这会让财务人员走进那个房间，与技术团队进行更有趣的理性对话吗？我也这么认为当然，在某些情况下，很多这样的事情需要时间来让每个人开心。当谈到今年有什么在加速发展时，这绝对是我感兴趣的事情之一。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>