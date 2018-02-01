> 本文由 @咕噜 BIHU.COM 推荐
>
> vitalik 和 Difinity 社区对于 Stablecoin 的思考
>
> 翻译自：https://ethresear.ch/t/collateralized-debt-obligations-for-issuer-backed-tokens/525
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator) [鱼](https://github.com/oscnet)
>
> 翻译时间：2018-1-30
>
> 本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。

### Collateralized Debt Obligations for Issuer-Backed Tokens

### 以债券抵押的由发行人背书的代币

*Special thanks to some discussions from Dominic Williams from 2015 that brought up the idea of multi-issuer collateral-risk-reduced stablecoins.*

*特别感谢2015年多米尼克·威廉斯（Dominic Williams）的一些关于降低多个发行者抵押风险的稳定币的想法*

One major type of "stablecoin" that already exists, and will likely continue to become more popular, on public blockchains is the issuer-backed token (eg. [Tether](https://tether.to/?p=7889), and likely soon Digix Gold). In this model some centralized issuer maintains a reserve (likely a bank or brokerage account or vault depending on context) of some underlying backing asset, and issues a quantity of tokens on the blockchains equal to the quantity of the backing asset. They promise that each unit of the blockchain token will be redeemable for a unit of the backing asset.

目前主流的稳定币已经存在，而且可能会变得越来越流行，公链上有由发行人担保的代币（如 [Tether](https://tether.to/?p=7889), 以及即将推出的 Digix Gold）。在这种模式下，一些中央发行机构保存了一些基础资产的储备（类似于银行或经纪人账户或保险库，视情况而定。）， 然后在区块链上发放等值于其资产背书的代币。并且承诺区块链上的每单位代币都可以兑换一个单位的用于背书的资产。

This kind of token is attractive because it avoids the [financial "black swan" risk](https://prestonbyrne.com/2017/12/10/stablecoins-are-doomed-to-fail/) of stablecoins like DAI that are purely backed by crypto, but it comes with its own set of problems, chief among which is that it brings back the spectre of counterparty risk. Issuers of backed tokens are often met with suspicion, and the tokens are often avoided as a result.

这种代币之所以有吸引力, 是因为它避免了象贷币这类单纯由密码学支撑的稳定币的["黑天鹅"金融风险](https://prestonbyrne.com/2017/12/10/stablecoins-are-doomed-to-fail/), 但是也有自己的一系列问题, 其中最主要的问题是它带来了合同对方的风险。有背书的代币的发行方经常会受到怀疑（应该是类似于 USDT 一样怀疑用于背书的资产是否足额，以及中心化等问题。译者注）, （有些人）由此通常会避免使用这种代币。

The following is a proposal for how to mitigate this risk, effectively creating 1-of-N issuer-backed stablecoins that only fail if most or all of the issuers fail.

以下是如何减轻这种风险的方案，它有效地创造了 1-of-N 发行人背书的稳定币，它只有在大多数或所有发行人破产时才会失效。

---

Suppose that we have N issuers of USD on the blockchain, I[1] ... I[n], and there exists a DAO into which M coins from each issuer have been deposited. The DAO releases N new assets, which we call "slice 1" … "slice N", effectively ordered low risk to high risk. The goal is as follows: buyers of slice 1 will be able to redeem a dollar if at least one, any one, of the issuers continues to be solvent. Buyers of slice 2 will be able to redeem a dollar as long as at least two issuers are solvent. And so on and so forth until slice N, which will be able to redeem a dollar only if all issuers are solvent.

假设我们在区块链上有 N 个美元发行者，I [1] ... I [n] ，并且存在一个 DAO （去中心化自治组织，也指区块链上的智能合约，译者注），其中存放着来自每家发行人的 M 个币。DAO 发行了 N 个新的资产，我们称之为"第 1 部分"..."第 N 部分"，并且从低风险到高风险进行了排序。规则如下：
* 如果至少有一家（可以是任何一家）发行人仍有偿债能力，则第一部分的买家将能够赎回一美元。
* 只要至少有两家发行人具有偿债能力，第二部分的买家将能够赎回一美元。
* 等等等等，直到第 N 部分，只有当所有的发行人都是有偿债能力的时候，才能赎回一美元。

The expected loss component of counterparty risk can never be reduced or removed - if the issuers collectively lose $X, that loss of $X has to be paid by someone. But what this does let us do is channel the risk toward those who are most willing to bear it, and give those who are not an asset that is highly robust, losing value only if a very large number of issuers fail.

交易对手风险的预期损失部分永远不能减少或消除 - 如果发行人集体损失 X 美元，那么 X 美元的损失必须有人来承担。因此，我们要做的就是把风险转移到那些愿意承担风险的人手上，对那些不愿意承担风险的人，我们就给他们高度稳健的资产，这个资产只有当极大量的发行人都不能偿债时资金才会有所损失。

To compensate those who are willing to bear risk (or those with insider knowledge that allows them to trust the issuers more than the general public does), the holders of slices closer to N would be paid interest rates, which would come out of the pockets of the holders of slices closer to 1.

为了补偿那些愿意承担风险的人(或那些知情的内幕人士、比普通公众更信任发行者的人) , 接近于第 N 部分的持有者将得到利率补偿, 并且这个利率由自接近第 1 部分的持有者来支付。

---

Now, on to implementation. The coins are issued at time T, and have a pre-determined duration D. Before T, anyone is allowed to specify a bid, of the form "I want to buy a unit of slice i, and I am willing to pay x / N units of every coin in the basket to purchase it". The system then keeps track of the bids in highest-to-lowest sorted order for each slice, and once the bidding period ends it starts processing the bids. It looks at the top bid for each slice, and sees if the top bids sum to at least 1. If they do, then it accepts the bids, and if they do not then it terminates.

现在，我们来看看实施情况。代币是在时间 T 发行，并且具有预先确定的持续时间 D。在 T 之前，任何人都可以指定出价，以“我想在第 i 部分购买一个单位的代币, 并且我愿意支付  x / N 篮子里的每币单位 来购买它”的形式。然后，系统以每个部分的最高到最低排序顺序跟踪出价，一旦出价周期结束，就开始处理出价。它会查看每个部分的最高出价，并查看这些最高出价总和是否大于等于 1 。如果是的，则接受出价，如果不是则结束。

At the end of the process, everyone who bid for slice i pays the same price as the last (ie. lowest) accepted bid for slice i. This mechanism ensures that, for every set of bids the system accepts, the system issues one coin for each slice and receives at least one coin from each issuer as backing, so it will be able to meet all obligations.

在这个过程的最后，毎个对第 i 部分出价的人支付相同的价格（如最低价）作为 i 部分最后接受的价格。这种机制确保系统接受的每套出价，系统为各部分发行的毎一个代币，至少能收到发行人一个代币的背书，这样就能够满足所有的债务。

At time T + D, comes the claiming phase, which is split into N periods. In the first period, everyone who has a coin of slice 1 can redeem it in exchange for a coin from any issuer of their choosing. In the second period, everyone who has a coin of slice 2 can do the same, though if there is some issuer whose coins have already been fully drained by the redeeming process they can naturally no longer be claimed. This continues for all N slices.

 T + D 时间到了以后，来到赎回阶段，它被分成 N 个阶段。在第一个时期，每个拥有第 1 部分代币的人都可以
换取他们选择的任何发行人的代币。在第二个时期，每个拥有第 2 部分代币的人同样如此，但是如果有一些发行人的币已经在赎回过程中赎回，他们当然就不会再被要求赎回了。这种情形一直持续下去，直到第 N 部分。

This mechanism removes the need to have any kind of fancy dynamically adjusted/controlled interest rate, or an oracle to tell which issuers are insolvent. If k of the N issuers are insolvent, then holders of coins in slices 1…N-k would redeem all of the solvent coins first, leaving the holders of coins in slices N-k+1…N with worthless coins; the need for an oracle is substituted with market-based preference revelation.

这种机制不需要有任何形式的动态调整/利率控制，或者靠先知来预测哪些发行人将破产。如果 N 个发行人中有 k 个破产，那么 第 1 部分 ... 第 N-k 部分的币持有者将首先赎回所有的有清还能力的币，留下 第 N-k+1 部分 ... 第 N 部分的币持有人手中就变成没有价值的币; 先知的需求被基于市场的优先偿还权利取代。

To create an infinite-duration coin on top of this, one can simply imagine a DAO that creates rounds of this game with duration 2D every D (ie. there are always two overlapping games) and another DAO which buys tokens of some specific slice on the open market a quarter of the way through their period and sells them three quarters of the way through to buy the coins from the next game.

在此基础上为了创造一个无限持续的代币，可以简单地想象下，一个 DAO 每隔 D 时间建立这个游戏回合，每个回合的持续时间为 2D （即：总是有两个重叠的游戏），另一个 DAO，它们用期间四分之一的时间从公开市场购买一些特定部分的代币，然后用四分之三的时间卖掉，用以买下一场游戏的币。

### Variations
### 其它变化

* Have one of the "issuers" be a contract that holds ETH and has a redemption process that allows holders of a coin to claim an amount of ETH equivalent to 1 USD. The contract's USD liabilities would be half the value of its ETH holdings at the start, and if the contract becomes insolvent it would simply give each token holder an equal share of its entire quantity of ETH. Any undistributed ETH would be given to a second class of token holder, who would thus be holding "ETH at 2x leverage"

* Come up with more complex combinatorial mechanisms that allow people to express through the market opinions like "I think issuers 1, 4 and 11 are solvent but have no idea about any of the others"

* Have one of the "issuers" be DAI

* "发行人"可以是持有以太的智能合同，并且有一个兑换程序允许持有人兑换相当于 1 美元的以太。智能合同的美元债务开始时是以太持有价值的一半。如果这个合同资不抵债，它会让每个令牌持有者平分全部数量的以太。任何未分配的以太将被分配给第二类代币持有者，这些持有者因此持有"2倍杠杆的以太"。

* 提出更复杂的组合机制，让人们能够通过市场表达意见，比如"我认为发行人 1, 4 和 11 是具有偿付能力, 但对其它任何一家都不知情"

* 贷币可以是发行者之一。
