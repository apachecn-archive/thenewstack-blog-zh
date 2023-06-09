# 什么时候智能合约是矫枉过正？

> 原文：<https://thenewstack.io/do-i-need-a-smart-contract-2/>

智能合同是分布式分类帐的一个强大功能。这些平台可以跨公司、云和地理位置共享数据，但通常它们转换或操纵数据的能力是有限的。智能合约通过支持广泛的数据转换来扩展平台本身的内置数据处理能力，在 Vendia 等系统中，当这些计算需要与多个现有系统协调时，还可以轻松地与现有 it 基础设施和其他应用程序集成。

## 什么是事件处理程序？

事件处理是一种强大的架构设计模式，允许系统松散耦合。分布式分类帐非常适合这种模式:当一个事务块被提交时，分类帐可以通过任意数量的云集成机制(队列、流数据记录、云函数调用、事件中心、云编排步骤等)来“激发”事件。)事件处理程序使得将两个或更多系统集成在一起变得容易——在这种情况下，将分布式分类帐中的一个节点与应用程序或系统的其他元素集成在一起。

当然，还有其他的架构模式将代码与分类帐联系起来，比如轮询；为了在本文的剩余部分保持简单，我们将使用“事件处理程序”作为“您可以将代码与分布式分类帐中的信息集成的所有方式，这些方式都是*而不是*智能契约。”

## 智能合约与事件处理程序

 [蒂姆·瓦格纳

Tim 是 AWS Lambda 的发明者，也是 AWS Lambda 和亚马逊 API 网关服务的前总经理。他还曾在比特币基地担任工程副总裁，管理设计、安全和产品管理团队。蒂姆联合创立了 Vendia，以帮助各种规模的组织更有效地跨云和公司共享数据，他担任其首席执行官。](https://www.linkedin.com/in/timawagner) 

决定使用智能契约还是事件处理程序很重要，它影响到从各方之间的信任到如何处理数据安全的方方面面。智能合同通常是共享的，这种共享有很大的好处(信任、协议)，但也有成本——例如，合同的更新通常需要在多方之间协调和确认，使开发过程和最终的“链上”部署变得复杂。虽然 Vendia 允许以任何语言表达智能合同，从而使智能合同的编写更加灵活，但与一方拥有的传统应用程序代码相比，管理智能合同还需要更多的“仪式”。

相反，当涉及到与其他方的互操作时，事件处理程序和常规应用程序逻辑具有局限性:因为它们是公司私有 it 基础架构的一部分，所以不太可能被其他人信任，并且它们的执行可能不会与其他方的活动紧密同步。

你怎么知道什么时候用哪个？当智能契约在多方之间同步可执行的策略或分析时，它们最有意义。相比之下，事件处理程序是一种很好的方式，可以让一方与应用程序基础设施的其余部分集成。这里有四个问题，你可以问自己，以帮助判断一个操作是否应该“在链上”(智能契约)还是“在链外”(事件处理程序)。

为了使这个清单更加具体，我们将使用一个运行的例子:一家银行和一家像 Visa 这样的信用卡发行商需要联合处理一个用户的信用卡，包括计算账户的月利息。

*   谁需要相信结果？

要考虑的最关键的问题是，计算是否需要成为唯一的真实来源。当单个参与者对结果感兴趣时，事件处理程序和传统的应用程序逻辑就足够了。但是如果多方都依赖于结果，那么通常需要一个聪明的契约。在我们的运行示例中，计算和应用信用卡的月利息需要是真实的单一来源——如果银行和发卡行在对账户应用多少利息的问题上意见不一，那将是一场灾难！相反，如果银行希望通过银行的网站向用户显示当前余额，或者发卡行希望运行内部报告，他们只关心他们各自的系统，而不是彼此，实现网站 ui 和报告软件不需要征得对方的同意，甚至不需要对方的意识。

*   **计算的输入(参数)或输出(结果)是链式的，并与其他更新一起序列化吗？**

这是一个经典的数据库难题:序列化重要吗，或者“足够接近”就足够好了吗？在我们的示例中，利息计算是一个需要与用户的信用卡购买正确序列化的交易——错过一次购买或包含两次购买会造成很大的伤害。相反，如果一个显示最近交易的网站一分钟更新一次，而不是一秒钟更新一次，这不会影响正确性(尽管它可能会影响客户满意度！)如果智能合约旨在成为正在进行的交易流的一部分，那么智能合约是更好的答案，因为它们将输入、输出和处理都连接在一起。相反，如果信息只需要传递到软件架构的其他部分，那么事件处理程序或其他传统的数据集成方法就足够了。

*   **对于审计、透明度或信任而言，合同的执行本身是一个关键步骤吗？**

当智能合约模拟现实世界的协议时，记录它的执行情况及其参数可能很重要。在我们运行的示例中，信用卡上的利息交易本身就是最重要的交易之一，它被应用的事实对于银行和发行者来说都很重要。仅仅看到用户的余额变得更高就会令人惊讶:双方都需要知道为什么以及何时调整余额。相反，银行不关心发行人何时发布内部报告，发行人也不对银行在其网站上显示的内容负责。

*   还有其他与《守则》相关的仪式吗？

智能合同执行很重要，但这只是生命周期中的一步:在现实世界中，创建、更新和取消智能合同也是重要的步骤。智能合约上的这些“CRUD”操作可以在共享分类帐中产生重要的额外好处和后果，例如，允许在所有参与方之间对新的或更改的合约进行代码检查可能很重要。在这里，分类帐的存在和它提供内置保证的能力，例如验证共享用于检查的代码是否真正代表了在以后调用智能合约时执行的代码，极大地简化了这些结果的实现。虽然双方可以参与一系列点对点或相互执行的书面合同和通信，以验证已执行的合同更新，但将“计算机擅长的事情”保留在计算机中显然比简化协调会议、与律师的电子邮件等更有效。当需要进行可以以更加自动化的方式处理的更改时。在我们运行的例子中，如果美联储提高利率，信用卡市场也跟着提高利率，银行、发卡行和双方的审计师都需要同意利息计算正在改变(以及改变应该何时发生)。交替智能合约计算的“元交易”对于建立所有未来利息交易的有效性至关重要。

下表总结了在事件处理程序和智能协定之间进行选择的一些关键要素:

## 了解更多信息

对跨公司、云和地理位置共享数据的应用程序进行建模涉及到许多决策，尤其是在分布式分类账和数据共享平台层面上建模什么，而不是在应用程序逻辑中建模什么。我们希望这篇文章对思考智能合约与事件处理程序和其他应用程序级功能有所帮助，我们期待听到您的想法！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>