# 以下是如何驯服您的 API 蔓延——以及为什么您应该这样做

> 原文：<https://thenewstack.io/heres-how-to-tame-your-api-sprawl-and-why-you-should/>

[“API 蔓延”](https://thenewstack.io/six-signs-youve-got-an-api-sprawl-problem/)指的是组织内 API 环境的快速和不受控制的增长。当一个组织有许多管理不善或根本没有管理的连接点时，就会出现这种情况，导致 API 激增，难以维护和使用。

这种蔓延是[规模扩张的副作用，](https://thenewstack.io/the-exploding-endpoint-problem-why-everything-must-become-an-api/)而且也不全是坏事。但是每个组织的 API 数量正在快速增长。例如，在 2020 年底，SaltSecurity 调查的组织平均报告了 42 个 API。2022 年 7 月，同样的调查[发现其受访者平均保持 162 个 API。](https://content.salt.security/state-api-report?utm_source=website&utm_medium=homepage&)

但是，如果有太多的 API 需要有效地跟踪和管理，API 蔓延也会增加安全风险，增加维护需求，并对工作效率产生负面影响。

通过制定清晰的 API 策略并建立管理和记录 API 的流程，组织可以公开多种功能，同时避免 API 蔓延带来的负面影响。这就是为什么你需要那个策略和那些过程，以及创建它们的一些初始步骤。

## API 蔓延的好处和坏处

API 蔓延是有益的，因为它允许组织构建若干功能，并向外部开发人员或组织内的不同团队公开这些功能。这可以带来更多的创新和更快的开发时间，因为团队可以轻松地访问和使用 API 提供的功能，而不必从头开始构建那些连接点。

还有更大的灵活性。通过访问大量 API，组织可以更加灵活地构建和部署新系统和服务。这可以让他们更快地响应不断变化的业务需求，适应新技术。

然而，API 蔓延也会带来负面后果。对于众多的 API，开发人员可能很难理解哪些是可用的，如何使用它们，以及它们如何适应组织的整体架构。这可能导致混乱和低效，并使团队难以有效地合作。

一个庞大的 API 集合会导致功能的重复和接口设计和实现方式的不一致。这可能会减缓发展。

最糟糕的是，如果 API 数量太多而无法正确管理，以至于无法跟踪哪些 API 正在被使用，以及被谁使用，那么 API 可能会带来安全风险。2022 年第三季度的 SaltSecurity 调查发现，94%的受访者报告在生产 API 中存在 API 安全问题。

最后，一个组织拥有的 API 越多，就越需要持续的维护。更多的 API 意味着生成更多的代码来保持更新，导致成本增加。

## 与 API 蔓延相关的安全风险

对于组织来说，确保所有的 API 都有适当的安全控制是一项挑战。对于大量的 API，组织可能很难监控哪些 API 正在被使用，以及被谁使用。此外，识别安全问题和快速响应事故也很困难。

一个或多个 API 包含可被恶意参与者利用的漏洞的可能性增加了。这可能导致数据泄露和其他安全事故。

有了这么多的连接点，黑客还可以通过查找和使用不再使用或没有得到适当保护的 API 来利用 API 蔓延。这使得他们能够未经授权访问敏感数据或系统而不被发现。

网络犯罪分子可能会以非预期的方式使用 API，例如发送过多的请求或使用 API 抓取数据。

好心的开发人员犯错误的危险也增加了。如果他们不能理解组织中的 API 情况，他们可能会产生具有安全隐患的错误。

## 集权与分权

在设计 API 管理策略时，您需要决定是集中还是分散对 API 的控制。以下是你应该权衡的因素。

API 集中化涉及到拥有一个单一的系统来监督对组织的所有 API 的访问。相反，API 去中心化意味着一种更加分布式的方法，不同的团队或部门管理他们自己的 API。

集中 API 有助于减少 API 蔓延，使监督和记录它们变得更简单，还可以设置安全协议和跟踪 API 使用情况。然而，它也可能有缺点，例如通过施加太多的限制来减缓发展进程和抑制创新。

然而，分散 API 允许更大的灵活性和更快的开发，因为团队能够创建和部署 API，而不需要通过中央过程。另一方面，它可能导致 API 蔓延，因为对 API 的开发和部署的监督和控制可能会更少。

根据组织的特定需求和目标，最好选择将集中和分散结合起来的混合方法。

例如，虽然对组织运作至关重要的核心 API 应该集中管理，但分散控制可能更适用于不太重要或实验性的 API。

## 创建应对 API 蔓延的策略

创建有效的 API 策略对于确保 API 以符合组织目标的方式构建是至关重要的。这应该包括为 API 设计和文档建立标准，建立 API 治理策略，以及为 API 管理分配角色和职责。

### 盘点一下。

您首先需要确切地知道您的组织当前有多少 API 以及有哪些 API。文档可以帮助开发人员理解每个 API 的功能、用途以及与之相关的任何需求或限制。

### 建立原料药的修订程序。

进行审查和淘汰不再使用的 API 有助于防止蔓延和降低维护成本。这可以包括对组织的 API 环境进行定期审核，以识别和丢弃任何不必要的或重复的 API。

建立一个系统来批准和发布新的 API 是必要的，以保证只有需要的 API，这些 API 被适当地记录，并提供给开发者。这应该包括新 API 的评审过程，以及命名、版本控制和 API 文档化的规则。

### 监控您的 API 活动。

监视 API 的使用可以提供关于哪些 API 正在被使用以及被谁使用的洞察，有助于识别任何不再需要的 API。

### 利用 API 网关的力量。

API 网关也称为多重网关，是强大的软件系统，为组织的连接点提供集中控制。此类网关用于管理、保护和提供 API 的附加功能，如路由、负载平衡和缓存，从而增强 API 性能并减少后端系统的压力。

API 网关的优势之一是集中管理。它们为组织内的所有 API 提供了方便的集中控制，使管理和记录这些连接点、设置安全控制和监控 API 使用变得更加容易。

API 网关还可以执行安全措施，例如[认证、授权、](https://thenewstack.io/how-do-authentication-and-authorization-differ/)和加密，以防止任何对 API 和机密数据的未授权访问。

对于开发人员的生产力来说，API 网关可能是最好的，它为开发人员提供了使用和访问 API 的单一访问点，使得团队之间的协作更加容易。

## “左移”也适用于 API 测试

谈到安全性，你可能听说过[“左移”哲学:](https://thenewstack.io/shift-left-where-cloud-native-computing-security-is-going/)这意味着在应用构建过程的开始，将应用安全性的更多责任放在开发人员的肩上，而不是完全依赖运营工程师来保证代码安全。但是“左移”也适用于 API 测试和质量保证(QA)任务。

下面是如何做到这一点:

### 建立持续测试的流程。

Shift left 需要尽早和经常地进行测试，所以在开发过程中创建一个持续测试 API 的系统是非常重要的。这可能涉及到设置每当您修改 API 时运行的自动化测试，或者频繁地手工测试 API。

### 实现单元测试。

单元测试是一种自动化的测试形式，它验证不同代码单元的行为。通过在开发过程的早期生成单元测试，您可以更早地发现问题，并减少在测试的后续阶段出现意外问题的风险。

### 使用模拟 API。

通过使用真实 API 的模拟版本，您可以测试连接点的行为，而无需依赖外部依赖或实际数据。

### 执行用户验收测试。

用户接受度测试是测试一个 API 以保证它满足目标用户的需求和愿望的过程。通过在开发过程的开始进行用户验收测试，您可以发现 API 的可用性或操作的任何问题，并在部署之前解决它们。

### 为原料药规定明确的验收标准。

在您开始构建 API 之前，请确保您清楚地了解 API 应该做什么以及它应该如何出现。这将帮助您从一开始就设计和构建更好的 API。

### 使用自动化测试工具。

自动化测试工具可以帮助你更快更有效地测试你的 API。考虑使用诸如[詹金斯、](https://thenewstack.io/4-power-tips-to-get-jenkins-enterprise-ready/)波兹曼或 SoapUI 之类的工具来自动化你的测试过程。

### 在 API 开发过程中包括 QA 人员。

确保你的 QA 团队从一开始就参与到 API 开发过程中。它们可以帮助检测潜在的问题，并提供关于 API 设计和实现的重要反馈。

总的来说，shift left 的目的是在开发过程中尽可能早地发现错误，这样就可以在它们给下游带来重大问题之前将其解决。通过在开发过程的早期实现这些测试活动，您可以提高预生产 API 的质量和可靠性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>