# 傀儡工程师:窥视集装箱内部，你会发现堆栈并不都是新的

> 原文：<https://thenewstack.io/puppet-engineer-peeking-inside-containers-find-stack-isnt-new/>

您最终投入生产的容器化应用程序是否真正经过改造、云就绪，并且是为流程编排和持续集成量身定制的？或者它们中的许多主要是您的组织自克林顿政府以来一直使用的客户机/服务器应用程序的容器化改装？

周一下午，在比利时根特举行的 2017 年配置管理营上，[木偶](https://puppet.com/)高级软件工程师[加雷思·拉什格罗夫](https://twitter.com/garethr)更新了他熟悉的主题:企业并不真正知道他们在容器化什么。这一更新带来了一些新的惊人证据，表明简单地将现有遗留工作负载容器化的组织正在压倒那些抓住机会重新设计它们以提高效率和安全性的组织。

“我认为，在那些只关注容器和只考虑世界观的人中间，”拉什格罗夫在接受《新堆栈》的后续采访时说，“对话往往非常理想化。”

Rushgrove 建议，如果对开发人员进行调查，并从该样本中确定有多少人在使用[scratch containers](http://www.richardbucker.com/2015/11/scratch-containers.html)——他称之为“理想的”,通常由新堆栈的支持者提出——或使用 [Nix](https://nixos.org/nix/) 或类似工具进行版本控制；或者在他们的容器中使用最小的 Linux 发行版，比如 [Alpine Linux](https://alpinelinux.org/) ，人们会看到很多人举手。

“这就是他们正在做的，也是他们周围的人正在做的，”他说。“通过观察我们的一些客户和一些大型组织正在做的事情，从 GitHub 中提取他们的数据，这真的不是现实世界中正在发生的事情。”

## 新堆栈和大世界

Rushgrove 的灵感来自 Docker 贡献者 David Gageot 最近的一篇博客文章，他为 Google big query 创建了一个 SQL 查询，能够提取被推送到 GitHub 公共档案馆的容器中的基本 Linux 映像的身份，根据 Gageot 的统计，大约有 281，212 个 Docker 文件。大约 9.5%的图像查询使用完整的 Ubuntu 14.04 作为它们的基本 Linux 图像，并且总共大约 19.4%的这些文件显示包括一些版本的 Ubuntu。

Alpine Linux——一个有意建议但不一定打算用于容器的轻量级发行版——在 Gageot 的列表中排名很低，使用最频繁的版本在 Linux 版本中排名第 30 位，GitHub 上不到百分之的 Docker 文件的标题中出现了“Alpine”。

“是的，阿尔卑斯山的使用率似乎比其他东西增长得更快，”拉什格罗夫说。“但这是从如此低的起点开始的。”

实际上，Rushgrove 可能会很感兴趣地了解到，大多数被调查的开发人员并没有如此严重地倾向于“理想”

> “我认为，在那些只关注集装箱、只考虑这种世界观的人当中，对话往往非常理想化”——加雷思·拉什格罗夫

在【2016 年 8 月由容器分析公司 [Anchore](https://anchore.com/) 对容器开发者进行的一项调查中，给出了 15 个容器主机操作系统的列表，包括最小化的容器特定内核，加上“无”和“其他”，约 34.5%的受访者表示他们使用 Ubuntu，相比之下，CoreOS(现在称为[容器 Linux](https://coreos.com/products/premium-managed-linux/) )的比例为 13.7%，RancherOS 的比例为 3.6%，Red Hat Atomic 的比例为 1.8%，Ubuntu 自己的比例为 2.5%

正如 Rushgrove 从 Gageot 的数据中推断出的，引用了他周一的一张幻灯片，“大多数使用 Docker 的人使用的是包含整个操作系统文件系统的映像。”这句话促使主厨产品经理朱利安·c·邓恩在当天晚些时候发推特说，“是的，这太可怕了。”

自从 Docker 第一次出现以来，就有一些建议——也有一些演示——一个完全包含的 Linux 内核由另一个完全包含的 Linux 内核托管，提供了一个大型星球大小的攻击面。去年 12 月， [Aporeto](https://www.paloaltonetworks.com) 工程师 [Stefano Stabellini](https://twitter.com/stabellinist?lang=en) 在新的堆栈中认为，虽然这样的配置可能难以破解，但同样难以确保安全。

## 铺设牛道

但是在与我们交谈时，拉什格罗夫淡化了这种担忧，这让我们感到惊讶。

“我认为那是错误的想法有点误导，”他说。在他看来，容器“纯粹主义者”可能会认为容器化的理想是基于最初的 Google Borg 模型。尽管 Gageot 的数据提供了令人震惊的不可辩驳的证据，表明这一理想并没有像理想主义者所希望的那样得到广泛传播，但 Rushgrove 建议，邓恩所列举的恐怖的解决方案——而不是加强我们对为什么理想模式更可取的宣传——是开始确保组织实际选择的模式。

“Docker 特别想到的是，人们可以非常容易地在容器中使用他们的软件，”他继续说道，“而不必重建世界。我认为阻力最小的方法的直接结果是在容器中使用整个操作系统文件系统。不管它是好是坏，是更好还是更坏的想法。这是人们出于兼容性原因正在做的事情。这将把我们带到现实世界中的集装箱世界。”

Rushgrove 认为，开发者工具社区现在必须面对的真正问题只是部分地涉及到安全性:他认为，工具制造商正在为管理模仿谷歌、脸书或网飞的超大规模系统的理想主义者和率先采用者构建和完善他们的产品和方法。虽然这个群体确实在增长，但它是以更快的速度向外扩展的普通采纳者的海洋。对于后一类人来说，配置管理和其他工作会有所不同，因为他们已经做出了选择。此外，随着时间的推移，这些选择更有可能是永久性的。

“这是一种令人不安的认识，”他告诉我们。

## 那为什么要集装箱化？

但是，我问拉什格罗夫，如果组织更愿意选择阻力最小的道路，难道他们不愿意避免容器化的全部努力，坚持在 [vSphere](http://www.vmware.com/products/vsphere.html) 、 [XenServer](http://xenserver.org/) 或 [KVM](http://www.linux-kvm.org/page/Main_Page) 上运行他们的第一代虚拟机吗？为什么不选择对他们来说最滑、最无摩擦的路径呢？

他的回答有些拐弯抹角。他说，集装箱化的理想倾向于融合两种优势。首先是调度程序，开发人员依靠它来实现资源可移植性、资源优化和软件基础设施健壮性的整体提升。在过去的十五年中，调度程序已经将运营和基础设施经理以及 DevOps 团队的最佳实践进行了编码。

其次是容器催化更好的开发架构的原则，比如微服务。这种融合表明，一个组织不能缺一不可——为了利用调度和可移植性，需要承担为这种新架构重写所有内容这一看似不可完成的任务。

然而，解开大多数软件已经内置的依赖关系(如果我可以补充的话，这是一个由 Linux 打造的链条，就像 Windows 一样)可能会推动组织选择容器化——并且更快地选择它——作为一种避免重新架构的方式，绕过大山绕过山谷。

那么，我问，安全社区和容器工具社区是否应该联合起来，为这种更广泛的攻击面构建新的安全方法，如果您愿意的话，大多数企业都会选择山谷之路？

“如果我们欣赏人们实际上正在做的事情，那么我们可以——单独地或集体地——教育人们去做，引用——引用，“更好”的事情，”Puppet 的 Rushgrove 回答说。“另一方面，有一个方面是‘铺平道路……’随着时间的推移，我们实际上使用了很多工具来解决这种[*安全*问题。但是容器正在改变游戏。这不是使用相同的工具；这是关于回到那些工具被设计来解决的问题，然后说，‘在这个新的环境下，解决*那个*问题的工具会是什么样子？’"

## 你的花园品种操作系统

问题是，许多旧工具都带有 Windows 徽标。如果我们忙于为可能选择阻力最小的道路的企业铺平道路，那么不久之后，这种田园风光会不会开始变得越来越不像 Linux 呢？

Rushgrove 承认他的数据显示目前很少使用 Windows 容器。“但是我很想在一年内重做这些查询，并随着时间的推移跟踪其中的一些内容。我认为这一数字将会快速增长。”

Rushgrove 建议容器演化跟踪应该采取的一个步骤是合并一个更详细的包含组件及其依赖项的清单。虽然这种列表可能只对微服务有一定的用处，但它可以极大地帮助调度人员和指挥人员管理和保护当今更普遍使用的大型容器。他说，随着 Windows 容器被越来越广泛地采用，这种类型的列表可能特别有用。

“我们的想法是，用一个一致的 API，更容易地向这些容器中的任何一个询问关于它们自己的问题，”他告诉新堆栈。“根据这个想法，你可以想象对解决实际操作问题有用的高级工具。”

在周一的演讲中，Rushgrove 断言，这样的工具将解决所有集装箱化平台的需求，实现不变性。正如他的一张幻灯片所说，“不变性意味着我们需要知道我们在盒子里放了什么。”

《新书库》的劳伦斯·赫克特为这篇报道提供了信息。

阿波雷托、多克和 T2 是新堆栈的赞助商。

专题图片:“特里格拉夫国家公园七湖谷中的[奶牛在去双湖](https://commons.wikimedia.org/wiki/File:Cow_on_the_way_to_the_Double_lake_in_the_Valley_of_the_seven_lakes_in_Triglav_National_Park.jpg)的路上”，由 Dreamy Pixel 拍摄，根据 Creative Commons 4.0 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>