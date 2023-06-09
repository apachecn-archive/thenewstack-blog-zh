# 什么是零信任架构？|新堆栈

> 原文：<https://thenewstack.io/what-is-zero-trust-architecture/>

零信任架构(ZTA)建立在国家标准与技术研究所(NIST)在出版物 [800-207](https://csrc.nist.gov/publications/detail/sp/800-207/final) 中定义的[零信任安全](https://thenewstack.io/what-is-zero-trust-security/)的基本原则之上。NIST 建议关注用户、资产和资源，而不是传统的网络边界防御。

在最基本的层面上，它包含了一种设计哲学，在这种哲学中，任何事物和任何人都不能仅仅基于位置而被信任。为了对“什么是零信任架构？”这个问题给出一个答案我们必须首先了解安全设计的组成部分。

## 零信任网络架构

作为零信任网络体系结构(ZTNA)的关键支柱之一，最低权限安全的概念以完成所需任务所需的最低权限级别向关键网络资源分配访问凭证。在评估替代解决方案时，必须考虑识别关键的公司信息以及用户如何获得对该信息的访问权。

特权访问管理(PAM)，也称为特权身份管理(PIM)，可以使用公司目录产品(如微软的 Active Directory)来实现。微软最近推出了一款名为 Microsoft Entra 的产品，以解决多云环境中的身份和访问问题。PAM/PMI 类别中的其他供应商包括 Jumpcloud、IBM、Okta 和 Sailpoint。

如今，很少有企业网络在孤立的环境中运行。来回答“什么是零信任架构？”完全提问我们必须讨论如何允许外部用户连接到内部公司资源。传统上，这是通过使用虚拟专用网络(VPN)来实现的，需要正确的凭证来建立连接。添加额外的层，如双因素身份认证和网络隔离，有助于最大限度地减少由外部来源引入的潜在威胁。

## 安全管理

自动化在复杂网络的管理中至关重要。在零信任架构中，正确保护所有管理功能必须是重中之重。这可以通过多种方式实现。几年前，微软使用 PowerShell 脚本语言引入了及时(JIT)管理和足够管理(JEA)的概念。这个想法建立在最小特权的概念上，并添加了有时间限制的凭证。

Microsoft PowerShell 的另一项功能称为期望状态配置(DSC ),它利用 Windows 管理框架来配置和监控网络资源。DSC 支持内部网络和微软的 Azure 云环境。一旦实施了配置，称为本地配置管理器(LCM)的自动服务将根据位于单独的 DSC 服务器上的参考文件来验证本地系统。任何差异都会被记录下来，并提醒系统管理员采取进一步的措施。

类似的功能以开源软件(OSS)项目的形式存在于基于 Linux 的平台上，如 [Ansible](https://www.ansible.com/) 、 [Chef](https://www.chef.io/) 、 [Puppet](https://puppet.com/) 和 [SaltStack](https://saltproject.io/) 。所有这些工具都提供了类似于微软产品的功能，以实现最低权限管理和配置监控。了解您的基础设施的状态并确保它符合预定义的配置将在实现零信任架构的战斗中大有帮助。像对待软件开发一样对待基础设施配置，也要遵循基础设施即代码的概念。

## 持续网络监控

保护关键资产和资源需要持续监控和验证凭据。虽然传统上这是在网络边缘通过防火墙和入侵检测来实现的，但它也必须覆盖内部网络。从零信任体系结构的角度来看，它假设不良行为者可以访问内部网络，并且必须被阻挡在关键资源之外。

实现强大的边缘安全性仍然是任何防御策略的关键组成部分。虽然这从防火墙开始，但它还必须包括对外部连接的规定，如应用程序或电路级网关。这些产品提供了一种不仅仅是用户访问的外部通信途径。最新一代的防火墙产品实施了状态数据包检测(SPI ),根据非常具体的规则集来允许或阻止数据包。

保护内部资源需要一套完全不同的能力。像 [Crowdstrike](https://www.crowdstrike.com/) 这样的公司提供的产品涵盖了检测和保护企业网络内端点的所有领域。这将包括从反病毒和反恶意软件到异常网络活动监控的所有内容。微软、趋势科技和 SentinelOne 提供了类似的功能，并在其 2021 年终端保护报告中名列 Gartner 的上象限。

## 总结零信任架构

什么是零信任架构这个问题的真正答案取决于你最重要的公司资产。任何网络设计都应该考虑到能够访问这些关键资产的人员。信任但核实适用于公司员工以及地缘政治关系。

选择合适的供应商和合作伙伴来满足您的特定目标，将有助于您实施可靠的零信任架构。一旦实施，它归结为勤奋和坚持。新的威胁经常出现，必须用适应性的安全态势来应对。那些不适应不改变的人，注定会失败。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>