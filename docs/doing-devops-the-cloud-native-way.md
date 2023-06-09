# 以云原生方式进行开发

> 原文：<https://thenewstack.io/cloud-native/doing-devops-the-cloud-native-way/>

这篇文章是由 [CloudBees](https://www.cloudbees.com/) 赞助的系列文章的一部分，探索“云原生开发应用”的新概念。

云原生 DevOps 不是我们都需要在它像热带风暴一样席卷我们之前拥抱和体现的某种趋势或方法。DevOps 是关于人们以及他们如何一起工作的。云原生技术改变了人们的工作方式。因此，我们将云原生 DevOps 作为一种现象来观察不仅是恰当的，而且是重要的。

## 效率潜力

在 2016 年 6 月的一次公共部门峰会上，[亚马逊网络服务解决方案架构师 Alex Corley 介绍了云原生 DevOps](https://www.youtube.com/watch?v=p7FF3ZObth0) 的想法，将其与他所描述的持续业务改进的理念联系起来。科利解释说，这个概念本质上是多余的，没有一家企业真正做到了自我改进。

“这不仅仅是技术问题。这是关于商业和人，”科利告诉与会者。“对我来说，这是 DevOps 的本质:我们都在参与能够持续改善业务所有功能的活动，并让所有员工参与进来。你会听到打破孤岛、整合业务——这种理念……通过改进标准化的活动和流程，我们可以变得更加高效并减少浪费。”

AWS 开发人员继续说，一旦摆脱了传统的内部系统管理的限制，这个概念的云原生特性对企业来说变得更加实用。理论上，这些“无差别的繁重”工作过程中的大部分可以自动化，以加快它们。但他断言，云原生开发推进了它们可能被完全消除的概念。

通过改变开发团队做什么和运营团队做什么的定义，这种消除反过来会从根本上转变开发运维的需求。

Corley 的云原生 DevOps 的表现可能只适用于一个组织的 IT 武库的云原生部分，尽管该武库也将包含其*无服务器*功能。在与新堆栈的对话中， [DXC Technology](http://www.dxc.technology/) 的应用服务首席技术官 [JP Morgenthal](https://www.linkedin.com/in/jpmorgenthal/) 将云原生开发操作系统和无服务器交付描述为捆绑在一起。他指出，当有人提到其中一个时，她也包括另一个。

“实际上，你现在谈论的是一个处理发布管理、生命周期管理、遥测、仪器和组件安全的平台，”Morgenthal 说。“它实际上是一个 PaaS[*平台即服务*]，但更重要的是，无服务器的整个理想是，我不必担心它在哪里运行。我不担心运行在该平台上的应用程序的可伸缩性。经济情况是，我只为函数执行时非常有限的时间跨度付费。这是一种与我们过去所做的非常不同的计算模式，坦率地说，我为什么还要去投资至少数十万美元来建立所有的基础架构来做同样的事情呢？”

Morgenthal 认为维护内部基础设施的行为是一种“无差别的繁重工作”，亚马逊的 Corley 很可能会同意这一点。科利对这个短语的使用可以追溯到 2006 年，当时[亚马逊首席执行官杰夫·贝索斯在一次奥赖利会议上首次为他的公司的云计算](https://blog.fugue.co/2017-08-30-fugue-reduces-undifferentiated-heavy-lifting.html)概念辩护。当时，贝佐斯估计，组织在实际执行其想法的核心愿景方面所花费的工作量约为 30%。

亚马逊将其云平台描述为无差别繁忙工作的终极根除者。从亚马逊的角度来看，利用公共云作为自动化工具，为组织提供了一种基础修复——提升其基础设施，清理贝佐斯所谓的“垃圾”，并将其转移到单一的外包平台上，供组织中的每个人使用。Capital One 的开发人员 Kapil Thangavelu，[在 2017 年*的新堆栈制造商*播客](https://thenewstack.io/going-serverless-doesnt-mean-no-ops/)中表示，无服务器架构——以及推而广之的云原生性——并不是指消除甚至减少 IT 运营商，而是指专注于“一个公共基础平台”

从这个角度来看，有人可能会说，为了使 DevOps 平台完全有效，它实际上*必须*是云原生的——它应该在一个从一开始就可供所有人访问的环境中构建和定位，而不是由任何一个部门的筒仓或独家监管。

## 包装困境

在 2016 年 10 月的一次网络研讨会上，[凯捷高级技术架构师 Les Frost 提出了一个论点](https://www.youtube.com/watch?v=zONF9zu9iYo),该论点可归结为:更广泛的 DevOps 概念不能被组织逐渐接受。要么一口吞下，要么干脆不吃。因此，维护组织的 DevOps 自动化的平台需要是一个完整的单一机制——“盒子中的 DevOps”

因此，弗罗斯特认为，整个事情可能是浪费时间。

"如果你在接下来的三年里实施 DevOps，你真的会过时吗？"弗罗斯特反问道。“因为当你专注于开发运维时，有一大批公司将会扰乱市场。我们都知道这些干扰因素…所以你必须问自己，我们是应该把时间花在开发运维上，还是应该把时间花在尽快实现业务关键型功能上？”

弗罗斯特肯定是在倡导一种反直觉的想法。Frost 继续将微服务作为一种技术的例子，这种技术解决了在更短、更容易实现、更容易测试的迭代中产生业务功能的关键需求。“IT 市场上发生的这些事情都是为了快速地把东西拿出来，”他说。“人们想尽快把东西拿出来的原因是，如果你不这么做，还有其他人会很快拿出来。因此，在这个市场上，把所有时间都花在开发运维上是正确的吗？”

由于微服务架构是一种在更短周期内加速软件交付的手段，他们会告诉你，[它实际上是 DevOps](https://thenewstack.io/containers-microservices-two-peas-devops-pod/) 的一种实现。正如新堆栈的 [Alex Handy 在 2018 年 4 月](https://thenewstack.io/devops-is-the-secret-ingredient-to-make-microservices-cook/)所写的那样，“在微服务世界中……通常开发人员的职责是建立构建大规模环境所需的所有基础设施。这意味着 Web 应用服务器、注册中心和存储库、操作系统和容器映像、虚拟化网络、防火墙、负载平衡器、消息队列和反向代理。"

这个清单听起来危险地接近于一些人称之为“无差别举重”的处方。这也是凯捷反驳的核心:软件开发正朝着几乎完全基于*意图*产生功能或服务的能力发展，而不考虑其基础设施的要求。这种方法从设计上来说，就是多开发，少运营。事实上，可能正是底层功能的分离使得无服务器方法，以及某种程度上的微服务方法变得有价值和可行。反对者问道，为什么要花费时间和精力去整合不再相关的任务呢？

如果我们将这种思路发挥到极致，微服务方法的一个危险是，它可能会从开发人员的独特角度构建企业软件的整个场景。由于云原生平台是面向开发人员的利益进行营销的，因此，至少，运营专业人员可能会感到被冷落。在最大程度上，他们可能*被*排除在外。

CloudBees Jenkins 社区布道者 r·泰勒·克罗伊在接受 New Stack 采访时表示:“作为一名软件开发人员，最美妙的事情是，我所接触的一切都可以通过某种形式或时尚的代码来控制。”“从运营的角度来看，情况并非如此。

“在传统的数据中心环境中，”克罗伊继续说道，“我没有一个 API 来为一架戴尔机器提供新的采购订单；我必须经历手动流程，填写电子表格，然后必须有人来装架、烧录、调配，然后我才能使用这部分基础架构。从操作员的角度来看，他们认为我必须将实际的、人类的、真实世界的手动流程与我的自动化相结合。开发人员倾向于将一切都视为软件，因此他们可以将一切自动化。”

开发人员自动化一切并不是 DevOps 的重点。如果云原生平台将自动化提升为代码，那么它可能会使开发人员完全自动化某些操作员角色。

## 选举指挥

CloudBees 的克罗伊认为，一个组织的整体商业模式必须不仅包括日常业务功能的自动化，还包括由执行这些功能的人类产生的创意的创造和培育。任何云原生 DevOps 平台都必须包括创意，如果它的目的确实是让创意在云中扎根的话。因此，人们设计创意和创新的能力不仅能保住他们的工作，还能让他们进入一个更紧密的循环。

克罗伊说，历史上的业务流程工程师要么没有理解，要么选择避免提及的是，许多想法都是糟糕的。相对而言，很少真正成熟到部署阶段。然而，这正是敏捷等商业方法论试图考虑的:好的产品和服务往往是在坏想法的框架下发展起来的。只是在实施过程中，很多想法可能会被认为是糟糕的。

他接着说，对于一个 DevOps 平台来说，要实现其从业者所宣称的鼓励创新的目标，它必须为失败提供支持。这并不是说它应该从开发树中删除失败的过程，而是暂停当前失败的过程的开发，直到情况发生变化，一个或多个坏主意可能汇聚成或催化成一个好主意。

但是在这个上下文中，我们所说的“平台”是指单一的应用程序吗，就像古代(20 世纪 90 年代)的业务流程管理(BPM)环境一样？或者通过插件和 API 接口的多种工具——套用一句话，一种*栈*？

“我认为这个问题必须通过多种工具协同工作来解决，”克罗伊回应道。“当我们遇到工具的宗教归属问题，或者对一种方法的欣赏超过另一种方法的问题时，我认为确实需要一个*指挥*……一个很难公正回答的大问题是，整个问题陈述——“问题确定”到“问题解决”——应该在哪里建模？管弦乐队的指挥是谁？”

这听起来像是一个经典的问题，即哪个工具位于生态系统的中心——这是最近几个月关于 Docker 经常被问到的问题，而且不是以一种好的方式。当然，不同的开源厂商会同意不同意哪个工具扮演指挥的角色。然而，即使指挥的角色仍然由每个组织为自己指定，但该指挥是否是“云原生的”又有什么关系呢

“我认为这无关紧要，”他回答说。“我现在可以坦然地说:现在世界上没有一个成功的企业不以某种形式依赖云原生技术……对我来说，那艘船已经启航了。从企业的角度来看，我认为拥有一切的想法已经过时了。”

如果“云”已经发展成为数字功能的虚拟舞台，包含将虚拟化提升到同一水平的所有基础架构，那么对于 DevOps 来说，“云原生”可能已经与社会“世界原生”一样有意义。就在我们检查这个想法的时候，它已经变得过时了。当然，这正是凯捷(Capgemini)的莱斯弗罗斯特(Les Frost)所警告的结果。

标题图片旧金山金门大桥建设的第一周，大约 1934 年，来自美国国会图书馆，公共领域。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>