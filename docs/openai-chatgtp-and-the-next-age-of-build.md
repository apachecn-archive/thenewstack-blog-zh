# OpenAI、ChatGPT 和下一个“建筑”时代

> 原文：<https://thenewstack.io/openai-chatgtp-and-the-next-age-of-build/>

OpenAI 的工作，特别是 ChatGPT，最近主导了技术圈。3.5 版本的最新更新通过提供一个允许用户与人工智能对话互动的界面，将“生成式人工智能”的概念带入了主流。

与其他新技术不同，这个系统的易接近性很快使它超越了软件开发的圈子。对某些人来说，这是生成关于某个主题的完整报告或分析；对其他人来说，它可能是创作歌曲或其他艺术。如果你想真正开怀大笑，请它给你写一封“辞掉工作的刻薄信”

在软件开发领域，ChatGPT 正在引领构建软件的下一个时代。快速浏览任何一个主要的社交媒体平台都会显示出两极分化的观点。

一些人将这种对话式生成人工智能的引入视为革命性和令人兴奋的，完全改变了他们的日常工作流程。对于其他人来说，它代表了不确定性和风险——有缺陷和未经检查的代码进入生产的风险，甚至是对工作淘汰的恐惧。

关于是兴奋还是担心的争论可能会在中间的某个地方结束，尽管双方都有强烈的主张，但我们有一种方法可以接近 ChatGPT，这种方法可以真正改变开发人员构建和发布代码的方式。

一方面，ChatGPT 以一种我们从未见过的方式极大地降低了编写软件的复杂性。我不禁想到人们在学习新的软件语言时最常走的路，以及这是如何转变的。

花费数小时在搜索引擎上寻找示例代码或浏览论坛寻找答案的旧方式可能已经成为 Blockbuster 或座机的方式。老方法有时会给你答案，希望能给你一个解释，但你也可能会比开始时更困惑地结束你的搜索。

在“用 ChatGPT 构建”时代的早期阶段，我们向 AI 请求一个组件，它会返回示例代码。我很好奇这是如何实现的，并通过询问 ChatGPT “演示如何在 React with launch crystally 中编写一个特性标志”来测试这个想法正如宣传的那样，它令人惊讶地迅速返回了一个用特性标志在两个软件组件之间切换的例子。

当我第二次提示它“你能给我看一个 Python 的例子吗？”它很快转向新的例子。这两个实例还包括一步一步的例子，展示了代码的含义和特定于 LaunchDarkly 的实现注意事项。它甚至包括文档的链接。

但它是“可复制可粘贴”的吗？不完全是。

> 即使是在人工智能方面，学会问正确的问题也是一种艺术形式。

虽然这段代码是有效的，但是代码的关键部分却丢失了。launch crystally 要求在应用程序代码中初始化语言 SDK，因为提示没有要求这样做，所以省略了这一部分。当我扩充我的查询时，它返回了新的代码，包括初始化组件。

这是一个很好的例子，即使是在人工智能方面，学会问正确的问题也是一种艺术形式。即使最终提出了正确的问题，仍然需要考虑业务逻辑。ChatGPT 可能永远不会理解其他实现的特定不同方面，因为它所学习的模型可能包含也可能不包含符合您自己需求的示例。

在这个简单的例子中，我们向 ChatGPT 请求一些代码，得到了我们所要求的结果，以及解释和文档链接，但这还不够，因为它缺少我们没有考虑过的需求。我们稍微修改了我们的问题，作为回报，我们收到了我们需要的额外细节。然而，ChatGPT 缺乏足够的定义来运行，它需要我们对工具有一定的了解，才能知道应该问什么问题。当考虑 ChatGPT 和开发人员体验时，很难想象 ChatGPT 会完全取代开发软件的开发人员。

这对 ChatGPT 在现实世界中的有用性意味着什么？

在修补了 ChatGPT 之后，我相信答案在于对开发人员工作流程的改进。当考虑 ChatGPT 和开发人员体验时，很难想象 ChatGPT 会完全取代开发软件的开发人员。该系统当然擅长回答问题和提供信息，但它总是很难理解给定环境中特定软件实现的复杂性。

在这个新的构建时代，开发人员可能会盲目地将 ChatGPT 生成的代码复制到他们的环境中，并在出现问题时花费几个小时进行调试。虽然这肯定是可行的，但快速代码工具的后果很可能被类似网站崩溃的可能性所压倒。

使用 ChatGPT 更有可能的结果是，开发人员将它作为一种工具，他们可以使用它来增强他们现有的开发工作流，以加速他们开发过程的早期阶段。

像快速启动项目或填补知识空白(从语言知识领域，甚至到过程知识领域)这样的任务让开发人员加速他们学习和构建的方式。

如果软件世界是由千篇一律的代码组成的，那么 ChatGPT 有可能取代开发团队。然而，这不是我们的现实。事实是，每个企业都以不同的方式处理问题。

一层层的流程、业务逻辑、技术债务、设计决策和架构创造了一个 ChatGPT 无法普遍回答的语境。这是一个工具，我们可以用它来更快地构建软件，扩展我们自己的知识，并在使用中成长。那些忽视它的人将会落后，但是那些完全依赖它的人将会结束更多的停机回顾电话和填写根本原因分析文档。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>