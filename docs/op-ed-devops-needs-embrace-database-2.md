# 专栏:为什么 DevOps 需要拥抱数据库

> 原文：<https://thenewstack.io/op-ed-devops-needs-embrace-database-2/>

敏捷。DevOps。连续交货。如果你和它有关，你已经听过这些词不止几次了，你自己可能也用过。尽管只有少数组织成功地采用并实施了所有这些方法，敏捷、开发运维以及持续交付将继续推动 IT 战略。Gartner 预测，到 2018 年，大多数应用程序开发将使用敏捷方法。

有充分的理由。

数字世界的需求给开发团队带来了巨大的压力，他们需要比几年前更快地构建、准备和部署应用程序。这些最近引入的方法有望实现这一目标。

有了这样的创新和自动化水平，开发团队发布应用程序的速度最终满足了业务领导者的需求。他们生产更多产品，对业务产生更大影响。此外，它还见证了系统级别的快速创新，包括虚拟化和云，从而缩小了数据中心。当之无愧的击掌和鼓掌！这一创新让以前备受打击的 IT 团队成为英雄。

## 但没那么快

它长期以来都是各自为政。DevOps 协作消除了障碍，为参与应用交付流程的所有人创造了一个共同目标和无缝操作的和平环境…直到我们到达最后一英里。仔细看看，从开发到交付过程的最后 10%花费了 90%的时间和资源。这是为什么呢？

我们忘了数据库。

纵观历史，无论开发团队使用构建和修复、瀑布、敏捷还是任何其他过程模型，最后一英里总是落在数据库管理员的肩上，他的任务是实现、记录、测试和管理数据库的更改。没有这最后一步，什么都不会发生，然而自动化提供的好处和加速却没有数据库。应用程序正以创纪录的速度生产出来，但是 DBA 团队还没有准备好按照他们的开发团队同行设定的速度来处理大量增加的数据量。

当做出加速发布过程的 IT 决策时，DBA 会遇到善意的忽视，有时甚至是完全的敌意。开发人员不了解数据库管理员的重要性，也不了解他们的角色的难度。例如，我们听到开发人员抱怨 DBA 不允许将带有默认值的列添加到现有的表中。

[![Robert Reeves Headshot](img/db44c3e851c4e366724cda4e1024e340.png)](https://twitter.com/robertreeves)

罗伯特·里维斯

开发人员认为这没有问题，但是 DBA 知道生产表有超过一百万行。这种改变将导致在检查每一行数据并更新新的默认值时锁定表。行数越大，锁越长。有很好的理由不允许这种改变，因为它会破坏应用程序 SLA 并破坏维护窗口。数据库管理员正在执行所需的服务，因此应该得到认可。

DBA 团队经常忘记的另一件事是，更新和部署每个应用程序版本所需的数据库更改是一个手动的、容易出错的艰巨过程。随着所有新的创新、技术和方法的出现，IT 部门能够跟上数字企业的发展速度，数据库管理员需要继续使用同样的旧方法。DBA 的生活已经变成了一种持续的状态，如果还停留在这种状态之上的话，那就是几乎不踩水。

随着压力的增加，数据库管理员面临着部署变更的风险，这些变更会延续应用程序发布的基本原罪——破坏应用程序。如果没有检测到错误的数据库更改，应用程序可能会停止运行，并导致不值得羡慕的连锁反应。数据库管理员必须跟踪并补救变化，开发人员对他们必须回去修复应用程序感到恼火，首席执行官可能对企业赔钱感到愤怒，最终用户在无法访问他们所依赖的应用程序时陷入混乱。

## 自动化最后一英里

现在，公司投入更多的人力和资源来解决数据库瓶颈，但应用程序发布量和速度的持续增长意味着这充其量只是权宜之计，而不是真正的解决方案。布鲁克斯定律告诉我们这是愚蠢的。记住:九个女人一个月生不出孩子。

那么什么样的创新可以立即帮助数据库呢？从逻辑上讲，我们必须将推动开发过程的相同原则应用于数据库管理方式。整个行业都在讨论如何将敏捷工作流扩展到基础设施、安全甚至营销领域；DBA 没有理由被冷落。也许敏捷最重要的方面是持续改进和对变化的快速响应，这与 DBA 的主要目标非常吻合。

在 [Datical](http://www.datical.com/) ，我们的工程师开发了敏捷数据库自动化，这是一套基于与 [Liquibase](http://www.liquibase.org/) 相同原理的技术，后者是流行的开源数据库独立库，用于跟踪、管理和应用数据库模式变更。 [Datical DB](http://www.datical.com/product/) 通过使数据库部署像应用程序一样敏捷来加快发布周期。

通过欢迎数据库管理员加入 DevOps 组织，并利用敏捷数据库解决方案实现最后一英里的自动化，IT 主管可以扩大现有人员和工具的规模，更快地交付应用程序，减少停机时间，强制实施合规性，并提供整个数据库环境的可见性

让我们给历史上被忽视的 DBA 一个姗姗来迟的欢迎。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>