# Jest: Meta 的 JavaScript 测试框架加入 OpenJS

> 原文：<https://thenewstack.io/jest-metas-javascript-testing-framework-joins-openjs/>

在发布了 JavaScript 测试框架的更新后， [Jest](https://jestjs.io/) ，Meta [宣布](https://openjsf.org/blog/2022/05/11/openjs-foundation-welcomes-jest/)它将把这项技术转移到 OpenJS 基金会。

我与 [Rick Hanlon](https://twitter.com/rickhanlonii?lang=en) 进行了交谈，他是 Meta 的前端工程师，也是 React 核心团队的成员，他谈到了 Jest 在我们今天看到的项目中的成长以及它向 OpenJS 的转移。在为 Meta 工作之前，Hanlon 是 Jest 的核心贡献者，这使他能够从内部和外部看到项目的发展。

“2014 年，Jest 正式开源，”他说。“从那时到 2016 年左右，工程师们兼职工作，直到他们决定围绕它建立一个团队。克里斯托夫·中泽友秀，他当时为 Meta 工作，现在仍然是 Jest 的核心贡献者，他彻底修改了它。他和他的团队创造了人们今天真正知道的 Jest 的大多数功能，如观察模式、错误消息、错误报告和真正的大测试体验。”

汉隆继续说道，“那项工作一直持续到 2018 年，也就是我参与这个项目的时候。从一开始，不仅仅是 Jest，我们以前开发的语言也是如此，我们内部有一种风气，如果你在创造对社区有价值的东西，那么它应该是开源的。”

## **如何。jst 演变成 Jest**

Jest 是一个已经发展了十多年的框架的最新版本。在过去的日子里，当 Meta 还是脸书，并忙于微调其信使服务。jst 只在内部使用。Hanlon 给出了 Jest 如何从一种内部语言变成一个开源项目的一些见解。

“虽然。“jst 是在 2011 年为我们的 messenger 平台构建的，”他解释说，“几年后它很快变成了其他东西。我们真的需要一些高性能测试，以及其他东西，它只是从那里起飞。因为它与脸书没有直接联系，所以它是开源的一个很好的候选。此外，它对测试 React 应用程序非常有用，脸书当时刚刚开源了 React。”

三年后，Jest 作为开源首次亮相，并迅速获得了贡献者和一个活跃的社区。到 2018 年，[Jest Open collection](https://opencollective.com/jest)成立，开始为 Meta 之外的开发者筹集资金，为项目做贡献。迄今为止，Jest 社区已经筹集了近 8 万美元。

汉隆说:“克里斯托夫和梅塔把开放集体作为赞助非梅塔员工的一种方式。“多年来，Meta 本身直接向基金捐款至少 22，000 美元。他们一直支持开源维护者，并允许我们资助聚会，让贡献者可以聚在一起，真正相互见面，这很好。”

我问 Hanlon 为什么 Jest 在开放集体开始后变得如此有活力，他的回答很简单。更多的开发者加上更多的资金相当于对已经流行的 Jest 进行了显著的改进，包括内嵌快照和 ESM 支持。

## **测试变得简单**

Jest 的标语承诺“令人愉快”的测试。在我们的采访中，我请 Hanlon 给我们一个深入的视角，看看 Jest 提供了什么，让开发者使用起来如此愉快。

“我认为有很多东西使它令人愉快，”他回答说。“我可以说，当我第一次看到 Jest 时，是什么让我震惊——其中之一就是表演。它的表现比其他任何东西都要好。其次，手表模式。当你改变你的代码时，能够自动运行你的测试，而不需要来回切换并重新运行它们。它不断监视文件的变化，并自动运行只与被改变的文件相关的测试。这对开发者速度的提高是不可思议的。最后，报告—很清楚什么时候失败了，什么时候通过了正在运行的测试。我们在真正清晰的错误信息上下了很大功夫，这样开发人员就不会为了解决问题而花费不必要的时间去解码它们。”

Hanlon 接着说，“零配置也是一个很好的观点。很难配置所有的东西，很难开始，很难确定哪些测试文件是哪些，等等。“开箱即用”的体验非常好。另一件事是 Jest 在项目中是一致的。您可以进行大量的定制，但是这会迫使整个项目标准化。因此，如果你进入两个使用 Jest 的不同项目，你通常会明白大致发生了什么，并能够很快开始做出贡献。”

## **OpenJS 基金会**

Hanlon 说，Jest 转向 [OpenJS 基金会](https://openjsf.org/)是开源社区朝着正确方向迈出的一步。“这一举措将主要是一种组织上的举措。有了它，我们就能在 Meta 之外发展，并能够增加这些数字。这反过来将允许我们建立更多的功能。此外，它将使我们能够让以前从未为开源做出贡献的人们做出贡献。”

OpenJS 基金会是众多 JavaScript 标准的发源地，包括 Node.js 和 jQuery。像所有项目一样，当他们第一次被 OpenJS 吸收时，Jest 正处于孵化阶段，正在接受入职检查。在 OpenJS 入职流程完成后，Jest 将发现自己处于 Impact 或网络普通用户阶段项目中。OpenJS 基金会交叉项目委员会主席 Joe Sepi 表示:“OpenJS 基金会是社区中许多项目的中立之家，我希望 Jest 能够作为项目家族的新成员在这里蓬勃发展。我相信，让它处于开放治理之下将会重振它的贡献者基础，我们将会看到这个基础的增长。我还希望它的领导层能够参与到我们的基金会和交叉项目委员会中来，继续改进我们支持我们的项目及其社区以及整个 JavaScript 生态系统的方式。”

根据 Hanlon 的说法，这种转变将进一步增强 Jest 社区的能力，以提高他们的技能并增加他们的人数。开源项目是由社区发起的，是为社区服务的，他说 Jest 也不例外。

“我认为，在从事这些大型开源项目时，最令我满意的事情之一就是能够结识新接触开源的人，帮助他们提交他们的第一次更改，或者回答问题，并能够支持他们，邀请他们加入社区，帮助他们在职业生涯中前进。，”他说。“你会遇到编程新手或已经编程很长时间的人，这是一个非常好的机会，可以结识很多志同道合的人。”

最后，他指出 Meta 的开源团队对向 OpenJS 过渡的过程非常有帮助。

“这太棒了，因为我们有一个支持我们的成熟团队，这让我们很容易为开源做出贡献，”他说，“但我们在每个项目中都有非常不同的专业社区。Jest 的伟大之处在于，我们能够围绕 Jest 建立这个社区，最终他们(这个社区)自己就成功了。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>