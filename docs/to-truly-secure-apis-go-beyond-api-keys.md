# 要真正保护 API，不要局限于 API 密钥

> 原文：<https://thenewstack.io/to-truly-secure-apis-go-beyond-api-keys/>

关于 API 安全性，我们能学到的最重要的一课是什么？

 [雅各布·艾德斯科格

Jacob 是 Curity 的身份专家兼首席技术官。他的大部分时间都花在 API 和 webspace 的安全解决方案上。他曾为大型企业部署和小型创业公司设计和实现 OAuth 和 OpenID Connect 解决方案。](https://se.linkedin.com/in/ideskog) 

除此之外，它应该是所有现代企业最关心的问题，我认为 API 安全应该围绕身份。如果公司在保护 API 时没有考虑身份，他们可能会发现自己成为 API 攻击的受害者，导致数据丢失和安全漏洞。

为了应对这一挑战，理解并非所有的 API 安全措施都同样有效是至关重要的。实现 API 安全性有几种方法，每种方法都有不同程度的保护。我将在下面讨论其中的一些:

*   API 密钥和基本身份验证
*   基于令牌的认证
*   基于令牌的授权
*   使用声明的集中式信任

## **API 密钥和基本认证**

许多公司通过使用 API 密钥开始了他们的 API 安全之旅。它们验证 API 调用并使用基本身份验证。在这种情况下，API 键被插入到 API 请求的 URL 的头部或主体中。

这种方法仍然非常流行和广泛使用，但是它有一些主要的缺点。首先，API 密钥很容易被泄露。第二，API 密钥验证完全不依赖用户的身份；只是依赖于机器对机器的验证。虽然在某些情况下 API 密匙已经足够了，但是如果这是保护 API 的方法，我建议您考虑增加安全措施。

## **基于令牌的认证**

提高 API 安全性的一种方法是实现基于令牌的身份验证。这意味着使用访问令牌进行身份验证。在这种实现中，访问令牌决定用户的类型，在需要内部和外部用户分离的环境中可以建立特权访问。

基于令牌的身份验证部分关注身份，因为它是请求的一部分，但是这种方法仍然有一些漏洞。首先，特权访问不一定是隔音的——它仍然可以被黑客攻击，因为任何拥有令牌的人都可以修改 API，因为特权没有绑定到令牌。因此，虽然访问令牌可以描述用户的类型，但如果不编写自定义代码，就无法确定权限。

## **基于令牌的授权**

与以前的方法相比，这种方法有明显的优点。它不仅涉及基于令牌的认证，还涉及基于 OAuth 的授权。这意味着请求方不仅通过回答问题“你是谁”来进行身份验证而且还被授权和分配了某个实体被允许做什么的某些特权。

OAuth 的优势之一是使用了作用域。它们可以包含更有价值的数据，并且比 if 语句更容易构建到系统中。此外，作用域可以指定特权，允许您创建适合您的 API 的自定义作用域。

然而，基于令牌的授权并不是没有问题，即使是在关注身份的情况下。因为身份是直接构建在 API 中的，所以逻辑错误可能会成为潜在的威胁。此外，在一个复杂的系统中，一些 API 请求依赖于其他 API 响应，如果一个 API 调用另一个失败的 API，就会出现问题。

范围绑定到令牌，但没有绑定到用户，因此它仍然没有提供用户级的细粒度授权。

实用提示:如果您选择遵循仅限范围的方法，请花额外的时间规划身份信息是如何使用的，并跟踪所有的 API——这是一项艰巨的任务，但却是值得的。

## **集中信托运用债权**

最先进的 API 安全方法是通过声明和(作为一个附加选项)签名的 JSON Web 令牌(jwt)建立集中式信任。如果使用正确，这种方法可以安全地解决上述所有问题。

jwt 是 OAuth 流用来携带身份信息的经过签名的数据片段。此外，jwt 可以用于共享范围，这为声明提供了逻辑分组。声明是包含主体(关于谁做出声明)、属性(关于主体的特定属性)和做出声明的声明方的声明。

阿莱克莎说:“吉姆是一位父亲。”。只有我们信任 Alexa，这个说法才可信。在 OAuth 上下文中，应该是这样的:“身份提供者 X 声明用户 Y 具有属性 z。”您的 API 应该只信任声明方(身份提供者)。

与其相信属性，不如相信熟悉的人的声明。这样，请求方将首先调用声明方(或发布方)。颁发者返回用私钥签名的数据，然后将数据发送给回复方。结果，签名用公钥验证，声明的信任建立。

*实用提示:遵循最佳实践* [*使用 jwt*](https://curity.io/resources/learn/jwt-best-practices/)*和* [*声明*](https://curity.io/resources/learn/using-claims-in-apis/) *。*

## **为什么强大的 API 安全性很重要**

仅信任令牌的发行者并不能 100%保证所有 API 都受到保护。但是，验证请求方的身份并通过集中信任标准化该过程是确保关键信息安全和整个系统不易受攻击的最佳方式。这还意味着您可以限制对自定义代码的需求，并降低由于 API 调用失败而导致的级联信任问题的风险。

如果没有高级安全性，API 就会变得容易受到攻击，例如，GitHub 存储库中留下了一个流氓密钥。因此，API 提供者必须做出安全决策，保护整个平台的完整性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>