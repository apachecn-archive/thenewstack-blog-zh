# 通过云原生软件消除零信任

> 原文：<https://thenewstack.io/shifting-zero-trust-left-with-cloud-native-software/>

[](https://www.alcide.io/)

[Gadi Naor](https://www.alcide.io/)

[Gadi Naor 作为首席技术官和 Alcide 的联合创始人，拥有 15 年的网络安全产品开发经验。Gadi 将他的管理和技术背景融合在不同的岗位上。Gadi 曾在 CheckPoint 工作，担任业务开发经理和高级开发人员，领导 CheckPoint 的防火墙核心安全引擎和 VPN 软件的开发。然后，他在 Altor Networks 担任高级软件工程师，Altor Networks 是虚拟化数据中心安全领域的先驱，后来被 Juniper Networks 收购，他继续担任高级软件工程师。在联合创立 Alcide 之前，Gadi 是基于微服务的系统 Fitfully 的联合创始人兼首席技术官。](https://www.alcide.io/)

[](https://www.alcide.io/)[](https://www.alcide.io/)

随着公司寻求减少在云原生应用中提供新功能所需的时间，现成和第三方代码(尤其是开源代码)的使用正在改变开发者的网络安全范围。据估计，云原生应用[中高达 80%到 90%的代码源自开源组件](https://www.sonatype.com/2017-state-of-the-software-supply-chain-report)。

代码组成的这种变化迫使今天必须由 DevOps 专业人员保护的领域发生转变。DevOps 专业人员现在必须扩展他们对如何保护整个软件供应链的视角，而不是仅仅关注软件开发生命周期。

> "结合零信任和连续扫描，企业可以平衡性能需求和安全需求."

软件供应链代表所有贡献的软件组件(无论是源代码还是预打包组件)以及最终将代码部署到试运行或生产环境中的交付系统、渠道和流程。第三方未知的开发技能和动机造成了具有挑战性的安全风险，这可能导致无意中的安全缺陷或恶意软件的故意注入。安全和 DevOps 团队现在必须防范未经监管或适当的安全审查而生产的组件，这些组件有时会集成到应用程序代码中。

## 对 Kubernetes 和容器环境应用零信任

对软件供应链风险的实质范围的自然反应是不相信任何人和任何东西，并扩展零信任的概念以包括其他风险载体。虽然零信任是建立安全基线的绝佳场所，但必须以不损害业务敏捷性或创新的方式来实现。

从最佳实践的基础开始:

1.  根据 Kubernetes 和 Istio 等平台推荐的最佳实践，确保群集的启动环境最初配置为“完全健康”。默认配置有时会进行优化，以使开发团队可以轻松访问系统，但不一定代表生产就绪、加固和锁定的配置。
2.  确保基础设施软件有最新的补丁和更新，因为容器运行时会出现越来越多的漏洞。

部署集群并微调访问控制:

1.  在生产中使用准入控制来实施策略，并防止违反策略和卫生级别的资源进入群集。
2.  除非明确批准和要求，否则降低工作负载的运行时特权，并避免以 root 或任何提升的特权运行它们；使用 AppArmor/seccomp 配置文件控制风险面。
3.  使用不可变的文件系统运行工作负载，以降低系统受损的风险。
4.  基于运行时的工作负载应用分段和隔离策略。
5.  观察配置以避免泄露机密、密码和密钥。
6.  确保应用网络策略。
7.  控制对工作节点的网络访问。

这些准则将为我们的应用程序的安全性建立一个强大的初始基线，但这并不是我们能做的全部。

## 持续 Kubernetes 卫生-来自持续部署

完全应用零信任是一个企业可能需要更长时间来采用和实施的过程。企业可能希望在这种努力和交付速度之间取得平衡。结果是，在 Kubernetes 中，对不太重要的组件(有时是整个集群)的访问控制变得宽松了。虽然从网络和访问控制的角度来看，这造成了安全缺口，但对风险应用防护栏引入了一个重要的缓解层。这些护栏可以插入 CI/CD 的 CD 部分。这种零信任的扩展版本可以与 DevOps 协调工作，充当速度和安全性的推动者。

正如传统的映像漏洞扫描可用作运行时可能采用的工作负载飞行前风险分析一样，我们可以对每个部署事件应用类似的策略和风险驱动的检查，以实现对工作负载的连续扫描，了解正在运行的内容，并了解完整性和健康水平。无论触发器是单次代码提交还是批量代码提交，我们都可以在产品化之前捕捉到偏差。

例如，我们寻找嵌入的秘密或连接到错误位置的秘密，精明的入侵者、内部用户或其他系统组件可以利用这些秘密来访问敏感数据。在测试集群上应用这些保护轨可以产生立竿见影的效果。

持续扫描使 DevOps 能够监控应用程序不断发展的安全状态。扫描检测部署后出现的新漏洞，而不是依赖于部署时应用程序安全状态的陈旧知识。DevOps 监控不断发展的安全状态，并对安全形势的变化做出反应。

### 平衡护栏和传送速度

企业现在必须保护其云原生应用程序免受软件供应链带来的安全风险。将零信任和连续扫描相结合，使企业能够平衡性能需求和安全需求。关键组件得到强化，不太关键的组件可以在仔细的监督下自由执行。通过这种方式，公司可以实施零信任安全方法，解决新的加速开发模型的复杂性，并使开发运维团队能够以平衡的方式采用持续的安全实践，而不会妨碍敏捷性或速度。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>