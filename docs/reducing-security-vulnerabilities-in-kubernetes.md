# 减少 Kubernetes 中的安全漏洞

> 原文：<https://thenewstack.io/reducing-security-vulnerabilities-in-kubernetes/>

在本帖中，我们将讨论关键的集装箱安全最佳实践，以帮助您避免复杂的安全挑战，并成功减少 Kubernetes 集装箱化环境中的漏洞。

容器化环境为开发人员提供了许多优势，但也带来了复杂的安全挑战。遵循容器安全最佳实践可以帮助您降低风险、减少漏洞并成功交付经验证的软件。

在这里，我将为开发人员提供容器安全性基础知识的概述。如果你是一个开发 Docker 容器的开发者[，并且想要确保它的安全性，下面的提醒会有所帮助。](https://thenewstack.io/how-to-run-a-cassandra-operation-in-docker/)

## 不，名称空间不够隔离

 [亚历山大·沃洛奇涅夫

Aleks 是 DataStax 在 EMEA 的主要开发者支持者。作为一名多年的开发人员、技术主管、DevOps 工程师和架构师，Aleks 现在专注于云计算和分布式系统，并分享他在高性能和容灾系统领域的专业知识。](https://www.linkedin.com/in/aleks-volochnev/?originalSubdomain=de) 

名称空间是主 Kubernetes 集群中的一个虚拟集群，它提供了一种在控制平面中隔离相关组件组的机制。然而，假设名称空间足以让资源在隔离环境中执行进程，这是大多数开发人员的错误之处。

虽然名称空间(以及在其中运行的资源)为您提供了额外的上下文和内部隔离，但它们不会将您的资源与其他名称空间隔离开来。

因此，您需要一个名称空间作为开始来描述部署或服务，然后是额外的配置以使隔离有效。

此外，pod 可以通过它们的 IP 地址继续相互通信，而不管它们位于哪个名称空间。这是因为跨名称空间通信是 Kubernetes 集群和常规设置中的默认设置。

## 不要容器和根

遵循最小特权(PoLP)原则，根容器和非根容器之间的主要区别在于，后者侧重于确保运行进程所需的最小特权。如果开发人员尽可能坚持这一原则，并且不以 root 身份运行容器，那么严重的安全问题就会减少。

让我解释一下:您有一个监听特权端口的服务，比如端口 80，您需要以 root 用户身份运行它。但是你也应该问问自己，你**是否真的**需要在 80 端口上运行你的服务。你的责任是在意识到所有可能的影响后做出这个决定。

*“但是它是在一个容器中运行的，这不是很好吗？”*

不幸的是，没有。这是因为一个严重的安全问题:特权升级。

防止权限提升是避免以 root 用户身份运行容器的关键。容器中的根用户可以作为传统主机系统上的根用户运行每个命令，包括启动服务、安装软件包和创建新用户。从应用程序的角度来看，这当然是不可取的，容器也是如此。

您还需要了解容器运行时或内核漏洞。根用户可以作为高特权用户访问和执行底层主机上的任何内容。这意味着他们可以访问在主机上配置的用户名/密码以连接到其他服务，可以安装不想要的恶意软件并访问其他云资源，以及其他可能使文件系统装载面临风险的活动。

大多数服务无需提升权限即可运行。对于那些做不到的人，有一些功能可以给你细粒度的控制。特权容器尤其如此，它代表了所有可用功能的最高升级级别。如果有人要接管容器中的服务，这个人需要拥有最高的特权。否则，他们根本不能。所以即使一个容器化的 app **真的**需要一些高级权限，你还是不应该以 `--privileged`的身份运行；最好使用`--cap-add`进行更细粒度的控制。

Docker 还有一个无根模式，您可以用它作为非根用户运行 Docker 守护进程和容器。此外，您可以使用这种模式来减少守护程序和容器时间中的漏洞，这些漏洞有时会让恶意代理获得对整个节点和集群的超级用户访问权限。

这里的另一个重要注意事项是，缺省情况下，无根模式能够在用户名称空间内运行没有根权限的守护程序和容器。

## 网络需要分段

使用入侵防御系统(IPS)来阻止恶意流量不足以充分保护集装箱化的环境——这是我的经验之谈。

让我用一个简短的轶事来说明这一点。我曾经在一家公司工作，该公司为了协作而实施了扁平网络模型。您可能知道，扁平网络和可访问区域意味着网络中的每个人都可以访问任何内容，这可能会带来严重的安全问题。我问当时的网络设计师他们是否对此感到担忧，他们告诉我他们已经“实施了一个 IPS 来防止恶意尝试。”

一年后，建筑师离开了公司，随之而来的是一个巨大的安全漏洞。单纯依靠 IPS 在当时是不够的，现在肯定也是不够的。

那么，您能做些什么来避免违规呢？构建网段。这样做的主要优点如下:

*   **他们最大限度地减少违规** —通过创建仅包含特定于您需要授权访问的消费者的资源的网络段，您创建了一个最小特权的最佳环境，从而最大限度地减少违规。

*   **将伤害降到最低**——他们控制了爆炸半径，以防成功开采。这使得更容易防止被恶意代理利用的集装箱的横向移动，并且符合 PCI DSS 标准。

*   **最大限度地减少数据泄露** —网络分段还有助于防止或最大限度地减少数据泄露的不良影响，这是入侵检测系统(IDS)和 IPS 的不足之处。由于 IDS 和 IPS 是反应性的，因此只有在这些设备上的规则更新后，它们才能检测到新的攻击或漏洞。因此，更新总是有可能来得太晚，使网络罪犯更容易找到并利用您的网络。

## 让您的依赖关系保持最新

依赖性管理是创建和维护安全可靠的软件供应链的一个重要方面。这也有点复杂，因为守护进程和其他因素的存在使得很难确定到底需要做什么来保持依赖关系最新。

这也是为什么简单地为 Docker 容器使用最新的标签不足以确保足够的保护。要正确地做到这一点，您必须首先通过以下方式了解您的依赖关系:

*   查看 CI/CD 中的依赖检查( [npm](https://docs.npmjs.com/about-npm) 或 [Apache Maven](https://maven.apache.org/) )。
*   监控相关数据源，如安全公告。
*   定期更新/重建(这有助于确保安装最新的安全补丁)。

您还需要小心“隐藏”或嵌入的依赖项。当您运行 Docker 容器时，您可能会使用包管理器来安装依赖项。有时你可能不得不下载一些类似模块的东西，甚至自己开发一个软件。在这两种情况下，您都应该确保更新这些依赖关系，因为它们不一定会在所有扫描中弹出，如果它们过时，可能会成为潜在的容器安全问题。

依赖性管理的另一个重要方面是只使用可信的来源，并确保手头的项目是一个实际的 Docker Hop 项目。

首先，你需要注意域名仿冒，骗子使用拼写错误或修改过的域名来欺骗用户访问欺诈网站。令人震惊的是，如果你使用“MGINX”而不是“NGINX”，那么会有多少项目试图给你恶意软件。所以要小心你输入和点击的内容。

其他最佳实践包括使用描述性标记，而不是最新的标记，以及定期检查依赖项更新。

## 外卖食品

容器安全包括持续实施和维护安全控制，以保护容器和底层基础设施。

通过将上述最佳实践应用到您的开发管道中，您可以提高容器化工作负载的可见性。这将帮助您保护所有容器资源和组件，从最初的开发阶段直到其生命周期结束，防止违规并确保及时补救。

这里有一些资源可以帮助您复习容器知识:

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>