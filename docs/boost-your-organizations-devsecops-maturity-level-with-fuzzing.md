# 通过 Fuzzing 提高您组织的 DevSecOps 成熟度级别

> 原文：<https://thenewstack.io/boost-your-organizations-devsecops-maturity-level-with-fuzzing/>

[](https://users.ece.cmu.edu/~dbrumley/)

 [大卫·布鲁姆利博士

大卫·布鲁姆利博士联合创立了 ForAllSecure，对全世界的软件进行自动检查和保护。ForAllSecure 的产品基于他在程序分析方面超过 10 年的研究。大卫作为卡内基梅隆大学的终身教授正在休假，他的职位是计算机科学、电子和计算机工程。大卫的学术工作获得了美国总统早期职业生涯奖，斯隆奖，以及在同行评审场所发表的许多奖项。](https://users.ece.cmu.edu/~dbrumley/) [](https://users.ece.cmu.edu/~dbrumley/)

进步的组织相信持续测试——作为 DevSecOps 的一部分——是主动缓解新威胁的答案。持续测试使安全团队能够跟上开发和 IT 运营团队的步伐，并交付安全工具的深度集成和自动化。这些要求导致人们对优先考虑自动化、准确性和简单性的新兴技术越来越感兴趣。

第一个问题是团队软件开发的传统方式，瀑布方法，是线性的，这不是当今世界的工作方式。速度和规模总是包含着复杂性，而复杂性是无法用线性过程来支撑的。需要有一个反馈循环，使用瀑布，一旦开始了开发过程，就很难对软件进行迭代。

二、软件怎么操作？你如何构建软件会影响它在现实世界中的运行。所以，开发者和操作者之间需要不断的反馈。这就是你获得 DevOps 的方式，devo PS 实际上是开发和 IT 运营的结合。

第三，你打算如何维护软件？它不能只是存在，需要有一个从开始到规划阶段的反馈循环，其中包括安全性。这就是你获得敏捷方法的方式，它是连续的和迭代的，以及 DevSecOps，它包括安全性。

> DevOps 是敏捷的补充。它旨在缩短系统开发生命周期。

如前所述，敏捷是一个比瀑布更迭代的开发模型。虽然敏捷也有一个最终目标，但是过程会在过程中被回顾和调整。这允许开发人员在编码时对设计变更和安全反馈做出响应。并且这个过程一直重复，直到完成。

DevOps 是敏捷的补充。它旨在缩短系统开发生命周期。它旨在提供高质量软件的连续交付，以便在服务中没有中断。想想有多少次像脸书这样的在线服务在后台更新，对用户的干扰最小。

更快、更好的软件开发是一回事。大规模提供安全性是另一个原因。

DevSecOps 是 DevOps 的扩展，其中也包括安全专业人员。这个想法是让每个人一起看代码，而不是各自为政。这将用最少的时间和成本生产出最健壮、最有弹性的软件。

DevSecOps 并不新鲜。它实际上始于 1976 年 IEEE 会议上的一篇论文，当时瀑布是当前的软件开发方法，敏捷尚未被广泛使用。四十年前，世界对软件的依赖程度更低。今天，通过持续集成对敏捷的、最新的软件的需求已经引起了业界对 DevSecOps 的重新审视。

如何让安全性被视为一种价值而不是一种成本？已经有例子了。密码术是成功的电子商务的必要基础。没有它，用户就不会放心把他们的银行和信用卡信息放在互联网上。所以组织将 SSL 和 TLS 放在他们的应用程序、服务和浏览器中。它创造了一个相当于西班牙国内生产总值的在线经济。它催生了像亚马逊这样成功的组织。

相反，为了保持领先，组织需要创新，但他们也应该像攻击者一样思考。他们需要知道进攻，以便实施防守。这就是模糊测试在 DevSecOps 中发挥重要作用的地方。

模糊测试是一种针对负面测试的动态应用安全测试(DAST)技术。Fuzzing 旨在检测已知、未知和零日漏洞。模糊器向目标发送格式错误的输入。它们的目的是触发不良行为，比如崩溃、无限循环和/或内存泄漏。这些异常行为通常是潜在漏洞的迹象。

Fuzzing 帮助组织验证应用程序是否按预期工作，即使在意外情况下也是如此。随着生态系统变得复杂，这一点至关重要。这不仅仅是关于人们对应用程序的不当处理，也是关于如果一个集成的应用程序行为不当，应用程序会如何反应。换句话说，如果连接到你的应用程序的系统出了问题，应用程序还能运行吗？还是会崩溃？如果它崩溃了，会允许恶意代码运行吗？

在高层次上，模糊化提供了可预测性。如果在开发周期中持续进行测试，这将缩短上市时间，并降低应用程序在整个生命周期中的相关成本。首先进行适当的测试后，现场问题的数量会减少。

丽莎霍恩通过 Pixabay 功能图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>