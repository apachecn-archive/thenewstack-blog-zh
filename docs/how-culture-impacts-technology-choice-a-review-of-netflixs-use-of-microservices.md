# 文化如何影响技术选择:对网飞使用微服务的回顾

> 原文：<https://thenewstack.io/how-culture-impacts-technology-choice-a-review-of-netflixs-use-of-microservices/>

[](https://www.linkedin.com/in/itiel-shwartz-18542853)

[Itiel Shwartz](https://www.linkedin.com/in/itiel-shwartz-18542853)

[Itiel Shwartz 是 Komodor 的首席技术官和联合创始人，komo dor 是一家为 Kubernetes 构建下一代故障排除平台的初创公司。曾在后端和基础设施开发人员易贝|福特|鲁克特工作过的 DevOps 是一名热心的公共演讲者，喜欢谈论基础设施、Kubernetes、Python 可观察性和研发文化等话题。](https://www.linkedin.com/in/itiel-shwartz-18542853)

[](https://www.linkedin.com/in/itiel-shwartz-18542853)[](https://www.linkedin.com/in/itiel-shwartz-18542853)

我最近有机会读了网飞的雷德·哈斯汀斯和艾琳·迈耶写的《没有规则的规则:网飞和再创造的文化》一书，我突然意识到，虽然这本书根本没有关注网飞的技术，但全球公司文化对其技术选择有着重大影响。这本书集中讲述了网飞为了彻底改变娱乐业而不得不多次重塑自我、改变业务的过程。这场革命之所以成为可能，是因为一种同样激进且前所未闻的公司文化方法，这种方法不仅影响了我们今天构建技术的方式，还在全球范围内思考公司文化。

不用说，网飞的技术选择继续影响着整个行业对大规模建筑的看法。在这篇文章中，我想看看网飞的文化是如何支撑其前沿技术决策的——特别是[微服务](https://thenewstack.io/category/microservices/)。这里写的一些，其实是我自己个人对微服务爱恨交加的直接影响。这本书为我提供了一个新的视角，告诉我如何通过确保正确的文化机制首先到位，来成功地构建具有挑战性的技术架构以支持业务。我认为，如果没有网飞独特的公司文化，他们的技术选择也不可能实现，最终他们也不会成功。

## 我的背景故事

为了更深入地挖掘我写这篇文章的灵感，我对微服务又爱又恨的关系开始于我还是易贝的一名软件工程师时，当时我正试图驯服一个疯狂的庞然大物。它是如此的复杂和庞大，没有人真正理解它的全部，以至于我认识到要拆散一个作为企业心脏的庞然大物是多么的困难。

在 kickstart[komo dor](https://komodor.com/)之前，我有更多的机会来构建微服务。第一个是逐渐分解一个整体，另一个是从头开始构建一个微服务架构。所有这些经历让我有机会在新公司的第一天就建立起推动我们业务发展的架构，我也一直在尝试应用我所学到的一切。

所以我们在同一页上，如果你需要复习微服务，一个很好的起点是 ThoughtWorks 的 Martin Fowler 的这篇[基础文章](https://martinfowler.com/articles/microservices.html)。另一个值得一读的是[分部](https://segment.com/blog/goodbye-microservices/)的这篇较新的文章，它提供了一个关于迁移到微服务和相关挑战的更加实用的视角。

## 网飞建设文化和伟大科技的六大原则

那么这一切是如何结合在一起的呢？在他们的书《雷德·哈斯汀斯和艾琳·迈耶概述了使他们的成功成为可能的核心文化原则》中，我想将这些原则与使工程组织能够成功部署和维护微服务架构的文化实践并排进行比较——这实际上不是这本书背后的前提，但它确实让我想到了工程和文化相交的地方。

### 1.原则一:建立人才密度

在招聘方面，网飞在人才方面毫不妥协。它为每个职位雇佣最优秀的人，这是他们成功的基础。就微服务架构而言，这是千真万确的。微服务需要很强的学习能力，因为维护架构的人会不断遇到他们从未遇到过的新挑战和问题。坦率地说，不可能所有的开发人员和 DevOps 工程师都是各自领域的佼佼者。

虽然一些公司有一些非常优秀的工程师，但网飞有世界级的工程师。这使得网飞有可能克服许多其他工程师作为复杂建筑的先驱可能没有能力解决的挑战。它有一些世界上最好的工程师致力于新发现的挑战微服务浮出水面，他们克服了这些挑战，后来通过分享这一经验使行业也能做到这一点。

### 2.第二个原则:开始去除控制

网飞对文化的激进做法可以在最基本的公司准则中看到，从费用到假期批准，员工信任作为一项基本原则被嵌入到文化中。也就是说，只有拥有合适的基础设施来支持这种文化，这才有可能实现。我们稍后会谈到这一点。

这种文化实践是影响非网飞公司成功管理微服务架构的核心因素之一。我发现，即使是已经决定走微服务路线的公司也是在旧流程和机制仍然存在的情况下这样做的，这极大地阻碍了正确利用迁移的能力。如果公司仍然维护规则，比如对引入系统的每个新变更或提交的批准，或者甚至恢复变更，他们本质上拥有分布式的整体文化。

因此，一方面，他们拥有可以自主扩展的架构，但他们的员工却不能。您需要相信您的员工会做出正确的决策，以便获得微服务可能带来的真正好处和速度。没有这种与生俱来的信任和自主，你将会面临两个世界中最糟糕的情况。网飞在所有事情上都采取了这种方法，不仅仅是工程，并且在取得成功的过程中友好地回报了他们。

### 3.第三个原则:利用反馈圈最大限度地坦诚

很多时候，迁移到微服务的决策是自上而下的。经常发生的情况是，决策者并不真正了解手头任务的复杂性——将他们的架构分解成越来越小的部分。另一方面，那些需要自上而下执行决策的人没有影响决策过程的机构。向微服务的转移通常会带来很多复杂的情况，以前正常工作的东西会突然停止工作。快速行动和解决这些问题的一个关键是短反馈循环。

在网飞，当问题浮出水面时，他们被要求举起旗帜，进行沟通，而其他公司往往无法营造这种坦诚的文化。不具备这种沟通和坦诚氛围的公司将在复杂架构中失败，他们的团队将不断地解决问题，而不是构建基于协作思维和沟通的更长期的解决方案，因为往往听不到战壕中人们的声音。

### 4.第四项原则:建设支持性基础设施

为了取得成功，您需要知道，作为第一步，您将花费大量时间为您的开发人员和 DevOps 团队构建支持工具，以使他们能够在这一转变中富有成效。

像所有的“左移”实践一样，如果你只是在事后才记得这么做，你会发现构建支持机制以使团队成功要花费你 100 倍的时间、资源，甚至预算。松散耦合架构的成功，需要对工程师的决策有很大的信任，需要你为那些在链底部的人提供更多的“权力”例如，为了支持他们对费用报告和休假申请的创新方法，网飞提前在系统中建立了适当的检查和平衡，以确保一方面它不会被滥用，另一方面它也可以随着他们的成长和维护其文化的这一重要部分而扩展。

### 5.第五条原则:庆祝成功，阳光失败

我认为整个行业都知道了庆祝成功的重要性，如今几乎每个以公司文化为傲的组织都有某种方式来表达对优秀工作的欣赏。然而，从另一方面来看，企业仍可以从网飞身上学到一点，那就是他们对待失败的方式。在网飞，失败不会被掩盖，他们会被分析，以便能够从每一次经历中吸取教训，从而使组织成长和发展，不会犯同样的错误两次。

当您迁移到微服务时，一开始会有很多失败，如果您不抓住机会从中吸取教训，您将注定会重复同样的错误。本着网飞的这一支柱精神，在一个有许多部分成功和共同失败的环境中，重要的是要有自知之明，并从这些失败中吸取教训，找出根本原因，并最终解决问题，这样它就不会重复。

### 6.第六条原则:以上下文为导向，而不是控制

使用整体架构，很容易进行控制，因为只有一个服务，并且每个人在很大程度上都了解他们领域中正在发生的事情，并使自己与适当的实践保持一致。有了微服务，工程管理根本无法从整体上理解系统中发生的一切，每个团队都需要有高度的自主权。这就是为什么在这种快速发展的工程环境中，当涉及到能够做出决策时，透明度极其重要，同时还要提供许多关于正在发生的事情的背景信息。

对于微服务，不可能进行微观管理，因此您必须提供总体愿景和方向，并相信您的团队将与这些共同目标保持一致。网飞知道如何很好地做到这一点，这灌输了一个自下而上的共同目标，推动了他们的成功。

## 我们学到了什么

总而言之，微服务已被证明是一种非常强大的架构，可以为现代复杂的业务提供动力，但你需要记住，要通过技术架构取得成功，同样重要的是“设计你的文化”(又一个伟大的网飞咒语)。您需要很好地理解您需要的文化，以支持分布式、高级的微服务架构，并使一切最终按预期工作。拥有技术而没有文化只会导致许多不开心和过度工作的工程师。

没有现代工程和架构实践的伟大文化会导致无法以期望的速度前进和以工程师希望的速度交付服务的挫败感。没有这种文化的高级架构注定会失败，因为您将无法利用微服务的优势。因此，如果你努力从头开始打造一种真正伟大的文化，这将是让你的员工茁壮成长的基础。

因此，最终当我们在打造优秀产品的同时打造伟大的文化时，这将推动那些与我们目标一致的人发挥创造力，并将在创新和业务方面慷慨回报我们。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>