# 关于狂喜，一种为云设计的语言

> 原文：<https://thenewstack.io/all-about-ecstasy-a-language-designed-for-the-cloud/>

如果你曾经希望构建现代的、可扩展的、分布式的基于云的应用程序可以像过去构建基本的 Windows 桌面或客户端-服务器应用程序一样简单，你并不孤单。

在 CloudNative London 2019 上首次展示的[狂喜语言](https://github.com/xtclang/xvm)是由内存数据网格软件制造商 Tangosol 的联合创始人[卡梅隆·波弟](https://www.linkedin.com/in/cameronpurdy/)和[吉恩·格利泽](https://www.linkedin.com/in/ggleyzer/)共同创造的，正是出于这一目标。摇头丸是一种新的，强类型，模块化，通用，C 系列编程语言。

除了语言本身，摇头丸项目包括一个新的可移植二进制格式和指令集，以及一个新的托管运行时，旨在支持 JIT，AOT 和自适应编译。

Java 用于运行当前的狂喜工具链(编译器和运行时)；它需要 LTS 最新发布的 JDK 17。整个项目是开源的，并在 Apache 2.0 下获得许可。它是由 xqiz . it 赞助的，到目前为止，还没有外部资助。

Ecstasy 不打算用作系统编程语言——换句话说，它不是为编写操作系统或文字处理器而设计的。相反，它是专门为现代、[无服务器式](https://thenewstack.io/category/serverless/) [云](https://thenewstack.io/category/cloud-native/)架构设计的，旨在支持现代[开发](https://thenewstack.io/category/development/)实践，如 [CI/CD](https://thenewstack.io/category/ci-cd/) 。

该语言目前处于 0.3 版本，尚未准备好用于生产，正如该项目的 [GitHub README](https://github.com/xtclang/xvm/blob/master/README.md) 所表明的那样:“这是一个庞大且极其雄心勃勃的项目，该项目可能还需要几年才能获得生产使用的认证。”

也就是说，尽管语言实现还不成熟，但语言设计已经完成，而且波弟和 Gleyzer 都有丰富的语言和编程工具工作经验。

在甲骨文收购 Tangosol 后，波弟成为甲骨文负责企业 Java、WebLogic、Coherence、流量总监、HTTP、JDBC 和中间件云服务器产品的高级副总裁。他和格利泽一起工作了大约 30 年。

“我们一起的第一份工作是在一家制作几种编程语言和编程工具的公司，”“我们用 Java 构建了一个 IDE，这是一个基于组件的环境，”波弟告诉 New Stack，

“当我们离开那家公司时，我们购买了我们已经开发的技术，而这正是 Coherence”——tanga sol 的旗舰产品——“内置的东西。”

## 狂喜的设计目标

根据该语言官方网站上的一篇博客文章，狂喜团队有五个最初的设计目标:

1.  1.  正确性，也就是可预测性。语言的行为必须是显而易见的、正确的和可预测的。这也结合了[最小惊奇](http://principles-wiki.net/principles:principle_of_least_surprise)的原则。
    2.  安全。虽然安全性通常不是语言设计的优先考虑事项，但不言而喻的是，安全性不是添加到系统中的东西；安全要么是系统的基础和底层，要么就不存在。具体来说，一种语言不能使任何没有明确授权给正在运行的软件的资源的访问成为可能(或者甚至使其存在成为可检测的)。
    3.  可组合性。高级计算机语言是关于组成的。具体来说，一门语言应该让开发人员能够将每一部分设计和逻辑放在一个最佳和自然的位置。
    4.  可读性。代码编写一次，引用多次。我们所说的“代码”应该是一个美丽的东西，形式遵循功能。
    5.  最后，语言的设计必须是递归的。没有其他机制可以预见复杂性的增加并自然地支持封装。一路上都是乌龟。"

此外，这种语言应该非常容易上手。

“离开甲骨文后，我四处玩，我意识到一切都变得如此复杂，”波弟告诉我们。“如果你回到 30 年前，你可以使用 Access、PowerBuilder、Delphi 或其他软件。您安装了它，两个小时后您就有了一个工作演示。30 年后，随着大量的投资，我们实际上已经使建造东西变得更加困难，管理起来更加复杂，这是怎么回事？

“因此，我对摇头丸的头号目标是‘我希望开发人员能够在一小时内启动并运行应用程序——从开始、部署到展示给朋友。一个小时。它必须简单，必须有意义…然后我们希望能够在一台服务器上运行 10，000 个应用程序。"

## “海龟类型系统”

狂喜对可预测性的强调也许可以通过被称为海龟类型系统的类型系统得到最好的说明，因为它是自我引导的。

在 [Smalltalk](https://thenewstack.io/can-man-spark-renaissance-smalltalk-programming-language/) 中，狂喜中的一切都是客体，所有狂喜类型都是由其他狂喜类型构建而成。换句话说，与 Java 或 C#不同，这里没有第二基本类型系统，chars、int、bit 和 booleans 都是对象。

与 Java 和 C#一样，有一个名为 Object 的根——尽管在 Ecstasy 中，Object 是一个接口，而不是一个类。

从技术上讲，类型系统支持一长串看起来相当吓人的特性。它是完全通用和完全具体化的、协变的、基于模块的、传递封闭的、类型检查的和类型安全的。

大多数类型安全检查都由编译器执行，并由链接时验证器重新检查，只有那些类型不能事先完全知道的检查才在运行时执行，特别是为了支持类型差异。

“摇头丸语言规则自动处理协变和逆变，”波弟在回复新堆栈的电子邮件中写道。“这让开发人员避免了你在 Java 中看到的所有无意义的胡言乱语，比如:

`void putAll(Map<? extends K, ? extends V> m);`

或者在 Scala 中，比如:

`trait EventListener[-E] { def listen(e:E) }`

(Scala 中的减号表示逆变。)

“然而，在许多情况下，对类型差异的支持意味着(即需要)运行时类型检查，”波弟说摇头丸做的是在编译时防止明显的方差错误，但然后在运行时做必要的类型检查，就好像你已经添加了显式类型转换。

“由于这些规则，在狂喜中你几乎从来不用‘施法’当我回到 Java 工作时，这可能是最突出的事情之一——我到处都有强制转换。"

函数和元组在语言中很突出，支持多重(和命名)返回、可选(和命名)参数、lambdas、部分和完整参数绑定以及 currying。

虽然听起来很复杂，但类型系统的特性感觉非常符合语言的整体设计。波弟说，狂喜也“不必建立在某些外部基础上；它是自足的，完全自指的。”

实际上，类型系统是使 Ecstasy 代码易于阅读和愉快使用的因素之一。

狂喜的设计的另一个重要方面是它有一种熟悉感。"我们真的很努力地让这个字体系统看起来像其他更老的字体系统."波弟告诉我们的。“我们主要模仿 Java 和 C#，但也模仿一些 Smalltalk、Ruby 和 [Python](https://thenewstack.io/an-introduction-to-python-for-non-programmers/) 。”

这种熟悉延伸到了语言语法本身。摇头丸不是一种简洁的语言，尽管有差异，但从设计上来说，任何使用 Java、C#或 Swift 等语言编写过代码的人都会对它非常熟悉，就像 Java 对从 C++进入它的开发人员一样。

例如，这里是狂喜中的典型“Hello World”应用程序，取自该项目的 GitHub repo 中的[示例。](https://github.com/xtclang/xvm/blob/master/xdk/src/main/resources/xdk/examples/HelloWorld.x) 

```
module  HelloWorld
    {
    void run()
        {
        @Inject Console console;
        console.println("Hello World!");
        }
    }

```

## XVM 运行时和安全性

理解摇头丸的关键是它基于容器的运行时，称为 XVM。与操作系统容器不同，在摇头丸容器中运行的代码不能访问任何操作系统或硬件资源。运行库也不能承载本机代码。你可以从 [XVM 字节码](https://github.com/xtclang/xvm/blob/master/doc/ops.txt)的列表中看到这一点，这是极其受限的。

“我们开始创建一个不同的运行时模型，”波弟说，“默认情况下，你的应用程序没有任何功能。”

这意味着应用程序必须声明它需要的所有资源，然后通过控制反转( [IoC](https://martinfowler.com/articles/injection.html) )来提供这些资源。在前面给出的“hello world”示例中，代码依赖于它的容器来提供实现控制台接口的东西。

一切都是作为接口而不是类注入的。因此，任何东西都可以很容易地被用来测试。“当你部署你的应用程序时，它需要一个文件系统，如果我在测试中运行它，我可以在内存中给它一个假的文件系统，当我完成时，我会扔掉它，”波弟说。"我可以并行运行一千个这样的程序，一切都变得可以模仿了."

这有很大的安全好处。首先，在容器中运行的任何代码都不能做它无权做的事情。此外，资源在它们的表面区域中被自动限制到由主机定义的编程接口，并且主机环境可以精确地决定为那些被请求的资源中的每一个提供什么。

这意味着通过注入引入的任何安全缺陷都被限制在资源注入所支持的相对少量的接口的设计和这些接口的各种可注入实现的范围内。

此外，“一旦你有了这个基本的构建模块，像 API 键这样的东西就不再是应用程序的领域了，”波弟说。“如果您需要 API 密钥，您可以要求被注入 API 密钥，因此现在我可以将我的应用程序源代码交给其他人，而他们没有我的密钥。”

## 内存模型和并发性

类似地，狂喜管理运行时也没有提出线程的概念。狂喜使用一个类似于 Erlang 的过程的演员模型。在狂喜中，这些被称为服务，可以被开发人员用来将代码分解成潜在的并发单元。

一个服务是一个独立的冯诺依曼机器的编程抽象，它可能最好被认为是一个类的类别，代表一个可变性的领域。

“改变的数据是在服务内部，只有服务可以改变这些数据，”波弟说。“如果你在服务之外，你可能认为你可以看到数据，但你实际上不能；当您访问该服务中的数据时，您实际上是向该服务发送了一个为您访问该数据的请求。”

同样，当一个服务想要修改另一个服务中的数据时，它通过一个属性来这样做，并且该属性访问变成了对另一个服务的代理调用。如果没有竞争，这个代理调用可以被内联——“基本上，在那个时候它是一个被删除的信号量，”波弟告诉我们。

换句话说，能离开一个服务边界进入另一个服务边界的只有两个东西，即不可变数据或对另一个服务的引用，这构成了一个非常简单的内存模型。

服务的作用类似于工作队列和线程的组合，其中来自服务上下文之外的任何调用(即，来自任何其他概念性执行线程的对服务的任何调用)都被转换成放置在工作队列中的工作项目，并且相关联的未来结果作为返回值被提供给调用者。

从并发的角度来看，对服务的每个调用都会创建一个新的纤程或虚拟线程。在该服务中，一次只能运行一条光纤。纤程不必运行到完成，它可以运行到阻塞。

如何为潜在的并发和异步工作分配硬件线程的选择由运行时做出。本质上，这是将自适应编译应用于并发和线程问题。

运行时还专门针对现代 CPU 缓存线行为进行了优化。“从运行时的角度来看，我们的设计是消除所有的读写障碍，”波弟说。“因为单线程代码，尤其是在用完 L2 或 L3 缓存时，速度快得惊人，但是当您遇到读取障碍时，您就已经浪费了 200，也许 400 个时钟周期。”

## 学习摇头丸的下一步

想自己尝试狂喜的读者应该看看语言博客，它包括一个[有用的，而且惊人广泛的介绍](https://xtclang.blogspot.com/2016/11/welcome-to-ecstasy-language-first.html)对于一门如此年轻的语言；它还包括一个面向来自 Java 的程序员的部分。

我还发现浏览源代码很有帮助，特别是 [ecstasy.x](https://github.com/xtclang/xvm/blob/master/lib_ecstasy/src/main/x/ecstasy.x) ，这是模块定义； [Object.x](https://github.com/xtclang/xvm/blob/master/lib_ecstasy/src/main/x/ecstasy/Object.x) ，是根对象；以及 [Service.x](https://github.com/xtclang/xvm/blob/master/lib_ecstasy/src/main/x/ecstasy/Service.x) ，这是理解并发模型的关键

仍然有大量的工作要做，还有大量来自社区的贡献机会。该项目有一份[行为准则](https://github.com/xtclang/xvm/blob/master/CODE_OF_CONDUCT.md)和一份[贡献者指南](https://github.com/xtclang/xvm/blob/master/CONTRIBUTING.md)。

下一阶段，也就是波弟和格利泽刚刚开始原型开发的阶段，是构建一个平台即服务(PaaS ),让团队展示所有这些功能。

“我们已经进行了大约六年，现在我们正在建设我们打算建设的实际项目，”波弟说。"这是你听说过的通向最小可行产品的最长的路！"

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>