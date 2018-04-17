
>文章来自：https://masterthecrypto.com/guide-cryptocurrency-valuation-onchain-data/
>
>译者：区块链中文字幕组 Chuan
>
>时间：2018-04-17

The ubiquitous price chart. Over the past year, variations of the image above have become a mainstay on the screens of millions of rabid cryptocurrency investors. Price is the guiding beacon that the majority of investors in crypto live and die by today. The art of using historical prices to predict future price movements is called technical analysis, and is widely used by many in the crypto world.

价格趋势图无处不在。过去一年，上面这个图表的各种变化形式占据着上百万狂热的虚拟货币投资者的屏幕。价格是指引大多数虚拟货币投资者活到今天以及离开人世的风向标。使用历史价格来预测未来价格走势的做法称作技术分析，被虚拟货币世界中的人广泛地采用。

When wild upswings or downswings in price occur, as happens quite frequently, it is often simply chalked up to market sentiment or periodic swings in demand.

当价格上涨或者下降变得非常频繁时，这经常被简单归结为市场情绪或者需求上的周期波动。

In this piece, we will make the case for why examining who is transacting on-chain is the key to fundamentally understanding and valuing cryptocurrencies. We will focus on the Ethereum blockchain and go over some of the nuances involved in interpreting on-chain data.

这篇文章里，我们将举例说明为什么研究谁在链上交易是基本理解和估值加密货币的关键。我们将专注于以太坊区块链，认真讨论在解释链上数据时一些细微的差异。

#### What’s On-chain Data? 什么是链上数据？
First off, what do we mean by on-chain data? To put it succinctly: All data that is natively stored on the blockchain.

首先，链上数据是什么意思？简单来说，所有存储在区块链上的数据。

This data includes (but is not limited to):

这些数据包括（但不仅限于）：

* Details of every block (timestamp, gas price, miner, block size etc.) 
* 每个块的具体信息（时间戳、Gas价格、矿工，区块大小等等）
* Details of every transaction (The ‘from’ and ‘to’ addresses, the amount transferred in the transaction etc.)
* 每笔交易的详情（发送方地址，接收方地址，交易中传输的数量等等）
* Smart contract invocation and usage
* 智能合约的引用和使用

#### Why Is This Information Interesting? 为什么这样的信息值得关注？

Of late, many thinkers in the burgeoning field of cryptoeconomics have proposed theoretical frameworks to fundamentally value cryptoassets -whether it is the application of the equation of exchange (MV =PQ) to cryptoassets by Chris Burniske, an alternative interpretation of token velocity by Alex Evans and the levers that influence it by James Kilroe, or the popular Network Value to Transactions (NVT) ratio championed by the excellent coinmetrics team and by Woobull.

最近，在迅速增长的加密货币领域许多富有创意的人提出一些理论框架来对加密货币资产进行基本的评估 - 无论是Chris Burniske把交易等式（MV=PQ）应用到加密货币资产，还是货币计量组和Woodbull提出的网络价值对加密货币资产交易（Network Value to Transactions）的比率。

> Many of these different valuation methodologies use on-chain transaction volume as a proxy for the network utility of a given cryptoasset.
>
> 在这些不同的评估方法中，许多都使用链上交易规模作为对一个指定的加密货币资产的网络价值的替代值。

In other words, the on-chain transaction volume is being used to judge whether a given cryptoasset is actually being used.

换句话说，链上交易规模被用于判断一个指定的加密货币资产是否实际被使用。

Instead of just crudely measuring the overall usage of a cryptoasset network, we think we can use on-chain transaction data to figure out who are the entities that are actually using a given cryptoasset. 

我们并不是粗略地评估一个加密货币网络的整体使用情况，而是使用链上交易数据来弄清楚谁在使用这个加密货币资产。

This allows us to examine and learn from their on-chain transaction patterns – leading to deeper and more nuanced insights to fundamentally value the cryptoasset in question.

这让我们可以研究链上交易模式并从中学习，最后能够对受到质疑的加密货币资产的估值拥有更深层的、更加细微的见解。

#### Classifying Addresses 对地址分类

Wait a minute… isn’t information about “who” is transacting hidden on the blockchain? Isn’t that the whole point of public-key cryptography?

等一下......难道信息不是关于“谁”在区块链上交易吗？难道那不是公钥加密方法干的事儿吗？

Yes and yes.

是的，是的。

We found a little quirk though.

可是我们发现一些奇怪的事情。

When one steps back and examines every Ethereum address (unique user account) and their respective on-chain transactions in aggregate — one begins to see distinct clusters of addresses that exhibit remarkably similar transaction patterns and on-chain behaviour. 

当人们退一步思考，查看每个以太坊地址（唯一的用户账户）和他们各自的汇总的链上交易时，他们开始看到截然不同的地址簇，呈现出明显相似的交易模式和链上行为。

Our intuition tells us that each of these clusters of addresses generally belongs to certain types of entities.

直觉告诉我们，这每一个地址簇一般属于某种类型的实体。

Based on the patterns we saw, we made some inferences of specific entities that could be represented by these clusterings:

根据这些我们看到的模式，我们对具体的实体作出一些推论，这些实体可以用三类簇来表示：

* Exchange-related addresses: Centralized cryptocurrency exchanges that generally have thousands of “hot wallets” that are used interchangeably to manage exchange operations and customer transactions. 
* 和交易所相关的地址：中心化的加密货币交易所通常拥有上千个“热钱包”，这些钱包被相互代替使用，来管理兑换操作和客户的交易。
* “Bot” and “Burner” Addresses: Addresses that either display an “automated” transaction pattern — such as repetitive, similar transactions to and from the same recipient— or are clearly one-time-use “burner” addresses that only ever have one incoming and outgoing transaction.
* “机器人“和“用后即焚”地址：要么显示一个“自动的”交易模式，比如重复的、相似的发送和接收地址都相同的交易，要么明显就是一个一次性使用的“用后即焚”地址，它只有一个进入的和出去的交易。
* Human-operated or “other” addresses: A catch-all bucket of addresses that generally display more irregular transaction patterns and show more variance in on-chain transactional relationships — hinting at an actual human being behind the address in question.
* 人为实际操作的或“其它的”地址：一个笼统的地址，通常显示更多不正常的交易模式，显示链上交易关系中更多不同的情况，暗示了与这个地址相关联的某个人。

#### What Does This Enable? 这有什么作用？

Typically, the performance of traditional internet companies is measured by web analytics and user demographics that serve as benchmarks for how well a website is doing compared to its peers.

一般来说，传统互联网公司的表现通过web分析和用户统计来评估，这些分析数据用作评判一个网站与其它网站相比较的基准依据。

When it comes to the world of crypto, aggregating addresses and classifying them into distinct entity types enables similarly nuanced analysis into the makeup of a given cryptoasset’s ecosystem.

说到加密货币领域，对地址进行统计并分类成不同的实体类型能够做到把相似的细微分析作为一个特定的加密货币资产的生态系统的组成部分。

For example, we can get a better picture of network strength by analyzing whether a given token is actually being utilized for its intended use-case by humans or simply being speculated on by a large botnet.

例如，通过分析一个指定的代币是否实际上用于它的预期用例，或者只是被一大批机器人投机而用，我们能够更好地认清网络力量。

This could prove especially useful for “apples-to-apples” comparisons between decentralized applications (dApps) within the same “category”. For example, one could make a comparison between prediction market tokens Gnosis and Augur, or on a lighter note, between ‘digital collectable’ games such as CryptoKitties and CryptoFighters.

这可能对在相同“类别”下去中心化应用之间的同类比较证实尤其有用。例如，我们可以在预测市场代币Gnosis和Augur之间进行比较，或者轻量级的层面，在收集类游戏如“加密猫”和“加密斗士”之间的比较。

When we drill down into address transaction patterns and are able to loosely (or specifically) identify distinct entities like the token team, exchanges, or “whales” (individual entities transacting with large sums of money on-chain), we are also able to get a view of how centralized a token’s ownership is.

当我们提取这些数据形成地址交易模式，能够大概地识别出具体的实体时，如发行代币的团队，交易所、或者“大鲸”（那些使用大额资金在链上交易的个人实体），我们也能够一窥代币的所有者是多么的中心化。


You can see above that the token team and “whale” addresses hold significant amounts of the token in question. This could potentially mean significant price volatility if a few key players decided to liquidate their position.

从上面图中，你可以看到代币团队和“大鲸”地址持有相当多数量的代币。这可能意味着，如果一些重要玩家决定清算他们的资产，将会产生非常大的价格波动。

#### Nuanced Interpretation Required 需要细微的解释

While diving deeper into on-chain data to better understand cryptoasset usage is surely an exciting challenge, it is useful to caveat a few of the points made above to illustrate the nuances involved with accurately interpreting and analyzing this data:

尽管对链上数据更多地挖掘能够更好地理解加密货币资产使用情况肯定是一个令人兴趣的挑战，但是以上的一些注意事项能够用来说明在准确解释和分析数据时需要考虑到一些细微差异。

* Currently, it is unfeasible to know for certain whether a given address is a specific type of entity or not. The best we can do right now is arrive at a reasonable heuristic. However, even general estimates of users can lead to useful insights that allow you better evaluate and compare cryptoassets.

* 当前，确切地知道一个指定的地址是否是某种特定的实体还不可行。我们能做的就是达成一个合理的探索。可是，甚至对用户的一般评估也能够得出有用的见解，让你更好地评判和比较加密货币资产。

* On-chain transaction volumes and counts can sometimes be misleading when taken at face value as any individual entity (a human, an exchange, etc) can own multiple addresses. Thus a lot of on-chain activity may simply be the shuffling of tokens within a given individual’s own set of addresses.

* 当任意一个个体可以拥有多个地址时，只从表面价值来看的话，链上交易规模和数量有时候可能会误导。因此，许多链上活动可能只是在一个指定个体的自己的地址集合内代币的来回变换。

* A lot of exchange trading volume is often not reflected on-chain. Many exchanges, for example, internally debit or credit client wallets without actually invoking a transaction on the blockchain.

* 许多交易所交易规模没有经常被反映在链上。比如，很多交易所只是内部把款项记在客户钱包里或者从客户钱包上记上借贷方，实际上没有在区块链上有过任何交易。

* We believe on-chain data is a main dish that’s part of a bigger data buffet that one should consume when fundamentally evaluating cryptoassets.Off-chain data on protocol differences (PoWor PoS), token supply structures, token types, and token category should be taken into account to provide context to on-chain data on a given cryptoasset.

* 我们认为链上数据是重要一环，它是人们在对加密货币资产进行基本评估时应该利用的数据池的一部分。关于协议差异（PoW 还是 PoS）、代币供应设计、代币类型以及代币种类等链下数据都应该有所考虑，用来为链上数据的分析提供背景资料。

***

区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号：w1791520555。

[点击查看 GITHUB 及更多的译文](https://github.com/BlockchainTranslator/EOS)

本文译者介绍

Chuan，区块链技术爱好者。欢迎加我的微信：youyuxiaochuan

译文版权所有，转载需完整注明以上内容。


