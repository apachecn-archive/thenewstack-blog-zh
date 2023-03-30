# 持续集成和持续交付(CI/CD)如何增强 DevOps

> 原文：<https://thenewstack.io/how-continuous-integration-and-continuous-delivery-ci-cd-enhances-devops/>

[](https://www.linkedin.com/in/sgunja/)

 [赛义夫·冈贾

赛义夫是 Dynatrace 云自动化和 DevOps 解决方案的产品营销总监，他曾在 VMware、Apple 和 Deloitte 任职，拥有超过 10 年的 IT 和营销经验。](https://www.linkedin.com/in/sgunja/) [](https://www.linkedin.com/in/sgunja/)

当今数字业务环境的需求要求组织在向市场推出新产品和服务时，既要实现速度，又要实现可靠性。为了满足这一需求，他们正在采用 [DevOps 实践](https://thenewstack.io/5-cloud-automation-tips-for-developers-and-devops/) —例如持续集成和持续交付(以及持续部署的相关实践)，统称为 CI/CD。

这些相互关联的流程使开发人员能够通过协调一致的自动化开发、测试、交付和部署来构建高质量的软件，从而确保 DevOps 团队在整个软件开发生命周期中实现更好的协作和更高的效率。

以下是您需要了解的关于这些软件开发实践的内容，它们之间的关系，以及它们如何使组织及其 DevOps 团队在推动优化和自动化更多 CI/CD 流程以及为客户实现更快价值的过程中受益。

## **持续集成解决开发难题**

根据德勤的说法，持续集成(CI)简化了内部软件开发的过程。CI 使从事同一应用程序的不同特性或模块的多个软件开发人员能够在完成更新时，将他们的更新分别提交到共享的代码存储库中，通常是一天多次。每次，构建管理系统都会自动创建一个构建并测试它。如果测试失败了，系统会通知团队修复代码，并将代码返回给他们。这种实践帮助软件团队快速检测并解决开发过程中出现的任何错误。

持续集成还防止了“合并地狱”，当两个或更多的开发人员无意中对代码进行了冲突性的更改，从而在将行合并回主分支时破坏了构建时，就会发生这种情况。协调大量冲突或冗余的代码需要冻结代码，甚至需要在管道中设置专门的集成阶段。

当软件开发团队不断地将增量更改集成到他们的构建中时，每个开发人员都可以自由地进行更改，而不用担心将其他人的工作偏离轨道，或者担心他们自己的工作被其他人踩在脚下。平滑、规则的合并免除了代码冻结，帮助开发人员更快、更有效地完成项目。它还确保始终有一个可测试的、最新的版本可以正确编译——这对于频繁而严格的应用程序测试至关重要。

这种方法节省了时间和资源，否则这些时间和资源将在软件开发生命周期的后期用于解决问题；或者更糟，释放后。一旦有问题的代码被发布到产品中并被构建，修复它的问题通常会困难得多。

## **连续交付有利于敏捷生产**

连续交付(CD)是一个过程，在这个过程中，DevOps 团队开发软件的完整部分，并在短时间内交付给一个存储库，如 GitHub 或容器注册表。持续交付旨在使发布成为 DevOps 员工的定期和可预测的事件；并且对最终用户来说是无缝的。持续交付的另一个目标是始终将代码保持在可部署的状态，这样更新可以在很少或没有问题的情况下即时生效。

DevOps 团队可以自动化 CI/CD 管道，在没有人工输入的情况下在适当的环境中移动代码，这加快了软件开发的构建、测试和部署阶段，或者他们现有的任何其他阶段，具体取决于他们使用的流程。

例如:当一个特性为客户演示做好准备时，DevOps 团队可以让一个 CD 工具自动将它部署到一个测试服务器上，这样客户就可以看到它是如何工作的，并在它发布到生产服务器之前提供反馈。

## **持续交付与持续部署:CI/CD 中孰轻孰重？**

如果 CD 代表持续交付*和*持续部署，当人们提到 CI/CD 实践时，它是什么？

简而言之，要么是持续投放；或者连续投放*和*连续展开。

您可以将采用这些实践视为 DevOps 自动化连续体中的三个步骤:

1.  **持续集成**简化开发，自动化构建和测试。
2.  **连续交付**将完成的代码块交付到主分支的过程自动化。
3.  **持续部署**为客户将完成和测试的代码部署到产品中的过程自动化。

当一个组织第一次开始采用敏捷开发运维实践时，他们通常从持续集成开始，并迅速成熟为持续交付——从而实现 CI/CD。许多组织止步于此，更喜欢手工发布产品代码。其他人进展到持续部署，因此他们可以自动化整个软件开发、交付和部署管道。

## **CI/CD 的优势**

CI/CD 减少了开发应用程序和特性所需的时间，与仍然采用手工方法进行软件开发的企业相比，为使用这种最佳实践的公司提供了竞争优势。

CI/CD 非常适合那些想要不断迭代和发布新特性的敏捷开发团队。这些实践确保每个人在编写和提炼代码时都使用相同版本的应用程序。随着管理和组织负担的自动化，工程师可以专注于他们最擅长的事情:编码。此外，如果团队已经实现了持续部署，他们的工作成果将花费更少的时间来等待测试和部署，而将更多的时间投入到生产中，从而加速来自用户的反馈，并(最终)改善业务成果。

提高的效率、缩短的上市时间和更快的创新使 CI/CD 对所有类型的组织都是一个有吸引力的提议。

## **推动更多 CI/CD 流程的优化和自动化**

为了满足竞争需求，组织知道他们必须比以往更快地发布新产品和服务，而不牺牲质量或可靠性。他们知道基本的 CI/CD 实践是 DevOps 计划的基础，这些计划旨在开发具有更有效协作和更高精确度的应用程序。

成功实施 CI/CD 实践的团队依赖于许多工具和方法来管理特性、版本、测试和构建。 [CI/CD 自动化](https://thenewstack.io/3-ways-to-use-automation-in-ci-cd-pipelines/)发生在流水线的每个阶段——从构建、封装和测试，到将应用程序推向不同的生产环境。

为了以更低的风险加速更快版本的开发管道，团队需要持续的自动化和高级人工智能驱动的可观察性，跨越他们 DevOps 工具链中的所有工具。这允许他们自动化手动步骤，并在软件生命周期的早期识别质量问题。

如果您的组织使用或正在考虑采用 CI/CD DevOps 流程，最佳实践是采用全栈可观察性平台，该平台可以提供您环境中所有软件版本、应用和服务的代码级可见性，无论它们是处于开发阶段还是部署到最终用户。通过在单个平台和共享数据模型上改进协作，您可以自动化手动质量验证流程，并确保您的整个团队在整个生命周期中持续了解情况。

有关持续集成和交付对 DevOps 的影响的更多信息，请观看我的公司如何为一家大型电信公司创建了一个[自动化、集成的应用交付管道](https://info.dynatrace.com/apm_wc_devops_journey_series_verizon_na_registration.html);或者查看本指南，了解[事件驱动、SRE 启发的 DevOps](https://www.dynatrace.com/news/blog/a-guide-to-event-driven-sre-inspired-devops/) ，提升您现有的 CI/CD 战略。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>