# 如何超越云供应商的工具来保护您的云环境

> 原文：<https://thenewstack.io/how-to-secure-your-cloud-environment-beyond-your-cloud-vendors-tools/>

[Twistlock](https://www.paloaltonetworks.com/prisma/cloud) 赞助本帖。

自从大约十年前云成为一种东西以来，我们已经被关于云如何带来安全风险的警告淹没了(比如这里的、这里的和这里的)。

事实上，尽管有些人可能会暗示，云并不是天生不安全的。尽管如此，云服务用户需要采取一些重要步骤来保护他们基于云的环境和工作负载，尤其是那些云供应商自己无法有效保护的环境和工作负载。

本文通过强调云供应商如何提高安全性，以及用户需要采取哪些额外的预防措施，详细介绍了这些步骤。

## 您的云供应商的安全责任

 [Maame Efua Boham

Maame 是加纳 Ashesi 大学的三年级学生，正在攻读计算机科学学位。Boham 对 Python 作为全球各领域技术飞跃的工具深感兴趣。她曾在数据科学、web 开发和软件工程领域工作。](https://www.paloaltonetworks.com/prisma/cloud) 

您的云供应商提供的安全性将根据您使用的云服务类型而有所不同。

如果你使用的是 AWS EC2 或 Azure 虚拟机这样的基础设施即服务(IaaS ),你的云供应商只负责底层基础设施。操作系统、中间件和其他运行时都落在客户端。

对于 PaaS 平台，比如 Google App Engine，一个客户端构建自己的应用；然而，诸如数据存储和管理之类的任务被抽象掉了。

借助软件即服务(SaaS)，云供应商托管、管理和提供企业可以购买和使用的基础设施和应用。然而，对于所有这些云计算类别，客户端负责所涉及的数据。

## 终端用户的云安全责任

无论您使用哪种类型的云服务，保护特定类型工作负载的负担都落在您身上，而不是您的云供应商。

一般来说，您需要记住以下几点，以最大限度地提高云环境的安全性。

### 查看默认云设置

您需要记住的第一件事是，虽然某些设置是由提供商自动设置的，但其中一些必须手动激活。拥有您自己的一套安全策略总是比假设云供应商正在处理您的云安全的特定方面要好。

### 根据您的组织调整数据存储和身份验证配置

所有上传数据的位置都应该有密码保护。此外，应该仔细选择密码过期策略，以满足您组织的需求。

### 不要假设你的云数据是安全的

永远不要认为云供应商加密的数据是完全安全的。有些云厂商提供上传前加密服务，有些不提供。无论是哪种情况，确保使用自己的密钥加密数据。还要记住，数据应该在传输过程中和静态时进行加密。

### 与您的云数据保留策略相集成

了解云供应商的数据保留和删除政策对于确保数据安全至关重要。从云中删除数据会发生什么？云供应商还能访问它吗？有没有可能被缓存或复制的地方？这些是您在转向新的云环境时应该预先验证的一些事情。拥有数据的多份拷贝和固定的数据保留期也很重要。

### 设置适当的权限

权限级别的适当设置有助于使您的云环境更加安全。通过使用基于角色的访问控制进行授权，您可以确保每个查看或使用您的服务的人只能访问绝对必要的内容。或者，一个基于规则的访问控制服务(T1)，比如 T2 扭锁(T3)，可以简化这个过程。

### 让基于云的软件保持最新

您的云供应商可能会提供基础架构，在某些情况下，还会提供预构建的软件环境。但是你添加的任何东西都要由你来保护。

因此，作为云服务的用户，你有责任确保你的安全补丁、操作系统等。都是最新的。防止技术债务和积压的最简单方法是[自动化](https://www.twistlock.com/2018/11/05/automation-crucial-ingredient-microservices-security/)更新。

### 在您的云映像中构建安全策略和最佳实践

将云环境的安全性留给 DevOps 团队中的不同开发人员可能会导致策略上的差异。解决这个问题的一个好方法是创建配置了安全工具和应用了策略的云映像，这样开发人员就可以简单地创建它们的实例并使用它们。

### 隔离您的云资源

为了降低黑客完全控制您的系统的风险，建议为开发、部署、测试等设置单独的管理帐户。这样，如果黑客访问一个帐户，他或她就不能跳到环境的其他方面。

## 结论

您的云供应商将尽其所能保护您在云中运行的资源，但事实是您的云供应商无法独自保护您。您的协作对于保护服务和资源至关重要，这些服务和资源不是云供应商管理的，就是云供应商配置的方式不太符合您组织的需求。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>