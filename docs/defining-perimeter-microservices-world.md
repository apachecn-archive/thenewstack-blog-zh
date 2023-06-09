# 定义微服务世界的边界

> 原文：<https://thenewstack.io/defining-perimeter-microservices-world/>

当应用程序被限制在单个服务器上时，安全性很简单。它所需要的是一个防火墙，就像一个盒子，盒子里的一切都是安全的，而盒子外面的一切都是易受攻击的。防火墙是责任停止的地方，它构成了您的网络和应用程序的边界。

唉，时代变了。新技术彻底颠覆了基于边界的安全性，是时候重新思考安全性对现代云原生应用程序意味着什么了。

## 云如何改变安全性

 [吐温·泰勒

Twain Taylor 是印度的一名技术分析师，他的职业生涯始于谷歌，曾参与 AdWords 团队的技术支持。此贴为扭锁客贴。](https://www.paloaltonetworks.com/prisma/cloud) 

云对安全的最大影响在于防火墙的工作方式。防火墙根据 IP 地址允许或拒绝用户访问。用户可以是一个人，如雇员，也可以是另一个应用程序。这方面最大的变化是，像亚马逊网络服务(AWS)这样的云提供商现在已经将访问控制掌握在自己手中。他们拥有成熟的身份和访问管理(IAM)工具，这些工具已深度集成到他们自己的云平台中。例如，AWS IAM 可以控制对 EC2 实例上运行的应用程序的访问，方法是允许应用程序从 S3 存储桶中获取数据，或者向 AWS CloudTrail 发送 API 调用以进行日志记录。它还可以定义基于角色的访问控制(RBAC ),只允许授权用户查看或更改应用程序的代码。从这个意义上说，AWS IAM(不使用术语防火墙)执行了防火墙的大部分职责。

此外，云供应商已经建立了共享安全模型，他们负责云的安全，客户负责云中的安全。他们在最基本的层面上保护安全，并设置强大的默认设置来避免恶意软件的攻击。此外，AWS Inspector 和 AWS Macie 等工具会自动扫描云中的所有资源，以检查漏洞。虽然云供应商尽力维护安全性，但安全性通常会因为客户未能保护自己在云中的资源而受到影响，例如在没有加密的情况下存储机密，留下一个 S3 开放端点，或者不注意如何将数据同步到云。

云是一种改进，因为它承担了一些关键的安全责任。但它也带来了一种不同的安全方法，需要一些时间来适应。

## 容器和微服务可能是一场安全噩梦

从外围防火墙的简单时代开始，云让 IT 团队的安全性变得更加微妙。然而，随着容器的出现，这个等式达到了新的复杂程度。

当他们开始时，关于容器的口头禅是“[容器不包含](https://opensource.com/business/14/7/docker-security-selinux)”Linux 安全专家对容器之间的弱进程隔离直言不讳，并且由于多个容器共享同一个客户操作系统，不容易控制漏洞向相邻容器的传播。

然后是微服务架构的引入，其中一个单一的应用程序被分解成多个相互依赖的服务。虽然“分而治之”的方法在运营效率方面很有吸引力，但只要看一看将微服务相互连接的网络，就会让任何安全专业人士望而却步。服务需要在多对多的网络中相互通信，现在称为服务网格。尽管它们联系如此紧密，但仍需要一种方法来确保延迟、失败的实例和安全威胁被包含在每个服务中，以便即使一个服务被关闭，其他服务也能执行它们的功能，直到受影响的服务被恢复。不用说，请求的数量和复杂的路由模式看起来都像是为乌托邦式的基础设施方法缴纳的重税。如果没有新的安全方法，特别是现代云原生应用程序的网络安全，这种情况就会发生。

## 微服务安全的新方法

今天的容器化应用程序重新定义了边界的含义。充分保护云原生应用需要多方面的努力。我们来讨论一下关键策略。

**特定于容器的安全性**:容器映像是漏洞的主要来源，因为公开共享的映像经常被感染，并且对于生产环境来说是不安全的。集装箱登记处的图像扫描功能使得扫描所有下载的集装箱图像变得容易。他们对常见的已知漏洞进行检查，并遵循 CIS Docker 安全基准。

重要的是，在运行容器时，它们需要作为无特权、非根容器运行。这可以防止漏洞传播到其他容器和主机。此外，需要采取措施使容器图像尽可能小。这减少了潜在的攻击面。此外，确保容器的生命周期短(不超过一周)可以使您的系统更具动态性，更不容易受到攻击。

**基于策略的网络安全**:容器网络现在是一个复杂的服务网络，无法手动配置。相反，您需要一组策略，根据需要自动启用授权服务之间的通信。Weave、Linkerd 和 Project Calico 等工具采用了这种方法，并在容器编排的早期采用者中获得了广泛采用。这与防火墙有关。现在有了保护每项服务的微型防火墙，而不是有一个外围防火墙，一旦被攻破，整个系统都将不堪一击。因此，即使其中一项服务遭到破坏，其他服务仍然是安全的。

**威胁检测**:集装箱安全和监控解决方案有很多种，每一种都满足整个安全难题的一部分。将它们结合在一起并提供整体安全性的是一个威胁检测工具，它可以提供端到端的监控。重要的是，在攻击过程中，它可以识别可疑模式，并快速突出攻击的来源和范围。这需要使用机器学习进行高级数据分析，但将复杂性隐藏起来，同时允许安全团队利用高级安全措施，而不需要专门的数据科学团队。

**集中式日志**:在集装箱时代，日志在 SecOps 中扮演了更加突出的角色。由于有大量的容器、大量的网络请求和不断变化的状态，日志有助于详细监控所有事件。它们在故障排除过程中至关重要。日志需要集中存储，并通过专用的日志分析工具方便地访问。像 Elasticsearch 这样强大的开源解决方案使容器的日志分析变得很容易。

## 结论

随着基础设施的变化和攻击变得越来越复杂，安全解决方案需要与时俱进。通过在内部管理访问控制，云承担了传统防火墙的一些角色。随着容器和微服务的出现，这种情况进一步改变，使得外围防火墙变得过时。然而，在传统防火墙的废墟上，新的应用程序安全方法已经兴起。

容器映像的容器特定安全性、基于策略的网络安全性、运行时威胁检测和集中式日志分析是保护微服务应用的新方法。简单安全的好日子已经一去不复返了。虽然在微服务世界中，安全边界已经变得模糊，但新的微边界能够提供以前不可能提供的安全级别。这个承诺值得它带来的所有复杂性。

[Twistlock](https://www.paloaltonetworks.com/prisma/cloud) 赞助本帖。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>