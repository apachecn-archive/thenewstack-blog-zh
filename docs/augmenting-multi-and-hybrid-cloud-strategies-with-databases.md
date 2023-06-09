# 用数据库增强多云和混合云战略

> 原文：<https://thenewstack.io/augmenting-multi-and-hybrid-cloud-strategies-with-databases/>

威廉·奎维格

威廉是 Couchbase 的社区主任。他以前是 Docker 的社区负责人。在过去的 15 年里，他一直在开源社区工作，为一系列组织工作，包括 Mozilla Firefox、联合国和开放网络基金会。

“云”不仅是科技领域的一个流行语，它已经成为下一代数字业务的载体，企业正在调整其战略，以利用云功能，并满足人工智能、物联网和边缘计算革命的需求。据 Gartner[称，到 2022 年底，四分之三的企业将采用多云或混合云方法。](https://www.gartner.com/en/conferences/emea/infrastructure-operations-cloud-germany/featured-topics/cloud)

可以肯定的是，术语“多云”和“混合云”指的是集成了多个云的云部署，尽管它们听起来很相似(有些人可以互换使用这两个术语)，但它们所包含的云基础架构种类不同。下面快速回顾一下这两种云方法，它们的主要优势是什么，以及数据库在每种方法中的作用。

## **多云和混合云**

多云指的是在单一异构架构中使用来自不同供应商的多个云计算和存储服务。该解决方案适用于希望与多个云提供商合作的公司，以便在多个云存储技术和基础架构提供商之间分配工作负载和数据。

混合云略有不同，因为它是一个混合的计算、存储和服务环境，由内部基础架构、私有云服务和公共云组成，并在各种平台之间进行协调。换句话说，如果一家公司在其数据中心使用公共云、内部计算和私有云的组合，那么他们本质上是在使用混合云基础架构。

## **多云方法的优势**

许多公司被吸引到多云方法，因为它在降低总体成本的同时提高了服务和安全性。这种方法不仅可以让公司分配其技术能力，确保应用程序性能更好、可用性更高，还可以让公司选择不同地区的云提供商，以最好地满足其特定需求，例如平衡用户负载或减少系统故障转移。

多云方法的其他一些优势包括:

*   **通过确保数据存储资源始终可用，提高了弹性**。它还有助于最大限度地减少延迟、抖动和丢包等影响性能的因素，这些因素通常是由网络和服务器之间的跳跃引起的。
*   **提高灵活性和可扩展性**让公司能够根据需要灵活扩展存储需求。
*   **通过优化离应用程序和用户最近的区域和分区的数据存储和处理，提高性能**。随着越来越多的全球云提供商推出边缘计算解决方案，这一点尤其明显。改进的邻近性导致更好的性能和减少的延迟。
*   **优化投资回报**让公司能够在不影响选择的情况下加速利用任何云资源。多云基础设施提供了一套丰富的云选项来解决各种计算和业务功能的严格需求，从而优化云投资回报。
*   **降低总拥有成本**通过允许不同基础设施即服务(IaaS)提供商之间的服务混合和匹配来降低总拥有成本，尤其是对于更大、更复杂的应用程序。将所有系统放在一个单独的云提供商之内无法将部分工作负载或系统转移到另一个价格更好的提供商。
*   **不再依赖单一供应商，降低了风险**。随着一家公司在一家 IaaS 提供商中添加越来越多的技术解决方案，这一数字会成倍增加。

## **混合云方法的优势**

虽然混合云方法的优势非常相似，但混合云的主要优势是敏捷性，它允许公司快速适应和改变方向。例如，一家公司可能会决定将公共云、私有云和内部资源结合起来，以获得竞争优势所需的敏捷性。

通过将一些应用程序和技术放在公共云中，将一些放在管理更加完善的环境中，公司可以获得灵活性、弹性和对成本的更多控制。从安全角度来看，公司可以将其最注重安全性的工作负载保留在私有云中，同时在经济高效的公共云网络中运行常规业务数据和应用。例如，一家公司可能希望在公共云中部署面向客户的 web 应用程序，但要确保其任务关键型系统在内部运行，以获得更好的隐私、数据安全性和控制。

## **评估适合您云战略的数据库**

数据库是支持任何现代应用程序的设计、开发和功能的核心，因此也是公司云方法的核心。在评估适合公司云战略的最佳数据库管理系统(DBMS)时，需要考虑以下几个关键因素:

*   **该技术是否提供自动复制和同步功能？**在节点和集群之间快速高效地平衡和分配工作负载，以全面支持多云和混合云策略，这是企业在数据平台中应该寻求的一项关键功能。通过自动化复制技术，组织可以满足当今企业的冗余、故障转移和灾难恢复要求。此外，数据更新必须即时反映到组织的整个生态系统中，以确保企业提供数据完整性和弹性。
*   **它能降低风险并满足数据隐私要求吗？**隔离数据并将存储和处理管理限制在特定集群和节点的能力有助于组织满足国内和国际日益严格的数据隐私和主权要求。
*   **it 是否能够本地化数据以改善客户体验？**组织需要能够将特定数据存储在离用户和应用最近的区域的数据库架构，以便提供出色的客户体验。这使得企业能够减少网络跳数，提高延迟和应用程序性能。

## **采用多云或混合方法的 Couchbase】**

从一开始，Couchbase 的现代数据库就被设计为云原生的，以向客户提供最大的灵活性，并使其能够轻松获得跨其部署的一致优势。了解[客户](https://www.couchbase.com/customers?ref=blog)如何跨各种云策略使用 Couchbase 来提高弹性、性能和稳定性，同时降低风险和总拥有成本。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>