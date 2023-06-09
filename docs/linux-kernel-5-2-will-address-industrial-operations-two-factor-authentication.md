# Linux 内核 5.2 将解决工业操作、双因素认证

> 原文：<https://thenewstack.io/linux-kernel-5-2-will-address-industrial-operations-two-factor-authentication/>

目前，在候选发行版 3 中，Linux 5.2 [内核](https://www.kernel.org/)即将推出，并承诺提供大量令人印象深刻的新特性和改进。让我们来看看其中的一些亮点。

## 新功能

**现场总线子系统**

新的特性之一是引入了新的现场总线子系统，这应该会让任何处理自动化工业系统的人感到兴奋。现场总线在连接工业环境中的不同系统方面至关重要，通过这一添加，Linux 内核现在可以作为控制系统的一部分与现场仪器(如制造工厂中使用的仪器)进行本地通信。

**U2F 零驱动器**

由于新的 U2F Zero 驱动程序，双因素认证将在 5.2 内核中得到提升。这款新驱动器将增加对基于 USB 的 U2F 令牌的支持，该令牌可与在线双因素身份认证配合使用。U2F 驱动程序还将提供基于硬件的随机数发生器(RNG)功能。

**英伟达“替代模式”**

一个新的开源 NVIDIA 驱动程序即将推出，它可以处理使用基于 USB-C 连接器的 RTX 图灵显卡的 VirtualLink 设备。至于 VirtualLink 设备，还不能确定首先支持哪个设备，但是(根据 [Phoronix](https://www.phoronix.com/scan.php?page=news_item&px=Valve-Index-VR-Headset) ) Valve 可能是首先支持的 VR 头戴显示器之一。

**通用计数器接口**

虽然没有内核中的其他新特性那么吸引人，但有一个新的通用计数器接口，它允许计数器设备和驱动程序重用公共代码(而不是必须为每个驱动程序使用冗余代码)。什么是计数器设备？根据 generic-counter.rst 的差异:

*计数器设备在各种行业中普遍存在。这些设备的普遍存在使得交互和暴露的公共接口和标准成为必要。该驱动程序 API 试图通过引入通用计数器接口来解决现有计数器设备驱动程序中的重复代码问题。通用计数器接口使驱动程序能够支持和公开计数器设备中的一组通用组件和功能。*

**空 TTY 驱动程序**

当需要控制台驱动程序，但没有控制台驱动程序时，空 TTY 驱动程序是必需的。当这种情况发生时，空 TTY 驱动程序将提供一个虚拟控制台，以便所有写入都被丢弃。这种驱动器的一个实际应用是嵌入式控制器。

**达科司机**

达科公司是一家大型显示器(如用于记分牌的显示器)的全球制造商。这些特殊的驱动程序在 2.x 时代就已经从 Linux 中消失了，但是现在终于回来了。一旦这些驱动程序返回，它们将被清理以供生产使用。任何使用达科显示器的人都应该对这个利基新闻感到非常兴奋。

**英特尔彗星湖**

Intel Comet Lake 是 Coffee Lake 的继任者，据传将达到 10 个物理核心。这些新处理器应该会在年中推出(根据[的传言](https://www.tweaktown.com/news/65857/intel-comet-lake-cpus-require-new-socket-mobo/index.html)，可能需要新的主板/插座)。彗星湖应该在内核 5.2 中得到很好的支持。

## 丰富

5.2 有许多改进。让我们来看看其中的一些亮点。

**罗技无线设备**

如果您拥有任何类型的罗技无线设备(如键盘或鼠标)，您将会看到显著的改进，如更好的电池监控和每个设备的按键映射。以前版本的内核通过通用 HID 仿真支持 Logitech 无线设备，但在 5.2 版本中，每个设备的按键映射将使更好地支持单个无线设备成为可能。

**EXT4 不区分大小写的文件名/文件夹**

Linux 从一开始就是区分大小写的。然而，在 5.2 中，EXT4 文件系统将允许在每个目录的基础上支持不区分大小写的文件和文件夹。这些补丁一直在开发中，看起来他们最终准备好了主线支持。

**AMD 锐龙笔记本电脑改进**

对于那些使用 AMD 锐龙芯片的笔记本电脑，你应该会看到触摸屏和触摸板的显著改善。

**AMDGPU**

Alex de ucher(AMD 的)一直在研究替代代码，以清理/改进:

*   PowerPlay 的电源配置文件
*   Dx 显示带宽
*   Vega 20 的 RAS 支持
*   用 DC 电码进行飞机操纵
*   自由同步

**X86 内存管理**

多亏了 VMware 的 Nadav Amit，通过修改内核的 x86 翻译后备缓冲区(TLB)/内存管理代码的一部分，5.2 内核应该可以获得 3%的性能提升。

## 其他改进/特点

内核 5.2 应该会看到许多其他的改进，比如:

*   英特尔冰湖
*   ARM Mali 图形硬件
*   修复了新的开源图形驱动程序
*   改进了对 Thunderbolt 的支持(针对旧的 Apple 硬件)
*   英特尔 i40e 动态设备个性化
*   ASpeed AST2500 SoC 驱动器
*   Zap 着色器对高通 Adreno 600 的支持
*   GCC 9 实时补丁

## 警觉地注意

当 5.2 内核发布时，对于几乎任何类型的用户都应该有重大的改进。发布日期尚未确定，但内核 5.2 应该会在 2019 年底或 2020 年初的某个时候找到出路。在接下来的几个月里，请注意这一点。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>