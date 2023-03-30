# CI/CD 管道的混沌工程

> 原文：<https://thenewstack.io/chaos-engineering-on-ci-cd-pipelines/>

[桑德拉](https://www.thundra.io/)赞助了这篇文章。

 [埃姆拉·萨姆丹

艾姆拉是桑德拉公司的产品副总裁。他热衷于无服务器、可观测性和混沌工程。](https://www.linkedin.com/in/emrahsamdan/) 

混沌工程是将故障引入系统以测试其响应并在导致停机之前发现缺陷的行为。这是一个不断发展的实践，允许工程团队和开发人员对他们软件的可靠性负责。

在实践中，一个没有经过有效和常规检查的应用程序更容易停机，这会导致客户流失。这份由 ITIC 进行的 [2020 年调查](https://itic-corp.com/blog/2020/06/forty-percent-of-enterprises-say-hourly-downtime-costs-top-1million/)显示，87%的组织要求至少 99.99%的可用性。十分之四的企业还报告说，一个小时的停机时间会给他们带来 100 万到 500 多万美元的损失，这还不包括罚款和法律费用。

混沌工程是网飞在 2011 年推出的，当时该公司的流媒体和在线租赁服务是在内部服务器上运行的，导致了大规模的中断和服务器故障。为了应对这些问题，网飞决定从物理内部基础设施迁移到运行在 AWS 上的分布式基于云的架构，以支持越来越需要资源和复杂的活动，例如将其客户群扩展到 190 多个国家的 [1 亿用户](https://media.netflix.com/en/about-netflix)。

虽然迁移有其优势，但它也带来了新的复杂性，并需要开发容错和可靠的系统。那时，网飞工程团队构建了一套开源工具，名为[猿军](https://github.com/Netflix/SimianArmy)，用于检查他们的 AWS 基础设施对各种故障的弹性、可靠性和安全性。

## 混沌工程原理

在混沌工程中，你运行有计划的和深思熟虑的实验，这些实验产生关于系统的性能、属性和行为的新知识。

以下几点总结了你在进行混沌实验时需要遵循的一些原则:

### **定义系统稳定状态的指标**

为了成功地运行混沌实验，您需要定义指示您的应用程序在正常条件下的行为的指标。系统的稳定状态取决于它的用例及用途。因此，对稳定状态的良好理解将使您能够跟踪、监视并正确理解您的系统在遇到错误时是如何工作的。

当您定义系统的稳定状态时，业务指标在功能上比纯粹的技术指标更有用，因为它们提供了关于应用程序健康状况的更细粒度的细节。它们也更适合衡量客户运营或体验。例如，网飞使用“每秒流数”来评估他们的[用户按下流媒体设备](https://www.techrepublic.com/article/chaos-engineering-a-cheat-sheet/)上的播放按钮的频率。业务度量的其他例子是每分钟被拒绝的事务数、每小时的搜索数、每分钟失败的登录数以及高峰时期的登录数。

### **最小化爆炸半径**

当您在生产中运行混沌实验时，您可能会遇到意外的系统中断和负面的客户影响。因为系统故障是不可避免的，你需要确保混沌实验的负面影响被控制和最小化。

### **持续混乱**

连续的混沌实验使您能够自动识别系统故障，并使您能够花更多的时间来实现新的服务和功能。做一次性的实验是一个很好的开始，但是为了不断地建立对你的系统的信心，持续地运行你的混沌实验是明智的。

### **缩放爆炸半径**

混沌工程不是关于引起停机，而是关于学习你的系统在故障下如何表现。因此，在注入故障时，您需要遵循粒度方法。这意味着注入一个小故障，检查系统输出和故障的影响，并记录您的观察结果。如果没有观测，增加混乱，从而扩大爆炸半径。通过缩放爆炸半径，您可以进一步识别与实际系统行为相关的系统故障。

## 运行混沌工程实验

生产系统注定会失败，但混沌工程帮助您开发能够应对意外事件和不可避免的灾难的应用程序。

下面是有效运行混沌工程实验的步骤。

1.  阐明一个假设。

要成功运行混沌实验，您需要对您的系统在遇到意外事件或故障时的行为做出一些现实的假设。发展你的假设的最好方法是与所有参与开发和操作的人讨论应用程序应该如何应对意外的变化。

您可以通过提出几个“假设”问题开始头脑风暴会议，并让开发、支持工程和运营团队中的每个人提出几个可能影响系统稳定状态的场景。通过与您的团队坐在一起，用白板演示您的依赖项(外部和内部)、数据存储和服务，您可以创建一个系统中可能出错的画面。

2.  **注入现实的失败和 bug。**

你的混沌实验应该反映可能的和现实的场景。在你的实验中注入真实的失败将帮助你很好的理解哪些技术和过程需要升级。例如，您可以主动注入与实际软件故障(如格式错误的消息和响应)、硬件故障(如服务器崩溃或扩展事件)或非故障事件(如流量峰值)相对应的事件。

3.  **衡量影响。**

为了完全理解您的系统在压力下的行为，或者当它遇到一个 bug 时，它的稳态行为的变化，您需要分析您在系统上的实验结果。您应该衡量失败对与客户成功相关的关键性能指标的影响。例如每秒请求数、每分钟订单数或每秒流启动数。

4.  **验证或否定你的假设。**

在运行混沌实验之后，您将发现一个需要修复的问题，或者验证您的系统对注入的故障具有弹性。这两种结果都是好的；它们将增强您对整个系统功能的信心，或者发现您需要修复的问题，以免造成生产中断。

由于混沌工程主要是制定一个假设，然后验证或否定它，如果您获得尽可能多的关于您的系统的细节，您就可以根据已知的漏洞做出预测。

## 将混沌工程集成到 CI/CD 中

尽管自动化的 [CI/CD 管道](https://thenewstack.io/category/ci-cd/)能够实现快速的产品迭代，为开发人员提供标准化的反馈循环，并减少人工错误的机会，但它们无法预测应用程序的所有故障模式。因此，组织需要创新的解决方案来帮助他们发现应用程序的漏洞，并了解当组件在构建时受到影响时它是如何执行的。这就是混沌工程和 DevOps 的交集。

通过将混沌工程集成到 CI/CD 管道中，您可以构建更好的抗脆弱应用程序，并确保系统的每个组件都具有可靠性。当您故意破坏东西并测试系统在压力下如何工作时，您可以检测应用程序故障并在它们导致代价高昂的停机之前修复它们。这也将导致更少的重复事故、更快的响应高严重性事故的平均时间、改进的系统设计和更有弹性的系统的开发。

网飞已经将混沌工程整合到他们的 CI/CD 管道中。该公司开发了 [ChAP](https://netflixtechblog.com/chap-chaos-automation-platform-53e6d528371f) (混沌自动化平台)来克服 FIT(故障注入测试)的局限性，并提高他们实验的速度、广度和安全性。他们使用 FIT 来构建更具弹性的系统，以一种受控和一致的方式将故障传播到整个系统中。

在较高层次上，ChAP 自动执行实验，并查询网飞部署管道以获得特定于用户的服务，启动该服务的控制组和实验组，并将少量流量路由到每个组。

如果结果超过预定的误差预算或阈值，ChAP 将结束自动实验，以防止灾难性的损害。网飞还将 ChAP 与 [Spinnaker](https://www.spinnaker.io/) 整合，后者是一个由网飞构建的开源 CI/CD 平台，由甲骨文、微软和谷歌提供支持。这允许工程团队连续运行实验，使用 ChAP 识别意外的交互、CPU 密集型回退以及负载平衡器和断路器之间失谐的重试策略。

微软还使用自动故障注入技术和混沌工程原理来增强他们交付给客户的应用程序、他们交付的产品以及他们向开发人员提供的服务的信心和弹性。

最终，随着客户越来越依赖功能系统，威胁变得更加复杂，错误空间缩小，将混沌工程集成到 CI/CD 管道中的需求只会增加。通过使用混沌工程和故障注入，开发人员可以测量、理解和提高应用程序的弹性。架构师可以建立对其设计的信心，运营团队也可以在向客户推出新的数据中心和硬件之前对其进行验证。

## 桑德拉混沌注入特征

使用混沌工程，开发人员和工程团队可以构建分布式关键业务或高可用性系统。

[桑德拉](https://thundra.io)使用混沌注入将混沌工程整合到服务中。此功能允许您主动将故障注入到您的应用程序中，以模拟您的系统故障，并查看它们如何影响您的系统。桑德拉给你工具来运行现代建筑的混沌工程实验，甚至在任何问题发生之前测试你的建筑的弹性。桑德拉目前支持 Python、Node.js 和 Java 中的混沌注入。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>