# 在生产环境中迁移到无服务器

> 原文：<https://thenewstack.io/migrating-to-serverless-in-an-production-setting/>

对于大型企业来说，无服务器似乎是一个遥不可及的技术机会。

对于许多人来说，对传统基础架构的依赖、偏好管理而非自治的既定内部文化以及对云的风险厌恶似乎会将无服务器排除在潜在选项之外。

但是，大型企业仍然试图找出如何在现有环境中采用无服务器模式，主要是因为实时分析大数据流的需求不断增加。

[Asaf some KH](https://www.linkedin.com/in/asafsomekh),[Iguazio](https://www.iguazio.com/),[nucl io](https://nuclio.io/)的制造商，认为他们的关键价值主张是使企业能够针对该用例采用无服务器。“我们帮助企业构建翻译实时数据的应用程序。Somekh 说:“我们帮助他们将内部和外部服务结合起来，将人工智能放在首位，然后更多地转向平台方法，这在以前只是科技巨头的奢侈品。

Iguazio 的 Nuclio 产品是一个开源的无服务器平台，可以与 Docker、Google Container Engine、Azure Container Service 和 Kubernetes 协同工作。

Somekh 说，当 iguazio 构建 Nuclio 时，他们开始回答希望迁移到无服务器的企业的一个关键问题:“如何以最佳方式在无服务器中插入逻辑？”他说答案基本上是，让平台来做工作。“您设置触发器，让开发人员专注于业务逻辑，剩下的工作应该由平台来完成:与数据服务的紧密耦合，以及自动伸缩。当您将无服务器与数据服务混合使用时，应用程序的上市时间会大大缩短，只需几周而不是几个月。有时是几天而不是几周，”他说。

“三年前可没这么酷，”Somekh 开玩笑说。“所以我们决定让 Nuclio 开源，这样我们就可以围绕它创建一个社区。我们现在从大型玩家那里获得了巨大的贡献，例如，微软正在制作 Azure 触发器。”

Somekh 给出了两个使用 Nuclio 过渡到无服务器的用例:叫车公司和电信公司。

打车公司正在从乘客、潜在乘客、司机和车辆中收集数据。随着乘车公司规模的扩大，他们需要基础设施来收集数据，将数据从一个收集点转移到一个数据中心，进行转换和分析:所有这些都是实时的，以便他们可以分配司机和收取乘客费用。它还允许乘车公司将司机分配到供不应求的地区，这样他们就可以在整个城市的汽车和司机物理网络中实现“负载平衡”。Somekh 说:“在没有服务器的情况下，实时数据的货币化和对事件的反应可能是一个漫长的过程，等到你可以用这些数据做些什么的时候，价值已经太低了。”

对于电信公司来说，他们需要实时监控网络基础设施。Somekh 解释说:“使用所有这些网络监控功能，例如，当网络过载时，处理 DDoS 攻击会变得非常被动。”他说，正因为如此，许多电信公司希望将人工智能引入他们的平台，以便他们可以监控他们的网络基础设施并应用预测算法。但这需要他们接收从网络设备收集的采样数据，如 Netflow 数据，将这些数据与过去网络故障和攻击的历史记录进行比较，然后预测一个小时或接下来几个小时内将发生的风险。“这使得网络运营商可以通过改变配置来防止故障:这是对网络的预测性维护。”

在这两种情况下，云服务都可以用来训练算法。然后，可以将一个无服务器工作流放在靠近收集数据的地方，该无服务器工作流将在收集数据时应用模型进行分析(在叫车的情况下)或预测(在电信公司的情况下)。

Somekh 说，一旦这个基础设施到位，就更容易继续收集数据，并每三到六个小时更新一次预测或分析模型。Somekh 说:“这取决于统计方差，但上传更新的模型不会有太多负担。”

Somekh 说，为了帮助企业起步，无服务器启动过程的第一阶段包括绘制企业当前的基础设施。

“通常，我们会将企业客户当前使用的所有 API 进行映射。他们是否在使用亚马逊的数据服务，比如用于流媒体的 Kinesis、用于键值存储的 DynamoDB 等？他们可以对 Iguazio 使用相同的 API。他们不需要将数据从一个回购转移到另一个回购。通常，当数据被捕获后，将数据转移到 Dynamo，然后进行转换是开发人员的责任。那么它需要被转移到 S3 仓库。我们培训我们的客户，他们不需要移动数据。如果是本地部署，则有一组不同的 API 可能在本地部署中更常见。但我们的平台上总会有连接器，我们帮助他们使用这些连接器进行连接。”

瑞士 [LC Systems](https://www.lcsys.ch/) 的数据分析管理顾问 Mika Borner 在他与金融、汽车、制药和工业制造领域的大型企业的合作中表示，现在的趋势是公司希望保持其数据中心在本地，但转向混合云解决方案，可能比他们的美国同行更具尝试性。德国和瑞士的国家法规加剧了这种情况，这两个国家都要求数据中心留在国内，以管理客户的财务数据。(这在瑞士尤其困难。在德国，微软和亚马逊都有云托管产品，保证数据留在国内。)

“一些公司有点保守，他们将大多数最重要的数据保存在本地，以保持监管和风险评估的观点，”Borner 说。

“我们的客户正在寻找像 AWS Lambda 这样的技术，但这些无服务器选项在本地不可用。但公司仍然希望使用新技术，所以他们正在寻找像 nucleo 和其他无服务器框架这样的技术，”Borner 解释说。

Borner 说，由于一些监管限制，企业不能将大型数据集移动到云，所以他们需要更靠近边缘的无服务器模式，数据就是在那里产生的。

Borner 举了一个制药和工业制造行业的常见例子。两家公司都在生产线上安装了相机，并希望能够拍摄药丸或新成分的制作照片，将新作品的照片与最佳实践的高质量示例进行比较，并分离出质量不合格的产品。

Borner 说，当帮助大型企业迁移到无服务器工作流时，首要任务是详细了解用例。

“我们的企业客户比我们更了解他们的流程。所以我们试图理解他们在做什么，”Borner 说。“然后我们进入需求收集。我们同意他们的最高目标，例如降低成本。他们查看自己的限制，例如，他们当前的技术、收集了多少数据、数据的敏感性。无服务器不是解决所有问题的锤子，还有其他方法来进行分析，所以我们想看看他们在每个用例中需要什么。

Borner 说，一个普遍的经验法则是，当一家公司谈论衡量可以生产的组件(或药丸或产品)的质量时，他们会倾听公司的目标是一天内制造出多少个组件，还是几毫秒内制造出多少个组件。第一个目标与批处理技术更相关，而第二个目标与实时数据分析有关，因此更适合无服务器模型。

Borner 说:“一旦我们进入实时过程，我们就进入无服务器状态。从那里，LC Systems 开始创建概念验证(PoC)或试点示例。他们通常已经与企业客户建立了可信任的关系，因此虽然已经进行了一些成本计算，但在这个阶段还相当原始，因为企业希望 PoC 能够提供更多关于最终解决方案在生产中的成本的信息。

Borner 说:“概念验证是为了展示无服务器技术的可行性，但我们与客户密切合作，让他们了解未来的技术发展。我们通常要做很多白板来解释无服务器，我们画了很多图片，我们给他们一些资源，我们有一些演示，”他解释说。对于目前的任何无服务器迁移项目，无论是内部管理还是通过顾问，首席倡导者都需要承担教育角色，以帮助团队成员了解无服务器。

事实上，Borner 说，任何迁移项目中最大的挑战是团队成员相互不理解时的困难。在工业企业环境中，这一点尤其重要，因为最后期限通常是不可协商的。

专题图片:[哈尔·盖特伍德](https://unsplash.com/photos/OgvqXGL7XO4?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/search/photos/nucleus?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的照片

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>