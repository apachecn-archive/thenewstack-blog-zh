# 华为推出基于 Kubernetes 的容器引擎

> 原文：<https://thenewstack.io/huawei-launches-kubernetes-based-container-engine/>

加入越来越多的公司，亚洲电信巨头华为技术公司发布了自己的容器编排引擎，云容器引擎(CCE)。

华为云计算首席架构师熊英在本周举行的北美 LinuxCon 大会上发布了 1.0 版本。

像来自 CoreOS 和 T2 的编排引擎一样，CCE 将基于谷歌开源的 Kubernetes 平台。

在他的演讲中，熊谈到了集装箱在中国日益增长的使用。2016 年，华为发现 14%的公司在生产中使用容器，另有 23%的公司在测试和开发中使用容器。大约 44%的人计划在未来六个月内采用集装箱技术。

虽然 14%仍然相当低，但增长速度很快。在过去的一年里上涨了 250%。“对我来说，这意味着工具正在成熟，”熊说。

在生产中使用容器的人中，大约 42%使用正式的编排工具，如 [Kubernetes](/category/kubernetes/) ，相比之下，51%的人使用脚本和其他自制工具。

熊说，在云时代，这种方法是不可扩展的。“我们希望看到更多的人使用容器编排工具，”熊说。

熊说，协调是将容器放置在服务器上，提供存储和网络，以及保持它们在所需状态下运行的过程。

虽然今天的编排以某种形式提供了这些功能，但还需要更多的功能来将编排器提升到行业水平。

调度器应该在预订系统上工作，并且使用服务级别协议动态地调度容器。“您告诉调度程序您对应用程序需要什么样的 SLA，调度程序应该计算出您需要多少资源。”

熊说，网络和存储也应该抽象，使它们像今天的计算能力一样容易配置。“如果我们能够自动扩展存储池并自动发现容器的存储服务，那就太好了，”他说。

在网络方面，“我们需要一种通用的方式来实时和按需传达网络策略。我们应该能够在网络资源上调度容器，因为有些应用程序更关心网络带宽和延迟，而不是 CPU 和内存。”

工程师 Lee Calcote 对本文有贡献。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>