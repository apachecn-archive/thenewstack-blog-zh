# 当网络规模不够时:电信领域的容器

> 原文：<https://thenewstack.io/web-scale-isnt-enough-containers-telecommunications-space/>

Docker 容器是一个扩展问题的解决方案:Web 服务工作负载，尤其是微服务，不能以传统方式扩展。容器提供了一个更简单的、可商品化的解决方案，包括隔离这些工作负载中的功能、扩展这些隔离的单元，以及经常重组底层网络以适应新的规模。

然而，有一组具有如此大的工作负载的系统，其中容器仍然必须被定制以适应基于因特网的电信的需求。

## 行动呼吁

位于阿拉巴马州亨茨维尔的 [Digium](https://www.digium.com/company) 生产基于软件的电信系统，如 VoIP 交换和统一通信(UC)控制台，基于一个名为 Asterisk 的开源会话发起平台(SIP)。就像 Docker Inc .成为现在标准化集装箱化平台的商业冠军一样，Digium 也是 Asterisk 公认的冠军。

在去年 10 月于[举行的 AstriCon](https://www.youtube.com/watch?v=532_DP68jEE)AstriCon 用户大会上，Digium 的主要合作伙伴之一、名为 Avoxi 的呼叫中心平台提供商的两名工程师向 Docker 介绍了开发人员，其中一些人是第一次接触。工程产品开发总监叶小开·麦德森和首席技术官达伦·塞申斯[*如上图，从左至右*]在其他开源项目的背景下展示了容器平台，我们在这里也没有过多谈论这些项目，如 [Kamailio](https://www.kamailio.org/w/) 、 [Calico](https://github.com/catid/calico) 和 [Sippy](http://www.sippysoft.com/) 。

这些是电信世界中一个新堆栈的元素，这个堆栈正在以 Docker 改造 Web 服务的方式改造电信行业和电信公司。但这是一个不同的堆栈，在 AstriCon，Sessions 和 Madsen 解释了为什么在解释关系数据库呈现的难题时，使用创建 Hadoop 的人首次向世界展示的那种图表。

Docker 不能扩展…至少，如果要处理 VoIP 流量，容器化平台不需要扩展。塞申斯和麦德森正在研究一个解决方案，这让人想起了十年前改变世界的那些 Hadoop 人。

“当我们谈论所有这些令人兴奋的新技术时，我们必须记住，这些技术是为网络规模而构建的，”塞申斯非常坦率地说。他的意思不是“网络规模”，就像营销人员倾向于把它设计成好像网络是有史以来最大的东西，比洛克希德-马丁公司的 C5M 大，比唐纳德·特朗普的自负大，比斯科特·富尔顿的一堆手写笔记大。

他的意思是网络规模“太小了”

“这只是意味着这些项目是专门为扩展 Web 服务而设计的，”CTO 解释道。“当我们谈论在那个领域之外使用应用程序时，如何配置这些 Web 扩展技术来支持这些非基于 Web 的应用程序的动态发生了巨大的变化。”

如你所见，网络是被设计成在一个共同的背景下扩展事物的。统一资源定位器被设计成通过服务器指向客户迫切需要的东西。超文本最初被认为是一种由文本、词汇上下文组成的思想网。

当它转变为一个函数网络时，URL 仍然有意义，因为应用程序中的函数仍然共享公共上下文。但是语境是一个不适用于流量的维度。

交通流量是一种不同的野兽。虽然 Docker 容器对于一个单位的通信量来说似乎是一个极好的载体，但是在其上交换 Docker 容器的网络却不是。

“在生产环境中，如果不做大量的工作，几乎不可能将 Asterisk 与这些平台一起开箱即用，”Sessions 说

![[SCM]actwin,0,0,0,0;Zoom Player zplayer 1/28/2016 , 4:20:32 PM](img/3430cb8437b7d4dd0ce477e3532dd1a1.png)

“当我们谈到扩展和 Docker 容器时，”他继续说道，“网络也是一个非常重要的考虑因素。网络容器并不像你想象的那么简单。Docker 最初设想解决的问题是扩展 Web 服务的问题。最后，Docker，CoreOS，和很多这些非常酷的网络规模的项目，在解决网络规模的问题上有很多偏见。对我们来说，明显的问题是我们是 VoIP 用户。”

## 另一个维度

从世纪之交开始，就有了开源的 SIP 路由器项目。多年来，知识产权持有者已经迫使这些项目的管理者改变他们的名字。今天，最初项目的两个主要分支是 [OpenSIPS](http://www.opensips.org/) 和 [Kamailio](https://www.kamailio.org/w/) (一个夏威夷单词，发音为“ka-ma-ee-li-o”)。与此同时，[星号](http://www.asterisk.org/)是一个电话引擎，它的工作负载单元不是一个函数或记录，而是一个*调用*。

更具体地说，在电话技术中，呼叫被认为是*信号*的协调会话。Kamailio 设计用于处理信号，它从客户端抽象出 IP 网络的复杂性，而不是以电话专家所期望的方式处理信号。

当基于互联网(基于 IP)的网络处理电话呼叫的概念首次提出时，那些反对者引用了电话的实时性，并指出 IP 分组被设计成无序接收，然后重组——他们说这一过程将花费太长时间。在此期间，网速加快到如此程度，以至于等待时间缩短到可以忽略不计的程度。

但那是在 SIP 被认为是传送会议流量的媒介之前。如果你了解电话的本质，你就知道它是双向的。在有线电路上，会议是通过将几个双向会话交叉到一个集线器来处理的。对于 SIP 会话，您需要一个会议服务器。这种服务器的引入增加了基于 IP 的连接的复杂性，因为会话中的每一方在实际交换流量之前都要与另一方协商连接的参数。

Kamailio 是一种 SIP 服务器，设计用于执行基于 IP 的呼叫促进者的主要角色。这就是你开始对这份工作的重量产生一些同情的地方。在电路交换电话时代，位置是固定的。当有人打电话时，系统知道是哪部电话在打电话。互联网协议被明确地设计成在从一个地方到另一个地方转发数据包时不关心这样的事情。

所以 SIP 必须建立一个代理服务器来假装代表客户，即使它并不真正关心客户的情况(有点像离婚律师)。它处理通信量的交换，然后将适当的反馈过滤到客户端，给客户端一种通信的错觉。

将这一过程乘以至少十几个数量级，你就会知道互联网现在在处理语音流量时必须处理什么。

## 重新缩放

Avoxi 对扩展 Asterisk 流量问题的解决方案是双重的。随着呼叫流量的增加，它不能简单地增加包含 Asterisk 服务器的容器的数量，除非成倍增加处理所有同时连接的 SIP 代理的级别。

![[SCM]actwin,0,0,0,0;Zoom Playerzplayer1/28/2016 , 4:21:37 PM](img/40db807bdc317a1a706b1b875b87e8dc.png)

因此，Madsen、Sessions 和他们的团队创建了另一个代理层，专门管理代表呼叫处理逻辑的 Asterisk APIs(称为 ARI)。消息总线可以位于 ARI 层的前面，以协调来自任意数量的缓存的调用，并且正是这些缓存可以随着流量的增加而增加。

然而，这并不一定意味着 Asterisk 服务器的数量必须增加。它的可伸缩性可以由 ARI 代理层和服务器之间的过程调用流来决定。

对于标准的面向 Docker 的网络，每个容器在主机网络上都有自己的 IP 端口，通常与某种类型的代理或负载平衡器结合在一起。典型的网络地址转换(NAT)使得容器在同一网络上大规模表示呼叫处理是不可行的。

所以在星号层，Avoxi 用 CoreOS 的法兰绒取代了典型的 Docker 网络方案。这创建了一种虚拟网络，其中每个容器被分配一个/24 子网上的专用 IP 地址，而不是端口号。然后，它应用 CoreOS 的构造 Calico(T4)作为虚拟基础设施平台，以便容器环境可以与 Kubernetes 兼容，同时将容器网络与基于云的网络集成，而不需要另一个覆盖。

一位 AstriCon 参与者问道，在这样一个环境中有这么多星号容器，系统如何跟踪所有 SIP 端点的位置？

Avoxi 的 Madsen 解释说，Kamailio 充当所有 SIP 客户联系的分发点。“那么你的集装箱网络对外界来说确实是隐藏的。实际上不知道容器网络在外部，所以来自代理的调用分布在内部网络中。这就是为什么您需要一个覆盖网络或类似 Calico 的东西，这样您就可以移动 NAT 方面，因为默认情况下，Docker 会尝试对容器使用 NAT——如果您运行 Apache 或 NGINX，这很好，但使用 Asterisk，您会希望避免这种情况。”

Madsen 说，后端网络——拥有所有星号服务器的网络——可以保持传统的容器网络。然后，Kamailio 将另一端的端点视为传统的虚拟化网络。

Avoxi 的工程师意识到，呼叫处理程序和管理呼叫处理程序的服务器必须分开扩展，它们之间的网络必须唯一地内插。但是，正如大数据的情况一样，只有当他们所面临的巨大工作量与他们对工作的看法不成比例时，他们才会意识到这一点。

他们重新定义了工作，并在这样做的过程中，改变了他们对规模和维度的概念。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>