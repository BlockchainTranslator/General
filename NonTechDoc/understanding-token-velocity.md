# Understanding token velocity | 理解代币周转率

> 本文翻译自：https://multicoin.capital/2017/12/08/understanding-token-velocity/
> 作者：KYLE SAMANI
> 译者：[区块链中文字幕组 胡亮](https://github.com/gumoon)
> 感谢币乎创始人咕噜荐文
> 翻译时间：2018-1-31

Basically, all token pitches include a line that goes something like this: “There is a fixed supply of tokens. As demand for the token increases, so must the price.”

基本上，所有代币都包含一条类似的线：“有固定的代币供应，随着对代币的需求增加，价格也随之上升。”

This logic fails to take into account the velocity problem.

这种逻辑没有考虑到周转率问题。

In this post, I’ll explain the velocity problem by providing an in-depth example. Then I’ll examine mechanisms that reduce velocity.

在这篇文章中，我将通过提供一个深入的例子来解释周转率问题。然后，我将分析降低周转率的机制。

## A HIGH-VELOCITY EXAMPLE | 一个高周转率的例子
Ticket fraud (literally reprinting and selling a ticket multiple times) for events is a [huge problem](https://www.cnbc.com/2014/05/02/making-your-summer-concert-plans-how-not-to-get-scammed.html).

门票欺诈（拷贝和多次销售同一张门票）的事件是一个[巨大的问题](https://www.cnbc.com/2014/05/02/making-your-summer-concert-plans-how-not-to-get-scammed.html)。

There’s a reasonable case to be made that tickets for live events should be issued on blockchains. If venues come to accept blockchain-issued tickets, this solution should stomp out all fraud. You can’t double spend blockchain-based assets.

一个合理的案例是现场活动的门票应该应用区块链销售。如果场地接受区块链销售的门票，这个解决方案应该能消除所有的欺诈。你不能多次购买基于区块链的资产。

Issuing tickets on blockchains can bring other benefits, including disallowing resale, profit sharing on resale back to the venue, capping resale amounts, etc. Ticketing on-chain should create a lot of value for venues, artists and consumers: it eliminates fraud, reduces scalping, and reduces fees to middlemen like Ticketmaster and StubHub.

基于区块链销售门票能带来其他好处，包括不允许转售，转售回场所收益共享，限制转售数量等等。门票上链为场所、艺术家和消费者创造很多价值。它消除了欺诈，减少了倒票，并且降低了给中间商（如：Ticketmaster 和 StubHub）的费用。

Although I love this use case for blockchains, there is no reason that I, as a full-time crypto investor (speculator), want to actually hold [Aventus](http://aventus.io/), [Ticketchain](https://ticketchain.ie/) or [Blocktix](https://www.cnbc.com/video/2017/07/28/headed-to-a-concert-or-game-watch-out-for-ticket-scams.html) tokens (all three are blockchain-based ticket issuance platforms). Even if these platforms become widely used and process tens of billions of dollars of transactions, their underlying token mechanics are not structured so that the price of the underlying token will materially appreciate.

尽管我喜欢这个应用案例，但，我，作为一个全职数字货币投资者（投机者），仍然没有理由实际持有[Aventus](http://aventus.io/), [Ticketchain](https://ticketchain.ie/) 或 [Blocktix](https://www.cnbc.com/video/2017/07/28/headed-to-a-concert-or-game-watch-out-for-ticket-scams.html) 代币（这三都是基于区块链的门票销售平台）。即使这些平台变得广泛被使用和处理亿级交易，但是它们底层的代币机制不是结构化的，以至于代币价格会相当大的上涨。

Consider a hypothetical platform that we’ll call Karn, in honor of [the show that never ends](https://genius.com/Emerson-lake-and-palmer-karn-evil-9-1st-impression-pt-2-lyrics).

考虑一个假设的平台，我们叫它 Karn, 纪念 [the show that never ends](https://genius.com/Emerson-lake-and-palmer-karn-evil-9-1st-impression-pt-2-lyrics)。

Consumers want to pay for tickets denominated in dollars. They may purchase Karn tokens as part of the ticket acquisition process, but they won’t hold the tokens for more than a few minutes at a time. There’s simply no incentive to hold them and incur price risk relative to the dollar.

消费者想使用美元买门票。他们可以通过购买 Karn 代币来获得门票，但是他们每次只短时间持有代币。简而言之，他们没有动机持有代币，而且相对于美元来说会招致价格风险。

Venues also don’t have an incentive to hold Karn tokens because they, too, want to avoid price risk. After consumers trade their tokens for concert tickets, venue hosts will trade Karn tokens for their preferred currency. Note that this cycle can be completed in seconds by leveraging decentralized exchanges such as 0x:

消费场所亦没有动机持有 Karn 代币，因为他们也想避免价格风险。在消费者使用代币购买完音乐会门票后，场所主人将把 Karn 代币换成它更喜欢的货币。请注意，这个循环通过去中心化交易所像 0x ，可以在数秒内完成。

![](media/15171473485650.jpg)


No one actually wants to hold Karn tokens. The presence of a proprietary token actually creates a worse UX for consumers by introducing an unnecessary layer of friction into the ticket purchasing process. The moment anyone receives Karn tokens, they exchange them for something else – either a ticket (consumer) or dollars (venue).

没有人的确想持有 Karn 代币。专门的代币通过在门票销售过程中引入一个不必要的阻力层，对消费者来说，实际上创造了一个更坏的用户体验。任何人收到 Karn 代币的时候，他们使用代币交换其它的东西-可能是一张门票（消费者），也可能是美元（场所）。

Even if Karn becomes the global standard for ticket issuance, no one will want to hold it. BTC/ETH/USD-denominated trading volume for Karn tokens may skyrocket as the platform becomes the global ticketing standard, but the price will grow sub-linearly relative to transaction throughput.

即使 Karn 变成了门票销售全球标准，也没有人想持有它。由于平台变成了全球门票标准，比特币/以太坊/美元结算的 Karn 代币的交易量可能疯长。但是，价格上涨曲线将会在交易量上涨曲线之下。

The primary stakeholder group who will profit from the rise in trading volume of Karn tokens will be market makers who provide liquidity for those entering and exiting the market. This is not a bad thing. As asset pairs increase in volume and become highly liquid, bid-ask spreads collapse to near 0 percent, which is good for consumers and venue hosts.

主要的出资人群体将从 Karn 代币交易量上涨中获利。他们作为做市商为进出市场的人提供流动性。这不是一件坏事。随着资产对数量的增加和高流动性，买卖价差下降到接近0%，这对消费者和场所主人都是有利的。

To be clear, in this scenario the venue hosts still win by cutting out scalpers, and consumers win because of increased fraud protection. But despite delivering real, tangible benefits to marketplace participants, our fictional Karn token won’t actually capture the value the protocol is creating.

需要明确的是，在这种场景下，场所主人赢了，因为干掉了黄牛党，消费者也赢了，因为增加了欺诈保护。但是，尽管提供了真正的，实实在在的好处给市场参与者，我们虚构的 Karn 代币仍然不会实际地创造价值。

## QUANTIFYING VELOCITY | 量化周转率
Here’s where velocity comes in. It’s defined as:

这里讲周转率怎么来的。它的定义是：

Velocity = Total Transaction Volume / Average Network Value

周转率 = 总交易量 / 代币平均网络价值

Therefore:

因此：

Average Network Value = Total Transaction Volume / Velocity

代币平均网络价值 = 总交易量 / 周转率

Velocity can be measured over any time span, but is normally measured annually. Trading volume can be difficult to measure. This not only includes trading volume that occurs on exchanges, but over-the-counter trades and actual usage of the platform.

周转率可以在任何时间范围内测量，但通常每年测量一次。交易量很难衡量。这不仅包括交易所发生的交易量，而且包括场外交易和平台实际使用量。

We can say that an asset has a velocity of 0 if, over the course of a year, no one buys or sells it. The lack of liquidity would cause the asset to trade at a discount to its “intrinsic” value. Assets need some velocity to achieve their full intrinsic value. The difference is known as the [liquidity premium](https://www.google.com/search?q=liquidity+premium).

我们可以说，如果一年内没有人买卖，资产就有0的周转率。缺乏流动性会导致资产折价交易。资产需要一定的周转率才能达成其全部内在价值。这种差异被称为[流动性溢价](https://www.google.com/search?q=liquidity+premium)。

In the case of a proprietary payment token that nobody wants to hold, velocity will grow linearly with transaction volume. Per the second equation above, transaction volume could grow a million-fold and network value could remain constant. Almost all utility tokens suffer from this problem.

在这个案例中，一个专有支付代币没有人愿意持有，周转率将随着交易量线性增长。根据上面的第二个方程，交易量可以增长一百万倍，而代币网络价值保持恒定。几乎所有的实用代币都受到这个问题的困扰。

## REDUCING VELOCITY | 降低周转率
There are a few ways a protocol can reduce the velocity of its associated asset.

有一些方法可以降低代币相关资产的周转率。

1) **Introduce a profit-share (or buy-and-burn) mechanism:** For example, the [Augur](http://augur.net/) ($REP) network pays REP holders for performing work for the network. REP tokens are like taxi medallions: you must pay for the right to work for the network. Specifically, REP holders must report event outcomes to resolve prediction markets. A profit-share mechanism reduces token velocity because as the market price of an asset decreases, its yield increases. If the yield becomes too high, market participants seeking yield will buy and hold the asset, increasing price and reducing velocity.

1）**引入利润共享（或者叫买入销毁）机制：** 例如，[Augur](http://augur.net/) ($REP)网络为替网络执行工作的 REP 代币持有者付费。REP 代币就像出租车奖章：你必须为替网络执行工作的行为付费。具体而言，REP持有者必须报告事件结果，以完善预测市场。一个利润共享的机制降低了代币周转率，因为资产的市场价格下降，收益率相应上升。如果收益率过高，追求收益的市场参与方将购买并持有资产，推高价格并降低周转率。

Also, a cash-flow stream makes a token easier to value using a traditional [discounted cash-flow](https://www.google.com/search?q=discounted+cash+flow+model) (DCF) model. Note: see the Multicoin Capital [Augur analysis and valuation](https://multicoin.capital/rep2017/).

此外，现金流使一个代币更容易使用传统的[贴现现金流](https://www.google.com/search?q=discounted+cash+flow+model) (DCF)模型来估值。注意：查看 Multicoin 资本的 [Augur 分析和估值](https://multicoin.capital/rep2017/)。

2) **Build staking functions into the protocol that lock up the asset**: This includes proof-of-stake mechanisms for achieving network-layer consensus. However there are far more compelling reasons to stake than simply to achieve node consensus. For example, [FunFair](https://funfair.io/) is a platform that powers online casinos. FunFair only supports one-against-one games such that the player is playing the house directly (therefore no poker). The house must maintain reserves to pay out highly unlikely events, such as a user winning big in slots or winning 10 times in a row in blackjack. The casino operators will need to lock up far more than 50 percent of all tokens.

2）**在锁定资产协议中构建锚定函数**：这包括为取得网络层共识的 POS 机制。然而，有比简单的取得节点共识更令人信服的理由来锚定。例如：[FunFair](https://funfair.io/) 是一个在线赌场平台。FunFair 只支持一对一游戏，玩家直接在房间游戏。该房间必须保留储备金，以支付小概率事件，如：一个用户在极小概率下赢得大票，或者在21点中连续赢得10次。赌场运营者需要锁定远超所有代币50%的代币。

3) **Balanced burn-and-mint mechanics**: [Factom](https://www.factom.com/) is the best, and perhaps only, example.

3）**平衡销毁和挖矿机制**：[Factom](https://www.factom.com/) 是最好也许是唯一的案例。

A number of protocols have implemented the burn concept (without minting), notably FunFair. I am highly skeptical of currencies that are explicitly deflationary to create upwards price pressure on the value of the token. In the long run, deflationary currencies will create weird incentives for holders, causing unnecessary volatility due to excessive speculation. Burn-and-mint addresses this problem.

一些协议已经实现了销毁概念（不挖矿），尤其是 FunFair。我对那些明显通缩的货币持高度怀疑态度，这会对代币的价值产生上行压力。从长期来看，通货紧缩会给持有者带来奇怪的刺激，导致过度投机造成不必要的波动。销毁和挖矿机制正是为了解决这个问题。

In Factom, the cost of using the protocol is denominated in U.S. dollars at $.001. Each use is $.001, regardless of the price of FCT. Users burn tokens to use the protocol as designed. Independently, the protocol mints 73,000 new tokens each month and distributes them to validators (Factom is its own chain, not an [ERC20](https://www.coindesk.com/ethereums-erc-20-tokens-rage-anyway/) token). If users don’t burn 73,000 tokens in a month, supply increases, which should exert downwards price pressure. Conversely, if users burn more than 73,000 tokens per month, supply decreases, exerting upward price pressure. In the long run, there should be linear relationship between the usage of protocol and price.

在 Factom 里，使用该协议的成本是0.001美元。不考虑 FCT 价格的前提下，每次使用都是 0.001美元。协议被设计为以销毁代币的形式来使用。独立地，协议每月新挖出73000个代币分发给矿工。（Factom 有一条自己的区块链，不是一个 [ERC20](https://www.coindesk.com/ethereums-erc-20-tokens-rage-anyway/)代币。如果用户每月没有销毁73000个代币，供应量就会增加，这会施加下行的价格压力。相反，如果用户每月销毁超过73000个代币，供应量会下降，这会施加上行的价格压力。从长期来看，协议的使用与价格之间应该存在线性关系。

The burn-and-mint dynamic is possible because Factom is its own chain. ERC20 tokens do not have network validators who can be compensated via inflation. Burn-and-mint is possible for ERC20 tokens, albeit trickier. There’s not a generic, obvious set of network participants who should receive the tokens that are generated by inflation. Also, more technically: inflation is tricky to implement because smart contracts cannot run as daemons that auto-inflate; they must be triggered.

因为 Factom 有自己的区块链，所以，销毁和挖矿 是动态可调的。ERC20 代币没有能够被补偿的网络验证者。销毁和挖矿机制也是可能应用到 ERC20 代币的，尽管挺困难。没有一个通用的、明显的网络参与者集合，它们应该接收由通货膨胀产生的代币。同时，在技术上更多的做到：通货膨胀很难实现，因为智能合约不能以守护进程的方式运行（守护进程能实现自动通货膨胀），它们必须被触发。

Note: see the Multicoin Capital [Factom analysis and valuation](https://multicoin.capital/fct2017/).

注意：查看 Multicoin 资本的[Factom 分析和估值](https://multicoin.capital/fct2017/)。

4) **Gamification to encourage holding**: Let’s revisit ticketing. Since many concerts sell out quickly, venues could prioritize customers based on having held X tokens for Y days. If enough venues adopt this mechanic, velocity will fall.

4）**游戏化鼓励持有**：让我们重温门票。由于许多演唱会门票卖得很快，场所可以优先考虑持有 X 币 Y 天的顾客。如果足够多的场所采用这一机制，周转率将下降。

Another example: [YouNow](https://www.younow.com/) is rolling out a proprietary in-app cryptocurrency called [PROPS](https://www.propsproject.com/) that allows users to tip content creators during live video broadcasts. YouNow also has a “discover” tab. The YouNow service is more likely to rank a creator’s content highly if they hold tokens. This creates an interesting dynamic in which content creators are paid in PROPS, but need to convert to fiat to pay the bills. On the other hand, they want to hoard tokens to become more discoverable, fueling more attention and generating more tip-based income.

另外一个例子：[YouNow](https://www.younow.com/) 正在推出一种App内专有数字货币，叫做 [PROPS](https://www.propsproject.com/)。它允许用户在观看直播时打赏内容创作者。YouNow 有一个“发现”选项卡。如果内容创作者持有代币，YouNow服务会给他创造的内容更高的排序权重。这创造了一个有趣的均衡，一方面，内容创作者接受 PROPS 打赏，然后希望转换 PROPS 为法币。另一方面，他们想囤积代币来使创造的内容变得更容易被发现，引发更多的关注以至于产生更多的小费收入。

5) **Become a store of value**: This is by far the most difficult to achieve as it’s not a function of a specific design mechanic, but rather a question of broader technical viability and market acceptance. If people genuinely come to believe in a token as a store of value, there will be a significant probability that they’re willing to hold onto excess tokens rather than sell them for something else.

5）**成为价值存储**：这是迄今为止最难实现的，因为它不是一个特定设计技艺的一个功能，而是一个更广泛的技术可行性和市场接受度的问题。如果人们真的相信代币是一种价值存储，那么很有可能他们愿意持有多余的代币而不是卖掉换别的东西。

One reason to hold an asset is an expectation that it will increase in price. In theory, this should dampen velocity and drive up the price of the asset. This basically [defines bitcoin today](http://avc.com/2017/08/store-of-value-vs-payment-system/). Bitcoin’s value is a function of a speculative value game, not from intrinsic utility as a payment system.

持有资产的一个原因是期望它会升值。从理论上讲，这会抑制周转率并且抬高资产价格。这从根本上[定义了比特币的今天](http://avc.com/2017/08/store-of-value-vs-payment-system/)。比特币的价值是一个投机的价值游戏，而不是作为支付系统的内在效用。

Another reason to hold an asset is the expectation that its value will be stable. A number of stablecoin projects such as [Maker](https://makerdao.com/) and [Basecoin](http://www.getbasecoin.com/) are trying to create trustless assets that are price-stable on the open market.

持有资产的另一个原因是期望它的价值稳定。一些提供稳定货币的项目，像 [Maker](https://makerdao.com/) 和 [Basecoin](http://www.getbasecoin.com/)，都在尝试创造去信任的资产，使他们在开放市场上价格稳定。

Becoming a general-purpose store of value is extremely difficult. There are only a handful of projects even attempting to fulfill this vision today. It’s not clear how dominant the long-run winner will be. You can make perfectly rational arguments for a handful of currencies with 20–30 percent of global value each, a 75-5-5-5-5-5 percent split, or an 80-20 percent split. Although money has a strong network effects, it’s not clear how strong those effects are, or how much the market will demand viable competition to mitigate macro-level risk associated with a single mega currency.

成为一个通用目的的价值存储是极其困难的。今天只有少数项目试图实现这一愿景。目前还不清楚长期赢家是如何分配数字货币比例的。你可以理性探讨一捆数字货币的比例：每种20-30%比例，或者75-5-5-5-5-5%的分配比例，或者80-20%的分配比例。虽然货币具有很强的网络效应，但不清楚这些影响有多大，或者市场需要多少竞争来缓解与单一超级货币相关的宏观层面的风险。

## CONCLUSION | 结尾
Velocity is one of the key levers that will influence long-term, non-speculative value.

周转率是影响长期、非投机性价值的关键杠杆之一。

Most utility tokens don’t provide a compelling reason for token holders to hold the token for more than a few seconds. Absent speculation, assets with high velocity will struggle to maintain long-term price appreciation.

大多数实用代币无法为代币持有者持有代币提供令人信服的理由。缺乏投机，高周转率的资产将难以维持长期的价格升值。

Hence, protocol designers will be well served to incorporate mechanisms into their protocols that encourage holding, not just usage.

因此，协议设计者将很好地将机制引入到他们的协议中，以鼓励持有，而不仅仅是使用。

----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/)

#### 本文译者简介

胡亮 区块链技术爱好者，欢迎加微信号:haobaba-huliang

本文由币乎社区（bihu.com）内容支持计划赞助。

版权所有，转载需完整注明以上内容。

----------------------------------------------------


