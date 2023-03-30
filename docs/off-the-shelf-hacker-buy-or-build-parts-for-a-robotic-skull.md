# 现成的黑客:购买或制造机器人头骨的零件

> 原文：<https://thenewstack.io/off-the-shelf-hacker-buy-or-build-parts-for-a-robotic-skull/>

在过去的几个月里，我报道了制作赫德利，我的机器人头骨。我最初是在寻找一种方法来研究、理解和开发 [JeVois 机器视觉传感器](http://jevois.org/)的用途。这个尖端的传感器使用运行 Linux 和人工智能(AI)程序的四核 ARM 芯片来分析和响应进入赫德利视野的事物。该模块带有一个内置的微型摄像机，包裹在一个 1x1x3/4 英寸的蓝色塑料立方体中。

万圣节期间，我漫无目的地在当地 Target 商店的过道里闲逛，发现了一个廉价的塑料头骨，我认为它会与 JeVois 传感器完美配合。让一个头骨在视觉上跟踪一个人，并训练它说话，这既有挑战性又很有趣。

正如你所料，该项目已经演变为添加平移和下颌伺服系统，三色 LED 左眼球，一个单独的 Arduino 来管理下颌，以及一个用于一般计算和视频(JeVois 传感器回放)操作的 Raspberry Pi。一路上，我还建造了内部黄铜管道框架和安装系统，用于将头骨放在桌子上或盒子里。制造你自己的机器人头骨是唯一的出路吗？

答案是响亮的不。在搜索了一段时间“机器人用品”和“机器人头骨”之后，我终于找到了回报。今天，我们将看看几个机器人头骨的特定网站，以防你不想从头开始构建。请注意，预制机器人头骨的价格可能有点吓人。

## 怪物内脏

看看[怪物内脏](http://www.monsterguts.com)。它的标语“怪物的内脏，没有它们就没用了”很有描述性。它的论坛不是说“现在直播”，而是“现在直播”我喜欢这种半开玩笑的幽默。正如我们过去讨论过的，戏剧和上演一场精彩的表演对于吸引注意力非常重要。我认为现成的黑客会从这个网站中得到乐趣。

怪物内脏标榜自己是电子动画和道具制作人的天堂。他们还提供一些非常复杂的机器人头骨套件。三轴 skull elite 产品配有 skull、他们定制的带伺服系统的云台机构、2 轴眼睛机构和可选的彩色 LED 眼睛。我对所有的高端产品都进行了定价，得出了 835 美元左右的价格。你必须提供自己的[控制电子设备](http://www.lynxmotion.com/p-1032-ssc-32u-usb-servo-controller.aspx)、软件、电源和安装硬件。我现在正在积极寻找资金在实验室里得到一个。

贵吗？也许是，也许不是。在做出判断之前，你应该看看演示视频，因为他们头骨的能力令人印象深刻。该视频还谈到了他们即将推出的全息眼睛选项。滑头。

[https://www.youtube.com/embed/DWeEdW5YdMQ?feature=oembed](https://www.youtube.com/embed/DWeEdW5YdMQ?feature=oembed)

视频

一个更大的问题是，你如何利用所有这些真实的运动和动画来达到你的目的。在我的情况下，赫德利将协助我的演讲演出。十月底，我将带他去明尼阿波利斯参加[嵌入式系统会议](http://www.embeddedconf.com/)。会议的人想让我上来谈谈我是如何把他组织起来的。赫德利也可能会和我一起参加 7 月在 OSCON 举行的会议。

## 万圣节头骨

[万圣节骷髅头](https://halloweenskulls.com/)制造三轴骷髅头，使用 DMX 控制系统进行运动。它提供带有伺服系统的完整头骨，价格堪比怪兽的内脏。

[DMX](http://dmxusb.com/what-is-dmx/) 是一种标准协议，经常在剧院和演出制作中用于控制灯光、小工具、运动机制等。您可以从控制台、计算机生成 DMX 命令，甚至通过网络连接发送它。这些设备以菊花链形式连接在一起，形成一个总线结构，并分配有地址。命令被发送到特定的地址来控制每个设备。该协议允许设备系统通过脚本实现自动化，包括机器人头骨。DMX 在 Linux 计算机上工作，通过图书馆使用 Arduino 和 Raspberry Pi 等微控制器。你可能需要一个 USB 转 DMX 适配器。这是亚马逊的[一个](https://www.amazon.com/Open-DMX-USB-Interface-Controller/dp/B00O9RY664/ref=sr_1_19_sspa?ie=UTF8&qid=1528162944&sr=8-19-spons&keywords=usb+to+dmx+adapter&psc=1)。

万圣节头骨区别于其他供应商的另一点是，它可以 3D 打印自己的头骨系统。这些部分整齐地装配在一起，并在很大程度上消除了影响头骨美观的关节。用简单的手工工具组装。

你会喜欢这个[宣传片](https://halloweenskulls.com/assets/video/Prototype%20Skull%20Demo%20Video.ogv):

## Skulltronix

Skulltronix 为主题公园、餐馆、“常去的地方”和商业景点制作头骨。像万圣节的头骨一样，他们制造自己的塑料部件，并使用 DMX 控制协议。它还销售自己的卡盘伺服控制板。他们甚至开发了几首录音动画歌曲，让他们的头骨跟随脚本。

除了头骨，Skulltronix 还有其他令人难以忘怀的万圣节道具，包括箱子、板条箱和一个超酷的[轨道头骨真人系统](http://www.skulltronix.com/liveaction.shtml)。该公司使用球帽上的反射器、红外摄像机和软件来感应演员头部的运动，以驱动机器人头骨的动作。该系统是为观众面前的现场表演而设计的。它还简化了录制头骨动画序列，以便以后播放。

## 后续步骤

哇，我希望我能想到为赫德利做一个头部运动跟踪系统。看别人的作品是一种可行的方式来提出你自己怪异的新想法。

现成的黑客越来越多的选择建立或购买。当然，3D 打印正在开辟一个定制/原型制作的新世界。项目打包和机制与物理计算项目中的其他部分一样重要。

并且，请记住，最终目标是生产出真正有用的东西。购买机器人头骨部件，一旦你了解了基本原理，就可以加快生产速度，并帮助你获得一个项目。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>