# 过多的访问是你的库本内特公司的致命弱点

> 原文：<https://thenewstack.io/too-much-access-is-your-kubernetes-achilles-heel/>

**目标**。现在是 2013 年，塔吉特是微软的一个大客户，使用 [Azure](https://thenewstack.io/azure-went-dark/) 和其他来自 Redmond 的服务，并有一个非常详细的在线案例研究。攻击者意识到，凭借其 300 人的安全团队，Target 可能不是直接攻击的最佳目标。

相反，攻击者将注意力集中在一家合作公司，一家供暖、通风和空调(HVAC)维修公司，并诱骗其一名员工提供登录详细信息。据开源身份管理和访问公司 [Infra](https://infrahq.com/) 的开发者和技术传播者[马特·威廉姆斯](https://www.linkedin.com/in/technovangelist/)称，攻击者利用这个机会在目标系统中放置了一个木马。

威廉姆斯在上周的 Civo Navigate 会议上告诉观众:“这个维修 HVAC 公司的员工可以登录到相同的目标系统，并有可能访问许多其他有趣的信息。”。"他们开始查看所有的记录，开始收集所有的东西."

威廉姆斯说，安全部门已经注意到了这个问题，但是他们关闭了自动修复，因为他们认为应该有人参与这种情况。

“这些黑客能够花一些宝贵的时间从网络上窃取信用卡和各种其他信息，”他说。“他们在两周内抓取了大约 11gb 的数据——他们在那里呆了两周！…这导致大约 4000 万张信用卡、借记卡和 7000 万名客户的信息全部被这些黑客窃取。”

他补充说，总计攻击目标的成本估计为 2.91 亿美元。首席信息官辞职，90 多起诉讼被提起，而且，自从攻击的消息在圣诞节公之于众后，销售额下降了。

**万豪**。现在是 2018 年，这家连锁酒店刚刚完成了与喜达屋地产的合并，其中包括西方、喜来登、威斯汀、W 和圣瑞吉斯等酒店。在攻击被发现之前，一名用户在万豪[酒店](https://thenewstack.io/the-newest-remote-working-alternative-working-from-hotels/)受到威胁，信用卡等个人信息在四年内被盗。威廉姆斯说，攻击者几乎可以以管理员身份访问任何东西。

“数以亿计的客户记录丢失了，”威廉姆斯说。“很明显，2014 年，这种违规行为确实发生过，并且一直在被利用……他们在那里待了四年，抢东西。”

### '不要向任何人授予群集管理访问权限'

这两个案例都显示了当 IT 对文件权限不严格时会发生什么，这对于 Kubernetes 来说是一个特殊的挑战，因为在 Kubernetes 中,[集群管理员](https://thenewstack.io/managing-access-to-all-your-clusters-at-scale/)角色拥有全权。

“你可以做任何你想做的事。你可以改变秘密。您可以删除节点。您可以删除集群。威廉姆斯说:“你可以用它做任何事情。“你可以大肆破坏。太牛逼太可怕了。”

他的解决方案是:不要给每个人或任何人集群管理员权限。

他说:“我知道拿走群组配置文件很容易，只要和你所有的朋友分享，让每个人都可以访问就行了。”

通常，这是因为开发人员试图快速部署，而没有设置适当的权限。他们可能有最好的意图在以后锁定访问。他们就是不知道。

“Security Magazine 上有一篇文章讨论了如今违规的成本；在 20-21 年度，平均花费是 424 万美元。这比我们看到的塔吉特百货或[万豪酒店](https://www.politico.com/story/2018/12/12/pompeo-says-china-hacked-marriott-1059172)的 3 亿美元少了很多，但这仍然是一大笔钱。"

他说，发现漏洞的平均时间是 212 天，处理它需要将近一年的时间，平均 286 天，因此，从漏洞到遏制平均 498 天。与此同时，被发现的违规行为被起诉的可能性为 0.05%，这意味着攻击者尝试的风险很小，但有可能通过盗窃或赎金获得大笔支出。

## Infra:一个开源工具

Williams 向观众介绍了设置适当权限所需的七个繁琐步骤。成为 Kubernetes 的用户需要一个证书，你可以花所有的时间给用户发权限，尤其是在大公司。

然后他演示了如何使用免费的开源工具[来自动化和管理](https://github.com/infrahq/infra)[认证过程](https://thenewstack.io/what-do-authentication-and-authorization-mean-in-zero-trust/)。它使用下拉菜单和更直观的用户界面。它还可以删除用户的访问权限。

“如果我意识到(这个人)是个白痴，我们应该除掉他，那么我就删除访问权限，”他说，并补充道，“你的 SSH 也有同样的选项。”

Civo 支付了 Loraine Lawson 参加会议的差旅费和住宿费。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>