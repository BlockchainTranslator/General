# Understanding Token Velocity
# 理解代币速度

> 本文翻译自：https://docs.google.com/document/d/1-ix9BDmGie8tPAwrfRKqe9CNUDnakmiwoh7tHfXeV9g/mobilebasic
> 
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [龙心小台](https://github.com/xnylong/EOS)
>
> 翻译时间：2017-11-19


Basically all token pitches include a line that goes something like this: “There are a fixed supply of tokens. By increasing demand for the token, price must increase.”
This logic fails. This is the velocity problem.

基本上所有的代币卖点都包含一句类似这样的话：“代币供应是恒定的。 通过增加对代币的需求，价格必须增加。“
此逻辑是失败的。 这是速度问题。


In this post, I’ll explain the velocity problem by providing an in-depth example. Then I’ll examine mechanisms that reduce velocity.

在这篇帖子中，我将通过提供一个深入的例子来解释速度问题。 然后，我将探讨降低速度的机制。

## A High-Velocity Example: Ticket Issuance
## 一个高速的例子: 门票发行

Ticket fraud (literally reprinting and selling the same ticket multiple times) for live events is a [huge problem](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.cnbc.com/2014/05/02/making-your-summer-concert-plans-how-not-to-get-scammed.html%26amp;sa%3DD%26amp;ust%3D1511116955561000%26amp;usg%3DAFQjCNHWQbKGESlzPQKlWu8BtIjoRuI5Uw&sa=D&ust=1511116955598000&usg=AFQjCNETchcYoC2KbHJpHzRrEP-X1mud6w). There’s a reasonable case to be made that tickets for live events should be issued on blockchains. If venues come to accept blockchain-issued tickets, this solution should stomp out all fraud. You can’t double spend blockchain-based assets.

门票欺诈（字面解释是多次重印和出售同一张票）对现场活动来说是一个[巨大的问题](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.cnbc.com/2014/05/02/making-your-summer-concert-plans-how-not-to-get-scammed.html%26amp;sa%3DD%26amp;ust%3D1511116955561000%26amp;usg%3DAFQjCNHWQbKGESlzPQKlWu8BtIjoRuI5Uw&sa=D&ust=1511116955598000&usg=AFQjCNETchcYoC2KbHJpHzRrEP-X1mud6w)。我们可以合理地解释，为什么应该在区块链上发布现场活动的门票。 如果场馆接受区块链发行的票，这个解决方案应该会阻止所有的欺诈行为。 你是无法双重花费区块链上的资产的。

Issuing tickets on blockchains can bring other benefits, including disallowing resale, profit sharing on resale back to venue, capping resale amounts, etc. Ticketing on chain should create a lot of value for venues, artists, and consumers: it eliminates fraud, reduces scalping, and reduces fees to middlemen like Ticketmaster and Stubhub.

在区块链上发行门票可以带来其他好处，包括禁止转售，转售的利润分成返还回场地，给转售金额制定上限等。在链上售票应该可以为场馆，艺术家和消费者创造很多价值：它消除了欺诈，减少了倒卖 ，并降低了对 Ticketmaster 和 Stubhub 这样的中间商的付费。  

Although I love this use case for blockchains, there is no reason that I, as a full-time crypto investor (speculator), want to actually hold [Aventus](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttp://aventus.io%26amp;sa%3DD%26amp;ust%3D1511116955562000%26amp;usg%3DAFQjCNHHbibJBxnDLswHU6ePs3HUAWV9_A&sa=D&ust=1511116955598000&usg=AFQjCNERD5rS5nJ80d-zqigeA5L07jYaxA), [Ticketchain](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://ticketchain.ie/%26amp;sa%3DD%26amp;ust%3D1511116955563000%26amp;usg%3DAFQjCNGX8nQ_fb0QFrMFr_dJv1VRpydH7g&sa=D&ust=1511116955598000&usg=AFQjCNEbtTFdA8R5Gbem0no2j3sByY6ifA), or [Blocktix](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.cnbc.com/video/2017/07/28/headed-to-a-concert-or-game-watch-out-for-ticket-scams.html%26amp;sa%3DD%26amp;ust%3D1511116955563000%26amp;usg%3DAFQjCNGeYiQHRdbpt3_bc3BuaKaNllS_EA&sa=D&ust=1511116955598000&usg=AFQjCNE4O4mTnUUzyEG9wt2k0dHNKtEt9Q) tokens (all 3 are blockchain-based ticket issuance platforms). Even if these platforms become widely used and process tens of billions of dollars of transactions, their underlying token mechanics are not structured so that the price of the underlying token will materially appreciate.

尽管我喜欢这个区块链的使用案例，但是我，作为一个全职的加密货币投资者（投机者），没有任何理由要实际持有 [Aventus](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttp://aventus.io%26amp;sa%3DD%26amp;ust%3D1511116955562000%26amp;usg%3DAFQjCNHHbibJBxnDLswHU6ePs3HUAWV9_A&sa=D&ust=1511116955598000&usg=AFQjCNERD5rS5nJ80d-zqigeA5L07jYaxA)，[Ticketchain](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://ticketchain.ie/%26amp;sa%3DD%26amp;ust%3D1511116955563000%26amp;usg%3DAFQjCNGX8nQ_fb0QFrMFr_dJv1VRpydH7g&sa=D&ust=1511116955598000&usg=AFQjCNEbtTFdA8R5Gbem0no2j3sByY6ifA) 或 [Blocktix](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.cnbc.com/video/2017/07/28/headed-to-a-concert-or-game-watch-out-for-ticket-scams.html%26amp;sa%3DD%26amp;ust%3D1511116955563000%26amp;usg%3DAFQjCNGeYiQHRdbpt3_bc3BuaKaNllS_EA&sa=D&ust=1511116955598000&usg=AFQjCNE4O4mTnUUzyEG9wt2k0dHNKtEt9Q) 代币（所有 3 个都是基于区块链的门票发行平台）。 即使这些平台被广泛使用并且处理了数百亿美元的交易，它们的底层代币机制也没有很好构建以使价格可以大幅升值。

For simplicity of reading, I’ll refer only to Aventus. However, everything below is generally true of Ticketchain, Blocktix, and most utility tokens in general.

为了便于阅读，我将只提到 Aventus。 但是，下面的所有内容通常也都适用于 Ticketchain，Blocktix 和大多数效用代币。
 
Consumers want to pay for tickets denominated in USD. They may purchase Aventus tokens as part of the ticket acquisition process, but they won’t hold Aventus tokens for more than a few minutes at a time. There’s simply no incentive to hold Aventus tokens and incur price risk relative to USD.

消费者想要支付以美元计价的门票。 他们可能购买 Aventus 代币作为购票过程的一部分，但他们一次不会持有 Aventus 代币超过几分钟。 因为根本没有动力去持有 Aventus 代币，并承担相对于美元的价格风险。
 
Venues also don’t have an incentive to hold Aventus tokens because they also want to avoid price risk relative to USD. After consumers trade Aventus tokens for concert tickets, venue hosts will trade Aventus tokens for their preferred currency. This process is illustrated in Figure 1 below. Note that this cycle can be completed in seconds by leveraging decentralized exchanges such as 0x:

场地也不没有动机持有 Aventus 代币，因为他们也想避免相对于美元的价格风险。 在消费者将 Aventus 代币换成演唱会门票之后，场地主办方将把 Aventus 代币换成他们自己的首选货币。 这个过程如下图 1 所示。 请注意，这个周期可以通过去中心化交易所（如0x）在几秒内完成：

<img src="Understanding-Token-Velocity.png" width="700">

###### Figure 1: Ticket and money flows in the Aventus ecosystem

###### 图 1: Aventus 生态系统中的门票和资金流动


No one actually wants to hold Aventus tokens. The presence of a proprietary token actually creates a worse UX for consumers by introducing an unnecessary layer of friction into the ticket purchasing process. The moment anyone receive Aventus tokens, they exchange them for something else - either a ticket (consumer) or USD (venue).

没有人真的想要持有 Aventus 代币。 一个专有代币的存在实际上为消费者带来了更糟的用户体验，因为给购票过程引入了不必要的摩擦。 一旦任何人收到 Aventus 代币，他们就会把代币换成其他东西 - 门票（消费者）或美元（场地）。
 
Even if Aventus becomes the global standard for ticket issuance, no one will want to hold Aventus tokens. BTC/ETH/USD-denominated trading volume for Aventus tokens may skyrocket as Aventus becomes the global ticketing standard, but the price of Aventus tokens will grow sub-linearly relative to transaction throughput.

即使 Aventus 成为门票发行的全球标准，也不会有人愿意持有Aventus 代币。 由于 Aventus 成为全球门票标准，Aventus 代币的比特币/ 以太币 / 美元计价的交易量可能会飙升，但 Aventus 代币的价格将相对于交易吞吐量呈次线性增长。

The primary stakeholder group who will profit from the rise in trading volume of Aventus tokens will be market makers who provide liquidity for those entering and exiting the Aventus token market. This is not a bad thing. As asset pairs increase in volume and become highly liquid, bid-ask spreads collapse to near 0%, which is good for consumers and venue hosts.

从 Aventus 代币交易量上升中获利的主要利益相关者群体将是为进入和退出  Aventus 代币市场的人提供流动性的做市商。 这不是一件坏事。 随着资产配对量的增加和流动性的增强，买卖价差缩小到接近 0％，这对消费者和场地主办方都有好处。
 
To be clear, in this scenario venue hosts still win by cutting out scalpers, and consumers win because of increased fraud protection. Despite delivering real, tangible benefits to marketplace participants, the Aventus token won’t actually capture the value the protocol is creating.

要清楚的是，在这种情况下，场地主办方仍然通过剔除黄牛获利，消费者因为增加了欺诈保护而获利。 尽管为市场参与者带来实实在在的好处，但 Aventus 代币实际上并不能真正捕获到协议创造的价值。


## Quantifying Velocity
## 量化速度

Velocity = Total Transaction Volume / Average Network Value
速度 = 总交易量/平均网络价值

Therefore:
因此：

Average Network Value = Total Transaction Volume / Velocity
平均网络价值 = 总交易量/速度

Velocity can be measured over any time span but is normally measured annually. Trading volume can be difficult to measure. This not only includes trading volume that occurs on exchanges, but OTC trades and actual usage of the platform.

速度可以在任何时间范围内测量，但通常每年测量一次。 交易量可能难以衡量。 这不仅包括在交易所发生的交易量，而且包括场外交易和平台的实际使用。

We can say that an asset has a velocity of 0 if, over the course of one year, no one buys or sells the asset. The lack of liquidity would cause the asset to trade at a discount to “intrinsic” value. Assets need some velocity to achieve intrinsic value. This is known as the [liquidity premium](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.google.com/search?q%253Dliquidity%252Bpremium%26amp;sa%3DD%26amp;ust%3D1511116955567000%26amp;usg%3DAFQjCNFUqCFApad4eNDkd6h8Xpwkl4aCSw&sa=D&ust=1511116955600000&usg=AFQjCNEnmLbXvqVuiii9dZYKn2aFGBdrCg).

我们可以说一个资产的速度为 0，如果在一年的时间内，没有人购买或出售该资产。 缺乏流动性会导致资产相对内在价值折价交易。 资产需要一些速度来实现内在价值。 这被称为[流动性溢价](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.google.com/search?q%253Dliquidity%252Bpremium%26amp;sa%3DD%26amp;ust%3D1511116955567000%26amp;usg%3DAFQjCNFUqCFApad4eNDkd6h8Xpwkl4aCSw&sa=D&ust=1511116955600000&usg=AFQjCNEnmLbXvqVuiii9dZYKn2aFGBdrCg)。

In the case of a proprietary payment token that nobody wants to hold, velocity will grow linearly with transaction volume. Per the 2nd equation above, transaction volume could grow 1,000,000x and network value could remain constant. Almost all utility tokens suffer from this problem.

在没有人愿意持有专有支付代币的情况下，速度将随交易量线性增长。 根据上面的第二个等式，交易量可以增长100万倍，网络价值可以保持不变。 几乎所有的效用代币都受到这个问题的困扰。


## How Protocols Can Reduce Asset Velocity
## 协议如何降低资产速度
 
There are a few ways a protocol can reduce the velocity of its associated asset.
协议可以通过几种方式降低相关资产的速度。
 
(1) Introduce a profit-share (or buy-and-burn) mechanism. For example, the [Augur](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttp://augur.net%26amp;sa%3DD%26amp;ust%3D1511116955569000%26amp;usg%3DAFQjCNHGCaj0eavvjG6pniavXsZ274iUcw&sa=D&ust=1511116955600000&usg=AFQjCNHmsIPOX1VS7sGVbr0hZjTWcBE_ZA) ($REP) network pays REP holders for performing work for the network. REP tokens are like taxi medallions: You must pay for the right to work for the network. Specifically, REP holders must report event outcomes to resolve prediction markets. A profit-share mechanism reduces token velocity because as the market price of an asset decreases, its yield increases. If the yield becomes too high, market participants seeking yield will buy and hold the asset, increasing price and reducing velocity.

(1）引入利润分享（或购买并销毁）机制。 例如，[Augur](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttp://augur.net%26amp;sa%3DD%26amp;ust%3D1511116955569000%26amp;usg%3DAFQjCNHGCaj0eavvjG6pniavXsZ274iUcw&sa=D&ust=1511116955600000&usg=AFQjCNHmsIPOX1VS7sGVbr0hZjTWcBE_ZA)（$ REP）网络会支付 REP 持币者为网络工作。 REP 代币就像出租车奖章一样：你必须支付以获得为网络工作的权利。 具体来说，REP 持币者必须汇报预测事件的结果来解决预测市场问题。 利润分享机制降低了代币的速度，因为随着资产的市场价格下降，其收益率会增加。 如果收益率过高，寻求收益率的市场参与者将购买并持有资产，导致价格上涨，速度下降。

Also, a cash flow stream makes a token easier to using a traditional [discounted cash flow](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.google.com/search?q%253Ddiscounted%252Bcash%252Bflow%252Bmodel%26amp;sa%3DD%26amp;ust%3D1511116955570000%26amp;usg%3DAFQjCNHsgZaXOJiyTawlfSOlO7gZ1IqD_g&sa=D&ust=1511116955601000&usg=AFQjCNGfjRRDBeE9Eg7Bj3ORR-MBrI751A) (DCF) model. Side note: check Multicoin Capital’s [Augur analysis and valuation](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://multicoin.capital/2017/08/24/rep2017/%26amp;sa%3DD%26amp;ust%3D1511116955571000%26amp;usg%3DAFQjCNE2VtBMdCRWWNJBguh-GoY46cpiZg&sa=D&ust=1511116955601000&usg=AFQjCNG7a4lneubtuOSBiLzyUAzBRAJGDQ).

另外，现金流量使得在代币上使用传统[贴现现金流](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.google.com/search?q%253Ddiscounted%252Bcash%252Bflow%252Bmodel%26amp;sa%3DD%26amp;ust%3D1511116955570000%26amp;usg%3DAFQjCNHsgZaXOJiyTawlfSOlO7gZ1IqD_g&sa=D&ust=1511116955601000&usg=AFQjCNGfjRRDBeE9Eg7Bj3ORR-MBrI751A)（DCF）模型更容易。 附注：阅读 Multicoin Capital 的 [“Augur 分析和估值”](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://multicoin.capital/2017/08/24/rep2017/%26amp;sa%3DD%26amp;ust%3D1511116955571000%26amp;usg%3DAFQjCNE2VtBMdCRWWNJBguh-GoY46cpiZg&sa=D&ust=1511116955601000&usg=AFQjCNG7a4lneubtuOSBiLzyUAzBRAJGDQ) 报告。


(2) Build staking functions into the protocol that lock up the asset. This includes proof-of-stake based staking for achieving network-layer consensus. However there are far more compelling reasons to stake than simply staking to achieve node consensus. For example:

(2）在协议中建立权益功能以锁定资产。 这包括基于 PoS （proof-of-stake) 权益证明的锁定权益以实现网络层面的共识。 但是，除了可以实现节点共识，锁定权益还有更令人信服的理由。 例如：

[Numeraire](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://numer.ai/%26amp;sa%3DD%26amp;ust%3D1511116955572000%26amp;usg%3DAFQjCNFmvZWcIIooBqygC7RrubZmz1BWpw&sa=D&ust=1511116955601000&usg=AFQjCNHqlkvKcsH4ApTvd4KAybBKFIYyQA) requires data scientists to stake their NMR tokens for 30 days to compete for prize pools.

[Numeraire](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://numer.ai/%26amp;sa%3DD%26amp;ust%3D1511116955572000%26amp;usg%3DAFQjCNFmvZWcIIooBqygC7RrubZmz1BWpw&sa=D&ust=1511116955601000&usg=AFQjCNHqlkvKcsH4ApTvd4KAybBKFIYyQA) 要求数据科学家将他们的 NMR 代币锁定 30 天以争夺奖池。

[Filecoin](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://filecoin.io/%26amp;sa%3DD%26amp;ust%3D1511116955573000%26amp;usg%3DAFQjCNGyYtiony7ZiF_H8QXSh-4Z-9IKkQ&sa=D&ust=1511116955601000&usg=AFQjCNG6xmBN7148MV6VDFKOiBMsUdJDNQ) requires that miners stake FIL tokens while storing data. If a miner goes offline or loses the data that she promised to store, her deposit is slashed. [Keep](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://keep.network/%26amp;sa%3DD%26amp;ust%3D1511116955573000%26amp;usg%3DAFQjCNFgGnRFfhkFOhHMcdqfgBsnm0OGDA&sa=D&ust=1511116955601000&usg=AFQjCNHcG5AxIp1ifadsc2qhGR3TFuCE8Q) operates in the same way. This mechanic is generally true of decentralized cloud protocols.

[Filecoin](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://filecoin.io/%26amp;sa%3DD%26amp;ust%3D1511116955573000%26amp;usg%3DAFQjCNGyYtiony7ZiF_H8QXSh-4Z-9IKkQ&sa=D&ust=1511116955601000&usg=AFQjCNG6xmBN7148MV6VDFKOiBMsUdJDNQ) 要求矿工在存储数据的同时锁定 FIL 代币。 如果矿工下线或丢失她答应存储的数据，她的定金就会被削减。 [Keep](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://keep.network/%26amp;sa%3DD%26amp;ust%3D1511116955573000%26amp;usg%3DAFQjCNFgGnRFfhkFOhHMcdqfgBsnm0OGDA&sa=D&ust=1511116955601000&usg=AFQjCNHcG5AxIp1ifadsc2qhGR3TFuCE8Q) 使用同样的方式运作。 这种机制通常应用与去中心化云协议。

[FunFair](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://funfair.io/%26amp;sa%3DD%26amp;ust%3D1511116955574000%26amp;usg%3DAFQjCNF1yP8uX5SeFFaea6PE92NEuVKAww&sa=D&ust=1511116955602000&usg=AFQjCNHPa9iA0jSBnx7y6YBpi0g0muy_vA) is a platform that powers online casinos. FunFair only supports 1v1 games such that the player is playing the house directly (therefore no poker). The house must maintain reserves to pay out highly unlikely events, such as a user winning big in slots or winning 10x in a row in blackjack (approximately 1 / 210 = .1%. The casino operators will need lock up far more than 50% of all tokens.

[FunFair](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://funfair.io/%26amp;sa%3DD%26amp;ust%3D1511116955574000%26amp;usg%3DAFQjCNF1yP8uX5SeFFaea6PE92NEuVKAww&sa=D&ust=1511116955602000&usg=AFQjCNHPa9iA0jSBnx7y6YBpi0g0muy_vA) 是一个支持网络赌场的平台。 FunFair只支持 1 对 1 游戏，玩家可以直接与赌场对赌（因此不需要扑克）。 赌场必须持有一定储备金来支付极不可能发生的事件，比如用户在老虎机上赢得大奖或者在二十一点上连续 10 次获胜（约为 1/210 = 0.1％ 概率）。 赌场经营者需要锁定远远超过 50％ 的所有代币。

[Dash](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.dash.org/%26amp;sa%3DD%26amp;ust%3D1511116955575000%26amp;usg%3DAFQjCNG5blrHR8bbFQ0Dy2wJuz0NECT7BA&sa=D&ust=1511116955602000&usg=AFQjCNGqaKYIHmfOPCl6PKC8ktxJEN_Wpg) offers users the opportunity to become masternode operators by purchasing and staking 1,000 DASH tokens. Masternodes help enable specific network-level functions such as private send (using Coin Join). In exchange for staking Dash and running beefy computers 24/7, Masternode operators receive a percentage of network fees.

[Dash](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.dash.org/%26amp;sa%3DD%26amp;ust%3D1511116955575000%26amp;usg%3DAFQjCNG5blrHR8bbFQ0Dy2wJuz0NECT7BA&sa=D&ust=1511116955602000&usg=AFQjCNGqaKYIHmfOPCl6PKC8ktxJEN_Wpg) 为用户提供了一个可以通过购买和锁定 1000 个DASH 代币来成为主节点 (masternode) 运营者的机会。 主节点 (masternode) 帮助启用特定的网络级别的功能，如私人发送（使用 Coin Join）。 作为对锁定 DASH 并全天无歇地运行拥有强大算力的电脑的补偿，主节点 (Masternode) 运营者可以收到一定比例的网络费用。

Some services graft artificial staking mechanisms into their protocols. Examples include [SALT Lending](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.saltlending.com/%26amp;sa%3DD%26amp;ust%3D1511116955576000%26amp;usg%3DAFQjCNG0W5s6es4ECQR9XEa8NkFMyq0oOQ&sa=D&ust=1511116955602000&usg=AFQjCNErTl_bthm9AQSKNPZUdgjokkUKsw) and [Airswap](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.airswap.io/%26amp;sa%3DD%26amp;ust%3D1511116955576000%26amp;usg%3DAFQjCNEltkuIjMq7Jsw1dd4nXzXXxR500w&sa=D&ust=1511116955602000&usg=AFQjCNGiqotaxrOfhVSOTq90s1JsPXckUQ). Both services simply require that in order to use each service, users must first buy and stake each platform’s respective token. On one hand, they provide compelling end-user services and strong velocity-reducing mechanisms. On the other, their tokens are entirely superfluous and unnecessary for the actual functioning of the platform. Will the self-fulfilling prophecy hold, or will rational users at some point be unwilling to take on currency risk and opportunity cost of capital associated with a proprietary token after someone else in the market copies and provides the same service for free? If enough liquidity and network effects develop around a given service such as Airswap, it seems possible that the token can sustain value even if the token is technically unnecessary.

一些服务将虚假的权益机制植入他们的协议中。 例子包括 [SALT Lending](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.saltlending.com/%26amp;sa%3DD%26amp;ust%3D1511116955576000%26amp;usg%3DAFQjCNG0W5s6es4ECQR9XEa8NkFMyq0oOQ&sa=D&ust=1511116955602000&usg=AFQjCNErTl_bthm9AQSKNPZUdgjokkUKsw) 和 [Airswap](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.airswap.io/%26amp;sa%3DD%26amp;ust%3D1511116955576000%26amp;usg%3DAFQjCNEltkuIjMq7Jsw1dd4nXzXXxR500w&sa=D&ust=1511116955602000&usg=AFQjCNGiqotaxrOfhVSOTq90s1JsPXckUQ)。 两种服务都只是要求用户为了使用每项服务，必须首先购买和持有每个平台各自的代币。 一方面，它们提供了令人信服的终端用户服务和强大的速度降低机制。 另一方面，他们的代币对平台的实际运行来说是完全多余的和不必要的。 这种自我实现的预言是否会持续下去，还是会有理性的用户在市场上其他人复制并免费提供相同的服务之后，不再愿意承担与持有专有代币相关的货币风险和机会成本？ 如果在特定服务 (如 Airswap) 周围有足够的流动性和网络效果,，那么即使代币在技术上是不必要的，代币似乎也可以维持价值。

(3) Balanced burn-and-mint mechanics. [Factom](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.factom.com/%26amp;sa%3DD%26amp;ust%3D1511116955577000%26amp;usg%3DAFQjCNF45L4tb5btxt2oxgcAba0y-hK0cA&sa=D&ust=1511116955602000&usg=AFQjCNF90yuynAqfock1ytCmBJzZ_KW0yg) is the best, and perhaps only, example.

(3）平衡的销毁-并-重铸机制。 [Factom](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.factom.com/%26amp;sa%3DD%26amp;ust%3D1511116955577000%26amp;usg%3DAFQjCNF45L4tb5btxt2oxgcAba0y-hK0cA&sa=D&ust=1511116955602000&usg=AFQjCNF90yuynAqfock1ytCmBJzZ_KW0yg) 是最好的，或许也是唯一的例子。

A number of protocols have implemented the burn concept (without minting), notably FunFair. I am highly skeptical of currencies that are explicitly deflationary to create upwards price pressure on the value of the token. In the long run, deflationary currencies will create weird incentives for holders, causing unnecessary volatility due to excessive speculation. Burn-and-mint addresses this problem.

一些协议已经实现了销毁概念（没有铸币），特别是 FunFair。 我对那些明确想要通过通货紧缩来迫使价格上涨的货币持高度怀疑态度。 从长远来看，通货紧缩的货币会给持币人带来奇怪的激励，会导致由于过度投机造成不必要的波动。 销毁并重铸解决了这个问题。

In Factom, the cost of using the protocol is denominated in USD at $.001. Each use is $.001, regardless of the price of FCT. Users burn tokens to use the protocol as designed. Independently, the protocol mints 73,000 new tokens each month and distributes them to validators (Factom is its own chain, not an ERC20 token). If users don’t burn 73,000 tokens in a month, supply increases, which should exert downwards price pressure. Conversely, if users burn more than 73,000 tokens per month, supply decreases, exerting upward price pressure. In the long run, there should be linear relationship between the usage of protocol and price.

在 Factom 中，使用该协议的成本以 $ .001 美元计价。 无论 FCT 代币的价格如何，每次使用都是 $ .001。 用户销毁代币以使协议可以如设计的方式使用。 独立地，协议每月提供73,000 个新的代币，并将它们分发给验证人（Factom 自己就是一条链，而不是 ERC20 代币）。 如果用户在一个月内不销毁 7.3 万个代币，供应就会增加，这会带来价格下降的压力。 相反，如果用户每个月销毁超过 73,000 个代币，供应就会减少，从而产生价格上涨的压力。 从长远来看，协议的使用与价格之间应该存在线性关系。

The burn-and-mint dynamic is possible because Factom is its own chain. ERC20 tokens do not have network validators who can be compensated via inflation. The burn-and-mint model is possible for ERC20 tokens, albeit trickier. There’s not a generic, obvious set of network participants who should receive the tokens that are generated by inflation. Also, there’s a technical problem: inflation can be tricky to implement because smart contracts cannot run as daemons that auto-inflate; they must be triggered.

这个销毁-并-重铸的动态机制是可行的，因为 Factom 自己就是一条链。 ERC20 代币没有可以通过通货膨胀得到补偿的网络验证人。销毁并重铸模型对 ERC20 代币来说是可能的，尽管比较棘手。 对 ERC20 代币来说，没有一群通用的，明显的网络参与者应该接收由通货膨胀产生的代币。 此外，还有一个技术问题：通货膨胀可能难以实施，因为智能合约不能作为自动通货膨胀的守护程序运行； 它们必须被触发。

Side note: check Multicoin Capital’s [Factom Analysis and Valuation](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://multicoin.capital/2017/09/07/fct2017/%26amp;sa%3DD%26amp;ust%3D1511116955580000%26amp;usg%3DAFQjCNE9LHnvFAjLtPFnnQk9Ff9LNFhSiQ&sa=D&ust=1511116955603000&usg=AFQjCNE-NelwWqpOKiM023y9m5-vseEgxw).

附注：阅读 Multicoin Capital 的 [“Factom 分析和估值”](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://multicoin.capital/2017/09/07/fct2017/%26amp;sa%3DD%26amp;ust%3D1511116955580000%26amp;usg%3DAFQjCNE9LHnvFAjLtPFnnQk9Ff9LNFhSiQ&sa=D&ust=1511116955603000&usg=AFQjCNE-NelwWqpOKiM023y9m5-vseEgxw) 报告。
 
(4) Implement gamification techniques to incentivize holding. Let’s revisit ticketing. Since many concerts sell out quickly, venues could prioritize customers based on having held X tokens for Y days. If enough venues adopt this mechanic, velocity will fall.

(4）实施游戏化技术来激励持有。 让我们重温一下售票的例子。 由于许多音乐会很快就会售罄，主办方可以根据根据将 X 代币持有了 Y 天来确定顾客的优先顺序。 如果足够的场地采用这种机制，速度将下降。

Another example: [YouNow](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.younow.com/%26amp;sa%3DD%26amp;ust%3D1511116955581000%26amp;usg%3DAFQjCNGQ6JPBF4Vxc4a4zXsm-PzK4abeiw&sa=D&ust=1511116955603000&usg=AFQjCNEy3x-Jm5H5zsZ5ZOEycdSaXhuMQA). YouNow is rolling out a proprietary in-app cryptocurrency called [PROPS](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.propsproject.com/%26amp;sa%3DD%26amp;ust%3D1511116955581000%26amp;usg%3DAFQjCNEFC0tSlLp7fvE8K8MEN3_SRdZwyQ&sa=D&ust=1511116955603000&usg=AFQjCNHDQvzVREmx-yHxukvOwcAFCVBcBQ) that allows users to tip content creators during live video broadcasts. YouNow also has a “discover” tab. The YouNow service is more likely to rank a creator’s content highly if they hold tokens. This creates an interesting dynamic in which content creators are paid in PROPS, but need to convert to fiat to pay the bills. On the other hand, they want to hoard tokens to become more discoverable, fueling more attention and generating more tip-based income.

另一个例子：[YouNow](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.younow.com/%26amp;sa%3DD%26amp;ust%3D1511116955581000%26amp;usg%3DAFQjCNGQ6JPBF4Vxc4a4zXsm-PzK4abeiw&sa=D&ust=1511116955603000&usg=AFQjCNEy3x-Jm5H5zsZ5ZOEycdSaXhuMQA)。 YouNow 正在推出名为 [PROPS](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://www.propsproject.com/%26amp;sa%3DD%26amp;ust%3D1511116955581000%26amp;usg%3DAFQjCNEFC0tSlLp7fvE8K8MEN3_SRdZwyQ&sa=D&ust=1511116955603000&usg=AFQjCNHDQvzVREmx-yHxukvOwcAFCVBcBQ) 的专有应用内加密货币，允许用户在视频直播中向内容创作者打赏。 YouNow 也有一个 “发现” 选项。 如果内容创作者持有代币，YouNow 服务更有可能将他们的内容排在前列。 这创造了一个有趣的动态，内容创造者获得的报酬是 PROPS 代币，但需要将其转换为法定货币来支付账单。 另一方面，他们希望囤积代币以使自己变得更容易被发现，引起更多的关注，并获得更多的打赏收入。

(5) Become a store of value. This is by far the most difficult to achieve as it’s not a function of a specific design mechanic, but rather a question of broader technical viability and market acceptance. If people genuinely come to believe in a token as a store of value, there will be a significant probability that they’re willing to hold onto excess tokens rather than sell them for something else.

(5）成为价值的储备。 这是迄今为止最难以实现的，因为它不是一个具体的设计机制的功能，而是更广泛的技术可行性和市场接受度的问题。 如果人们真的相信某个代币是价值的存储，那么他们就很可能会持有多余的代币，而不是把它们卖了换成别的东西。

One reason to hold an asset is an expectation that the asset will increase in price. In theory, this should dampen velocity and drive up the price of the asset. This basically [defines Bitcoin today](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttp://avc.com/2017/08/store-of-value-vs-payment-system/%26amp;sa%3DD%26amp;ust%3D1511116955582000%26amp;usg%3DAFQjCNGv_R45Xpt-IU_mHkUz5P6R663Pyw&sa=D&ust=1511116955604000&usg=AFQjCNHKIe3BMb75HNRDh14aVydIVNKXuQ). Bitcoin’s value is a function of a speculative value game, not from some intrinsic utility as a payment system.

持有资产的一个原因是期望资产价格会上涨。 理论上讲，这应该会降低速度并抬高资产价格。 这基本上[定义了今天的比特币](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttp://avc.com/2017/08/store-of-value-vs-payment-system/%26amp;sa%3DD%26amp;ust%3D1511116955582000%26amp;usg%3DAFQjCNGv_R45Xpt-IU_mHkUz5P6R663Pyw&sa=D&ust=1511116955604000&usg=AFQjCNHKIe3BMb75HNRDh14aVydIVNKXuQ)。 比特币的价值是由投机的价值游戏带来的，而不是由于作为支付系统的内在效用。

Another reason to hold an asset is the expectation that its value will be stable. A number of stablecoin projects such as [Maker](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://makerdao.com/%26amp;sa%3DD%26amp;ust%3D1511116955583000%26amp;usg%3DAFQjCNE4ZOqk6AkYiwDZaet51dPUNi_bqg&sa=D&ust=1511116955604000&usg=AFQjCNHj2Wjq6h_DHLoe15oERv6b7A264g) and [Basecoin](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttp://www.getbasecoin.com/%26amp;sa%3DD%26amp;ust%3D1511116955583000%26amp;usg%3DAFQjCNG4kGXJwJktOqzWjAHfET4yNRsBOQ&sa=D&ust=1511116955604000&usg=AFQjCNEH5arXskDKEYjYNiUxM-LKa9CqWg) are trying to create trustless assets that are price-stable on the open market.

持有资产的另一个原因是期望它的价值会保持稳定。 一些 stablecoin 的项目, 如 [Maker](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttps://makerdao.com/%26amp;sa%3DD%26amp;ust%3D1511116955583000%26amp;usg%3DAFQjCNE4ZOqk6AkYiwDZaet51dPUNi_bqg&sa=D&ust=1511116955604000&usg=AFQjCNHj2Wjq6h_DHLoe15oERv6b7A264g) 和 [Basecoin](https://www.google.com/url?q=https://www.google.com/url?q%3Dhttp://www.getbasecoin.com/%26amp;sa%3DD%26amp;ust%3D1511116955583000%26amp;usg%3DAFQjCNG4kGXJwJktOqzWjAHfET4yNRsBOQ&sa=D&ust=1511116955604000&usg=AFQjCNEH5arXskDKEYjYNiUxM-LKa9CqWg), 正试图创造在公开市场上无需信任的、价格稳定的资产。

Becoming a general-purpose store of value is extremely difficult. There are only a handful of projects even attempting to fulfill this vision today. It’s not clear how dominant the long-run winner will be. You can make perfectly rational arguments for a handful of currencies with 20-30% of global value each, a 75-5-5-5-5-5% split, or an 80-20% split. Although money has a strong network effects, it’s not clear 1) How strong those effects are. The network effect of money could be n2, n*log(n), or something else. 2) How much the market will demand viable competition to mitigate macro-level risk associated with a single mega currency.

成为一个通用的价值存储是非常困难的。 今天只有少数几个项目试图实现这个愿景。 目前尚不清楚长期赢家会多占优势。 你可以为少数几种货币的市值分布提供完全合理的猜测，如货币的全球价值占比分别为每个占比20-30％，或 75-5-5-5-5-5％ 分布，或 80-20％ 分布。 虽然金钱有很强的网络效应，但还不清楚 1）这些效应有多强。 金钱的网络效应可能是 n2，n * log（n）或其他。 2）市场将要求有多大的竞争, 以减轻与单一大型货币相关的宏观风险。

## Conclusion
## 结论

Velocity is one of the key levers that will impact long-term, non-speculative value. Most utility tokens don’t provide a compelling reason for token holders to hold the token for more than a few seconds. Absent speculation, assets with high velocity will struggle to maintain long-term price appreciation. Protocol designers will be well served to incorporate mechanisms into their protocols that encourage holding, not just usage.


速度是影响长期非投机价值的关键杠杆之一。 大多数效用代币都没有令人信服的理由，来使持币人能够持有相应代币超过几秒钟。 没有投机的情况下，高速度的资产将难以维持长期的价格升值。 协议设计人员如能在协议中纳入鼓励持有，而不仅仅是使用的机制，将会获得很好的成效。

                                                                                                  
----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

本文由币乎社区（bihu.com）内容支持计划赞助。

版权所有，转载需完整注明以上内容。

----------------------------------------------------

