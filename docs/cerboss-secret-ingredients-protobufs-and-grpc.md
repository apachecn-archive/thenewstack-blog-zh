# Cerbos 的秘密成分:Protobufs 和 gRPC

> 原文：<https://thenewstack.io/cerboss-secret-ingredients-protobufs-and-grpc/>

当设计任何类型的软件时，决定你的数据格式、类型和结构会让你受益或后悔。在设计 [Cerbos](https://cerbos.dev) 时，我们很早就决定使用结构化的、类型安全的和可序列化的数据，因为我们知道我们希望能够向应用程序公开一个可预测的接口，使用可预测的数据类型，这些数据类型可以被无数种语言的其他服务使用。

选择用来实现这一点的技术是[协议缓冲区](https://developers.google.com/protocol-buffers) (protobuf)，以及 [gRPC](https://grpc.io) ，其中定义了所有的核心特性——包括策略、API、数据存储、数据交换甚至测试用例。

## 一点背景知识

协议缓冲区是一种语言和平台中立的机制，用于序列化结构化数据。与更广为人知的 JSON 格式不同，protobufs 有一个紧凑的二进制网络格式，并且每个消息都有强制模式。

 [查里斯·埃拉瓦拉

Charith 是 Cerbos 的联合创始人兼首席技术官。他之前在 Elastic、Qubit 和 Ocado 从事大规模数据处理平台、分布式系统和 API 服务的工作。他对安全性、编程语言、优化和云原生技术感兴趣。](https://www.linkedin.com/in/charithe/) 

模式语言支持广泛的数据类型、嵌套消息、联合和枚举。protobuf 编译器使用这些模式为开发人员选择的编程语言生成代码。生成的代码包含与模式中定义的抽象类型等效的类型安全的本机数据类型和结构，以及专门的实用函数，如针对每种类型的优化编码/解码函数。

gRPC 是一个使用 protobufs 进行数据交换的 RPC 框架。它使用 HTTP/2 作为传输机制，允许它利用 HTTP/2 规范为服务间(甚至进程间)通信提供的所有速度、安全性和效率特性。gRPC 还受益于代码生成，使 RPC 调用类似于编程语言中的本机函数调用。

我们非常熟悉 protobufs 和 gRPC，因为我们以前的角色是构建高可用性、数据密集型、面向互联网的 API 服务和大规模数据处理系统。Protobufs 简洁而轻量级的接口定义语言(IDL)允许我们创建灵活的模式来描述我们正在处理的数据，并通过添加新字段或取消旧字段来随着时间的推移对它们进行改进，同时保持向后和向前的兼容性。

高效的二进制编码帮助我们节省了带宽，并在不同的处理管道之间快速高效地传输消息。(在处理数十亿条消息的规模下，即使每条消息减少几个字节也会产生巨大的影响。)因为编码的 protobufs 是语言无关的，所以它们是用不同语言编写的应用程序之间交换数据的理想格式，比如用 Go 编写的 API 服务和用 Java 或 Python 编写的数据处理管道。

对于存储具有松散模式的数据(如缓存条目)来说，它们也是一个很好的选择，这些数据仍然可以在选择的编程语言中以类型安全的本机语言结构进行访问。将 gRPC 用于服务是我们使用 protobufs 的自然扩展。同样，它允许我们构建快速高效的 API 服务，以二进制 protobuf 编码交换数据，并在 HTTP/2 上工作，提供双向流和连接多路复用等高级功能。

尽管上面列出了所有的优点，但是以一种非平凡的方式使用 protobufs 曾经是相当痛苦的。上面描述的多语言系统需要一组共享的 protobuf 模式，包括本地导入和第三方导入，比如 Google protobufs。每次模式更新时，我们都必须为多种编程语言、包、版本生成代码，并将它们分发到不同的包注册中心。

我们必须构建自己的定制工具和 CI 作业，以正确地对变更进行版本控制，下载外部依赖项，下载 protobuf 代码生成器，并为每种编程语言编译工具链，生成打包项目，最后构建包并上传到适当的包注册中心。有一些社区构建的工具，比如 ProtoEasy 和 ProtoTool，可以帮助解决一些棘手的问题，比如下载依赖项和语言生成器，但是它们都没有解决这个过程的所有方面。

我们喜欢 gRPC 的流功能、速度和效率——与之前基于 JSON 的 REST 服务相比，我们服务的资源使用明显更低，并且它们具有更好的延迟和吞吐量——但是如果前面没有像 [grpc-gateway](https://grpc-ecosystem.github.io/grpc-gateway/) 这样的转换层，很难对外公开纯 gRPC 服务。流式传输——尤其是双向流式传输——对于转换层来说是不可能的，所以我们也失去了一些功能。

大多数云提供商在他们的负载平衡器上不支持 HTTP/2(事实上，支持仍然很不稳定)。即使可以使用 TCP 负载平衡器解决这个限制，我们仍然有生成 gRPC 客户端代码并将其分发给外部客户的问题。甚至我们自己在浏览器中运行的 JavaScript 代码也无法访问我们的 gRPC 服务。grpc-web 的引入是这个问题的部分解决方案，但是该项目处于非常早期的阶段，功能有限，需要额外的基础设施，如特使代理来进行翻译，这并不理想。

## 生态系统的状况

在过去几年中，protobuf/gRPC 生态系统有了显著的改进。越来越多的组织投资并采用这项技术。像 etcd、CockroachDB 和 Vitess 这样的项目就是构建在 protobufs 和 gRPC 之上的大规模关键基础设施的例子。几乎所有流行的服务网格、代理服务器和负载平衡器现在都支持 gRPC 服务。像 [Dapr](https://dapr.io) 这样的框架使用 gRPC 为应用程序开发提供语言无关的、标准化的组件构建块。(Cerbos 非常类似，因为我们的目标是为任何应用程序提供即插即用的访问控制解决方案。)

许多优秀的工具和实用程序，如 [Buf](https://buf.build) 、 [grpcurl](https://github.com/fullstorydev/grpcurl) 、 [ghz](https://github.com/bojand/ghz) 和 [others](https://github.com/grpc-ecosystem/awesome-grpc) ，使得开发和使用 protobufs 和 gRPC 成为一种更加愉快的体验。Buf 在这里值得一提，因为它解决了本文前面提到的与 protobuf 开发相关的几乎所有麻烦和痛点。(我们不以任何方式隶属于 Buf 我们只是一群快乐的用户，对一个令人敬畏的产品怀有深深的感激。)

## 建造地狱犬

当我们第一次开始构建 Cerbos 时，我们有一套明确的原则需要遵循。

*   Cerbos 应该可以在多语言环境中使用，并提供一致的体验。
    我们的目标用户是那些采用云计算原生计算模式并使用容器、服务网格和声明式 API 等技术构建可扩展、动态、面向服务的系统的用户，这些系统运行在公共/私有/混合云上。然而，根据我们自己的经验，我们知道这些转变不会在一夜之间发生。大多数组织花费数月甚至数年的时间迁移到新的架构，并处理由遗留和新应用程序组成的嵌合环境。通常情况下，迁移还涉及到平台迁移到不同的编程语言，而且有一段时间，用不同语言编写的应用程序必须相互集成和协同工作。在其他情况下，组织将多语言开发作为增加开发人员快乐和速度的一种方式。无论潜在的原因是什么，我们希望确保 Cerbos 能够很好地适应多语言环境，并提供一致的体验，无论使用哪种语言与之交互。我们希望 Cerbos API 尽可能简单，这样任何人都可以通过他们的编程环境提供的内置工具和库开始使用我们的产品。作为一个非常小的团队，我们知道用不同的语言构建 SDK 需要时间。然而，当时机到来时，我们也希望有一个坚实的基础，以避免我们针对的每一种新的编程语言都要重新发明轮子。

*   **地狱犬应该感到“本土”**
    将授权决策委托给外部服务的想法相当激进，容易让很多人紧张。鉴于授权是贯穿整个代码库的横切关注点，这是一个合理的关注点。然而，我们过去(现在仍然)相信解耦访问控制有许多好处，远远超过这些顾虑。毕竟，如今许多应用程序依赖基于云的服务来处理数据库等高度关键的组件并不罕见。与这些服务不同，Cerbos 部署在本地网络(没有互联网中继)上，并且是无状态的(不需要在每个请求上处理万亿字节的数据)。随着技术的进步和确保可靠性和弹性的成熟技术，我们非常有信心 Cerbos 可以像嵌入式解决方案一样运行，同时提供额外的功能，如在整个堆栈中一致的访问实施、无需重新部署的动态更新以及访问规则和审计跟踪的全面可见性。

鉴于上述需求，为 Cerbos 产品的一些最基础的部分选择 protobufs 和 gRPC 是一个自然的选择。今天，几乎所有的核心数据结构和我们大部分广泛的测试套件都是使用 protobufs 定义的，Cerbos 的主要 API 是 gRPC API。

*   我们能够使用 protobuf IDL 为我们的数据结构实施一个模式。它加强了纪律，因为开发人员被迫仔细考虑他们试图做出的改变。自动化工具可以检测和警告任何潜在的破坏性变更，并帮助我们避免进行我们认真对待的向后的、不兼容的变更。
*   我们不必花时间复制或转换通过 gRPC API 接收的对象，因为它们已经是 Cerbos 引擎和其他组件所期望的格式。
*   Cerbos 策略规则包括用通用表达式语言(CEL) 编写的[条件。CEL 运行时支持以类型安全的方式使用 protobufs。同样，这也为我们省去了将请求数据转换成特定数据格式(比如 JSON)的麻烦和开销，JSON 没有 protobufs 那样强的类型保证。](https://docs.cerbos.dev/cerbos/latest/policies/conditions.html)
*   我们可以使用像[protocol-gen-validate](https://github.com/envoyproxy/protoc-gen-validate)这样的插件来基于注释自动生成验证代码， [vtprotobuf](https://github.com/planetscale/vtprotobuf) 来生成优化的编组和解组代码，以及[protocol-gen-OpenAPI v2](https://github.com/grpc-ecosystem/grpc-gateway/tree/master/protoc-gen-openapiv2)来从我们的 gRPC 服务定义生成 open API 规范。我们还开发了自己的定制插件，例如[protoco-gen-go-hashpb](https://github.com/cerbos/protoc-gen-go-hashpb)来生成散列函数，以及[protoco-gen-JSON schema](https://github.com/cerbos/cerbos/tree/main/hack/tools/protoc-gen-jsonschema)来生成 ide 和其他工具可以使用的 JSON 模式。
*   我们可以很容易地在数据格式之间转换，并使用本地语言结构来处理它们。Cerbos 策略有一个 protobuf 模式，我们利用不同的 protobuf 编码器在人类友好的 YAML 或 JSON 到机器友好的二进制 blobs 之间来回读/写和验证这些策略。
*   能够轻松地序列化和反序列化数据结构使我们能够编写简洁的测试，从磁盘加载它们的输入和预期的输出。在我们广泛的测试套件中，很大一部分[是使用 protobuf 模式定义的，并作为 YAML 文件存储在磁盘上。在运行时，我们的测试框架将这些文件中的测试用例加载到我们可以在运行时使用的 Go 结构(由 protobufs 生成)中。](https://github.com/cerbos/cerbos/tree/main/internal/test/testdata)
*   审计跟踪是 Cerbos 产品的核心特性，我们广泛地利用了模式进化特性和 protobufs 的压缩编码格式来存储和处理审计条目。有几种类型的审计条目具有复杂的嵌套结构，如数组，但它们都作为 protobuf 编码的 blobs 存储在我们的审计存储中。我们可以在 Cerbos 的新版本中向审计条目添加新字段，并且仍然可以读取和使用没有这些字段的旧审计条目，因为 protobuf schema evolution 支持这一点。
*   Cerbos 项目本身是用 Go 编写的，但是我们能够很容易地使用其他语言的相同数据结构来构建工具和原型。这给了我们使用最适合手头任务的工具的自由。

Cerbos 的主要 API 表面是使用 gRPC 实现的。在服务器端，我们使用拦截器来实现许多重要的功能，如请求验证、审计日志捕获、指标收集、分布式跟踪传播、错误处理和身份验证。Grpc-gateway 用于为没有 Grpc 实现的人和语言提供 REST+JSON 翻译层。一些 RPC(如用于检索审计日志条目的 RPC)被构建为流式 RPC，可以有效地将大量数据流式传输到具有背压的客户端。

几乎我们所有的客户端 SDK 都使用 gRPC API，主要是为了提高速度和效率。但是，几乎同样重要的是，使用 gRPC 允许我们使用内置的低级管道(支持 mTLS、Unix 域套接字等的 HTTP/2 传输)生成类型安全的客户端存根。)对于大多数流行的编程语言来说。这个基础层为我们提供了一个坚实的基础，在此基础上，我们可以添加一个简单、方便的层，为使用 Cerbos 提供惯用的语言结构。

大多数流行的服务网格和负载平衡器提供 gRPC 请求的跟踪、重试、电路中断和负载平衡，这使用户可以完全控制如何配置其服务，以便与环境中的 Cerbos 服务或 sidecars 进行通信。它还让我们不必为那些复杂的弹性功能重新发明轮子，而是依靠专家构建的经过实战检验的实现。

我们的 protobuf/gRPC 工作流程广泛使用了 [Buf](https://buf.build) ，这是一个几乎神奇的工具，让使用 protobuf 成为一种绝对的乐趣。我们使用 Buf CLI 和 GitHub 动作来格式化、lint、检测重大更改并从 protobufs 生成代码。Buf 自动下载构建所需的依赖项和插件，让我们不必手动管理它们。

在每次成功构建时，Cerbos protobuf 定义会自动上传到 [Buf 模式注册表](https://buf.build/cerbos/cerbos-api) (BSR)，这使我们可以毫不费力地将服务和模式定义分发给任何人使用。BSR 消除了在每个 SDK 存储库中维护 protobuf 定义副本的需要。只需一个命令，开发人员就可以从 BSR 下载最新的定义，并重新生成客户端代码。Buf 的[管理模式](https://docs.buf.build/generate/managed-mode)和[远程插件](https://docs.buf.build/bsr/remote-generation/remote-plugin-execution)在定制输出和管理工具链的过程中变得非常方便。

## 结论

投资 protobufs 和 gRPC 的决定对我们的生产力和速度产生了巨大的积极影响。即使只有一个小团队(四人),我们也已经成功地构建了一个快速、精简、功能丰富的产品和大量的工具、SDK 和演示，如果没有 protobuf/gRPC 生态系统提供的便利性、安全性和生产力，这些都需要花费更多的时间和精力来构建。展望未来，我们将利用同样成熟可靠的技术基础，开发大量令人兴奋的新 Cerbos 功能。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>