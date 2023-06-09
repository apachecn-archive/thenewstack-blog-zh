# spectro Cloud:SaaS·库伯内斯你的方式

> 原文：<https://thenewstack.io/spectro-cloud-saas-kubernetes-your-way/>

使用 Kubernetes 来管理您的基础架构意味着您要么在内部部署和管理它，要么雇用托管服务提供商，这通常采用一刀切的方法。

第一个提供了灵活性，但是非常复杂，而第二个处理了复杂性，但是非常僵硬。

总部位于加州圣克拉拉的 Spectro Cloud 断言应该有一条中间道路——为 Kubernetes 用户提供 SaaS 管理的控制和灵活性。

首席执行官 [Tenry Fu](https://www.linkedin.com/in/tenryfu/) 表示:“虽然 Kubernetes 是一项令人敬畏的技术，但它不是一种产品，它只是一个更广泛的难题的一部分，你也必须解决它，以确保它能够真正投入生产，而不是接管你的生活。”。

“我们希望提供一个基于 SaaS 的平台，帮助企业客户能够保持对其 Kubernetes 基础架构堆栈的控制，同时还能提供托管 Kubernetes 体验的便利性。”

Spectro Cloud 使用它所谓的集群配置文件，将集群分为多个层，用户可以在其中创建所有相关组件的声明性模型:Kubernetes 版本、网络、存储、安全性、日志记录、监控、负载平衡和用户定义的层。

该平台可自动维护和升级集群，确保快速应用补丁和无缝升级。

组织内的不同小组可以有不同的配置文件来满足他们的需求，然后让 Spectro Cloud 负责大规模部署和管理集群。

“由于运营的复杂性，企业正在努力实现 Kubernetes 的承诺。虽然托管 Kubernetes 服务为那些希望/需要完全预打包方法的人解决了这个问题，但对于大多数人来说，它们对于企业的各种需求来说可能会变得过于严格。Omdia 的分析师 Roy Illsley 表示:“Spectro Cloud 创建了一个灵活的解决方案，它提供了可扩展的自动化和易于使用的托管服务，同时使企业能够保持更大的控制权。

### 年轻的公司

联合创始人傅、[萨阿德·马利克](https://www.linkedin.com/in/saad-malik-37b83b1/)(现任 Spectro Cloud 首席技术官)和[高塔姆·乔希](https://www.linkedin.com/in/gautam-joshi-27087a/)(工程副总裁)，之前曾在 [CliQr](https://www.cisco.com/c/en/us/about/corporate-strategy-office/acquisitions/cliqr.html) 共事，这是一个多云管理平台，于 2016 年被思科收购。

他们在去年五月成立了公司，并在一月份开始对他们的产品进行私人测试，涉及 16 个客户。它预计将在未来几个月内全面上市。

“尽管所有人都对 Kubernetes 感到兴奋，但许多企业在需求和运营模式之间真的陷入了进退两难的境地，”产品副总裁 Tina Nolte 说。

“我们向人们描述它的方式是围绕基础架构控制连续体。它确实迫使企业在控制和易用性之间进行权衡。在一个极端，你有像托管 Kubernetes 服务和公共云这样的东西，它们提供了你可以认为是易用性的天堂，对吗？对你想使用哪种云的昂贵控制… Kubernetes 版本，对系统组件的确切已知的好版本的控制。…另一个极端是真正的完全控制，您可以从头开始管理基础架构的每一部分。…每个企业都是独一无二的，我们相信他们应该能够准确地使用他们需要的组件，而不是供应商强加给他们的组件。”

她说，经常出现的一个例子是，公司希望能够使用更新的 Kubernetes 版本，因为他们的开发人员看到了 Kubernetes 生态系统中的功能，在托管服务或软件包发行版供应商集成或支持该特定版本之前，他们无法利用这些功能。

她说，Spectro Cloud 在整个基础设施堆栈的背景下提供集群生命周期管理，而不仅仅是 Kubernetes 本身。对于每一层，都有现成的选项，但是用户也可以创建自定义配置文件。

“我们的业务部门最终选择了不同的 Kubernetes 提供商，因为它们在人工智能、机器学习、公共云和本地产品等不同领域都有不同的利基和不同的成熟度水平。在操作上，这变成了一场噩梦，因为它需要多个支持结构来应对不同的基础架构堆栈，”加拿大保险公司 until Financial corp .的基础架构、安全和 IT 服务 IT 架构师专家 [Sébastien Morissette](https://www.linkedin.com/in/s%C3%A9bastien-morissette-60154418/?originalSubdomain=ca) 说

“像 Spectro Cloud 这样的平台通过规范在内部和云中广泛的终端上部署、操作和管理 Kubernetes 集群的方式，解决了我们的 Kubernetes 生态系统的第一天和第二天运营问题。IT 从 Spectro Cloud 的集群配置文件中获得的控制意味着他们可以为每个业务部门定制产品，同时保持对整体运营的责任。”

### 基础设施作为代码

Spectro Cloud 的集群配置文件保持整个组织的配置一致。

傅说，对于 Kubernetes 来说，它实际上只是一个代码基础设施。集群配置文件只是一个 YAML 文件。

“它基本上允许用户轻松地模拟 Kubernetes。一旦有了模型，我们功能的另一个独特部分是编排引擎，它可以采用这个模型，并在集群中部署或更新它，”他说。

“我们确实将此群集配置文件视为一种最后阶段的声明性模型，因此，如果此群集配置文件的任何内容被修改，或者如果此群集的任何内容在环境之外被修改，都将导致不匹配，我们的平台将自动检测该内容，然后自动重新计算，以使群集与最新的群集配置文件匹配。”

Spectro Cloud 通过版本升级自动监控集群的合规性，并且在 canary 部署期间依赖性不会中断。

“我们的系统会在后台自动维护您的部署与您在集群配置文件中定义的基础事实之间的一致性，”Nolte 说。“那是相当强大的。”

集群可以部署到公共云、私有云、裸机或边缘系统上。

该公司在 3 月份悄然崛起，宣布了由 Sierra Ventures 牵头、Boldstart Ventures 参与的 750 万美元种子轮投资。

“虽然云原生应用和支持基础设施仍处于早期阶段，但我们认为大创意可以帮助加速市场发展。Sierra Ventures 的董事总经理马克·费尔南德斯(T3)谈到这笔投资时说:“容器和容器集群管理基础设施将支撑下一代应用，我们很高兴能够支持 Spectro Cloud，让所有人都能访问这些基础设施。”。

图片来自 Pixabay 的 kitti851

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>