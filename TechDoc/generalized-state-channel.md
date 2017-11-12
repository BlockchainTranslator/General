Generalized State Channels on Ethereum
------------------------------------------------------

> 本文翻译自：https://medium.com/l4-media/generalized-state-channels-on-ethereum-de0357f5fb44
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS)  [Xuming Meng](https://github.com/jonas-meng)
>
> 翻译时间：2017-11-12

---------------------------

# Generalized State Channels on Ethereum #
# 以太坊的广义状态通道 #

A fundamental limitation of blockchain applications is that blockchains are expensive. Sending transactions requires fees, and using ethereum to run smart-contract code is comparatively costly to other kinds of computation.

区块链应用的根本局限在于区块链很昂贵。发送交易需要费用，使用以太网运行智能合约代码对于其他类型的计算来说成本相对较高。

The idea behind state channels is that we can make blockchains more efficient by moving many processes off-chain, while still retaining a blockchain’s characteristic trustworthiness. Despite their conceptual simplicity as a natural extension of the “payment channel” concept, this technique today remains heavily under-utilized and underdeveloped.

状态通道背后的想法是，我们可以通过将许多处理事转移到区块链外来提高区块链的效率，同时保持区块链的可信的特征。尽管从概念上的简单性而言，他们只是“支付通道”概念的自然延伸，但是今天的这种技术仍然没有得到充分的利用和发展。

This is why we are excited to share that we have started working on a generalized state channels implementation with a focus on privacy, speed, trust minimization, security, and modularity. We think this is one of the most important layers of infrastructure that needs to be built today.

这就是为什么我们很高兴与大家分享，我们已经开始致力于开发专注于隐私，速度，信任最小化，安全性和模块化的广义状态通道。我们认为这是当今需要建设的最重要的基础设施之一。

We will not be doing an ICO, token sale, or other kind of fundraising event involving a token. As has been pointed out by Fred Ehrsam, Elad Gil, Vitalik Buterin, and many others, the economic incentives for core protocol innovation and second-layer infrastructure are much too low, and so the token model of funding a project in these domains has unfortunately become overused. Instead, we will initially be funded by a donation from Vitalik Buterin.

我们不会做ICO，代币销售或其他类型的涉及代币的筹款活动。正如Fred Ehrsam，Elad Gil，Vitalik Buterin等人所指出的，核心协议的创新和第二层基础设施的经济激励太低，所以在这些领域为项目提供资金的代币模型是被过度使用。相反，我们最初就获得Vitalik Buterin的资金捐助。

In our view, state channels are the basic foundation for usability in distributed applications. They reduce latency from the unacceptably high levels of today’s blockchain applications to the weblike response times that users expect.

我们认为，状态通道是分布式应用可用性的基础。他们将当前区块链应用程序的不可接受的延迟减少到用户期望的网络响应时间。

Even with other scalability methods like sharding, many applications that rely on large numbers of individual operations (such as streaming payments, IoT devices, games, etc) cannot hope to achieve the cost reductions they require without the added savings that state channels are able to introduce.

在不利用状态通道引入的成本节约的情况下，即使使用其他可扩展性方法（如分片），依赖大量独立的操作（如流式支付，物联网设备，游戏等）的应用程序也无法实现所需的成本降低。

Rather than receiving the benefit of these savings across a wide number of different applications, today’s blockchain application users will be lucky to find a one-off single-purpose state channel design that runs on its own network, isolated from other applications.

当今的区块链应用程序用户可以很幸运地找到一种一次性的单一用途的状态通道设计，它可以在自己的网络上运行，与其他应用程序隔离开来，而不是在许多不同的应用程序中获得这些节省的好处。

These different applications may use the same types of assets, yet deploy separate and highly bespoke contracts that cannot interoperate. They must be audited for security concerns on an individual and ongoing basis; significantly increasing costs. They are rarely optimized to the theoretical limits, often consuming orders of magnitude more gas than is necessary, and frequently going to chain when doing so is not even strictly required.

这些不同的应用程序可能使用相同类型的资产，但部署独立且高度定制的不能互相操作的合同。他们必须对每一个安全问题进行持续的审计。大大增加成本。它们很少被优化到理论极限，往往比所需要的要多消耗数量级的燃料，并且在这样做的时候甚至经常在链上进行操作，即使不是必要需求的。

The state of the art advances slowly, and developers are often left struggling to solve the same problems over and over, where one mistake threatens the entire security model of the application. Even when secure, these custom implementations have significant privacy drawbacks; leaking detailed information about the network graph, participant assets and activity.

现有技术发展缓慢，开发人员往往一直在努力解决同样的问题，一个错误威胁到应用程序的整个安全模型。即使在安全的情况下，这些自定义实现也存在重大隐私缺陷；泄漏有关网络图，参与者资产和活动的详细信息。

We envision a different future.
- We want to see clearly designed general purpose state channels that do not reduce, and in fact in many cases greatly increase, privacy.
- We don’t want to put anything on the chain that doesn’t need to be.
- We want channels that can be easily incorporated into new applications without the requirement for those developers to also be state channel experts.
- We want to achieve a level of privacy where state channel operations are indistinguishable from other common types of on-chain activities.
- We want to see support for multiple parallel operations inside of a single channel that do not interfere with each other.
- We want to provide expertly optimized, formally verified, and highly audited components that developers of decentralized applications can rely on without repeatedly re-inventing the wheel.
- We want to support deploying or upgrading channel designs without requiring the user to make a single on-chain operation.
- And we want to establish clear standards for how all of these generalized state channels will fit together into a global, multi-blockchain network where any user can easily connect to any other.

我们设想一个不同的未来。
- 我们希望看到明确设计的通用目的状态通道不会降低，实际上在很多情况下会大大增加隐私。
- 我们不想把任何东西放在不需要的链上。
- 我们希望通道可以很容易地纳入到新的应用程序，而不需要这些开发者也成为状态通道的专家。
- 我们希望达到一定的隐私水平，在这种情况下，状态通道操作与其他常见类型的链上活动没有区别。
- 我们希望看到在单个通道内不会相互干扰的多个并行操作的支持。
- 我们希望提供经过专业优化，经过正式验证且经过高度审计的组件，去中心化应用程序的开发人员可以依靠这些组件，而无需重复发明轮子。
- 我们希望支持部署或升级通道设计，而不需要用户进行一个的链上操作。
- 我们希望就所有广义状态通道如何融入一个全球性，多区块链的网络建立明确的标准，在这个网络中，任何用户都可以轻松地连接到任何其他的网络。

Together, we are working towards building this future.
We will be making further announcements around our plans for this project soon. For now, we are entirely focused on building a working prototype using our approach and speaking to developers and founders of decentralized application projects. We intend on building the best possible interface for decentralized application developers to work with so they can deliver the web-like experience their users expect without compromising on any component of the decentralized internet.

我们一起努力建设这个未来。
我们将很快就我们的计划进一步公布我们的计划。就目前而言，我们完全专注于使用我们的方法构建原型，并和去中心化应用项目的开发人员和创始人交流。我们打算为去中心化应用程序开发人员构建最好的接口，以便他们能够交付用户所期望的类似网络的体验，而不会影响去中心化互联网的任何组件。

----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

抖抖，在读博士，专注区块链技术研究与行业分析，jonas.meng.jm@gmail.com

本文由币乎社区（bihu.com）内容支持计划赞助。

版权所有，转载需完整注明以上内容。

----------------------------------------------------
