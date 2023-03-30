# 如何发现和解决工程瓶颈

> 原文：<https://thenewstack.io/how-to-find-and-solve-engineering-bottlenecks/>

在当今的技术环境中，强大、高效的工程团队是企业最有价值的资产之一。[据麦肯锡](https://www.mckinsey.com/industries/technology-media-and-telecommunications/our-insights/developer-velocity-how-software-excellence-fuels-business-performance)称，那些通过为开发人员创造合适的创新环境和消除摩擦点来增强他们能力的组织，其收入增长速度平均比那些在实现卓越工程方面不太成功的公司快四到五倍。

该数据表明，一个组织的底线与他们的工程师的效率和快乐程度之间存在相关性。作为一名现任高级软件工程师和前工程负责人，我可以证明这样一个事实，即通过数据驱动的洞察力和透明的沟通来提高效率对工程团队的成功至关重要，因此对整个组织也是如此。然而，工程瓶颈或摩擦点使得工程师难以有效地发布代码，这可能是对软件团队完整性的真正威胁。以下是如何识别和根除工程团队中的瓶颈，以便您可以更快地向客户交付价值。

## 什么导致了工程瓶颈？

 [克里斯汀·福斯特·马克斯

Kristen Foster-Marks 是 Pluralsight Flow 价值交付团队的工程总监。她是一名前 ESL/EFL 教师，早年在韩国教授英语作为外语，在科罗拉多州立大学教授学术英语和写作。她在 2016 年过渡到软件开发职业生涯，通过学习编程语言，她很高兴地观察到学习人类和计算机语言之间的许多相似之处。在业余时间，她喜欢阅读和学习新事物，写作，在山里度过时光，旅游，打高尔夫球，打乒乓球打败她的丈夫。](https://www.linkedin.com/in/kristenfostermarks/) 

在我担任软件工程师期间，我观察到瓶颈的一个主要来源是依赖其他团队来审查、合并和部署代码到产品中。尽管微服务和受限上下文非常流行，但是没有一个团队能够完全自主地审查和发布他们所有的代码。有许多共享库和服务是支持基于服务的架构的基础设施所必需的，并且这些共享组件的构建和维护需要跨团队协作。

如果这些工具中只有一两个“所有者”能够在合并和部署之前对拉请求进行最终批准，那么就很容易出现瓶颈。例如，也许项目所有者有极端的代码标准，并期望在第一次合并时就达到完美，或者被审查请求淹没，因为他们是项目的唯一批准者，或者甚至优先考虑某些团队或个人的工作。这些因素中的任何一个都可能导致代码发布变慢。

瓶颈的另一个主要来源是错误的 CI/CD 系统。CI/CD 检查对团队来说是非常宝贵的，因为它们确保在代码发布到产品之前满足一组特定的预定义标准。然而，这些 CI/CD 系统是由工程师构建的，它们本身很容易被破坏。当团队不依靠 DevOps 工程师来处理所有与 CI/CD 有关的事情时，团队中的工程师将不会拥有快速识别和修复问题所必需的知识和能力。

最后，整个应用程序的复杂性会导致团队的瓶颈。应用程序变得越复杂，为生态系统贡献代码的工程师的认知负荷就越高。随着组件之间依赖关系的增长，工程师越有可能忘记更新这些组件中的一个，或者他们越有可能不得不等待组件所有者通过管道来移动这项工作。

## 发现摩擦点

知道这些瓶颈的存在只是成功的一半——工程师和工程领导者还必须能够发现这些瓶颈并快速调整。通过像回顾会这样的[仪式，可以相对容易地识别工程瓶颈。一个常见的回顾活动是询问团队，在之前的项目或开发周期中，什么是令人沮丧的。这使得工程师能够说出他们在上一个开发周期中可能遇到的摩擦点。没有人喜欢瓶颈，所以如果它们在团队中经常发生，那么在这些讨论中一定会出现。](https://builtin.com/software-engineering-perspectives/sprint-retrospective-actionable)

一旦通过定性的数据收集方法(如回顾)识别出潜在的瓶颈，团队就可以利用定量数据来支持或推翻他们的假设。团队可以使用数据回答的问题有:

*   我们完成的哪些票证具有异常高的周期和排队时间？这是什么原因呢？
*   我们承诺的和未完成的工作有多少是因为我们无法控制的力量而未完成的？我们是否依赖另一个团队或项目所有者来审查和批准我们的工作？
*   我们的平均每日部署频率是多少？是否存在我们没有或不能部署的多天时间段？

## 摆脱困境

正如我前面提到的，在解决令人沮丧的工程瓶颈时，具体的数据可能是一个强大的工具。作为 [Pluralsight 的 Flow](https://www.pluralsight.com/product/flow?utm_term=&pslp=product-flow&aid=7014Q0000022XDUQA2&promo=&utm_source=branded&utm_medium=digital_paid_search_google&utm_campaign=US_Brand_Flow_E&utm_content=&cq_cmp=9134953436&gclid=Cj0KCQjwhLKUBhDiARIsAMaTLnEqMx6DuizK5vN5ZWh3jDlO3oa_tm52RGGUA1G4-Se06d_V7Ran0hIaAqBbEALw_wcB) 产品的工程师，这是一个软件交付智能平台，旨在用数据武装工程团队，使他们的工作流程更高效，数据驱动的见解对我来说尤其重要。

一旦团队确定了瓶颈，他们就可以在他们的票务系统(吉拉、Azure、GitLab 等)中创建一个状态。)反映了瓶颈，跟踪票证处于该状态、被阻止前进的时间。在开发周期结束时，数据驱动的洞察将在总体水平上显示票证处于特定“排队”状态的总时间。如果一个团队通过这种策略意识到，他们仅仅是在等待其他团队审查和部署他们的代码，就损失了几天的生产力，那么他们可以向管理层提出数据驱动的案例，以采取行动来修正这个障碍的来源。

我的工程团队已经形成了一种积极主动的态度来找出并减轻瓶颈。我们已经形成了一种文化，即定期识别内部和外部瓶颈，集思广益找出缓解瓶颈的方法，然后找到跟踪瓶颈的方法，这样我们就可以准确地评估我们的缓解工作是否有效。这种正面解决工程瓶颈的方法将很好地服务于工程团队。

## 外卖

不解决瓶颈的后果是可怕的。当团队分析一组要完成和交付的工作时，我们倾向于假设我们之前经历的瓶颈不会随着我们的前进而持续。然而，如果现有的瓶颈持续或者新的瓶颈出现，团队很容易错过他们的交付日期。这对团队士气是毁灭性的，导致个人和集体的习得性无助感。它还延迟了工程团队一直努力交付给客户的价值。

有时我们根本无法预测瓶颈。然而，对于我们所知道的那些人来说，通过定期的团队反思和数据驱动的洞察力来预测和提前规划瓶颈可以减少时间损失和由工程路障造成的挫折。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>