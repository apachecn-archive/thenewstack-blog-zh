# 在代码库猎场发布私钥

> 原文：<https://thenewstack.io/posting-private-keys-in-the-code-repository-hunting-grounds/>

在一切可编程的新世界中，密码肯定不是自动化规模的强大访问控制的可行工具。配置文件包括公共 ssh 密钥，用于远程安全地配置、访问和管理基础架构、平台和应用。

但是如果暴露不当，钥匙就一文不值了。开发人员有时会无意中在 Git repos 中发布他们的私钥，任何人都可以看到。上周，一名开发人员使用简单的技术和总共不到 80 行的代码，称他通过使用 Github Search 在两个小时内访问了 5 台亚马逊 EC2 服务器。

攻击者总是在寻找链条中最薄弱的一环。如果一个简单的搜索或一个小脚本可以在几分钟内完成一个公共代码库 API 来提取数百个私有密钥，为什么要在有针对性的攻击上花费时间和精力呢？将这一点添加到公共云提供商的模式或预测输出中，你可以将这两者结合起来，彻底改变自动化，做真正*真正*糟糕的事情。将这种攻击隐藏在 DDoS(分布式拒绝服务)背后，业务就会崩溃——看看 codespaces.com。

虽然公共“云”服务可以提供这种攻击的规模和深度，但这种情况在私有的 API 中同样是可能的。需要一个勇敢的企业 CSO(首席安全官)来证明跨整个终端或服务器的零妥协环境。因此，暴露敏感访问控制数据的风险及其对私有代码库的影响是相同的。

### 开发者意识

第一道防线永远是开发人员，他们处理敏感的访问数据，比如他们的私钥。很明显，Github 详细地强调了开发人员的风险。Github 有[详细的指导方针](https://help.github.com/articles/remove-sensitive-data)来做到这一点，尽管是在`Advanced Git`下。`.gitignore`的重要性怎么强调都不为过。

> > 危险:一旦你向 GitHub 提交了一个 commit，你就应该考虑到它包含的任何数据都会受到威胁。如果您提交了密码，请更改它！如果您提交了一个密钥，请生成一个新密钥。
> > 
> > 

### 安全 API 设计

虽然人类并不完美，但 API 肯定可以努力做到完美。虽然安全 API 设计指南旨在保护实际的 API 服务免受安全攻击，但是设计还应该考虑它所呈现的数据，并且不响应敏感的数据请求。像`.pem`和`BEGIN RSA PRIVATE KEY`这样明显的搜索关键词不应该从公共代码库中提取任何结果，除非有例外。

SecOps 通常倾向于遵循 DevOps，并且它们可能主要被法规遵从性要求和清单所耗尽。在安装下一代应用安全防火墙来防御 APTs(高级持久威胁)之前，使用错误提交给代码存储库的私钥的脚本可能会危及或破坏整个企业的关键基础设施，这种可能性非常小。

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/111692634@N04/11407106173/in/photolist-dxdmTX-5R7rco-cvNwF3-iuSuaX-7sNKjK-dGiyJX-dPcqJ1-gtrQKZ-gwUHSX-8TnkqM-9TfRmX-64tcvq-2bQaJ-5CZdrC-JuSvG-7ULkET-64tcgY-64kQmM-inZJqm-io1pfn-795oXP-64kQbn-64r7wb)