## What You Need to Know About the Future of Bitcoin Technology | 你需要了解的比特币技术的未来


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

比特币（BTC）最近一度创下了11,400美元的历史新高，随后在几个小时内跌至8,595美元。不要迷失在混乱之中，并了解比特币在技术上的进步是非常重要的。

考虑购买比特币的人至少应该学习两件事：

1. 比特币技术的历史
2. 更重要的是比特币未来的前景。

正如比特币专家Andreas M. Antonopoulos所说：“ 投资于教育而不是投机。”

With Bitcoin and its underlying blockchain being such incredibly new technological concepts, it can seem daunting at times to try and research and understand its underlying technical details. This article is written in an effort to highlight the scalability problem Bitcoin faces, and what expected or proposed solutions to that problem are. There are some really exciting ones out there that this article discusses!

I wrote this as I was learning about Bitcoin myself, to aggregate the great amount of information about Bitcoin’s future from countless sources out there. When writing this, I kept in mind even those who don’t possess a programming background. However, it is assumed that the reader has a very basic understanding of Bitcoin as a currency and what a blockchain is. Coindesk has a great 5-minute read that should get you up to speed here if you’re just starting out with Bitcoin or if you need a refresher.

Let’s begin with the scalability problem Bitcoin faces.

随着比特币及其底层区块链成为如此难以置信的新技术概念，有时试图研究和理解其基本技术细节似乎令人望而生畏。本文旨在强调比特币面临的可扩展性问题，以及该问题的预期或提出的解决方案。这里有一些非常令人兴奋的，这篇文章讨论！

我之所以这样写，是因为我自己也在学习比特币，把比特币未来的大量信息汇总在那里。写这个的时候，我还记得那些没有编程背景的人。然而，假设读者对比特币是一种货币和区块链是非常基本的了解。Coindesk有一个伟大的5分钟读取，应该让你加快速度在这里，如果你刚刚开始使用比特币，或者如果您需要复习。

让我们从比特币面临的可扩展性问题开始。

### The Transaction Throughput Problem | 交易吞吐量问题

When Bitcoin was first introduced to the world, its creator Satoshi Nakomoto described Bitcoin in the [Bitcoin whitepaper](https://bitcoin.org/bitcoin.pdf) as “A purely peer-to-peer version of electronic cash would allow online payments to be sent directly from one party to another without going through a financial institution.”

One of Bitcoin’s fundamental values was instant and secure peer-to-peer payment transactions. Now, more than ever, Bitcoin is emerging as the prevailing cryptocurrency in the global market, with a 1,200%+ increase in value over the last year alone.

Because of this unprecedented growth, the number of transactions on the Bitcoin blockchain has also increased, with up to [400,000 transactions per day](https://blockchain.info/charts/n-transactions) being conducted. This rapid increase in transactions is posing to be a serious scalability problem for the blockchain, with [over 90,000 transactions](https://blockchain.info/unconfirmed-transactions) being backlogged as unconfirmed at the moment.

当比特币首次引入世界时，其创始人Satoshi Nakomoto在比特币白皮书中将比特币描述为“纯电子现金的对等版本将允许在线支付从一方直接发送到另一方而不经过财务机构。”

比特币的基本价值之一是即时和安全的点对点支付交易。现在，比特币比以往任何时候都更加成为全球市场上流行的加密货币，仅比去年就增长了1200％以上。

由于这一前所未有的增长，比特币区块链交易的数量也有所增加，每天交易量高达40万笔。交易量的迅速增长对区块链构成了严重的可扩展性问题，目前有超过9万笔交易被囤积为未经确认。

![](https://cdn-images-1.medium.com/max/1600/1*kDRKF6Iu3wPbSByqSr32gw.png)

As Bitcoin’s price skyrockets, so does its usage. Note the stagnation at around 400,000 transactions per day | 随着比特币的价格猛涨，它的使用也是如此。请注意每天大约40万笔交易的停滞

In order to understand why transactions are being backlogged, Bitcoin transactions must first be explained.

Every time a user sends a Bitcoin transaction from his or her wallet to another, the transaction is added into the **memory pool** (mempool), which is essentially a pool of all unconfirmed transactions in the Bitcoin network. This pool is upheld by smaller individual pools on machines that hold a copy of the blockchain ledger, called **nodes**.

From the mempool, miners select transactions that they want to verify. Once miners validate a transaction (i.e. confirm that the sender actually has enough bitcoins to send to the receiver), they add it to a new block, which is eventually published to the blockchain. Other nodes then iterate through this newly published block’s transactions to ensure the block is valid, before accepting the block as a part of its ledger.

为了理解交易被积压的原因，必须首先解释比特币交易。

每当用户从他或她的钱包中发送比特币交易到另一个交易时，交易就被添加到内存池（mempool）中，这实际上是比特币网络中所有未经确认的交易的一个池。在拥有区块链账本副本的机器（称为节点）上，较小的个人池支持该池。

从mempool，矿工选择他们想要验证的交易。一旦矿工确认交易（即确认发件人实际上有足够的比特币发送给收件人），他们将其添加到一个新的块，最终发布到区块链。其他节点然后遍历这个新发布的块的事务，以确保该块是有效的，然后接受该块作为其分类账的一部分。

![](https://cdn-images-1.medium.com/max/2000/1*K6iO4o2oxd0IeU0luVze0w.png)
A diagram of the transaction lifecycle, source: [weusecoins.com](https://www.weusecoins.com/en/questions/) | 交易生命周期图，来源：weusecoins.com

Let’s calculate the throughput of transactions:

* The median transaction size [approximately 250 bytes](https://tradeblock.com/blog/analysis-of-bitcoin-transaction-size-trends)

* A block’s size is limited to 1MB (1000000 bytes)

* Thus, a block holds around 4000 transactions (1MB divided by 250 bytes)

* A block can only be published to the blockchain once every 10 minutes on average (600 seconds).

* 4000 transactions (at most) are published every 600 seconds, at a rate of **6.66 transactions / second**

我们来计算交易的吞吐量：

* 中位数事务大小大约为250字节

* 一个块的大小限制为1MB（1000000字节）

* 因此，一个块保存大约4000个事务（1MB除以250字节）

* 一个区块平均每10分钟只能发布到区块链（600秒）。

* 4000次交易（最多）每600秒发布一次，速度为6.66次/秒

With over 90,000 unconfirmed transactions in the mempool, how does a miner select which transactions to verify? Transaction fees! The sender of a transaction has the option of adding a custom transaction fee to its transaction intended for the miner, incentivizing a miner to select the transaction and have it verified faster. Miners will select the transactions that have the highest fee attached to them to maximize profits. Theoretically, you can send a transaction with no fee. But if there are transactions that have fees higher than yours in the pool, why would yours ever get picked?

*As Bitcoin’s user base grows, so does the average transaction fee. At most, there are only 7 transactions that are processed every second and everyone wants to get their transaction verified first.* At the moment, the average transaction fee is approximately [$3.58 USD](https://bitinfocharts.com/comparison/bitcoin-median_transaction_fee.html). This fee is certainly not ideal — if you want to send your friend a couple of dollars worth of bitcoin, you may end up spending more in transaction fees than the transaction value itself! Therein lies the problem, and if all else remains equal, transaction fees can be expected to rise due to the transaction bottleneck.

在mempool中有超过90,000个未经证实的交易，矿工如何选择要验证的交易？交易费用！交易的发件人可以选择将自定义交易费用添加到矿工的交易中，从而激励矿工选择交易并使其更快地被验证。矿工将选择附加费最高的交易来实现利润最大化。理论上，您可以免费发送交易。但是，如果有些交易的收费高于你的收入，你为什么会被挑选？

随着比特币用户群的增长，平均交易费用也在增长。最多只有7个交易每秒处理，每个人都希望首先验证交易。目前，平均交易费用约为3.58美元。这笔费用当然不是理想的 - 如果你想给你的朋友发送价值几美元的比特币，你最终可能会花费更多的交易费用。这就是问题所在，如果其他条件保持不变，交易费用会因交易瓶颈而上升。

### Solving the Throughput Problem | 解决吞吐量问题

A proposed solution to this bottleneck that has brought great controversy to the Bitcoin community is to simply raise the block size from the original 1MB limit, thus allowing more transactions per block.

Every time the block size is increased in the chain, a **hard fork** is required, meaning an entirely new copy of the chain must be created, therefore requiring consensus from the Bitcoin community. Because millions of people use Bitcoin, gaining consensus is difficult and efforts should be made to avoid it. Furthermore, although the block size can be increased enough to accommodate the current backlog of transactions, as Bitcoin’s userbase continues to grow, there will eventually be another backlog of unconfirmed transactions, so another block size increase will be needed, and subsequently another hard fork.

So why don’t we just make the block size large enough to ensure the throughput will never be a bottleneck, no matter how many people are using it? First, the mathematics of a block size even remotely large enough to handle mass adoption are impractical and will restrict mining to incredibly powerful machines that only large corporations will be able to maintain, introducing an element of centralization.

对这个瓶颈提出的解决方案给比特币社区带来了巨大的争议，就是将块的大小从原来的1MB限制提高到每块的交易量。

每当链中的块大小增加时，都需要一个硬分叉，这意味着必须创建一个全新的链，因此需要比特币社区的共识。由于数百万人使用比特币，达成共识是困难的，应该努力避免。此外，尽管块大小可以增加到足以容纳当前积压的交易，但随着比特币用户数量的不断增长，最终还会有另外一些未确认的交易积压，因此需要增加另一个块大小，并随后出现另一个硬分叉。

那么为什么我们不能把块大小做得足够大，以确保吞吐量永远不会成为瓶颈，不管有多少人在使用它？首先，数据块大小即使远大于处理大规模采用也是不切实际的，并且会限制采矿到只有大公司才能维持的难以置信的强大机器，引入集中化元素。

![](https://cdn-images-1.medium.com/max/2000/1*GF7OTotvNMX6hmHkeIAfYQ.png)
Given a block size big enough for just one city’s population, it would restrict node hosting and mining to only those with the most powerful machines, i.e. massive businesses, source: [Lightning Network](https://lightning.network/lightning-network.pdf) | 鉴于只有一个城市的人口规模足够大，它将节点托管和采矿限制在只有那些拥有最强大机器的大型企业，源：Lightning Network


Furthermore, recall that once a block is mined, all other nodes must validate the block before accepting it. *If the block size was incredibly large and somebody were to publish an invalid block, nodes would waste a large amount of time attempting to validate the block before discarding it as invalid and moving onto the next block.* A denial of service attack can essentially be orchestrated by repeatedly publishing insanely large invalid blocks to the network, stopping valid blocks from being processed for a long period of time. As stated by blockchain pioneer Nick Szabo in [this interview](https://medium.com/@giftedproducts/cryptocurrencies-with-tim-ferriss-nick-szabo-and-naval-ravikant-51a99d037e04), the small block size acts as a technical security parameter to prevent network flooding.

*You can read more about the full impact of an increased block size if Bitcoin were to take over the world, in an article I’ve written [here](https://hackernoon.com/if-we-lived-in-a-bitcoin-future-how-big-would-the-blockchain-have-to-be-bd07b282416f).*

此外，回想一下，一旦块被挖掘，所有其他节点必须在接受它之前验证块。如果块的大小非常大，有人发布一个无效的块，节点会浪费大量的时间来验证该块，然后将其丢弃为无效并移动到下一个块。拒绝服务攻击本质上可以通过反复向网络发布非常大的无效块来阻止有效的块被长时间处理。正如区块链先驱Nick Szabo在本次采访中指出的那样，小块的大小是防止网络泛滥的技术安全参数。

如果比特币接管世界，你可以阅读更多关于增加块大小的全面影响，在我写在这里的一篇文章。

If we can’t increase the block size, what can we do? Luckily, there are several solutions in the works that are expected to be deployed in order to solve this issue.

如果我们不能增加块的大小，我们可以做什么？幸运的是，为了解决这个问题，预计将会部署一些解决方案。

### Segregated Witness (SegWit) | 隔离见证（SegWit）

*Segregated Witness (SegWit) has actually already been implemented into the Bitcoin network, as of August 2017. It’s a fundamental network change that modifies the format of transactions, essentially slimming them down in size, and allowing more transactions to be fit into a block which increases throughput.* SegWit is considered a **soft fork**, meaning it is completely backwards compatible with existing Bitcoin protocol, although nodes and wallets must upgrade to take advantage of all SegWit features.

Each transaction has a signature from the sender, or in other words, **witness data**; this is usually the largest part of the transaction. This data is not actually necessary to verify the transaction, and so SegWit moves this data to the end of the transaction, segregating it. If this transaction is sent to a legacy node (a node that has not upgraded to SegWit), the node strips the witness data off the end of the transaction before inserting it into a block, thus reducing the overall transaction size and saving space. The added benefit of this is that nodes can no longer modify the witness data, changing who the transaction was from, an ability nodes previously had. This makes way for the implementation of multi-layer solutions that we’ll discuss soon. Users also save on transaction fees, as they’re usually calculated per transaction byte, and SegWit reduces total transaction size.

截至2017年8月，隔离见证（SegWit）实际上已经应用到比特币网络中。这是一个基本的网络变化，它修改了交易的格式，实质上减少了交易的规模，允许更多的交易进入到一个区块增加吞吐量。SegWit被认为是一个软分叉，意味着它完全向后兼容现有的比特币协议，尽管节点和钱包必须升级才能充分利用SegWit的所有功能。

每笔交易都有发件人的签名，换句话说就是证人资料 ; 这通常是交易的最大部分。这些数据实际上并不是验证交易所必需的，因此SegWit会将这些数据移到交易结束时隔离它。如果这个事务被发送到一个遗留节点（一个没有升级到SegWit的节点），节点将事务结束之前的见证数据剥离，然后将其插入到一个块中，从而减少整个事务的大小并节省空间。这样做的另一个好处就是节点不能再修改证人数据，改变事务的来源，以前的能力节点。这为我们即将讨论的多层解决方案的实现提供了方便。用户还可节省交易费用，因为它们通常是按每个事务字节计算的，而SegWit可减少总交易量。

![](https://cdn-images-1.medium.com/max/2000/1*4IKDVzPN0FzJFgOnZADoIQ.png)

SegWit moves signature data to the end of transaction, after which stripped before being stored in a block, source: [Programming Blockchains](https://programmingblockchain.gitbooks.io/programmingblockchain/content/other_types_of_ownership/p2wpkh_pay_to_witness_public_key_hash.html) | SegWit将签名数据移动到事务结束，之后在被存储在一个块中之前剥离，源：Programming Blockchains


Furthermore, SegWit changes the definition of a block: instead of a block being defined in terms of bytes, its now defined in terms of “weights”; a block can have a maximum weight of 4,000. Legacy transactions have a weight of 4, while SegWit transactions have a weight of 0.25, thus enabling a block to contain many more SegWit transactions and have a slightly higher size (approximately 2 megabytes at most). Nodes must upgrade to SegWit to follow this definition, and wallets must incorporate SegWit in order to send SegWit transactions. As a result, SegWit adoption has been slow, accounting for only 12% of current traffic.

此外，SegWit改变了一个块的定义，而不是用字节定义的块，现在用“权重”来定义。一个街区可以有4000的最大重量。传统交易的权重为4，而SegWit交易的权重为0.25，从而使块能够包含更多的SegWit交易，并且具有略高的大小（最多大约2兆字节）。节点必须升级到SegWit才能遵循此定义，并且钱包必须包含SegWit才能发送SegWit事务。因此，SegWit采用速度缓慢，仅占当前流量的12％。

![](https://cdn-images-1.medium.com/max/2000/1*GQjWddG72KhXJYQ3k-bnQg.png)
Current state of SegWit adoption hovers around 12% of all transactions, [source: segwit.party](http://segwit.party/charts/) | SegWit采用的当前状态约占所有交易的12％，来源：segwit.party


*Because of the aforementioned benefits of SegWit, I highly encourage anybody reading this to use wallets that have incorporated SegWit to speed up SegWit adoption.* A neat list of them can be found [here](https://bitcoincore.org/en/segwit_adoption/) (my personal favourite is [Samourai Wallet for Android](https://samouraiwallet.com/)). If you want to learn more about the intricacies of SegWit, [Jimmy Song](https://medium.com/u/4acb12744ff8) has written a great article about it:

由于SegWit的上述优势，我强烈建议任何人阅读此文档，以便使用包含SegWit的钱包来加速SegWit的应用。一个整洁的列表可以在这里找到（我个人最喜欢的是Android的Samourai钱包）。如果您想了解更多关于SegWit的错综复杂的信息，Jimmy Song写了一篇很棒的文章：

>Understanding Segwit Block Size

>After I wrote my last article, I was surprised by the protest about the 2MB part of the title (the title has since been…

> medium.com https://medium.com/@jimmysong/understanding-segwit-block-size-fd901b87c9d4

了解Segwit块的大小

在我写了我的上一篇文章后，我对标题的2MB部分的抗议感到惊讶（标题已经是...
medium.com


### Multi-Layered Solutions | 多层解决方案

*As it stands, the Bitcoin blockchain isn’t very feasible for micropayments. If you want to buy a $2 cup of coffee, you’re probably going to pay more than $2 equivalent of BTC in transaction fees, and the transaction won’t be confirmed instantly — you must wait for the transaction to be published in a verified block on the chain, which will appear within 10 minutes at best.*

*Second and third layer solutions are networks layered on top of the Bitcoin blockchain that enable users to send several transactions of small amounts of Bitcoin almost instantly, with no transaction fees.*

**The Lightning Network** is this layered network currently in development expected to alleviate Bitcoin’s scaling problems. This network consists of two additional layers and enables users to open direct channels between each other to send an effectively unlimited number of payments to each other in an instant manner.

就目前而言，比特币区块链对于小额支付来说不是很可行。如果你想购买2美元的咖啡，你可能要支付超过2美元的BTC等值交易费用，交易将不会被立即确认 - 你必须等待交易被公布在链条上阻塞，最好在10分钟内出现。

第二层和第三层解决方案是在比特币区块链上分层的网络，使用户能够几乎立即发送少量比特币的几笔交易，而无需交易费用。

闪电网络是目前正在开发的这个分层网络，预计可以缓解比特币的扩展问题。该网络由两个附加层组成，使用户能够在彼此之间打开直接的渠道，以即时的方式相互发送无限次数的支付。

>Lightning Network

>The Lightning Network is dependent upon the underlying technology of the blockchain. By using real Bitcoin/blockchain…
lightning.network
https://lightning.network/

闪电网络

闪电网络取决于区块链的基本技术。通过使用真正的比特币/区块链...
lightning.network

### The Second Layer | 第二层

A user joins the second layer network by conducting a transaction on the blockchain that declares the user is committing a certain number of bitcoin to be used in the layered network. The user then joins a group of nodes that are interconnected with one another, called **channel factories**. These nodes essentially uphold a lobby of individuals that potentially want to conduct transactions with one another. Channel factories then enable an unlimited number of micropayment channels to be created on the third layer (hence the name factories) between individual parties.

用户通过在区块链上进行交易来加入第二层网络，该交易声明用户正在提交一定数量的比特币用于分层网络。然后用户加入一组相互连接的节点，称为通道工厂。这些节点基本上维持了可能想要彼此进行交易的个人大厅。渠道工厂然后在第三层（因此名称工厂）之间在各方之间创建无限数量的微支付渠道。

![](https://cdn-images-1.medium.com/max/1600/1*AjpC5PHSLvJ-drKZI-7JpA.png)

From the [whitepaper](https://www.tik.ee.ethz.ch/file/a20a865ce40d40c8f942cf206a7cba96/Scalable_Funding_Of_Blockchain_Micropayment_Networks%20%281%29.pdf): users are hooked into a channel factory upon joining the network, which then allocates multiple micropayment channels | 从白皮书：用户在加入网络后被连接到一个渠道工厂，然后分配多个微支付渠道

### The Third Layer | 第三层

*Micropayment channels are set up to ensure direct payments between two users on the third layer.* Because the blockchain is no longer present in this layer, it cannot be used to validate transactions and ensure one party paid the other. Instead, smart-contract technology is employed, such as **multisig addresses**, meaning addresses that can be signed off by multiple users to enable the movement of funds, and **hashed time-lock contracts**, which are cryptographically secure automated contracts that lock funds for a certain period of time to ensure one parties that cannot cheat with another. These technologies eliminate the need for trust between users that are connected in micropayment channels.

小额支付渠道的建立是为了确保第三层两个用户之间的直接支付。由于区块链不再存在于此层，因此不能用于验证交易，并确保一方支付另一方。相反，采用了智能合约技术，如多重地址，可以由多个用户签名以实现资金流动的签名地址，以及加密的时间锁定合同，这是一种密码安全的自动化合同，将资金锁定在一定的一段时间，以确保一方不能与另一方作弊。这些技术消除了在小额支付渠道中连接的用户之间的信任需求。

Here is an example of how a Lightning Network micropayment channel works:

1. Alice wants to dedicate 1 Bitcoin to a micropayment channel between Bob. She declares this 1 Bitcoin to be used in a **commitment transaction** on the Bitcoin blockchain. This 1 Bitcoin is then locked up in a **multisig address** that both parties can sign off on if they want to close the channel. This address is secured with a **hashed time-lock contract** which states, “Alice has 1 BTC and Bob has 0 BTC, to be released in one hour”. This means the 1 Bitcoin Alice has is locked for 1 hour after which it will be returned to Alice and published to the Bitcoin blockchain once more.

2. Alice then decides to give Bob 0.1 BTC. This transaction is logged with a new hashed time-lock contract stating “Alice has 0.9 BTC and Bob has 0.1 BTC, to be expired in 50 minutes”. This contract has an expiry time of 50 minutes, meaning it will be published to the blockchain before the original contract stating Alice has 1 BTC. Therefore Bob instantly knows he has the 0.1 BTC because this new contract will be published to the blockchain before the original contract, essentially making the old contract invalid.

3. Once the full hour passes, the micropayment channel closes and the final balance between Alice and Bob is published to the blockchain. If Alice and Bob want to continue making transactions, they can extend the expiry time of their channel for as long as they want. If one of them wants to close the channel early, one of them needs to sign off on the original multisig address that the Bitcoin is stored in.

以下是一个Lightning Network微支付通道如何工作的例子：

1. 爱丽丝想把1个比特币专用于Bob之间的一个微型支付通道。她宣称这个比特币将用于比特币区块链的承诺交易。然后这1比特币被锁定在一个多重地址中，如果双方想要关闭该频道，双方都可以签字。这个地址是用一个哈希时间锁定合同来保护的，该合同规定“Alice有1 BTC，Bob有0 BTC，将在一个小时内发布”。这意味着1比特币爱丽丝已被锁定1小时后，它将被返回到爱丽丝和再次发布到比特币区块链。

2. Alice然后决定给Bob 0.1 BTC。这笔交易记录了一个新的哈希时间锁定合约，指出“Alice有0.9 BTC，Bob有0.1 BTC，在50分钟内过期”。此合约的到期时间为50分钟，这意味着它将在原始合同声明Alice有1 BTC之前发布到区块链。所以鲍勃立即知道他有0.1比特币，因为这个新的合同将在原始合同之前发布到区块链上，从而使旧合同无效。

3. 一旦整个小时过去了，微支付通道关闭，Alice和Bob之间的最终平衡被发布到区块链。如果爱丽丝和鲍勃想继续交易，他们可以延长他们频道的到期时间，只要他们想要的时间。如果其中一个人想要提前关闭频道，他们中的一个需要在比特币存储在原始的multisig地址上签字。

*The network enables transactions to route itself to its final destination by using other connected users in the channel as intermediaries.* This can happen even if a direct connection to the desired user isn’t able to be sought the current micropayment channel. For example, if Alice has a channel open with Bob, and Bob has a channel with Mark, and Alice wants to send Mark some Bitcoin, the network can route the payment to Mark through Bob, all while ensuring no party has to trust another.

网络使交易可以通过使用渠道中的其他连接用户作为中介，将自己路由到最终目的地。即使与所需用户的直接连接不能被寻求当前的微支付信道，也可能发生这种情况。例如，如果Alice有一个用Bob打开的频道，而Bob有一个带有Mark的频道，Alice想要发送一些比特币给Mark，那么网络可以通过Bob将支付路由给Mark，同时确保没有一方必须信任另一个。

![](https://cdn-images-1.medium.com/max/1600/1*qtUo7s-5lIOhoxUKe7w99g.png)

In the lightning network, transactions are routed through intermediate users in order to reach its final destination | 在雷电网络中，交易通过中间用户进行路由以达到其最终目的地

The implementation of lightning network transactions and their trust-less nature can get incredibly complex, and is best explained by the Lightning developers in [this conference](https://www.youtube.com/watch?v=8zVzw912wPo) or in the following series by [ecurrencyhodler](https://medium.com/@ecurrencyhodler):

> The Lightning Network (Part 1)

>Multisig Addresses: The Building Blocks of the Lightning Network
medium.com
https://medium.com/the-litecoin-school-of-crypto/a-primer-to-the-lightning-network-part-1-be909c403bde

闪电网络交易的实施和它们的无信任性质可能会变得非常复杂，最好由本次会议的Lightning开发人员或ecurrencyhodler的以下系列来解释：
闪电网络（第1部分）

多重地址：闪电网络的构建块
medium.com


Ideally, a user will only create a commitment transaction to the secondary layer very rarely because he or she will remain in the layered network for prolonged periods of time to conduct most of their day-to-day transactions. Once a user wants to exit this multi-layered network, a **settlement transaction** is made on the blockchain declaring the user’s final Bitcoin balance after all of the second-layer activities. This reconciles their total Bitcoin balance on the blockchain after comparison with the original commitment transaction. In total, only two blockchain transactions are made in order to let the user to conduct a limitless number of transactions for free on the second layer.

理想情况下，用户只会很少创建一个到第二层的承诺交易，因为他或她将长时间留在分层网络中进行大部分的日常交易。一旦用户想要退出这个多层次的网络，就会在区块链上进行结算交易，在所有的第二层活动之后宣布用户的最终比特币余额。与原始承诺交易进行比较之后，这将它们在比特币上的总比特币余额调节到区块链上。总共只有两个区块链交易是为了让用户在第二层免费进行无限次的交易。

As mentioned previously, SegWit paves the way for the lightning network because it removes nodes’ abilities to modify witness data, which is what is used to identify a user’s entry into the second layer. If the user’s commitment transaction can’t be found because the witness data referring to the user was changed, there is a greater level of difficulty involved when trying to reconcile the user’s settlement transaction.

The second layer of the lightning network involving channel factories was very recently introduced in [this whitepaper](https://www.tik.ee.ethz.ch/file/a20a865ce40d40c8f942cf206a7cba96/Scalable_Funding_Of_Blockchain_Micropayment_Networks%20%281%29.pdf). It is still under heavy development, so a lot of its concepts are explained abstractly. However, the network is poised to launch in 2018 and will be by far the biggest improvement in transaction scalability thus far.

如前所述，SegWit为雷击网络铺平了道路，因为它消除了节点修改目击者数据的能力，这是用来识别用户进入第二层的。如果由于涉及用户的见证数据被改变而无法找到用户的承诺交易，则在试图调和用户的结算交易时涉及更大的难度。

涉及渠道工厂的雷电网络的第二层最近在本白皮书中介绍。目前仍处于重大的发展阶段，很多概念都被抽象地解释了。不过，该网络将于2018年推出，迄今为止是迄今为止交易可扩展性方面的最大改进。

### Schnorr Signatures | Schnorr签名

When a user sends a Bitcoin transaction, the inputs of the transaction (the amount you’re sending) is calculated simply by retrieving from the blockchain the total unspent amounts of Bitcoin you previously received. So for example:

* Starting with an empty wallet, I receive 1 Bitcoin in transaction #1, and then another 1 Bitcoin in a separate transaction #2

* I now want to send 2 Bitcoins in a transaction. There will be two inputs to this transaction: transaction #1, and transaction #2, summing up to 2 Bitcoin

当用户发送比特币交易时，只需从区块链中检索您以前收到的未使用比特币总额即可计算交易输入（您发送的金额）。举个例子：

* 从一个空的钱包开始，我在交易＃1中收到1个比特币，然后在另外一个交易＃2中收到另一个比特币

* 我现在想在交易中发送2比特币。这个交易将有两个输入：交易＃1和交易＃2，总计2个比特币

Under the current algorithm for generating signatures (Elliptic Curve Digital Signature Algorithm), each input requires its own signature. This increases the total transaction size and therefore increases the transaction fee.

在现有的签名算法（椭圆曲线数字签名算法）下，每个输入都需要自己的签名。这增加了总交易量，因此增加了交易费用。

![](https://cdn-images-1.medium.com/max/1600/1*byA4UmLgEij_1oGp2EaLjg.png)

Currently, each input requires a signature, increasing total transaction size | 目前，每个输入都需要签名，增加了总的交易规模

*Schnorr signatures are an alternative and more efficient way of storing signature data in transactions. All inputs are accumulated and then stored as a single signature by utilizing the Schnorr algorithm, which greatly saves space in a transaction and further helps increase transaction throughput by allowing blocks to store more transactions on average.*

Schnorr签名是在交易中存储签名数据的另一种更有效的方式。所有的输入都被累积，然后通过Schnorr算法被存储为一个单一的签名，这大大节省了事务空间，并且通过允许块平均存储更多的事务来进一步提高事务吞吐量。

![](https://cdn-images-1.medium.com/max/1600/1*22yyLNKn02a-D7YsDgRw5A.png)

All sender signatures are stored as one signature under the Schnorr algorithm | 所有发送者签名都作为一个签名存储在Schnorr算法下


Schnorr signatures can be also be used to aid Bitcoin’s advancement in privacy by benefiting CoinJoin transactions. CoinJoin is a method of introducing anonymity to Bitcoin transactions. It works by pooling transaction inputs together with other peoples’ transactions when making a payment to a receiver. When payments are pooled, it becomes difficult to track which user sent what input, effectively making them anonymous. However, CoinJoin transactions have increased fees due to a higher number of inputs in a single transaction resulting in a higher number of signatures. Utilizing Schnorr signatures would enable all signatures in a transaction to be compressed into one, saving greatly on transaction fees and encouraging the use of CoinJoin.

Furthermore, Schnorr paves the way for complex multisig transactions which require signing off from multiple parties; no matter how many parties’ signatures are required for a transaction, all the transaction needs is one Schnorr signature.

Schnorr signatures are only now a possibility because of the implementation of SegWit; because signature data can’t be modified by third parties, it can now be used to effectively create a Schnorr signature.

Schnorr签名也可以用来帮助比特币的隐私进步，受益于CoinJoin交易。CoinJoin是一种向比特币交易引入匿名的方法。它通过在向接收者付款时将交易输入与其他人的交易汇集在一起​​而起作用。当付款汇集后，很难跟踪哪个用户发送了什么输入，有效地使他们匿名。然而，CoinJoin交易增加了费用，因为在单个交易中输入的数量更多，签名数量更多。使用Schnorr签名可以使交易中的所有签名被压缩为一个，大大节省交易费用并鼓励使用CoinJoin。

此外，Schnorr为需要从多方签字的复杂多重交易铺平了道路; 无论交易需要多少方签名，所有的交易需求都是一个Schnorr签名。

由于SegWit的实施，Schnorr签名现在才成为可能; 由于签名数据不能被第三方修改，现在可以用它来有效地创建一个Schnorr签名。

### MimbleWimble |

MimbleWimble is a radical but incredibly powerful proposed change to Bitcoin architecture that was anonymously introduced through this [whitepaper](https://download.wpsoftware.net/bitcoin/wizardry/mimblewimble.txt) in July 2016.

Named after the [tongue-tying curse from the Harry Potter series](http://harrypotter.wikia.com/wiki/Tongue-Tying_Curse), its aim is to remove transactions entirely from blocks. Under MimbleWimble, transactions consist of nothing but input amounts, output amounts, and a signature. The signature of the transaction can only be decrypted by the receiver, and so transaction verification is left to the receiver.

By extension, blocks consist of only the list of all transaction input amounts of all transactions, all transaction output amounts, and their corresponding signatures. Blocks can then be merged seamlessly with previous blocks as they’re nothing but pairs of input and output amounts. Nodes then have the ability to cryptographically ensure that transactions in blocks do not create extra bitcoins (i.e. their net difference between inputs and outputs in blocks is 0) without having to decrypt transactions.

MimbleWimble是对比特币架构的一个激进但却非常强大的改​​变，在2016年7月通过此白皮书匿名推出。

以“哈利·波特”系列的诅咒诅咒命名，其目的是完全取消交易。在MimbleWimble下，交易只包含输入金额，输出金额和签名。交易的签名只能由接收方解密，交易验证留给接收方。

通过扩展，块只包含所有交易的所有交易输入金额，所有交易输出金额及其相应的签名的列表。块可以与之前的块无缝合并，因为它们只是输入和输出量的对。然后，节点能够以加密方式确保块中的事务不会创建额外的比特（即，它们在块中的输入和输出之间的净差值为0），而不必解密事务。

This removal of transaction storage grants complete anonymity to all users by stripping away the ability to generate transaction history. Furthermore, with blocks only containing the **unspent transaction outputs** (meaning the number of Bitcoins that have been received in an address but not moved out yet), the blockchain size can be reduced by over 60% according to the whitepaper. This reduction in size means that in order to validate a MimbleWimble blockchain, nodes will only need to look at the set of unspent transaction outputs instead of the entire set of transactions, which will exponentially increase performance.

这种删除交易存储通过剥离生成交易历史记录的能力而赋予所有用户完整的匿名性。此外，根据白皮书，只有包含未使用的交易输出（即在地址中收到但未移出的比特币数量）的区块，区块链大小可以减少60％以上。这种大小的缩减意味着为了验证MimbleWimble区块链，节点只需要查看未使用的事务输出集合，而不是整个事务集合，这将成倍地提高性能。

The mathematical details of MimbleWimble are outside of the scope of this article, but are explained in detail in the whitepaper. Although MimbleWimble presents some clear advantages and technical breakthroughs, its implementation requires the removal of Bitcoin’s Script system that much of the existing architecture relies on. As a result, MimbleWimble’s implementation on the Bitcoin blockchain is not technically feasible.

However, there are proposals for MimbleWimble to exist as a sidechain. A sidechain is a separate blockchain directly attached to the Bitcoin blockchain through the use of a two-way peg. This peg enables assets between the two chains to be exchanged and “pegs” the value of the sidechain asset to the value of Bitcoin. In this setup, users would be able to exchange Bitcoins for MimbleWimble coins, conduct completely private and rapid transactions on the MimbleWimble chain, and then exchange their MimbleWimble coins for Bitcoin whenever they please.

MimbleWimble的数学细节超出了本文的范围，但在白皮书中有详细的解释。尽管MimbleWimble提供了一些明显的优势和技术突破，但其实施需要删除现有体系结构所依赖的比特币脚本系统。因此，MimbleWimble在比特币区块链上的实施在技术上是不可行的。

不过，有人建议MimbleWimble作为一个侧链存在。侧链是一个独立的区块链，通过使用双向挂钩直接连接到比特币区块链。这种挂钩使两链之间的资产能够交换，并将侧链资产的价值“钉住”到比特币的价值。在这种设置中，用户将能够以MimbleWimble硬币兑换比特币，在MimbleWimble链上进行完全私密和快速的交易，然后随时将他们的MimbleWimble硬币兑换成比特币。

![](https://cdn-images-1.medium.com/max/2000/0*shjdJcexgSIUXttC.png)
Sidechain coins are pegged to the Bitcoin blockchain, operating alongside it with a fixed exchange rate, source: [Blockchain.com](http://blockchain.com/) | 侧链硬币固定在比特币区块链上，以固定汇率同时运行，资料来源：Blockchain.com

In fact, a group of developers are already in the process of developing MimbleWimble as a separate cryptocurrency called [GRIN](https://github.com/mimblewimble/grin); it was recently deployed on a test network and may be launched in the near future.

事实上，一群开发者已经在开发MimbleWimble作为一个独立的加密货币GRIN ; 它最近部署在测试网络上，并可能在不久的将来发射。


### Rootstock | 砧木

>Rootstock — Smart Contracts on the Bitcoin Blockchain

>As a concept the Rootstock [1] platform is one of those ideas that once it is proposed it is obvious that it is a great…
medium.com
https://medium.com/@CryptoIQ.ca/rootstock-smart-contracts-on-the-bitcoin-blockchain-e52b065421a8

>Rootstock - 比特币区块链上的智能合约

>作为一个概念，Rootstock [1]平台就是这样一个想法，一旦被提出，显然它是一个伟大的...
medium.com

Rootstock is for whatever reason one of the less talked about advancements in Bitcoin technology but is by far one of the coolest. Rootstock is described as “the first open-source smart contract platform with a 2-way peg to Bitcoin that also rewards the Bitcoin miners via merge-mining, allowing them to actively participate in the Smart Contract revolution.”

Much like MimbleWimble, Rootstock is being developed as a sidechain solution to the Bitcoin blockchain. Its fundamental value lies in its focus in smart contracts. Rootstock aims to be a [Turing Complete](https://simple.wikipedia.org/wiki/Turing_complete) (completely programmable) smart-contracts platform that will be backwards compatible with Ethereum’s virtual machine. This means that Rootstock will be able to execute any smart contracts developed for the Ethereum platform and have smart contracts developed for its own platform.

砧木无论是什么原因都是比特币技术中少有人谈论的进步之一，但却是迄今为止最酷的之一。砧木被形容为“第一个开放源代码的智能合约平台，双向与比特币挂钩，也通过合并挖矿来奖励比特币矿工，使他们能够积极参与智能合约革命。”

就像MimbleWimble一样，Rootstock正在开发成比特币区块链的侧链解决方案。其基本价值在于其重点在智能合约。Rootstock的目标是成为一个图灵完全（完全可编程）的智能合约平台，这个平台将向后兼容以太坊的虚拟机。这意味着Rootstock将能够执行为以太坊平台开发的任何智能合约，并为自己的平台开发智能合约。

Rootstock aims to implement this versatile smart-contract functionality all while leveraging Bitcoin’s comparatively dominant userbase and value by acting as a two-way pegged sidechain. It is also being designed to be secured by the existing Bitcoin mining network, therefore not needing to incentivize miners to secure its own blockchain. Rootstock also aims to tackle the transaction scalability problem by implementing its own version of a multi-layered solution called [Lumino](https://uploads.strikinglycdn.com/files/9dcb08c5-f5a9-430e-b7ba-6c35550a4e67/LuminoTransactionCompressionProtocolLTCP.pdf). With this, it may be able to accomplish up to 20,000 transactions per second.

*Rootstock is aiming for [a launch by the end of 2017](https://www.coindesk.com/bitcoin-startup-rsk-launch-smart-contracts-sidechain-2017/). Overall, the platform aims to fit in perfectly alongside Bitcoin and if its claims hold true, it will undoubtedly bring unprecedented utility to the Bitcoin network.*

Rootstock的目标是实现这种多功能的智能合约功能，同时充当比特币相对占统治地位的用户群和价值，充当双向挂钩的侧链。它也被设计成由现有的比特币挖掘网络来保证，因此不需要激励矿工来保护自己的区块链。Rootstock还旨在通过实施其自己版本的称为Lumino的多层解决方案来解决事务可伸缩性问题。有了这个，它可能能够完成每秒高达20,000笔交易。

砧木的目标是到2017年底推出。总的来说，这个平台的目标是与比特币完美契合，如果它的声明成立，它无疑将为比特币网络带来前所未有的效用。



If you’ve gotten this far, congratulations! I hope you were able to learn something about the future of Bitcoin and are as excited about it as I am.

Bitcoin isn’t perfect and is faced with challenges that its community must work to solve. However, it is backed by an incredibly dedicated and thriving developer community that is working day in and day out to tackle these problems. There are constant innovations happening everyday, and I am sure by the time you finished reading this another new and exciting proposal for the Bitcoin blockchain popped up.

This article by no means covers everything out there; if there’s anything that you’re aware of that I didn’t mention, please mention them in the comments!

如果你已经得到这么多，祝贺！我希望你能够学习一些关于比特币未来的东西，并且像我一样激动。

比特币并不完美，面临着社区必须解决的挑战。然而，它却得到了一个令人难以置信的热情开发者社区的支持，他们每天都在努力解决这些问题。每天都有不断的创新，而且我相信在你读完这个比特币区块链的另一个令人兴奋的新建议之后，

这篇文章决不是涵盖了所有的东西。如果有什么你知道的，我没有提到，请在评论中提及它们！

Follow me on Twitter and Medium if you’re interested in more in-depth and informative write-ups like these in the future!
I’m a relative Bitcoin beginner myself so if there are any mistakes or if you have any feedback please don’t hesitate let me know!

BTC Address: 3MGguJhw1bm95tDQjZ3b8ySBwZLJ77CgG1

如果您有兴趣在将来更深入和翔实的文章，请关注我的推特和中介。
我是一个相对比特币初学者，所以如果有任何错误，或者如果您有任何反馈，请不要犹豫，让我知道！
BTC地址：3MGguJhw1bm95tDQjZ3b8ySBwZLJ77CgG1

Here are some resources if you’re interested in learning more:

* [Mastering Bitcoin](https://github.com/bitcoinbook/bitcoinbook), an comprehensive book written by [Andreas M. Antonopoulos](https://medium.com/@aantonop)

* [The Bitcoin Wiki](http://bitcoin.it/)

* [The Bitcoin whitepaper](https://lopp.net/pdf/bitcoin.pdf)

* [A collection of Bitcoin resources](https://lopp.net/bitcoin.html) by [Jameson Lopp](https://medium.com/@lopp)

* [This highly informative interview with Nick Szabos](https://www.google.ca/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=0ahUKEwiznZ-Oo-zXAhUW02MKHZ0aAhcQtwIILzAB&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D3FA3UjA0igY&usg=AOvVaw0JIy-AaKaXyDsGm8psm7Qj) conducted by [Tim Ferriss](https://medium.com/@timferriss)

* [Ivan on Tech on Youtube](https://www.youtube.com/channel/UCrYmtJBtLdtm2ov84ulV-yg), who is absolutely amazing at breaking down technical Bitcoin concepts

Thanks to Emma Soolepp.

Bitcoin Technology Blockchain Finance Business

这里有一些资源，如果你有兴趣学习更多：

* 掌握比特币，Andreas M. Antonopoulos撰写的综合性书籍

* 比特币维基

* 比特币白皮书

* 由Jameson Lopp 收集的比特币资源

* 这非常翔实的采访尼克Szabos通过进行蒂姆·费里斯

* 伊万技术在Youtube上，谁是绝对惊人的技术比特币概念

感谢 Emma Soolepp。

关键字：比特币 技术 区块链 金融 商业
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
