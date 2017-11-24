# Maker for Dummies: A Plain English Explanation of the Dai Stablecoin | Maker 的稳定币贷券傻瓜式简介

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

* 1 Dai (贷券) = 1 美元

* Maker 使用抵押物及价格反馈系统来保持1贷券价格固定为 1 美元。其抵押物由 MKR 持有人和智能合约协同精细管理。

* MKR 持有人将充当最后的买家。

* 智能合约是区块链的魔术。

* Maker 额外地还通过智能合约，使用利率反馈机制来使贷券价值稳定在1美元。

* 全球结算提供了最后的安全保证。

* 我们需要稳定币来充分发挥区块链技术的潜力。

* Maker 还能提供去中心化的杠杆交易功能，这可真棒。

The most common response when someone is asked about the Maker project is: “Well it looks cool, but it’s too complicated and I don’t get it.” The following seeks to simplify how Maker works and to walk you through the system in an ELI5 fashion. I’m even going to write things like “ELI5 = explain it like I’m five,” because that’s how basic this is going to be. This is your parents’ Maker tutorial. If you’re looking for more details, technical explanations, or are just fresh out of books written in Haskell, I recommend the [Purple Paper](https://makerdao.com/assets/documents/purple.pdf).

当人们被问到 Maker 项目时，最常见的回答是：“它看起来很酷，但太复杂，我真看不明白”。本文试图简明扼要地描述 Maker 的工作方式，并利用时尚的 ELI5 （给五岁小孩子的解释）方法来使你了解整个系统，通过对 Maker 最基本的描述，来试图达到ELI5的效果。同时也是针对你父母的 Maker 教程。但是如果你需要了解更多的细节、技术说明，或者你刚刚读完用 Haskell 编写的书籍，我推荐阅读[紫皮书](https://makerdao.com/assets/documents/purple.pdf)。

## What Product Does Maker Make? | Maker 创造了什么产品？

Rather than focus on what Maker is, this explanation focuses on the first product of the Maker organization. This product is called Dai.

想要了解 Maker，更好的方法是先了解 Maker 组织的第一个产品---贷券.

Dai is type of a stablecoin. The concept of a stablecoin is fairly straight forward — it’s a token (like bitcoin and ether) that exists on a blockchain. But unlike bitcoin or ether, it has no volatility. “How can something have no volatility, volatility is relative!” Good catch. The asset that Dai is trying to be stable relative to is the U.S. Dollar. So, to summarize, one Dai equals one dollar. Dai is set to be the first working consumer-grade stablecoin.

贷券是稳定币的一种。稳定币的概念非常简单 - 它是一种存在于区块链中的代币（如比特币和以太）。但又不像比特币或以太，它没有波动性。“怎么可能存在没有波动的东西呢，波动总是相对的！”这话说得好。贷券是试图相对美元保持稳定的资产。所以，总而言之，一个贷券等于一美元。贷券将成为第一个运作的消费级稳定币。

![](https://cdn-images-1.medium.com/max/800/0*1YWODlh9hfUrM0uU.)

## But aren’t there already stablecoins? You lied! | 现在还没有稳定币吗？你撒谎！

Yes, and no. You’re most likely familiar with stablecoins that hold USD in bank accounts and issue tokens on a blockchain that are ‘backed’ by these dollars. I call this legally-backed crypto, or an IOU coin, because if those bank accounts should ever be frozen or if the accountants defrauded token holders, the stablecoin now becomes an IOU on whatever’s left when they eventually get the bank accounts back (if they ever regain the bank accounts). Relying on the legal system to maintain crypto-tokens inserts an unreliable middle-man into the blockchain.

是的，没有。您最有可能熟悉这一类稳定币：你在银行账户中的美元，或由这些美元“支撑”的，在区块链上发行的代币（如USDT,译者加）。我称之为法币支撑币或者 IOU 代币，因为如果这些银行账户被冻结或者会计师欺骗了代币持有者，那么最终当他们的账户解冻时（如果他们的银行账户能解冻的话），这类稳定币就成为了欠条。**依靠法律制度来维护代币，就是把不可靠的中间人带入了区块链**。

We can do better. Enter Dai.

贷券在这方面做得更好。

Maker’s Dai is a stablecoin that lives completely on the blockchain chain with its stability unmediated by the legal system or trusted counterparties.

Maker 的贷券是一种完全存在于区块链上，并且其稳定性不需要法律体系或信任方提供中介的稳定币。

## Wait, wait, why do I need a stablecoin in the first place? |但是，等等，为什么我们首先需要一个稳定币？

Stablecoins are what allow us to fully realize the promise of blockchain technology. Any application which requires a low threshold of volatility to be viable on a blockchain, consumer loans for example, simply cannot be denominated in a currency which fluctuates 10–20% in a day, like bitcoin and ether. If you’re using bitcoin to send a remittance from one country to another, there’s a good chance that the price movement over the period of one block confirmation (how long it takes the blockchain to include your transaction) will be larger than the fees charged by Western Union or PayPal. If you’re betting on the outcome of a presidential election on Augur and the election isn’t for six months, you don’t want to denominate that bet in ether. Most importantly, stablecoins allow decentralized exchanges (an exchange without a trusted intermediary, where users always maintain full custody their own funds) to denominate trading pairs in US dollars instead of bitcoin or ether. This makes crypto trading more accessible to the average person and puts high-profile hacks, like that of [Mt. Gox](https://www.wired.com/2014/03/bitcoin-exchange/) and [Bitfinex](https://en.wikipedia.org/wiki/Bitfinex_hack), behind us for good.

稳定币能让我们完美实现我们对区块链技术的愿景。任何要求具有较低波动性的区块链应用，例如消费者贷款，肯定不能以每天波动10-20％的货币计价，比如比特币和以太币。如果您使用比特币从一个国家汇款到另一个国家，那么区块确认期间（区块链包含您的交易需要的时间）的价格波动很可能大于西联汇款或贝宝收取的费用。如果你在Augur上打赌总统选举的结果，并且选举持续六个月，那么你肯定不想用以太币来做赌注。最重要的是，稳定币允许去中心化交易所（一种没有信赖中介机构的交易所，用户能始终保持对自己的资金的全面监管）能够以美元而不是比特币或以太币计价来进行交易。这使得代币交易对普通人来说更为容易，并且能防止如[Mt. Gox](https://www.wired.com/2014/03/bitcoin-exchange/)和[Bitfinex](https://en.wikipedia.org/wiki/Bitfinex_hack)之类的黑客攻击。


## So how does the Maker system function? |那么 Maker 系统如何运作呢？

This is going to be the most challenging part of this tutorial. To understand how Maker creates the stability for the Dai token requires a bit of background about blockchains and specifically, ethereum. I’ll put some quick definitions next to some of the words you may not understand. If you do have this foreknowledge, that’s great and you’re going to love the elegance of the Maker system. Let’s begin:

这将是本教程中最具挑战性的部分。要理解 Maker 如何保持贷券的稳定性，需要一些关于区块链和特定的以太坊的背景知识。我会在你可能不了解的一些术语旁加上一些简短的说明。如果你确实懂得这些预备知识，那很棒，你会爱上 Maker 系统的优雅。让我们开始：

Note: If you’re simply a consumer, you do not need to understand the following explanation outside of your own curiosity. If you just want to buy Dai, you’ll be able to trade it for dollars, won, bitcoin, ether, and other currencies on a variety of exchanges.

注意：如果你只是一个消费者，除了好奇，你可能不需要理解下面的内容。如果您想购买贷券，您可以在各种交易所上以美元，韩元，比特币，以太币和其他货币进行购买。

Dai (Maker’s stablecoin) is backed by collateral (ether to be specific). Let’s say you’re an ether holder and you would like to create Dai. Your first move would be to send your ether to a “collateralized debt position” known in shorthand as a CDP. A CDP is a type of software that runs on the blockchain, in this case the ethereum blockchain, and lives within the Maker ecosystem. This software is called a smart contract, but don’t overthink that name too much.

贷券（Maker 的稳定币）是由抵押物（具体来说如以太）来支撑的。如果你是以太币持有者，你就可以印制贷券。首先你得把以太发送到一个“担保债务头寸”（简称 CDP）上。CDP 是一种在区块链上运行的软件，这种情况下是以太坊区块链，并且存在于 Maker 生态系统中。这个软件被称为智能合约，但不要对这个名称有过多地联想。

## STOP, you lost me! |停，跟不上了！

If you understood everything above, skip this part. If you find yourself a bit confused, let’s break this down into smaller pieces and an analogy!

如果你理解了上面的一切，就可以跳过这一部分阅读。如果你觉得自己还是有些困惑，那我就把它分解成更小的片断和比喻来说明！

## What is the basis of the Maker ecosystem? |Maker 生态系统的基础是什么？

The entire Maker ecosystem is built on “smart contracts” like a CDP, the smart contract mentioned above. A blockchain lets you do things by yourself where you used to need a middleman. Much like the internet lets you share information without a middleman, blockchains let you share value without a middleman. Bitcoin was the first network to put this concept to use, its core premise being that you can send bitcoins from Point A to Point B without having to trust anyone but yourself. All trust is vested in the blockchain, which isn’t controlled by anyone. Ethereum took this concept a step further and allows users to add instructions to these transfers.That’s how the smart contract was born. Now you can say: “Send my ether from Point A to Point B on this date, at this time, and with these special instructions.”

整个 Maker 生态系统是建立在“智能合约”上的，如上述的 CDP 智能合约。区块链能让您独立完成一些通常需要中间商的事情。就像互联网让你不通过中间人直接分享信息，区块链让你不通过中间商分享价值， 比特币是第一个使用这个概念的网络，它的核心前提是您可以从点 A 到点 B 发送比特币，且除了您自己不必信任何其它人。所有信任归于区块链，且不受任何人控制。以太坊使这一概念更进一步，并允许用户为这些交易添加指令。这就是智能合约的诞生。现在你可以说：“此日此时，请把我的以太从 A 点发送到 B 点，并且附加这些特别的指令。”

## So, how does Maker use smart contracts to create a stablecoin? | 那么，Maker 如何使用智能合约来创建一个稳定币？

![](https://cdn-images-1.medium.com/max/800/0*Vw2mUUL4KboG-7bi.)
<center>I knew a pile of money would get your attention...
我就知道一大堆钱才会引起你的注意...</center>

The core smart contract at Maker is the CDP. Let’s use an analogy to describe these. Pretend you are at the bank asking for a home equity loan. You put up your house as collateral and they give you cash as a loan in return. If the value of your house decreases, they’re going to ask you to pay the loan back. If you can’t pay the loan back, they’re going to take your house. To bring this back to Maker, just replace your house with ether, the bank with a smart contract, and the loan with Dai. That’s all there is to it. You give the Maker CDP smart contract your ether and it lets you take out a loan in Dai. If the value of your ether goes below a certain threshold, you either have to pay back the smart contract as you would a bank or it will auction off your ether to the highest bidder.

CDP 是 Maker 的核心智能合约。我们用一个类比来说明。假设你在银行请求房屋贷款。你把你的房子当作抵押物，来换取他们的现金贷款。如果认后房价大跌，他们就会要求你偿还贷款。如果你不能偿还贷款，他们就会拿走你的房子的所有权。对于 Maker 来说, 就是用以太来代替房子，用智能合约代替银行，贷券就是贷款。就这样，你把以太交给 CDP 智能合约，然后你就可以取走你的贷款（贷券）。假如以太币的价值低于某一个特定值，你就必须像银行一样偿还贷券，否则它会把你的以太拍卖给出价最高者。

In summary, **CDPs are simply where the collateral (ether) in the Maker system is held**.

总之，**CDP 只是 Maker 系统中的保存抵押品（以太）的地方**。

Once your ether is in the CDP smart contract, you are able to create Dai. The amount of Dai you can create is relative to how much ether you have put into the CDP. This ratio is fixed, but can be changed over time. The amount of Dai I can create relative to the ether I put in is called the collateralization ratio.

一旦把你的以太发送到 CDP 智能合约，你就可以创建印制贷券。你可以得到的贷券数量跟你在 CDP 中投入的以太数量成正比。这个比例是固定的，但可能随时间变化。投入的以太数量与贷券数量比称为抵押比率。

Let’s say ether is worth $100 right now and the collateralization ratio is 150%. If I send 1 ether ($100) into the CDP smart contract, then I am now able to create 66 Dai. This means that, at the current value of ether, each 100 Dai that I’ve created is backed by 1.5 ether collateral. In the Maker system, you don’t lose your ether, but you also no longer control it. The ether that you sent to the CDP is stuck there until you pay back the 66 Dai (this destroys the Dai). The following diagram helps to visualize how you can open and close a CDP. Try to follow along with “your wallet” as actions are performed above. This diagram is somewhat simplified. For instance, a CDP doesn’t really sit in your wallet. It also removes a couple steps that are necessary for the more advanced aspects of the system, but ultimately irrelevant to you as a Dai borrower.

假设以太现在价值100美元，抵押比率为150％。如果我把1个以太（100美元）送到 CDP 智能合约，那么我现在可以印制 100/1.5 = 66.66 个贷券。这意味着，在以太的当前价值下，我创造的每 100 个贷券都有 1.5 个以太币抵押。在 Maker 系统中，虽然你不会失去你的以太，但你也不再能使用它。你发给 CDP 的以太将冻结直到你还清 66.66 个贷券（此操作实际将销毁这些贷券）。下图帮助您了解如何打开和关闭 CDP。按照图中所示，尝试使用“您的钱包”执行操作。这个图例做了些简化。例如， CDP 其实并不在你的钱包里。它也去除了某些高级系统所必需的几个步骤，但是这些最终与你作为一个贷券借用者无关。

![](https://cdn-images-1.medium.com/max/800/0*hQXqxfslCn53_3-y.)
<center>Opening and closing a CDP while creating/destroying dai.打开和关闭 CDP，同时创建/销毁贷券。</center>

## What about the stability of Dai? | 贷券的稳定性？

If the price of ether never fluctuated, it alone would ensure Dai’s stability (and we would not need Dai in the first place). But the price of ether varies so we need to account for that.

如果以太的价格从未波动，它自己就能保证贷券的稳定（这样我们也不需要贷券了）。但是以太的价格肯定会变动，所以我们需要思考这一点。

By the way, if all you wanted to do was learn how to interact with the system, you can quit here!

顺便说一句，如果你只想学习如何与系统交互，你可以在这里退出阅读！

## What happens if the value of ether goes down? |如果以太的价格下跌会怎样？

There’s not much need to address what happens when ether goes up.The system becomes more collateralized and Dai becomes stronger. That’s not to say that Dai can’t become too strong, where there’s more demand for Dai than there is people willing to create it, but Maker has mechanisms that incentivize users to create more Dai if the price of Dai should trade above one dollar (see below: Target Rate Feedback Mechanism).But if ether goes down, now that can cause problems. If the value of ether held as collateral is worth less than the amount of Dai it’s supposed to be backing, then Dai would not be worth one dollar and the system could collapse. **Maker combats this by liquidating CDPs and auctioning off the ether inside before the value of the ether is less than the amount of Dai it is backing**. Basically, if the price feed into the CDP indicates that the value of ether has gone below a certain threshold (let’s use 125% of created Dai), then the CDP is “liquidated” and the ether inside the CDP is auctioned off for Dai until there is enough Dai to pay back what was extracted from the CDP. Let’s go back to the diagram to see how this works. As before, I’ve simplified some of the steps for the sake of understanding, there are some additional features in the system that prevent various edge-case attacks.

当以太上涨时，我们并不需要做得太多。因为抵押物价值越高，贷券就越强势。这并不是说贷券不能变得强势，意味着对贷券的需求比贷券印制出来的要多，但是如果贷券的价格超过一美元，那么 Maker 就有激励用户印制更多贷券的机制(见下图：目标利率反馈机制），但如果以太下跌，那么就可能会导致问题。如果作为抵押品的以太的价值低于贷券的价值，那么贷券将不值一美元，系统就可能崩溃。**在以太的价值少于它所支撑的贷券的价值前，Maker 通过清理 CDP 和拍卖以太来应对这种情况**。基本上，如果在 CDP 中以太的价格已经低于一定的阈值（我们使用印制的贷券的125％），那么 CDP 将被“清算”， CDP 中的以太被拍卖，一直到有足够的贷券偿还 CDP。让我们回到图表来看看这时是如何工作的。和前面一样，为了便于理解，我简化了一些步骤，实际上系统还有一些附加功能用以防止各种边缘攻击。
![](https://cdn-images-1.medium.com/max/800/0*1PMi1hf9kkFRcVDy.)
<center>A CDP being liquidated due to insufficient collateral. 由于抵押物不足，CDP被清算。</center>

See? Simple enough. The system liquidates your collateral and gives it away if don’t return the Dai you’ve borrowed to the CDP quickly enough. This ensures that Dai always has sufficient collateralization.

明白了吗？这个很简单。如果不及时将借给你的贷券还给 CDP，系统就会拍卖掉你的的抵押物。这确保了贷券总是有足够的抵押。

## Plucking the black swan — What’s the MKR token? |避免黑天鹅事件 - 什么是 MKR 令牌？

![](https://cdn-images-1.medium.com/max/800/0*OR_GJlMt0QCNx2jP.)
<center>Behold, the most feared creature in finance.看，财经领域最可怕的动物。</center>

If you’ve been scrutinizing the system for flaws, it probably didn’t take you long to find one. It’s the possibility of a dreaded “black swan event.” It would involve a situation where the price of ether crashes well below the one-to-one collateralization ratio in a time frame too short for the system to handle. Fortunately, Maker has a solution for situations like this: MKR, or makercoin. MKR is a token on the ethereum blockchain (like the rest of the Maker ecosystem) that has governance rights over the Maker smart contracts. For instance, the number used in the above examples (the collateralization rate of CDPs) is set by a vote of MKR holders. In return for regulating the system, MKR holders are rewarded with fees. There is, however, a catch to being a MKR holder. They function as the buyer of last resort. Should the collateral in the system not be enough to cover the amount of Dai in existence, MKR is created and sold onto the open market in order to raise the additional collateral. This provides a strong incentive for MKR holders to responsibly regulate the parameters at which CDPs can create Dai, as it will ultimately be their money on the line should the system fail, not holders of Dai. I could write a lot more about the mechanics and role of MKR, but that’s a subject for a different post.

如果你一直在仔细研究这个系统的缺陷，相信不需要很长时间，就能找到。这很可能是一个可怕的“黑天鹅事件”。在一个系统无法处理的，极短的时间内，如果以太的价格出现大大低于一对一抵押率的状况。幸运的是，Maker 为这样的状况提供了解决方案：MKR 或者 makercoin。MKR 是以太坊区块链上的代币（与 Maker 生态系统的其他部分一样），它具有对 Maker 智能合约的治理权限。例如，上述例子中使用的比率（ CDP 的抵押率）由 MKR 持有者的投票来决定。同时作为治理系统的回报，MKR 持有者将获得奖励。然而，成为一名 MKR 持有者是有风险的，他们将作为最后的买家，如果系统中的抵押物不足以支撑现存的贷券，那么 MKR 就会被创建并出售到公开市场上，以提供额外的抵押。这为 MKR 持有者提供了一个强有力的激励机制，MKR 持有者可以负责任地规范地调整 CDP 用以创造贷券的参数，因为如果系统失败，极大的可能，最终他们将遭受损失，但与此同时贷券的持有者却没有这个风险。我可以写更多有关 MKR 的机制和角色的文章，但这是另一个主题。

## Keeping in line with USD: What’s the Target Rate Feedback Mechanism? |与美元保持一致：什么是目标利率反馈机制？

So far I’ve addressed the fundamental stability of the Maker system, but we haven’t spoken about the incentives that are in place to keep one Dai equal to one dollar. This is called the Target Rate Feedback Mechanism [TRFM], and to be honest it’s quite complex. The important thing to know is the following: When Dai trades over $1, the smart contracts incentivize the creation of Dai. When Dai trades less than $1, the smart contracts incentivize the destruction of Dai. This is accomplished with a process that’s similar to the way a central bank uses interest rates to control the money supply. You can read the [Whitepaper](https://github.com/makerdao/docs/blob/master/Dai.md) for more details on how the system actually functions.

到目前为止，已经解决了 Maker 系统的基本稳定问题，但是我们没有谈到保持一个贷券等于一美元所采取的激励措施。它被称为目标利率反馈机制（TRFM），说实话这个还是相当复杂的。但是重要的是知道以下几点：当贷券的交易价格超过1美元时，智能合约将激励贷券的创造。当贷券的交易价格不到1美元时，智能合约将激励贷券的销毁。总之，通过类似于中央银行通过利率来控制货币供应量的过程，来实现这个稳定机制。您可以阅读[白皮书](https://github.com/makerdao/docs/blob/master/Dai.md)以获取有关系统如何实际运作的更多详细信息。

## A final protection — What’s Global Settlement? | 最后的保护伞 - 什么是全球结算？

Despite being developed over the course of three years by some of the best developers in the blockchain space, enduring a rigorous byte-code level audit, and having a working developer-focused stablecoin (Sai) on the mainnet for several months without incident, we all know that nothing is perfect. To keep the system as secure as possible and prevent what cannot be foreseen, the Maker team has added a process called global settlement. When global settlement is triggered, the entire system freezes and all holders of Dai and CDPs are returned the underlying collateral. So, if a global settlement is triggered and I hold 100 Dai, and one ether is worth $100, I can exchange my 100 Dai directly for one ether right through a smart contract. The collateral held in CDPs will be similarly released to its owners. A global settlement can be triggered by a select group of trusted individuals who hold the global settlement keys. If these signatories see something going horribly wrong, they will enter their keys initiate the process of gracefully winding down the system. “But doesn’t that make this….CENTRALIZED?!”

尽管是由有三年经验的区块链领域的一些最优秀的开发人员来开发，并通过了严格的字节码级审计，而且在主网上已经有一个以开发人员为中心的稳定币（Sai）无故障工作了好几个月，但我们都知道世界上没有完美的事物。为了尽可能保持系统的安全并防止无法预见的风险，Maker 团队添加了一个名为“全球结算”的进程。当全球结算被触发时，整个系统将冻结，抵押物将归还给贷券和 CDP 的所有持有者。所以，如果全球结算触发，假如我拥有100个贷券，一个以太的价值是100美元，我可以通过一个智能合约直接将100个贷券兑换成一个以太。CDP 所持有的抵押物也将同样向其所有者发放。全球结算可以由一组持有全球结算密钥的可信人员触发。如果这些人员看到有什么可怕的错误，他们将使用他们的钥匙来启动这个过程，以便优雅地结束系统。“但这不是让这个......中心化了？！”

![](https://cdn-images-1.medium.com/max/800/0*WxxF63UgU_Iu1d9s.)

No, it doesn’t. The only thing a global settlement can do is give you back your collateral. It can’t steal your ether or Dai or interact with the system on your behalf. The worst case scenario in a global settlement is that you end up being exposed to the volatility of your collateral until the system is fixed or you can send it to an exchange.

不，不是的。全球结算唯一可以做的就是退回你的抵押物。它不会偷走你的以太或贷券，或者代替你来与系统交互。全球结算中最糟糕的情况是：一直要等到系统修复，或者你将它发送给交易所，否则您将面临抵押物的价格波动风险。

## Bonus feature: decentralized leverage?! | 额外奖励的功能：去中心化杠杆交易？

The more savvy among you may have noticed an interesting consequence of the Dai creation process. Volatility cannot be destroyed, it can only be transferred. If we have a stable token like Dai that has been stripped of its volatility, where did it go? In the Maker system, volatility is transferred entirely to the holder of the CDP. Using our prior example, should I withdraw 66 Dai from a CDP containing one ether, I will only own that one ether if its price is above the liquidation ratio. Dai is effectively a loan on my ether.

聪明的人，也许会注意到贷券创造过程中还有一个有趣的结果。价格波动不能被消灭，它只能转移。如果我们有一个像贷券一样的稳定币，被剥夺了波动性，那么它的波动到底去哪里了呢？在 Maker 体系中，波动性完全转移给 了 CDP 的持有者。用我们前面的例子，我可以从以一个以太抵押的 CDP 中提取 66 个贷券，如果它的价格高于清算比例，我将只拥有一个以太。贷券实际上是我以太的贷款。

This leads us to the interesting consequence: **I can take the Dai that I borrowed and use it to buy more ether**. By doing this, I am basically buying ether on margin. That’s right, completely decentralized leverage! Now when you trade on a decentralized exchange that has integrated with Maker, you’ll be able to bet on the price of ether with 2x, 3x, or more funds than you actually have.

这将导致有趣的结果：我可以用我借的贷券来买更多的以太。通过这样的方法，我本质上是以保证金购买了以太。没错，完全去中心化的杠杆作用！现在，在与 Maker 系统整合过的去中心化交易所中，您可以用比您实际拥有的2倍，3倍或更多资金对以太进行杠杆合约交易。

## Conclusion | 结论

I call the Maker Dai stablecoin the first working consumer-grade stablecoin because it stands out from both its predecessors and competitors. It is going to be the first application, in a series of many, that brings blockchain technology to the masses. If you want to dive deeper, head over to https://makerdao.com/.

我把 Maker 的贷券称为第一个消费级稳定币，因为它从前辈和竞争对手中脱颖而出，是第一个在一系列将区块链技术带到大众市场的应用。如果您想深入了解，请前往 [https://makerdao.com/](https://makerdao.com/)。

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
