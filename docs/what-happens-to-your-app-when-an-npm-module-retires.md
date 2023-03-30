# 当 npm 模块退役时，您的应用程序会发生什么变化？

> 原文：<https://thenewstack.io/what-happens-to-your-app-when-an-npm-module-retires/>

Tidelift 赞助了这篇文章。

 [杰里米·卡茨

杰里米是 Tidelift 的联合创始人兼工程主管，他正在扩展为该公司软件平台提供动力的基础设施。在 Tidelift 之前，他是谷歌、Stackdriver(被谷歌收购)和 HubSpot 的软件工程师。Jeremy 最初在 Red Hat 从事软件工程，是 Fedora 项目的长期贡献者和董事会成员。他在麻省理工学院获得了系统和设计管理硕士学位，在北卡罗来纳州立大学获得了计算机科学学士学位。](https://www.linkedin.com/in/katzj/) 

由于公司[被 GitHub](/github-acquires-npm-buying-microsoft-a-presence-in-the-node-javascript-community/)收购，Npm 现在处于聚光灯下。免费的 npm 注册表和节点包管理器支持超过 1100 万 JavaScript 开发人员，每月下载量高达 750 亿次。超过 130 万个 JavaScript 包背后的维护者和团队通过 npm 让开源社区普遍可以使用它们。随着这些 npm 模块的发展和功能的增加，成千上万的模块已经成为公司应用程序开发团队的工作核心。但是，当他们的创造者转向其他兴趣时，这些包的维护往往会偏离正轨。

对于 JavaScript 开发人员来说，处理 npm 中的模块弃用的需求一直是一项冒险。Node.js 生态系统随着传递性依赖关系的膨胀而膨胀，在很大程度上，它们是开发环境中被接受的一部分。但是如果不进行管理或维护，可传递依赖项可能会成为代码库中的薄弱环节，甚至成为恶意活动的后门。

最近，JavaScript 开发人员发现广泛使用的请求库被弃用。这样做的计划已经进行了近一年，因此依赖于 48，000 个 npm 模块的开发者有足够的时间来考虑他们的选择。

软件团队祈祷重要 JavaScript 项目的维护人员不会转移到其他工作或兴趣上。但是当他们这么做的时候会发生什么呢？

### 您的开源供应链可能包括被放弃的或者不活跃的项目

几乎今天开发的每一个新应用都依赖于开源代码。企业软件开发和 DevOps 团队了解开源的许多优势，包括快速创新和代码质量。通常，自定义功能和业务逻辑只占应用程序代码库的 10%。

越来越少的开源用户意识到许多项目——包括那些势头强劲并在发布时使用的项目——在几年内都是不活跃的。事实证明，选择开源组件是一回事，但是随着时间的推移管理它的使用是完全不同的任务。

最近，我们与新堆栈合作调查软件开发人员，以便我们能够更好地了解他们如何为自己的应用程序选择开源组件。数百人作出了回应，我们了解到他们在选择一个开源项目来构建他们的应用程序之前所考虑的因素有着显著的一致性。

使用可接受的开源许可是考虑的首要事项——86%的受访者表示这是一个重要因素。这并不奇怪，因为大多数大公司都有一份许可清单，上面列有合格的许可和不合格的许可。我们还发现，开发人员寻找项目维护良好的信号。86%的受访者表示提交和拉取请求的数量很重要，80%的人表示他们关心维护者的响应能力。进一步分析，74%的受访者将自上次活动以来的天数作为评估开源项目的关键指标。

简而言之，开发人员在构建应用程序时有一个选择开源组件的过程。

但是，维护者的兴趣可能会改变。一份新工作不允许再有时间做这个项目了。或者，他们可能筋疲力尽，选择完全退出项目，无论是否将项目移交给另一个维护者。开发人员审查开源组件的过程通常不会捕捉到这些变化，然而组件状态或维护的这种变化每天都在发生。

### 受管理的开源方法可以帮助您发现不推荐的项目并修复相关问题

如果您的团队已经对这些项目中的一个产生了商业依赖，那么即使报告了，您如何知道功能不再被添加，漏洞没有被修补？当一个依赖于不推荐使用的库的 npm 模块被标记时，谁的工作是判断您是否应该在您的应用程序中采取行动？您的开发团队，他们管理生产应用程序的 DevOps 同事，还是您的 AppSec 团队？

这些事情发生在开源中。组件被淘汰或失宠，新的东西取而代之。我们构建 Tidelift 订阅不仅是为了跟踪这些变化并为您的团队标记它们，而且是为了修复它们在您的应用程序中产生的问题。通过与数千个开源项目的维护者合作，我们正在寻找这样的东西，所以你不必这样做。当我们看到这种情况发生时，我们将为您识别它，并建议一个推荐的路径来替换它，以保持到未来。

如果您有兴趣了解如何更好地管理您的开源组件，包括不再维护的包的表面问题，我们可以提供帮助。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>