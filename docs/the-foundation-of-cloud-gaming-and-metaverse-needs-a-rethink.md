# 云游戏和元宇宙的基础需要重新思考

> 原文：<https://thenewstack.io/the-foundation-of-cloud-gaming-and-metaverse-needs-a-rethink/>

从概念上来说，**云游戏**(或游戏流)就像是在你邻居拥有的非常好的机器上玩游戏，但插入一个控制器，用一根非常长的电线连接到你的房间，然后将摄像头对准屏幕。那么你所需要的就是一个屏幕设备来捕捉相机流。既然我们接受了云在其他计算负载上的优势，为什么不接受现代游戏所需的高功率呢？类似的问题会影响即将到来的元宇宙吗？

谷歌因 Stadia 的[失败而受到指责，这很公平——如果你看看](https://www.polygon.com/23378721/google-stadia-shutting-down)[谷歌墓地](https://killedbygoogle.com/)，你会看到他们泰然自若地杀死了绝大多数自己的孩子。关于他们缺乏与他们应该一起工作的社区的联系，可以说很多，但情况一直如此。谷歌内部的项目团队知道这一点:如果你不能适应母舰的配方，你将会毫无预警地被抛弃。非常死亡或荣耀。我只能希望那些陷入困境的游戏开发者能够掸掉身上的灰尘，吸取相应的教训。

在涉足电信和游戏行业(以及电信行业进入游戏行业)之后，我更感兴趣的是，为什么云游戏这种确定性还没有形成。

## 云游戏的市场是什么？

游戏市场一直是突发奇想和可能性的混合体；对于下一件大事会是什么，没有真正的线性逻辑。使用 Stadia 的成本很高，但与购买一部新 iPhone 相比并不昂贵。当然，对于像*赛博朋克 2077、*这样的处理器密集型游戏来说，这可能是许多人唯一可行的玩法。然而 Stadia 陷入的黑洞是“市场适应”；他们既没有说服游戏玩家，也没有说服足够多的开发者相信他们有强大的商业产品。

那么这种类型的东西会有市场前景吗？

已经有稳固的云游戏平台，来自微软、亚马逊、PlayStation 和 Nvidia。杂志《Polygon》中的一段话最好地总结了其余行业参与者的看法:

> “这不是一个范式的转变，只是一个额外的好处。”

云游戏作为突破性产品的想法现在可能已经被耗尽了(之前与 OnLive 的尝试在 2015 年失败)。制作一款高度细节化的游戏，几乎不与你的平板电脑互动，这个概念起初很吸引人，这也刺激了一些进入这个领域的人。但是很快意识到你不能从交付技术开始创造一个伟大的游戏设计。这不是游戏玩家玩的，也不是设计师做的。

由于游戏需要集中运行和维护，云客户认为服务取代了所有权。所以 Stadia 是一个内容提供商，很像网飞或 Spotify。这确实会引起一些恐慌，但如果有适当的前期储蓄和广泛的产品，这对大多数玩家来说似乎不是问题。人们确实会重玩游戏或者长时间停留在一个游戏中，但这些往往是需要马力才能运行的游戏。然而，令人不安的是，人们对游戏的消费方式与电影、书籍或音乐不同。

## 更智能地分离工作负载

从技术角度来看，Stadia 很好。云游戏的敌人仍然是滞后(由你按下的消息、到达服务器的 fire 按钮和一路返回的子弹射出的响应图像之间的往返行程造成)，但这应该会慢慢改善。互联网不是通过网络做智能的事情，而是智能的事情发生在边缘，传输保持简单。

你可能会争辩说，一旦你的图像被创建，仅仅把它们发送到目标设备上对于互联网来说是一个合理的——即使是大量的——使用。但这是游戏的另一个不同之处。与电影或书籍不同，人类以一种积极的方式不断地互动。当我的电脑过热时，我知道它会丢帧(即屏幕上的东西会跳动)，但至少我可以控制这种情况。但是，你所依赖的远程系统的任何视觉、听觉或触觉反馈中的微小不一致都会让你心烦意乱。

虽然我是网络中立的大力倡导者，但事实上，没有一家互联网提供商能给我一条网速真正保证不会让我失望的线路，这是一个很大的问题。更重要的是，云游戏公司不能强迫互联网提供商不要在晚上奇怪的时间上网，这个时候很多游戏玩家都很活跃。即使网络提供商和云游戏提供商是同一家公司，他们也不可能在所有方面都获得独家接入。消费者不希望处于没有人会为结果承担责任的境地，每个服务都在指责另一个服务。我们都去过那里，没有人喜欢它。

> 更智能的工作负载分离可能会带来改进。例如，为什么我希望在上游生成一个静态菜单？

另一方面，流式传输一个我只浏览一次的过场动画是一件非常明智的事情。事实上，知道一个许多 MB 大小的乏味的过场动画必须存储在你自己的设备上是有点烦人的。

要求独立的服务来呈现游戏的各个部分意味着从技术上来说，多个服务可以提供帮助。虽然这听起来像某种类型的微服务 hellscape，但显而易见的是(例如)致力于完善过场动画的工作室可以按需提供这些服务。许多游戏添加了物理引擎，但各种动态效果都可以外包。像 Improbable、Polystream 和 Amazon Lumberyard(现在是[开放 3D 引擎](https://thenewstack.io/open-3d-engine-talks-metaverse-and-its-new-partner-epic-games/))这样的公司已经尝试性地提供了多人游戏平台。我们看到有人试图将其他平台的独立语音聊天或成就系统整合在一起；大多数工作室知道他们不必再做所有的事情。

## 对元宇宙的影响

那么这对元宇宙有什么影响呢？虽然没有人确切知道[元宇宙是什么](https://thenewstack.io/metaverse-standards-forum/)，但它至少会是一种 3D 视觉体验，在一个持续的世界里，有大量的人实时体验它。这种类型的平台可能会有很高的计算成本，再加上已经成为 AR / VR 必要部分的耳机硬件，这将限制适用于 Meta(例如)明确瞄准的受众规模的交付选项。

> 流媒体很可能是让元宇宙进入大众市场的唯一途径。

不幸的是，大多数关于云游戏的负面观点也适用于流式虚拟持久世界。当他们舒适的世界被卖给他们不喜欢的公司时，人们会抱怨。他们会想，当性能下降时，谁该受到责备。在相似的时间，性能问题将会被大量的人看到，这使得他们可以聚集在一起抱怨。从历史上看，在(比如)第二人生中，化身之间的互动一直相对平静，但用这种观点来限制未来世界是不明智的。

与书籍和电影相比，电子游戏是一种年轻的娱乐形式。行为模式仍在诞生。我们知道 Kindle 是好的。我们怀疑 3D 电影没有必要。虽然很难明确关注云游戏的确切价值，但有证据表明，随着问题的全面解决，采用云游戏的速度缓慢但稳定，而不是从一个点突然创新。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>