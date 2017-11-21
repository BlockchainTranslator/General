# Maker for Dummies: A Plain English Explanation of the Dai Stablecoin
> 本文翻译自：https://medium.com/@greg_10160/maker-for-dummies-a-plain-english-explanation-of-the-dai-stablecoin-e4481d79b90
>
> 译者： 鱼 [区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [oscnet](https://github.com/oscnet)
>
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


The most common response when someone is asked about the Maker project is: “Well it looks cool, but it’s too complicated and I don’t get it.” The following seeks to simplify how Maker works and to walk you through the system in an ELI5 fashion. I’m even going to write things like “ELI5 = explain it like I’m five,” because that’s how basic this is going to be. This is your parents’ Maker tutorial. If you’re looking for more details, technical explanations, or are just fresh out of books written in Haskell, I recommend the Purple Paper.

## What Product Does Maker Make?

Rather than focus on what Maker is, this explanation focuses on the first product of the Maker organization. This product is called Dai.

Dai is type of a stablecoin. The concept of a stablecoin is fairly straight forward — it’s a token (like bitcoin and ether) that exists on a blockchain. But unlike bitcoin or ether, it has no volatility. “How can something have no volatility, volatility is relative!” Good catch. The asset that Dai is trying to be stable relative to is the U.S. Dollar. So, to summarize, one Dai equals one dollar. Dai is set to be the first working consumer-grade stablecoin.

![](https://cdn-images-1.medium.com/max/800/0*1YWODlh9hfUrM0uU.)

## But aren’t there already stablecoins? You lied!

Yes, and no. You’re most likely familiar with stablecoins that hold USD in bank accounts and issue tokens on a blockchain that are ‘backed’ by these dollars. I call this legally-backed crypto, or an IOU coin, because if those bank accounts should ever be frozen or if the accountants defrauded token holders, the stablecoin now becomes an IOU on whatever’s left when they eventually get the bank accounts back (if they ever regain the bank accounts). Relying on the legal system to maintain crypto-tokens inserts an unreliable middle-man into the blockchain.

We can do better. Enter Dai.

Maker’s Dai is a stablecoin that lives completely on the blockchain chain with its stability unmediated by the legal system or trusted counterparties.

## Wait, wait, why do I need a stablecoin in the first place?

Stablecoins are what allow us to fully realize the promise of blockchain technology. Any application which requires a low threshold of volatility to be viable on a blockchain, consumer loans for example, simply cannot be denominated in a currency which fluctuates 10–20% in a day, like bitcoin and ether. If you’re using bitcoin to send a remittance from one country to another, there’s a good chance that the price movement over the period of one block confirmation (how long it takes the blockchain to include your transaction) will be larger than the fees charged by Western Union or PayPal. If you’re betting on the outcome of a presidential election on Augur and the election isn’t for six months, you don’t want to denominate that bet in ether. Most importantly, stablecoins allow decentralized exchanges (an exchange without a trusted intermediary, where users always maintain full custody their own funds) to denominate trading pairs in US dollars instead of bitcoin or ether. This makes crypto trading more accessible to the average person and puts high-profile hacks, like that of Mt. Gox and Bitfinex, behind us for good.

## So how does the Maker system function?

This is going to be the most challenging part of this tutorial. To understand how Maker creates the stability for the Dai token requires a bit of background about blockchains and specifically, ethereum. I’ll put some quick definitions next to some of the words you may not understand. If you do have this foreknowledge, that’s great and you’re going to love the elegance of the Maker system. Let’s begin:

Note: If you’re simply a consumer, you do not need to understand the following explanation outside of your own curiosity. If you just want to buy Dai, you’ll be able to trade it for dollars, won, bitcoin, ether, and other currencies on a variety of exchanges.

Dai (Maker’s stablecoin) is backed by collateral (ether to be specific). Let’s say you’re an ether holder and you would like to create Dai. Your first move would be to send your ether to a “collateralized debt position” known in shorthand as a CDP. A CDP is a type of software that runs on the blockchain, in this case the ethereum blockchain, and lives within the Maker ecosystem. This software is called a smart contract, but don’t overthink that name too much.

## STOP, you lost me!

If you understood everything above, skip this part. If you find yourself a bit confused, let’s break this down into smaller pieces and an analogy!

## What is the basis of the Maker ecosystem?

The entire Maker ecosystem is built on “smart contracts” like a CDP, the smart contract mentioned above. A blockchain lets you do things by yourself where you used to need a middleman. Much like the internet lets you share information without a middleman, blockchains let you share value without a middleman. Bitcoin was the first network to put this concept to use, its core premise being that you can send bitcoins from Point A to Point B without having to trust anyone but yourself. All trust is vested in the blockchain, which isn’t controlled by anyone. Ethereum took this concept a step further and allows users to add instructions to these transfers.That’s how the smart contract was born. Now you can say: “Send my ether from Point A to Point B on this date, at this time, and with these special instructions.”

## So, how does Maker use smart contracts to create a stablecoin?

![](https://cdn-images-1.medium.com/max/800/0*Vw2mUUL4KboG-7bi.)
<center>I knew a pile of money would get your attention…</center>


The core smart contract at Maker is the CDP. Let’s use an analogy to describe these. Pretend you are at the bank asking for a home equity loan. You put up your house as collateral and they give you cash as a loan in return. If the value of your house decreases, they’re going to ask you to pay the loan back. If you can’t pay the loan back, they’re going to take your house. To bring this back to Maker, just replace your house with ether, the bank with a smart contract, and the loan with Dai. That’s all there is to it. You give the Maker CDP smart contract your ether and it lets you take out a loan in Dai. If the value of your ether goes below a certain threshold, you either have to pay back the smart contract as you would a bank or it will auction off your ether to the highest bidder.

In summary, **CDPs are simply where the collateral (ether) in the Maker system is held**.

Once your ether is in the CDP smart contract, you are able to create Dai. The amount of Dai you can create is relative to how much ether you have put into the CDP. This ratio is fixed, but can be changed over time. The amount of Dai I can create relative to the ether I put in is called the collateralization ratio.

Let’s say ether is worth $100 right now and the collateralization ratio is 150%. If I send 1 ether ($100) into the CDP smart contract, then I am now able to create 66 Dai. This means that, at the current value of ether, each 100 Dai that I’ve created is backed by 1.5 ether collateral. In the Maker system, you don’t lose your ether, but you also no longer control it. The ether that you sent to the CDP is stuck there until you pay back the 66 Dai (this destroys the Dai). The following diagram helps to visualize how you can open and close a CDP. Try to follow along with “your wallet” as actions are performed above. This diagram is somewhat simplified. For instance, a CDP doesn’t really sit in your wallet. It also removes a couple steps that are necessary for the more advanced aspects of the system, but ultimately irrelevant to you as a Dai borrower.

![](https://cdn-images-1.medium.com/max/800/0*hQXqxfslCn53_3-y.)
<center>Opening and closing a CDP while creating/destroying dai.</center>

## What about the stability of Dai?

If the price of ether never fluctuated, it alone would ensure Dai’s stability (and we would not need Dai in the first place). But the price of ether varies so we need to account for that.

By the way, if all you wanted to do was learn how to interact with the system, you can quit here!

## What happens if the value of ether goes down?
There’s not much need to address what happens when ether goes up.The system becomes more collateralized and Dai becomes stronger. That’s not to say that Dai can’t become too strong, where there’s more demand for Dai than there is people willing to create it, but Maker has mechanisms that incentivize users to create more Dai if the price of Dai should trade above one dollar (see below: Target Rate Feedback Mechanism).But if ether goes down, now that can cause problems. If the value of ether held as collateral is worth less than the amount of Dai it’s supposed to be backing, then Dai would not be worth one dollar and the system could collapse. **Maker combats this by liquidating CDPs and auctioning off the ether inside before the value of the ether is less than the amount of Dai it is backing**. Basically, if the price feed into the CDP indicates that the value of ether has gone below a certain threshold (let’s use 125% of created Dai), then the CDP is “liquidated” and the ether inside the CDP is auctioned off for Dai until there is enough Dai to pay back what was extracted from the CDP. Let’s go back to the diagram to see how this works. As before, I’ve simplified some of the steps for the sake of understanding, there are some additional features in the system that prevent various edge-case attacks.
![](https://cdn-images-1.medium.com/max/800/0*1PMi1hf9kkFRcVDy.)
<center>A CDP being liquidated due to insufficient collateral.</center>


See? Simple enough. The system liquidates your collateral and gives it away if don’t return the Dai you’ve borrowed to the CDP quickly enough. This ensures that Dai always has sufficient collateralization.

## Plucking the black swan — What’s the MKR token?

![](https://cdn-images-1.medium.com/max/800/0*OR_GJlMt0QCNx2jP.)
<center>Behold, the most feared creature in finance.</center>

If you’ve been scrutinizing the system for flaws, it probably didn’t take you long to find one. It’s the possibility of a dreaded “black swan event.” It would involve a situation where the price of ether crashes well below the one-to-one collateralization ratio in a time frame too short for the system to handle. Fortunately, Maker has a solution for situations like this: MKR, or makercoin. MKR is a token on the ethereum blockchain (like the rest of the Maker ecosystem) that has governance rights over the Maker smart contracts. For instance, the number used in the above examples (the collateralization rate of CDPs) is set by a vote of MKR holders. In return for regulating the system, MKR holders are rewarded with fees. There is, however, a catch to being a MKR holder. They function as the buyer of last resort. Should the collateral in the system not be enough to cover the amount of Dai in existence, MKR is created and sold onto the open market in order to raise the additional collateral. This provides a strong incentive for MKR holders to responsibly regulate the parameters at which CDPs can create Dai, as it will ultimately be their money on the line should the system fail, not holders of Dai. I could write a lot more about the mechanics and role of MKR, but that’s a subject for a different post.

## Keeping in line with USD: What’s the Target Rate Feedback Mechanism?

So far I’ve addressed the fundamental stability of the Maker system, but we haven’t spoken about the incentives that are in place to keep one Dai equal to one dollar. This is called the Target Rate Feedback Mechanism [TRFM], and to be honest it’s quite complex. The important thing to know is the following: When Dai trades over $1, the smart contracts incentivize the creation of Dai. When Dai trades less than $1, the smart contracts incentivize the destruction of Dai. This is accomplished with a process that’s similar to the way a central bank uses interest rates to control the money supply. You can read the [Whitepaper](https://github.com/makerdao/docs/blob/master/Dai.md) for more details on how the system actually functions.

## A final protection — What’s Global Settlement?

Despite being developed over the course of three years by some of the best developers in the blockchain space, enduring a rigorous byte-code level audit, and having a working developer-focused stablecoin (Sai) on the mainnet for several months without incident, we all know that nothing is perfect. To keep the system as secure as possible and prevent what cannot be foreseen, the Maker team has added a process called global settlement. When global settlement is triggered, the entire system freezes and all holders of Dai and CDPs are returned the underlying collateral. So, if a global settlement is triggered and I hold 100 Dai, and one ether is worth $100, I can exchange my 100 Dai directly for one ether right through a smart contract. The collateral held in CDPs will be similarly released to its owners. A global settlement can be triggered by a select group of trusted individuals who hold the global settlement keys. If these signatories see something going horribly wrong, they will enter their keys initiate the process of gracefully winding down the system. “But doesn’t that make this….CENTRALIZED?!”

![](https://cdn-images-1.medium.com/max/800/0*WxxF63UgU_Iu1d9s.)

No, it doesn’t. The only thing a global settlement can do is give you back your collateral. It can’t steal your ether or Dai or interact with the system on your behalf. The worst case scenario in a global settlement is that you end up being exposed to the volatility of your collateral until the system is fixed or you can send it to an exchange.

## Bonus feature: decentralized leverage?!

The more savvy among you may have noticed an interesting consequence of the Dai creation process. Volatility cannot be destroyed, it can only be transferred. If we have a stable token like Dai that has been stripped of its volatility, where did it go? In the Maker system, volatility is transferred entirely to the holder of the CDP. Using our prior example, should I withdraw 66 Dai from a CDP containing one ether, I will only own that one ether if its price is above the liquidation ratio. Dai is effectively a loan on my ether.

This leads us to the interesting consequence: **I can take the Dai that I borrowed and use it to buy more ether**. By doing this, I am basically buying ether on margin. That’s right, completely decentralized leverage! Now when you trade on a decentralized exchange that has integrated with Maker, you’ll be able to bet on the price of ether with 2x, 3x, or more funds than you actually have.

## Conclusion

I call the Maker Dai stablecoin the first working consumer-grade stablecoin because it stands out from both its predecessors and competitors. It is going to be the first application, in a series of many, that brings blockchain technology to the masses. If you want to dive deeper, head over to https://makerdao.com/.



----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

鱼 区块链技术爱好者， 欢迎加微信号 oscnet 交流。

本文由币乎社区（bihu.com）内容支持计划赞助。

版权所有，转载需完整注明以上内容。

----------------------------------------------------
