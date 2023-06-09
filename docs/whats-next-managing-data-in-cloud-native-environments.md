# 下一步:在云原生环境中管理数据

> 原文：<https://thenewstack.io/whats-next-managing-data-in-cloud-native-environments/>

随着信息在客户体验和业务流程中变得至关重要，管理大规模数据变得越来越重要。对数据丢失和阻止访问关键信息的停机时间的容忍度已经变得很低，而让软件更快、更有弹性的努力则侧重于改善管理和简化扩展跨多个位置的大型数据集的工作。

在本视频演示中，我们了解了挑战传统方法以满足数据密集型应用需求的最新工具。我们采访了[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)的工程副总裁[韦恩·杜索](https://www.linkedin.com/in/wayneduso/)、[乔丹·蒂加尼](https://www.linkedin.com/in/jordantigani/)、 [SingleStore](https://www.singlestore.com/) 的首席产品官[卡比尔·沙哈尼](https://www.linkedin.com/in/kabirshahani/)、Amperity 的首席执行官。这些采访是在去年年底的 AWS:ReInvent 会议上录制的。TNS 出版商亚历克斯·威廉姆斯负责采访。

请点击此处观看我们的回顾和我们稍加编辑的视频记录:

[https://www.youtube.com/embed/-crP8-G_nus](https://www.youtube.com/embed/-crP8-G_nus)

视频

**Alex Williams(主持人):**大家好，Alex Williams 带来了新的堆栈，今天我们将讨论我们在 AWS re 上听到的三件事:发明数据。这三个主题是什么，让我们来看看:[亚马逊冰川](https://aws.amazon.com/s3/storage-classes/glacier/)和数据在深度冷藏中的可访问性，应用优先思维和网页组装和机器学习(WASM ML)以及它们如何成为新的热点。第一:冰川。AWS 宣布了其冷存储 Glacier 的更多功能，包括接近实时的数据拉入能力。

**Wayne Duso，Amazon Web Services:** 我们为 S3 冰川开发了这种存储类，它允许他们平均每年在几毫秒内检索一次、两次或四次数据，这是通过利用允许我们在这段时间内检索数据的技术实现的。S3 智能分层功能也很重要。因此，如果您将数据放入 S3 并打开智能分层，这些数据将从各种类别转移，一直到深层归档。因此，随着您的数据变得越来越冷，这些数据可能会越来越低。您可以围绕这一点制定一些策略，例如，某些数据将只降到像这种新的即时检索或即时访问这样的低水平。

第二:坚持。Veeam 正在建立数据备份和恢复市场。是秘制酱？将应用程序视为应用程序；不要将所有单个元素视为独特的筒仓。应用程序有许多不同种类的存储，可能是结构化的，也可能是非结构化的。你可能有对象存储。您可以在服务器中看到这一点，例如适用于持久和非持久数据的 VMware Data Mover。重要的是应用程序。

新的热门产品 SingleStore 是一个分布式关系 SQL 数据库管理系统，现在集成了对 WebAssembly 的支持。对于那些在大规模环境中工作的人来说，WebAssembly 是一个热门话题。新的堆栈作者 Mary Branscombe 将 WebAssembly 描述为一个小型、快速、高效且非常安全的基于堆栈的虚拟机，它不关心它运行在什么 CPU 或 OS 上。它旨在以接近本机的速度执行从最初用 C、C++、Rust、Python 或 Ruby 编写的代码编译而来的可移植字节码。WebAssembly 不仅仅在浏览器中运行，它开始于客户端，但是在服务器上也非常有用。这使得在数据所在的位置处理数据变得更加容易，因此您可以将计算转移到数据本身。

**Jordan Tigani，SingleStore:** 这允许你将业务逻辑放在数据库中，并且允许你不必经历重重困难。因此，如果我用 Go、Rust 或 JavaScript 编写——在大多数其他数据库中，您必须使您使用的编程语言与数据库支持的语言保持一致。有了 WASM，你可以运行 Python，你可以运行 Rust 或者其他任何东西。这是一种近乎裸机的表现。

**Williams:** 在机器学习领域，模型可以从多个来源获取数据，而不需要模式。不再了解所有的实体，所有的来源，并绘制一些方框之间的线条示意图。二十年的这种工作已经足够了，尤其是如果底层数据真的不能使用的话。

**卡比尔·沙哈尼，安珀里蒂** **:** 事实证明，很多系统都有坏数据、脏数据和缺失数据。通过建立一个系统，首先是数据，然后查看所有这些系统，以及每个来源中的底层原子级信息，遍历所有这些，并使用机器学习来理解数据中的模式。我们做的事情之一是，我们将华盛顿大学的一系列研究成果商业化，世界领先的概率数据库专家就在华盛顿大学。我们利用他的研究来找出我们如何训练机器去直觉地了解那些告诉我们关于那个顾客和那个人的数据。

**Williams:** 总之，第一:我们看到了在深度冷藏系统中对数据可访问性的真正需求，特别是亚马逊冰川。第二:应用第一的思想正在生根发芽。第三:从网络组装到机器学习模型的所有新东西。将计算转移到数据是一条开始出现的道路。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>