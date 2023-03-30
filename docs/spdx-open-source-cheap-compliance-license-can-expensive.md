# SPDX 可以帮助组织更好地管理他们错综复杂的开源许可

> 原文：<https://thenewstack.io/spdx-open-source-cheap-compliance-license-can-expensive/>

随着开源变得越来越普遍，公司正在消费具有开源组件的产品。今天，你几乎不能使用任何没有任何开源代码的软件，这使得公司很难记录他们正在消费的东西，并保持与开源许可证的合规性。

一个名为[软件包数据交换](https://spdx.org/)的新 Linux 基金会项目有助于简化问题。通过 SPDX，基金会主持项目并拥有规范和商标资产的版权。这是一个由志愿者组成的开放社区，因此许多公司、学术界和其他基金会的人都参与其中。

Black Duck Software 副总裁 [Phil Odence](https://www.linkedin.com/in/podence/) 和前 Canonical Ubuntu 发布经理、现任 Linux 基金会战略项目总监 Kate Stewart 为 SPDX 工作组撰写的一篇论文指出:“互联网上免费提供的软件有 2000 多种不同的软件许可证，许可证激增是软件开发组织以及在其产品中重新分发软件包的公司的一个主要头痛问题。”。

鉴于如此多不同的许可证可能互不兼容，即使对于拥有大量资源的公司来说，开源和许可证也是一个令人头疼的问题。试图获得准确完整的许可信息是一件非常耗时的事情，尤其是在大规模的情况下。同时，公司也需要更好地理解遵守开源许可的问题。

SPDX [治理](https://spdx.org/Governance)模型基于精英治理模型，就像 Apache Software Foundation 使用的模型一样。有三个团队，每个团队都有自己的主席和章程:技术、法律和外展。此外，一个核心小组提供全面指导和协调。

技术委员会维护并发布 SPDX 规范和工具。它由[凯特·斯图尔特](https://www.linkedin.com/in/katestewartaustin/)和[加里·奥尼尔](https://github.com/goneall)共同主持。实际的团队由来自 SPDX 社区的志愿者组成，任何人都可以参与。团队的日常工作中会用到很多资源，包括 wiki、bug/特性跟踪系统和 GitHub 库。每周都有电话会议。该规范是在 Linux 基金会的指导下制定的。

SPDX 以标准格式提供公司所需的许可证信息，以便做出这些类型的合规性决策。SPDX 使用一种通用的机器和人类可读的语言来传达许可证合规性信息，以减少多余的工作并阐明开发人员的许可意图。

## 使用 SPDX

SPDX 提供了许多可供外部方使用的输出。每一种都有其独特的价值，有助于许可证识别和最终的合规性:

1.  **许可证列表**:许可证列表使用短标识符来表示特定的开源许可证。SPDX 在一个非授权 URL 上维护了一个[发布页面，该页面包含已经由法律团队审查和发布的开源许可证的短标识符和许可证文本。](https://spdx.org/licenses/)
2.  **源文件中的许可证标识符**:源文件中许可证标识符的使用极大地提高了自动解析源文件以确定许可证的可靠性和效率。
3.  SPDX 文档 : SPDX 文档是标准格式的相关许可和版权信息的总结，允许在项目和用户、供应链成员等之间共享。至少，它包含了一个包中所有文件的版权和许可信息(你要传递的东西)。

SPDX 文档有一个标准格式，但有许多不同的工具，包括开源和商业工具，可以与它们一起工作，并自动执行许可证合规性流程中的例行步骤。根据进入 SPDX 文档的分析级别(以及创建该文档的内容),可能还需要一些手动步骤，例如，使用审阅者注释对 SPDX 文档进行注释等。

SPDX 文档由一个或多个部分组成。其中一些部分是必需的，而其他部分是可选的。SPDX 规范的 2.1 版列出了以下部分:

1.  **文档创建信息**:表示文档的创建者、创建方式以及其他与创建相关的有用信息。
2.  **包信息**:本节提供关于“包”的信息一个包可以是一个或多个文件。这些文件可以是任何类型的一个或多个文件，包括但不限于源文件、文档、二进制文件等。包信息包含发起者、其来源、下载 URL、校验和等等。它还包含软件包的简要许可。
3.  **文件信息**:这是一个特定文件的信息。它可以包含在文件中找到的文件版权(如果有的话)、文件的许可证、文件的校验和(以确保文件没有被更改)、文件贡献者等等。
4.  **Snippet Information**:Snippet Information 可以用来定义在不同的许可下，文件内特定字节或行的不同许可。这将涵盖如下场景:有人将代码从 GPL-2.0 文件复制到 Apache-2.0 许可的文件中。
5.  **其他许可信息**:其他许可信息提供了一种描述不在 SPDX 许可列表上的许可的方式。您可以为许可证创建一个本地(SPDX 文档)标识符，并将许可证文本本身放在文档中，然后在文件中引用它，就像从许可证列表中引用许可证一样。
6.  **关系**:关系是在 2.0 规范中引入的，是表达 SPDX 文档如何相互关联的一种非常强大的方式。例如，二进制文件是从源包中生成的。
7.  **注释**:注释是人们对文档中各种实体和元素所做的评论。例如，某个审阅文档的人可能会对某个特定文件及其许可证进行注释。注释对于审阅 SPDX 文档以及传达关于包、文件、创建、许可证、文件等的特定信息非常有用。

## SPDX 是给谁的？

SPDX 不局限于个人或组织，它同时满足两者的需求。该组织鼓励开源开发者采用其许可证标识符。Das U-Boot 项目是这种方法的早期采用者。

即使对于独狼开发者来说，它也有非常明显的好处。如果人们可以明确地确定一个文件的许可，那么遵从性(从而遵从他们的意愿)就会变得不容易出错并且更加可靠。虽然浏览四五个文件并不是什么“大不了的事”，但是当你试图实际构建一些东西时，试着浏览 10，000 个文件。

有许多大公司与 SPDX 合作，包括 ARM、高通、三星、西门子、TI、WindRiver 等。不同公司使用 SPDX 的方式不同。有些只使用许可证标识符。有些人把信息的结构用于他们自己的程序，有些人用这些材料创建文档。

但是，请记住，使用 SPDX 并不意味着它提供了针对任何侵犯的完全保护。SPDX 只是用来总结和报告包中许可的事实。该项目不判断某件事是否违规。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>