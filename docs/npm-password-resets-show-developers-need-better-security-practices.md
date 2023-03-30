# Npm 密码重置表明开发人员需要更好的安全实践

> 原文：<https://thenewstack.io/npm-password-resets-show-developers-need-better-security-practices/>

自 5 月份以来，数千名在 npm 存储库中发布 JavaScript 包的开发人员的密码被重置，因为他们的登录凭证太弱或已被公开暴露。受影响的帐户控制着数以万计的 Node.js 模块，而这些模块又直接或间接依赖于整个 npm 生态系统的一半。

该事件强调了为什么开发人员需要改进他们的安全姿态和实践，特别是因为据估计，任何现代应用程序中有超过 80%是由开源代码组成的，其中大部分是从组件库中消耗的。

作为 Node.js 模块的主要来源，npm registry 托管了近 50 万个 JavaScript 包——世界各地的开发人员使用这些构建块来开发从网站和移动应用程序到控制物联网设备和机器人的 API 的一切。

npm 注册表中的许多可用包通过一个复杂的依赖系统相互连接。如果恶意代码进入其中的一个，感染可能会蔓延到成千上万的其他软件包，并可能蔓延到数百万个最终用户应用程序。

这个系统的脆弱性的一个例子发生在 2016 年 3 月，[关于一个包的名称的争议](https://thenewstack.io/the-kik-kerfuffle/)导致一个开发者没有从公共 npm 注册中心发布他的所有包，包括一个叫做 left-pad 的小包。这个[引发了数千个其他软件包失败的连锁反应](http://blog.npmjs.org/post/141577284765/kik-left-pad-and-npm)，这些软件包要么直接依赖于 left-pad，要么正在使用依赖于 left-pad 的软件包。这一事件在社区中被称为 npm-gate。

软件供应链自动化公司 [Sonatype](https://www.sonatype.com/) 的联合创始人兼首席技术官[布莱恩·福克斯](https://twitter.com/brian_fox)说:“正如我们在#npmgate 中看到的，随着左 pad 的移除，即使是很小的组件也可以对整个生态系统产生巨大的影响。“当开发人员选择发布他们的作品时，他们正在承担一种非同寻常的责任，通常是在不知不觉中。他们在选择如何保护其凭证时需要考虑这一点，因为他们面临风险的不仅仅是自己；如果它们遭到破坏，整个生态系统都会面临风险。”

## 最近的国家预防机制问题

Npm 公司。运行 npm 注册中心的公司[在 6 月初宣布已经重置了 1000 多名开发者的密码和授权令牌。这一决定是在该公司接到一名独立研究人员的通知，称许多 npm 账户凭证可从其他网站的数据泄露中获得之后做出的。](http://blog.npmjs.org/post/161515829950/credentials-resets)

事实证明，开发者在多个在线服务中使用了同一个密码，其中一些人的用户数据库被黑客窃取并在网上发布。

但是密码重用并不是唯一的问题。向 Npm 报警的独立研究员是尼基塔·斯科沃罗达，他是 Node.js 核心技术委员会的成员[。后来，他在自己的 GitHub 页面上发表了一篇关于 npm 凭证安全性的研究报告。](https://github.com/nodejs/node#current-project-team-members)

Skovoroda，在开发者社区中被称为 [ChALkeR](https://github.com/ChALkeR) ，声称自 5 月以来，他使用多种方法成功获得了 16427 个 npm 账户的有效密码和认证令牌。

账户所有人自己将一些证书纳入了他们的国家预防机制包。其他凭证已经上传到公共 GitHub 库，保存在公共 CI 日志中，粘贴到 [GitHub Gist](https://gist.github.com/) 或类似的地方。

一些帐户的密码很弱，使用标准的暴力破解技术很容易猜到，但其中最大数量的帐户(12，710 个)的密码由于第三方的破坏而可以在网上获得。

受影响的帐户直接控制 72，298 个软件包，约占 npm 注册表的 14%。然而，ChALkeR 在他的详细报告中说，由于依赖性，潜在受影响的软件包总数超过了生态系统的一半。

为了客观地看待问题的规模，40 个受影响的帐户拥有每月总计超过 1000 万次下载的软件包的发布权。有 13 个用户访问了每月下载量超过 5000 万次的包，4 个账户来自前 20 名。一些人的密码非常不安全。

ChALkeR 说:“其中一个可以访问 publish koa(一个流行的框架)的密码是字面上的‘password’。”他补充说，还有 123 个其他帐户也使用‘password’作为他们的密码。他说，另外 174 名开发者使用了密码“123”，662 名使用了“123456”，1409 名使用了相同的密码作为用户名。

即使在他们的密码被重置后，一些用户也没有把这个问题看得太重。根据研究人员的说法，一个软件包每月下载超过 2000 万次的用户决定“改进”他们以前泄露的密码，只添加！人物在最后。与此同时，前 20 名用户之一在重置后将其旧密码重置，但 Npm 再次强制重置。

值得称赞的是，该公司已经采取了预防措施。现在，它会自动撤销包内硬编码的凭据，并强制执行阻止使用弱密码或普通密码的密码要求。

Npm 还[放弃了一些 API 端点的基于密码的认证](http://blog.npmjs.org/post/160809090595/basic-auth-to-be-limited-soon),转而支持更容易撤销的无记名令牌，并且还实施了暴力保护和其他滥用监控系统。

## 这是一个更大的问题

糟糕的密码卫生和硬编码凭证是过去影响多种技术和开发人员社区的问题。2014 年，一名研究人员在 GitHub 的公共项目中发现了近 10，000 个亚马逊网络服务和弹性计算云的访问密钥。

然后在 2015 年，一个来自德国的学术研究团队发现了来自 Parse、CloudMine 或亚马逊 Web 服务等提供商的后端即服务(BaaS)框架的访问密钥，这些密钥被硬编码到数千个移动应用程序中。这些凭证[提供了对存储在后端数据库中的 5600 万个数据项](https://www.blackhat.com/docs/eu-15/materials/eu-15-Rasthofer-In-Security-Of-Backend-As-A-Service-wp.pdf)的访问，包括车祸信息、用户特定位置数据、生日、联系信息、电话号码、图片、有效电子邮件地址、购买数据、私人信息、婴儿成长数据，甚至整个服务器备份。

去年，来自网络安全公司 [Detectify](https://detectify.com/) [的研究人员在 GitHub 项目](https://labs.detectify.com/2016/04/28/slack-bot-token-leakage-exposing-business-critical-information/)中发现了超过 1500 个 Slack 访问令牌，这些令牌提供了对属于支付处理商、ISP、学校、广告公司、报纸、医疗保健提供商和其他处理敏感数据的公司的 Slack 团队账户的访问。其中一些团队帐户包含带有敏感凭据的共享文件、CI 平台和其他内部服务和数据库的登录信息、私人聊天日志等。

Detectify 的安全顾问 Frans Rosén 说，弱密码问题可以很容易地得到解决，看起来 npm 已经解决了这个问题。他补充说，通过 CI 日志暴露凭据的问题也在一定程度上得到解决。“我知道 TravisCI，它有开源项目的公共 CI 日志[对他们的日志](https://blog.travis-ci.com/2017-05-08-security-advisory)进行了更改，对他们的令牌清理更加严格，因为他们确实错过了很多时间。这更多地与 GitHub 令牌有关，但 npm 令牌也在那里。”

然而，根据 Rosén 的说法，由于 npm 模块之间复杂的嵌套依赖关系树，一些风险将始终存在。这创造了一个“对等网络”,开发者需要在他们的应用程序中信任这个网络，其中的任何一个对等点都可能是一个薄弱环节。

而且开发者要担心的不仅仅是凭证泄露或者凭证薄弱的问题。他们的工作计算机的任何损害也可能被攻击者滥用来对他们的代码进行恶意修改。

2013 年，[一群黑客](https://securelist.com/wild-neutron-economic-espionage-threat-actor-returns-with-new-tricks/71275/)入侵了一个受欢迎的 iOS 开发论坛，并通过当时未打补丁的 Java 漏洞让访问者的电脑感染了间谍恶意软件。那次攻击影响了许多大公司的开发者，包括 Twitter、脸书和苹果。

Sonatype 的 Brian Fox 说:“新的现实是，开发人员自己也站在现代安全攻击的前线。“他们的系统如果遭到破坏，可能会在不知不觉中向其组件的批准和批准版本中注入恶意软件。”

Sonatype 托管的大型 Java 组件中央存储库要求开发人员使用 GPG 密钥来签署他们的发布。这增加了针对恶意修改的另一层防御，以及验证新组件版本真实性的方法。

“这是存储库的一个未被充分利用的功能，因为大多数消费者都懒得去验证，”Fox 说。"然而，它在各种甚至不提供类似保护的组件库中脱颖而出."

存储库可以受益的另一个安全特性是双因素身份验证。这种机制要求用户除了密码之外还要使用一次性代码进行身份验证，尤其是在尝试从新设备登录时。这些代码可以通过短信发送到用户注册的电话号码，也可以通过手机应用程序生成。

不管有没有双因素身份验证，开发人员和所有用户都应该为他们的所有在线帐户使用不同的复杂密码，并且应该定期更改这些密码。没有必要记住所有的密码，因为有许多密码管理应用程序，包括像 [KeePass](http://keepass.info/) 这样的开源应用程序，可以用来安全地存储它们。

HaveIBeenPwned.com 等免费服务允许用户检查他们的账户是否因数据泄露而暴露。用户可以用他们的电子邮件地址注册，并在这些地址出现在公开泄露的数据库中时收到通知。

在 npm 环境中，还建议定期轮换身份验证令牌，并查看对您的包具有发布访问权限的帐户列表。任何不活动的帐户或不必要的权限都应该被删除，因为 ChALkeR 联系的一些受影响的用户甚至不知道他们有一些软件包的发布权限。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>