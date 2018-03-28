Understanding Hyperledger In a Bit More Detail　详细理解超级账本项目
====

对超级账本项目进行了一下稍微详细的介绍，帮助厘清一些概念。

> 本文翻译自: https://decentralize.today/understanding-hyperledger-in-a-bit-more-detail-3d40a37c74f2
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [荆凯](https://github.com/shuke0327)
> 本文由币乎社区（http://www.bihu.com）内容支持计划奖励。特此致谢
> 翻译时间：2018-01-07
---------------------------

![1.png](http://upload-images.jianshu.io/upload_images/1084915-2185db1eaf64ad6a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

I had the opportunity to explorer the Hyperledger project in more detail and my first impression was:

我有机会详细地了解了超级账本项目(Hyperledger)，我的第一印象是:

> *"It is an inter web mess of “stuff” that takes a bit of time to understand. "*
> *"这是一堆乱七八糟的东西，需要一点时间才能理解。"*

It took me a few days to slowly build a picture of what Hyperledger is and my second impression is:

我花了几天时间慢慢建立了对Hyperledger是什么的图景，我的第二个印象是:

> *“It’s actually pretty neat once you breakdown the various components and there is a lot of potential.”*
> *“一旦你对各种各样的组件进行分解，它实际上非常简洁，而且有很大的潜力。”*

The biggest challenge at the beginning was understanding all the terminology involved. Fabric, Sawtooth, Iroha, Composer, Indy etc, then figuring out how they fit together. Hint: They don’t. The next step involved taking 1 technology and peeling back the layers and understanding the architecture and concepts. If you have a current understanding of blockchains or even bitcoins it helps a lot because you can draw parallels.

开始时最大的挑战是理解所涉及到的所有术语。Fabric, Sawtooth, Iroha, Composer, Indy等等，然后弄清楚它们是如何组合在一起的。提示:他们没有。下一步涉及到使用技术，把各个层次剥离，理解架构和概念。如果你现在对区块链甚至是比特币有了一些了解，这将会有很大帮助，因为你可以进行比拟。

#### So what is Hyperledger?　什么是超级账本?

Some define Hyperledger by defining what it is not. This is helpful. It is not a company, not a cryptocurrency and not a blockchain. The definition that made sense straight away to me was:

有些人通过定义超级账本不是什么来得到它的定义。这挺有用。它不是一家公司，不是一种加密货币，也不是区块链。对我来说有意义的定义是:

> *“Hyperledger is an umbrella project of open source blockchains and related tools”*
> *“Hyperledger 是一个包含了开源区块链和相关工具的伞型项目”*

From here, let’s look at the components and rename them slightly.
从这里开始，让我们了解一下组件并对它们稍微做下重命名。

#### Platform　平台

*   Fabric: Let’s call this IBM Fabric because this is IBM’s blockchain design and architecture.
*   Sawtooth: This should be called Intel Sawtooth Lake. Intel’s flavoured blockchain.
*   Iroha: This one, Soramitsu Iroha. Soramitsu flavoured blockchain.


*   Fabric: 我们把它叫做 IBM Fabric 因为这是IBM的区块链设计和架构。
*   Sawtooth: 应该叫做 Intel Sawtooth Lake. Intel 特色的 blockchain.
*   Iroha: 这个应该叫做 Soramitsu Iroha. Soramitsu特色的blockchain.

All these blockchain platforms are independent of each other and generally focus on different areas. Broadly speaking, IBM Fabric is a multi-purpose pluggable framework, Intel Sawtooth for IOT and Iroha for mobile. Corda (another blockchain platform from R3) is looking to contribute their flavour as well to the Hyperledger umbrella and their area, finance.

所有这些区块链平台都是相互独立的，并且通常侧重于不同的领域。广义上讲，IBM Fabric是一个多用途的可插拔框架，Intel Sawtooth针对IOT，Iroha则针对移动设备。Corda(另一个来自R3的区块链平台)也希望能贡献它们的特性，既为了超级账本的伞型项目，也为了它们的领域，即金融领域。

#### Tooling (at a high level)　工具(从一个高的层次看)

*   Hyperledger Cello: Deployment tooling
*   Hyperledger Composer: Package management tooling
*   Hyperledger Explorer: Analytics tooling
*   Hyperledger Indy: Supporting independent identity

*   Hyperledger Cello: 部署工具
*   Hyperledger Composer: 包管理工具
*   Hyperledger Explorer: 分析工具
*   Hyperledger Indy:支持独立的身份识别

Let’s take a look at one particular blockchain and explore the architecture in more detail.

让我们来看看一个特定的区块链，并更详细地探索它的架构。

#### Fabric

Although a little dated (Nov 16), this presentation by Arnaud Le Hors whose a Senior Technical Staff Member on IBM’s blockchain team explains Fabric really well. I recommend watching the video within.

虽然有点过时(11月16日)，但是Arnaud Le Hors, IBM区块链团队的Senior Technical Staff 成员, 在他的演示中很好地解释了Fabric。我建议你在这里看下视频。

[https://www.altoros.com/blog/hyperledger-approaches-version-1-0-with-better-scalability-and-security/](https://www.altoros.com/blog/hyperledger-approaches-version-1-0-with-better-scalability-and-security/)

#### Fabric whitepaper mystery　Fabric白皮书的神秘

For the true enthusiasts, the Hyperledger whitepaper is a must read. Warning, although it is informative, it can add to the confusion if you are not clear on terminology. The whitepaper talks in terms of Hyperledger but then refers to Chaincode (the smart contract aspect of Fabric) and Docker which is how one can run Fabric.

对于真正的狂热者来说，Hyperledger白皮书是必须阅读的。警告，虽然它能提供丰富信息，但如果你不清楚术语的话，它反而会增加混乱。白皮书中说的是超级账本，但之后提到了Chaincode(Fabric的智能合约部分)和Docker, 后者是说人们如何能够运行Fabric。

Attempts to get an updated whitepaper led me to the Hyperledger [whitepaper working group](https://wiki.hyperledger.org/groups/whitepaper/whitepaper-wg) which has been inactive for over a year. I have a feeling it has probably moved elsewhere. There is a link to a 2.0 whitepaper though that has feedback comments from as early as 6 months ago so maybe this working group is still relevant? Who knows.

为了得到最新的白皮书，我去找Hyperledger[白皮书工作组](https://wiki.hyperledger.org/groups/whitepaper/whitepaper-wg), 这有一年多一直没有活跃了。我觉得它可能已经转移到别的地方了。有一个2.0的白皮书的链接，上面的反馈评价最早是6个月前的, 可能这个工作组仍然存在关联?　谁知道呢。

#### Key concept of Fabric　Fabric的核心概念

Fabric has been engineered and architected with practical real world use cases in mind. In whatever business application whether it be supply chain, asset management & tracking or smart contracts there are several important requirements. They include:

在Fabric的设计和架构中，已经把真实世界的实践用例考虑到了。无论在何种商业应用中，无论是供应链、资产管理和跟踪还是智能合约都有几个重要的要求。它们包括:

*   identity and auditability
*   private transactions
*   confidential contracts
*   modular consensus
*   performance
*   scalability
*   chaincode/smart contracts


* 身份识别和可审计性
* 私有交易
* 保密合约
* 模块化共识
* 性能
* 可扩展性
*  chaincode /智能合约

Fabric has, is working on or improving on these concepts.
Fabric已经或者正在研究、改进这些概念。

#### Design philosophy　设计理念

One of the design philosophies of Fabric is for a modular & extensible approach with interoperability. An example is a pluggable consensus algorithm. Think of Wordpress and the plugin ecosystem or Atlassian with all their 3rd party plugins. Corda also has a similar approach. This is good because it provides the most flexibility where different components can be used based on the requirements.

Fabric的设计理念之一是使用可互操作的模块化和可扩展的方法。一个例子是可插拔的共识算法。想想Wordpress和插件生态系统，或者Atlassian的所有第三方插件。Corda也有类似的方式。这很好，因为它提供了最大的灵活性，可以根据需求使用不同的组件。

#### Reference Architecture　参考架构

![2.png](http://upload-images.jianshu.io/upload_images/1084915-1e1fe50e67c4c6f8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Something that is mentioned a lot is the reference architecture. The [whitepaper](http://www.thedata.co/sites/thedata.co/files/u1/Hyperledger%20Whitepaper.pdf) does a good job of explaining each part in detail.

我们经常提到的是参考架构。[白皮书](http://www.thedata.co/sites/thedata.co/files/u1/Hyperledger%20Whitepaper.pdf)很好地解释每个部分的细节。

Another popular image that shows the Fabric architecture is as follows:
另一个显示Fabric结构的流行图片如下:

![3.png](http://upload-images.jianshu.io/upload_images/1084915-e829f9d3dd4fde0e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


What is interesting here is that there are different types of peers. In the Bitcoin blockchain, there are 2 types of nodes. Mining codes and validating nodes. ie not every node in the network is a mining node. In Fabric, there are also different types of nodes. Endorser nodes, Orderer and Committers.

有趣的是，有不同类型的peers节点。在比特币区块链中，有两种类型的节点。挖矿节点和验证节点。并非网络中的每个节点都是一个挖矿节点。在Fabric中，也有不同类型的节点。见证人节点、排序节点和提交节点。

#### Where’s the token? 通证在哪里?

The one glaring omission (by design though) from this architecture is the token. The cryptocurrency or as some say the lubricant or oil that makes the blockchain work.

这个架构中的一个明显的遗漏(虽然是根据设计而来)是通证。加密货币或者像某些人说的润滑剂或润滑油，能够使区块链运转。

In a public open blockchain where participants are free to join, incentivising participants to do the right thing and penalising them for bad or undesirable behaviour is very important. In a private and permissioned blockchain, of which Fabric and the others are, this is not so much of a concern because the penalty from a bad participant would potentially be the lost of business.

在公有的开放式区块链中，参与者可以自由加入，激励参与者做正确的事情，并惩罚他们的不良行为或恶意行为，是非常重要的。在一个私有和存在许可的区块链中，如Fabric和其它的一些项目，这不是那么重要，因为对一个恶意参与者的处罚可能是使其失去业务。

Having said this, it would be very interesting to see what the effects are if a token is introduced into the tool kit.

说到这里，想想看如果把一种通证被引入到工具包中会带来什么效果，也会很有趣。

#### What next?　接下来呢?

With this new found knowledge, the next step is to give it a try. There are some detailed docs at [https://hyperledger-fabric.readthedocs.io/en/release/](https://hyperledger-fabric.readthedocs.io/en/release/) There’s a lot to go through. Take your time and go through it step by step.

有了新发现的知识，下一步就是进行一下尝试。有一些详细的文档在[https://hyperledger-fabric.readthedocs.io/en/release/](https://hyperledger-fabric.readthedocs.io/en/release/)。有很多。慢慢来，一步一步来。

#### Summary 总结

Hyperledger is a collection of open source blockchains and toolsets driven and backed by various companies and they all have their unique angle. They are all private and permissioned based blockchains and targeted towards business use case. Fabric for instance has a modular design and targeted towards most general applications such as supply chain and asset management. Fabric has centered its design around core features important in any business network, namely identity, privacy, confidentiality, performance and scalability. Modularity provides flexibility and smart contracts allow for “self” execution of business rules.

Hyperledger是一个由各种各样的公司驱动和支持的开源区块链和工具的集合，它们都有自己独特的角度。它们都是基于私有和存在许可的区块链，并针对业务用例来设计。例如，Fabric具有模块化设计，针对的是大多数通用的应用程序，如供应链和资产管理。Fabric围绕在任何业务网络中都很重要的核心特征进行设计，即身份识别、私有性、机密性、性能和可扩展性。模块化提供了灵活性，而智能合约则允许业务规则的“自我”执行。

Ref:

*   [https://blockgeeks.com/guides/what-is-hyperledger/](https://blockgeeks.com/guides/what-is-hyperledger/)
*   [A gentle introduction to The Hyperledger Project](https://bitsonblocks.net/2016/12/09/a-gentle-introduction-to-the-hyperledger-project/)
*   [https://www.ibm.com/developerworks/cloud/library/cl-top-technical-advantages-of-hyperledger-fabric-for-blockchain-networks/index.html](https://www.ibm.com/developerworks/cloud/library/cl-top-technical-advantages-of-hyperledger-fabric-for-blockchain-networks/index.html)
*   [https://medium.com/@philippsandner/comparison-of-ethereum-hyperledger-fabric-and-corda-21c1bb9442f6](https://medium.com/@philippsandner/comparison-of-ethereum-hyperledger-fabric-and-corda-21c1bb9442f6)

--------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

荆凯(shuke0327) 区块链技术爱好者，程序员，坚信区块链将会改变潮水的方向，欢迎关注我的公众号: 增长之道

本文由币乎社区（bihu.com）内容支持计划奖励。

版权所有，转载需完整注明以上内容。

----------------------------------------------------