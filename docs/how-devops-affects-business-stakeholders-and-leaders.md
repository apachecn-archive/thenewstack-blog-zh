# DevOps 如何影响商业利益相关者和领导者

> 原文：<https://thenewstack.io/how-devops-affects-business-stakeholders-and-leaders/>

[](https://www.linkedin.com/in/emrahsamdan/)

 [埃姆拉·萨姆丹

艾姆拉是桑德拉公司的产品副总裁。他热衷于无服务器、可观测性和混沌工程。](https://www.linkedin.com/in/emrahsamdan/) [](https://www.linkedin.com/in/emrahsamdan/)

承诺，承诺，承诺。DevOps 流程，特别是持续集成/持续部署(CI/CD)管道，*承诺*巨大的商业价值。通过缩短新产品和新功能的上市时间，它们可以帮助组织有效地、创新地满足不断变化的市场需求。获取的价值可以是直接的(如增加收入)和间接的(如提高客户满意度)。

但是非技术业务利益相关者如何理解 DevOps 是否正在为他们的组织*实现它的承诺？答案在于跟踪正确的 DevOps 关键绩效指标(KPI ),也许最重要的是，在有意义的上下文中呈现它们。*

本文着眼于要监控的最重要的 DevOps KPIs，以及应该如何将它们呈现给业务涉众，以便他们可以做出明智的决策。

## DevOps 生态系统

软件开发的敏捷方法，强调灵活性和快速迭代，在世纪之交就已经出现了。然而，到 2008 年，具有前瞻性思维的工程师们试图[打破开发和运营之间的壁垒](https://cdn.ttgtmedia.com/rms/onlineImages/whatis-devops_over_time-f.png)，并将敏捷方法应用于应用程序开发和基础设施问题。这种新方法被称为 DevOps，它慢慢地获得了关注。Forrester Research 宣布 2017 年为“开发运维年”已经过去了近十年，届时将有 50%的组织实施开发运维计划。

在 DevOps 模型中，开发和运营团队——通常还有 QA 和安全团队——在从开发/测试到生产的整个应用生命周期中紧密合作。开发运维团队使用的技术和工具支持自助式资源调配，以及传统手动流程的自动化。

除了云服务提供商提供的云原生 DevOps 堆栈，市场上还有许多工具。DevOps 生态系统中的领先工具包括 [Docker](https://www.docker.com/) 和 [Kubernetes](https://kubernetes.io/) ，用于容器管理和编排； [Git 和 GitHub](https://github.com/git) 用于源代码控制；用于 IT 自动化和配置管理的[詹金斯](https://www.jenkins.io/)、 [Ansible](https://www.ansible.com/) 、[主厨](https://www.chef.io/)和[傀儡](https://puppet.com/)； [Splunk](https://www.splunk.com/) 、 [Prometheus](https://prometheus.io/) 、[桑德拉 APM](https://www.thundra.io/apm) 用于记录、监控和可观察性； [ServiceNow](https://www.servicenow.com/products/itsm.html) ，[吉拉](https://jira.atlassian.com/)为其售票；还有更多。

## 反映 DevOps 值的 KPI

一般来说， [KPI 提供了可量化的、客观的进度证据](https://devops.stackexchange.com/questions/738/what-key-performance-indicators-kpis-are-used-to-measure-devops),有助于实现预期的业务绩效结果。无论是用于衡量投入、流程、产出还是结果，关键绩效指标都有助于制定明智、分析性和有针对性的决策流程。当然，重要的是要记住 KPI 是达到目的(即提高绩效)的手段，而不是目的本身。你不希望团队专注于产生好的 KPI“分数”，而不是提供好的产品和服务。

考虑到这一点，这里有一些可量化的 DevOps KPIs，让业务利益相关者能够洞察他们的 DevOps 活动的有效性。

### 部署频率和新请求交付时间

部署频率衡量一段时间内的部署量，而交付周期则衡量新功能或产品从请求到实现所需的总时间。

通过在 CI/CD 管道末端配置一个 webhook，可以相对容易地测量部署频率，只要部署发生，web hook 就会自动增加。新产品/功能的交付周期可以通过组织的项目管理平台进行跟踪。

这两个 KPI 共同提供了对组织的 DevOps 工作流的速度和生产力的重要见解。部署频率的降低和/或交付时间的增加可能表明存在阻碍进展的瓶颈。一般来说，业务涉众应该寻找这些指标的适度但稳定的改进。

### 部署失败率

如果在部署到产品中时失败率很高，那么高的部署频率和短的项目交付时间就毫无意义。

在战术层面上，部署失败率是通过跟踪批量部署导致系统停机或变慢或者需要后续修复甚至回滚的频率来衡量的。在更具战略性的层面上，跟踪有多少代码提交甚至没有进入生产环境也是很有价值的。

如果这些战术和战略失败率指标在增加，业务领导应该考虑缩减开发运维活动，直到发现并解决潜在问题。

### 变更数量和变更请求交付时间

第一组 KPI 处理部署频率和将新请求投入生产的交付时间，这组 KPI 测量部署之间的变更请求*的数量，以及将它们投入生产需要多长时间。*

为了衡量这些 KPI，重要的是将每个补丁、错误修复和其他补救作为统一开发和运营工作积压中的离散工作单进行跟踪。然后，可以使用 webhooks 在成功部署后自动关闭票证，从而跟踪它们的总容量以及每个票证的生命周期。

尽管批量部署之间的频繁更改表明 DevOps 在性能和安全问题上处于领先地位，但不断增加的更改量可能表明主要部署正在匆忙投入生产。变更请求交付周期是组织开发运维工作流效率的重要衡量标准。

### 服务水平协议中的可用性和性能

组织对应用程序可用性(正常运行时间)和性能目标(错误率、响应时间等)有正式或非正式的目标。).验证组织的 DevOps 实践至少不会成为满足现场可靠性工程正常运行时间和性能要求的障碍，这一点非常重要。理想情况下，开发运维工作流应该能够优化和提高应用和服务的可靠性，以及最终用户体验。

目前有许多 IT 监控方法和工具用于跟踪应用程序的可用性和性能。例如，黑盒监控使用模拟的用户代理来获取性能指标。

这些受监控的 KPI 应该显示一致的可用性和性能指标，满足或超过组织定义的目标。同样值得注意的是，应该在整个应用程序生命周期中监控这些指标，而不仅仅是在生产环境中。

### 平均恢复时间

无论一个组织的环境有多好，生产中的应用程序和服务都不可避免地会停机和变慢。设计良好且实施稳健的开发运维实践应支持快速平均恢复时间(MTTR ),最大限度地减少应用或服务功能的丢失或缓慢访问。例如，像[桑德拉 APM](https://blog.thundra.io/the-serverless-path-to-devops) 这样的 DevOps 工具有助于通过自动化分布式跟踪和产品调试来减少 MTTR。

由组织的 ITSM 系统测量的 MTTR 度量提供了关于组织如何满足其 MTTR 基线的宝贵见解。组织应该期望其开发运维实践能够提供一致的 MTTR，最大限度地减少放弃应用或服务的用户数量。

### 缺陷量和逃逸率

组织不希望用户感觉他们是组织的 QA 团队的一部分，因为他们识别并报告运行时缺陷。业务利益相关者希望 DevOps 工作流支持低缺陷逃逸率，即最终用户发现的缺陷数除以 QA 在生产前发现的缺陷数。收集该 KPI 指标的一个非常简单的方法是跟踪客户票证和 QA 打开的与 bug 相关的票证。

这里重要的是商业利益相关者*而不是*期待无缺陷的应用程序。这将是一个很好的例子，说明一个使用不当的 KPI 指标会如何阻碍创新和限制部署速度，破坏 DevOps 本来要支持的业务目标。

## 理解 KPI 数据

非技术业务利益相关者需要强大的报告和可视化工具，这些工具可以分析 DevOps KPI 指标并将其关联到图表、图形和表格中，这些图表、图形和表格可以清楚地显示在哪些地方达到了预期基线，在哪些地方超过了预期基线，以及在哪些地方没有达到预期基线。这些资源将在逐个项目的基础上向业务领导展示他们当前的 DevOps 实践是加速还是限制了业务成果。

可视化工具的一些例子有:

*   来自精益制造和敏捷软件开发的世界，[看板](https://www.atlassian.com/agile/kanban/boards)被设计用来可视化工作，优化正在进行的工作，并最大化工作流程的效率。
*   票务软件平台，如吉拉和 ServiceNow，带有内置的看板和其他工具，这些工具可以可视化许多自动化 DevOps 工作流核心的票务活动的数量和速度。
*   Trello 和 Asana 等协作工具可以与 DevOps 工作流集成，自动向整个组织的相关利益相关者提供报告和警报。
*   Datadog、Grafana 和 Tableau 软件等仪表板解决方案将大数据转化为商业智能，是向决策者提供可操作的 DevOps KPI 见解的重要工具。

## 最后一点

在当今的应用程序架构中，上面讨论的所有 DevOps KPIs 都更加难以监控和评估，这些应用程序架构通常部署在多种环境类型中。考虑到这一点，我们在[桑德拉](https://www.thundra.io/?utm_content=inline-mention)提供[桑德拉 APM](https://www.thundra.io/apm) ，这种 APM 从一开始就被设计为提供可观察性、监控和仪表板功能，使业务领导能够洞察他们公司的 DevOps 实践，以及他们是否正在交付预期的业务价值。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>