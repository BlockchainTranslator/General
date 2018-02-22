# Ethereum Casper 101 | 初识以太坊 Casper

> 本文翻译自：https://medium.com/@jonchoi/ethereum-casper-101-7a851a4f1eb0
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS)  [oscnet](https://github.com/oscnet) [胖哥@胖哥说币](https://github.com/RickyShiJs)
>
> 翻译时间：2017-11-02

Casper will implement proof of stake in Ethereum. We begin with a review on why proof of stake matters and continue with its strengths & weaknesses. This post aims to provide a broad overview of Casper and clarify some of the confusion with respect to the two protocol design efforts related to Casper. The two proposed implementations share the same core design principle: **applying cryptoeconomic mechanism design to secure the network while managing challenges regarding liveness, safety and synchrony assumptions**. This post is also an overview of the progress so far and the challenges that lie ahead. Most importantly for fellow newcomers, the post identifies & defines key concepts and ties together various helpful resources under one context. The overarching intention is to make Casper and proof of stake more approachable to everyone in the community.

Casper 将在以太上坊上实现 POS (权益证明) 协议。这篇文章首先回顾了 POS 的重要性及其存在的优缺点，并且对 Casper 进行了广泛的概述，澄清了与 Casper 相关的两个协议设计上的一些混淆问题。这两种提议在实现上使用了相同的核心设计原则:**应用数字货币经济机制设计来保护网络，同时处理关于活跃度，安全性和同步假设上的挑战**。这篇文章还概述了迄今取得的进展和未来的挑战。最重要的是，对于初学者，本文将各种有用的资源结合在一起，对关键概念进行了说明和定义。

Enjoy and please don’t hesitate to reach out with questions, corrections or feedback

文中如有不当之处，请随时向我联系提出问题、更正或反馈。
([email](hello@jonchoi.com), [twitter](https://twitter.com/jon_choi_/)).

![](https://cdn-images-1.medium.com/max/2000/1*M7f5y6HY3Y9HRcFGplaFuQ.jpeg)

## Outline | 大纲

1. Introduction 介绍

2. Proof of Stake 权益证明

3. A Tale of Two Caspers 两个 Caspers 的故事

4. Why Casper Matters 为什么 Casper 重要

5. Design Principles 设计原则

6. Challenges 挑战

7. Future Work 未来的工作

8. Glossary 词汇表

9. Conclusion 结论


## Introduction | 介绍

Casper is hardly a new project as it dates back to 2014, so fortunately it has a lot of related information online. However, despite the wealth of information out there, there’s no easy jumping-off point for a beginner to ramp up and start engaging with the project. That’s why I’m writing this post.

While other posts, videos and papers focus on the specification, implementation and verification of Casper. This post focuses on the various guiding design principles of Casper, how it differs from competing approaches, why you should care about it, and how you can contribute to this project.

Casper 最早从2014年出现，并不能算是一个新的项目，所以幸运的在网上能找到很多有关于它的文章。虽然有关的信息非常多，但初学者还是没有一个足够简明的学习起点来参与到这个项目中。这就是我为什么写这篇文章的原因。

不同于其它的文章、视频和论文主要集中讨论有关 Casper 的规范、实施和验证。这篇文章着重介绍 Casper 的各种指导性设计原则；它与其它竞争替代方案的差异；以及为什么我们要关注它；如何为这个项目做出贡献等内容。

In addition, Casper has maintained an exceptionally open and collaborative culture among Ethereum researchers, developers and community members. I hope this post can continue that tradition by introducing you to Casper and convincing you why it’s important to Ethereum as well as the larger public blockchain ecosystem.

此外，Casper 的保持着了非常开放和相互协作的文化，它由以太坊研究人员，开发人员和社区成员共同维护。我希望这篇文章可以继续保持这个传统，向你介绍 Casper， 并试图阐述 Casper 对于以太坊以及更大的公链生态系统的重要性。


To summarize, this post is:

* A quick and broad introduction to PoS and Casper.

* Discussion on why Casper matters, its design principles and its challenges.

* A list of key resources and terms to get you started with PoS and Casper.

总而言之，这篇文章是：

* 对 PoS 和 Casper 的快速和广泛的介绍。

* 讨论为什么 Casper 重要，其设计原则及其面对的挑战。

* 能让你开始学习使用 PoS 和 Casper 的一系列关键资源和术语的列表。


This is not:

* A full history of Casper.

* Specification of Casper.

* Implementation details of Casper.

* Formal verification of Casper.

而不是：

* Casper 的完整历史。

* Casper 规范。

* Casper 的实现细节。

* Casper 形式化验证。

*If this is review for you, a list of resources are linked throughout the post.*

With that, I hope you enjoy this beginner-friendly introduction to Casper: Ethereum’s proof of stake research and implementation.

*注意：文章中随处可见相关资源列表的链接。*

通过这个，我希望你喜欢这个适合初学者的 Casper 的介绍：以太坊 POS （权益证明）的研究和实现。

## Proof of Stake | 权益证明

*(If you’re already familiar, please feel free to skip ahead to the next section: “What is Casper?”)*

*（如果您已经对 PoS 了如指掌，请阅读下一节：“Casper 是什么？”）*


Proof of Stake (PoS) is a category of consensus algorithms for public blockchains that depend on a validator’s economic stake in the network.

In proof of work (PoW) based public blockchains (e.g. Bitcoin and the current implementation of Ethereum), the algorithm rewards participants who solve cryptographic puzzles in order to validate transactions and create new blocks (i.e. mining). In PoS-based public blockchains (e.g. Ethereum’s upcoming Casper implementation), a set of validators take turns proposing and voting on the next block, and the weight of each validator’s vote depends on the size of its deposit (i.e. stake). Validators are rewarded for their service to the network, but the stake also acts as an economic disincentive for bad actors.

Significant advantages of PoS include **security, reduced risk of centralization, and energy efficiency**.

权益证明（PoS）是公链的一种共识算法，其实现依赖于验证人在网络中的经济利益。

在基于工作量证明（PoW）的公链（如比特币和当前实施的以太坊）中，通过对**解加密算数题**的参与者进行奖励，来验证交易并创建新的块（即采矿）。而在基于 PoS 共识的公共块（如以太坊即将推出的 Casper ）中，验证人轮流提议新块并对下一个块投票，每个验证人的投票权重取决于其持币量的大小（即股权）。验证人对于区块链网络提供服务是有奖励的，而且这种奖励也实现了对攻击者的的经济制约。

PoS 的明确优点包括安全性、降低集权风险和提高能源效率。

### Explicit Economic Security | 明确的经济安全

In PoW, your downside is capped at how much energy cost and hardware depreciation you incur and therefore has an implicit cost that adjusts dynamically (via 10 min block time target). While PoS has its own challenges (discussed later in the post), one of its major strengths is the flexibility to explicitly design the penalties of Byzantine behavior (i.e. not following the protocol). This gives the protocol designer increased control over dialing in the “shape” of the asymmetric risk & reward profile of various actions within the network. One proxy for security is the cost of doing damage to the utility and correctness of the network, and therefore the ability to have explicit penalties (perhaps at levels that are more draconian than PoW) can increase the security of the network (i.e. economic security).

PoW 工作量证明受到你能承受多少电力成本和硬件折旧的限制，所以具有一个动态调整（通过10分钟出块的目标）的隐性成本。虽然 PoS 有自己的挑战（在后面有讨论），其主要优点之一是可以灵活地明确地设计对拜占庭行为（即不遵循协议）进行的惩罚。
这使得协议设计者能够对网络中各种行为的不对称风险和收益回报情况进行更多的控制。
安全性的另一个方面是对软件和网络精密性进行破坏的成本，因此具有明确惩罚（可能在比PoW 更严重的级别上）的能力可以增加网络的安全性（意即经济安全）。

On a related note, Vitalik further argues that PoS has better recovery properties. In PoW, there’s an issue of [“spawn camp” attacks](https://twitter.com/VitalikButerin/status/827783678910558208) that can render a blockchain unusable. In PoS, the network can delete the attacker’s stake and prevent repeated attacks. The economic analysis further clarifies this concept. The marginal cost of repeated attack is the same as the first round in PoS. Whereas in PoW, the main marginal cost for another round during a 51% attack is the power cost (the incremental hardware depreciation & physical space cost is minimal for repeated attacks). To drive the point home, let’s paraphrase [Vlad Zamfir](https://medium.com/@Vlad_Zamfir), the cost profile of a repeated 51% attack in PoS is as if “your ASIC farm burned down” with each additional round.

相关说明，Vitalik 进一步认为，PoS 具有更好的恢复属性。在 PoW 中，存在一个可以使块链不可用的[“51%算力攻击](https://twitter.com/VitalikButerin/status/827783678910558208)问题。在 PoS 中，网络可以处罚没收攻击者的股权，防止重放攻击。经济分析进一步澄清了这一概念。重放攻击的边际成本与 PoS 的第一轮相同。而在 PoW 中，51％ 攻击期间另一轮的主要边际成本是电力成本（重放攻击引起的的硬件折旧和物理空间成本增加很小）。简明如 [Vlad Zamfir](https://medium.com/@Vlad_Zamfir)所说，在 PoS 中重复的 51％ 的攻击成本就好像每一轮都要“你的 ASIC 矿场烧毁”一样。


### Mitigation of Centralization | 减少集中化


Proof of Stake mitigates the impact of [economies of scale](https://en.wikipedia.org/wiki/Economies_of_scale) in making consensus. In proof of work, we can already see that the network trusts a relatively concentrated set of mining pools (e.g. AntPool) to secure the network. Larger proof of work mining pools can lower the unit cost of their technical and operational infrastructure (datacenter costs, power costs, personnel) by both (1) amortizing a fixed cost over a larger operation and (2) having bargaining power by operating as a larger entity.

为了达成共识，PoS 权益证明减轻了[规模经济](https://en.wikipedia.org/wiki/Economies_of_scale)的影响。在 PoW 工作量证明中，我们已经看到，为保护网络安全，相对集中的矿池（例如 AntPool）比规模小的更受到信任。大矿池可以通过（1）在较大的运营中摊销固定成本，（2）通过运营较大的实体来提高议价能力，来降低其技术和运营基础设施（如数据中心成本，电力成本，人员成本）的单位成本。

This means that two sets of mining pools with equal economic cost, one may be able to achieve a higher hash rate and have more influence in the network, dollar for dollar. For example, 10,000 miners that each spend $1/min ($87.6M/yr) may have less hashing power than one mining pool that spends $10,000/min (despite also spending $87.6M/yr). (Further work: quantifying the benefits to centralization in PoW mining would be fascinating. i.e. is it 1bps, 1% or multiples in hashing power per dollar invested?)

这意味着两个成本相同的矿池，取得的算力会不一样，一个能实现更高的算力，并在网络上有更大的影响，即钱能生钱，例如，10,000名矿工单独挖矿，每个矿工花费1美元/分钟（8,860万美元/年）的成本，比一个同样花费10,000美元/分钟(尽管也花费了8760万美元/年）的矿池的算力要低得多。(进一步：量化 PoW 挖矿中心化的好处将是令人着迷的，即它是1bps ，1％ 还是算力以投资每美元比率的倍数？）

However, in proof of stake, a dollar is a dollar. The benefit here is that you can’t pool together to mae a dollar worth more. Nor can you develop or buy application-specific integrated circuits (ASICs) to have an advantage technologically. So, PoS intends to mitigate the regressive distribution of PoW mining rewards and move directionally towards proportional distribution. (Going beyond proportional to progressive distribution will require mature decentralized reputation/identity management services).

然而，在 POS 权益证明的情况下，一美元就是一美元。这样的好处是，你不能通过汇集在一起，使得一美元值得更多。您也不能开发或购买专用集成电路（ASIC），从而在技术上占有优势。所以，PoS 不同于 PoW 挖矿收入的累计分配方式，采用了比例分配。（成熟的去中心化的声誉/身份管理服务为按比例分配收益成为可能）。

### Energy Efficiency | 能源效率

Proof of work relies on wasting resources to secure the network. Bitcoin currently uses [over 20 TWh per year of power](https://digiconomist.net/bitcoin-energy-consumption), which is close to the power consumption by the entire country of Ecuador. In order for Bitcoin to have broader adoption and operate at Visa’s scale, it would have to waste as much power as a much larger country. Extrapolating it’s current pace, one can see why proof of work may not be a sustainable path forward.

PoW 工作量证明机制通过浪费资源来保障网络。比特币目前每年使用[超过20 TWh的电力](https://digiconomist.net/bitcoin-energy-consumption)，这已经接近厄瓜多尔整个国家的电力消耗。为了使比特币在支付的规模上得到更广泛的使用，它必须浪费象更大的国家一样多的电力。根据这样的发展，我们就可以明白，工作量证明可能不是合适的发展方向。

While Bitcoin may serve an important social function that may indeed exceed its financial costs and environmental externalities (i.e. [Nick Szabo’s social scalability argument](http://unenumerated.blogspot.com/2017/02/money-blockchains-and-social-scalability.html)), proponents of PoS believe it is possible to replicate the incentive mechanisms of a PoW blockchain without wasting as much energy (by orders of magnitude). Alternatively, some may argue there exists a price of negative externalities where even the benefits of social scalability might be outweighed by the environmental costs.

虽然比特币可能具有超过其财务成本和外部环境的重要社会功能（即[Nick Szabo的社会可扩展性论证](http://unenumerated.blogspot.com/2017/02/money-blockchains-and-social-scalability.html)），但 PoS 的支持者认为借鉴 PoW 块链的激励机制，而不用浪费太多的能量是可能的。或者，有些人可能认为存在负面外部性的代价，即社会可扩展性的好处甚至可能超过环境成本。

While the exact answer is hard to ascertain a priori, I believe the crypto ecosystem as a whole has the responsibility to explore all promising consensus mechanisms to weigh their pros/cons and feasibility. (For example, it’s great that other projects are testing the benefits and feasibility of various forms of proof of storage, among others.)

虽然确切的答案很难得到确定，但我认为整个数字加密生态系统有责任探索所有有希望的共识机制，衡量其利弊和可行性。（例如，其他项目正在测试各种形式的存储证明的好处和可行性等等）。

Taking a step back, it’s also worth noting the two kinds of costs to PoW issuance. There are internalized costs, which are paid by miners and passed on to currency holders. Then there are externalized costs, such as the environmental costs and subsidies from governments (most likely in the form of cheaper electricity). In PoS, there are low consensus costs (no power & hardware costs), which allows for low issuance. As the network matures, it may even allow for negative issuance (net of burned tx fees as well as any penalties and slashing), which can have a price-stabilizing effect.

退一步讲，值得注意的是 PoW 的发行存在两种成本。内部成本，由矿工支付，并转交给货币持有人。外部成本，比如政府的环境成本和补贴（很可能以更便宜的电力）。在 PoS 中，共识成本较低（无电力和硬件成本），从而允许低发行量。随着网络的成熟，甚至可能会出现负发行（网络交易燃烧的，以及罚款和销毁的），并形成稳定的价格。

Therefore, not only is lower energy consumption better for the environment but it also enables simpler mechanism design. That is because lower energy consumption allows for substituting **realized costs** (power and depreciation costs are nonreversible) with **potential economic value-at-loss** (i.e. believable risk of unrealized costs) in order to secure the network. This is a key underlying hypothesis of PoS: **both realized costs and prospect of losing money can incentivize participants to secure the network**. Therefore–while difficult–it is possible (and thus preferable) to secure public blockchains via loss aversion, which can decrease the [public costs](https://en.wikipedia.org/wiki/Externality#External_costs) and [deadweight losses](https://en.wikipedia.org/wiki/Deadweight_loss) in a system.

因此，不仅能降低环境的能耗，而且还能实现更简单的结构设计。这是因为较低的能源消耗允许将潜在的经济价值损失（即可信赖的未实现成本的风险）代替实际成本（电力和折旧成本是不可逆的），以确保网络的安全。这是 PoS 的一个关键的基本假设：实际成本和对亏损的预期可以激励参与者保护网络。因此，虽然困难 - 但是有可能（因此更好）通过避免损失来确保公链安全，这可以减少系统中的[公共成本](https://en.wikipedia.org/wiki/Externality#External_costs)和[无谓损失](https://en.wikipedia.org/wiki/Deadweight_loss)。


### Proof of Stake: Summary | PoS 总结

That sums up the main benefits of PoS. While Casper provides specific benefits to Ethereum (discussed below), a significant portion of its importance are the general benefits of PoS: **explicit economic security, mitigation of centralization and energy efficiency**.

So, now that we’ve discussed PoS, let’s dive into Casper.

这里总结了 PoS 的主要优点。虽然 Casper 为以太坊（以下讨论）提供了具体的好处，但其重要性的很大一部分是 PoS 带来的好处：**明确的经济安全，减少集权和能源效率**。

所以，现在通过 PoS，让我们来看看 Casper。

### Further Reading on PoS | 进一步阅读 PoS

* [Proof of Stake FAQ 权益证明常见问题](https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQ) in Ethereum wiki

* [Proof of Stake Design 权益证明设计哲学 Philsophy](https://medium.com/@VitalikButerin/a-proof-of-stake-design-philosophy-506585978d51) by [Vitalik Buterin](https://medium.com/@VitalikButerin)

* [Critique of PoS Pos的批判](https://medium.com/@tuurdemeester/critique-of-buterins-a-proof-of-stake-design-philosophy-49fc9ebb36c6) by
[Tuur Demeester](https://medium.com/@tuurdemeester) (and comments
[1](https://medium.com/@VitalikButerin/this-statement-is-misleading-because-he-is-really-only-talking-about-what-a-51-attacker-could-65cd02a2389e),
[2](https://medium.com/@tuurdemeester/re-buterins-criticism-of-my-pos-piece-4ee70d6fd289),
[3](https://medium.com/@VitalikButerin/theres-a-long-history-of-nationalization-to-prove-that-after-governments-imo-the-most-likely-39c39c82b66))

* [Tendermint Whitepaper Tendermint白皮书](https://tendermint.com/static/docs/tendermint.pdf) by [Jae Kwon](https://medium.com/@jaekwon)

* [Cryptocurrencies without Proof of Work 非工作证明的加密货币](https://arxiv.org/pdf/1406.5694.pdf) by Iddo Bentov et al. ([Slides](http://www.cs.cornell.edu/~iddo/CoAslides.pdf))

* [Bitcoin Wiki on Proof of Stake  PoS 在比特币维基上的介绍 ](https://en.bitcoin.it/wiki/Proof_of_Stake)

* Select examples 选择的示例: [Tendermint](https://tendermint.com/), [Polkadot](https://polkadot.io/), [Peercoin](https://peercoin.net/).

## A Tale of Two Caspers | 两个Caspers的故事

In simple terms, Casper is Ethereum’s Proof of Stake work stream.

简单来说，Casper 是以太坊的 PoS 权益证明实现的工作流。

Casper is not a specific implementation but a family of two main projects under active research by the Ethereum team. Informally, there’s “Vitalik’s Casper” aka **Casper FFG ** and “Vlad’s Casper” aka **Casper CBC** (explained below). This subtlety isn’t clear until you start diving deep into Casper materials online, which can be very confusing to the “uninitiated.” (In fact, that is a main motivator for this post). While independent implementations, they have the same goal in mind: moving Ethereum over to proof of stake.

Casper 并不是一个具体的实现，它是实际上由以太坊团队正在积极研究的两个主要项目组成。非正式地，“Vitalik's Casper” 又称 **Casper FFG**，还有 “Vlad's Casper”，又名**Casper CBC**（见下文说明）。细节部分只有到你开始深入了解 Casper 的在线资料才能明白，外行可能对这个非常不解（事实上，这就是写这篇文章的主要动力）。虽然他们是独立的实现，但他们有着一样的目标：将以太坊的工作量证明转到 PoS 权益证明。

(Despite a surprisingly common impression that Ethereum is already implementing PoS, it is still a PoW chain (using [ethash](https://github.com/ethereum/wiki/wiki/Ethash)). While being [memory hard](https://www.vijaypradeep.com/blog/2017-04-28-ethereums-memory-hardness-explained/) and more ASIC-resistant than Bitcoin, Ethereum is a PoW chain nonetheless and has the same drawbacks with respect to energy efficiency.

So with that, let’s briefly discuss the two Caspers.

（尽管有一个令人惊讶的共同印象是，以太坊已经在实施 PoS ，但它仍然是一个 PoW 链（使用[ethash](https://www.vijaypradeep.com/blog/2017-04-28-ethereums-memory-hardness-explained/)挖矿算法），虽然比比特币更[内存相关](https://www.vijaypradeep.com/blog/2017-04-28-ethereums-memory-hardness-explained/)(挖矿的效率基本与CPU无关，却和内存大小和内存带宽正相关)，更耐 ASIC (即使用专门优化的芯片产生的挖矿优势尽可能的小)，但是它们是 PoW 链无疑，并且在能源效率上具有相同的缺点。

所以我们来简要的讨论这两个 Caspers。

### FFG vs CBC

Caveat: both of these projects will present more detailed papers and proof of concepts the weeks following Devcon3, but here’s a quick preview of their approaches.

注意事项：这两个项目将在 Devcon3 之后的几周内提供更详细的论文和概念证明，这里对其实现方法进行快速预览。

**Casper the Friendly Finality Gadget (“FFG”)** — aka “Vitalik’s Casper” — is a hybrid PoW/PoS consensus mechanism, which is the immediate candidate for Ethereum’s first bridge to proof of stake. More specifically, FFG implements a proof of stake mechanism as an overlay on top of a proof of work chain (such as Ethereum’s ethash PoW chain). Simply, the blockchain would grow every block with the familiar ethash PoW algorithm, but every 50 blocks is a PoS “checkpoint” where finality is assessed via a network of validators.

**友好的终结工具 Casper（“FFG”）**  - 又名“Vitalik's Casper” -  是一种混合 PoW / PoS 的共识机制，它是以太坊首个通向 PoS 权益证明的候选方法。更具体地说，FFG 在工作量证明（如以太的 ethash PoW 链）的基础上，实施了权益证明。简单地说，块链将用熟悉的 ethash PoW 算法增加区块，但是每50个块有一个 PoS “检查点”，通过网络验证人来评估区块的最终有效性。

**Casper the Friendly Ghost**: Construction by Correction (“**CBC**”) — aka “Vlad’s Casper”—differs in approach from traditional protocol design: (1) the protocol is partially specified in the beginning and (2) and the rest of the protocol is derived in way that is proven to satisfy the desired/requisite properties (typically protocol is fully defined then tested to satisfy the said properties). In this case, one way to derive the full protocol is to implement an estimate safety oracle (“[an ideal adversary](https://edcon.io/ppt/one/Vlad%20Zamfir_Casper_EDCON.pdf)”), which either raises exceptions of a fault of a justified estimate or enumerates the potential future faulty estimates. More specifically, Vlad’s work focuses on designing protocols where one can extend local views of a node’s estimate of safety to achieve consensus safety.

**鬼马小精灵 Casper（其名字源于上世纪90年代的一部电影《鬼马小精灵》）** ：使用正确的建设（“CBC”）  - 又称“Vlad's Casper” - 与传统协议设计的方式不同：（1）协议在开始阶段是部分确定的（2）其余部分协议以证明能够满足所需/必需属性的方式得到（通常协议被完全定义，然后被测试以满足所述属性）。在这种情况下，得出完整协议的一种方法是实现所预计的安全性 [(一个理想的对手)](https://edcon.io/ppt/one/Vlad%20Zamfir_Casper_EDCON.pdf) ，或者提出合理估计的错误的例外，或列举潜在的未来错误估计。更具体地说，Vlad 的工作侧重于设计协议，扩展单个节点对安全性估计的局限视角，以实现共识安全性。

Taking a step back, FFG focuses more on a multi-step transition to introducing PoS for the Ethereum network. This prepares for an iterative implementation that increases the role of PoS in the network over time. (PoS will claim a smaller portion of the rewards to start). In contrast, CBC focuses on formal methods that derive safety proofs “by construction” from first principles. Albeit confusing, the different approaches to solving this problem created two distinct work streams that complement each other well. The final form of Casper will likely draw from learnings from both FFG and CBC.

退后一步，FFG更侧重于通过多步骤过渡为以太网络引入 PoS。通过准备的迭代实现，增加 PoS 在网络中的作用。（PoS 将从较小部分的奖励开始）。相比之下，CBC 着重于通过第一个原则“通过建设”得出安全证明的正式方法。尽管令人困惑，解决这个问题的不同方法创造了两个不同的工程。Casper 的最终形式可能来自对 FFG 和 CBC 的互相学习。

### Next steps | 下一步

While substantial progress was achieved, many of the details — both at the higher mechanism design level and at the lower implementation level — remain to be finalized. This is openly acknowledged by both Vitalik and Vlad, and this can be an invitation for more of the community to engage to move the conversation forward.

In sum, both research projects are very active, and more updates should be available at Devcon3 in November. The role of this overview does not include going into more detail, but please feel free to dive into more implementation and design details in the links below (This doc will likely be updated or followed up once FFG and CBC papers are released).

虽然取得了实质性进展，但是在高层的机制设计层面和底层编程实现层面的许多细节仍有待确定。维塔利克和弗拉德都公开承认了这一点，并且邀请更多的社区参与推动和讨论。
总而言之，这两个研究项目都非常活跃，11月份 Devcon3 将有更多的更新。此概述的作用不包括更详细的内容，但请随时在以下链接中深入了解更多实施和设计细节（ FFG 和 CBC 论文发布后，本文档可能会更新或后续）。

### Links for FFG |  FFG的相关链接

* [Casper FFG Basics Paper Casper FFG基础教材](https://github.com/ethereum/research/blob/master/papers/casper-basics/casper_basics.pdf) by Vitalik Buterin and [Virgil Griffith](https://medium.com/@virgilgr) (Draft)

* [Casper Github Repo](https://github.com/ethereum/casper) (FFG)

* [Karl Floersch](https://medium.com/@karl_dot_tech)’s [FFG Implementation on pyethereum](https://github.com/karlfloersch/pyethereum/)


### Further Reading on FFG | 进一步阅读 FFG

* [Simple explanation on Reddit 在Reddit上的简单解释](https://www.reddit.com/r/ethereum/comments/6pmye8/incentives_in_casper_the_friendly_finality_gadget/dkqsgwp/) by Vitalik Buterin. August 2017.

* [Minimal Slashing Conditions 最小削减条件](https://medium.com/@VitalikButerin/minimal-slashing-conditions-20f0b500fc6c) by Vitalik Buterin. March 2017.

* [Safety Under Dynamic Validator Sets 动态验证组的安全性](https://medium.com/@VitalikButerin/safety-under-dynamic-validator-sets-ef0c3bbdf9f6) by Vitalik Buterin. March 2017.

* [Slasher](https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm/) by Vitalik Buterin. January 2014.

* [Weak Subjectivity](https://blog.ethereum.org/2014/11/25/proof-stake-learned-love-weak-subjectivity/) by Vitalik Buterin. November 2014.

* [On Settlement Finality](https://blog.ethereum.org/2016/05/09/on-settlement-finality/) by Vitalik Buterin. May 2016.

* [Triangle of Harm | 三角形的危害](http://vitalik.ca/general/2017/07/16/triangle_of_harm.html) by Vitalik Buterin. July 2017.

* [Casper Economic Incentives Overview | Casper经济激励概述](https://docs.google.com/presentation/d/1zK0T6dyChBknGULtdmDZQLwf23bxBfrNADEApuddtNE/edit) by Karl Floersch. Sept 2017.

* [Formal Methods on Another Casper | 另一个Casper的形式化方法](https://medium.com/@pirapira/formal-methods-on-another-casper-8a75f6e02073) by Yoichi Hirai.

* [Github. ethereum/casper](https://github.com/ethereum/casper).


### Links for CBC | CBC 的相关链接

* Will be updated after Devcon3 将在Devcon3之后更新

### Further Reading on CBC | 进一步阅读CBC

* [Casper CBC CESC deck](https://drive.google.com/open?id=0B5PcPC6ZC_GyaDBFcno3YXVNbnM) and [video](https://youtu.be/5ScY7ruD_eg) by Vlad Zamfir. September 2017.

* [Casper CBC EDCON deck](https://edcon.io/ppt/one/Vlad%20Zamfir_Casper_EDCON.pdf) by Vlad Zamfir. (Video [part 1](https://www.youtube.com/watch?v=6boQSQ7IuNY), [part 2](https://www.youtube.com/watch?v=6boQSQ7IuNY)) February 2017.

* [Devcon2 CBC Casper Deck](https://ethereumfoundation.org/devcon2/wp-content/uploads/2016/10/A-Correct-by-Construction-Asynchronous-Casper-Protocol.pdf) and [video](https://www.youtube.com/watch?v=4LhC-jDaI00) by Vlad Zamfir. October 2016.

* 2016.12.06 [History of Casper: Chapter 1](https://blog.ethereum.org/2016/12/06/history-casper-chapter-1/)by Vlad Zamfir — How Vlad started working on Ethereum and PoS. Slasher and deposits (Mar 2013 — Sep 2014)

* 2016.12.07 [History of Casper: Chapter 2](https://blog.ethereum.org/2016/12/07/history-casper-chapter-2/)by Vlad Zamfir — Nothing-at-stake. Bribing attack. Long range attack. Game theory and security research. (Fall 2014)

* 2016.12.11 [History of Casper: Chapter 3](https://medium.com/@Vlad_Zamfir/the-history-of-casper-chapter-3-70fefb1182fc) by Vlad Zamfir — Finality. Synchronicity Assumptions. Slashing Conditions. Tendermint. (Sep ’14 — Dec ’14)

* 2016.12.12 [History of Casper: Chapter 4](https://medium.com/@Vlad_Zamfir/the-history-of-casper-chapter-4-3855638b5f0e) by Vlad Zamfir — Cooperative Game Theory. Oligopolies. How Casper is different than other PoS consensus designs. (Dec’14 — Jan ’15)

* 2016.12.30 [History of Casper: Chapter 5](https://medium.com/@Vlad_Zamfir/the-history-of-casper-chapter-5-8652959cef58) by Vlad Zamfir — Censorship. Defining decentralization. Availability vs Consistency. Friendly GHOST (Feb ’15 — March ’15)

* *History of Casper series is to be continued…*
* Casper 系列历史继续...*

## Why Casper Matters |  为什么Casper重要

Now that we have decoded what this mysterious Casper project is. Let’s synthesize what we learned about PoS and Casper to understand why this matters.

现在我们解码了这个神秘的 Casper 项目。让我们综合一下我们对 PoS 和 Casper， 来理解 Casper 的重要性。


In simple terms:

1. Decentralization (covered in PoS)

2. Energy efficiency (covered in PoS)

3. Explicit Economic Security (covered in PoS)

4. Scaling Ethereum

5. Gentle Transition from PoW

简单来说：

1. 去中心化（PoS）
2. 能效（PoS）
3. 明确的经济安全（PoS）
4. 以太坊的扩展性
5. 从 PoW 温和过渡

### Because of Proof of Stake |  PoS 方面的原因

The first three points are covered in the Proof of Stake section. However, it is worth mentioning that at ~$28B, Ethereum is the second largest cryptocurrency and represents ~18% of the total market cap of the space. So any incremental decentralization and gains in energy efficiency can have a non-trivial impact today and a very significant impact in the future.

前三点在“权益证明”部分中介绍过。不过值得一提的是，以太价格在280亿美元上下时，它是第二大的数字货币，约占总市值的18％。因此，任何增量的去中心化和能源效益的提高都可能产生不平凡的影响，并对未来产生非常重要的影响。

As a review, (1) PoS has less available economies of scale because — “dollar for dollar” — a miner/validator can’t achieve outsized influence on the network. In PoW, a large mining pool might get more hashing power per dollar than an individual miner, whereas in PoS, a dollar is a dollar, which will likely mitigate the centralizing forces in mining.

作为回顾，（1）PoS 具有较小的可用经济规模，因为 - “美元兑美元” - 一个矿工/验证人不能对网络产生巨大的影响。在 PoW 中，一个大型矿池可能比单个矿工获得每美元更多的哈希算力，而在 PoS 中，一美元是一美元，这可能会减轻挖矿的中心化。

And (2) whereas PoW relies on energy wastage for network security, PoS relies on the potential of losing a deposit for network security. The challenge then becomes (3) how we mimic (and enhance) the positive features of PoW and mitigate the weaknesses of PoS with economic mechanism design.

（2）PoW 的网络安全依赖于能源的浪费，PoS 则依赖于保证金的损失。那么挑战就是（3）我们如何模仿（和增强）PoW 工作量证明机制）的优点，并通过经济机制设计来减少 PoS 的缺点。


### Because of Scaling | 扩展性的原因

Next, let’s talk about something new: (4) scaling. The key to understanding this is two-fold: (a) Casper is about establishing explicit finality (as opposed to probabilistic finality) and (b) explicit finality enables maintaining network security while scaling via [sharding](https://github.com/ethereum/wiki/wiki/Sharding-FAQ).

接下来，让我们来谈谈一些新的东西：（4）扩展性。理解这一点的关键是双重的：（a）Casper关于建立明确的最终共识（而不是概率上最终共识），（b）明确的最终共识可以通过[分片](https://github.com/ethereum/wiki/wiki/Sharding-FAQ)进行扩展来维护网络安全。

In PoW chains, finality is implicit (just as “skin in the game” is implicit via power wastage). The implicit nature of finality in PoW chains is apparent when you examine how transactions are finalized in real use cases. Depending on the magnitude and importance of the payment, you wait for additional number of block confirmations (number of block times since a transaction appears in the longest chain). For example, for a coffee, you might be okay with a few confirmations, but for buying a car, you may need more than the average number of
confirmations.

在 PoW 链中，最终共识是隐性的（如“游戏中的皮肤”特效是通过花费电力进行渲染）。当您检查交易在真实用例中的最终确定时，PoW 链中的最终性的隐性是显而易见的。根据付款的金额大小和重要性，您可以等待额外的块确认（最长链中出现交易以来的区块个数）。例如，对于买咖啡，您可以使用较少的确认，但是为了购买汽车，您可能使用比平均确认数量更多的区块个数来确认交易。

In contrast, Casper provides a concept of explicit finality. For example, Casper FFG begins to overlay finality on top of the PoW chain. So the underlying chain continues to have an implicit way of determining how final a transaction is. However, Casper FFG provides explicit finality [after about 2.5 “epoch times.”](http://ethresear.ch/t/casper-contract-and-full-pos/136/2) (Each epoch time being a sequence of 50 PoW blocks. A checkpoint is the last block in an epoch. It is first “justified” then “finalized” by a validator set. More details available in the paper linked above and potentially a future post.)

相反，Casper 提供了一个明确最终共识的概念。例如，Casper FFG 开始将最终性依赖于在 PoW 链上。因此，基础链依然有一种隐性的方式来确定交易的最终结果。然而，Casper FFG [在大约2.5 个epoch 时间窗口之后](http://ethresear.ch/t/casper-contract-and-full-pos/136/2)提供了明确的最终性（每个 epoch 是一个50个PoW 区块，一个检查点是一个 epoch 的最后一个块，区块首先被合理的提出，然后被验证人确定，在上面链接的文章中或以后的文章中可以看到更多的细节。）

At that point, with certain [Byzantine Fault Tolerance](https://en.wikipedia.org/wiki/Byzantine_fault_tolerance) assumptions, we can be sure that either our assumptions have been violated or that the checkpoint is final. Since we are also aware of the validator set a priori (which can also be dynamic), bad actors are penalized through fault attribution.

在这一点上，使用某些[拜占庭容错](https://en.wikipedia.org/wiki/Byzantine_fault_tolerance)假设，我们可以确定我们的假设是否被违反，或是检查点是最终的。既然我们也意识到验证人设定了先验（也可以是动态的），则不良行为者将通过分析故障归因而受到惩罚。

So how does this relate to sharding & scalability? Having this explicit finality allows more flexibility in how much (more accurately, how little) each node in the network has to do. Having more regular explicit finality allows further exploration of questions such as: what if not every node had to hold all of the state or all of the transactions? what if not every node had to validate every transaction? These questions of having heterogenous “responsibilities” of nodes in public blockchains are tackled by a workstream around [blockchain sharding](https://github.com/ethereum/wiki/wiki/Sharding-FAQ).

那么这与分片和可扩展性有什么关系呢？具有这种明确的终结性提供了
每个网络节点必须做的（更准确地说是更少的）工作的灵活性，有更多的定期明确的最终性允许进一步探索问题，如：如何处理如果不是每个节点都保存所有的状态或所有的交易？如果不是每个节点都必须验证每个事务怎么办？公链上有关区块的这些问题都在[区块分片](https://github.com/ethereum/wiki/wiki/Sharding-FAQ)工作中解决了。

So to go back to the point, **if we are to explore each node in the network “doing less” or “knowing less,” it is hugely beneficial to consider only the past few epochs of finality rather than the entire probabilistic chain since the genesis block.** Therefore, at this epoch time interval, finality doesn’t actually help with confirming a simple transaction, since transactions clear in number of confirmations fewer than the epoch time. Instead, finality will enable public blockchains to scale beyond the current ~10 transactions per second to larger orders of magnitude.

所以要回到这一点，**如果我们要网络中的每个节点“做得更少”或者“知道得更少”，
那么只考虑过去几个 epoch 时间内的确定性比考虑创世块以来的整个区块链的确定性有巨大的好处**。因此，在这个 epoch 时间间隔内，确定一个简单的交易实际上并不能提高最终性，因为确认次数比 epoch 时间少。相反，最终性将使公链扩展到比现在每秒至10个事务更大的数量级。

### Because Ethereum is worth ~$28B | 因为以太值280亿

The final point is (5) a gentle transition from PoW. Here’s the context for newcomers such as myself. Ethereum’s explicit goals to move to PoS predates the significant increase in the value of ether this year. The plan is to start with a hybrid PoS overlay on top of the ethash PoW chain and to ramp up gradually towards “pure” PoS. Given the significant increase in ETH network value, this gradual transition to PoS is a prudent strategy to prevent potential value destruction while transitioning a significant piece of the underlying Ethereum infrastructure.

最后一点是（5）从 PoW 平缓过渡。象我这样的新手需要了解的以下原委：以太的明确目标是在今年大幅度提高以太网的价值。该计划是在 ethash PoW 链的基础上混合 PoS，然后逐渐转向纯粹的 PoS 实现。鉴于 ETH 网络价值的大幅增长，逐渐过渡到 PoS 是一种谨慎的策略，用于防止潜在的价值破坏，同时转移重要的以太坊基础设施。

### Further Reading | 进一步阅读

* [Sharding FAQ 分片常见问题](https://github.com/ethereum/wiki/wiki/Sharding-FAQ), Ethereum wiki
* [On Slow and Fast Block Times](https://blog.ethereum.org/2015/09/14/on-slow-and-fast-block-times/) by Vitalik


## Design Principles | 设计原则

This is a collection of design principles found in various posts by Vlad and Vitalik. Currently, the guiding design principles for Casper are scattered around various resources. Hope reading them in one go provides more clarity on the overall design principles.

这是从Vlad和Vitalik发布的各种各样的文章中所收集的设计原则。当前，Casper的指导设计原则分散在各种资料间。希望能够整体阅读，提供更明确内容来概括设计原则的概念。

1、 **Economics to design behavior.** Explicit economic mechanism design can achieve implicit economic incentives found in other social contracts (i.e. consensus protocols like proof of work). If you like analogies, search “big games” in [History of Casper part 3](https://medium.com/@Vlad_Zamfir/the-history-of-casper-chapter-3-70fefb1182fc).

1、**经济学设计行为**。明确的经济机制设计可以实现其他社会契约（如以工作证明方式的共识协议）中隐含的经济激励。如果你喜欢类比，在[History of Casper part 3](https://medium.com/@Vlad_Zamfir/the-history-of-casper-chapter-3-70fefb1182fc)中搜索“big games” 。


2、 **Maximize cost of attack.** For example, the amount of damage that an attacker can do to a protocol’s utility should be bound by some “[griefing factor](http://vitalik.ca/general/2017/07/16/triangle_of_harm.html).” In order to do $100 of damage, it shouldn’t cost $0.01. It should hopefully cost in the order of $100. In other words, we want to minimize the “attack multiple” of each dollar used for attacking the protocol (more on this coming in another post).

2、 **最大化攻击成本**例如，攻击者可以对协议功能进行攻击的损坏程度应受到一些行为因素的约束“[griefing factor](http://vitalik.ca/general/2017/07/16/triangle_of_harm.html).”。为了造成100美元的损失，不应该花费0.01美元。也希望成本在100美元左右。换句话说，我们希望最大限度地减少用于攻击协议的每一块钱的“攻击利益倍数”（更多的是在另一篇文章中介绍）。

3、 **Public cost-benefit, not just private.** Protocol economics should account for social (i.e. “public”) cost & benefit (negative and positive [externalities](https://en.wikipedia.org/wiki/Externality#External_costs)) as we begin scaling public blockchains. Energy cost, environmental impact and wealth distribution are some notable examples.

3、**公共成本效益，不只是私人的**。在我们开始扩张公有链时，协议经济学应该考虑到社会（即 “公众”）成本和利益（消极和积极的外部因素）。能源成本，环境影响和财富分配是一些显着的例子。


4、 **Prevent [economies of scale](https://en.wikipedia.org/wiki/Economies_of_scale)**. Centralization weakens the main value proposition of public blockchains. Preventing economies of scale prevents those centralizing factors and build more secure blockchains.

4、 **防止[规模经济](https://en.wikipedia.org/wiki/Economies_of_scale). 中心化削弱了公有链主要的价值**。阻止规模经济能杜绝产生中心化要素，并能建立更安全的区块链。

5、 **Network security is derived from “skin in the game.”** Simple yet worth reiterating. The more you have to lose, the more we can trust you as a validator. Whereas burning energy secures proof of work chains, “[putting up economic value-at-loss](https://medium.com/@VitalikButerin/a-proof-of-stake-design-philosophy-506585978d51)” secures proof of stake chains.

5、 **网络安全来源于“游戏中的皮肤”**。简单而值得重申。你抵押愿意可能失去的越多，我们才可以更相信你作为一个验证人。虽然燃烧能源确保了pow的链安全，但“[经济价值的损失](https://medium.com/@VitalikButerin/a-proof-of-stake-design-philosophy-506585978d51) ”确保了POS链的安全。


6、 **Design for [oligopolies](https://en.wikipedia.org/wiki/Oligopoly).** Cooperative game theory is the name of the game as a protocol won’t be able to fully mitigate the inherent centralizing forces (e.g. economies of scale) in a network. This means analyzing all edge cases that involve self-interested cartel behavior. Notably, a protocol should disincentivize cartels from bullying non-cartel validators (i.e. be “friendly”)

6、**寡头垄断设计**。合作博弈理论，是协议将无法完全减轻网络中固有的集权力（即规模经济）的博弈的名称。这意味着分析所有边缘案例影响着自利卡特尔行为。值得注意的是，协议应该能避免卡特尔验证人欺凌非卡特尔验证人（即 “友好”）


7、 **Accountable safety.** Design that makes it possible to attribute faults to bad actors as much as possible. Casper relies on the ability to slash attributable Byzantine behavior.

7、 **追责安全**。设计应使得尽可能的能将故障归因于某个不良行为者。Casper依赖于削减归因拜占庭行为的能力。

8、 **Plausible liveness.** Design that doesn’t allow attackers to block the chain from continuing to propose and vote on checkpoints/blocks. This is where Casper differs from other implementations such as Tendermint, which will “lock up” if safety isn’t achieved synchronously.

8、**合理的活跃度**。设计不允许攻击者阻止区块链的不间断提议的发起和对检查点/区块块进行投票。这就是Casper与其他实现方式（如Tendermint）的区别，Tendermint如果没有同步实现安全性，它将“锁定”。

9、 **Minimal synchronicity assumptions.** To allow for liveness and “unblock” the chain growing, Casper has minimal synchronicity assumptions. In fact, we expect nodes to log on as infrequently as every couple of months.

9、 **最小同步性假设**。为了让其活跃和不阻断区块链增长，Casper具有最小的同步性假设。事实上，我们预计节点每几个月都不会频繁登录。


10、 **Decentralized things should be able to regenerate.** A protocol is decentralized only if it can fully recover from the permanent removal of all but one of its nodes. Availability, not just consistency (Again, Tendermint is susceptible to getting “blocked” and cannot regenerate; the validator set for each branch can keep getting smaller [per Matthew Wampler-Doty and Vlad’s observation](https://medium.com/@Vlad_Zamfir/the-history-of-casper-chapter-4-3855638b5f0e))

10、**去中心化的事物应该能够被重新生成**。一个协议只有在能够从永久删除所有其他节点，从只留下一个节点中完全恢复才能算是去中心化。可用性，而不仅仅是一致性（同样，Tendermint很容易被“阻挡”，无法重新生成;每个分支的验证人集合将不断变的更小[根据Matthew Wampler-Doty和Vlad的观察](https://medium.com/@Vlad_Zamfir/the-history-of-casper-chapter-4-3855638b5f0e))

11、 **Disincentivize censorship.** The major tradeoff is that validators have a new attack vector by deliberately going offline. However, cartel censorship is the greater evil here. Choosing the right relative cost of censorship vs. rewards and other penalties (as a % of deposits) will be the key to getting this right.

11、**反审查**。主要的权衡的是有一种新的攻击维度是验证人故意离线。不过，卡特尔的审查制度在这里是更大的罪恶。选择审查制度的相对成本与奖励和其他处罚（作为存款的百分比）将是获得这项权利的关键。

### Further Reading 进一步阅读

* [PoS Design Philosophy](https://medium.com/@VitalikButerin/a-proof-of-stake-design-philosophy-506585978d51)  PoS设计理念

* History of Casper (links above) Casper历史（上面的链接）

## Challenges 挑战

Broader list of Ethereum challenges are available
[here](https://github.com/ethereum/wiki/wiki/Problems).

[这里](https://github.com/ethereum/wiki/wiki/Problems).提供了更广泛的Ethereum面临的挑战的列表。

### Challenges for Proof of Stake | POS的挑战

[**Nothing-at-stake problem**](https://ethereum.stackexchange.com/questions/2402/what-exactly-is-the-nothing-at-stake-problem) — If there’s a fork in the chain, the optimal strategy for any validator is to validate on every chain, so that the validator gets their reward regardless of the outcome of the fork.


[**无利害关系**](https://ethereum.stackexchange.com/questions/2402/what-exactly-is-the-nothing-at-stake-problem)   - 如果链进行了分叉，任何验证人的最优策略是在每个链上都进行验证，以便验证人获得奖励，而不考虑叉的结果。

[**Long range attack**](https://blog.ethereum.org/2014/05/15/long-range-attacks-the-serious-problem-with-adaptive-proof-of-work/) — Same mechanism as 51% attack (make a longer chain that rewrites the ledger in the attacker’s favor), but instead of starting the attack 6 blocks back, go much further back in the chain’s history (i.e. 60,000 blocks). This is a problem for PoS since it there’s no proof of work required to rewrite a very long chain.

[**长程攻击**](https://blog.ethereum.org/2014/05/15/long-range-attacks-the-serious-problem-with-adaptive-proof-of-work/)   - 与51％的攻击相同的机制（使得更长的链条以攻击者的方式重写账本），但不只是攻击了前面的6个区块，而是回朔到更早的链的历史中(比如6万个区块)。这是PoS的一个问题，因为它没有工作量证明重写一个很长的链。


These two main challenges are solved via ideas from [slasher](https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm/) (and its improved variations). The main points are that (1) validators are known, which allow for fault attribution at a validator level and (2) by having “slashing conditions” that strongly disincentivize certain actions, it is possible to mitigate these issues. Again, this example is crucial in understanding the Casper team’s view on consensus algorithm design: we can leverage economic mechanism design to a secure distributed system.

解决这两个挑战的想法来自于[slasher](https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm/) (以及其改进的变体)。要点是：(1)验证人是已知的，这允许在验证人级别的错误归因;（2）通过“削弱条件”强烈地抑制某些行为，可以减轻这些问题。再次，这个例子对于了解Casper团队对共识算法设计的观点至关重要：我们可以将经济机制设计用于安全的分布式系统。


### Criticisms of Proof of Stake | 对POS的批评

**Adverse selection** — Given the potentially draconian penalties, many average or risk-averse “candidate validators” may stay away from participating as a validator. Then, one may argue people with more to gain by “gaming the system” are more likely to join as a validator. More broadly, one may claim that — on average — a good actor may never have a better ROI than a bad actor.


**[逆向选择](http://wiki.mbalib.com/wiki/%E9%80%86%E5%90%91%E9%80%89%E6%8B%A9)** — 由于有潜在的严厉惩罚，很多中等或者厌恶风险的候选验证人可能会不参加验证人。那么人们可能会争论那些寻找游戏规则漏洞的人更有可能成为验证人并获取更多利益。更广泛地，可以这么说—一个好人永远的得不到比坏人更好的回报。

*Response:*

This falls under future work and an area of great focus for the research team: cryptoeconomics. As the parametrization of the mechanism is progresses, the team will iterate on optimizing the constants the balance the risk reward tradeoffs as well as their proportion to the size of the deposits and the action of others (Byzantine behavior).

*回应:*

这是未来的要解决的工作，也是研究团队的重点领域：密码经济学。随着这个机制的参数化深入，团队将迭代的去不断优化参数，平衡风险回报与存款规模的比例和他人的行为(拜占庭行为)。

It’s worth mentioning that this problem is also existent (albeit to a lesser degree given the nature of proof of work) in Bitcoin.

值得提的是这个问题同样存在于比特币中。

**“The rich get richer”** — Another common concern when people hear “a consensus algorithm based on how much money you’re staking” is that this may exacerbate wealth inequality within the crypto ecosystem as well as more broadly in the global economy.

**富有的变的更富有** — 另外一个共同的担忧是当人们知道“共识算法是基于你持有多少的代币”，这可能会加剧在这个加密货币生态系统中财富的不平等，同时更广泛的发生在全球的经济中。

*Response:*

The main takeaway here should be that Proof of Stake is considerably more egalitarian (i.e. gives less benefit to having more capital) than the incumbent Proof of Work based algorithm of Bitcoin.

As discussed in the Proof of Stake overview above, **PoS mitigates economies of scale**, which diminishes the centralizing force among miners. Again, **in PoS, a dollar is a dollar**.

Therefore, against the fair intuition that PoS can exacerbate wealth inequality, it is in fact a non-trivial improvement on the status quo.

*回应:*

这里的主要观点应该是POS和现行基于算法的比特币POW相比较是相对平等(如拥有大资金的获得较少的好处)。正如上面讨论的关于PoS的概述，**PoS削减了规模经济**，这减少了矿工的集权。而且，**在PoS中，一美元就是一美元**。所以根据合理的直觉判断，反对PoS将加剧财富不平等，这实际上是对现状的一个不平凡的改进。


Quick aside: In order to have diseconomies of scale or progressive wealth distributions in PoS (one more degree of counteracting wealth inequality), I posit that it is necessary to have mature and reliable identity or reputation systems. Otherwise, larger pools of money will have “sybil behavior” that spreads their wealth over many “less wealthy” false identities that will collectively capture the benefits of a progressive reward system. However, this challenge will be solved a bit further down the line and is also out of scope for Casper.

题外话：为了在PoS中具有不规则的扩张或者阶梯式的财富分配(一个消除财富不平等分配的新维度)，我认为有必要拥有成熟可靠的身份或者荣誉系统。否则，较大的资金池将会有“女巫行为”假冒的身份也能够享受到阶梯式奖励系统的好处。然而，这个挑战将被进一步解决，这也超出了Casper的范畴。

### Questions/Concerns around Casper | 对于Casper的问题/关注

**“It’s confusing to have multiple Caspers.”**

**“有多个Casper让人困惑”**

Sorry about that! This post aims to lessen the cognitive dissonance around that fact. But to review, Casper is Ethereum’s family of PoS research and implementations. These work streams will likely converge, but the nature of protocol research requires forking sometimes to explore various approaches until deciding on the best way forward. Things tend to get more complex before they get simpler 🙂

很抱歉！这篇文章的目标是减少认知不对称。但是要回顾一下，Casper是以太坊家族PoS的研究和实现。这些不同的工作流将很可能殊途同归，但是协议研究的本质有时候需要在确定最佳方案实施以前去研究各种不同的方法。事情往往先变的越来越复杂，才会变得简单。

**“How does Casper differ from Tendermint?”**

**“Casper和Tendermint有什么区别？”**

The simplified answer here is that Casper focuses on liveness (availability) and can accept less immediate safety (correctness). While Tendermint is a great project, its downside is that the chain will stall if a checkpoint doesn’t have 2/3 of the votes. That is one of the reasons why Ethereum is working on Casper rather than working off of Tendermint.

这里比较简单的回答是Casper重点关注活跃度(可用性)和可以接受相对不实时的安全(正确性)。虽然Tendermint是一个伟大的项目，但他的缺点时，如果检查点没有得到三分之二的投票，那么链出块将会停止。这就是为什么以太坊选择在Casper上做工作而不是使用Tendermint的原因。

To quote [Vlad Zamfir](https://medium.com/@Vlad_Zamfir):

引用[Vlad Zamfir](https://medium.com/@Vlad_Zamfir):

>Tendermint favours consistency over availability, Casper favours availability over consistency (see [the CAP theorem](https://en.wikipedia.org/wiki/CAP_theorem)).

>Tendermint doesn’t punish online validators for potentially censoring potentially-actually-just-offline validators.

> Tendermint 更倾向一致性多于可用性，Casper 更倾向可用性多于一致性(参考 [CAP理论](https://en.wikipedia.org/wiki/CAP_theorem))

> Tendermin 对于在线的验证节点没有检查潜在刚刚下线的验证节点的行为，Tendermint 没有做出惩罚。

For further reading on this topic: [Hudson Jameson](https://medium.com/@hudsonjameson)’s explanation this quote, reddit discussion featuring [Vitalik](https://medium.com/@VitalikButerin) & [Jae Kwon](https://medium.com/@jaekwon), and the [Tendermint whitepaper](https://tendermint.com/static/docs/tendermint.pdf).

更多的了解这个主题： [Hudson Jameson](https://medium.com/@hudsonjameson) 解释这个引用， reddit讨论板块 [Vitalik](https://medium.com/@VitalikButerin) & [Jae Kwon](https://medium.com/@jaekwon), 以及 [Tendermint 白皮书](https://tendermint.com/static/docs/tendermint.pdf).

**“ 😱 You’re going to change the engine of a live $28B network?”**

**“ 我们将要为一个价值280亿美金活跃的网络更换引擎?”**

Yes, that is very ambitious and daunting. However, moving to PoS was the intent since the early days, and one of the guiding principles of the project. The community members were very much aware of Ethereum’s plans to switch to PoS (i.e. refer to [Ethereum Ice Age](https://www.cryptocompare.com/coins/guides/what-is-the-ethereum-ice-age/) — the PoW chain difficult adjustment to encourage migration to PoS — which is commonly known in the ecosystem).

是的，这真的是非常有抱负和艰巨的事情。然而， 切换到 PoS 在很早的时候其实已经计划了，也是项目的指导原则之一。社区的成员非常链接以太坊改用 PoS 的计划。( 参考 [以太坊冰河时代](https://www.cryptocompare.com/coins/guides/what-is-the-ethereum-ice-age/)  —这条 PoW 举步维艰的调整的并被鼓励迁移到 PoS 上—这是被生态系统中众所周知的)。

This should go without saying, but the team will be rolling out the change in stages with the test network. Also, the initial implementation is a hybrid where the PoS elements have less of an economic impact — and therefore impact on security — than in the eventual “pure” PoS consensus.

不用多说这件事应该继续推进，但是团队将通过测试网络逐步推进变革。同时，最初的实现是混合的 PoS 模式，比起最终的纯 PoS 共识，这样做对经济和安全的影响相对较小。

**“In practice, transactions are cleared in 10 blocks. Why does finality matter over a 50 block epoch?”**

**“在实践中，交易一般在10个区块就被确认了。为什么最终确定需要通过一个50个区块的 epoch?”**

We covered this above, but let’s go over this once again since it’s important.

我们在上面已经提过了，但是由于这个很重要，再提一次。

First, Casper enables [sharding](https://github.com/ethereum/wiki/wiki/Sharding-FAQ).

首先，Casper 将开启[分片](https://github.com/ethereum/wiki/wiki/Sharding-FAQ).

This was very unclear to me in the beginning, but that’s because we need to take a step back from Casper for a moment. Ethereum has many goals, but one of them is to provide a scalable blockchain solution, both technically and environmentally. Ethereum is building for a world where cryptocurrencies have a larger place in the global economy and grow by many orders of magnitude. In that vision, Casper aims to prevent the wasted energy of PoW mining but we still need to scale Ethereum technically. That project is largely encompassed under sharding.

一开始我对这个并不是很了解，但这是因为我们需要先抛开 Casper。 以太坊有很多的目标，但其中之一就是在技术和环境方面提供可扩展的区块链解决方案。以太坊正在构建一个世界，在这个世界里数字货币在全球经济中将拥有更大的空间，数量级上将有很大增长。在这个愿景中，Casper 旨在防止 PoW 挖矿浪费能源，但是我们仍然需要在技术上扩展 Ethereum。这个项目一大部分涵盖在了分片技术中。

Today, every node in the network does everything. Sharding explores various ways to decrease the average responsibility of each node. The details are out of scope of this post, but an example might be to pose the question: “are there ways to create a new mechanism, where only small subset of nodes verifies each transaction?”

The takeaway is that the periodic finality provided by Casper will mitigate lower security related to implementing sharding.

今天，网络中的每个节点做了所有事情。分片探索了各种办法来减少每个节点所担负的责任。这些细节超出了这篇文章的范畴，但是一个例子可能提出一个问题“有没有一种办法创建一种新机制，只用很小的节点组来验证每一个交易？”

另外的信息时，Casper 提供的定期最终共识在实现分片的过程中将带来更小的安全风险。

Second, explicit finality allows for a consistency-favoring blockchain. To quote Vitalik:

>In a PoW chain, if there is, for example, a geth/parity consensus split, then both chains keep growing, and exchanges running one client or the other risk finalizing deposits on a bad chain. But if exchanges wait for Casper finality, then in a 50/50 split it’s likely *neither* chain will finalize. This increases the safety of the platform, as in extreme circumstances it “defaults toward finalizing nothing” rather than finalizing *the wrong thing*.

第二点，明确共识机制更被推崇一致性的区块链所青睐。引用自 Vitalik：

>在一个 PoW 链中，如果发生类似 geth/party 的共识分叉，然后两条链同时又在增长， 同时交易所只运行了一种客户端或者有风险存款验证在一条坏的链上。但是如果交易所等待 Casper 共识，那么在50/50的分叉中可能任何一条链都不会最终共识。这增加了平台的安全性，因为在极端情况下，它“默认不去做最终共识” 好过于共识*错误的东西*。

In sum, contrary to intuition, explicit finality matters less for transaction clearing and more for blockchain scalability and safety.

总的来说，与直觉相反，明确的共识对交易清算不是那么重要，对区块链的扩展性和安全性更重要。

## Future Work | 未来的工作

### Execution | 执行

* Finalizing the design of FFG and CBC.

* Implementing proof of concept code.

* Deploying into test nets.

* 最终确定FFG和CBC的设计

* 实现概念论证的代码

* 在测试网络部署

### “The One Casper” | 一个Casper

Thinking about about the final state of Casper PoS. How to leverage concepts from both FFG and CBC to converge on a final state that is compelling, secure and elegant.

思考 Casper PoS 的最终状态。如何利用 FFG 和 CBC 的概念来整合成一个最终令人信服，安全和优雅的版本。


### Parameter Optimization | 参数优化
For a given mechanism, optimize parameters and constants for intended incentivization. Iterate on mechanism design with findings.

对于一个确定的机制，优化用于预期激励方式的参数和常数。在机制的设计和发掘上进行迭代。

### Community Education | 社区培育
Writing more about the thought process beyond various research work streams to keep engaging with Ethereum, PoS and broader crypto communities.

写更多除了各种研究工作进度有关而于思想过程相关的文章，继续于以太坊， PoS 和更广泛的数字社区接触。

### Potential Future Posts | 将发布的之后的文章

* History of Casper Part 6

* Deep dive into how Casper enables sharding

* Deep dive into how and why Casper is different from competing designs

* Non-monetary measures of “stake” and “skin in the game” (i.e. $10,000 is worth more to average person than billionaire)

* Griefing Factor Analysis 2.0

## Glossary | 词汇表

We covered a lot of concepts in this post, and you will run into some other common ones as you dive into the maze of Chrome tabs that will inevitably ensue. Here’s a rough summary of the most helpful and common concepts you need to grok. Hope it helps!

我们在这篇文章中介绍了很多概念，您会碰到其他一些常见的概念，你将不可以避免的陷入大量的Chrome网页中。这是您需要了解最有用和最常见的概念的粗略总结。希望有帮助！(译者：下方词汇表请自行浏览，不进行翻译)

**[Proof of Stake](https://github.com/ethereum/wiki/wiki/Proof-of-Stake-FAQ)** — a category of consensus algorithms for public blockchains that depend on a validator’s economic stake in the network.

**[Casper](https://blog.ethereum.org/2015/08/01/introducing-casper-friendly-ghost/)** — Ethereum’s proof of stake research and projects.

**Finality** — Once an operation in a system completes, the system doesn’t allow for the operation to be reverted ([Vitalik on settlement finality](https://medium.com/@jonchoi/an%20attack%20wherein%20a%20reputation%20system%20is%20subverted%20by%20forging%20identities%20in%20peer-to-peer%20networks)). Context: in proof of work, finality is probabilistic and implicit. Casper is designing mechanisms that explicitly enforce finality.

**[Fork Choice Rule](https://medium.com/@VitalikButerin/minimal-slashing-conditions-20f0b500fc6c)** — A fork choice rule is a function, evaluated by the client, that takes as input the set of blocks and other messages that have been produced, and outputs to the client what the “canonical chain” is.

**[Slashing Conditions](https://medium.com/@VitalikButerin/minimal-slashing-conditions-20f0b500fc6c)** — Set of rules that, if violated, penalize the validator.

**[Sybil Attack](https://en.wikipedia.org/wiki/Sybil_attack)** — an attack wherein a reputation system is subverted by forging identities in peer-to-peer networks.

**[3 E’s of Sybil Resistance](https://twitter.com/dominic_w/status/648330685963370496)** — 1. Entry Cost 2. Existence Cost 3. Exit Penalty. (coined by [Dominic Williams](https://medium.com/@dominic_w)).

**[Nothing-at-stake problem](https://ethereum.stackexchange.com/questions/2402/what-exactly-is-the-nothing-at-stake-problem)** — A proof of stake implementation challenge that refers to the inherent lack of downside for validating both chains in the case of a fork. It is a well-known problem of proof of stake that is considered solvable. For example, refer to [Slasher](https://blog.ethereum.org/2014/01/15/slasher-a-punitive-proof-of-stake-algorithm/).

**Bribe attack** — Attacker uses a bribe to change the Nash Equilibrium of a validator’s game theory framework to undermine the security of the protocol. (More context in [History of Capser pt 2](https://blog.ethereum.org/2016/12/07/history-casper-chapter-2/))

**[Long range attack](https://blog.ethereum.org/2014/05/15/long-range-attacks-the-serious-problem-with-adaptive-proof-of-work/)** — Same mechanism as 51% attack (make a longer chain that “rewrote” the ledger in the attacker’s favor), but instead of starting the attack 6 blocks back, go much further back in the chain’s history (think 60,000 blocks).

**[DAG](https://en.wikipedia.org/wiki/Directed_acyclic_graph)** — “Directed Acrylic Graph”. A finite directed graph with no directed cycles. ([ETH Stack Exchange](https://ethereum.stackexchange.com/questions/1993/what-actually-is-a-dag)).

**GHOST** — “Greedy Heaviest Observed Subtree.” It’s a chain selection rule with the objective of fast confirmation times while limiting compromises in security or decentralization. ([Original Paper](https://eprint.iacr.org/2013/881.pdf), [ETH GHOST](https://github.com/ethereum/wiki/wiki/White-Paper#modified-ghost-implementation))

**Synchronicity** — Refers to the timing assumptions around the messages (i.e. synchronous, partially synchronous and asynchronous).


**Liveness** — “Availability.” Protocol-following nodes eventually decide on a value. Opposite would be a network state that is blocked from deciding on a value (i.e. Tendermint without 2/3 votes at a given depth)

**Safety** — “Correctness.” Protocol-following nodes decide on the same value. Another intuitive proxy is whether two conflicting blocks can be committed.

**[FLP Impossibility Theorem](https://groups.csail.mit.edu/tds/papers/Lynch/jacm85.pdf)** — “It’s impossible to have a live, safe and asynchronous network” (formally proven as well).

**Accountable Faults** — Faults that can be attributed to a specific validator or specific set of validators.

**[Byzantine Faults](https://en.wikipedia.org/wiki/Byzantine_fault_tolerance) / Byzantine Behavior** — Any fault presenting different symptoms to different observers. Non-protocol following behavior.

**Byzantine Failure** — Loss of a system service due to Byzantine faults in a system that requires [consensus](https://en.wikipedia.org/wiki/Consensus_%28computer_science%29).

**[Byzantine Fault Tolerance](https://en.wikipedia.org/wiki/Byzantine_fault_tolerance)** (“BFT”) — Ability for a system to tolerate Byzantine faults. 1/3 Byzantine fault threshold in asynchronous networks. 1/2 in synchronous networks. (BFT consensus algorithms include Paxos, PBFT as well as newer Casper and Tendermint).

**Nakamoto Consensus** — PoW-based bitcoin-style consensus building. Also, Nakamoto-style Consensus exists, which would be chain-based PoS as opposed to BFT-based PoS.

**[Tendermint](https://tendermint.com/static/docs/tendermint.pdf)** — Proof of Stake implementation that focuses on consistency. Never forks with less than 1/3 malicious actors, but downside is that the chain can stall if a chain lacks 2/3 of the validator votes.

**Validator** — An entity that validates checkpoints/blocks of a blockchain for rewards. A miner analog in PoS.

**Validator Set** — Set of validators for a given chain at any given time.

**Checkpoint** — In FFG, it is a block spaced in regular intervals (i.e. every 50 blocks) where the PoS validation mechanism is overlaid on top of the underlying PoW chain (e.g. Ethereum with ethash)

**Epoch** — In FFG, it is a 50 block period where a validator can vote on the finality of its final block (i.e. checkpoint). PoW miners mine blocks and PoS validators validate checkpoints every epoch.

**Dynamic Validator Sets** — The idea that a blockchain can have changing set of validators throughout a period. Treatment of this is a huge breakthrough in BFT-style consensus algorithms. Tendermint was first notable breakthrough. Casper is also working on this actively.

**Equivocation** — The act of a validator sending two messages that conflict with each other (more specific definition on [slide 28 of this deck](https://ethereumfoundation.org/devcon2/wp-content/uploads/2016/10/A-Correct-by-Construction-Asynchronous-Casper-Protocol.pdf)).

**Dunkles** — Mechanism that includes data from non-dominant block into the dominant block. This provides better incentive mechanisms and notably helps alleviate the nothing-at-stake problem ([link](https://ethereum.stackexchange.com/questions/19146/are-there-still-uncles-with-proof-of-stake)).

**Proposal Mechanism** — Mechanism by which a validator in the set will suggest a block to assess for justification or finalization.

**Justification** —In FFG for example, 2/3 of a validator set voting on a fresh checkpoint that a checkpoint is the accurate record. This is the intermediary step for a finalized checkpoint.

**Finalization** — In FFG for example, 2/3 of a validator set voting on a justified checkpoint that a checkpoint is the accurate record. The completion of this step gives a checkpoint finality.

**[State Transition System](https://github.com/ethereum/wiki/wiki/White-Paper#bitcoin-as-a-state-transition-system)** — A system that maintains a given state (e.g. set of transactions or accounts) and its mutations over time (i.e. transition). Bitcoin, Ethereum, and other public blockchains can be considered state transition systems.

**Protocol Utility Function** — “…a formula that tells us how well the protocol is doing, that should ideally be calculable from inside the blockchain. In the case of a proof of work chain, this could be the percentage of all blocks produced that are in the main chain. In Casper, protocol utility is zero for a perfect execution where every epoch is finalized and no safety failures ever take place, with some penalty for every epoch that is not finalized, and a very large penalty for every safety failure. If a protocol utility function can be formalized, then penalties for faults can be set as close to the loss of protocol utility resulting from those faults as possible.” (from [Triangle of Harm](http://vitalik.ca/general/2017/07/16/triangle_of_harm.html))

## Conclusion | 总结

OK, this was a lot of information for a “101,” but now you have all the basics covered and the context to dive into any Casper conversation. My intention in writing this post was (1) to provide an overarching thread of context across the plethora of information out there on Casper, (2) solidify my own understanding of Casper as I dive into cryptoeconomic research for Ethereum scaling (Casper, sharding, gas pricing), (3) to raise awareness and encourage conversation about PoS, Casper and Ethereum and (4) to convince talented mathematicians, economists, computer scientists and developers to start diving into the problems we are trying to solve.

好了，这是一个“初步了解”的很多信息，但是现在你基本上掌握了所有的基本知识，并且可以深度到任何 Casper 的交流。我写这篇文章的目的是 （1）从大量的关于 Casper 的内容中整理提供一个总体的大纲 （2）巩固我自身队 Casper 的认识因为我正在研究以太坊(Casper， 分片，Gas 价格) (3) 勾起大家对 PoS，Casper 和以太坊的认知和讨论 (4) 驱动有才华的数学家，经济学家，计算机科学家和开发者们开始一同来解决我们的问题。

If you want to dive deeper, dive into the resources linked throughout the post, consider contributing to the future work, and talk to your math, CS, economics, game theory, and distributed systems friends (in and out of crypto) about Ethereum and Casper.

如果你想更深入地了解，请查阅文章中的链接参考资源，考虑为未来的工作做贡献，并与你身边了解数学，计算机科学，经济学，博弈论和分布式系统的朋友（不管是否在数字货币领域）谈谈以太坊和 Casper。

If you’ve made it this far, thank you for reading. Hope this helped and please reach out with questions, concerns or comments via email or twitter. We would love to hear your feedback!

如果你看到这，谢谢你的阅读。希望这对你有帮助，请通过电子邮件或 twitter 来向我提出问题，意见或者评论。我们很乐意听到您的反馈！

Special thanks to [Vitalik Buterin](https://medium.com/@VitalikButerin), [Vlad Zamfir](https://medium.com/@Vlad_Zamfir), [Virgil Griffith](https://medium.com/@virgilgr) and [Karl Floersch](https://medium.com/@karl_dot_tech) for discussion and review. All errors remain my own.

特别鸣谢 [Vitalik Buterin](https://medium.com/@VitalikButerin), [Vlad Zamfir](https://medium.com/@Vlad_Zamfir), [Virgil Griffith](https://medium.com/@virgilgr) and [Karl Floersch](https://medium.com/@karl_dot_tech) 参与讨论。所有的错误都是我自己的。

*Thanks to Vitalik Buterin and Karl Floersch.*

*谢谢Vitalik Buterin和Karl Floersch.*

----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

* 胖哥Ricky 区块链技术爱好者，资深技术达人，开设技术性关于区块链公众号：__胖哥说币__

以非典型技术男的角度分享技术性币圈观点。


* 鱼 区块链技术爱好者，微信号: oscnet


本文由币乎社区（bihu.com）内容支持计划赞助。

版权所有，转载需完整注明以上内容。

----------------------------------------------------
