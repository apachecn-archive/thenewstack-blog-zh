# 为什么选择 NoSQL 数据库？有很多重要的原因

> 原文：<https://thenewstack.io/why-choose-a-nosql-database-there-are-many-great-reasons/>

NoSQL 是“不仅是 SQL”的缩写，是一个用于数据库系统的术语，它以各种格式存储信息，以支持传统关系(或 SQL)数据库难以解决的需求。在存储极其昂贵的时代，传统的关系系统旨在最大限度地减少数据重复。

虽然关系数据库仍然被广泛使用，但数据存储和使用的性质已经发生了变化。例如，像谷歌风格的搜索这样的东西被内置到大多数应用程序中。数据爆炸、网页浏览、移动使用和分析极大地改变了现代数据库的需求。这些新需求导致了 NoSQL 数据库的增长，包括各种模型，如键值、文档、列、时间序列和图形。此外，领先的 NoSQL 数据库现在还包括关键的关系功能。

## 什么是现代多模式 NoSQL 数据库？

多种数据访问方法，也称为多模型，使得数据库在各种各样的用例中都很有用。JSON (JavaScript Object Notation)是一种常见的 NoSQL 数据格式，它提供了灵活性，并能很好地适应不同的访问模式。NoSQL 数据库作为主要的内容存储，这意味着您可以在一个应用程序中输入数据，但可以根据使用情况以多种方式访问它。随着时间的推移，这使得应用程序更容易开发和发展。许多 NoSQL 数据库从头开始构建，以实现快速、灵活和高可用性——支持现代云计算、分发和[数据管理需求](https://thenewstack.io/microservices-and-nosql-a-great-match/)。

## **为什么组织选择 NoSQL**

最大的因素之一是需要提供卓越的客户体验，这是一个关键的竞争优势。客户期望通过按需、实时、个性化和快速响应的服务获得出色的数字体验。因此，应用程序必须是动态的，跨多种设备运行并不断发展。没有合适的技术，管理这种变化速度并不容易。这就是为什么许多组织选择 NoSQL。

## **关系型与 NoSQL 型:主要区别**

关系数据库是为驻留在一台服务器上的后台业务应用程序设计的。为了扩大数据库，您需要一个更大的盒子，称为“垂直扩展”

NoSQL 数据库诞生于互联网周围的大规模数据增长。谷歌和亚马逊在 2005 年左右引领了潮流。高效、分布式、高度可伸缩的键-值引擎是这一进化步骤的关键。从那以后，现代数据库被设计来满足下一代的规模和灵活性。这些数据库提供分布式系统，随着服务器的增加，通过在多个节点之间自动分发数据来提供高可用性。通过 JSON 数据模型和多模型访问，NoSQL 数据库可以满足巨大的性能需求，并快速发展，提供新的和快速的客户体验。

## **在 NoSQL 支持 SQL**

关系系统以严格的链接表设计或模式来维护数据。对象数据被拆分到单独的表中以消除重复信息，这称为规范化。虽然这很有效，但当新特性需要更改数据模型时，这通常会受到限制。NoSQL 系统可以保存层次化的 JSON 数据，支持更多的结构和需求，如 ACID 事务，同时还提供灵活的半结构化方式来存储和返回数据。关系数据库和现代 NoSQL 的最佳结合简化了信息体系结构和应用程序开发，并有助于支持现代数据库需求，例如:

*   通过网络和移动设备提供高度响应的体验。
*   处理半结构化和非结构化数据，同时还支持 ACID 事务需求。
*   通过频繁更新快速适应不断变化的用户需求。
*   以更短的上市时间发布新功能。
*   支持多种数据类型和数据访问方法。
*   确保不停机的高可用性。

这些需求可以用关系数据库来满足，但是工作量和成本会非常高。

## **敏捷发展**

速度对创新至关重要，但灵活性也很重要。敏捷开发的核心原则是快速响应变化。通常当需求改变时，数据模型也需要改变。对于关系数据库，开发人员通常必须向数据库管理员正式请求“模式更改”。这会减缓或停止发育。

相比之下，NoSQL 文档数据库完全支持敏捷开发，因为它是无模式的，并且没有静态地定义数据必须如何建模。相反，它遵从应用程序和服务，因此遵从开发人员如何对数据建模。在 NoSQL 中，数据模型是由应用程序模型定义的。

应用程序和服务将数据建模为对象(如员工档案)，将多值数据建模为数组(角色)，将相关数据建模为嵌套对象或数组(如经理关系)。然而，关系数据库将数据建模为行和列的表格——相关数据作为不同表格中的行，多值数据作为同一表格中的行。通过分解和重组对象来读写数据。

相比之下，面向文档的 NoSQL 数据库读取和写入 JSON 格式的数据，这是 web、移动和物联网应用程序消费和生产数据的事实标准。对象的读写不需要分解它们。NoSQL 数据库具有逻辑层次分组，称为集合和/或范围，以组织文档子集，这些子集可以被限制到特定用户、功能或工作负载。

## **在任何规模下操作**

支持 web、移动和物联网应用的数据库必须能够在任何规模下运行。像 Oracle 这样的关系数据库的大规模扩展通常是复杂、昂贵且不完全可靠的。NoSQL 分布式数据库运行在商用硬件上，并被设计为横向扩展—例如，要添加更多资源，您只需添加另一台服务器(也称为“横向扩展”)。向外扩展的能力有助于团队部署满足当前负载所需的硬件；应用较便宜的硬件和/或云基础设施；按需扩展，无需停机。此外，数据中心之间的高级复制在全球范围内扩展了高可用性。

## **在 NoSQL 使用 SQL 和 ACID 事务查询**

习惯于使用 SQL 进行查询的应用程序开发人员可以继续在 NoSQL 平台上使用相同的语言，但是要对存储的 JSON 数据进行操作。精选的现代云数据库供应商提供了一种基于 SQL 的查询语言，该语言在 JSON 中返回结果，并在适当的地方提供行和子文档组件集，支持高级连接并可用于分析。这与大多数其他 NoSQL 数据库形成对比。

由于将对象规范化到多个数据表中，关系系统几乎每次更新都需要一个事务。对于 NoSQL 数据库，更新通常涉及单个文档，不需要事务。一些高级 NoSQL 数据库支持分布式多文档 ACID 事务。

## **数据库即服务**

通常，数据库即服务(DBaaS)可简化运营并减少团队必须完成的工作量，例如基础架构即服务的设置和配置、数据库配置、运营管理、扩展自动化、监控和安全性。

从财务和运营的角度来看，公司看到了以下好处:

*   快速设置
*   扩展能力
*   快速配置更改
*   高服务级别
*   安全自动化

## **NoSQL 支持现代需求**

成千上万的组织已经采用了 NoSQL。选择合适的云数据库平台并不容易。为了支持重要的应用程序，许多[企业选择 Couchbase 五车二](https://www.couchbase.com/customers?ref=blogf=blog)来提高弹性、性能和稳定性，同时降低风险、[数据蔓延](https://blog.couchbase.com/a-story-of-how-multimodel-databases-can-reduce-data-sprawl-told-in-the-pixar-style/)和[总拥有成本](https://blog.couchbase.com/low-tco-with-couchbase/)。开发人员喜欢 Couchbase，因为它将 NoSQL 的灵活性和敏捷性与熟悉的关系数据库概念相结合。这就是为什么 30%的财富 100 强企业使用 Couchbase 数据库平台管理关键数据。

今天就用我们的[免费试用版](https://cloud.couchbase.com/sign-up/)亲自体验一下 Couchbase 吧。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>