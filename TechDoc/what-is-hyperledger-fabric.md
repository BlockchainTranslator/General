What is Hyperledger Fabric?--什么是超级账本 Fabirc?
------------------------------------------------------

> 本文翻译自：http://hyperledger-fabric.readthedocs.io/en/latest/blockchain.html#what-is-hyperledger-fabric
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS)  [荆凯(shuke0327)](https://github.com/shuke0327)
>
> 翻译时间：2017-10-29

---------------------------

The Linux Foundation founded Hyperledger in 2015 to advance cross-industry blockchain technologies. Rather than declaring a single blockchain standard, it encourages a collaborative approach to developing blockchain technologies via a community process, with intellectual property rights that encourage open development and the adoption of key standards over time.

超级账本项目由 Linux 基金会创建于2015年，目的是推进跨行业的区块链技术．该项目并未宣布单一的区块链标准，而是鼓励以协作的方式遵照社区标准过程(community process)开发区块链技术，以知识产权鼓励开放式的开发，随着时间发展而采纳关键的标准．

Hyperledger Fabric is one of the blockchain projects within Hyperledger. Like other blockchain technologies, it has a ledger, uses smart contracts, and is a system by which participants manage their transactions.

Hyperledger Fabric是超级账本项目内部的一个区块链项目．与其他区块链技术一样，它具有账本，使用智能合约，是一个参与者可以管理其交易的系统．

Where Hyperledger Fabric breaks from some other blockchain systems is that it is **private** and**permissioned**. Rather than an open permissionless system that allows unknown identities to participate in the network (requiring protocols like Proof of Work to validate transactions and secure the network), the members of a Hyperledger Fabric network enroll through a**Membership Service Provider (MSP)**.

超级账本 Fabric 与其他区块链系统不同之处在于，它是**私有**和**具有权限控制的**.它不是一个开放的无权限的系统，　并不会允许任何未知身份的用户可以参与到网络之中(需要类似PoW的协议来验证交易，确保网络安全)， 超级账本Fabric网络的成员需要通过一个成员服务提供商（MSP）注册．

Hyperledger Fabric also offers several pluggable options. Ledger data can be stored in multiple formats, consensus mechanisms can be switched in and out, and different MSPs are supported.

超级账本Fbaric也提供了一些可插拔的选项．账簿信息可以存储为多种格式，共识机制也可以切换，并且支持不同的MSP.

Hyperledger Fabric also offers the ability to create **channels**, allowing a group of participants to create a separate ledger of transactions. This is an especially important option for networks where some participants might be competitors and not want every transaction they make - a special price they’re offering to some participants and not others, for example - known to every participant. If two participants form a channel, then those participants – and no others – have copies of the ledger for that channel.

超级账本Fabric项目还提供了创建**通道(Channel)**的功能，允许一组成员创建单独的交易账本．对于一个参与其中的成员可能具有竞争关系的网络而言，这一特性非常重要，参与者并不想自己的每一笔交易 -- 比如，他们提供给某些成员的特殊价格 -- 对网络之中的所有成员可见．如果两个创建者组成一条通道(Channel),　只有这些参与者 -- 而非其他人 -- 才会拥有该通道账本的副本．

## Shared Ledger 共享账本

Hyperledger Fabric has a ledger subsystem comprising two components: the **world state** and the**transaction log**. Each participant has a copy of the ledger to every Hyperledger Fabric network they belong to.

超级账本Fabric的账本子系统具有两个组件："世界状态(world state)"和交易记录．每个成员都会有一份他们所属的每一个超级账本Fabric网络的账本副本．

The world state component describes the state of the ledger at a given point in time. It’s the database of the ledger. The transaction log component records all transactions which have resulted in the current value of the world state. It’s the update history for the world state. The ledger, then, is a combination of the world state database and the transaction log history.

世界状态组件描述了某个时间点上账本的信息．它是账本的数据库．交易记录(transaction log)组件，记录了导致了当前的世界状态的所有交易．它是世界状态的更新历史．账本，就是一个世界状态数据库和交易记录历史的组合．

The ledger has a replaceable data store for the world state. By default, this is a LevelDB key-value store database. The transaction log does not need to be pluggable. It simply records the before and after values of the ledger database being used by the blockchain network.

账本中世界状态的数据库存储方式是可替换的．默认是用的LevelDB的键值存储数据库．交易记录并不需要可插拔．它仅仅记录了区块链网络中所用账本数据库的前值和后值．

## Smart Contracts　智能合约


Hyperledger Fabric smart contracts are written in **chaincode** and are invoked by an application external to the blockchain when that application needs to interact with the ledger. In most cases chaincode only interacts with the database component of the ledger, the world state (querying it, for example), and not the transaction log.

超级账本Fabric智能合约用**链码( chaincode )**编写，区块链外部的程序在需要与账本交互时，会激活链码.　大多数情况下chaincode只与账本的数据库组件--世界状态组件产生交互(例如，查询)，而非交易记录组件．

Chaincode can be implemented in several programming languages. The currently supported chaincode language is [Go](https://golang.org/) with support for Java and other languages coming in future releases.

Chaincode可以用多种语言来实现．当前支持的语言是[Go语言](https://glolang.org)，未来发布中会支持Java和其他语言．

## Privacy 私有性

Depending on the needs of a network, participants in a Business-to-Business (B2B) network might be extremely sensitive about how much information they share. For other networks, privacy will not be a top concern.
不同网络，这方面的需求会有所不同，B2B网络的参与者对于所分享信息的多少会非常敏感．对于其他网络而言，私有性并非最关心的问题．

Hyperledger Fabric supports networks where privacy (using channels) is a key operational requirement as well as networks that are comparatively open.

超级账本Fabric会支持将私有性视为关键运营要求的网络(使用通道)，同时也支持相对公开的网络．

## Consensus 共识机制


Transactions must be written to the ledger in the order in which they occur, even though they might be between different sets of participants within the network. For this to happen, the order of transactions must be established and a method for rejecting bad transactions that have been inserted into the ledger in error (or maliciously) must be put into place.

交易记录必须按照发生的顺序写入到账本上，尽管这些交易可能发生在网络上不同组的参与者中．为了做到这一点，必须确定交易记录的顺序，必须有方式可以拒绝错误的交易记录，这些记录由于错误(或出于恶意)而被插入到账本中．

This is a thoroughly researched area of computer science, and there are many ways to achieve it, each with different trade-offs. For example, PBFT (Practical Byzantine Fault Tolerance) can provide a mechanism for file replicas to communicate with each other to keep each copy consistent, even in the event of corruption. Alternatively, in Bitcoin, ordering happens through a process called mining where competing computers race to solve a cryptographic puzzle which defines the order that all processes subsequently build upon.

这是在计算机科学之中得到充分研究的领域，有多种方式可以实现，每种方式都有不同的权衡．例如，PBFT(拜占庭容错)能够提供一种机制，使得即便存在腐败事件，文件副本彼此间能够通讯，保持每份副本的一致性．另外，在比特币中，交易顺序通过一个被称为挖矿的过程产生，相互竞争的计算机争相解决密码学难题，这决定了后续过程所构建于其上的顺序．

Hyperledger Fabric has been designed to allow network starters to choose a consensus mechanism that best represents the relationships that exist between participants. As with privacy, there is a spectrum of needs; from networks that are highly structured in their relationships to those that are more peer-to-peer.

超级账本Fabric项目被设计为允许网络发起者选择能够最好的表示参与者之间关系的共识机制．与私有性一样，这方面的需求也存在一系列的光谱，从关系高度结构化的网路，到p2p的同等节点网络．

We’ll learn more about the Hyperledger Fabric consensus mechanisms, which currently include SOLO, Kafka, and will soon extend to SBFT (Simplified Byzantine Fault Tolerance), in another document.

我们会研究更多的超级账本共识机制，当前包含SOLO, Kafka, 很快也会扩展到　SBFT(简化拜占庭容错)，我们会在另外一篇文档中说明．


----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

荆凯，程序员，相信区块链终将改变潮水的方向．欢迎加微信号:shuke0327，也可以关注公众号: 增长之道

本文由币乎社区（bihu.com）内容支持计划赞助。

版权所有，转载需完整注明以上内容。

----------------------------------------------------
