# 集装箱安全:一个麻烦的故事，但希望在地平线上

> 原文：<https://thenewstack.io/container-security-a-troubling-tale-but-hope-on-the-horizon/>

作为一名研究容器采用的数据科学家，我花了大量时间研究事实告诉我们的关于数百万开发者每天使用的公共容器的构成。所以，本周我在底特律的 KubeCon NA，与令人难以置信的 Kubernetes 社区分享我们的发现。

史林看着[。AI](https://www.slim.ai/) ，我每天都在探索开发人员在大规模运行容器时遇到的现实。我的使命是提供一个了解世界的窗口，为此，我的团队最近完成了我们对世界上最受欢迎的公共集装箱图像的第二次年度分析。除了这个基础数据集，我们还与 Dimension Research 合作，对 300 多名开发人员& [DevOps](https://thenewstack.io/category/devops/) 专业人员进行了一项关于供应链安全及其如何与[现代集装箱化应用](https://thenewstack.io/category/containers/)相关的全球随机调查。

这项研究的结果可以在《瘦身》中找到。AI Top Public Container Report 2022，我昨天在 KubeCon 的主题演讲中分享了其中的亮点。以下是我们对过去一年中 800，000 多张独特的集装箱图片进行分析后所发现的内容的概述，以及我们的调查如何揭示这些发现。我想你会发现结果和我一样令人大开眼界。

首先，我们发现:

*   60%的顶级公共容器现在比一年前有更多的漏洞。这是经过一年对软件供应链的高度关注和多次安全事故后的结果。此外，研究中剩余的 40%的集装箱也没有显著改善其安全状况。

*   回应我们调查的 70%的开发人员表示，他们的客户和最终用户要求他们的容器没有漏洞。最重要的是，88%的人表示，确保容器没有漏洞变得越来越有挑战性。首要因素是这些容器中的复杂性和众多依赖组件。

故事是这样展开的:容器变得越来越脆弱，客户比以往任何时候都更要求完美，开发人员感受到了压力。

容器在任何时候、任何地方、任何现代软件项目中、任何垂直领域都被使用，这不会让你感到惊讶。事实上，开发人员已经开始将 Docker 这样的技术视为工作流的原生工具，如 Git 或 IDE。根据 [Stack Overflow 2022 开发者调查](https://survey.stackoverflow.co/2022/)显示，Docker 是开发者最喜爱和最想学习的技术，其次是 Kubernetes。我们还可以在 Docker Hub 上看到这一趋势，去年该网站的访问量增加了两倍。但是，虽然有很多关于建造和运输集装箱的教程，但对其中的内容却知之甚少。就像生物学中的细胞一样，容器被视为这些小的原子单位，是更大系统的组成部分:请求进入，数据出来。就是简单。

但是，类似 Log4Shell 的事情发生了，2022 年突然变成了软件供应链安全年。作为一个行业，我们不仅对软件系统中的主要组件和贡献者投入了更多，而且对它们的二阶效应也投入了更多。随着每一次这样的利用，我们的行业对我们共同面临的问题有了新的认识。

那么，我们如何利用这种更新的意识，可持续地改变整个集装箱的安全状况呢？在 Slim，我们的答案是系统地关注容器安全和优化。自 2020 年以来，我的研究团队一直在观察和解构数十万个容器，目的是了解它们如何随着时间的推移而变化，以及是什么使这些容器对开发人员友好并适合生产。

去年，大约在这个时候，我们在 Docker Hub 上的顶级公开容器上放了一个放大镜，并在去年[发布了我们的第一份公开容器报告](https://www.slim.ai/blog/container-report-2021.html)。我们惊讶地发现，即使是最常用的公共集装箱——我们说的是在 Docker Hub 上分别有 50 亿、60 亿和 70 亿次拉动的集装箱！—有大量漏洞。

我们现在出版了那份报告的续篇——第二份年度 Slim。人工智能公共容器报告([可在此免费下载](https://www.slim.ai/blog/container-report-2022.html))——在其中，我们探索了从 2021 年到今天数据集的增量。

**调查结果#1:在所有类别中，我们发现了比以往更多的关键漏洞。**

我已经提到 60%的顶级公共容器比一年前有更多的漏洞。是的，我们看到某些事件得到了解决，但是检测到新事件的速度比我们的“补救速度”快三倍最值得注意的是，我们解决的问题大多是可以忽略的低严重性漏洞，而我们发现的新问题大多是严重和高严重性的:高严重性漏洞增加了 50%，其次是严重漏洞增加了 10%。今天，平均每个公共容器有 287 个漏洞，其中 30%属于高/关键类别，比去年的 20%有所增加。(我们认为 20%太高了！)

**调查结果 2:组件的复杂性在过去一年里也显著增加。**

我们发现每个集装箱平均多出 13%的包裹。现在平均每个集装箱有 387 个包裹，差不多 400 个。正如多项学术研究所示，考虑到每个包可能有成千上万的依赖项，这个数字应该只是冰山一角。令人担忧的不仅仅是包裹数量。我们平均看到了两倍半多的许可证和四倍多的层。使用开源扫描工具扫描它们需要两倍的时间，导致我们的 CI/CD 系统浪费时间。

不要误解我——这些组件中有很多是实验所必需的。这些工具和包可以帮助开发人员构建、调试和测试他们的应用程序。但是它们也代表了复杂性和攻击面。如果我们在将集装箱运送到生产场所之前，没有有意识地努力移除不必要的组件并优化集装箱，我们就会招致大量的技术债务，这些债务需要在以后解决。这显然意味着需要自动化流程来确保膨胀的攻击面永远不会进入生产环境。

**发现 3:高管和一线工程师之间存在脱节。**

在我们的调查中，49%的高管认为集装箱变得更薄、更坚固，但那些做实际工作的人，即一线工程师和经理，报告的数字要低得多。如上所述，我们的调查发现，88%的开发人员承认消除漏洞具有挑战性。此外，不到 26%的人说他们知道如何使容器变薄和变硬。

今天，许多公司和政府都要求一个零漏洞的世界，但我们的研究揭示了在当前的工具和技术下，这一目标是多么遥不可及。

## 复杂性不是敌人；无知是

令人清醒的底线是:我们今天并不比 2021 年的这个时候更安全。确保生产容器的安全越来越不容易，但客户正通过要求零漏洞供应链来应对安全漏洞。结果，开发人员、DevOps 和 DevSecOps 团队感到了压力。

然而，令人欣慰的是，我们已经觉醒，我们比以往任何时候都更加意识到这些问题。在世界各地，有能力的、不懈的、杰出的团队因为思考这些问题而失眠，所以我相信当我将来分享我们的容器分析结果时，我会带来更好的消息。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>