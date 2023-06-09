# 安全性:当今企业架构师需要了解的内容

> 原文：<https://thenewstack.io/security-enterprise-architects-need-know-today/>

[](https://www.paloaltonetworks.com/prisma/cloud)

 [吐温·泰勒

吐温·泰勒是一名 Fixate IO 撰稿人。他在谷歌开始了他的职业生涯，在那里，他参与了 AdWords 团队的技术支持。他的工作包括审查堆栈跟踪，解决影响客户和支持团队的问题，以及处理升级。此贴为扭锁客贴。](https://www.paloaltonetworks.com/prisma/cloud) [](https://www.paloaltonetworks.com/prisma/cloud)

企业架构师在传统和创新之间走钢丝。一方面，他们拥有仍然为业务提供动力的陈旧技术，另一方面，他们意识到技术进步需要渗透到他们监管的企业应用程序中。他们企业内部的世界似乎与创新无处不在的外部世界脱节。

除了这些苛刻的业务期望、复杂的团队结构和出现安全漏洞时出现的紧急情况，很明显，成为企业架构师不适合胆小的人。

当然，当您需要担心的安全漏洞较少时，成为企业架构师会更容易。为此，本文讨论了企业架构师应该知道什么，以便帮助最大化企业安全性。

## 企业应用的安全挑战

“企业”一词如今被用来表示从大型传统公司到任何 B2B 公司的任何事物。但是我们所说的“企业应用程序”是什么意思呢以下是一些定义特征，可能有助于澄清:

### 一切都与数据有关

对于企业应用程序，数据比使用数据的应用程序更有价值。这是因为数据集很大，而且通常可以追溯到几十年前。它们大多存储在 SQL 数据库中，但最近也存储在 NoSQL 的替代数据库中。数据是多方面的，可以在单个应用程序中或跨多个应用程序以多种不同的方式呈现。

因为这些数据非常有价值，所以攻击者首先针对的是对数据的访问。看看最近最大的数据泄露事件就能证实这一点。2017 年的 [Equifax 数据泄露](https://www.csoonline.com/article/3223229/security/equifax-says-website-vulnerability-exposed-143-million-us-consumers.html)导致 1.43 亿客户的私人信息被泄露。此外，209，000 名客户的信用卡数据被泄露。这是由 Equifax 网站中的一个漏洞引起的。

同样，[国税局](https://www.cbsnews.com/news/irs-identity-theft-online-hackers-social-security-number-get-transcript/)的 Get 抄本应用程序也遭到破坏，导致大约 70 万用户的社会安全号码被泄露。这些随后被用于申请虚假退款——这都是因为国税局避免使用双重身份认证来保护应用程序。他们不得不把这款应用程序撤下，几个月后在安全升级后发布。

对于企业架构师来说，保护数据是头等大事。重要的是如何存储、访问和使用数据。传统上，这些数据存储在物理磁盘上，通过简单的内部网络访问，并通过外围防火墙保护。这方面的问题很多。数据丢失是常见的，因为磁盘故障频繁；防火墙不是最好的防御手段，因为一旦遭到破坏，它们会使整个系统处于开放状态，而且在数据遭到破坏的情况下，很难调查破坏的来源和程度。如今，云提供商提供各种[云存储选项](https://cloud.netapp.com/blog/ebs-efs-amazons3-best-cloud-storage-system)，如亚马逊弹性文件系统(EFS)、弹性块存储(EBS)和简单存储服务(S3)，它们为多种目的提供存储。这些存储服务是安全的，可以防止数据丢失，并且易于访问。

### 与其他应用程序深度集成

企业应用程序需要相互通信才能正常运行。每个团队(如 IT、人力资源、财务、销售和营销)的应用程序都是独立的，但为了更全面地了解客户或员工，这些应用程序是集成的。集成项目通常会持续几个月，并且通常由一个供应商来处理。

当应用程序被集成时，确保只有授权的应用程序和用户能够访问数据是很重要的。开放 API 端点，以及糟糕的访问控制配置是集成项目的祸根。

### 传统应用与现代应用并存

企业陷入了一个尴尬的境地:传统应用程序只能完成工作，而现代替代应用程序却超出了所需的任务，而且用更少的资源完成工作的速度提高了 10 倍。任何更新应用程序的步骤都应该考虑向后兼容性。

传统应用的安全保护方式与云原生应用的安全保护方式截然不同。当一切都归结于私有数据中心的硬件时，安全性就更简单了。但是有了云，尤其是有了现代容器技术，安全性就大不相同了。云供应商有自己的安全、监控和日志工具。此外，还有专门的容器安全工具。

## 现代云原生应用的安全性

云原生应用程序虽然比传统应用程序更复杂，但如果方法正确，会更安全。保护这些应用程序有许多细微差别。下面我们来看几个。

### 内核安全特性

Docker 继承了 Linux 的一些核心安全特性。这些特性包括名称空间、cgroups、AppArmor、SELinux 和 Seccomp。它们强制容器之间的隔离，限制容器可以看到什么，以及容器可以使用多少资源。在容器受损的情况下，他们只对该容器造成损害。

### 图像扫描

容器化应用程序中最常见的漏洞原因是从公共注册表下载的图像。虽然这是一个令人担忧的原因，但今天的容器注册中心配备了检查常见漏洞的图像扫描工具。在生产中运行容器时，它们是必备的。

### 机密管理

容器堆栈中有许多组件，每个组件都需要对其他组件进行授权访问，因此有许多安全信息，如密码、令牌、API 密钥等等。这些数据不应该被硬编码到容器映像中，需要由单独的秘密管理特性来处理。数据经过加密，仅在需要时才可访问。

### 基于策略的网络

外围防火墙不足以保护微服务应用的网络。相反，微服务使用基于策略的网络来保护每个服务。这样，即使一项服务受到威胁，其他服务仍然是安全的。此外，当服务和底层容器被更新或替换时，它们不需要从头开始应用安全配置。可以应用相同的安全策略。像 [Weave](https://www.weave.works/) 、 [Linkerd](https://linkerd.io/) 和 [Calico](https://www.projectcalico.org/) 这样的工具正在引领这一新的基于政策的网络安全浪潮。

### 威胁检测

当在生产中运行容器化的应用程序时，漏洞可以通过许多接入点进入系统。手动浏览日志来寻找漏洞是不可能的。需要的是运行时的威胁检测。此外，这种威胁检测需要由机器学习算法提供支持，这些算法可以抓取大量数据，并在系统的各个部分之间绘制模式。这样，当有任何可疑活动时，威胁检测工具可以在它变成事件之前发现它。

## 结论

保护企业应用程序有很多风险。然而，传统的安全措施在现实世界的攻击面前显得力不从心。只有现代的云原生应用程序才能保护企业应用程序中的数据，同时提供更强大的用户体验。当今的企业架构师应该利用容器和微服务的强大安全特性，构建在传统和创新之间取得平衡的企业应用程序。

Twistlock 赞助了这篇文章。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>