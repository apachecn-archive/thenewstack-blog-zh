# 初创公司的开发者平台

> 原文：<https://thenewstack.io/developer-platforms-for-startups/>

随着关于[开发者控制平面](https://thenewstack.io/from-kubernetes-to-paas-to-developer-control-planes/)和集中式开发者平台的讨论在拥挤的云原生空间达到高潮，可以肯定地说，Kubernetes 开发者的平台可以驱动从好奇心到生产力的一切。

 [丹尼尔·布赖恩特

丹尼尔是大使实验室(前身为 Datawire)的开发者关系总监。Daniel 是一名 Java 拥护者和 TechBeacon DevOps 100 影响者，他为几个开源项目做出了贡献。](https://www.linkedin.com/in/danielbryantuk/) 

关于使用开发者平台来降低复杂性，似乎已经有了越来越多的共识——这导致了集中式平台，并由此带来了更集中的开发者体验。

虽然创业公司是通过平台简化的想法的最大支持者之一，但许多较小的组织对开发人员平台对他们的有效性或效率有疑问。

在大公司拥有无限资源和更大预算的情况下，大多数行业焦点都集中在大科技/FAANG(科技公司脸书、亚马逊、苹果、网飞和 Alphabet/谷歌)平台方法上。

那么，有预算意识的初创公司如何才能获得开发者平台的好处，而不必与大公司的投资竞争呢？

## 小型团队的开发者平台

2021 年，[美国非营利组织](https://www.youtube.com/watch?v=2mDakOMgITM) [UPchieve](https://upchieve.org/) 的首席技术官戴夫·苏迪亚，分享了开发者控制平面如何帮助他的小团队释放巨大成果的见解。他知道 UPchieve 的使命是通过为来自低收入社区的高中生提供免费的 24/7 在线辅导来实现学术支持的民主化，如果不简化流程，让他的团队能够快速迭代多个开发设置，这是无法实现的。

当时，UPchieve 有一个 3.5 人的工程团队，负责他们为 10，000 多名学生创建的“911 学术支持”网站。

Sudia 自己承认，在他使用 UPchieve 之前，他警告小团队不要使用 Kubernetes，主要是因为它的复杂性。但是，正如他所分享的，“Kubernetes 是开发工具中令人兴奋的事情发生的地方，”他意识到这可能是一种创造性创新和事半功倍的方法。

## 开发人员体验:围绕约束创建

作为一个主要依靠赠款运作的组织，UPchieve 采用了自助方法来支持长期业务战略。没有时间和资金可以烧钱。苏迪亚说，资源有限“创造了有趣的机会和约束，让你变得富有创造力”。

一种让开发人员在不破坏事物的情况下尽最大努力快速行动的热情最终导致 Sudia 沿着 Kubernetes 的道路前进——他并不孤单。许多初创公司已经发现，广阔的云原生工具前景创造了在交付和简化开发人员体验方面更加精益、敏捷和创新的机会。[也就是说，如果你对工具很小心的话，哪些领导者会在整个生态系统中出现](https://www.getambassador.io/resources/accelerating-kubernetes-for-cloud-native-organizations/)。

有了铺平的道路和正确的抽象，团队的规模就无关紧要了。根据 Sudia 的说法，“我不为工具本身而追逐工具，但我知道 Kubernetes 是我们能够以最小的足迹执行的地方。开发人员控制平面让我们可以做到这一点。我们有一个应用程序，一个整体，但我们有多个需要分开的环境。这影响到我们如何使用工具。我们需要保持我们的过程简单，对不对？我们需要强大的工具，但它们不能让我们停滞不前。”

开发人员控制平面作为一个稳定的出发点，开发人员可以不断地返回，因为它提供了一种清晰的、自以为是的工作方式，并从长远来看提高了效率和节省了时间。

## 工具节省的时间:在 API 网关上拥抱云原生

对于 Sudia 来说，工具是提高效率的地方。一个工具， [Ambassador Edge Stack (AES)，](https://www.getambassador.io/products/edge-stack/api-gateway/)从一开始就一直是 Sudia 自己的云原生生态系统的一部分，即使其他工具发生了变化。“AES 易于安装，而且运行正常。我可以毫无疑问地推荐它。当我试图为支持或高级功能付费时，比如在我的上一个组织，AES 很容易获得预算。”

Sudia 解释说:“我运行最少数量的高可用性实例。高峰时，我们每分钟收到大约 5000 个请求。这听起来是个很低的数字。但我喜欢说，‘我们有很大的上升空间。我们甚至没有触及我们能够处理的流量。此外，我为自己是一个只有三个人的提供端到端加密的小型工程团队而感到自豪。

“我们通过 Ambassador Edge 堆栈加密到我们的集群，然后从 Ambassador 到 Linkerd，在那里我们使用内部服务加密。在我的上一个组织中，尽管有 55 名工程师和每天数百万的请求，我们从未真正实现端到端加密。在 ingress 中获得安全性的便利性是超级容易和美好的。”

## 集成工具:寻找快速内部开发循环

根据 Sudia 的经验，工具的另一个关键是采用不只是在特殊情况下使用的工具，而是可以成为工作、速度和效率不可或缺的一部分。在 UPchieve 的例子中，你有能力摆脱不可扩展的任务。在某种程度上，这就是他的团队如何加速使用例如[网真](https://www.getambassador.io/docs/telepresence/latest/quick-start/)。

苏迪亚的团队已经自称为“远程呈现的超级用户”，因为他们是一个技术上不同的团队，在各种环境下工作，跨各种操作系统。Sudia 主要在 Mac 上工作，但有时也在 Linux 上工作，主要使用 Jetbrains。团队中的其他开发人员使用带有 VS 代码的 MAC，而一名开发人员在远程 Ubuntu VM 上完成大部分工作。

Sudia 解释说:“我们仍然需要快速、轻松地合作，而网真让我们做到了这一点。一名开发人员住在网真，因为他实际上不能做本地开发，因为他选择了如何设置他的开发环境。他无法访问本地主机，因为本地主机位于远程虚拟机上。他早上的例行公事是起床，启动网真，然后他整天工作，浏览一个自定义的 URL，并能够在他的远程机器上点击功能，这就是他如何开发的。

“这说明了远程呈现工具本身的速度和易用性。它允许我们做的不仅仅是“来，让我很快地和你分享这段代码”这样的事情。它可以让开发者在其中生活。”

根据 Sudia 的说法，在传统的本地开发中，组织必须不断地将代码提交到版本控制中，处理构建管道，推进到开发环境中进行测试，然后将代码升级到试运行，然后生产。即使对于需要大量快速迭代的任务，这个过程也是必要的。这也构成了许多潜在的不必要的步骤，并增加了时间开销，而像网真这样的东西可以让开发团队跳过步骤并节省时间。

“每次我们需要检查某样东西时，我们都要等 7 分钟来构建它，然后我们又要等几分钟来部署。现在，我们只需运行网真并在准备阶段检查它。如果我们可以将每次提交检查的时间减少 9 分钟，每个开发人员每天可能会进行 10 到 50 次提交检查，那么网真为我们带来了令人难以置信的时间和生产力。”

## 为“小金丝雀”使用网真

Sudia 的团队发现，这种方法比将代码推过整个管道并进行部署，然后不得不进行回滚的方法风险更小。网真将选择的请求发送到开发人员的笔记本电脑上，使他们能够修改代码，然后只需点击几下鼠标就可以完成。苏迪亚表示，从某种意义上来说，它就像一只测试用的小金丝雀。

“如果没有这一步，风险在于您认为您已经解决了一个问题，并且您将它推广到生产环境中，却发现‘哦，实际上，我们还没有解决它。’然后，您必须回滚整个过程。与此同时，你有你的金丝雀 5，10，15，20%的流量，直到你意识到它不工作，或者，如果你不是金丝雀，你所有的请求都通过一个系统仍然没有固定。"

UPchieve 的流程是在半登台环境中进行实际开发，但实际上，它是通过远程呈现针对他们的登台基础架构进行的。

“有了网真，当我们对某件事有信心时，我们会合并到 main，因为我们对它有很高的信心。然后经过 CI/CD，CD 流程推进到准备阶段，我们进行最后一种 QA 冒烟测试检查，然后我们将其推进到生产阶段。因此，管道变得非常快，因为绝大多数测试在通过管道之前就已经在高有效性的环境中进行了。”

## 摘要:开发人员控制平面的透明度和效率

Sudia 说，无论是非营利组织还是小型创业公司，每个小型组织都可以从节省的时间、资源和更高的效率中受益，因为相关的、精心选择的工具放在一个中央开发人员控制平面中。无论一个组织是由赠款资助的非营利组织还是由风险资本支持的公司，各种规模的组织都在寻求效率。

在基础设施投资上省下的钱可以让你换一个工程师。能够在 API 网关上轻松配置安全性和可靠性护栏，然后让开发人员通过自助服务配置他们自己的 API 端点，可以解放运营团队，让他们专注于企业中的其他高价值机会。

大量减少的构建时间可以等同于另一个特性的开发。像 Telepresence 这样的工具有助于通过云原生技术提高快速反馈，并随着基于微服务的架构中服务数量的增长而成为一项宝贵的资产。

对于每个组织来说都是如此，基于开源工具构建的开发人员控制平台支持开发人员体验，提高整个应用程序开发生命周期的效率，以便他们可以快速自信地编码、测试、交付和运行他们的 Kubernetes 工作流。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>