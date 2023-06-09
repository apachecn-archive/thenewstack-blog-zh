# 红帽把 Linux 放在汽车的驾驶座上

> 原文：<https://thenewstack.io/red-hat-puts-linux-in-the-driving-seat-for-automobiles/>

开源企业软件提供商 Red Hat 在本周举行的年度用户大会 [Red Hat Virtual Summit](https://www.redhat.com/en/summit) 上表示，该公司打算推出一款专为汽车应用打造的 Red Hat Enterprise Linux (RHEL)版本。

目前，公告只是一个“交付意图”，该公司表示，它正在与专注于多个行业功能安全的 [exida](https://www.exida.com/) 公司合作，为汽车用例提供 RHEL 的精简版，该版本将“在其生命周期中提供持续更新，同时仍保留关键的功能安全认证，”根据新闻声明。

红帽公司首席技术官办公室的技术策略师[杰瑞德·弗洛伊德](https://www.linkedin.com/in/jeredfloyd)解释说，如今许多新车都装有 100 多个计算机系统，尽管其中许多计算机都是非常小的微控制器，具有特定的功能和专门为该目的开发的定制软件。这些控制器上的软件经过了广泛的安全审计，Floyd 说这些不是汽车版 RHEL 的目标。相反，Red Hat 专注于更加集成的系统，如信息娱乐控制台甚至高级驾驶辅助系统(ADAS)。

要在汽车应用中使用，建议的 Linux 发行版必须满足 [ISO 26262](https://www.iso.org/standard/43464.html) 中提出的要求，并通过功能安全认证，exida 是该认证的专家和认证机构。Floyd 说，到目前为止，还没有任何版本的 Linux 能满足这些要求，Red Hat 打算成为第一个。

“特别突出的一点是，许多汽车用例的要求之一是所谓的功能安全，这基本上是一种认证，”弗洛伊德说。“功能安全是构建软件的基本概念，以便在出现故障时，将伤害风险降至最低。”

> “像特斯拉这样的公司已经为未来的发展定下了基调，这也将是业内其他公司的期望。这需要像 Linux 这样的现代通用操作系统。”
> 
> —杰瑞德·弗洛伊德，红帽子

目前在车辆中使用的许多系统都满足这些要求，并且只经过一次认证，然后定期更新，通常是消费者去经销商处，在那里软件可以通过 USB 进行更新。Floyd 说，在这种情况下，重新认证软件以满足功能安全认证可能不会太麻烦，但对于持续更新的操作系统来说，这样做就太麻烦了。

“持续更新是区别于当前市场状况的一个优势，”Floyd 解释道。“当你回到现在汽车中的系统，或者有功能安全认证的系统时，功能安全认证过程通常从操作系统或特定软件的快照开始，然后如果你改变该软件，你将再次经历整个认证过程。对于需要持续安全更新的平台来说，这真的不太合适，在这种平台上，您有一辆联网的汽车，出于安全和功能的原因，它将接收软件更新。因此，我们与 exida 建立的流程的独特之处之一是，它将涵盖我们为 CVE 和安全漏洞提供更新的能力，同时保持功能安全认证。”

汽车工业现在正试图将许多独立的计算机整合在一起，部分是因为实用性和效率，部分是因为消费者的期望。

“像特斯拉这样的公司已经为未来的发展定下了基调，”弗洛伊德说，“这也将是业内其他公司的期望。这需要像 Linux 这样的现代通用操作系统。”

Red Hat 进入汽车软件世界的消息传出时，该公司正在继续其在边缘计算领域的努力。虽然这个汽车 Linux 发行版不会按照其在 edge 上的一些努力(包括最小化的 OpenShift 发行版)来运行 Kubernetes，但 Floyd 说，容器仍然是他们期望的软件打包交付方式。然而，Floyd 说，向汽车领域的推进可以扩展到其他行业，这些行业经常在边缘运营，并有类似的安全和认证要求。

“由于市场的规模和集中度，以及已经存在的广泛生态系统和对 Linux 功能安全性的兴趣，汽车对我们来说非常重要。功能安全也适用于许多其他垂直行业。因此，如果你看看工业 4.0 制造用例，例如，或机器人用例，至少有相同的功能安全要求。它们都映射到一个父标准，”弗洛伊德说。“制造业也有类似的映射，机器人学也有类似的映射，航空学也有类似的映射。因此，一旦我们建立了认证，就有可能将已经完成的工作应用于具有这些功能安全要求的平行行业。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>