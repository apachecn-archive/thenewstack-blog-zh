# 高效云原生基础架构监控的七个步骤

> 原文：<https://thenewstack.io/seven-steps-to-effective-cloud-native-infrastructure-monitoring/>

数字企业继续转变和发展其 IT 基础设施，以提高与业务目标的一致性。数字服务中断可能会对销售、收入和公司声誉造成不利影响，因此团队面临着最大限度地提高整个体系的弹性和正常运行时间的压力。组织比以往任何时候都更需要全面的基础架构监控功能来保持可见性，并帮助他们的工程师在最终用户受到影响之前发现和解决问题。

## **基础设施监控的发展**

 [彼得·普茨博士

Peter 是 Dynatrace 的技术策略师。他在领导由科学家和工程师组成的国际软件项目团队以及管理复杂、创新的 IT 解决方案的整个生命周期方面拥有超过 15 年的经验。在加入 Dynatrace 之前，他是美国宇航局艾姆斯研究中心的高级科学家。](https://www.linkedin.com/in/pputz/) 

基础架构监控是整理和分析来自 IT 环境所有组件的指标、跟踪、日志和其他遥测数据的过程，以提供对可用性和性能的可操作见解。然而，随着云环境的复杂性和动态性的增加，实施有效的监控功能变得更具挑战性。

例如，在多云环境中，每个平台都配有来自公共云提供商的原生监控解决方案，该解决方案仅提供对其自身基础架构组件的可见性。因此，组织不得不拼凑各种工具，这造成了复杂性并阻碍了整个体系的端到端可见性。

有了正确的技术和配置，基础设施监控将改变游戏规则。它帮助团队发现和分析趋势，并在潜在问题破坏用户体验或违反服务级别协议(SLA)之前将其标记出来。它还可以支持 A/B 测试，这有助于团队确定性能和用户体验的最佳基础设施设置。高度自动化的监控解决方案可帮助团队减少浪费的手动流程，随着基础架构的增长轻松扩展，最重要的是，专注于创新而不是修复错误。

这里有七个最佳实践技巧，可以帮助基础架构团队设置和优化云原生监控功能。

1.  **尽可能实现自动化:**使用高度自动化的基础设施监控解决方案是大型动态环境的关键。监视功能的手动配置和仪表化是极其耗费人力的。团队发现自己无法检测基础设施的某些部分，并努力使监控代理保持最新。另一方面，自动部署、自动配置和自动基线使组织能够扩大他们可以捕获的指标的范围，消除盲点，并在云原生基础架构堆栈中实现端到端的可观察性。这带来了更高质量的监控能力，并产生了更精确的上下文洞察。借助增强的数据，团队可以更快地解决问题，从而带来更好的客户体验。减少人为干预可以为团队腾出时间，让他们专注于更具生产力的任务，从而加速转型和现代化计划。
2.  **投入时间配置警报:**有必要概述一下团队需要哪种警报，以便他们能够尽快发现问题。如果没有可靠的警报配置，团队在确定问题和确定多个警报是否与同一个问题相关时会变得不知所措。警报特异性提高了准确性，减少了误报。精心设计的警报机制可以减少响应时间，帮助团队更快地解决根本原因，从而提高正常运行时间。为了最大限度地提高效率，自动基线功能可以显著减少警报配置需求，能够自动消除误报，执行自动根本原因分析，并根据业务影响确定警报优先级。
3.  **创建优先级:**根据业务影响对警报进行分组有助于团队首先将精力集中在最严重的问题上。这种方法消除了判断通知重要性的猜测，节省了团队的时间和压力。还可以将警报发送到不同的频道。例如，一家公司可以将其 IT 服务管理(ITSM)系统配置为通过短信向待命工程师的智能手机发送高优先级警报，通过电子邮件发送低优先级问题。对于拥有 24 小时待命工程师的企业来说，优先化可以减少非工作时间的警报疲劳和团队中断。
4.  **设置定制仪表板:**通过创建特定于角色的仪表板，确保合适的人员能够访问他们所需的监控数据。组织中的不同团队可能出于不同的目的需要查看基础架构监控报告。例如，ITOps 工程师可能与 IT 安全团队、营销部门和业务主管有不同的关键绩效指标(KPI)。确定利益相关者认为哪些见解最有价值，哪些对他们的角色来说是不必要的。为每个组设置仅显示相关数据的自定义仪表板。(但是，关键是所有仪表板的底层数据是一致的，并且基于相同的数据模型。)
5.  **测试系统:**在没有彻底测试之前，大多数企业绝不会推出一个系统或部署一项重大变更。基础设施监控也不例外。确定最有可能出现的情况并设计测试框架，以确保基础设施监控解决方案按预期运行。最安全的方法是在指定的测试环境中进行，以防止生产和客户受到影响。然后，团队可以微调设置和警报配置，以确保一切按预期运行。
6.  **定期检查指标和 KPI:**目的和目标不断发展，因此定期检查指标以确保基础设施监控解决方案生成每个利益相关方需要的数据和见解至关重要。评估 KPI 并与团队一起确定未来要建立的新基准也是有益的。随着组织在数字化转型之旅中走得更远，新的基础架构盲点将会出现。定期指标审查可以避免无意的疏忽，并确保在整个基础架构体系中保持全面的可见性。
7.  **利用供应商的专业知识和资源:**努力完善监控设置或缺乏内部专业知识或经验的组织可以寻求供应商的支持。供应商专家将拥有行业最佳实践方面的专业知识，并熟悉团队正在努力解决的问题。利用供应商的专业知识可以帮助团队更快地实现其监控目标，同时也增强了内部技能。

## **基础设施监控的可扩展方法**

随着组织继续向现代多云环境过渡，最大限度地提高正常运行时间和弹性对于确保业务连续性和客户满意度比以往任何时候都更加重要。部署合适的监控解决方案以满足基础设施性能的明确战略目标，可以让团队获得最大的成功。对于许多人来说，最有效的方法是实施一个统一的平台，该平台可以在一个位置提供对所有云环境的观察能力。这有助于团队更有效地协作，充分利用他们的时间。通过将 AIOps 驱动的自动化与这些功能相结合，组织可以为基础设施监控设计一个可扩展的框架，该框架将随着业务的发展而增长，从而为创新和进一步转型创造更多空间。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>