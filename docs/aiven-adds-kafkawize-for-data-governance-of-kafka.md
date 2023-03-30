# Aiven 为 Kafka 的数据治理添加了 Kafkawize

> 原文：<https://thenewstack.io/aiven-adds-kafkawize-for-data-governance-of-kafka/>

Aiven 最近宣布将 [Kafkawize](https://kafkawize.com/) 加入其开源云数据平台。Kafkawize，Aiven 已经[将其重命名为 Klaw](https://aiven.io/press/kafkawize-joins-aiven-to-continue-open-source-journey) ，是一个管理 [Apache Kafka](https://thenewstack.io/apache-kafka-cornerstone-iot-data-platform/) 中数据的开源工具，Apache Kafka 是一个管理低潜在流数据的框架。

[Kafka](https://kafka.apache.org/) 广泛用于电子商务、物联网、工业互联网应用中生成的实时数据。Klaw 使 Kafka 用户能够针对单个主题对数据进行精细管理，这是 Kafka 中管理数据的基本组织单元之一。

“当公司在 Kafka 中有一个大集群时，他们遇到的第一件事是:我如何定义关于谁可以访问什么、什么可以进入哪个主题以及谁可以读写这些内容的策略？”说道 [Josep Prat](https://de.linkedin.com/in/jlprat) ， [Aiven](https://aiven.io/) 开源工程总监。“这很快就变成了一场噩梦。”

Klaw 旨在降低这些和其他数据治理任务的复杂性。它作为一个治理层，组织可以通过它访问他们的 Kafka 数据。该解决方案是一个中央管理平台，用于管理访问控制列表、实现数据治理策略以及根据主题定义模式。

“在卡夫卡中管理主题是很麻烦的，”普拉特指出。“这很复杂。我们怎样才能让每个人都能接触到这个东西？我们如何定义某些过程，以便如果你遵循这些过程，大多数人都会对卡夫卡有很好的体验？”

## 集中式治理能力

实施 Klaw 有助于解决这些问题以及更多问题。当然，Klaw 用户可以不通过 Klaw 访问 Kafka。然而，通过 Klaw 访问 Kafka 数据(通过 REST APIs 或 Klaw 的用户界面)，他们可以简化管理 Kafka 的复杂性。Klaw 从一个地方自动呼叫 Kafka。它对于管理不同的连接器、确定哪些连接器可以相互对话，以及了解它们可以访问哪些主题也是必不可少的。

没有 Klaw，使用 Kafka 的组织通常会遇到这样的情况，在实现连接器之前，“我需要以五种不同的方式请求三个、四个、五个东西；每件事都有不同的作用，”普拉特说。“忘掉那件事吧。该工具是一个中心位置，可以帮助您更快、更安全地做出决策。”Klaw 包含 Prat 所谓的“管理任务仪表板”,用于标准化主题和连接器的管理。它是分配和理解主题所有权以及基于企业规则实现治理的场所。“假设我们有一个包含敏感数据的话题，”Prat 说。“该主题的所有者可以定义谁可以写或读该主题。”

## 管理主题

Kafka 是一个用于高吞吐量系统的分布式平台，可生成多种类型的消息，其中许多直接与低潜在数据传输中的[事件相关。Prat 描述了一个电子商务用例，其中不同的事件可能由客户打开某个网页、将商品放入购物车或启动结账过程而触发。这个最终事件之后的敏感支付卡信息是显而易见的。](https://kafka.apache.org/documentation/#intro_streaming)

所有这些事件都被归类为不同的主题，Prat 将其定义为“将被编写和消费的消息的语义集合。”主题可以包含来自多个生产者或来源的数据(例如发出温度数据的传感器)，并由任意数量的客户端使用。因此，了解谁拥有这些主题，谁可以读写关于它们的数据，以及它们的模式是什么以促进数据治理是至关重要的。

## (计划或理论的)纲要

模式的概念——在数据建模和数据集成方面经常被考虑——对于正确管理 Kafka 的数据是必不可少的。Klaw 帮助定义模式，并解释 Prat 所谓的与数据源或业务需求变化相关的“模式演变”。“图式就是信息看起来的样子，所以每个人都知道他们能从这个话题中得到什么，”Prat 解释道。“我得到了那个消息；看起来是这样的。它有这样的形状，我知道我会得到什么。”

主题很容易包含对业务需求的修改，以帮助模式发展来反映新的或正在进行的消息元素。“所有这些东西，谁能读，谁能写，模式定义，这就是那个主题的数据治理的管理，”Prat 评论道。

## 实时数据治理

Klaw 是管理来自 Kafka 的数据的可行方法。这有助于确保即使是这些实时、海量的数据也能遵守许多数据治理计划所特有的严格的数据隐私和法规遵从性。通过将这些功能包含在一个开源框架中，Aiven 试图向不同规模、资金支持和成熟度的用户普及这些功能。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>