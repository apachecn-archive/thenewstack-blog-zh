# 为什么必须将错误监控放在代码附近

> 原文：<https://thenewstack.io/why-you-must-keep-error-monitoring-close-to-your-code/>

很少有 DevOps 团队有足够的带宽来手动解析和优先处理成百上千的应用程序错误警报中需要修复的内容。这包括区分小故障和那些可能使组织满足客户需求和期望的能力嘎然而止的错误。

理想情况下，一个可行的错误监控系统应该以一种指示必须做什么来进行修复的方式来自动化错误数据的通信。

错误跟踪软件公司[哨兵](https://sentry.io/welcome/)的工程副总裁本醋说，用户收到的错误警告必须是“可操作的”。醋溜说，“这也是一个很难解决的问题”。

[为什么错误监控必须靠近你的代码路径 w/ Ben 醋离哨兵](https://thenewstack.simplecast.com/episodes/why-error-monitoring-must-be-close-to-your-code-path-w-ben-vinegar-from-sentry)

该系统还必须涵盖广泛的数据类型和代码。如果错误监控只能在 [JavaScript](https://en.wikipedia.org/wiki/JavaScript) 服务器上传达错误，而您的许多其他应用程序都运行在 Python 上，那么它就没有多大价值。

换句话说，错误监控也必须以代码为中心。

在这一集的新 Stack Makers 播客中，醋讨论了错误监控在今天意味着什么，以及在不同版本的监控中，检测错误如何成为当今组织的一项关键能力。

在错误监控的早期，一个软件产品可能会指出“‘嘿，你正在运行一个坏掉的网络服务器，它正在崩溃，”醋溜说。醋溜说，一种更高级的系统可能包括盲目地翻找 Web 服务器日志文件，以查看“是否存在某种崩溃转储或堆栈跟踪”。“文本文件不会真的给你发电子邮件，或者在出问题的时候给你发信息，”醋溜说你必须非常主动和严格地定期检查它。"

如今，以 Sentry 为例，组织可以依靠错误监控来监控 30 多种不同编程语言的应用程序。这意味着，例如，在为用 Python 或 JavaScript 编写的应用程序安装了客户端库之后，“你会在收件箱或 Slack 频道中收到这样的消息:‘嘿，现在有一个问题。“用户体验触发了这条代码路径，导致了一个异常，他们过得并不愉快，”醋说这是尽可能多的信息，可以让你快速补救。"

醋溜说，Sentry 的产品反映了错误监控是如何“真正扩展为一个领域”的。“Sentry 是一个开源的、跨项目的错误监控服务器堆栈，它真的适用于每个平台，”醋说。"在早期，[错误监控]是非常特定于平台的."

错误监控也应该继续发展。例如，Sentry 正在开发一些功能，这些功能远远超出了吸收错误数据的范围，开始提供更精确的统计分析。“一个错误可能发生 100 次，可能发生 1 万次，可能发生 100 万次。但是根据你的总流量的百分比，你真的不知道这是好是坏。“一百万个错误听起来真的很糟糕，但如果您正在处理一个端点的十亿个事务，那可能还不算太糟糕。如果在一个电子商务网站上进行 100 次结账流程尝试时出现 100 次错误，那真的很糟糕，会损害你的业务——所以，相对于你的整体流量模式，能够区分就像是一个关键的下一步，也是我们现在正在努力的。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>