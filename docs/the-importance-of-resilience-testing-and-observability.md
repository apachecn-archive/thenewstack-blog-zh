# 弹性测试和可观察性的重要性

> 原文：<https://thenewstack.io/the-importance-of-resilience-testing-and-observability/>

为了迎接 4 月 21 日的[故障转移会议](https://failover-conf.heysummit.com/)，LightStep 赞助了这篇文章。

 [詹姆斯·伯恩斯

詹姆斯是 LightStep 的开发者倡导者。从网络负载平衡器到 FPGAs 到 ASICs 到嵌入式安全再到大规模的云操作，James 目睹了系统如何工作，但更有趣的是，他们是如何失败的。他热衷于分享他所学到的东西，以提升团队水平，让开发人员更开心，并改善客户体验。](https://www.linkedin.com/in/james-burns-7816a82/) 

人们喜欢写和谈论困难的事情，但有时谈论容易的事情更好。编写和部署代码以及自动扩展代码比以往任何时候都更容易。代码也很容易成为开发团队的闹钟，每天晚上叫醒他们。日复一日，周复一周，操作应用程序的经验会让开发团队疲惫不堪，减慢特性开发速度，削弱雄心。

令人惊讶的是，采取一些小步骤来改变你的开发团队体验他们的应用程序的方式也很容易。作为正常开发过程的一部分，通过定期使用来自可观察性和弹性的工具和实践，您可以提高开发团队的特性速度——同时提高他们的生活质量。

## 什么是可观测性？

可观测性通常用控制理论来解释，即只通过系统的输出来理解系统的状态。其他人解释说它是为未知的未知而建造的。最实际的定义是[可观察性](https://thenewstack.io/monitoring-and-observability-whats-the-difference-and-why-does-it-matter/)允许你跨越许多不同的服务、领域和尺度将结果与原因联系起来。

当一个团队试图理解他们的应用程序在生产中的行为时，这不是一些抽象的练习。有些事情发生了变化，他们需要理解*为什么*，以便恢复或改进他们的应用程序。可观测性不是工具，也不是遥测技术；这是一种获得准确且基于事实的应用程序行为模型的方法，为人类决策提供信息。

## 弹性以及如何测试它

弹性是一个(社会技术)系统最小化失败影响的能力。失败总是会发生。弹性系统采取渐进的步骤，允许系统中最有用的部分仍然服务于它们的目的。虽然像断路器或减载这样的特殊策略——甚至像重试失败这样的基本策略——是建立弹性的一部分，但弹性也是一种思维方式。这种方法承认复杂系统的现实以及失败和错误的存在。

弹性不是一件实现后就不再考虑的事情。它必须经过测试，而且理想情况下不仅仅是在东西碰巧坏掉的时候。[混沌工程](https://lightstep.com/blog/get-started-with-chaos-guide-to-gamedays/)是一种测试系统(包括人)和多种故障恢复能力的系统方法。通过有目的地将失败和退化引入系统，开发团队可以看到发生了什么。更重要的是，他们可以发现他们的可观察性和弹性的差距，以“看到他们看不到的东西”

## 更好的客户体验

最终，弹性测试和可观察性是关于一件事:给你的客户更好的体验。更快的应用程序、更少的停机时间和更多的功能。通过了解您所有系统的内部工作方式——并积极地针对故障进行测试——您会对您的团队、您的技术以及即使在出现问题时也能让客户满意的能力充满信心。通往更好睡眠和更快发展的旅程从一小步开始。

没有客户会说，“哇，这个应用如此引人注目”或“你能相信这个软件有多有弹性吗？”从很多方面来说，可观察性和弹性的影响是那些受其影响最大的人所看不到的。

但是，当您的系统扩展或达到峰值负载时，当流量峰值或大客户改变他们的行为时，当您部署新服务或您的下游依赖项部署新服务时，当您开始迁移时，当您完成迁移时，或者当看起来没有任何异常情况发生但事情仍在中断时—在所有这些情况下，经过测试的可观察性和弹性实践将让您的系统保持工作，让您的开发人员保持睡眠。

【T2![](img/927c8f3f8afea675d084dac46011c3a2.png)

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>