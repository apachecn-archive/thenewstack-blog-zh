# 微软 Azure:像暂停视频一样停止和启动 Kubernetes 集群

> 原文：<https://thenewstack.io/microsoft-azure-stop-and-start-kubernetes-clusters-like-pausing-a-video/>

微软九月份发布的 Azure Kubernetes 服务包括一个有趣的新功能:你可以在不需要的时候停止集群，并在需要的时候重新启动——就像你可以停止虚拟机、暂停视频或让笔记本电脑休眠一样。将一个集群扩展到零仍然会让系统池运行(并产生账单)；关闭它会完全停止控制面板和代理节点，因此没有任何成本，但当您想要恢复群集时，不需要创建群集和重新安装映像。

新的 **az aks stop** 和 **az aks start** 命令是对客户转向云服务的方式的回应，以实现疫情对组织的数字化转型，以及他们需要的成本和效率，Kubernetes 联合创始人兼微软公司副总裁 [Brendan Burns](https://mobile.twitter.com/brendandburns) 告诉新堆栈。

AKS 团队注意到，许多客户在晚上或周末删除他们的代理节点虚拟机，以降低服务成本，但这意味着他们仍在为控制面板付费，而且取回群集并不总是简单的，特别是如果他们仍在试验他们的环境，还没有准备好自动化一切。

伯恩斯说:“很多都是 DevTest 或批处理工作负载，因为人们实际上不是一天 24 小时工作，如果你有一个 DevTest 集群，你实际上可以停止它。”“许多人在 CI/CD 中这样做，我们通过 API 帮助他们更轻松地做到这一点。您无需让他们编写脚本来删除和创建群集，就像您停止和启动虚拟机而不是删除和重新创建虚拟机一样，您可以停止群集，然后在以后重新启动它，并保留其中的所有状态和所有内容。”

这利用了 AKS 已经在备份集群状态以实现弹性的事实。“最终，Kubernetes 系统中的唯一状态实际上是 etcd 的内容；有缓存，但其他一切都是无状态的。因此，当您停止集群时，您将获取 etcd 数据库的状态，并将其保存到文件中。我们已经这样做了，因为我们备份了它以防万一，所以我们可以恢复它。这基本上是主动将该状态文件下推到存储中，然后关闭所有计算资源，因此您不会因使用任何计算资源而付费。”

再次启动集群会重新加载控制平面状态和相同数量的代理节点，尽管他警告说这不是即时的，所以您可能希望安排重新启动，以确保工作负载在您需要时准备好响应。

“当您启动群集时，您安装的所有内容都会立即弹出，尽管需要几秒钟才能开始运行。如果您想在几秒钟内为一个 web 请求提供服务，您将无法及时启动您的集群来做到这一点。但是假设你正在使用 KEDA 和事件驱动处理来对人们上传的视频文件进行转码；大多数时候，人们会在外出时上传视频，所以大多数人有八到十个小时在睡觉。因此，您可以在这段时间内停止您的群集，然后当第一次上传进来时，您可以启动您的群集，然后重新启动，您需要的一切都已经在那里了，这样它就会立即拾取文件，处理事件并进行代码转换。”

**启停**非常适合突发和批量场景，以及在工作日使用的工作负载，如呼叫中心和医生办公室。“我们与客户交谈过，他们知道在上午 9 点，应用程序将有 10，000 个同时用户，但在 8.55 点没有用户，或者最多有一两个用户。或者有一场体育赛事，你知道人们会在特定的时间收看。现在，您可以提前五分钟启动集群，并做好准备。”对于需要进行演示，但在下一次演示或培训之前不需要集群运行的人来说，它也是理想的选择。

**停止开始**功能目前在预览版中，需要 AKS-preview Azure CLI 扩展(0.4.64 版或更高版本):您还需要在订阅上启用 StartStopPreview 功能标志。如果您使用 [pod 中断预算](https://kubernetes.io/docs/concepts/workloads/pods/disruptions/)来确保您的应用程序保持高可用性，即使您需要频繁升级，Stop start 仍然可以工作，但它将需要更长时间来完成排空过程。但它甚至可以处理要求苛刻的工作负载；微软最有价值专业人员(MVP) [Mohammed Darab](https://twitter.com/mwdarab/status/1308598289336545280) 用大数据集群(运行在 Kubernetes 上的 SQL Server、Spark 和 HDFS 容器)进行了试验。

## **成熟的标志**

**开始停止**并不意味着回到创建雪花或者拥有你没有记录的配置。群集状态仅存储 12 个月，之后将无法恢复。但这是一种在没有太多干扰的情况下获得灵活性和便利性的方式。

“我们显然仍然建议人们仍然遵循 DevOps 实践，将基础设施作为代码来做，并且如果他们需要恢复它，仍然将所有这些东西放在某个地方，”Burns 指出。“但是，就像在需要时打开笔记本电脑会更容易、更方便一样，向上翻转[您的群集]会更方便。”

**Start stop** 是一个小小的便利，但它也反映了更成熟的 Kubernetes 用户群和更广泛的采用。“我们不再处于发烧友的空间，”伯恩斯指出。“我们处在这样一个空间，人们会因为它非常有用而使用它，会因为它易于使用而使用它。因此，我们将增加这些细节，因为我们不再处于人们会接受粗糙边缘的地方。”

图片由来自 Pixabay 的 AndyPandy 提供。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>