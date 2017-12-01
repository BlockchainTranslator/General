# A Tour of Cosmos for Developers
# Cosmos 开发者之旅

> 本文翻译自：https://blog.cosmos.network/a-tour-of-cosmos-for-developers-7517ba1b4045
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [龙心小台](https://github.com/xnylong/EOS)
> 
> 原文发表时间：2017-11-23
>
> 翻译时间：2017-11-24

![](pics/A-Tour-of-Cosmos-for-Developers.png)


If you want to develop a decentralized application today, you have multiple choices. Depending on the use case, a decentralized application can be built as a blockchain (application-specific blockchain) or on top of an existing blockchain (e.g. a smart contract on Ethereum). The former option allows for full flexibility but is costly in terms of development, while the latter allows for easy deployment at the cost of limited performance and sovereignty. In both cases, you won’t have interoperability outside of your application’s underlying blockchain environment.

如果今天你想开发一个去中心化的应用程序，你有多种选择。 取决于应用场景，去中心化应用程序可以构建为区块链（为某个应用程序特别开发的区块链），也可以构建在现有区块链之上（例如以太坊上的智能合约）。 前者拥有充分的灵活性，但在开发方面代价昂贵，而后者以有限的性能和主权为代价，可以让你轻松地完成部署。 在这两种情况下，应用程序底层区块链环境之外都不会有互操作性。

Cosmos exists to solve these problems. It comes with a powerful toolkit based on [Tendermint](https://tendermint.com/) that enables developers to easily build decentralized applications. If your application requires sovereignty and flexibility, you can deploy your own blockchain without having to deal with the complicated networking and consensus parts of the software — thanks to Tendermint and its [Application-Blockchain Interface (ABCI)](https://github.com/tendermint/abci). If your application is of smaller scale and you don’t need your own chain, you can deploy it on [Ethermint](https://blog.cosmos.network/a-beginners-guide-to-ethermint-38ee15f8a6f4), which allows you to do everything Ethereum does — but with far greater performance. Finally, if you want to retain full privacy and control over your application, Tendermint enables you to deploy private blockchains.

Cosmos 的存在就是为了解决这些问题。 它配备了基于 [Tendermint](https://tendermint.com/) 的强大工具包，使开发者能够轻松构建去中心化的应用程序。 如果你的应用程序需要主权和灵活性，那么你可以部署自己的区块链，而无需处理复杂的网络和软件的共识部分 - 这多亏了 Tendermint 及其[应用区块链接口（ABCI）](https://github.com/tendermint/abci)。 如果你的应用程序规模较小，而且你不需要自己的链，那么你可以将应用程序部署到 [Ethermint](https://blog.cosmos.network/a-beginners-guide-to-ethermint-38ee15f8a6f4) 上，Ethermint 可以让你做到所有以太坊能做到的事，而且性能要高得多。 最后，如果你想保留完整的隐私和对应用程序的控制，Tendermint 可以让你部署私有链。

The good news is: all these applications are interoperable and can exchange value with each other. Together, they form the Cosmos ecosystem — an internet of blockchains.

好消息是：所有这些应用程序都具有互操作性，可以相互交换价值。 它们共同构成了 Cosmos 生态系统 - 一个区块链的互联网。

## Understanding Cosmos
## 了解 Cosmos 

There are two types of blockchains in the Cosmos ecosystem: Hubs and Zones. Zones are sovereign blockchains — public or private — built on top of Tendermint. They can exchange value between each other by transacting through Hubs, which act as coordinators to limit overhead. Hubs help isolate zone failures so that global token invariance is preserved. If a zone wants to send tokens to any other zone in the ecosystem, a single connection with a shared Hub is required. This connection is achieved by a protocol called [Inter-Blockchain Communication (IBC)](https://blog.cosmos.network/developer-deep-dive-cosmos-ibc-5855aaf183fe), which is optimized for chains with finality, and in particular, chains built on Tendermint.

Cosmos 生态系统中有两种类型的区块链：枢纽和分区。 分区是建立在 Tendermint 之上的主权区块链（公有或私有）。 他们可以通过枢纽进行交易来交换价值，枢纽在此作为协调者以限制管理费用。 枢纽可以帮助隔离分区发生的故障，从而保持各个分区中各类代币总量不变。 如果某个分区要将代币发送到生态系统中的任何其他分区，则需要与共享枢纽的单一连接。 这种连接是通过[区块链间通信（IBC）](https://blog.cosmos.network/developer-deep-dive-cosmos-ibc-5855aaf183fe)协议实现的，该协议针对具有最终性的链进行优化，特别是基于 Tendermint 的链。

Tendermint and IBC are the bread and butter of the Cosmos ecosystem. Let’s look into the detail of these two components.

Tendermint 和 IBC 是 Cosmos 生态系统的面包与黄油。 让我们来看看这两者的细节。

### Tendermint

A blockchain can be divided in three layers: networking, consensus and application. Before Tendermint was created, building a blockchain required building all the 3 layers from the ground up, you needed to build all three layers from the ground up, which represented a considerable amount of work.

一个区块链可以分为三层：网络、共识与应用。 在 Tendermint 被创建之前，三层都需从头构建才能建立区块链，这需要相当多的工作量。

The goal of Tendermint is to ease the development of blockchains by providing a standard engine that deals with the networking and consensus layers. The only thing developers have to worry about is the application layer, on which they have full control. The interface that connects the state machine (application) to the underlying consensus engine is a socket protocol called Tendermint [ABCI](https://github.com/tendermint/abci).

Tendermint 的目标是通过提供处理网络和共识层的标准引擎来使区块链的发展更容易。 开发者唯一需要担心的是应用层，而且开发者对应用层拥有完全控制权。 将状态机（应用程序）连接到底层共识引擎的接口是一个名为 Tendermint [ABCI](https://github.com/tendermint/abci) 的套接字协议。

Tendermint provides these benefits:

Tendermint 提供了下列好处：

- **Develop in any language.** Tendermint is a general purpose blockchain consensus engine that is agnostic to the application built on top of it. This means that Tendermint blockchains can be developed in any language. This also means that Tendermint can be used as a plug-and-play replacement for the consensus engines of other blockchain software. One can take the current Ethereum code base, whether in Go, Rust, or Haskell, and run it as an ABCI application using Tendermint consensus. Indeed, [we did that with Ethereum](https://ethermint.network/). Another example of a cryptocurrency application built on Tendermint is the Cosmos Hub.
  
- **可用任意语言开发。** Tendermint 是一个通用的区块链共识引擎，独立于建立在它之上的应用。 这意味着 Tendermint 区块链可以用任意语言开发。 这也意味着Tendermint 可作为其他区块链软件共识引擎的即插即用替代品。 无论是 Go，Rust还是 Haskell，都可以使用当前的以太坊代码库，并使用 Tendermint 共识将其作为ABCI 应用运行。 事实上，[我们是用以太坊来做到的](https://ethermint.network/)。 建立在 Tendermint 上的加密货币应用程序的另一个例子是 Cosmos 枢纽。
  
- **Public or private blockchain capable.** Since developers can deploy arbitrary applications on top of Tendermint, it is possible to develop both permissioned and permissionless blockchains on top of it.
  
- **公有或私有链适用性。** 由于开发者可以在 Tendermint 上部署任意应用，因此需许可的与无需许可的区块链都可以在 Tendermint 上开发。
  
- **Performance.** Tendermint is a state of the art replication (blockchain) engine. Tendermint Core can have a block time on the order of 1 second and handle thousands of transactions per second.
  
- **性能。** Tendermint 是最先进的复制（区块链）引擎。 Tendermint Core 的出块时间可达 1 秒，且每秒可处理成千上万笔交易。
  
- **Instant finality.** A property of the Tendermint consensus algorithm is instant finality, meaning that forks are never created, as long as no more than a third of the validators are malicious (byzantine). Users can be sure their transactions are finalized as soon as a block is created.
  
- **即时最终性。** Tendermint 共识算法的属性之一是即时最终性，意味着只要没有超过三分之一的恶意验证人（拜占庭），分叉便永远不会发生。 一旦区块被创建，用户便可确保他们的交易是达成了最终共识的。
  
- **Security.** Tendermint consensus is not only fault tolerant, it’s optimally Byzantine fault-tolerant, with accountability. If the blockchain forks, there is a way to determine liability. We had Tendermint Core audited through Jepsen.io, a distributed systems security analysis tool, and the results verify that Tendermint BFT does not violate its stated guarantees: https://jepsen.io/analyses/tendermint-0-10-2.
  
- **安全性。** Tendermint 共识不仅容错，而且是问责制的最优拜占庭容错。 如果区块链分叉了，问责制可让我们明确责任。 我们通过分布式系统安全分析工具 Jepsen.io 对 Tendermint Core 进行审计，结果证实 Tendermint BFT 未违反其声明的保证：https://jepsen.io/analyses/tendermint-0-10-2。
	
You can learn more about Tendermint [here](https://tendermint.com/).

你可[在此](https://tendermint.com/)了解更多关于 Tendermint 的信息。

### IBC | 区块链间通信

Zones in the Cosmos ecosystem can exchange tokens with each other via a protocol called IBC. This protocol takes advantage of the fact that every chain runs on top of the same core engine, Tendermint, which provides instant finality. Zones do not need to establish an IBC connection with every other zone, only a single connection with a Hub is sufficient to send tokens to every zone that is connected to it.

Cosmos 生态系统中的分区可以通过区块链间通信（IBC） 协议交换代币。 该协议利用了这样一个事实, 即每个链都在相同的核心引擎Tendermint 上运行,  Tendermint 提供了即时最终性。 分区之间无需建立 IBC 连接，一个分区只需与一个枢纽建立单个连接就足以将代币发送到与该枢纽连接的每个分区。

One of the main benefits of IBC is that it does not infringe on the sovereignty of individual zones. Every blockchain in the Cosmos ecosystem relies on a set of validators responsible for committing new blocks to the blockchain. For a blockchain to be sovereign it is important that the application has control over validator set changes. In a public setting, this is achieved with a staking token and Proof-of-Stake algorithm. In private settings, the application can grant privileges to a certain pool of address to make changes to the validator set. In both cases, IBC does not require that the application surrenders control over the validator set. Each zone can have its own validator set and business logic while retaining IBC compatibility.

区块链间通信 (IBC) 的主要好处之一是它不会侵犯个别分区的主权。 Cosmos 生态系统中的每个区块链都依赖于一组验证人，负责将新的区块提交给区块链。 为了使区块链拥有主权，应用程序需要可以控制验证人组的更改。 在公共环境中，这是通过权益代币与权益证明算法来实现的。 在私有设置中，应用程序可给特定地址授权， 以使其有权更改验证人集。 在这两种情况下，IBC 都不要求应用程序放弃对验证人集的控制权。 每个分区都可拥有自己的验证人集和商业逻辑，同时保持 IBC 兼容性。

As a result, each zone can implement its own governance mechanism to upgrade the software without losing compatibility with the rest of the ecosystem. Additionally, fully private blockchains can send and receive token from public blockchains or other private blockchains, opening a whole new range of possibilities for existing institutions and businesses that require high levels of control and privacy.

因此，每个分区都可实施自己的治理机制来升级软件，而不会失去与其他生态系统的兼容性。 此外，完全私有的区块链可以发送和接收来自公有链或其他私有链的代币，为目前需要高度控制和隐私性的机构与企业提供了全新的可能性。

You can learn more about IBC [here](https://github.com/cosmos/ibc/blob/master/CosmosIBCSpecification.pdf).

你可[在此](https://github.com/cosmos/ibc/blob/master/CosmosIBCSpecification.pdf)了解更多关于 IBC 的信息。

## Developing on Top of Cosmos
## 在 Cosmos 上开发

Once you have analyzed the benefits of Cosmos and want to move ahead, there are various possibilities for how to develop your application. Different options have different benefits that allow you to make the optimal choice based on the importance of factors including speed of development, performance or your application’s need for sovereignty.

一旦你分析了 Cosmos 的好处并想继续，Cosmos 上有各种各样的可能性来开发你的应用。 不同的选择有不同的好处, 使你能够根据不同因素的重要性 (包括开发速度、性能或应用程序对主权的需要) 做出最佳选择。

### Building your own ABCI app | 构建你自己的区块链应用接口  (ABCI) 应用程序

**Pros:**
- Full control and flexibility over the application
- Programmability. Code your blockchain with your preferred programming language
- Public or private
  
**优点：**
- 对应用的完全控制与灵活性
- 可编程性。 使用你喜欢的编程语言来编写你的区块链
- 公有或私有
	
**Cons:**
- Out of the three options, this is the one that requires the most development efforts, especially if you’re building a public blockchain (even if Tendermint saves you a lot of work!).
  
**缺点：**
- 在这三种选项中，此选项需要最多的开发工作，特别是如果你正在构建一个公有链（即使 Tendermint 为你节省了大量的工作）。
	
**Good for:** Applications that require their own chain and maximum flexibility, projects with high resources/network effect, private chains.

**适用于：** 需要自己的链条和最大灵活性的应用程序，具有大量资源/网络效应的项目，以及私有链。

Learn more [here](https://tendermint.readthedocs.io/en/master/app-development.html)

[在此](https://tendermint.readthedocs.io/en/master/app-development.html)了解更多

### Build on top of cosmos-sdk | 构建于 Cosmos - SDK 之上

The Cosmos SDK is an [ABCI application](https://github.com/tendermint/abci) designed to be used with the [Tendermint consensus engine](https://tendermint.com/) to build a Proof-of-Stake-based cryptocurrency. It also provides a general purpose framework for extending the feature set of the cryptocurrency by implementing plugins.

Cosmos SDK 是一个 [ABCI 应用程序](https://github.com/tendermint/abci)，旨在与 [Tendermint 共识引擎](https://tendermint.com/)一起使用来构建基于权益证明的加密货币。 它还提供了一个通用框架，通过应用插件来扩展加密货币的功能集。

**Pros:**
- Built-in plugins optimized for Proof-of-Stake blockchain (staking, governance,…)
- Design considerations taken care of
  
**优点:**
- 内置插件，针对权益证明区块链进行了优化（锁定权益，治理...）
- 设计方面无需操心
	
**Con:**
- Language constraint (golang)
  
**缺点：**
- 语言限制（golang）
	
**Good for:** Public proof of stake blockchains

**适用于:** 公有的权益证明区块链

Learn more [here](http://cosmos-sdk.readthedocs.io/en/latest/)

[在此](http://cosmos-sdk.readthedocs.io/en/latest/)了解更多

### Build on top of an existing blockchain like the Ethermint zone | 建立在如 Ethermint 分区的现有区块链之上

Ethermint is the high speed implementation of Ethereum built on top of Tendermint. Part of Tendermint’s goal, once Ethermint is launched together with the Cosmos Hub, is to give developers the best of both worlds — the full capabilities of writing and executing smart contracts in Ethereum plus all the added performance and interoperability benefits of a Tendermint-powered zone in the Cosmos Ecosystem.

Ethermint 是建立在 Tendermint 之上的以太坊的高速项目。 一旦 Ethermint 与 Cosmos 枢纽一同推出，Tendermint 的目标之一就是为开发者提供两全其美的解决方案 - 同时拥有在以太坊编写和执行智能合约的能力，以及 Cosmos 生态系统中由 Tendermint 驱动分区的所有附加性能和互操作性优势。

**Pros:**
- Just like an Ethereum application but with better performance and compatibility with the Cosmos ecosystem
- No need to deal with security / setting up a validator set

**优点：**
- 和一个以太坊应用程序相似，但具有更好的性能和与 Cosmos 生态系统的兼容性
- 无需考虑安全性问题/设置验证人集
	
**Con:**
- Less flexibility and sovereignty

**缺点：**
- 更少的灵活性和主权

**Good for:** Small to medium public decentralized applications that do not require their own chain

**适用于:** 不需要自己的链的，中小型公有去中心化应用程序

Learn more [here](https://github.com/tendermint/ethermint).

[在此](https://github.com/tendermint/ethermint)了解更多。

## Build with Lotion | 通过Lotion构建

Lotion is a JavaScript library for Cosmos applications which aims to make writing new blockchains fast, fun, and easy for beginners. Like the Cosmos SDK, it builds on top of Tendermint using the ABCI protocol.

Lotion 是一个用于 Cosmos 应用程序的 JavaScript 库，旨在使初学者能够快速，有趣地编写新的区块链。 像 Cosmos SDK 一样，它使用 ABCI 协议，并建立在 Tendermint 之上。

Lotion itself is a tiny framework; its true power comes from the network of small, focused modules built upon it. Adding a fully-featured cryptocurrency to a blockchain, for example, takes only a few lines of code.

Lotion 本身是一个小框架， 其真正的力量来源于建立在其上的小型、集中模块化网络。 举例来说，将一个具有完整功能的加密货币添加到区块链中只需要几行代码。

Writing a Lotion application is often as simple as writing a single function that mutates the application’s state (held in a single JavaScript object) in response to a transaction.

通常，编写一个 Lotion 应用程序就像编写一个单一的程式来改变应用程序的状态（存储在一个 JavaScript 对象中），并以此来响应一个交易一样简单。

**Pros:**
- Easy to use
- Access to the 500k+ modules on npm
- Cosmos-compatible via IBC
  
**优点:**
- 使用方便
- 可在 npm 上访问 500k+ 的模块
- 通过 IBC 与 Cosmos 兼容
  
**Con:**
- Light client support not yet implemented
- Experimental
  
**缺点:**
- 轻客户端支持尚未实现
- 处在实验阶段
	
**Good for:** Experimental blockchain applications, prototypes, javascript developers

**适用于：** 实验性区块链应用程序，原型，JavaScript 的开发人员

Learn more [here](https://lotionjs.com/)

[在此](https://lotionjs.com/)了解更多

## Deploying a decentralized application on Cosmos
## 在 Cosmos 上部署一个去中心化的应用程序

After you’ve developed and tested your application, it is time to deploy it. Once again, several options are available for you to choose from.

在你开发并测试应用程序之后，现在是部署它的时候了。与之前类似，现在仍有若干选项供你选择。

### My application is a public proof of stake blockchain | 我的应用是公有的权益证明区块链

If you’ve decided to go for a public proof of stake blockchain, either through a custom ABCI-app or a sdk-based app, you will most likely need to have a staking token and bootstrap a validator set.

如果你决定通过自定义的 ABCI 应用程序或基于 SDK 的应用程序来构建公有的权益证明区块链，那么你很可能需要权益代币并且引导验证人组。

Two questions then arise :
- What is the initial distribution of the staking token ?
- How to find validators to bootstrap the network ?
	
随后会出现两个问题：
- 权益代币的初始分布是什么？
- 如何找到验证人来引导网络？

**Pooled security**
**集中的安全性**

Bootstrapping a network is demanding in terms of resources, and blockchains that fail to reach critical mass could be exposed to security issues. For small to medium projects that require their own blockchain, the launching phase could prove difficult to handle. To circumvent this problem, these blockchains could pool security together. In effect, they would share the same validator set and staking token.

引导网络对资源的要求很高，而未能达到临界质量的区块链可能会暴露在安全隐患下。对于需要自己区块链的中小型项目来说，启动阶段可能会难以处理。为了避免这个问题，这些区块链可以将安全性集中在一起。实际上，他们将共享相同的验证人组和权益代币。

One way of implementing this would be via an incubator zone. Validators of this zone would lend their services to chains in exchange for some compensation. Chains would apply to be supported by the incubator zone and admission would be handled by the incubator’s governance system. Once an incubated chain reaches critical mass and if it makes sense, it would be able to move away from the incubator zone and become independent; that is, have its own staking token and validator set. Incubator zones do not exist yet, but they would be good additions to the Cosmos ecosystem in the future.

实现这点的一种方式是通过一个孵化器分区。这个分区的验证人将把他们的服务借给区块链来换取一些补偿。区块链将申请孵化器分区的支持，并由孵化器的治理系统来决定是否录取。一旦孵化的区块链达到临界质量，如果合适，它将能够离开孵化器分区并独立存在。也就是说，它将拥有自己的权益代币和验证人组。孵化器分区目前还不存在，但它们将成为未来 Cosmos 生态系统的良好补充。

### My application lives on top of an existing blockchain such as Ethermint | 我的应用程序构建在现有区块链（如Ethermint）之上

In this case, the deployment process is easier since you do not have to concern yourself with setting up a staking token and validator set. You can just deploy your application using the tools given by the underlying blockchain you’re using. For example, with Ethermint, you can use all the tools available for Ethereum, such as Truffle. A tutorial for doing this can be found here.

在这种情况下，部署过程更容易，因为你不必关心设置权益代币和验证器人组的问题。你可以用你正在使用的底层区块链提供的工具来部署你的应用程序。例如，有了 Ethermint，你可以使用以太坊提供的所有工具，比如Truffle。在此可找到相关教程。

### My application is a private blockchain | 我的应用程序是一个私有链

If your application is a private chain, you don’t need a staking token, and validators are known entities. You just have to launch your chain with an initial validator set of your choice and implement a mechanism to allow an address or set of addresses to authorize validator set changes.

如果你的应用程序是一个私有链，你不需要一个权益代币，而验证人是已知的实体。你只需要用你选择的初始验证人组来启动你的链，并通过一个机制来允许一个或一组地址，以授权验证人组的变动。

## Conclusion
The Cosmos network offers various options for running decentralized applications. They range from already-built Ethereum applications on Ethermint, all the way to creating high performance custom-built blockchains. Cosmos is set to launch in a few months with the release of the Cosmos Hub. With many projects already preparing to launch on Cosmos, the time to embrace the coming internet of blockchains and build consumer-ready decentralized applications has arrived.

## 结论
Cosmos 网络提供了运行去中心化应用程序的各种选项。 他们的范围涵盖从Ethermint 上已经建成的以太坊应用程序，一直到创建高性能的定制区块链。 伴随着 Cosmos 枢纽的发布，Cosmos 将在几个月内上线。 随着许多项目已经做好准备在 Cosmos 上发布，我们即将迎来拥抱区块链互联网和构建消费者去中心化应用程序的时代。



----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 文本译者简介

龙心小台，区块链学习者，微信公众号：视听区块链

本文由币乎社区（bihu.com）内容支持计划赞助。

版权所有，转载需完整注明以上内容。

----------------------------------------------------
