## What You Need to Know About the Future of Bitcoin Technology


> 本文翻译自：https://medium.freecodecamp.org/future-of-bitcoin-cc6936ba0b99

> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [鱼](https://github.com/oscnet)

> 翻译时间：2017-12-15

> 本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。

![](https://cdn-images-1.medium.com/max/2000/1*FfRqOEiRKdgvnbuvEgQF6g.jpeg)

Bitcoin (BTC) recently smashed an all-time high of $11,400 USD and subsequently dropped to as low as $8,595 within a few hours. It’s incredibly important to not get lost in the pandemonium and to stay informed about how Bitcoin is progressing technologically.

Anybody considering buying Bitcoin should at the very least learn two things:

1. the history of the technology behind Bitcoin

2. and more importantly, what lies ahead in Bitcoin’s future.

As Bitcoin expert [Andreas M. Antonopoulos](https://medium.com/@aantonop) says, “[Invest in education instead of speculation](https://www.youtube.com/watch?time_continue=328&v=6uXAbJQoZlE).”

With Bitcoin and its underlying blockchain being such incredibly new technological concepts, it can seem daunting at times to try and research and understand its underlying technical details. This article is written in an effort to highlight the scalability problem Bitcoin faces, and what expected or proposed solutions to that problem are. There are some really exciting ones out there that this article discusses!

I wrote this as I was learning about Bitcoin myself, to aggregate the great amount of information about Bitcoin’s future from countless sources out there. When writing this, I kept in mind even those who don’t possess a programming background. However, it is assumed that the reader has a very basic understanding of Bitcoin as a currency and what a blockchain is. Coindesk has a great 5-minute read that should get you up to speed here if you’re just starting out with Bitcoin or if you need a refresher.

Let’s begin with the scalability problem Bitcoin faces.

### The Transaction Throughput Problem

When Bitcoin was first introduced to the world, its creator Satoshi Nakomoto described Bitcoin in the [Bitcoin whitepaper](https://bitcoin.org/bitcoin.pdf) as “A purely peer-to-peer version of electronic cash would allow online payments to be sent directly from one party to another without going through a financial institution.”

One of Bitcoin’s fundamental values was instant and secure peer-to-peer payment transactions. Now, more than ever, Bitcoin is emerging as the prevailing cryptocurrency in the global market, with a 1,200%+ increase in value over the last year alone.

Because of this unprecedented growth, the number of transactions on the Bitcoin blockchain has also increased, with up to [400,000 transactions per day](https://blockchain.info/charts/n-transactions) being conducted. This rapid increase in transactions is posing to be a serious scalability problem for the blockchain, with [over 90,000 transactions](https://blockchain.info/unconfirmed-transactions) being backlogged as unconfirmed at the moment.

![](https://cdn-images-1.medium.com/max/1600/1*kDRKF6Iu3wPbSByqSr32gw.png)

As Bitcoin’s price skyrockets, so does its usage. Note the stagnation at around 400,000 transactions per day

In order to understand why transactions are being backlogged, Bitcoin transactions must first be explained.

Every time a user sends a Bitcoin transaction from his or her wallet to another, the transaction is added into the **memory pool** (mempool), which is essentially a pool of all unconfirmed transactions in the Bitcoin network. This pool is upheld by smaller individual pools on machines that hold a copy of the blockchain ledger, called **nodes**.

From the mempool, miners select transactions that they want to verify. Once miners validate a transaction (i.e. confirm that the sender actually has enough bitcoins to send to the receiver), they add it to a new block, which is eventually published to the blockchain. Other nodes then iterate through this newly published block’s transactions to ensure the block is valid, before accepting the block as a part of its ledger.

![](https://cdn-images-1.medium.com/max/2000/1*K6iO4o2oxd0IeU0luVze0w.png)
A diagram of the transaction lifecycle, source: [weusecoins.com](https://www.weusecoins.com/en/questions/)

Let’s calculate the throughput of transactions:

* The median transaction size [approximately 250 bytes](https://tradeblock.com/blog/analysis-of-bitcoin-transaction-size-trends)

* A block’s size is limited to 1MB (1000000 bytes)

* Thus, a block holds around 4000 transactions (1MB divided by 250 bytes)

* A block can only be published to the blockchain once every 10 minutes on average (600 seconds).

* 4000 transactions (at most) are published every 600 seconds, at a rate of **6.66 transactions / second**

With over 90,000 unconfirmed transactions in the mempool, how does a miner select which transactions to verify? Transaction fees! The sender of a transaction has the option of adding a custom transaction fee to its transaction intended for the miner, incentivizing a miner to select the transaction and have it verified faster. Miners will select the transactions that have the highest fee attached to them to maximize profits. Theoretically, you can send a transaction with no fee. But if there are transactions that have fees higher than yours in the pool, why would yours ever get picked?

*As Bitcoin’s user base grows, so does the average transaction fee. At most, there are only 7 transactions that are processed every second and everyone wants to get their transaction verified first.* At the moment, the average transaction fee is approximately [$3.58 USD](https://bitinfocharts.com/comparison/bitcoin-median_transaction_fee.html). This fee is certainly not ideal — if you want to send your friend a couple of dollars worth of bitcoin, you may end up spending more in transaction fees than the transaction value itself! Therein lies the problem, and if all else remains equal, transaction fees can be expected to rise due to the transaction bottleneck.

### Solving the Throughput Problem

A proposed solution to this bottleneck that has brought great controversy to the Bitcoin community is to simply raise the block size from the original 1MB limit, thus allowing more transactions per block.

Every time the block size is increased in the chain, a **hard fork** is required, meaning an entirely new copy of the chain must be created, therefore requiring consensus from the Bitcoin community. Because millions of people use Bitcoin, gaining consensus is difficult and efforts should be made to avoid it. Furthermore, although the block size can be increased enough to accommodate the current backlog of transactions, as Bitcoin’s userbase continues to grow, there will eventually be another backlog of unconfirmed transactions, so another block size increase will be needed, and subsequently another hard fork.

So why don’t we just make the block size large enough to ensure the throughput will never be a bottleneck, no matter how many people are using it? First, the mathematics of a block size even remotely large enough to handle mass adoption are impractical and will restrict mining to incredibly powerful machines that only large corporations will be able to maintain, introducing an element of centralization.

![](https://cdn-images-1.medium.com/max/2000/1*GF7OTotvNMX6hmHkeIAfYQ.png)
Given a block size big enough for just one city’s population, it would restrict node hosting and mining to only those with the most powerful machines, i.e. massive businesses, source: [Lightning Network](https://lightning.network/lightning-network.pdf)


Furthermore, recall that once a block is mined, all other nodes must validate the block before accepting it. *If the block size was incredibly large and somebody were to publish an invalid block, nodes would waste a large amount of time attempting to validate the block before discarding it as invalid and moving onto the next block.* A denial of service attack can essentially be orchestrated by repeatedly publishing insanely large invalid blocks to the network, stopping valid blocks from being processed for a long period of time. As stated by blockchain pioneer Nick Szabo in [this interview](https://medium.com/@giftedproducts/cryptocurrencies-with-tim-ferriss-nick-szabo-and-naval-ravikant-51a99d037e04), the small block size acts as a technical security parameter to prevent network flooding.

*You can read more about the full impact of an increased block size if Bitcoin were to take over the world, in an article I’ve written [here](https://hackernoon.com/if-we-lived-in-a-bitcoin-future-how-big-would-the-blockchain-have-to-be-bd07b282416f).*

If we can’t increase the block size, what can we do? Luckily, there are several solutions in the works that are expected to be deployed in order to solve this issue.

### Segregated Witness (SegWit)

*Segregated Witness (SegWit) has actually already been implemented into the Bitcoin network, as of August 2017. It’s a fundamental network change that modifies the format of transactions, essentially slimming them down in size, and allowing more transactions to be fit into a block which increases throughput.* SegWit is considered a **soft fork**, meaning it is completely backwards compatible with existing Bitcoin protocol, although nodes and wallets must upgrade to take advantage of all SegWit features.

Each transaction has a signature from the sender, or in other words, **witness data**; this is usually the largest part of the transaction. This data is not actually necessary to verify the transaction, and so SegWit moves this data to the end of the transaction, segregating it. If this transaction is sent to a legacy node (a node that has not upgraded to SegWit), the node strips the witness data off the end of the transaction before inserting it into a block, thus reducing the overall transaction size and saving space. The added benefit of this is that nodes can no longer modify the witness data, changing who the transaction was from, an ability nodes previously had. This makes way for the implementation of multi-layer solutions that we’ll discuss soon. Users also save on transaction fees, as they’re usually calculated per transaction byte, and SegWit reduces total transaction size.

![](https://cdn-images-1.medium.com/max/2000/1*4IKDVzPN0FzJFgOnZADoIQ.png)

SegWit moves signature data to the end of transaction, after which stripped before being stored in a block, source: [Programming Blockchains](https://programmingblockchain.gitbooks.io/programmingblockchain/content/other_types_of_ownership/p2wpkh_pay_to_witness_public_key_hash.html)


Furthermore, SegWit changes the definition of a block: instead of a block being defined in terms of bytes, its now defined in terms of “weights”; a block can have a maximum weight of 4,000. Legacy transactions have a weight of 4, while SegWit transactions have a weight of 0.25, thus enabling a block to contain many more SegWit transactions and have a slightly higher size (approximately 2 megabytes at most). Nodes must upgrade to SegWit to follow this definition, and wallets must incorporate SegWit in order to send SegWit transactions. As a result, SegWit adoption has been slow, accounting for only 12% of current traffic.

![](https://cdn-images-1.medium.com/max/2000/1*GQjWddG72KhXJYQ3k-bnQg.png)
Current state of SegWit adoption hovers around 12% of all transactions, [source: segwit.party](http://segwit.party/charts/)


*Because of the aforementioned benefits of SegWit, I highly encourage anybody reading this to use wallets that have incorporated SegWit to speed up SegWit adoption.* A neat list of them can be found [here](https://bitcoincore.org/en/segwit_adoption/) (my personal favourite is [Samourai Wallet for Android](https://samouraiwallet.com/)). If you want to learn more about the intricacies of SegWit, [Jimmy Song](https://medium.com/u/4acb12744ff8) has written a great article about it:

>Understanding Segwit Block Size

>After I wrote my last article, I was surprised by the protest about the 2MB part of the title (the title has since been…
medium.com
![](https://medium.com/@jimmysong/understanding-segwit-block-size-fd901b87c9d4)

### Multi-Layered Solutions

*As it stands, the Bitcoin blockchain isn’t very feasible for micropayments. If you want to buy a $2 cup of coffee, you’re probably going to pay more than $2 equivalent of BTC in transaction fees, and the transaction won’t be confirmed instantly — you must wait for the transaction to be published in a verified block on the chain, which will appear within 10 minutes at best.*

*Second and third layer solutions are networks layered on top of the Bitcoin blockchain that enable users to send several transactions of small amounts of Bitcoin almost instantly, with no transaction fees.*

**The Lightning Network** is this layered network currently in development expected to alleviate Bitcoin’s scaling problems. This network consists of two additional layers and enables users to open direct channels between each other to send an effectively unlimited number of payments to each other in an instant manner.

>Lightning Network

>The Lightning Network is dependent upon the underlying technology of the blockchain. By using real Bitcoin/blockchain…
lightning.network

### The Second Layer

A user joins the second layer network by conducting a transaction on the blockchain that declares the user is committing a certain number of bitcoin to be used in the layered network. The user then joins a group of nodes that are interconnected with one another, called **channel factories**. These nodes essentially uphold a lobby of individuals that potentially want to conduct transactions with one another. Channel factories then enable an unlimited number of micropayment channels to be created on the third layer (hence the name factories) between individual parties.

![](https://cdn-images-1.medium.com/max/1600/1*AjpC5PHSLvJ-drKZI-7JpA.png)

From the [whitepaper](https://www.tik.ee.ethz.ch/file/a20a865ce40d40c8f942cf206a7cba96/Scalable_Funding_Of_Blockchain_Micropayment_Networks%20%281%29.pdf): users are hooked into a channel factory upon joining the network, which then allocates multiple micropayment channels

### The Third Layer

*Micropayment channels are set up to ensure direct payments between two users on the third layer.* Because the blockchain is no longer present in this layer, it cannot be used to validate transactions and ensure one party paid the other. Instead, smart-contract technology is employed, such as **multisig addresses**, meaning addresses that can be signed off by multiple users to enable the movement of funds, and **hashed time-lock contracts**, which are cryptographically secure automated contracts that lock funds for a certain period of time to ensure one parties that cannot cheat with another. These technologies eliminate the need for trust between users that are connected in micropayment channels.


Here is an example of how a Lightning Network micropayment channel works:

1. Alice wants to dedicate 1 Bitcoin to a micropayment channel between Bob. She declares this 1 Bitcoin to be used in a **commitment transaction** on the Bitcoin blockchain. This 1 Bitcoin is then locked up in a **multisig address** that both parties can sign off on if they want to close the channel. This address is secured with a **hashed time-lock contract** which states, “Alice has 1 BTC and Bob has 0 BTC, to be released in one hour”. This means the 1 Bitcoin Alice has is locked for 1 hour after which it will be returned to Alice and published to the Bitcoin blockchain once more.

2. Alice then decides to give Bob 0.1 BTC. This transaction is logged with a new hashed time-lock contract stating “Alice has 0.9 BTC and Bob has 0.1 BTC, to be expired in 50 minutes”. This contract has an expiry time of 50 minutes, meaning it will be published to the blockchain before the original contract stating Alice has 1 BTC. Therefore Bob instantly knows he has the 0.1 BTC because this new contract will be published to the blockchain before the original contract, essentially making the old contract invalid.

3. Once the full hour passes, the micropayment channel closes and the final balance between Alice and Bob is published to the blockchain. If Alice and Bob want to continue making transactions, they can extend the expiry time of their channel for as long as they want. If one of them wants to close the channel early, one of them needs to sign off on the original multisig address that the Bitcoin is stored in.

*The network enables transactions to route itself to its final destination by using other connected users in the channel as intermediaries.* This can happen even if a direct connection to the desired user isn’t able to be sought the current micropayment channel. For example, if Alice has a channel open with Bob, and Bob has a channel with Mark, and Alice wants to send Mark some Bitcoin, the network can route the payment to Mark through Bob, all while ensuring no party has to trust another.

![](https://cdn-images-1.medium.com/max/1600/1*qtUo7s-5lIOhoxUKe7w99g.png)

In the lightning network, transactions are routed through intermediate users in order to reach its final destination

The implementation of lightning network transactions and their trust-less nature can get incredibly complex, and is best explained by the Lightning developers in [this conference](https://www.youtube.com/watch?v=8zVzw912wPo) or in the following series by [ecurrencyhodler](https://medium.com/@ecurrencyhodler):

> The Lightning Network (Part 1)

>Multisig Addresses: The Building Blocks of the Lightning Network
medium.com


Ideally, a user will only create a commitment transaction to the secondary layer very rarely because he or she will remain in the layered network for prolonged periods of time to conduct most of their day-to-day transactions. Once a user wants to exit this multi-layered network, a **settlement transaction** is made on the blockchain declaring the user’s final Bitcoin balance after all of the second-layer activities. This reconciles their total Bitcoin balance on the blockchain after comparison with the original commitment transaction. In total, only two blockchain transactions are made in order to let the user to conduct a limitless number of transactions for free on the second layer.

As mentioned previously, SegWit paves the way for the lightning network because it removes nodes’ abilities to modify witness data, which is what is used to identify a user’s entry into the second layer. If the user’s commitment transaction can’t be found because the witness data referring to the user was changed, there is a greater level of difficulty involved when trying to reconcile the user’s settlement transaction.

The second layer of the lightning network involving channel factories was very recently introduced in [this whitepaper](https://www.tik.ee.ethz.ch/file/a20a865ce40d40c8f942cf206a7cba96/Scalable_Funding_Of_Blockchain_Micropayment_Networks%20%281%29.pdf). It is still under heavy development, so a lot of its concepts are explained abstractly. However, the network is poised to launch in 2018 and will be by far the biggest improvement in transaction scalability thus far.

### Schnorr Signatures

When a user sends a Bitcoin transaction, the inputs of the transaction (the amount you’re sending) is calculated simply by retrieving from the blockchain the total unspent amounts of Bitcoin you previously received. So for example:

* Starting with an empty wallet, I receive 1 Bitcoin in transaction #1, and then another 1 Bitcoin in a separate transaction #2

* I now want to send 2 Bitcoins in a transaction. There will be two inputs to this transaction: transaction #1, and transaction #2, summing up to 2 Bitcoin

Under the current algorithm for generating signatures (Elliptic Curve Digital Signature Algorithm), each input requires its own signature. This increases the total transaction size and therefore increases the transaction fee.

![](https://cdn-images-1.medium.com/max/1600/1*byA4UmLgEij_1oGp2EaLjg.png)

Currently, each input requires a signature, increasing total transaction size

*Schnorr signatures are an alternative and more efficient way of storing signature data in transactions. All inputs are accumulated and then stored as a single signature by utilizing the Schnorr algorithm, which greatly saves space in a transaction and further helps increase transaction throughput by allowing blocks to store more transactions on average.*

![](https://cdn-images-1.medium.com/max/1600/1*22yyLNKn02a-D7YsDgRw5A.png)

All sender signatures are stored as one signature under the Schnorr algorithm


Schnorr signatures can be also be used to aid Bitcoin’s advancement in privacy by benefiting CoinJoin transactions. CoinJoin is a method of introducing anonymity to Bitcoin transactions. It works by pooling transaction inputs together with other peoples’ transactions when making a payment to a receiver. When payments are pooled, it becomes difficult to track which user sent what input, effectively making them anonymous. However, CoinJoin transactions have increased fees due to a higher number of inputs in a single transaction resulting in a higher number of signatures. Utilizing Schnorr signatures would enable all signatures in a transaction to be compressed into one, saving greatly on transaction fees and encouraging the use of CoinJoin.

Furthermore, Schnorr paves the way for complex multisig transactions which require signing off from multiple parties; no matter how many parties’ signatures are required for a transaction, all the transaction needs is one Schnorr signature.

Schnorr signatures are only now a possibility because of the implementation of SegWit; because signature data can’t be modified by third parties, it can now be used to effectively create a Schnorr signature.

### MimbleWimble

MimbleWimble is a radical but incredibly powerful proposed change to Bitcoin architecture that was anonymously introduced through this [whitepaper](https://download.wpsoftware.net/bitcoin/wizardry/mimblewimble.txt) in July 2016.

Named after the [tongue-tying curse from the Harry Potter series](http://harrypotter.wikia.com/wiki/Tongue-Tying_Curse), its aim is to remove transactions entirely from blocks. Under MimbleWimble, transactions consist of nothing but input amounts, output amounts, and a signature. The signature of the transaction can only be decrypted by the receiver, and so transaction verification is left to the receiver.

By extension, blocks consist of only the list of all transaction input amounts of all transactions, all transaction output amounts, and their corresponding signatures. Blocks can then be merged seamlessly with previous blocks as they’re nothing but pairs of input and output amounts. Nodes then have the ability to cryptographically ensure that transactions in blocks do not create extra bitcoins (i.e. their net difference between inputs and outputs in blocks is 0) without having to decrypt transactions.

This removal of transaction storage grants complete anonymity to all users by stripping away the ability to generate transaction history. Furthermore, with blocks only containing the **unspent transaction outputs** (meaning the number of Bitcoins that have been received in an address but not moved out yet), the blockchain size can be reduced by over 60% according to the whitepaper. This reduction in size means that in order to validate a MimbleWimble blockchain, nodes will only need to look at the set of unspent transaction outputs instead of the entire set of transactions, which will exponentially increase performance.

The mathematical details of MimbleWimble are outside of the scope of this article, but are explained in detail in the whitepaper. Although MimbleWimble presents some clear advantages and technical breakthroughs, its implementation requires the removal of Bitcoin’s Script system that much of the existing architecture relies on. As a result, MimbleWimble’s implementation on the Bitcoin blockchain is not technically feasible.

However, there are proposals for MimbleWimble to exist as a sidechain. A sidechain is a separate blockchain directly attached to the Bitcoin blockchain through the use of a two-way peg. This peg enables assets between the two chains to be exchanged and “pegs” the value of the sidechain asset to the value of Bitcoin. In this setup, users would be able to exchange Bitcoins for MimbleWimble coins, conduct completely private and rapid transactions on the MimbleWimble chain, and then exchange their MimbleWimble coins for Bitcoin whenever they please.

![](https://cdn-images-1.medium.com/max/2000/0*shjdJcexgSIUXttC.png)
Sidechain coins are pegged to the Bitcoin blockchain, operating alongside it with a fixed exchange rate, source: [Blockchain.com](http://blockchain.com/)

In fact, a group of developers are already in the process of developing MimbleWimble as a separate cryptocurrency called [GRIN](https://github.com/mimblewimble/grin); it was recently deployed on a test network and may be launched in the near future.

### Rootstock

>Rootstock — Smart Contracts on the Bitcoin Blockchain

>As a concept the Rootstock [1] platform is one of those ideas that once it is proposed it is obvious that it is a great…
medium.com

Rootstock is for whatever reason one of the less talked about advancements in Bitcoin technology but is by far one of the coolest. Rootstock is described as “the first open-source smart contract platform with a 2-way peg to Bitcoin that also rewards the Bitcoin miners via merge-mining, allowing them to actively participate in the Smart Contract revolution.”

Much like MimbleWimble, Rootstock is being developed as a sidechain solution to the Bitcoin blockchain. Its fundamental value lies in its focus in smart contracts. Rootstock aims to be a [Turing Complete](https://simple.wikipedia.org/wiki/Turing_complete) (completely programmable) smart-contracts platform that will be backwards compatible with Ethereum’s virtual machine. This means that Rootstock will be able to execute any smart contracts developed for the Ethereum platform and have smart contracts developed for its own platform.

Rootstock aims to implement this versatile smart-contract functionality all while leveraging Bitcoin’s comparatively dominant userbase and value by acting as a two-way pegged sidechain. It is also being designed to be secured by the existing Bitcoin mining network, therefore not needing to incentivize miners to secure its own blockchain. Rootstock also aims to tackle the transaction scalability problem by implementing its own version of a multi-layered solution called [Lumino](https://uploads.strikinglycdn.com/files/9dcb08c5-f5a9-430e-b7ba-6c35550a4e67/LuminoTransactionCompressionProtocolLTCP.pdf). With this, it may be able to accomplish up to 20,000 transactions per second.

*Rootstock is aiming for [a launch by the end of 2017](https://www.coindesk.com/bitcoin-startup-rsk-launch-smart-contracts-sidechain-2017/). Overall, the platform aims to fit in perfectly alongside Bitcoin and if its claims hold true, it will undoubtedly bring unprecedented utility to the Bitcoin network.*

If you’ve gotten this far, congratulations! I hope you were able to learn something about the future of Bitcoin and are as excited about it as I am.

Bitcoin isn’t perfect and is faced with challenges that its community must work to solve. However, it is backed by an incredibly dedicated and thriving developer community that is working day in and day out to tackle these problems. There are constant innovations happening everyday, and I am sure by the time you finished reading this another new and exciting proposal for the Bitcoin blockchain popped up.

This article by no means covers everything out there; if there’s anything that you’re aware of that I didn’t mention, please mention them in the comments!

Follow me on Twitter and Medium if you’re interested in more in-depth and informative write-ups like these in the future!
I’m a relative Bitcoin beginner myself so if there are any mistakes or if you have any feedback please don’t hesitate let me know!

BTC Address: 3MGguJhw1bm95tDQjZ3b8ySBwZLJ77CgG1

Here are some resources if you’re interested in learning more:

* [Mastering Bitcoin](https://github.com/bitcoinbook/bitcoinbook), an comprehensive book written by [Andreas M. Antonopoulos](https://medium.com/@aantonop)

* [The Bitcoin Wiki](http://bitcoin.it/)

* [The Bitcoin whitepaper](https://lopp.net/pdf/bitcoin.pdf)

* [A collection of Bitcoin resources](https://lopp.net/bitcoin.html) by [Jameson Lopp](https://medium.com/@lopp)

* [This highly informative interview with Nick Szabos](https://www.google.ca/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=0ahUKEwiznZ-Oo-zXAhUW02MKHZ0aAhcQtwIILzAB&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D3FA3UjA0igY&usg=AOvVaw0JIy-AaKaXyDsGm8psm7Qj) conducted by [Tim Ferriss](https://medium.com/@timferriss)

* [Ivan on Tech on Youtube](https://www.youtube.com/channel/UCrYmtJBtLdtm2ov84ulV-yg), who is absolutely amazing at breaking down technical Bitcoin concepts

Thanks to Emma Soolepp.

Bitcoin Technology Blockchain Finance Business


----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

鱼 区块链技术爱好者，欢迎加微信号交流：**oscnet**

本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。

版权所有，转载需完整注明以上内容。

----------------------------------------------------
