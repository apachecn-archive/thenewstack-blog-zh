# 现代软件的复杂性从何而来？

> 原文：<https://thenewstack.io/where-is-the-complexity-of-modern-software-coming-from/>

上个月，基于传感器的分析平台 [Estimote](https://estimote.com/) 的社区经理 [Wojtek Borowicz](https://twitter.com/wojtekborowicz) ，将他的想法转向了一个及时的主题:现代软件的复杂性，以及它来自哪里。他在 Medium 上[发布了一个新的系列，共采访了八位杰出的开发人员](https://medium.com/computers-are-hard/computers-are-hard-ed82bccc5c87)，每一位都是不同领域的专家，“探索并解释为什么软件比看起来更复杂……”

“其中一些原因是技术性的，而另一些则源于人类的易错性以及软件开发学科如何承担这些失败的后果，”Borowicz 写道。涵盖了从依赖和加密到容器和监控系统的所有内容，每篇文章都是对我们现代基础设施中的复杂性链中的另一部分的权衡。

Borowicz 从操作和数据库工程师 [Charity Majors](https://twitter.com/mipsytipsy) 开始了他的探索，他是 [Honeycomb](https://www.honeycomb.io/) 的联合创始人兼首席技术官，该公司开发了一种用于“反思和询问”生产分布式系统的可观察性工具。梅杰斯指出“我们正处于这一巨大转变的中间，从整体服务到微服务，或者从一个到多个。您依赖于所有那些松散耦合、分布广泛的服务，而这些服务并不属于您，但您仍然要对自己的可用性负责。”

> “我们已经把所有东西都切成了小块，分散开来，现在有一百个失败点，而不是一个”——honeycomb . io 的慈善专业。

这次采访解决了“围绕着[软件崩溃的棘手问题，以及工程师如何解决 bug 和中断](https://medium.com/@wojtekborowicz/computers-are-hard-bugs-and-incidents-with-charity-majors-252813ae9ce8)”并以生动的介绍开始:“出现中断的最初几分钟是疯狂的。警报开始响起，支持票的数量激增，工程师和客户服务人员争先恐后地组建响应团队。《华盛顿邮报》评论道，“没有哪个行业如此习惯于其产品出现故障，以至于认为这是日常工作的一部分。”

梅杰斯指出，由于多个系统之间不可预测的相互作用，一些风险悄悄通过了我们的测试。“这个问题通常就像六件不可能的事情加在一起，”她说。“坐下来真正思考这些系统有多复杂是令人难以置信的。让我感到惊讶的不是事情失败了，而是事情或多或少地成功了。”

梅杰斯描述了一个问题，这个问题最终被追溯到一个只影响罗马尼亚东部一个路由器的错误。“你无法预测这种东西。你甚至不应该尝试。你只需要有仪器，并善于调试你的系统。你能做的就这么多。”

当 Borowicz 调查代码更改的频率时，Majors 说“你的系统是建立在另一个系统之上的，建立在另一个系统之上……所以可能是有人引入了你看不到也无法控制的更改。时机不重要。你应该假设变化实际上一直在发生。这是为风险做计划的唯一方法……”

后期专业甚至更进一步。“你应该在假设它一直在失败的情况下构建它，这基本上没问题。我们需要定义 SLO——服务水平目标，而不是过于纠结于失败……这是真正的解放。这是一个我们都同意的数字，因此它有可能缓解许多团队多年来的许多挫折。”

## 我们选择了复杂吗？

Borowicz 从 David Heinemeier Hansson 那里得到了不同的回应，他是 Ruby on Rails 的创始人和 Basecamp 项目管理软件的联合创始人。汉森认为，“你不必让复杂性压倒你。你选择。”

“如果您无法控制单一应用程序的复杂性，您又怎么会认为您有能力将这种复杂性分散到一系列服务中，这些服务现在必须交互并处理网络不可靠性、重试、两阶段提交和所有其他复杂性，而当您处理方法调用、参数和运行单一进程的基础时，这些复杂性根本不存在。在复杂程度上，对应用程序造成的损害比分发它要小得多。你可以解决哪怕是最小的问题，一旦你把它分发出去，它的复杂性就会增长一个数量级。”

在一次欢快的采访中，Hansson 给了这个 8 部分的系列一个哲学上的结尾，挑战了哪些内在的复杂性是——哪些不是——融入了我们当前的软件开发方法。“如果你要总结整个软件开发的努力，你会说:‘项目运行晚了，取消了’。策划工作可以说是行不通的。”

> “在我们找到超越光速的方法之前，你能做的最好的事情就是确保资产尽可能靠近最终用户。”— Cloudflare 的丽塔·科兹洛夫。

汉森仍然对敏捷开发的评估和现代实现持怀疑态度。“模糊的项目定义实际上更现实，”他说。“非常具体的项目定义通常很快就会误入歧途。足够模糊的定义为从事这项工作的人提供了创造性和选择性。”但是他似乎建议，通过仔细和深思熟虑地检查整个软件开发过程，可以降低一些复杂性。

“有一个 10x 程序员的神话。但这并不是那些在实现问题时表现英勇的程序员。10x 程序员是重述问题的程序员。

但似乎复杂性无处不在。Borowicz [与 Cloudflare 产品经理 Rita Kozlov](https://medium.com/@wojtekborowicz/computers-are-hard-networking-with-rita-kozlov-6bf251991083) 讨论网络。Kozlov 解释了实现健壮基础设施的几种方法，包括多云解决方案和主要及次要 DNS 提供商。“但最终它只是一堆黑在一起的电线。人们正在编写有错误的代码，就像任何人的代码一样。有时，对于停机，您无能为力。”

还讨论了我们的外围设备和[与 Linux 内核维护者 Greg Kroah-Hartman](https://medium.com/@wojtekborowicz/computers-are-hard-hardware-with-greg-kroah-hartman-4be2d31c3126) 的硬件集成挑战，他最终解释说，从某种意义上讲，它一直是软件。内核维护者在采访中说，“过去 10 年制造的任何外设都没有运行为其编写的软件的处理器，这是非常罕见的。”

## 没有终点线

安全软件工程师[安娜斯塔西娅·沃伊托娃](https://twitter.com/vixentael)在[讨论安全和加密问题](https://medium.com/@wojtekborowicz/computers-are-hard-security-and-cryptography-with-anastasiia-voitova-d55ce5c0855d)，警告说“不幸的是，这里没有终点线。没有迹象表明‘你好，你已经做了所有的事情，100%安全’。”

Voitova 指出，我们至少已经意识到我们的复杂性来自哪里。"有些公司的主要业务是密切关注依赖关系."但与此同时，我们也认识到我们的现代基础设施是有限的。“没有什么是无法穿透的。您可以保护您的应用程序免受最常见的威胁，但您无法保护它免受即将暴露的漏洞，比如说，下个月。”

该系列继续其现代软件开发的全景之旅，与微软的 web 开发框架 ASP.NET 的项目经理 Jeff Fritz 讨论性能软件工程，最终将他们引向虚拟机和容器。博罗维奇还[采访了一家无障碍设计公司](https://medium.com/@wojtekborowicz/computers-are-hard-accessibility-with-sina-bahram-a3ce25b1f7b7)的总裁 Sina Bahram。(“它需要融入整个产品开发生命周期，从构思一直到后期生产和维护。”)

博罗维奇甚至采访了比安卡·柏宁，她是一家名为道尔顿·马格的字体设计工作室的工程师/设计师/创意总监[。(“有一些书写系统，如阿拉伯语和梵文，其中字母的形状根据它们出现的上下文而变化。”)](https://medium.com/@wojtekborowicz/computers-are-hard-representing-alphabets-with-bianca-berning-bc8c9a498343)

最后，这似乎证明了博罗维奇系列采访的简单但无可辩驳的标题。归根结底——计算机很难。Hansson 认为，至少我们应该对我们期望交付开发时间精确估计的开发人员有一些同情。

“在大多数情况下，软件天生就是不可预测、不可知和不成形的。它几乎就像一种气体。”

* * *

# WebReduce

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>