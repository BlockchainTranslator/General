

> 本文翻译自：https://media.consensys.net/state-of-decentralized-exchanges-2018-276dad340c79
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator) [鱼](https://github.com/oscnet)
>
> 翻译时间：2018-2-8
>

 本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。


## State of Decentralized Exchanges, 2018
## 2018 去中心化交易所展望

VariabL CCO Nathan Sexer undertakes an exhaustive study of current DEX tech and looks towards the (near) future of digital asset exchange.

VariabL CCO Nathan Sexer 详尽地研究了当前的 DEX （去中心化交易所）技术，并展望了数字资产交易的（近期）未来的发展。

![](https://cdn-images-1.medium.com/max/2000/1*lLWmbEQBykNZNoIdmu1jWA.jpeg)

Cryptocurrencies and decentralized technologies are booming. The numbers speak for themselves — market capitalizations have gone through the roof, transaction volume has skyrocketed, and adoption from individuals, corporations, and governments has reached a global scale.

Thanks to blockchain technology, we are moving toward a trustless economy, with no need of third parties to exchange goods. Yet today’s digital currency exchanges are centralized. They have proven to be vulnerable to hacks, to react poorly to unusual blockchain events like hard forks, and often run with a high regulatory risk. Centralized exchanges keep their systems off-chain, meaning they operate as escrows for their clients, and transactions are not recorded the blockchain. This leads to massive breaches of security and unsafe storage of information, funds, and private keys.

加密货币和去中心化技术正在蓬勃发展。市值的飙升，交易量的猛增，这些数据说明了一切。加密货币和去中心化技术在个人、企业和政府中的应用已经在全球范围内得到了发展。

借助区块链技术，我们正在向无需信任的经济方向发展，货物交易不再需要通过第三方。但今天的数字货币交易是还是中心化的。事实证明，中心化交易所很容易受到黑客的攻击，而且对诸如硬分叉等不常见的区块链事件疲于应对，还经常面临严重的监管风险。中心化交易所的系统在链下运行，意味着他们要为客户代管资金，交易也不记录在区块链中。导致了大量的安全漏洞，及对资金和私钥的信息存储的不安全性。

 **Trading comes with risks, but traders should not face any other risks than those they are already willing to take.**

Blockchain entrepreneurs understand this, and some of them are working hard on what many believe will be the future of trading: decentralized exchanges.

Decentralized exchanges — or DEXes — aim to tackle the problems that impede centralized structures by building peer-to-peer marketplaces directly on the blockchain — Ethereum mostly — allowing traders to remain custodian of their funds. However, building a fully decentralized and efficient exchange remains today something of a utopia. Exchanges are centralized because it is the simplest way to proceed, and it is either too costly or technically complex to build fully decentralized platforms — for now, at least.

**交易都有风险，但除了他们已经愿意承担的风险外，交易者不该再承担任何其它的风险。**

区块链企业家们清楚这一点，所以其中一些人正在努力研究去中心化交易所，很多人认为去中心化交易就是未来。

去中心化交易所（DEXes）旨在通过在区块链上（主要是以太坊）直接建立点对点的市场来解决中心化交易的问题 - 这将允许交易者继续管理资金。然而，建立一个完全去中心化和有效的交易所现在依然是一个乌托邦。采用中心化的交易所的主要原因是它是最简单的。而要建立完全去中心化的平台，则要么是太昂贵，要么技术上非常复杂，至少在现在来看是这样。

Throwbacks and inefficiencies struggle to create advantages. Many semi-decentralized exchanges are coming into action. They are hybrid models between centralized and decentralized marketplaces, trying to meld the best of both worlds. There is an increasing number of such exhanges, following up on a need expressed by the crypto-community.

This “state of decentralized exchanges” begins with major cryptocurrency numbers and centralized exchanges, which currently monopolize the market. Decentralized exchanges are building the future of cryptocurrencies trading, and this “state” aims to pave its way with its rough listing of projects in the making. We should pay them attention as they are shaping the way cryptocurrencies trading will operate tomorrow.

针对倒退和低效率的努力正在创造优势。许多半中心化的交易所开始实施。他们是在中心化和去中心化市场之间的混合模式，试图将中心化和去中心化的优点融合。随着密码社区的表现出的更多需求，越来越多的这样的交易所出现了。

这篇“去中心化交易的状况”的文章从主要的加密货币用户及当前垄断市场的中心化交易所开始讲起的。去中心化交易正在构建加密货币交易的未来，文章目的是为正在发展中尚显粗糙的项目铺平道路。我们应该关注它，因为它正在塑造明天加密货币交易的方式。

Disclaimer: I am part of [VariabL](https://variabl.io/) (a derivatives trading platform on Ethereum) and [Consensys](https://new.consensys.net/) (one of the largest global blockchain specialists).

免责声明：我是 [VariabL](https://variabl.io/)（以太坊衍生品交易平台）和 [Consensys](https://new.consensys.net/)（全球最大的区块链专家之一）的一员。

### I. Cryptocurrency Market Overview and the Flaws of Centralized Exchanges

#### 2017 Cryptocurrency market in numbers¹ :
+3400%*=Market cap of cryptocurrencies is experiencing an exponential growth:

From less than $18B to more than $600B in 2017.

### I. 加密货币市场概述及中心化交易所的缺陷
#### 2017年加密货币市场数字¹：
+3400％*=加密货币的市值正在呈指数级增长：

2017年从不到 180 亿美元发展到 600 多亿美元。

![](https://cdn-images-1.medium.com/max/1200/0*XUG1A-gSqcbkOh4_.)
Source: https://coinmarketcap.com

x240=Amount of transactions performed on the crypto market per day (Comparing 1st Jan’ 2017 and 1st Jan’ 2018): Around $130M exchanged a day to more than $30B.

240倍=每天加密市场的交易量（比较2017年1月1日至2018年1月1日）：每天交易额从大约为1.3亿美元到超过300亿美元。

![](https://cdn-images-1.medium.com/max/1200/0*c3QWZMS1z49pKQd0.)
Source: https://coinmarketcap.com

>170=Number of cryptocurrency exchanges (live, with traffic), growing at an exponential pace + uncountable number of exchange projects.

 More than 99% of cryptocurrency transactions go through centralized exchanges.

> 170=加密货币交易所数量（运行中，并有交易的），以指数速度增长+交易项目数量不计其数。

超过 99％ 的加密货币交易在中心化交易所进行。

### II. Centralized exchanges
Let’s first define what centralized exchanges are: platforms and apps that enable traders to buy, sell and exchange cryptocurrencies against fiat currencies or cryptocurrencies themselves. They are marketplaces for tokens, and are essential to the ecosystem, since many of them enable payments with fiat currencies ie. non-crypto holders to buy crypto with USD,EUR etc.

Among most well-known and trafficked centralized exchanges are Bithumb, Bitfinex, Bittrex, Poloniex, Kraken, GDAX, Coinbase, Gemini. Hundreds already exist, but the goal here is not to focus on their number, but rather on their limitations and potential for improvement.

### II. 中心化交易所
首先，我们来定义什么是中心化交易平台：能够让交易者购买、出售、交换加密货币，通过法定货币或加密货币本身的平台和应用程序。他们是代币市场，是加密货币生态系统不可或缺的一环，他们中很多可以用法定货币进行支付，使得非加密货币持有者可以用美元、欧元等人购买加密货币。

已经有数百家的中心化交易所，比较知名的有 Bithumb、Bitfinex、Bittrex、Poloniex、Kraken、GDAX、Coinbase、Gemini。但我们的目标不是关注他们的数量，而是关注他们的局限性和改进的潜力。

 Centralized crypto-exchanges may soon become obsolete as they lose the opportunity to leverage blockchain technology to improve their capabilities and efficiency.

 中心化的加密货币交易可能很快就会过时，因为他们失去了利用区块链技术来提高能力和效率的机会。

Localethereum’s official blog² has made a great overview of centralized exchanges³, laying out various hacks and summing up the main problems linked to these platforms that include:

* **Insecurity**, risk of loss and thefts due to their centralized functioning. They are legally accountable and a custodian of users’ funds. 73% of exchanges take custody of user funds, while 23% let users control keys⁴. They represent honeypots for hackers as they are responsible for billions of trades per day and store most of them on their servers.
* A lack of **liquidity**: large orders struggle to be matched. Even at an all-time-high, volumes remain low (compared to traditional markets)
* A **fragmented** (not to say decentralized) market: divides the global liquidity into few main marketplaces. No clear market leader in terms of volumes. Increases the liquidity problem.

Localethereum 的官方博客²对中心化交易所³进行了很好的概述³，列举了各种骇客攻击并总结了与这些平台相关的主要问题，包括：

* **不安全**，由于中心化运作，有损失和被盗的风险。他们具有法律责任，是用户资金的保管人。有 73％ 的交易所保管用户资金，而有 23％ 让用户自己控制密钥⁴。他们是黑客的蜜罐，因为他们每天有数十亿的交易额，并将大部分交易存储在他们的服务器上。
* 缺乏**流动性**：大额订单难以匹配。即使是在历史最高点，交易量仍然较低（与传统市场相比）
* 一个**支离破碎**的（不是说去中心化）市场：将全球的流动性划分到一些个主要交易市场中。使得在成交量方面没有明确的市场领导者。增加了流动性问题。

![](https://cdn-images-1.medium.com/max/1600/0*CR3Deg2hNqcZWHBh.)
Source: “State of Blockchain — Q3 2017"by Coindesk

* A high level of **risks** for users due to potential performance issues, market manipulation, hardware failures, latency problems and many other inherent problems when it comes to dealing with large volumes…
* A lack of trust and **transparency**: actual costs and processes of trading are opaque and involve high trading costs, often higher than announced fees and higher delays due to peaks of demand badly managed. Plus, they can front-run orders, which is as illegal as doable.
* A lack of **educated** users: markets are flowed by pure speculators unaware of safe ways to deal with cryptocurrencies

* **高风险**，由于潜在的性能问题，市场操纵，硬件故障，延迟问题以及处理大量问题时的许多其他固有问题，用户面临高风险。
* 缺乏信任和**透明度**：实际的交易成本和过程是不透明的，涉及高昂的交易成本，通常高于公布的交易费用，和需求管理不善造成的高峰延迟。另外，他们还可以前置订单（详见[Front Running](https://www.investopedia.com/terms/f/frontrunning.asp),译者注），而这是违法的。
* 缺乏**受过教育的用户**：市场上充斥着纯粹的投机者，他们不知道如何用安全的方式来处理加密货币。

### III. Decentralized exchanges and open protocols
Due to the lack of security, transparency, and efficiency that centralized exchanges have demonstrated, a strong demand for decentralized exchanges have surfaced. Scores of new actors are tackling these problems and addressing an obvious need by the community. Projects like 0x, Ethfinex, [ShapeShift.io](https://medium.com/@ShapeShift.io) (not decentralized but not custodian) and EtherDelta have emerged and generated a strong interest.

“[Decentralized exchanges promises two major benefits: Security & control and global marketplace](https://blog.airswap.io/airswap-and-novogratz-partner-to-provide-liquidity-on-decentralized-exchanges-d16518b440dd)” by [Michael Oved](https://medium.com/@ovedm606) (founder of [AirSwap Team](https://medium.com/@airswap), a [ConsenSys](https://medium.com/@ConsenSys) Spoke)

One of the oldest projects in the field is EtherDelta, a platform with a simple user-interface and basic trading features (no margin trading), which has already gained sufficient traction to generate up to 25 million USD-equivalent of daily transactions⁵.

### III. 去中心化交易和开放协议
由于中心化交易所缺乏安全性、透明度和效率，对去中心化交易的强烈需求已经浮出水面。许多新的参与者正在处理这些问题来解决社区的明显需求。像 0x、Ethfinex、[ShapeShift.io](https://medium.com/@ShapeShift.io)（不是去中心化的但它不管理用户资金）和 EtherDelta 等项目已经出现并引起了人们强烈的兴趣。

“ [去中心化交易有望两大好处：安全、控制和全球市场]((https://blog.airswap.io/airswap-and-novogratz-partner-to-provide-liquidity-on-decentralized-exchanges-d16518b440dd)) ”，
by [Michael Oved](https://medium.com/@ovedm606) ([AirSwap Team](https://medium.com/@airswap) 创始人在  [ConsenSys](https://medium.com/@ConsenSys) 上的讲话)

该领域历史最悠久的项目之一是 EtherDelta，它是一个具有简单的用户界面和基本交易功能（无保证金交易）的平台，已经获得足够的用户吸引力，日常交易量高达 2500 万美元。

#### Definition
Decentralized exchange differ from centralized exchanges as they enable users to remain in control of their funds by operating their critical functions on the blockchain: they leverage the technology behind cryptocurrencies themselves to enable a safer and more transparent trading. It solves the main limitations faced by cryptocurrency markets (see above), since there is no single point of failure, aligning them with what has made the blockchain technology so powerful in the first place.

Most decentralized exchanges are not fully decentralized, but semi-decentralized (full decentralization is today more of an ideal, due to limitations listed hereunder). In most cases, servers (centralized) still host order books (among other features) but **do not hold private keys**.

Another central aspect is that decentralized exchanges present the characteristics, benefits and limitations, of their underlying blockchain.

#### 定义
去中心化交易与中心化交易所有所不同，通过在区块链上操作的关键功能，用户能够自己控制资金：它们利用加密货币本身背后的技术来实现更安全和更透明的交易。它解决了加密货币市场面临的主要限制（见上文），因为不会产生单点故障，而这也是区块链技术如此强大的原因。

大多数去中以化交易所并不是完全去中心化的，而是半去中心化的（由于下面列出的限制，完全的去中心化交易所现在还只是一个理想）。在大多数情况下，服务器（中心化的）仍然保存着订单簿（和其他功能），但**不包含私钥**。

另一个核心方面是去中心化交易所揭露了底层区块链的特点、优势和局限性。

#### Main DEX Benefits
Trustless, which means that users’ funds and personal data are safe.
Security and privacy are well preserved.
#### Main DEX Limitations
Maintain the same scalability problems as the underlying blockchain.
Most are not easily usable, struggle with liquidity, do not provide fiat payments etc.
(more details in a section below)

#### 去中心化交易的主要好处
无信任，这意味着用户的资金和个人资料是安全的。
具有完好的安全和隐私性。
#### 去中心化交易主要限制
跟底层区块链一样，具有可扩展性问题。
大多数不易使用，流动性不足，无法使用法定货币付款等。
（更多细节在下面的部分）

### Decentralized Exchange mapping:
#### Disclaimers:
This “state of decentralized exchanges” may not be fully exhaustive and did not assess all of those projects’ viability nor teams’ legitimacy. However, an effort has been made towards making an exhaustive mapping. Abandoned or scammy projects might be included. It should be taken with a grain of salt and you should conduct your own due diligence before using or investing in any of those.

### 去中心化交易项目一览表
#### 免责声明：
这个去中心化交易项目列表可能并不详尽，也没有评估所有这些项目的可行性和团队的合法性。然而，虽然已经努力做了一个详尽的列表。但也有可能会包括已放弃或可疑的项目。在使用或投资任何一个项目之前，你应该对其进行尽职调查。

1. All the projects below are or contain decentralized exchanges functionalities in their global offers. Many are not limited to exchange services. For the sake of that study, and since there are not (m)any fully decentralized and working exchanges, semi-decentralized exchange will be included.
2. Some exchanges offering advanced financial products such as futures or derivatives like dYdX or VariabL are voluntarily excluded of this benchmark since there is another article in the making for these ones.
3. The vast majority is in production/beta; this report aims to list all of them and assess their current state of development. I included their website and Medium accounts when available, which provide most of projects’ updates.

----

1. 以下所有项目都提供了去中心化交易功能。许多不限于交易服务。这了研究方便，而且由于没有任何完全去中心化且正常运行的交易所，所以半去中心化的交易也将被包括在内。
2. 一些提供高级金融产品，如 dYdX 或 VariabL 等衍生品的交易所自愿被排​​除在这个名单外，因为对于这些另有文章正在写作。
3. 绝大多数尚在开发/测试阶段; 本报告旨在列出所有这些项目并评估其目前的发展状况。如果有的话，我提供了项目的网址和 Medium 帐号，以方便可以看到大部分项目的更新情况。

#### [AirSwap](https://www.airswap.io/) ([AirSwap Team](https://medium.com/@airswap))
P2P decentralized exchange on Ethereum using the Swap protocol (Live on February 1st 2018!)

以太坊上使用 Swap 协议的 P2P 去中心化交易所（2018年2月1日运行！）

#### [Altcoin.io](https://t.co/nArlI91TPP) ([Altcoin.io Exchange](https://medium.com/@altcoin.io))
Decentralized cryptocurrency exchange, powered by Atomic Swaps (Beta on testnet)

基于原子交换的去中心化加密货币兑换（Beta on testnet）

#### [Barterdex](https://barterdex.supernet.org/) (by [Komodo Platform](https://medium.com/@komodoplatform))
Open source decentralized network doing atomic swaps (in production)

开源的去中心化网络用于原子交换（开发中）

#### [Bancor Protocol](https://www.bancor.network/) ([Bancor](https://medium.com/@bancor))
Smart contract based token exchange protocol (Live on the Ethereum MainNet)

基于智能合同的令牌交换协议（以太坊主网运行）

#### [Bisq](https://bisq.network/) (ex Bitsquare)
Crypto-fiat open-source exchange with a desktop application working via Tor to trade Bitcoins (Live)

Crypto-fiat 开放源代码交易，使用 Tor 交易比特币的桌面应用（运行中）

#### [Blocknet](https://blocknet.co/) ([Blocknet Team](https://medium.com/@theblocknet))
Decentralized exchange enabling cryptocurrencies trading and fiat currency gateways through cross-chain atomic swaps and cross-chain data transfers (In production)

支持加密货币交易和法定货币网关通过交叉链式原子互换和交叉链式数据传输的去中心化交易所（开发中）

#### [Coinffeine](http://www.coinffeine.com/):
Decentralized Bitcoin exchange with a “Zero Trust” exchange algorithm (Down)

“零信任”交换算法的去中心化比特币交易所（已关闭）

#### [Catalyst](https://enigmampc.github.io/catalyst/index.html) (by [Enigma Project](https://medium.com/@EnigmaMPC))
Investment platform for algorithmic/data-driven trading on crypto-assets without a custodian (in alpha; simulation available)

在没有托管人的情况下，进行算法/数据驱动的加密资产交易的投资平台（alpha，可用于模拟）

#### [Etherdelta](https://etherdelta.com/)
The cryptocurrencies fully decentralized exchange market leader for ERC-20 tokens (Live)

完全去中心化的交易所， ERC-20 代币交易市场的领导者（远行中）

#### [Etherex](http://etherex.github.io/etherex)
Open-source decentralized exchange built on Ethereum (last update on April 2016)

建立在以太坊上的开源去中心化交易所（最后更新2016年4月）

#### [Forkdelta](https://forkdelta.github.io/)
Community-driven open source and forked version of Etherdelta, uses the same orderbook and contract (Live on the Ethereum MainNet)

社区驱动的开源项目，Etherdelta 以德分叉版本，使用 Etherdelta 相同的订单和合同（运行在以太坊 MainNet 上）

#### [Gnosis Dutch Exchange](https://blog.gnosis.pm/introducing-the-gnosis-dutch-exchange-53bd3d51f9b2) (by [Gnosis](https://medium.com/@gnosis.pm))
Decentralized exchange for ERC-20 tokens based on the Dutch auction principle (in production)

根据荷兰拍卖原则的去中心化 ERC-20 代币交易（开发中）

#### [Heat](https://heatwallet.com/)
Real-time asset-to-asset decentralized exchange (MainNet)

实时资产到资产去中心化交易（MainNet）

#### [Herdius](https://herdius.com/) ([Herdius](https://medium.com/@herdiusofficial))
Decentralized exchange focused on scalability and cross-chain interoperability (ICO expected in Q1’2018)

侧重于可扩展性和交叉链互操作性的去中心化交易（预计在 2018 年第一季度 ICO）

#### [Hodl Hodl](https://testnet.hodlhodl.com/) ([Hodl Hodl](https://medium.com/@hodlhodl))
P2P cryptocurrency exchange on the Bitcoin Testnet (Testnet)

比特币测试网（Testnet）上的 P2P 加密货币交易

#### [IDEX](https://idex.market/)
Decentralized exchange that provides instant order placement and execution, free order cancellation, and real-time order book updates. (Live on the Ethereum MainNet)

提供即时下单和执行，免费订单取消和实时订单更新的去中心化交易。（运行在以太坊 MainNet）

#### [KyberNetwork](https://kyber.network/) (by [Loi Luu](https://medium.com/@loiluu))
Decentralized exchange and conversion of digital assets, api for payments and derivatives (Demo on Ropsten)

数字资产的去中心化交换和转换，为支付和衍生产品提供了 api （在 Ropsten 上有演示）

#### [Legolas](https://legolas.exchange/)
Hybrid centralized/decentralized exchange targeting market makers (In production, ICO Q1’2018)

针对做市商的混合中心化/去中心化交易所（开发中，ICO 2018年 Q1）

#### [Loopring](https://loopring.org/) (by [Daniel Wang](https://medium.com/@loopring))
Decentralized Exchange for ERC20 and Open Protocol to serve multiple public blockchains (in production)

ERC20 的去中心化交易所，使用开放协议来服务多个公共链（开发中）

#### [Lykke](https://www.lykke.com/):
Semi-decentralized exchange for cryptocurrencies and fiats (live, with a centralized model. Will switch to decentralized model in the future)

加密货币和法定货币的半去中心化交易（目前采用中心化的模式，未来将转向去中心化模式）

#### [Mothership](https://mothership.cx/)
Decentralized exchange (in production, ICO raised)

去中心化交易系统（开发中，ICO ）

#### [NEX](https://neonexchange.org/)
Decentralized exchange on NEO with an off-chain matching engine including payment services. (in production, trading platform launch expected in Q3’2018)

NEO 的去中心化交易系统，包括支付服务的外链匹配引擎。（交易平台预计将于二零一八年第三季度运行，开发中）

#### [Next.exchange](https://next.exchange/)
Decentralized exchange focused on ICOs with Crypto-pools and community trading (in production, launch expected in January 2018)

去中心化交易所，关注于 Crypto-pools 密码池和社区交易的 ICO （预计于2018年1月运行，开发中）

#### [Nvo.io](https://nvo.io/)
Cross-platform modular / decentralized exchange using the Safenetwork for orders validation (in production, launch expected Q1’2018)

跨平台模块化/使用安全网络进行订单验证的去中心化交易所（预计将于2017年1月1日运行）

#### [Oasis DEX](https://oasisdex.com/) (by [Makerdao](https://medium.com/@MakerDAO))
Decentralized Token Market — on-chain market for all token assets in the Maker registry (live on MainNet)

去中心化代币市场 - 做市商注册中所有代币资产的链上市场（在 MainNet 上运行）

#### [OmegaOne](https://omega.one/) ([Omega One](https://medium.com/@omega.one))
Decentralized trade execution platform (a Consensys spoke, in production)

去中心化的交易执行平台（Consensy上的讲话，开发中）

#### [OpenANX](https://www.openanx.org/)
Open sourced and governed decentralized exchange (In production)

开源和管理的去中心化交易所（开发中）

#### [Raidex](https://www.raidex.io/)
Decentralized exchange with Raiden off-chain state channel technology (in production)

使用雷电链下状态信道技术的去中心化交易所（在开发中）

#### [SingularX](https://ex.singularx.com/) (by [SingularDTV](https://medium.com/@SingularDTV))
Decentralized peer reviewed trading platform for tokenized intellectual property and ERC-20 tokens (Live Beta)

用于代码化的知识产权和 ERC-20 代币的去中心化的同行审查交易平台（Beta 运行中）

#### [Stellar Distributed Exchange](https://stellarterm.com/) (by [Stellar](https://medium.com/@StellarOrg))
StellarTerm is an open source distributed exchange for the Stellar network. (Live since 2015)

StellarTerm 是 Stellar 网络的开源去中心化交易所。（自2015年以来）

#### [Streamity](https://streamity.org/) ([Streamity](https://medium.com/@streamityorg))
Semi-decentralized cryptocurrency exchange with fiat onramps (In production, ICO Q1’2018)

半去中心化化的加密货币兑换与平台（开发中，2018 第一季度 ICO ）

#### [Token Store](https://token.store/)
Ethereum token exchange built on smart contracts in a semi-decentralized way (Live on the Ethereum MainNet)

以半去中心化方式建立的建立在智能合约上的以太坊代币交易所（运行在以太坊 MainNet 上）

#### [Waves](https://wavesplatform.com/) ([Wavesplatform](https://medium.com/@wavesplatform))
Crypto-platform for asset/custom token issuance, transfer and trading on the Waves blockchain, with centralised order matching and decentralised settlement. (Live since June 2016)

在 Waves 区块链上进行资产/自定义代币发行，转账和交易的密码数字平台，使用集中式订单匹配和去中心化结算。（自2016年6月以来）

#### [Xchainge](https://xchain.io/assets) ([xChainge:](https://medium.com/@xchainge.io))
Decentralized exchanges of crypto-assets (by Counterparty, Open source platform on the Bitcoin blockchain)

数字资产的去中心化交易（Counterparty，比特币区块链上的开源平台）

### Graphene/Bitshares Decentralized Exchanges:
Graphene is an Open Protocol, see more information below.

### 基于石墨烯/比特股的去中心化交易系统:
石墨烯是一个开放协议，请参阅下面的更多信息。

#### [Bitshares](https://bitshares.org/)
Decentralized exchange providing price stable cryptocurrencies and banking services on the blockchain (Live since 2014) [Probably the oldest decentralized exchange sill working]

在区块链上提供价格稳定的加密货币和银行服务的去中心化交易所（自2014年起运行）[可能是正在运行的最古老的去中心化交易所]

#### [Blocktrades](https://blocktrades.us/)
Decentralized exchange acting as counterparty (Live)

以交易对手运作的去中心化交易所（运行中）

#### [BTSABC](https://bit.btsabc.org/)
Decentralized exchange powered by Bitshares and Graphene technology -in Chinese (Beta)

以石墨烯/比特股技术开发的去中心化交易平台 - 中文（Beta）

#### [CryptoBridge](https://crypto-bridge.org/) ([CryptoBridge](https://medium.com/@cryptobridge))
Decentralized cryptocurrency exchange with multi-signature federated gateway network (Live Beta)

使用多重签名联合网关网络的去中心化加密货币交易所 （Beta 试运行）

#### [Cybex](http://dex.cybex.io/) ([Cybex Decentralized Exchange](https://medium.com/@cybexexchange))
Decentralized exchange system based on the Graphene/EOS Blockchains (Beta)

基于石墨烯/EOS 区块链的去中心化交易系统 （Beta）

#### [DEEX Exchange](https://deex.exchange/) ([Deex Ex](https://medium.com/@deexex))
Decentralized exchange with blockchain traded funds and many (Private Beta)

区块链基金交易去中心化交易平台（私人测试）

#### [GDEX](https://www.gdex.io/)
Offers a stack of decentralized financial services including exchange and banking on a blockchain (Live)

在区块链上提供一堆去中心化的金融服务，包括交易和银行功能（运行中）

#### [OpenLedger](https://openledger.io/welcome) ([OpenLedger](https://medium.com/@openledger))
Decentralized exchange powered by Bitshares and Graphene technology (Demo)

由石墨烯/比特股技术支持的去中心化交易系统（演示）

#### [RuDEX](https://rudex.org/)
Decentralized exchange powered by Bitshares and Graphene technology — in Russian (Beta)

采用石墨烯/比特股技术的去中心化交易系统 - 俄文版（Beta版）

#### [0x Relayers](https://0xproject.com/) ([0x](https://medium.com/@0xProject))
0x is an Open Protocol, see definition below and read https://relayer.network for a great explanation of relayers.

0x 是一个开放的协议，见后面的定义，请阅读 https://relayer.network 了解对 relayers 的解释。

#### [Amadeus](http://amadeusrelay.org/)
Relayers for dApps looking for liquidity to exchange ERC20 tokens (in production)

寻找流动性来进行 ERC20 代币交易的去中心化应用中继者（开发中）

#### [DDEX](https://ddex.io/) ([DDEX](https://medium.com/@ddex))
User-Friendly decentralized exchange for ERC20 tokens (on MainNet)

用于 ERC20 代币的用户友好的去中心化交易系统（在 MainNet 上）

#### [Decent Ex](https://decent.exchange/):
Decentralized exchange for Ethereum tokens (on Kovan TestNet)

用于以太代币的去中心化交易系统（在 Kovan TestNet 上运行）

#### [Dextroid](https://www.dextroid.io/)
Low cost trading and user-friendly exchange on the blockchain. (on Kovan TestNet)

低成本的交易和用户友好的区块链交易系统。（在 Kovan TestNet 上运行）

#### [ERC dEX](http://ercdex.com/)
Decentralized Exchange with advanced financial tools, available on mobile (Beta on the Ethereum MainNet)

借助先进的金融工具进行去中心化交易，可在移动设备上使用（以太坊 MainNet 上的测试版）

#### [Ethfinex](https://www.bitfinex.com/ethfinex) ([Ethfinex](https://medium.com/@ethfinex))
Community-driven, decentralized trading platform for ERC20 Tokens (live)

社区驱动的 ERC20 代币去中心化交易平台 （运行中）

#### [IDT Exchange](https://www.idtexchange.com/) (ex [Kin Alpha](https://medium.com/@KinAlpha))
ERC20 decentralized exchange (first relayer to go on the MainNet)

ERC20 去中心化交易系统（ 第一个中继者要上 MainNet ）

#### [Paradex](https://paradex.io/) ([Paradex](https://medium.com/@paradex))
Exchange ERC20 tokens with a centralized matching strategy (beta on the MainNet)

使用集中匹配策略交易 ERC20 代币（在MainNet上测试）

#### [RadarRelay](https://t.co/NIuOBGMF2l) ([Radar Relay](https://medium.com/@RadarRelay))
0x order book to find and trade any ERC20 token. (live on the MainNet)

使用 0x 订单簿来查找和交易任何的 ERC20 代币。（运行在MainNet上）

#### [The Ocean X](https://theoceanx.com/) ([The Ocean X](https://medium.com/@theoceanx))
0x relayer and liquidity pool for trading Ethereum-based token (Beta)

用于以太坊的代币交易的 0x 中继和流动性池 （Beta）


### IV. Open protocols for decentralized exchanges:
#### Definition
Open Protocols are setting up and running decentralized applications (dApps) on a common basis: some are designed especially for decentralized exchanges (ie. 0x), others also seem suited (ie. Omise). Both will be mentioned below.

They create synergies by allowing “anyone” to build their own services on top of them: it fosters innovation and is essential for native dApps to interact with each other. For decentralized exchanges, open protocols present the benefits of creating common pools of liquidity by allowing any project built on top to interact with each others.

### IV. 去中心化交易的开放协议：
#### 定义
开放协议使建立和运行去中心化的应用程序（dApps）基于一个共同的基础上：其中一些专门为去中心化交易而设计（如 0x），另外一些似乎对去中心化交易也适用（如 Omise）。两者将在下面提及。

协议通过允许“任何人”在他们之上建立自己的服务来创造协同作用：它促进创新，并且对应用间的相互交互也是必不可少的。对于去中心化交易，
基于开放协议开发的其它项目，可以使用共同的流动性池并能彼此交互，从而带来流动性的好处。

#### [0x](https://0xproject.com/) ([0x](https://medium.com/@0xProject))
Open protocol for decentralized exchange on the Ethereum blockchain (live with dozens of relayers, dApps on open protocols/projects built)
在以太坊区块链上开放去中心化交易协议（运行中，已有几十个 relayers，及在开放协议/项目上构建的应用）

#### [OpenRelay](https://openrelay.xyz/)
Open source relay for the 0x protocol
0x 协议的开源中继

#### [Lendroid](https://lendroid.com/)
Open Protocol for Decentralized Lending that Enables Margin Trading and Short Selling of ERC20 Tokens
开放去中心化借贷协议，实现保证金交易和卖空 ERC20 代币

#### [Enigma Protocol](https://www.enigma.co/) ([Enigma Project](https://medium.com/@EnigmaMPC))
Decentralized exchange protocol supporting cross-chain atomic swaps, providing an open infrastructure and trading tools
支持交叉链原子交换的去中心化交易协议，提供开放的基础设施和交易工具

#### [Graphene](http://docs.bitshares.eu//index.html) (by @Bitshares)
A software platform for deploying decentralized ledgers. Not specifically developed for decentralized exchanges.
一个部署去中心化账本的软件平台。不是专门为去中心化交易而开发的。

#### [OmiseGo](https://omisego.network/)
Digital Wallets, P2P exchange & Payments (fiats&cryptos) protocol.
数字钱包，P2P 交易和支付（法币和数字货币）协议。

#### [Snowglobe](https://auroradao.com/faq/) (by [Alex Wearn](https://medium.com/@alexwearn), IDEX & Aurora DAO)
Fully-decentralized exchange protocol; designed for high-performance, EVM-compatible, decentralized childchain exchanges
完全的去中心化交易协议; 专为高性能 EVM 兼容的去中心化子链交换而设计

#### [Swap Protocol](https://swap.tech/faq/) (by [AirSwap Team](https://medium.com/@airswap))
Peer-to-peer protocol for trading Ethereum tokens, without orderbooks (to be open in the future)
用于交易以太坊代币的对等协议，没有订单（将来开放）


### V. What May Slow Down the Adoption of Decentralized Exchanges?
Security benefits, by allowing users to remain custodian of their funds, seem obvious and emphasized by all these hacks stories. So why everyone is not using them?

Some aspects are slowing down their adoption: Education and Technology.

### V. 影响去中心化交易的因素？
去中心化交易让用户保持资金的管理，这带来的安全的好处是很明显的，还有那些黑客故事都充分说明了这一点。那么为什么大家还不使用去中心化交易呢？

一些因素影响了去中心化交易的采用：教育程度和技术。

#### Education
Users are not aware of:
* **Drawbacks** and security issues of Centralized Exchanges
* **Security** measures to undertake (how to manage private keys etc.) since it is users’ responsibility
* **Existence** of Decentralized Exchanges
* **Advantages** of Decentralized Exchanges

#### 教育
用户不知道：

* 中心化交易所的**缺点**和安全问题
* 承诺的**安全**措施（如何管理私钥等），因为它是用户的责任
* 去中心化交易的**存在**
* 去中心化交易的**优势**

#### Technology
* **Usability**: DEX are not user-friendly enough (very solvable problem, linked to early stages of projects)
* **Scalability**: Possible blockchain bloat with ethereum network congestion and scaling pressure (with Token sales and a slow gas price adaptation…)
* **Speed**: Transactions take time to be validated on blockchains
* **Cost**: There is a potential high costs per trade
* **Liquidity**: Chicken and the egg problem. Traders do not join because traders are not already on the platform to match their orders; getting liquidity through a large adoption by the ecosystem is a long process.
* **Full decentralization**: Some services have to remain off-chain and have to suffer from limitations of centralized infrastructures (ie. onchain orderbook are expensive not efficient enough)
* **Front-running risk**: miners can preview transactions, since they validate them, and can have consequences on any DEX (market manipulation)
* **Interoperability**: need for cross-chain exchanges, and more blockchains/dapps interoperability for decentralized platforms to interact with each others.
* **Accessibility**: Need for fiat integrations and stable tokens for lower volatility.

#### 技术
* **可用性**：去中心化交易不够用户友好（这是个可解决的问题，与项目正处于早期阶段有关）
* **可扩展性**：以太网阻塞和扩展性压力（代币销售和缓慢的 gas 价格适应...）
* **速度**：交易需要花时间在区块链上进行验证
* **成本**：每笔交易都有潜在的高成本
* **流动性**：鸡和蛋的问题。交易者不愿意使用去中心化交易，是因为在此类平台上他们的订单不容易成交; 通过生态系统的大量使用来获得流动性是一个漫长的过程。
* **完全去中心化**：一些服务必须在链下提供，并且必须受到中心化的基础设施的限制（如，链上订单昂贵且不够高效）
* **Front-running 风险**：矿工可以预先查看交易，因为是由他们来验证交易的，有可能对任何去中心化交易产生影响（市场操纵）
* **互操作性**：需要跨链交换，以及更多的区块链/dapps 应用的互操作性，使得去中心化平台能够彼此交互。
* **可访问性**：需要集成法币和稳定币来降低波动性。

On the matter, Kyber’s chief executive and co-founder, Loi Luu stated:

“centralized exchanges are potentially unable to handle large volumes of users, touting decentralized trading platforms as a better alternative. However, decentralized exchanges are not as user-friendly as centralized options, and may not have the funds to support mass trading due to small numbers of users.”⁶

对此，Kyber 首席执行官兼共同创始人 Loi Luu表示：

“ 中心化的交易可能无法处理大量用户，去中心化的交易平台是更好的选择。但是，去中心化交易并不像中心化交易所那么用户友好方便，而且可能没有资金支持少量用户的大规模交易。“⁶

### Conclusion
99% of cryptocurrency transactions still go through centralized exchanges; this trend is expected to be reversed in the coming years. Switching to decentralized exchanges is necessary for cryptocurrency users to exploit their full potential, aligning with the decentralized nature of blockchain itself. Education is arriving, and most technological hurdles we face today will probably be overcome very soon.

Differences between projects’ value propositions are hard to spot in this field, and most of them will probably not exist in a close future. However, the trend towards decentralized exchanges is clearly evident.

Centralized exchanges will shift toward decentralized technologies sooner rather than later, but improvements have to come from both sides. Users to learn how to protect themselves, and platforms must provide better security tools, as well as education around common issues and best practices.

### 结论
99％ 的加密货币交易仍然通过中心化交易; 这一趋势预计将在未来几年内扭转。切换到去中心化交易是加密货币用户充分利用其潜力的必要条件，符合区块链本身的去中心化性。通过培养和训练，我们今天面临的大多数技术障碍很快就会被克服。

在这个领域，项目价值之间的差异是很难发现的。其中大部分可能会在不远的将来消失。然而，去中心化交易的趋势是显而易见的。

中心化交易将尽早转向去中心化化的技术，但是双方都必须进行改进。用户学习如何保护自己，平台必须提供更好的安全工具，以及针对常见问题和最佳实践的教育。

“Ultimately, I believe that centralized and decentralized exchanges will co-exist as they each provide their own unique benefits,” says Linda Xie, who sums up the situation pretty well (talking about 0x). Will Warren (0x Co-Founder) goes even one step further by stating that “centralized exchanges will continue to play a critical role in the cryptocurrency ecosystem, because they offer fiat on/off-ramps.” This is one function that fully decentralized exchanges, by definition, do not allow.

If some factors are slowing down adoption, the above-mentioned open protocols (for decentralized exchanges) are fostering development by lowering entry barriers to their implementation and adoption. 0x is probably among the best projects working on the matter. However, even the 0x protocol may suffer from problems like efficiency and scalability, which still represent massive hurdles for the whole blockchain, Ethereum and exchange ecosystem. Solutions in the making, such as State Channels, or Sharding/Plasma, will allow scaling, albeit with certain sacrifices.

“最终，我相信中心化和去中心化的交易将会共存，因为它们各自都有各自独特的好处，” Linda Xie 说，她很好地总结了这个情况(在谈到 0x 时)。Will Warren ( 0x 联合创始人)更进一步说，“中心化的交易所将继续在加密货币的生态系统中发挥关键作用，因为他们提供了与法币互换的通道。” 这是一个完全去中心化的交易所，根据定义，不允许的功能。

虽然一些因素正在影响去中心化交易的采用，但上述（去中心化交易的）开放协议正在通过降低实施和采用的进入壁垒来促进发展。0x 可能是在这个问题上最好的项目之一。然而，即使是 0x 协议也可能会遇到效率和可扩展性等问题，这对整个区块链，以太坊和交易系统来说仍然是一个巨大的障碍。尽管有一定的取舍，如 State Channels 状态通道，或分片/Plasma 解决方案，将解决可扩展性问题。


From a wider perspective, decentralized exchange adoption will follow the adoption of the (Ethereum) blockchain itself, alongside better educated users and technological breakthroughs. As mentioned, centralized/decentralized hybrid models will most likely get their break first. Fully decentralized exchanges remain an ideal, towards which most of those projects are aiming.

Some questions remain: does everyone want to take care of their own private keys? Probably not, but they should at least have the choice. Friction for new users switching from centralized exchanges to decentralized ones also remain a big hurdle; even the process of switching represents a considerable effort for most users…

从更广泛的角度来看，去中心化交易所的采用将遵循（以太坊）区块链本身的采用，以及更好的受过教育的用户和技术突破。如前所述，中心化/去中心化混合动力模型最有可能首先得到突破。完全去中心化的交易仍然是一个理想，大多数这些项目都瞄准了这个理想。

还有一些问题：每个人都想自己保存私钥吗？可能不会，但他们至少应该有选择。从中心化交易到去中心化交易的新用户的磨合也是一个很大的障碍，切换的过程对于大多数用户来说也是需要相当大的努力。


![](https://cdn-images-1.medium.com/max/1200/0*lr8tQ9eU8VrymT6m.)

Is the switch is going to happen any time soon? People like [Vinny Lingham](https://medium.com/@vinnylingham)(Civic) say that some centralized exchanges will soon close, and think this will accelerate the adoption of decentralized exchanges.

If the causes and triggers are matters of debate, we can hardly argue that decentralized exchanges are and will continue to grow as a hot topic of 2018 and potentially an essential pillar of the blockchain ecosystem.

这种转换是否会很快发生？[Vinny Lingham](https://medium.com/@vinnylingham) ( Civic ) 说，一些中心化交易会很快关闭，并认为这将大大加速采用去中心化交易的进程。

如果动机和诱因是争论的焦点，我们就很难说作为 2018 年的热门话题，去中心化交易现在将增长，并将会继续增长，这可能是区块链生态系统的重要支柱。

**If a project is not or should not be listed above, contact me and I will make sure to add/remove it. Feel free to suggest any modification!*

Special thanks to [Will Warren](https://medium.com/u/2b16f05dc65e) (0x), [Michael Oved](https://medium.com/u/27f3f1fdb061) (AirSwap), Jemayel Khawaja (Consensys) and my team ([VariabL](https://medium.com/u/9af0ea6e5ab0)) for their time and support on making this article a reality.

**如果项目不适合或不应该在上面列出，请联系我，我会确保添加或删除它。随意建议任何修改！*

特别感谢 Will Warren（0x），Michael Oved（AirSwap），Jemayel Khawaja（Consensys）和我的团队（VariabL），感谢他们的时间和支持使本文成为现实。

Footnotes: | 脚注

1. https://coinmarketcap.com
2. https://localethereum.com/ belongs to another type of cryptocurrencies marketplaces not mentioned here but also trending: local P2P token market places. Other examples: https://localbitcoins.com/fr/ or Dether
3. https://blog.localethereum.com/centralised-exchanges-are-terrible-at-holding-your-money/. More hack stories hacks stories: https://bitcointalk.org/index.php?topic=576337
4. “GLOBAL CRYPTOCURRENCY BENCHMARKING STUDY” Dr Garrick Hileman & Michel Rauchs (2017)
5. https://coinmarketcap.com/exchanges/etherdelta/
6. Loi Luu (Kyber Network): https://www.coindesk.com/uc-berkeley-kybernetwork-partner-for-decentralized-exchange-research/


----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/General)

#### 本文译者简介

鱼 区块链技术爱好者，欢迎加微信号交流：**oscnet**

本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。

版权所有，转载需完整注明以上内容。

----------------------------------------------------
