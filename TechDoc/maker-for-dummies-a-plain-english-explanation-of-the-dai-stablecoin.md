# Maker for Dummies: A Plain English Explanation of the Dai Stablecoin | Maker Dai 稳定币傻瓜简介

> 本文翻译自：https://medium.com/@greg_10160/maker-for-dummies-a-plain-english-explanation-of-the-dai-stablecoin-e4481d79b90

> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [鱼](https://github.com/oscnet)

> 推荐 ： @咕噜 BIHU.COM

> 翻译时间：2017-11-21

![](https://cdn-images-1.medium.com/max/600/1*kqGv5ezNT9bSa9oJUzC2nA.png)

## Summary:

* 1 Dai = $1  

* Maker keeps Dai at $1 using a system of collateral and price feeds. This collateral is carefully managed by the MKR holders and a set of smart contracts.

* MKR holders act as a buyer of last resort.

* Smart Contracts are blockchain magic.

* Maker additionally keeps Dai at $1 using a system of interest rates, also through smart contracts.

* Global settlement provides a final layer of safety.

* You need stablecoins to realize the full potential of blockchain technology.

* Maker also provides decentralized leverage, which is awesome.

## 摘要

* 1 Dai = 1 美元

* Maker 使用抵押和价格反馈系统保持 dai 代币价格固定为 1 美元。抵押品是由 MKR 持有人和一套智能合约仔细管理的。

* MKR 持有人充当最后的买家。

* 智能合约是区块链魔术。

* Maker 另外还通过智能合约利用利率来使用 Dai 保持在1美元。

* 全球结算提供了最后一层安全。

* 您需要 stablecoins 来充分发挥区块链技术的潜力。

* Maker 还提供分散杠杆，这是真棒。

The most common response when someone is asked about the Maker project is: “Well it looks cool, but it’s too complicated and I don’t get it.” The following seeks to simplify how Maker works and to walk you through the system in an ELI5 fashion. I’m even going to write things like “ELI5 = explain it like I’m five,” because that’s how basic this is going to be. This is your parents’ Maker tutorial. If you’re looking for more details, technical explanations, or are just fresh out of books written in Haskell, I recommend the [Purple Paper](https://makerdao.com/assets/documents/purple.pdf).

当人们被问到 Maker 项目时，最常见的回答是：“它看起来很酷，但太复杂，我真看不明白”。本文试图通过简化来说明 Maker 的工作方式，并试图利用时尚的 ELI5 方法来使你了解整个系统，通过对 Maker 做最基本的描述，来达到ELI5（给五岁小孩子的解释）的效果。这也是针对你父母的 Maker 教程。但是如果你需要了解更多的细节、技术说明，或者刚刚读完用 Haskell 编写的书籍，我推荐阅读[紫皮书](https://makerdao.com/assets/documents/purple.pdf)。

## What Product Does Maker Make? | Maker 制造什么产品？

Rather than focus on what Maker is, this explanation focuses on the first product of the Maker organization. This product is called Dai.

想要了解 Maker 是什么，更好的方法是先了解 Maker 组织的第一个产品，Dai.

Dai is type of a stablecoin. The concept of a stablecoin is fairly straight forward — it’s a token (like bitcoin and ether) that exists on a blockchain. But unlike bitcoin or ether, it has no volatility. “How can something have no volatility, volatility is relative!” Good catch. The asset that Dai is trying to be stable relative to is the U.S. Dollar. So, to summarize, one Dai equals one dollar. Dai is set to be the first working consumer-grade stablecoin.

Dai 是稳定币的一种。稳定币的概念非常简单 - 它是一种存在于区块链中代币（如比特币和以太）。但又不像比特币或以太，它没有波动性。“怎么可能存在没有波动的东西呢，波动总是相对的！”说得好。Dai 是试图相对美元保持稳定的资产。所以，总而言之，一 Dai 等于一美元。Dai 将成为第一个工作的消费级稳定币。

![](https://cdn-images-1.medium.com/max/800/0*1YWODlh9hfUrM0uU.)

## But aren’t there already stablecoins? You lied! |现在还没有稳定币吗？你撒谎！

Yes, and no. You’re most likely familiar with stablecoins that hold USD in bank accounts and issue tokens on a blockchain that are ‘backed’ by these dollars. I call this legally-backed crypto, or an IOU coin, because if those bank accounts should ever be frozen or if the accountants defrauded token holders, the stablecoin now becomes an IOU on whatever’s left when they eventually get the bank accounts back (if they ever regain the bank accounts). Relying on the legal system to maintain crypto-tokens inserts an unreliable middle-man into the blockchain.

是的，没有。您最有可能熟悉这一类稳定币：你在银行账户中的美元，及由这些美元“支持”的，在区块链上发行的代币。我称之为合法支持代币或者 IOU 代币，因为如果这些银行账户被冻结或者会计师欺骗了代币持有者，那么当他们最终获得银行账户时（如果他们能重新获得银行账户的话），这些稳定币就成为了欠条。依靠法律制度来维护代币，是把不可靠的中间人带入了区块链。

We can do better. Enter Dai.

Dai 在这方面做得更好。

Maker’s Dai is a stablecoin that lives completely on the blockchain chain with its stability unmediated by the legal system or trusted counterparties.

Maker 的 Dai 是一种完全存在于区块链上，并且其稳定性不需要法律体系或信任方提供中介的稳定币。

## Wait, wait, why do I need a stablecoin in the first place? |但是，等等，为什么我首先需要一个稳定币？

Stablecoins are what allow us to fully realize the promise of blockchain technology. Any application which requires a low threshold of volatility to be viable on a blockchain, consumer loans for example, simply cannot be denominated in a currency which fluctuates 10–20% in a day, like bitcoin and ether. If you’re using bitcoin to send a remittance from one country to another, there’s a good chance that the price movement over the period of one block confirmation (how long it takes the blockchain to include your transaction) will be larger than the fees charged by Western Union or PayPal. If you’re betting on the outcome of a presidential election on Augur and the election isn’t for six months, you don’t want to denominate that bet in ether. Most importantly, stablecoins allow decentralized exchanges (an exchange without a trusted intermediary, where users always maintain full custody their own funds) to denominate trading pairs in US dollars instead of bitcoin or ether. This makes crypto trading more accessible to the average person and puts high-profile hacks, like that of [Mt. Gox](https://www.wired.com/2014/03/bitcoin-exchange/) and [Bitfinex](https://en.wikipedia.org/wiki/Bitfinex_hack), behind us for good.

稳定币能让我们完全实现区块链技术的承诺。任何要求具有较低波动性的区块链应用，例如消费者贷款，肯定不能以每天波动10-20％的货币计价，比如比特币和以太币。如果您使用比特币从一个国家汇款到另一个国家，那么区块确认期间（区块链包含您的交易需要的时间）的价格波动很可能大于西联汇款或贝宝收取的费用。如果你在Augur上打赌总统选举的结果，并且选举不是六个月，那么你肯定不想用以太币来做赌注。最重要的是，稳定币允许去中心化交易所（一种没有信赖中介机构的交易所，用户能始终保持对自己的资金的全面监管）能够以美元而不是比特币或以太币计价来进行交易。这使得代币交易对普通人来说更为容易，并且能防止如[Mt. Gox](https://www.wired.com/2014/03/bitcoin-exchange/)和[Bitfinex](https://en.wikipedia.org/wiki/Bitfinex_hack)之类的黑客攻击。


## So how does the Maker system function? |那么 Maker 系统如何运作呢？

This is going to be the most challenging part of this tutorial. To understand how Maker creates the stability for the Dai token requires a bit of background about blockchains and specifically, ethereum. I’ll put some quick definitions next to some of the words you may not understand. If you do have this foreknowledge, that’s great and you’re going to love the elegance of the Maker system. Let’s begin:

这将是本教程中最具挑战性的部分。要理解 Maker 如何保持 Dai 代币的稳定性，需要一些关于区块链和特定的以太坊的背景知识。我会在你可能不了解的一些术语旁加上一些简短的说明。如果你确实懂得这些预备知识，那很棒，你会爱上 Maker系统的优雅。让我们开始：

Note: If you’re simply a consumer, you do not need to understand the following explanation outside of your own curiosity. If you just want to buy Dai, you’ll be able to trade it for dollars, won, bitcoin, ether, and other currencies on a variety of exchanges.

注意：如果你只是一个消费者，除了好奇，你可能不需要理解下面的内容。如果您想购买 Dai 币，您可以在各种交易所上以美元，韩元，比特币，以太币和其他货币进行购买。

Dai (Maker’s stablecoin) is backed by collateral (ether to be specific). Let’s say you’re an ether holder and you would like to create Dai. Your first move would be to send your ether to a “collateralized debt position” known in shorthand as a CDP. A CDP is a type of software that runs on the blockchain, in this case the ethereum blockchain, and lives within the Maker ecosystem. This software is called a smart contract, but don’t overthink that name too much.

Dai（Maker的稳定币）是由抵押品（具体来说如以太）支持的。如果你是以太币持有者，你就可以创造 Dai 币。你的第一个举动就是把你的以太坊发送到一个“担保债务头寸”上，简称 CDP。CDP是一种在区块链上运行的软件，在这种情况下是以太坊区块链，并且存在于 Maker 生态系统中。这个软件被称为智能合约，但不要对这个名称有过多地想法。

## STOP, you lost me! |停，等等我！

If you understood everything above, skip this part. If you find yourself a bit confused, let’s break this down into smaller pieces and an analogy!

如果你理解了上面的一切，就可以跳过这一部分阅读。如果你觉得自己还有些困惑，那我就把它分解成更小的片断和比喻！

## What is the basis of the Maker ecosystem? |Maker生态系统的基础是什么？

The entire Maker ecosystem is built on “smart contracts” like a CDP, the smart contract mentioned above. A blockchain lets you do things by yourself where you used to need a middleman. Much like the internet lets you share information without a middleman, blockchains let you share value without a middleman. Bitcoin was the first network to put this concept to use, its core premise being that you can send bitcoins from Point A to Point B without having to trust anyone but yourself. All trust is vested in the blockchain, which isn’t controlled by anyone. Ethereum took this concept a step further and allows users to add instructions to these transfers.That’s how the smart contract was born. Now you can say: “Send my ether from Point A to Point B on this date, at this time, and with these special instructions.”

整个 Maker 生态系统是建立在“智能合约”上的，如上述的CDP智能合约。区块链能让您独立完成一些通常需要中间商的事情。就像互联网让你不通过中间人直接分享信息，区块链让你不通过中间商分享价值， 比特币是第一个使用这个概念的网络，它的核心前提是您可以从点A到点B发送比特币，且除了您自己不必信任何其它人。所有信任归于区块链，且不受任何人控制。以太坊使这一概念更进一步，并允许用户为这些交易添加指令。这就是智能合约的诞生。现在你可以说：“在这天，这时候，把我的以太从A点发送到B点，并且附加有这些特别的指令。”

## So, how does Maker use smart contracts to create a stablecoin? | 那么，Maker 如何使用智能合约来创建一个稳定币？

![](https://cdn-images-1.medium.com/max/800/0*Vw2mUUL4KboG-7bi.)
<center>I knew a pile of money would get your attention… 我就知道一堆钱会引起你的注意</center>

The core smart contract at Maker is the CDP. Let’s use an analogy to describe these. Pretend you are at the bank asking for a home equity loan. You put up your house as collateral and they give you cash as a loan in return. If the value of your house decreases, they’re going to ask you to pay the loan back. If you can’t pay the loan back, they’re going to take your house. To bring this back to Maker, just replace your house with ether, the bank with a smart contract, and the loan with Dai. That’s all there is to it. You give the Maker CDP smart contract your ether and it lets you take out a loan in Dai. If the value of your ether goes below a certain threshold, you either have to pay back the smart contract as you would a bank or it will auction off your ether to the highest bidder.

Maker 的核心智能合约是 CDP。我们用一个类比来说明。假设你在银行请求房屋贷款。你把你的房子当作抵押物，来换取他们的现金贷款。如果房价下跌，他们就会要求你偿还贷款。如果你不能偿还贷款，他们就会拿走你的房子。对于 Maker 来说, 就是用以太来代替房子，用智能合约代替银行，Dai 就是贷款。就这样，你把以太交给 CDP 智能合约，然后你就可以取走你的 Dai 贷款。如果你的以太币的价值低于一个特定的值，你就必须像银行一样偿还 Dai，否则它会把你的以太拍卖给出价最高者。

In summary, **CDPs are simply where the collateral (ether) in the Maker system is held**.

总之，**CDP 只是 Maker 系统中的保存抵押品（以太）的地方**。

Once your ether is in the CDP smart contract, you are able to create Dai. The amount of Dai you can create is relative to how much ether you have put into the CDP. This ratio is fixed, but can be changed over time. The amount of Dai I can create relative to the ether I put in is called the collateralization ratio.

一旦你的以太投入 CDP 智能合约，你就可以创造出 Dai。你可以创造的 Dai 数量于你在 CDP 中投入以太数量成正比。这个比例是固定的，但可以随时间变化。Dai 数量与投入的以太数量比称为抵押比率。

Let’s say ether is worth $100 right now and the collateralization ratio is 150%. If I send 1 ether ($100) into the CDP smart contract, then I am now able to create 66 Dai. This means that, at the current value of ether, each 100 Dai that I’ve created is backed by 1.5 ether collateral. In the Maker system, you don’t lose your ether, but you also no longer control it. The ether that you sent to the CDP is stuck there until you pay back the 66 Dai (this destroys the Dai). The following diagram helps to visualize how you can open and close a CDP. Try to follow along with “your wallet” as actions are performed above. This diagram is somewhat simplified. For instance, a CDP doesn’t really sit in your wallet. It also removes a couple steps that are necessary for the more advanced aspects of the system, but ultimately irrelevant to you as a Dai borrower.

假设以太现在价值100美元，抵押比率为150％。如果我把1个以太（100美元）送到 CDP 智能合约，那么我现在可以创造 66 个 Dai。这意味着，在以太的当前价值下，我创造的每一百个 Dai 都有1.5个以太币抵押。在 Maker 系统中，你不会失去你的以太，但你也不再能使用它。你发给 CDP 的以太将冻结直到你还清 66 个 Dai（此操作将销毁这些 Dai 币）。下图帮助您了解如何打开和关闭 CDP。按照图中所示，尝试使用“您的钱包”执行操作。这个图有些简化。例如，一个 CDP 并不真正在你的钱包里。它也消除了某些高级系统所需的几个步骤，但是这些最终与你作为一个 Dai 借用者无关。

![](https://cdn-images-1.medium.com/max/800/0*hQXqxfslCn53_3-y.)
<center>Opening and closing a CDP while creating/destroying dai.打开和关闭 CDP，同时创建/销毁 Dai 币。</center>

## What about the stability of Dai? | Dai 的稳定性如何呢？

If the price of ether never fluctuated, it alone would ensure Dai’s stability (and we would not need Dai in the first place). But the price of ether varies so we need to account for that.

如果以太的价格从未波动，它自己就能保证 Dai 的稳定（这样我们也不需要 Dai了）。但是以太网的价格肯定会不同，所以我们需要考虑这一点。

By the way, if all you wanted to do was learn how to interact with the system, you can quit here!

顺便说一句，如果你只想学习如何与系统交互，你可以在这里退出阅读！

## What happens if the value of ether goes down? |如果以太的价值下降会发生什么？

There’s not much need to address what happens when ether goes up.The system becomes more collateralized and Dai becomes stronger. That’s not to say that Dai can’t become too strong, where there’s more demand for Dai than there is people willing to create it, but Maker has mechanisms that incentivize users to create more Dai if the price of Dai should trade above one dollar (see below: Target Rate Feedback Mechanism).But if ether goes down, now that can cause problems. If the value of ether held as collateral is worth less than the amount of Dai it’s supposed to be backing, then Dai would not be worth one dollar and the system could collapse. **Maker combats this by liquidating CDPs and auctioning off the ether inside before the value of the ether is less than the amount of Dai it is backing**. Basically, if the price feed into the CDP indicates that the value of ether has gone below a certain threshold (let’s use 125% of created Dai), then the CDP is “liquidated” and the ether inside the CDP is auctioned off for Dai until there is enough Dai to pay back what was extracted from the CDP. Let’s go back to the diagram to see how this works. As before, I’ve simplified some of the steps for the sake of understanding, there are some additional features in the system that prevent various edge-case attacks.

没有太多的需要解决以太上涨时会发生什么事情。抵押物越多，Dai 币就越强壮。这并不是说 Dai 不能变得强大，对 Dai 币的需求比有人愿意创造的要多，但是如果 Dai 的价格超过一美元，那么 Maker 就有激励用户创造更多 Dai 币的机制(见下图：目标利率反馈机制），但如果以太下跌，现在是可能会导致问题。如果作为抵押品的以太的价值低于 Dai 的价值，那么Dai将不值一美元，系统就可能崩溃。** 在以太的价值少于它支持的 Dai 币的价值前，Maker 通过清理 CDP 和拍卖以太来应对这种情况**。基本上，如果在 CDP 中以太的价格已经低于一定的阈值（我们使用创造的 Dai 的125％），那么 CDP 被“清算”，并且 CDP 中的以太被拍卖，直到有足够的 Dai 币来偿还从 CDP 中提取的东西。让我们回到图表来看看这是如何工作的。和以前一样，为了理解，我简化了一些步骤，系统中还有一些附加功能用以防止各种边缘攻击。
![](https://cdn-images-1.medium.com/max/800/0*1PMi1hf9kkFRcVDy.)
<center>A CDP being liquidated due to insufficient collateral. CDP 由于抵押物不足而被清盘。</center>

See? Simple enough. The system liquidates your collateral and gives it away if don’t return the Dai you’ve borrowed to the CDP quickly enough. This ensures that Dai always has sufficient collateralization.

看到？很简单。如果不及时将借给你的 Dai 还给 CDP，系统就会拍卖掉你的的抵押物。这确保了 Dai 总有足够的抵押。

## Plucking the black swan — What’s the MKR token? |摘下黑天鹅 - 什么是 MKR 令牌？

![](https://cdn-images-1.medium.com/max/800/0*OR_GJlMt0QCNx2jP.)
<center>Behold, the most feared creature in finance.看哪，财务上最可怕的动物来了。</center>

If you’ve been scrutinizing the system for flaws, it probably didn’t take you long to find one. It’s the possibility of a dreaded “black swan event.” It would involve a situation where the price of ether crashes well below the one-to-one collateralization ratio in a time frame too short for the system to handle. Fortunately, Maker has a solution for situations like this: MKR, or makercoin. MKR is a token on the ethereum blockchain (like the rest of the Maker ecosystem) that has governance rights over the Maker smart contracts. For instance, the number used in the above examples (the collateralization rate of CDPs) is set by a vote of MKR holders. In return for regulating the system, MKR holders are rewarded with fees. There is, however, a catch to being a MKR holder. They function as the buyer of last resort. Should the collateral in the system not be enough to cover the amount of Dai in existence, MKR is created and sold onto the open market in order to raise the additional collateral. This provides a strong incentive for MKR holders to responsibly regulate the parameters at which CDPs can create Dai, as it will ultimately be their money on the line should the system fail, not holders of Dai. I could write a lot more about the mechanics and role of MKR, but that’s a subject for a different post.

如果你一直在仔细研究这个系统的缺陷，那么可能不需要很长时间就能找到一个。这可能是一个可怕的“黑天鹅事件”。这涉及到在一个系统无法处理的极短的时间内，以太的价格大大低于一对一抵押比率的情况。幸运的是，Maker 为这样的情况提供了解决方案：MKR 或者 makercoin。MKR 是以太坊区块链上的代币（与 Maker 生态系统的其他部分一样），具有 Maker 智能合约的治理权限。例如，上述例子中使用的数字（CDP 的抵押率）由 MKR 持有者的投票决定。作为管理系统的回报，MKR持有者将获得奖励。然而，成为一名 MKR 持有者是一个难题。他们作为最后的手段买家。如果系统中的抵押品不足以覆盖现存的数额，MKR 就会被创建并出售到公开市场上，以提高额外的抵押品。这为 MKR 持有者提供了一个强有力的激励机制，可以负责任地规范 CDP 可以创造 Dai 的参数，因为如果系统失败，它们最终会成为他们的钱，而不是 Dai 的持有者。我可以写更多关于 MKR 的机制和角色，但这是另一个帖子的主题。

## Keeping in line with USD: What’s the Target Rate Feedback Mechanism? |与美元保持一致：目标利率反馈机制是什么？

So far I’ve addressed the fundamental stability of the Maker system, but we haven’t spoken about the incentives that are in place to keep one Dai equal to one dollar. This is called the Target Rate Feedback Mechanism [TRFM], and to be honest it’s quite complex. The important thing to know is the following: When Dai trades over $1, the smart contracts incentivize the creation of Dai. When Dai trades less than $1, the smart contracts incentivize the destruction of Dai. This is accomplished with a process that’s similar to the way a central bank uses interest rates to control the money supply. You can read the [Whitepaper](https://github.com/makerdao/docs/blob/master/Dai.md) for more details on how the system actually functions.

到目前为止，我已经解决了制造者制度的基本稳定问题，但是我们没有谈到保持壹代等于一美元的激励措施。这被称为目标利率反馈机制（TRFM），说实话这是相当复杂的。重要的是知道以下几点：当戴氏交易超过1美元时，智能合约激励戴的创造。当戴的交易不到1美元时，聪明的合同激励了戴的破坏。这是通过一个类似于中央银行利率来控制货币供应量的过程来实现的。您可以阅读白皮书以获取有关系统实际功能的更多详细信息。


## A final protection — What’s Global Settlement? | 最后的保护 - 什么是全球和解？

Despite being developed over the course of three years by some of the best developers in the blockchain space, enduring a rigorous byte-code level audit, and having a working developer-focused stablecoin (Sai) on the mainnet for several months without incident, we all know that nothing is perfect. To keep the system as secure as possible and prevent what cannot be foreseen, the Maker team has added a process called global settlement. When global settlement is triggered, the entire system freezes and all holders of Dai and CDPs are returned the underlying collateral. So, if a global settlement is triggered and I hold 100 Dai, and one ether is worth $100, I can exchange my 100 Dai directly for one ether right through a smart contract. The collateral held in CDPs will be similarly released to its owners. A global settlement can be triggered by a select group of trusted individuals who hold the global settlement keys. If these signatories see something going horribly wrong, they will enter their keys initiate the process of gracefully winding down the system. “But doesn’t that make this….CENTRALIZED?!”

尽管三年来由区块链领域的一些最优秀的开发人员进行了开发，经历了严格的字节码级审计，并且在主网上有一个以开发人员为中心的稳定币（Sai）工作了好几个月，都知道没有什么是完美的。为了尽可能保持系统安全并防止无法预见，Maker团队添加了一个名为“全球结算”的进程。当全球结算被触发时，整个系统冻结，傣族和CDP的所有持有者被归还的基础抵押品。所以，如果全球和解得以触发，我就拥有100个戴，一个以上的价值100美元，我可以通过一个智能合约直接换100个戴尔。CDP所持有的抵押品也将同样向其所有者公布。一个全球结算可以由一组持有全球结算密钥的可信人员触发。如果这些签署者看到有什么可怕的错误，他们将进入他们的钥匙，启动优雅地结束系统的过程。“但这不是让这个......集中？！”

![](https://cdn-images-1.medium.com/max/800/0*WxxF63UgU_Iu1d9s.)

No, it doesn’t. The only thing a global settlement can do is give you back your collateral. It can’t steal your ether or Dai or interact with the system on your behalf. The worst case scenario in a global settlement is that you end up being exposed to the volatility of your collateral until the system is fixed or you can send it to an exchange.

不，不。全球解决办法唯一可以做的就是回馈你的抵押品。它不能偷你的以太或傣族或代表你与系统互动。全球结算中最糟糕的情况是您最终将面临抵押物的波动，直到系统固定，或者您可以将其发送给交易所。

## Bonus feature: decentralized leverage?! | 奖金功能：分散杠杆？

The more savvy among you may have noticed an interesting consequence of the Dai creation process. Volatility cannot be destroyed, it can only be transferred. If we have a stable token like Dai that has been stripped of its volatility, where did it go? In the Maker system, volatility is transferred entirely to the holder of the CDP. Using our prior example, should I withdraw 66 Dai from a CDP containing one ether, I will only own that one ether if its price is above the liquidation ratio. Dai is effectively a loan on my ether.

你们中间越聪明的人，也许会注意到傣族创造过程的一个有趣的结果。波动不能被破坏，只能转移。如果我们有一个像戴的稳定的标志，被剥夺了它的波动性，那么它到底在哪里呢？在制造商体系中，波动性完全转移给CDP的持有者。用我们以前的例子，我应该从一个含有一个乙醚的CDP中提取66代，如果它的价格高于清算比例，我将只拥有一个乙醚。戴实际上是对我以太的贷款。

This leads us to the interesting consequence: **I can take the Dai that I borrowed and use it to buy more ether**. By doing this, I am basically buying ether on margin. That’s right, completely decentralized leverage! Now when you trade on a decentralized exchange that has integrated with Maker, you’ll be able to bet on the price of ether with 2x, 3x, or more funds than you actually have.

这导致了我们有意思的后果：我可以把我借的傣族用来买更多的乙醚。通过这样做，我基本上是以保证金购买乙醚。没错，完全分散的杠杆作用！现在，当您在与Maker整合的分散型交易所进行交易时，您可以用比您实际拥有的2x，3x或更多资金押注乙醚的价格。

## Conclusion | 结论

I call the Maker Dai stablecoin the first working consumer-grade stablecoin because it stands out from both its predecessors and competitors. It is going to be the first application, in a series of many, that brings blockchain technology to the masses. If you want to dive deeper, head over to https://makerdao.com/.

我把Maker Dai stablecoin称为第一个消费级稳定币，因为它从前辈和竞争对手中脱颖而出。这将是第一个将区块链技术带到大众市场的应用程序。如果您想深入了解，请前往https://makerdao.com/。

----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

鱼 区块链技术爱好者， 欢迎加微信号oscnet交流。

本文由币乎社区（bihu.com）内容支持计划赞助。

版权所有，转载需完整注明以上内容。

----------------------------------------------------
