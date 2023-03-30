# 数据集成的未来

> 原文：<https://thenewstack.io/the-future-of-data-integration/>

自从数据集中在数据仓库和数据湖中以来，数据集成有了很大的发展。ELT (Extract-Load-Transform)已经取代了 ETL (Extract-Transform-Load ),使分析师能够自主地访问他们在这些仓库中需要的数据。

新的[反向 ETL 解决方案](https://thenewstack.io/reverse-etl-can-help-companies-operationalize-data-lakes/)出现，使运营团队能够从相同的仓库访问整合的数据。业界称新标准为*现代数据栈*。当 [30%](https://www.accenture.com/nl-en/blogs/insights/data-driven-enterprise%23:~:text=And%2520that%2520approach%2520has%2520many,30%2520percent%2520growth%2520per%2520year.) 最有价值的公司——如亚马逊、苹果、脸书和微软——在 2008 年采用数据驱动的方法时，这个数字增长到了 70%。

“现代”的问题在于，今天的现代会变成明天的过时。这就引出了一个问题:鉴于我们已经有的迹象，数据集成将如何发展？在这篇文章中，我将探讨公司将面临的挑战，以及他们应该如何克服这些挑战。

## 当前英语教学面临的挑战

### 无法满足所有连接器需求

让我们从公司今天面临的问题开始，从 ELT 和反向 ETL 开始。公司继续在内部构建和维护越来越多的连接器有两个重要原因。

*   **长尾需求:** ELT 解决方案跟不上公司内部使用的工具数量。ELT 解决方案全部稳定在大约[150–200 个数据连接器](https://airbyte.com/blog/airbyte-strategy-to-commoditize-all-data-integration) 处。原因很简单:数据集成的难点不是构建连接器，而是维护它们。任何基于云的闭源解决方案都会受到 ROI(投资回报)的限制。支持连接器的长尾对他们来说是无利可图的，所以他们只关注最流行的集成。
*   **定制需求:**所有公司对于他们使用的相同工具在数据方面都有不同的需求。万一 ELT 解决方案缺少某个工具的 API 流，除了自己构建和维护它，别无选择。

对于 ELT 和反向 ETL 都是如此。

### 反向 ETL 缺少质量和数据沿袭

除了不能解决长尾和定制需求之外，逆向 ETL 解决方案还面临一个额外的问题。当将数据同步回运营工具时，团队需要知道该数据来自哪里(也称为数据血统)以及该数据有多正确。没有这些类型的洞察力和验证构成了运营风险，这将导致您向错误的人发送电子邮件或采取错误的行动，从而损害您的业务。不幸的是，反向 ETL 解决方案无法访问这些数据。数据团队需要手动将这些信息添加到他们的同步中，这需要更多的数据工程工作。

## 今天的问题将如何解决

### 整合 ELT 和反向 ETL

公司应该考虑使用一个工具合并他们的 ELT 和反向 ETL 过程。ELT 和反向 ETL 之间的技术差异很小，这种整合是可以预测的。包括 Airbyte 在内的一些 ELT 解决方案 [已经在其产品路线图中公布。这种整合有几个重要的好处:](https://app.harvestr.io/roadmap/view/pQU6gdCyc/launch-week-roadmap)

*   进行 ELT 使公司能够在反向 ETL 级别拥有数据血统。如果相同的工具处理 ELT，团队将知道数据来自哪里，减少数据工程工作。
*   在一个平台内监控所有管道更加容易，也减少了数据工程工作。

### 开放源码的出现

对于 ELT 供应商来说，解决每个公司的长尾或定制需求是非常具有挑战性的。我认为解决这些问题的唯一方法是通过开源，让一个积极的贡献者社区参与进来，为了所有人的利益发布他们自己的连接器。这就是 ELT 平台如何快速从 200 个连接器增加到数千个连接器的原因。

封闭源代码不能解决每个公司都有的长尾或定制需求。我认为公司解决这个问题的唯一方法是通过开源。工程团队应该采用一个 ELT 平台，该平台使用开放源代码，并有一个积极的贡献者社区来发布他们自己的连接器，以造福所有人。使用基于开源的 ELT 解决方案可能会带来挑战，例如在所有这些连接器之间保持高水平的可靠性。有两种方法可以解决这个问题:

*   通过抽象所有不特定于集成工具的东西。的确，数据连接器 [90%相同，只有剩下的 10%](https://airbyte.com/etl-is-dead) 特定于它们所连接的信号源。
*   通过财务或认可激励来激励社区维护他们贡献的连接器，就像连接器市场，个人和公司可以在那里发布他们的连接器，就像应用程序商店一样。

### 一种新的数据管道操作系统

仓库(雪花、BigQuery、红移等。)正在迅速成为数据的操作系统，所有操作都是在公司数据上进行的，以及在此基础上构建的数据应用生态系统。

同样的概念也适用于数据集成。平台可以做到以下几点:

*   ELT 和 reverse-ETL 带有开源连接器，可以随意定制；
*   一个活跃的数据工程社区，被激励去维护连接器的长尾；
*   数据血统；
*   所有数据管道的可观察性；
*   与公司数据堆栈的其他工具集成，以确保互操作性

这个平台——我称之为数据管道的操作系统——是当前现代数据堆栈的未来。这是所有数据团队努力的方向。他们需要一个平台来完成这一切，同时提供满足他们所有需求所需的可定制性。

## 结论

随着公司的数据创造在 2025 年 前经历 [23%的增长率，拥有一个高效的数据管道运营系统变得前所未有的重要。这是值得的:数据驱动型组织的收入](https://www.red-gate.com/blog/database-development/whats-the-real-story-behind-the-explosive-growth-of-data) [比他们的同行](https://www.capgemini.com/us-en/insights/research-library/the-data-powered-enterprise/) 高 70%。组织是时候通过采用数据管道操作系统来克服这些 ELT 挑战了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>