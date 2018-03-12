
[Source](https://www.reddit.com/r/ethereum/comments/30f98i/introducing_edollar_the_ultimate_stablecoin_built)

## Introducing eDollar, the ultimate stablecoin built on Ethereum

## eDollar 简介: 以以太坊为基础构建的终极稳定数字货币

As someone who's been obsessed with pegged cryptocurrencies for the past 6 months, I was delighted to find out that even with just my meager programming skills, developing for Ethereum is so incredibly easy that I've been able to come up with what I believe is close to being the perfect design for a stable cryptocurrency.

在过去 6 个月里, 我对锚定法币的加密货币非常痴迷。我很高兴地发现，即使像我这样薄弱的编程技能，以太坊开发也非常容易，我已经能够设计出一个我认为能接近完美的稳定币。

In short, the eDollar is a token pegged to the USD that is issued in a manner similar to bitUSD, and that has a DAO (called Maker) backing it and providing liquidity similar to the system of liquidity providing custodians that NuBits uses.

简而言之，eDollar 是一种锚定美元的通证，发行方式与 bitUSD 类似, 背后有一个 DAO（称为 Maker）提供支持并由类似于 NuBits 的流动性托管系统那样提供流动性。

The purpose of eDollar is to give average people a currency they can use on the ethereum network to interact with dapps, without having to worry about insane volatility like with bitcoin and other 1st gen cryptocurrencies. It also gives ethereum investors the possibility to take leveraged ETH positions (albeit with very high collateral requirements).

eDollar 的目的是为普通人提供可以在以太坊网络上使用的货币, 可以与 dapps 进行交互，而不必担心像比特币和其它第一代加密货币那样, 币价剧烈波动。它也让以太坊投资者有可能利用 ETH 杠杆头寸（尽管抵押需求非常高）。

To see a full (but rough) description of the features of the eDollar design, you can check out this post on the Maker forum: [http://makerdao.com/index.php?topic=4.0](http://makerdao.com/index.php?topic=4.0) (the forum design is really fancy, I know :p)

eDollar 完整（但粗略的）的功能设计描述，可以在 Maker 论坛上查看此帖：
[http://makerdao.com/index.php?topic=4.0](http://makerdao.com/index.php?topic=4.0) (论坛设计真的很花哨，我知道：p）

To see the eDollar contract with comments, check: [http://makerdao.com/peggedcoinremake.sol](http://makerdao.com/peggedcoinremake.sol)

要查看带评论的 eDollar 合约，请查看：[http://makerdao.com/peggedcoinremake.sol](http://makerdao.com/peggedcoinremake.sol)

To see the test frontend [http://makerdao.com/edollarfrontendtest.html](http://makerdao.com/edollarfrontendtest.html)

要查看测试前台[http://makerdao.com/edollarfrontendtest.html](http://makerdao.com/edollarfrontendtest.html)

(edit I should add that the front end is not currently set up to work with the latest version of the contract, so the dapp can't actually be tested atm without adding new ABI calls)

（我应该补充一点，前台目前不能兼容最新版本的智能合约，所以目前如果不加新的 ABI 调用，无法测试 dapp）

These are the basic pointers of the design:

这些是基本的设计方针：

* If EUSD is currently trading above 99 cents, then anyone can issue new EUSD by putting up 3 USD worth of ether as collateral for every 1 EUSD (300% collateral requirement).

* 如果 EUSD 目前交易价格在 99 美分以上，那么任何人都可以通过为每 1 个 EUSD 提供价值 3 美元的 ETH 作为抵押物( 300％ 抵押品要求)来发行新的 EUSD。

* After issuing EUSD, the issuer gets a debt that has to be covered by burning an equal amount of EUSD if they want to get their collateral back.

* 发行 EUSD 后，如果发行人希望获得抵押品，发行人必须偿还一笔等额的 EUSD。

* If the collateral/debt ratio for a position ever goes below 150% anyone can perform a "hard margin call", getting the entire collateral balance in return for covering the debt.

* 如果一个头寸的抵押/债务比率一直低于 150％，任何人都可以要求执行“硬性保证金追加”，获得全部抵押品余额以抵消债务。

* In practice this should never happen due to the existence of Maker (trading as MKR), the "guardian DAO". Maker has the ability to perform soft margin calls and forced covers.

* 在实践中，由于 Maker（MKR 交易）-- “监护人 DAO”的存在，这绝不应该发生。 Maker 有能力执行柔性保证金追加和强制偿还。

* a soft margin call can be done on any position with a c/d ratio below 200%, and with penalty of up to 5%. The issuer will get the remaining collateral after the value of the debt and the penalty (if any) has been subtracted from it.

* 任何抵押/债务比率低于 200％ 的仓位都可以进行柔性保证​​金追加，罚金最高为 5％。发行人将在扣除债务价值和罚金（如果有的话）后, 得到剩余的抵押品。

* a forced cover enables Maker to cover any position at the market rate as determined by the feed. This ability ensures that Maker can guarantee liquidity for users who wants to get out of eDollar.

* 强制清偿使得 Maker 能够根据反馈所决定的市场比率来覆盖任何头寸。这一能力可以确保 Maker 能够为想要卖出 eDollar 的用户提供流动性保证。

* Maker will earn income by staking with the eDollar collateral. Only a small portion of the collateral will be used for this since it gets locked up for 3 months at a time. A system will be in place to ensure that the collateral cannot be stolen by Maker, and that it only gains access to the profits from the staking.

* Maker 将通过 eDollar 的抵押品赚取收入。由于它每次被锁定 3 个月，所以只会使用一小部分抵押品。将建立一个系统来确保抵押品不会被 Maker 窃取，限制它只能获得从抵押中取得的利润。

* The profits will be used to buy diversified collateral, such as gold vouchers from DGX.io. This diversified collateral will be used as a last resort in case the ether price crashes so fast that some positions become undercollateralized before they can be margin called (known as a black swan event).

* 利润将用于购买多元化抵押品，例如 DGX.io 的金券。这种多元化的抵押品将被用作最后的手段，以防以太的价格崩溃得太快，使得有些头寸在追加保证金前就变得抵押不足（被称为黑天鹅事件）。

* The money will also be used to pay for price feeds from Augur, and to fund infrastructure such as the EtherEx foundation and the Ethereum Foundation, as well as be distributed to MKR holders as dividends.

* 这些资金还将用于支付 Augur 提供的喂价，并为 EtherEx 基金会和以太坊基金会等基础设施提供资金，并作为股息分配给 MKR 持有人。

* Maker can upgrade its own guardian contract, and update vital parameters of the eDollar contract (such as changing the source of price feeds, or changing collateral requirements). To prevent abuse these actions have to be primed with a delay (which can be several months for extremely vital functions), so that users will be able to notice and withdraw their funds from the contract if this power is being misused.

*  Maker 可以升级自己的监护合约，并更新 eDollar 合约的重要参数（例如改变价格反馈的来源或更改抵押品要求）。为了防止滥用，这些措施必须延迟执行（对于极其重要的功能可能需要几个月），以便用户能在注意到这种权力滥用后，先从合约中取回资金。

* To give users some amount of privacy, a simple coinjoin system will be avaiable soon after launch, called Shuffle. This should provide privacy equal to that of Darkcoin, but the eventual goal will be to have a zerocoin level privacy implementation that makes all eDollar transactions 100% anonymous by default.

* 为了给用户一定的隐私，简单的 coinjoin 系统在发布后不久即可使用，称为 Shuffle。这应该能提供与 Darkcoin 相同程度的隐私保护，但最终目标将是实现跟零币（zerocoin）一样的隐私保护，使得默认情况下所有 eDollar 交易能 100％ 匿名。

* Shapeshift will be natively integrated in the UI to allow users to seamlessly send and receive eDollar as bitcoin.

* Shapeshift 将原生集成在用户界面中，允许用户如同比特币一样无缝地发送和接收 eDollar。

* A bunch of features to make life easier for the user will be implemented in the eDollar front end, some based on bitcoin/shapeshift (shopping, debit cards) and some being curated lists of ethereum dapps that accept eDollar (gambling dapps and possibly augur and other prediction markets).

* 一系列让用户更简便的功能将在 eDollar 前端实现，一些基于比特币/shapeshift（购物，借记卡），另一些则是接受 eDollar 的以太坊 dapp 应用的列表（ 赌博应用、可能是 augur 和其他预测市场）。

* eDollar will trade against bitcoin and ether on etherex, and will also trade on a single centralized exchange where high liquidity will be ensured by Maker and the centralized market making company Cryptowall.

* eDollar 将在 etherex 上与比特币和以太坊进行交易，并将在一个由 Maker 和中心化做市商 Cryptowall 来确保高流动性的中心化交易所进行交易。

* other assets can be created by anyone using the same system, but be collateralized by eDollar instead in order to reduce risk (since it's easier to determine the right collateral requirements when the collateral isn't volatile). This opens up the possibility to trade any asset on the ethereum block chain. Maker will initially create and keep liquid AAPL, gold and CNY on EtherEx as a proof of concept that anything can be done as long as there's a price feed.

* 任何使用同一系统的人都可以创建其他资产，但由 eDollar 作为抵押以降低风险（因为抵押品价格稳定更容易确定正确的抵押品要求）。这为在以太坊区块链上交易任何资产开辟了可能。 Maker 将最初在 EtherEx 上创建并保持流动性，苹果股票、黄金和人民币等有喂价的任何东西来作为概念证明。

I made this post and the intentionally hyperbole claims in the hopes that I'll provoke the armchair economists out of the woodwork to start a discussion on how risky this type of pegged asset it, and what other mechanisms can be put in place to minimize the risk. The great effort of convincing dapps to use eDollar has also yet to begin, and there needs to be a community wide discussion on how to handle metacoin deposits to dapps before they can even implement it. In the long run I'm hoping to have an ongoing discussion about every aspect of eDollar, pegged currencies and other ethereum based assets on makerdao.com, so anyone will have easy access to the different arguments and points of view.

我发表这篇文章，并故意夸大其辞，希望我能激怒那些纸上谈兵的经济学家们，从而使得他们能开始讨论这种锚定资产的风险程度，以及可以采取哪些其他机制来最小化风险。说服去中心化应用使用 eDollar 的努力还没有开始，如何在实施它之前处理 metacoin 存款到去中心化应用，还需要在社区进行广泛的讨论。从长远来看，我希望在 makerdao.com 上能够持续讨论有关 eDollar、锚定货币和其他基于以太坊的资产的各个方面，从而让任何人都可以轻易得到不同的论点和观点。
