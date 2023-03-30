# 集装箱化的生产环境:网络、安全和存储

> 原文：<https://thenewstack.io/identifying-solving-issues-containerized-production-environments/>

[](http://www.vivekjuneja.in)

[Vivek June ja](http://www.vivekjuneja.in)

[Vivek June ja 是一名驻首尔的工程师，专注于云服务和微服务。他于 2008 年开始从事云平台工作，是 AWS 和 Eucalyptus 的早期采用者。他还是一名技术布道者，在印度的各种技术会议上发表演讲。他在 www.cloudgeek.in 和 www.vivekjuneja.in 上写作，热爱梳理技术社区。](http://www.vivekjuneja.in)

[](http://www.vivekjuneja.in)[](http://www.vivekjuneja.in)

所以你有一个围绕容器组成的应用程序。您拥有轻量级基础映像、集中式容器注册中心，以及与部署和持续集成(CI)管道的集成——让容器在您的硬件上全面工作所需的一切。为了运行多层应用程序，您花时间使用应用程序容器的服务发现机制。您有一个日志记录机制，它从每个容器中提取信息，并将它们发送到服务器进行索引。使用一个非常适合这个机器是一次性的时代的监控工具，您可以看到监控数据的集合，让您看到围绕容器角色分组的数据。一切都井井有条。

通过将您的管道连接到生产，您已经准备好进入下一个阶段。生产环境是容器看到最大熵的地方。将容器投入生产需要您花费时间构建一个 [canary release](http://martinfowler.com/bliki/CanaryRelease.html) 系统来实现滚动升级过程。从开发环境到生产环境，每次关闭一个容器，用一个全新版本的代码替换它们，这样每一个变化都很简单。当我们在高层次上谈论采用容器时，通常会想到这一点。

然而，对于真正的从业者来说，这只是冰山一角。做前面提到的所有事情仍然不能保证你的容器有一个完美的环境。你的计划仍有可能被打乱，更糟糕的是，这可能会动摇你对集装箱的信心。我们将围绕容器网络、存储和安全性来探讨这些问题。

## 集装箱联网

容器不是孤立存在的；他们需要连接其他服务。容器需要是可被发现的，并且可以连接到其他服务。不管它们在给定机器群中的位置如何，目标都是可靠且快速地到达目的地集装箱。容器领域的联网通常与服务发现交织在一起。虽然网络在开发、测试和生产环境中会发生变化，但服务发现在不同环境中保持一致。这意味着服务发现机制必须在部署容器的各种网络中保持通用。

如果您刚刚开始在生产中使用容器，有一些关键问题需要回答，以帮助稳定您的方法:

*   如何为给定场景选择正确的网络配置？您应该使用桥接、覆盖、底层还是其他联网方式？
*   服务发现如何与各种容器网络配置集成？
*   如何监控集装箱网络并识别其性能瓶颈？
*   如何可视化跨多台主机运行的网络拓扑？
*   如何保护容器网络？
*   当在相同的物理或虚拟主机上运行属于不同租户的容器时，如何隔离网络？

在转到生产中容器的其他被误解的方面之前，我们将解决这些问题。

### 网络结构

如果需要向外部用户公开容器中运行的服务，建议让容器使用主机网络，而不是桥接网络。这主要是因为桥接网络由于虚拟以太网(vEth)网络连接而导致延迟。当容器使用主机网络时，端口号冲突可能是一个问题。为了解决这个问题，容器中的应用服务被配置为在运行时提供的动态端口上运行，而不是在默认端口上运行。例如，在为 Java 应用程序运行 Tomcat 容器时，可以在运行时使用操作系统(OS)环境变量提供服务器和 Apache JServ 协议(AJP)端口号。

```
docker run  -d  -e  SERVER_HTTP_PORT=8080  -e  SERVER_AJP_PORT=8005  tomcat:8

```

环境(ENV)变量**服务器 _ HTTP _ 端口**和**服务器 _ AJP _ 端口**被用作参考，因为 Tomcat 镜像被修改为在定义的服务器端口上运行 Tomcat 服务器。这将防止容器绑定到主机上的一致端口，并允许容器的多个实例同时在同一主机上运行同一映像。

主机网络还防止 **iptables** 的不断变化，这在桥接网络中是常见的。您不希望在 iptables 可用于防火墙配置的生产环境中进行这种更改。桥接网络通常用在开发和测试环境中，以允许同一种类的多个并发容器在一组共享主机上运行。端口映射是允许终端用户访问桥接容器的方式。

[cyclone slider id = " ebook-4-赞助商"]

像 [Kubernetes](/category/kubernetes/) 这样的容器编排平台也为共享相同 IP 地址的容器网络提供 pod 模型。这对于将通常一起工作的容器中的应用程序服务分组很有用。

Docker 的特点是覆盖网络，可以轻松创建支持每个容器的互联网协议(IP)的多主机网络。其他解决方案，如 Calico、法兰绒和 Weave，可以作为网络插件与 Docker 集成。这个领域正在快速发展，因此建议在将这些技术应用到生产中之前，先测试它们的性能和可靠性。

### 服务发现和容器联网

服务发现通常是一个基础设施问题；它允许部署为容器的应用程序通过域名系统(DNS)透明地相互访问。如果容器部署在生产中的主机网络上，那么必须存在一个代理，可以将传入的请求路由到容器。以前，基于 Consul 和 Registrator 的服务发现解决方案是可发现容器的一种简单设置机制。

得益于覆盖网络和一系列第三方插件(如 Calico 和 Weave)的引入，这种情况已经发生了变化。实施需要使用键值存储来协调主机之间的网络更新。在一些解决方案中，DNS 被用作服务发现的基础。然而，DNS 有其自身的缺陷，因为在容器频繁改变或跨主机移动的情况下，本地缓存可能会影响发现过程。其他解决方案包括服务，如 [HAProxy](http://www.haproxy.org/) 或 [Traefik](https://traefik.io/) ，它们可以作为不同编排后端的反向代理。

基于端口的服务发现通常很难使用，但适用于应用程序最少的小规模集群。在使用代理配置进行发现的同时管理端口的生命周期可能会失控，并且难以调试。如果您选择集成允许每个容器 IP 的网络模式，请使用集成到网络提供商中的服务发现机制。这减少了解决方案中活动部件的数量，并简化了网络和服务发现之间的关系。

### 监控和可视化集装箱网络

当在生产中处理容器时，理解它们如何相互作用是很重要的。这对于帮助诊断问题和减少错误配置的机会至关重要。幸运的是，容器生态系统积极支持这一需求。例如， [Weave Scope](https://www.weave.works/products/weave-scope/) 提供了一个容器化的应用程序在一组给定主机上的互连概况。这对于理解容器如何相互通信以及如何与其他未包含的服务通信至关重要。容器本地监控工具，如 [Sysdig](http://www.sysdig.org/) ，提供了跨容器实例的实时流量移动视图。当集装箱数量增加且单个集装箱监控变得困难时，可以将它们组合在一起。

集装箱网络中的监控和性能管理是 Docker 和集装箱生态系统系列的下一本书也是最后一本书的主要主题，*用 Docker 和集装箱进行监控&管理*。我们将更深入地讨论这个话题，因为监控空间本身是复杂的，并且对于显示容器在生产中的价值极其重要。

### 隔离网络

当在共享基础设施上运行属于不同租户的多个服务时，需要创建隔离来保护相关容器之间的网络连接。Docker 通过用户定义的网络满足了这一需求。这意味着同一个租户上的容器通过一个独立于其他租户的网络连接在一起。Docker 还提供跨越多台主机的覆盖网络。可以有任意数量的覆盖网络，每个覆盖网络理想地用于相关的容器。

## 集装箱储存

对于大多数组织来说，容器已经成为连续交付(CD)故事的重要组成部分。而且容器是微服务最好的包装手段。在生产环境中运行容器需要提取文件系统变更层，并将它们一层一层地堆积到容器中——这是 Docker 流行的容器运行时中常用的模式。

一些采用者将其应用程序打包成容器，但仍然依赖本地容器存储，或者具有某种形式的主机挂载卷。虽然这在小范围内有效，但当它扩展到数十、数百或数千台主机时，这种做法很快就会失去动力。因此，不足为奇的是，大多数容器倡导者建议远离短暂的容器存储，将状态转移到容器之外。

轻量级内核在过去几年中已经出现，专门为应用程序的需求而构建。这种增长是因为轻量级容器映像有助于更快的部署，从而为开发人员带来快速的反馈循环。在生产环境中运行容器的团队经常发现他们自己在做日常工作，这需要从新映像版本的持续部署中清除旧的容器卷。定期清理活动可确保主机永远不会耗尽存储空间，并优化文件系统驱动程序。

与网络类似，我们想在采用容器存储之前先了解一些需要回答的关键问题:

*   如何为给定的部署案例选择正确的文件系统驱动程序？
*   如何为容器选择合适的持久存储后端？
*   如何缩小容器图像的尺寸？
*   如何淘汰旧的容器来控制文件系统？

### 解决文件系统驱动程序问题

许多驱动程序可以和 Docker 一起使用。高级多层统一文件系统( [AUFS](https://docs.docker.com/engine/userguide/storagedriver/aufs-driver/) )很常见；它很稳定，并在部署中取得了成功。AUFS 装载非常快，对于小文件，它提供了本机读写速度。但是，它可能会导致大型写入操作延迟，这主要是因为它的设计。对于大文件，最好使用 Docker 的[数据卷](https://docs.docker.com/engine/tutorials/dockervolumes/)。

OverlayFS 是一个相对较新的驱动程序，与 AUFS 相比提供了更快的读写速度；然而，在进入生产环境之前对其进行一段时间的测试是很重要的，这主要是因为它在 Linux 内核中是新出现的。Docker 提供 OverlayFS 作为驱动程序，容器运行时 rkt 也在新的 Linux 内核中使用它。

如果您选择使用设备映射器，并且在一台主机上运行多个容器，则最好对数据和元数据使用真实数据块设备。

### 容器的持久存储

容器化应用程序的理想情况是让它的状态完全在其执行领域之外进行管理；这意味着容器利用外部数据源来满足其所有状态需求。但是，您可以将有状态服务作为容器运行。在这种情况下，您可以选择使用容器管理的卷，或者将目录从主机装载到容器。你也可以使用 Docker volume 插件，比如 [Flocker](https://clusterhq.com/flocker/introduction/) ，从而允许容器访问共享存储。利用插件使得容器在访问持久块存储的同时使用多个主机变得更加容易。

也可以构建纯数据容器。但是，现在不鼓励在生产环境中使用这种做法，因为命名卷提供了更好的卷管理，以及使用其他[驱动程序](https://docs.docker.com/engine/extend/plugins_volume/)进行卷存储的能力。在确定要使用的正确数据容器时，纯数据容器可能会产生问题，如果您的生产环境中有多个数据容器，这就会成为问题。

主机管理卷的问题之一是权限冲突问题。当容器化的应用程序访问主机上具有不同所有权特权的文件时，会产生问题。然后，您需要更改主机管理的文件的所有权，以匹配容器内的操作用户。如果通过添加来自不同来源的新文件来更改共享主机卷，这可能会很难管理。

更好的做法是检查容器化应用程序上下文之外的持久性数据存储更改的频率。如果持久性存储完全由容器管理，这意味着所有文件都由容器化的应用程序创建和更改，那么使用命名卷是明智的。如果对持久数据存储的更改也是在容器外部进行的，那么最好使用使用主机装载的存储的数据卷。在这种情况下，冲突的文件权限可能会带来挑战。因此，在容器内部的应用程序访问文件权限之前，需要更改它们。

### 容器图像的大小

一般的经验法则是保持容器图像尽可能小。这有助于减少容器主机从存储库中提取图像时必须获取的数据量。缓解容器映像过度膨胀问题的一种方法是避免安装不必要的包，尤其是通过容器内部构建的包管理器。对于使用写时复制(COW)机制的容器运行时，创建 Dockerfiles 的这一原则也有助于创建轻量级映像。通过将运行命令组合成一行，并在构建容器图像时使它们作为一个层可用，避免不必要的层(这会增加容器图像的大小)。

当使用像 Alpine for Docker 这样的轻量级基础映像时，您需要确保它们符合 [apk 包管理器](https://github.com/gliderlabs/docker-alpine/blob/master/docs/usage.md)，这些包的名称可能与通过像 [Apt](https://wiki.debian.org/Apt) 这样的流行包管理器获得的包名称不同。

### 淘汰旧的容器映像、卷和实例

部署容器时的一个常见问题是在运行不同的容器及其关联卷时耗尽磁盘空间。大多数主机管理机制需要注意已经存在一段时间并且不需要在主机上的旧容器映像。如果您的连续交付管道一直是活跃的，在生产中每天产生数十或数百个变更，那么旧图像很可能会堆积起来。删除未使用的容器映像是容器运行时工具提供的一种策略。像 Docker 这样的容器运行时可以防止在删除容器实例时删除容器卷。

然而，通常是清理过程造成了最大的混乱。数据容器的行为类似于普通容器，在执行清理活动时可能会被错误地标记为删除。移动到命名卷容器可以防止与普通应用程序容器混淆。至于实际的命名卷，容器的移除不会影响命名卷，因此命名卷可以在多个容器的生命周期中重用。

## 集装箱安全

当容器开始流行时，一个主要的问题是容器是否安全。当考虑是否在运行不同租户的共享主机上使用容器时，这个问题变得更加突出。有了容器运行时中现在可用的粒度权限模型，以及隔离的用户、网络和进程名称空间，容器的安全性已经大大稳定了。然而，仍有一些争论和关注的领域。允许容器使用像证书或访问密钥这样的秘密仍然存在争议。

安全问题也影响集装箱存储和网络的实施方式。漏洞扫描和签名容器映像正在成为开发人员中众所周知的做法。像 Docker's Hub and Store 这样的容器市场已经实现了其中的一些实践，这有利于那些对这些问题了解有限或没有了解的用户。

在考虑生产环境中容器部署的安全性时，需要回答以下一些关键问题:

*   如何将关键的安全补丁传播到生产环境中的容器映像？
*   如何验证从外部来源获得的容器图像？
*   在将容器映像部署到生产环境之前，如何对其进行验证？
*   如何允许容器访问安全密钥和凭证，而不将它们暴露给主机或其他位于同一位置的容器？
*   如何防止受损的容器干扰主机或其他位于同一位置的容器？
*   如何测试安全的容器部署？

### 将安全补丁集成到容器基础映像

容器化的应用程序由一个基础映像和应用程序级别的更改组成，这些更改随后被放入最终映像中进行部署。通常，基础映像是不太容易更改的映像，而应用程序的更改是通过持续集成不断进行的。当以对操作环境进行修补的形式提出安全更改时，该更改会传递到基本映像。

使用计划的更改重新构建基础映像，然后将其用作新的基础映像来重新构建应用程序容器。在所有环境中保持一致的映像非常重要。基础映像中的更改与任何其他更改一样，通过连续交付管道传递到生产环境中。

### 可信容器映像和部署

Docker 从 1.8 版本开始引入了[内容信任](https://blog.docker.com/2015/08/content-trust-docker-1-8/)。在将图像推送到注册中心之前，它使用开发者或发行者的私钥对图像进行签名。当获取相同的图像时，使用开发者的公钥进行验证。这种机制可以集成到持续集成和部署管道中。Docker 还提供一个名为 [Docker Trusted Registry](https://docs.docker.com/docker-trusted-registry/) 的企业级图像存储解决方案。CoreOS 的 rkt 还提供可信的构建和部署，可以配置为从本地存储或远程元数据存储获取密钥。

### 从容器中访问机密

机密包括您不希望泄露给未授权代理但容器访问外部资源所需的任何信息。注入这些秘密的常见方法是使用环境变量或者将它们捆绑在构建清单中。

这两种方法都有内在的缺陷，会将秘密暴露给未经授权的代理。在需要密钥的 AWS 上部署容器可以[利用身份和访问管理(IAM)角色](https://blogs.aws.amazon.com/security/post/Tx2B3QUWAA7KOU/How-to-Manage-Secrets-for-Amazon-EC2-Container-Service-Based-Applications-by-Usi)而不是不安全地传递密钥。Shopify 的 [EJSON](https://github.com/Shopify/ejson) 库允许您加密秘密信息，这些信息可以提交给源代码库。来自 Square 的 [Keywhiz](https://square.github.io/keywhiz/) 和来自 HashiCorp 的 [Vault](https://github.com/hashicorp/vault) 也充当键值商店。

### 分离受损容器

受损的容器可能会解除容器主机的防护。解决这个问题的一种方法是启用 [SELinux](https://en.wikipedia.org/wiki/Security-Enhanced_Linux) 和 [SVirt](http://selinuxproject.org/page/SVirt) 。SVirt 与 Docker 一起禁止容器进程访问主机系统。一个[明细账户](http://www.projectatomic.io/docs/docker-and-selinux/)已经被项目原子共享。

[cyclone slider id = " ebook-4-赞助商"]

CoreOS 还将 SVirt 与 rkt 运行时集成在一起；默认情况下，每当新容器运行时，它都可用。如果开发人员未经检查就使用来自公共网站的不受信任的容器图像，这一点尤其重要。或者，对于 Docker，标志**–cap-drop**允许从给定的容器中撤销权限。

### 安全容器部署

Docker Bench 程序提供了一个自动化的工具，可以检查互联网安全中心(CIS)基准 v1.11 报告中提倡的所有最佳实践。这将有助于在将服务投入生产之前确定基础架构中需要关注的热点。另一个重要步骤是拥有一个安全的容器主机。Docker 安全部署指南是增强 Docker 容器运行时环境的好资源。

## 摘要

对许多人来说，成功采用容器是一项艰巨的任务。如果不大量考虑容器联网、存储和安全性，在生产环境中采用容器是不可能的。随着越来越多的组织实践这一艺术，新的模式和实践将会出现，使得容器部署成为未来构建的任何应用程序的事实。目标是重新思考当生产中的集装箱数量增加时，安全、存储和网络将如何发展，而不仅仅是运行几十或几百个节点，而是同时运行几千个节点。

CoreOS 、 [Docker](https://www.mirantis.com/software/docker/kubernetes/) 、 [Sysdig](https://sysdig.com/) 和 [Weaveworks](https://www.weave.works/) 是新栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>