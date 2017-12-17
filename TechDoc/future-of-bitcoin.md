## What You Need to Know About the Future of Bitcoin Technology | 你需要了解的比特币技术的未来

> 本文翻译自：https://medium.freecodecamp.org/future-of-bitcoin-cc6936ba0b99

> 作者：Subhan Nadeem
软件工程师 | 计算机科学与商业学生@滑铁卢大学 & 威尔弗瑞德劳里埃大学|subhan-nadeem.com/linkedin

> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [鱼](https://github.com/oscnet)

> 翻译时间：2017-12-15

> 本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。

![](https://cdn-images-1.medium.com/max/2000/1*FfRqOEiRKdgvnbuvEgQF6g.jpeg)

Bitcoin (BTC) recently smashed an all-time high of $11,400 USD and subsequently dropped to as low as $8,595 within a few hours. It’s incredibly important to not get lost in the pandemonium and to stay informed about how Bitcoin is progressing technologically.

Anybody considering buying Bitcoin should at the very least learn two things:

1. the history of the technology behind Bitcoin

2. and more importantly, what lies ahead in Bitcoin’s future.

As Bitcoin expert [Andreas M. Antonopoulos](https://medium.com/@aantonop) says, “[Invest in education instead of speculation](https://www.youtube.com/watch?time_continue=328&v=6uXAbJQoZlE).”

比特币（BTC）最近一度创下了11,400美元的历史新高，随后在几个小时内跌至8,595美元。
在混乱中不迷失方向，并随时了解比特币在技术上的发展，是非常重要的。

考虑购买比特币至少应该知道：

1. 比特币背后的技术历史

2. 更重要的是了解比特币未来的前景。

正如比特币专家 [Andreas M. Antonopoulos](https://medium.com/@aantonop) 所说：“ [投资于教育而不要投资于投机买卖](https://www.youtube.com/watch?time_continue=328&v=6uXAbJQoZlE)。”

With Bitcoin and its underlying blockchain being such incredibly new technological concepts, it can seem daunting at times to try and research and understand its underlying technical details. This article is written in an effort to highlight the scalability problem Bitcoin faces, and what expected or proposed solutions to that problem are. There are some really exciting ones out there that this article discusses!

I wrote this as I was learning about Bitcoin myself, to aggregate the great amount of information about Bitcoin’s future from countless sources out there. When writing this, I kept in mind even those who don’t possess a programming background. However, it is assumed that the reader has a very basic understanding of Bitcoin as a currency and what a blockchain is. Coindesk has a great 5-minute read that should get you up to speed [here](https://www.coindesk.com/information/what-is-bitcoin/) if you’re just starting out with Bitcoin or if you need a refresher.

Let’s begin with the scalability problem Bitcoin faces.

随着比特币及其底层的区块链成为令人难以置信的新技术，尝试研究并理解其潜在的技术细节，有时会令人感到望而生畏。本文旨在描述比特币面临的可扩展性问题，以及该问题的预期或建议的解决方案。这篇文章也讨论了一些非常让人兴奋的比特币前景!

我以我自己也正在学习比特币的方式来写这篇文章，从海量的资源中收集有关比特币未来技术的大量信息，并进行了汇总。在写作的时候，我甚至也顾及了那些没有编程知识背景的人们。但是，还是需要读者对比特币作为货币有一个基本的了解，并且知道什么是区块链。
如果你刚开始了解比特币或对此需要进一步的复习，Coindesk 上有一个很棒的只需5分钟就能读完的[《比特币是什么》](https://www.coindesk.com/information/what-is-bitcoin/)，可以让你速成。

先让我们从比特币正在面临的可扩展性问题开始吧。

### The Transaction Throughput Problem | 交易吞吐量问题

When Bitcoin was first introduced to the world, its creator Satoshi Nakomoto described Bitcoin in the [Bitcoin whitepaper](https://bitcoin.org/bitcoin.pdf) as “A purely peer-to-peer version of electronic cash would allow online payments to be sent directly from one party to another without going through a financial institution.”

One of Bitcoin’s fundamental values was instant and secure peer-to-peer payment transactions. Now, more than ever, Bitcoin is emerging as the prevailing cryptocurrency in the global market, with a 1,200%+ increase in value over the last year alone.

Because of this unprecedented growth, the number of transactions on the Bitcoin blockchain has also increased, with up to [400,000 transactions per day](https://blockchain.info/charts/n-transactions) being conducted. This rapid increase in transactions is posing to be a serious scalability problem for the blockchain, with [over 90,000 transactions](https://blockchain.info/unconfirmed-transactions) being backlogged as unconfirmed at the moment.

当比特币首次被公开介绍时，其创始人 Satoshi Nakomoto 在比特币[白皮书](https://bitcoin.org/bitcoin.pdf)中将比特币描述为“一种完全通过点对点技术实现的电子现金系统，可以不经过财务机构，实现从一方直接发送到另一方的在线支付"。

比特币的基本价值之一是即时和安全的点对点支付交易。现在，比以往任何时候, 比特币都更加成为全球市场上流行的加密货币，仅比去年就增长了1200％以上。

由于这一前所未有的增长，比特币区块链交易的数量也相应地增加，[每天的交易量高达40万多笔](with up to 400,000 transactions per day being conducted)。交易量的迅速增长对区块链造成了严重的可扩展性问题，目前有超过[9万笔交易](https://blockchain.info/unconfirmed-transactions)积压未经确认。

![](https://cdn-images-1.medium.com/max/1600/1*kDRKF6Iu3wPbSByqSr32gw.png)
*As Bitcoin’s price skyrockets, so does its usage. Note the stagnation at around 400,000 transactions per day | 随着比特币的价格猛涨，使用量也是如此。请注意每天有大约40万笔交易积压*

In order to understand why transactions are being backlogged, Bitcoin transactions must first be explained.

Every time a user sends a Bitcoin transaction from his or her wallet to another, the transaction is added into the **memory pool** (mempool), which is essentially a pool of all unconfirmed transactions in the Bitcoin network. This pool is upheld by smaller individual pools on machines that hold a copy of the blockchain ledger, called **nodes**.

From the mempool, miners select transactions that they want to verify. Once miners validate a transaction (i.e. confirm that the sender actually has enough bitcoins to send to the receiver), they add it to a new block, which is eventually published to the blockchain. Other nodes then iterate through this newly published block’s transactions to ensure the block is valid, before accepting the block as a part of its ledger.

想知道交易为什么会被积压的问题，首先必须了解比特币交易。

每当用户从他或她的钱包中发送比特币到另一个人时，交易就被添加到**内存池**（mempool）中，内存池实际上保存了比特币网络中所有未经确认的交易。内存池的内容由被称为**节点**的机器上更小的单个内存池维护，这些的机器上保存有区块链帐本的拷贝。

矿工从内存池中选择他们想要验证的交易。一旦矿工确认交易（即确认发件人实际上有足够的比特币发送给收件人），他们就将它添加到一个新的块，并最终在区块链上公布。其他节点只有在遍历这个新发布的块的所有交易，并确保该块有效，才接受该块并加入其账本。

![](https://cdn-images-1.medium.com/max/2000/1*K6iO4o2oxd0IeU0luVze0w.png)
A diagram of the transaction lifecycle, source: [weusecoins.com](https://www.weusecoins.com/en/questions/) | 交易周期图，来源：
[weusecoins.com](https://www.weusecoins.com/en/questions/)

Let’s calculate the throughput of transactions:

* The median transaction size [approximately 250 bytes](https://tradeblock.com/blog/analysis-of-bitcoin-transaction-size-trends)

* A block’s size is limited to 1MB (1000000 bytes)

* Thus, a block holds around 4000 transactions (1MB divided by 250 bytes)

* A block can only be published to the blockchain once every 10 minutes on average (600 seconds).

* 4000 transactions (at most) are published every 600 seconds, at a rate of **6.66 transactions / second**

我们来计算下交易的吞吐量：

* 平均的交易数据大小约为 250 字节

* 一个块的大小限制为 1MB（1000000字节）

* 因此，一个块能保存大约 4000 个交易（ 1MB 除以 250 字节）

* 一个块平均约每 10 分钟才能发布到区块链（ 600 秒）。

* 4000 次交易（最多）每 600 秒发布一次，速度为 6.66 次/秒

With over 90,000 unconfirmed transactions in the mempool, how does a miner select which transactions to verify? Transaction fees! The sender of a transaction has the option of adding a custom transaction fee to its transaction intended for the miner, incentivizing a miner to select the transaction and have it verified faster. Miners will select the transactions that have the highest fee attached to them to maximize profits. Theoretically, you can send a transaction with no fee. But if there are transactions that have fees higher than yours in the pool, why would yours ever get picked?

*As Bitcoin’s user base grows, so does the average transaction fee. At most, there are only 7 transactions that are processed every second and everyone wants to get their transaction verified first.* At the moment, the average transaction fee is approximately [$3.58 USD](https://bitinfocharts.com/comparison/bitcoin-median_transaction_fee.html). This fee is certainly not ideal — if you want to send your friend a couple of dollars worth of bitcoin, you may end up spending more in transaction fees than the transaction value itself! Therein lies the problem, and if all else remains equal, transaction fees can be expected to rise due to the transaction bottleneck.

在内存池中有超过90,000个未经确认的交易，矿工以什么标准来选择验证哪笔交易呢？是通过给矿工的交易费用！交易的发起人可以在交易中设置较高的交易费，从而鼓励矿工优先选择这笔交易，以得到更快地验证。矿工将选择交易费最高的交易来实现利润最大化。理论上，您可以用 0 交易费发送交易。但是，如果内存池中有着交易费高于你的交易，那你的交易凭什么会被选中呢？

*随着比特币用户群的增长，平均交易费用也在增加。因为最多每秒处理 7 条交易，每个人都希望最先验证自己的交易*。目前，平均交易费用约为[3.58 美元](https://bitinfocharts.com/comparison/bitcoin-median_transaction_fee.html)。这笔费用当然不是理想的 - 如果你想给你的朋友发送价值几美元的比特币，最终你花费的交易费比
交易本身的价值还要高！这就是问题所在，如果其他条件保持不变，交易费用会因交易瓶颈而提高。

### Solving the Throughput Problem | 解决吞吐量问题

A proposed solution to this bottleneck that has brought great controversy to the Bitcoin community is to simply raise the block size from the original 1MB limit, thus allowing more transactions per block.

Every time the block size is increased in the chain, a **hard fork** is required, meaning an entirely new copy of the chain must be created, therefore requiring consensus from the Bitcoin community. Because millions of people use Bitcoin, gaining consensus is difficult and efforts should be made to avoid it. Furthermore, although the block size can be increased enough to accommodate the current backlog of transactions, as Bitcoin’s userbase continues to grow, there will eventually be another backlog of unconfirmed transactions, so another block size increase will be needed, and subsequently another hard fork.

So why don’t we just make the block size large enough to ensure the throughput will never be a bottleneck, no matter how many people are using it? First, the mathematics of a block size even remotely large enough to handle mass adoption are impractical and will restrict mining to incredibly powerful machines that only large corporations will be able to maintain, introducing an element of centralization.

针对这个瓶颈提出的一种解决方案，给比特币社区带来了巨大的争议，就是简单地提高块的大小，突破原来 1MB 的限制，从而让每个块上能够存放更多的事务。

每当链中的块增加大小时，都需要一个**硬分叉**，这意味着必须创建一个全新的链，因此需要比特币社区的共识。由于有数百万人使用比特币，要达成共识非常困难，所以硬分叉应该努力避免。此外，尽管块可以增加到足以容纳当前积压的交易，但随着比特币用户数量的不断增长，又会引起有未确认的交易积压，因此又需要增加块大小，这样又将引起另外一个硬分叉。

那么我们能不能把块大小设置成足够大，无论以后有多少人使用，都能确保吞吐量永远不会成为瓶颈？首先，
采用极大的数据块大小，来处理大量数据是不切实际的，这将引起只有强大的机器才能挖矿的后果，而这么强大的机器最后只能大公司才能维持，这样就引入了中心化的元素。

![](https://cdn-images-1.medium.com/max/2000/1*GF7OTotvNMX6hmHkeIAfYQ.png)
*Given a block size big enough for just one city’s population, it would restrict node hosting and mining to only those with the most powerful machines, i.e. massive businesses, source: [Lightning Network](https://lightning.network/lightning-network.pdf) | 当块大到能满足一个城市的人口时，只有那些拥有最强大机器的大型企业才能进行节点托管和挖矿。图片来源：[Lightning Network](https://lightning.network/lightning-network.pdf)*

Furthermore, recall that once a block is mined, all other nodes must validate the block before accepting it. *If the block size was incredibly large and somebody were to publish an invalid block, nodes would waste a large amount of time attempting to validate the block before discarding it as invalid and moving onto the next block.* A denial of service attack can essentially be orchestrated by repeatedly publishing insanely large invalid blocks to the network, stopping valid blocks from being processed for a long period of time. As stated by blockchain pioneer Nick Szabo in [this interview](https://medium.com/@giftedproducts/cryptocurrencies-with-tim-ferriss-nick-szabo-and-naval-ravikant-51a99d037e04), the small block size acts as a technical security parameter to prevent network flooding.

*You can read more about the full impact of an increased block size if Bitcoin were to take over the world, in an article I’ve written [here](https://hackernoon.com/if-we-lived-in-a-bitcoin-future-how-big-would-the-blockchain-have-to-be-bd07b282416f).*

此外，回想一下，一旦一个块挖掘出来，所有其他节点必须在接受它之前验证这个块。**如果块非常大，有人发布了一个无效的块，节点就会浪费大量的时间来验证该块，然后才能将其丢弃视为无效并转到下一个块处理**。本质上可以长时间、反复向网络发布非常大的无效块，来阻止有效块地处理。从而造成拒绝服务攻击。正如区块链先驱 Nick Szabo 在[此次采访](https://medium.com/@giftedproducts/cryptocurrencies-with-tim-ferriss-nick-szabo-and-naval-ravikant-51a99d037e04)中指出的那样，保持小块能防止网络洪水攻击，是一项技术安全参数。

如果想了解更多，关于当比特币被全世界接受时，增加块大小所能造成的全面影响，可以看看我写的[有关于此的文章](https://hackernoon.com/if-we-lived-in-a-bitcoin-future-how-big-would-the-blockchain-have-to-be-bd07b282416f)。

If we can’t increase the block size, what can we do? Luckily, there are several solutions in the works that are expected to be deployed in order to solve this issue.

如果不能增加块的大小，又该怎么办呢？幸运的是，为了解决这个问题，一些正在进行中的解决方案预计将会部署。

### Segregated Witness (SegWit) | 隔离验证（SegWit）

*Segregated Witness (SegWit) has actually already been implemented into the Bitcoin network, as of August 2017. It’s a fundamental network change that modifies the format of transactions, essentially slimming them down in size, and allowing more transactions to be fit into a block which increases throughput.* SegWit is considered a **soft fork**, meaning it is completely backwards compatible with existing Bitcoin protocol, although nodes and wallets must upgrade to take advantage of all SegWit features.

Each transaction has a signature from the sender, or in other words, **witness data**; this is usually the largest part of the transaction. This data is not actually necessary to verify the transaction, and so SegWit moves this data to the end of the transaction, segregating it. If this transaction is sent to a legacy node (a node that has not upgraded to SegWit), the node strips the witness data off the end of the transaction before inserting it into a block, thus reducing the overall transaction size and saving space. The added benefit of this is that nodes can no longer modify the witness data, changing who the transaction was from, an ability nodes previously had. This makes way for the implementation of multi-layer solutions that we’ll discuss soon. Users also save on transaction fees, as they’re usually calculated per transaction byte, and SegWit reduces total transaction size.

*从2017年8月起，隔离验证（SegWit）实际上已经应用到比特币网络中。这是一项基本的网络更改, 它修改了交易存储的格式, 实质上缩小了交易大小, 使一个块能够放入更多的交易, 因而增加了吞吐量
。* 隔离验证被认为是一个软分叉，意味着它完全向后兼容现有的比特币协议，尽管节点和钱包必须升级才能充分利用隔离验证的所有功能。

每笔交易都有发件人的签名，即用于验证的数据; 这些通常占具了交易的大部分空间。这些数据实际上并不是验证交易所必需的，因此隔离验证会将这些签名数据移到交易的末尾，使签名和交易数据分开。如果这个交易被发送到一个遗留节点（一个没有升级到隔离验证的节点），节点将验证数据从交易末尾剥离，然后再将其插入到块中，从而减少了整个交易占用的空间大小。这样做的另一个好处就是节点不能象以前那样可以再修改验证数据，从而改变交易的来源。这为我们即将讨论的多层解决方案的实现提供了方便。用户还可节省交易费用，因为它们通常是按每个交易所用的字节计算的，因为隔离验证减少了全部交易占用的空间大小。

![](https://cdn-images-1.medium.com/max/2000/1*4IKDVzPN0FzJFgOnZADoIQ.png)
*SegWit moves signature data to the end of transaction, after which stripped before being stored in a block, source: [Programming Blockchains](https://programmingblockchain.gitbooks.io/programmingblockchain/content/other_types_of_ownership/p2wpkh_pay_to_witness_public_key_hash.html) | 隔离验证将签名数据移动到交易末尾，并在存储到块之前剥离出来，来源：[Programming Blockchains](https://programmingblockchain.gitbooks.io/programmingblockchain/content/other_types_of_ownership/p2wpkh_pay_to_witness_public_key_hash.html)*

Furthermore, SegWit changes the definition of a block: instead of a block being defined in terms of bytes, its now defined in terms of “weights”; a block can have a maximum weight of 4,000. Legacy transactions have a weight of 4, while SegWit transactions have a weight of 0.25, thus enabling a block to contain many more SegWit transactions and have a slightly higher size (approximately 2 megabytes at most). Nodes must upgrade to SegWit to follow this definition, and wallets must incorporate SegWit in order to send SegWit transactions. As a result, SegWit adoption has been slow, accounting for only 12% of current traffic.

此外，隔离验证改变了一个块的定义，原来用字节为单位定义的块，现在改用“区块重量”来定义。一个块最大重量为 4000 。一条传统交易的重量为 4，而隔离验证交易的重量为 0.25，从而使块能够包含更多的隔离验证交易，并且具有略高的大小（最多大约 2 兆字节）。节点必须升级到隔离验证才能遵循此定义，并且钱包必须包含隔离验证才能发送隔离验证交易。因此，隔离验证的采用速度非常地慢，仅占当前流量的12％。

![](https://cdn-images-1.medium.com/max/2000/1*GQjWddG72KhXJYQ3k-bnQg.png)
Current state of SegWit adoption hovers around 12% of all transactions, [source: segwit.party](http://segwit.party/charts/) | 隔离验证约占所有交易的12％，来源：[segwit.party]((http://segwit.party/charts/)


*Because of the aforementioned benefits of SegWit, I highly encourage anybody reading this to use wallets that have incorporated SegWit to speed up SegWit adoption.* A neat list of them can be found [here](https://bitcoincore.org/en/segwit_adoption/) (my personal favourite is [Samourai Wallet for Android](https://samouraiwallet.com/)). If you want to learn more about the intricacies of SegWit, [Jimmy Song](https://medium.com/u/4acb12744ff8) has written a great article about it:

*鉴于隔离验证的上述优势，我强烈建议阅读以下文章，以便使用包含隔离验证的钱包来加速隔离验证的应用*。一个整洁的列表可以在[这里](https://bitcoincore.org/en/segwit_adoption/)找到（我个人最喜欢的是安卓的 [Samourai钱包](https://samouraiwallet.com/)）。如果您想了解更多关于隔离验证的错综复杂的信息，[Jimmy Song](https://medium.com/u/4acb12744ff8)写了一篇很棒的文章：

> Understanding Segwit Block Size

> After I wrote my last article, I was surprised by the protest about the 2MB part of the title (the title has since been…

> medium.com https://medium.com/@jimmysong/understanding-segwit-block-size-fd901b87c9d4

> 了解Segwit块的大小

> 在我写了我的上一篇文章后，我惊讶于大家对文章标题中有关 2MB 部分的抗议（标题已经...

> medium.com https://medium.com/@jimmysong/understanding-segwit-block-size-fd901b87c9d4


### Multi-Layered Solutions | 多层解决方案

*As it stands, the Bitcoin blockchain isn’t very feasible for micropayments. If you want to buy a $2 cup of coffee, you’re probably going to pay more than $2 equivalent of BTC in transaction fees, and the transaction won’t be confirmed instantly — you must wait for the transaction to be published in a verified block on the chain, which will appear within 10 minutes at best.*

*Second and third layer solutions are networks layered on top of the Bitcoin blockchain that enable users to send several transactions of small amounts of Bitcoin almost instantly, with no transaction fees.*

**The Lightning Network** is this layered network currently in development expected to alleviate Bitcoin’s scaling problems. This network consists of two additional layers and enables users to open direct channels between each other to send an effectively unlimited number of payments to each other in an instant manner.

*就目前而言，比特币区块链对于小额支付来说不是很可行。如果你想购买 2 美元的咖啡，你可能要支付超过 2 美元的比特币等值交易费用，交易还不能马上确认 - 你必须等待交易纳入到已验证的块，并公布在区块链上，最快是10分钟。*

*第二层和第三层解决方案是在比特币区块链上分层的网络，用户间能够瞬时完成少量比特币的交易，且无需交易费用。*

*闪电网络* 是目前正在开发的分层网络，预计可以缓解比特币的扩展问题。该网络由两个附加层组成，使用户能够在彼此之间打开直接的通道，以即时的方式相互发送无限次数的支付。

>Lightning Network

>The Lightning Network is dependent upon the underlying technology of the blockchain. By using real Bitcoin/blockchain…
lightning.network
https://lightning.network/

> 闪电网络

> 闪电网络是依赖于区块链的底层技术。通过使用真正的比特币/区块链 ...

> [lightning.network](https://lightning.network/)

### The Second Layer | 第二层

A user joins the second layer network by conducting a transaction on the blockchain that declares the user is committing a certain number of bitcoin to be used in the layered network. The user then joins a group of nodes that are interconnected with one another, called **channel factories**. These nodes essentially uphold a lobby of individuals that potentially want to conduct transactions with one another. Channel factories then enable an unlimited number of micropayment channels to be created on the third layer (hence the name factories) between individual parties.

用户通过发送交易到区块链上来加入第二层网络，该交易声明用户正在提交一定数量的比特币用于分层网络。然后用户加入一组相互连接的节点，称为**通道工厂**。这些节点本质上是一个交易大厅，想要彼此进行交易的个人可通过大厅进行交易。通道工厂然后在第三层上创建各方之间可以进行无限次数微支付的通道（因此叫工厂）。

![](https://cdn-images-1.medium.com/max/1600/1*AjpC5PHSLvJ-drKZI-7JpA.png)
*From the [whitepaper](https://www.tik.ee.ethz.ch/file/a20a865ce40d40c8f942cf206a7cba96/Scalable_Funding_Of_Blockchain_Micropayment_Networks%20%281%29.pdf): users are hooked into a channel factory upon joining the network, which then allocates multiple micropayment channels | 摘自白皮书：用户在加入网络后被连接到一个渠道工厂，然后分配多个微支付通道*

### The Third Layer | 第三层

*Micropayment channels are set up to ensure direct payments between two users on the third layer.* Because the blockchain is no longer present in this layer, it cannot be used to validate transactions and ensure one party paid the other. Instead, smart-contract technology is employed, such as **multisig addresses**, meaning addresses that can be signed off by multiple users to enable the movement of funds, and **hashed time-lock contracts**, which are cryptographically secure automated contracts that lock funds for a certain period of time to ensure one parties that cannot cheat with another. These technologies eliminate the need for trust between users that are connected in micropayment channels.

*小额支付通道的建立是为了确保第三层两个用户之间的直接支付。* 由于此层不再存在区块链，因此不能用于验证交易，以确保一方支付给了另一方。因此，采用了智能合约技术，如**多重签名地址**，
这样的地址可以由多个用户签名以实现资金流动。以及**哈希化时间锁定合约**，这是一种密码安全的自动化合同，将资金在固定时间内锁定，以确保一方不能欺骗另一方。这些技术提供了小额支付渠道中连接的用户之间的信任需求。

Here is an example of how a Lightning Network micropayment channel works:

1. Alice wants to dedicate 1 Bitcoin to a micropayment channel between Bob. She declares this 1 Bitcoin to be used in a **commitment transaction** on the Bitcoin blockchain. This 1 Bitcoin is then locked up in a **multisig address** that both parties can sign off on if they want to close the channel. This address is secured with a **hashed time-lock contract** which states, “Alice has 1 BTC and Bob has 0 BTC, to be released in one hour”. This means the 1 Bitcoin Alice has is locked for 1 hour after which it will be returned to Alice and published to the Bitcoin blockchain once more.

2. Alice then decides to give Bob 0.1 BTC. This transaction is logged with a new hashed time-lock contract stating “Alice has 0.9 BTC and Bob has 0.1 BTC, to be expired in 50 minutes”. This contract has an expiry time of 50 minutes, meaning it will be published to the blockchain before the original contract stating Alice has 1 BTC. Therefore Bob instantly knows he has the 0.1 BTC because this new contract will be published to the blockchain before the original contract, essentially making the old contract invalid.

3. Once the full hour passes, the micropayment channel closes and the final balance between Alice and Bob is published to the blockchain. If Alice and Bob want to continue making transactions, they can extend the expiry time of their channel for as long as they want. If one of them wants to close the channel early, one of them needs to sign off on the original multisig address that the Bitcoin is stored in.

以下是闪电网络的微支付通道如何工作的示列：

1. 爱丽丝想把 1 个比特币专用于和鲍勃之间的一个微型支付通道。她宣称这个比特币将用于比特币区块链的** Commitment Transaction 承诺交易**(译者注：Commitment Transaction 是指闪电网络通道内的交易，没有在扩展区块里结算的交易，这里暂译为承诺交易)。然后这 1 比特币被锁定在一个**多重签名地址**中，如果双方想要关闭该频道，双方都可以对此进行签名。这个地址由一个**哈希化时间锁定合约**保护，该合约规定“爱丽丝拥有 1 BTC，鲍勃有 0 BTC，并将在一个小时后解约”。这意味着爱丽丝被锁定的 1 比特币在 1 小时后，将再次发布到比特币区块链并退回给爱丽丝。

2. 爱丽丝然后决定给鲍勃 0.1 BTC。这笔交易以一个新的哈希化时间锁定合约进行记录，指出“爱丽丝有 0.9 个比特币，鲍勃有 0.1 个比特币，在50分钟后到期”。此合约的到期时间为 50分钟，这意味着它将在原始合同声明爱丽丝有 1 个比特币 之前发布到区块链。所以鲍勃立即知道他有 0.1 个比特币，因为这个新的合同将在原始合同之前发布到区块链上，从而使旧合同无效。

3. 一个小时过去后，微支付通道关闭，爱丽丝和鲍勃之间的最终账目将被发布到区块链上。如果爱丽丝和鲍勃想继续交易，他们可以延长他们通道的到期时间，只要他们愿意，他们想要延长多长时间都可以。如果其中一个人想要提前关闭通道，他就需要在存储比特币的原多重签名地址上签名。

*The network enables transactions to route itself to its final destination by using other connected users in the channel as intermediaries.* This can happen even if a direct connection to the desired user isn’t able to be sought the current micropayment channel. For example, if Alice has a channel open with Bob, and Bob has a channel with Mark, and Alice wants to send Mark some Bitcoin, the network can route the payment to Mark through Bob, all while ensuring no party has to trust another.

*闪电网络使交易可以通过使用通道中的其他连接用户作为中介，将自己发送到最终目的地。*
即使不能在当前微支付信道中找到一个能直接连接到所需用户的情况下，也可以完成支付交易。
例如，如果爱丽丝有一个跟鲍勃打开的通道，而鲍勃有一个跟麦克的通道，爱丽丝想要发送一些比特币给麦克，那么闪电网络可以通过鲍勃将比特币支付给麦克，并且在此过程中任何一方都不必相任另一方。

![](https://cdn-images-1.medium.com/max/1600/1*qtUo7s-5lIOhoxUKe7w99g.png)
*In the lightning network, transactions are routed through intermediate users in order to reach its final destination | 在闪电网络中，交易可通过中间用户路由到达到其最终目的地*

The implementation of lightning network transactions and their trust-less nature can get incredibly complex, and is best explained by the Lightning developers in [this conference](https://www.youtube.com/watch?v=8zVzw912wPo) or in the following series by [ecurrencyhodler](https://medium.com/@ecurrencyhodler):

> The Lightning Network (Part 1)

>Multisig Addresses: The Building Blocks of the Lightning Network
medium.com
https://medium.com/the-litecoin-school-of-crypto/a-primer-to-the-lightning-network-part-1-be909c403bde

闪电网络交易的实施和它们的无信任性质可能会变得非常复杂，详情请看由闪电网络开发人员在[这次会议](https://www.youtube.com/watch?v=8zVzw912wPo)或[数字货币持有者](https://medium.com/@ecurrencyhodler)的以下系列：

>闪电网络（第1部分）

>多重签名地址：闪电网络的构建块

>medium.com https://medium.com/the-litecoin-school-of-crypto/a-primer-to-the-lightning-network-part-1-be909c403bde


Ideally, a user will only create a commitment transaction to the secondary layer very rarely because he or she will remain in the layered network for prolonged periods of time to conduct most of their day-to-day transactions. Once a user wants to exit this multi-layered network, a **settlement transaction** is made on the blockchain declaring the user’s final Bitcoin balance after all of the second-layer activities. This reconciles their total Bitcoin balance on the blockchain after comparison with the original commitment transaction. In total, only two blockchain transactions are made in order to let the user to conduct a limitless number of transactions for free on the second layer.

理想情况下，用户很少会创建一个到第二层的承诺交易，因为他或她将长时间停留在分层网络中进行大部分的日常交易。一旦用户想要退出这个多层网络，就会在区块链上进行**交易结算**，在所有的第二层活动结束之后宣布用户的最终比特币余额。通过比较原始的承诺交易，使得他们在区块链上的比特币帐目总额达到了一致。为了让用户在第二层免费进行无限次的交易，在区块链上总共只进行了二次交易。

As mentioned previously, SegWit paves the way for the lightning network because it removes nodes’ abilities to modify witness data, which is what is used to identify a user’s entry into the second layer. If the user’s commitment transaction can’t be found because the witness data referring to the user was changed, there is a greater level of difficulty involved when trying to reconcile the user’s settlement transaction.

The second layer of the lightning network involving channel factories was very recently introduced in [this whitepaper](https://www.tik.ee.ethz.ch/file/a20a865ce40d40c8f942cf206a7cba96/Scalable_Funding_Of_Blockchain_Micropayment_Networks%20%281%29.pdf). It is still under heavy development, so a lot of its concepts are explained abstractly. However, the network is poised to launch in 2018 and will be by far the biggest improvement in transaction scalability thus far.

如前所述，隔离验证为闪电网络铺平了道路，因为它消除了节点修改验证数据的能力，可以用来识别进入第二层的用户。如果由于涉及用户的验证数据被改变从而无法找到用户的承诺交易，当试图协调用户的结算交易时，会遇到更大的困难。

涉及通道工厂的雷电网络的第二层原理最近在[白皮书](https://www.tik.ee.ethz.ch/file/a20a865ce40d40c8f942cf206a7cba96/Scalable_Funding_Of_Blockchain_Micropayment_Networks%20%281%29.pdf)中有介绍。目前仍处于繁重的开发阶段，所以很多概念只能进行抽象地解释。不过，该网络有望于2018年推出，这将是迄今为止有关在交易可伸缩性方面最大的改进。

### Schnorr Signatures | Schnorr 签名

When a user sends a Bitcoin transaction, the inputs of the transaction (the amount you’re sending) is calculated simply by retrieving from the blockchain the total unspent amounts of Bitcoin you previously received. So for example:

* Starting with an empty wallet, I receive 1 Bitcoin in transaction #1, and then another 1 Bitcoin in a separate transaction #2

* I now want to send 2 Bitcoins in a transaction. There will be two inputs to this transaction: transaction #1, and transaction #2, summing up to 2 Bitcoin

当用户发送比特币交易时，只需从区块链中检索您以前收到的未使用比特币总额即可计算交易输入（您发送的金额）。举个例子：

* 从一个空的钱包开始，我在交易＃1 中收到 1 个比特币，然后在另外一个交易＃2 中收到另一个比特币

* 我现在想在交易中发送 2 个比特币。这个交易将有两个输入：交易 ＃1 和交易 ＃2 ，总计 2 个比特币

Under the current algorithm for generating signatures (Elliptic Curve Digital Signature Algorithm), each input requires its own signature. This increases the total transaction size and therefore increases the transaction fee.

在现有的签名算法（椭圆曲线数字签名算法）下，每个输入都需要有自己的签名。这增加了交易所占据的字节空间，因此增加了交易费用。

![](https://cdn-images-1.medium.com/max/1600/1*byA4UmLgEij_1oGp2EaLjg.png)
*Currently, each input requires a signature, increasing total transaction size | 目前，所有输入都需要签名，增加了交易所占据的字节空间*

*Schnorr signatures are an alternative and more efficient way of storing signature data in transactions. All inputs are accumulated and then stored as a single signature by utilizing the Schnorr algorithm, which greatly saves space in a transaction and further helps increase transaction throughput by allowing blocks to store more transactions on average.*

*Schnorr 签名是在交易中存储签名数据的另一种更有效的方式。所有的输入累积在一起，然后通过 Schnorr 算法被存储为一个单一的签名，这大大节省了交易占用的空间，通过使块平均能存储更多的交易，进一步提高交易吞吐量。*

![](https://cdn-images-1.medium.com/max/1600/1*22yyLNKn02a-D7YsDgRw5A.png)
*All sender signatures are stored as one signature under the Schnorr algorithm | 使用 Schnorr 算法使得所有发送者签名都作为一个签名存储*


Schnorr signatures can be also be used to aid Bitcoin’s advancement in privacy by benefiting CoinJoin transactions. CoinJoin is a method of introducing anonymity to Bitcoin transactions. It works by pooling transaction inputs together with other peoples’ transactions when making a payment to a receiver. When payments are pooled, it becomes difficult to track which user sent what input, effectively making them anonymous. However, CoinJoin transactions have increased fees due to a higher number of inputs in a single transaction resulting in a higher number of signatures. Utilizing Schnorr signatures would enable all signatures in a transaction to be compressed into one, saving greatly on transaction fees and encouraging the use of CoinJoin.

Furthermore, Schnorr paves the way for complex multisig transactions which require signing off from multiple parties; no matter how many parties’ signatures are required for a transaction, all the transaction needs is one Schnorr signature.

Schnorr signatures are only now a possibility because of the implementation of SegWit; because signature data can’t be modified by third parties, it can now be used to effectively create a Schnorr signature.

Schnorr 签名也可以帮助比特币提高隐私，使 CoinJoin 交易受益。CoinJoin 是比特币匿名交易的方法。它通过在向接收者付款时将交易输入与其他人的交易汇集在一起，从​​而起作用。当付款汇集后，很难跟踪哪个用户发送了什么输入，从而达到匿名目的。然而，CoinJoin 交易增加了费用，因为在单个交易中输入的数量越多，签名数量就越多。使用 Schnorr 签名可以使交易中的所有签名压缩为一个，大大节省交易费用，从而使 CoinJoin 更受欢迎。

此外，Schnorr 为需要多方签名的复杂多重签名交易铺平了道路; 无论交易需要多少方签名，所有的交易只需是一个 Schnorr 签名。

由于隔离验证的实施，Schnorr 签名才成为可能; 由于签名数据不能被第三方修改，现在可以用它来有效地创建一个 Schnorr 签名。

### MimbleWimble

MimbleWimble is a radical but incredibly powerful proposed change to Bitcoin architecture that was anonymously introduced through this [whitepaper](https://download.wpsoftware.net/bitcoin/wizardry/mimblewimble.txt) in July 2016.

Named after the [tongue-tying curse from the Harry Potter series](http://harrypotter.wikia.com/wiki/Tongue-Tying_Curse), its aim is to remove transactions entirely from blocks. Under MimbleWimble, transactions consist of nothing but input amounts, output amounts, and a signature. The signature of the transaction can only be decrypted by the receiver, and so transaction verification is left to the receiver.

By extension, blocks consist of only the list of all transaction input amounts of all transactions, all transaction output amounts, and their corresponding signatures. Blocks can then be merged seamlessly with previous blocks as they’re nothing but pairs of input and output amounts. Nodes then have the ability to cryptographically ensure that transactions in blocks do not create extra bitcoins (i.e. their net difference between inputs and outputs in blocks is 0) without having to decrypt transactions.

MimbleWimble （译者注：出自《哈利波特》，是一种诅咒，可让他人口齿不清或发不出声音。）是对比特币架构的一个激进但却非常强大的改​​变，在2016年7月通过此[白皮书](https://download.wpsoftware.net/bitcoin/wizardry/mimblewimble.txt)([中文版]((中文版点此)))匿名推出。

MimbleWimble 以[《哈利·波特》系列中令人舌头打结的诅咒](http://harrypotter.wikia.com/wiki/Tongue-Tying_Curse)命名，其目的是从块中完全取消交易。在 MimbleWimble 下，交易只包含输入金额，输出金额和签名。交易的签名只能由接收方解密，所以交易验证是由接收方进行的。

通过扩展，块只包含所有交易的输入金额，所有交易的输出金额及其相应的签名的列表。块因此可以与之前的块无缝合并，因为它们只是一对对的输入和输出的数量。然后，在不必解密交易的情况下，节点能够以加密方式确保块内的交易不会创建出额外的比特币（即，它们在块中的输入和输出的差值为0）。

This removal of transaction storage grants complete anonymity to all users by stripping away the ability to generate transaction history. Furthermore, with blocks only containing the **unspent transaction outputs** (meaning the number of Bitcoins that have been received in an address but not moved out yet), the blockchain size can be reduced by over 60% according to the whitepaper. This reduction in size means that in order to validate a MimbleWimble blockchain, nodes will only need to look at the set of unspent transaction outputs instead of the entire set of transactions, which will exponentially increase performance.

通过移除生成交易历史的能力，交易存储的移除授予所有用户完全的匿名性。此外，根据白皮书，只使用包含**未使用的交易输出**（即在比特币地址中收到但未付出的比特币的数量）的区块，区块链大小可以减少 60％ 以上。这种大小的缩减意味着验证一个 MimbleWimble 的区块链，节点只需要查看未使用的交易输出集合，而不是整个交易集合，这将成倍地提高性能。

The mathematical details of MimbleWimble are outside of the scope of this article, but are explained in detail in the whitepaper. Although MimbleWimble presents some clear advantages and technical breakthroughs, its implementation requires the removal of Bitcoin’s Script system that much of the existing architecture relies on. As a result, MimbleWimble’s implementation on the Bitcoin blockchain is not technically feasible.

However, there are proposals for MimbleWimble to exist as a sidechain. A sidechain is a separate blockchain directly attached to the Bitcoin blockchain through the use of a two-way peg. This peg enables assets between the two chains to be exchanged and “pegs” the value of the sidechain asset to the value of Bitcoin. In this setup, users would be able to exchange Bitcoins for MimbleWimble coins, conduct completely private and rapid transactions on the MimbleWimble chain, and then exchange their MimbleWimble coins for Bitcoin whenever they please.

MimbleWimble 的数学细节超出了本文的范围，但在白皮书中有详细的说明。尽管 MimbleWimble 提供了一些明显的优势和技术突破，但其实施需要删除现有体系结构所依赖的比特币脚本系统。因此，MimbleWimble 在比特币区块链上的实施在技术上是不可行的。

不过，有人建议 MimbleWimble 作为一个侧链存在。侧链是一个独立的区块链，通过使用双向挂钩直接连接到比特币区块链。这种挂钩使两链之间的资产能够交换，并将侧链资产的价值“钉住”到比特币的价值。在这种设置中，用户将能够以 MimbleWimble 硬币兑换比特币，在 MimbleWimble 链上进行完全私密和快速的交易，然后随时可以将他们的 MimbleWimble 硬币兑换成比特币。

![](https://cdn-images-1.medium.com/max/2000/0*shjdJcexgSIUXttC.png)
*Sidechain coins are pegged to the Bitcoin blockchain, operating alongside it with a fixed exchange rate, source: [Blockchain.com](http://blockchain.com/) | 侧链硬币固定在比特币区块链上，以固定汇率同时运行，来源：[Blockchain.com](http://blockchain.com/)*

In fact, a group of developers are already in the process of developing MimbleWimble as a separate cryptocurrency called [GRIN](https://github.com/mimblewimble/grin); it was recently deployed on a test network and may be launched in the near future.

事实上，一群开发者已经把 MimbleWimble 作为一个独立的加密货币 [GRIN](https://github.com/mimblewimble/grin) 进行开发; 它最近部署在测试网络上，并可能在不久的将来发布。


### Rootstock

>Rootstock — Smart Contracts on the Bitcoin Blockchain

>As a concept the Rootstock [1] platform is one of those ideas that once it is proposed it is obvious that it is a great…
medium.com
https://medium.com/@CryptoIQ.ca/rootstock-smart-contracts-on-the-bitcoin-blockchain-e52b065421a8

>Rootstock - 比特币区块链上的智能合约

>有些方案一旦提出，显而易见就是一个伟大的...,作为一个概念，Rootstock 平台就是这样的方案。
https://medium.com/@CryptoIQ.ca/rootstock-smart-contracts-on-the-bitcoin-blockchain-e52b065421a8

Rootstock is for whatever reason one of the less talked about advancements in Bitcoin technology but is by far one of the coolest. Rootstock is described as “the first open-source smart contract platform with a 2-way peg to Bitcoin that also rewards the Bitcoin miners via merge-mining, allowing them to actively participate in the Smart Contract revolution.”

Much like MimbleWimble, Rootstock is being developed as a sidechain solution to the Bitcoin blockchain. Its fundamental value lies in its focus in smart contracts. Rootstock aims to be a [Turing Complete](https://simple.wikipedia.org/wiki/Turing_complete) (completely programmable) smart-contracts platform that will be backwards compatible with Ethereum’s virtual machine. This means that Rootstock will be able to execute any smart contracts developed for the Ethereum platform and have smart contracts developed for its own platform.

无论是什么原因，对于比特币技术的发展，Rootstock 是很少有人谈论的，但却是迄今为止最酷的。Rootstock 被形容为“第一个开放源代码的智能合约平台，双向与比特币挂钩，并通过混合挖矿来奖励比特币矿工，使他们能够积极参与智能合约革命。”

就像 MimbleWimble 一样，Rootstock 正在开发成比特币区块链的侧链解决方案。它的基本价值在于其着重于智能合约。Rootstock 的目标是成为一个[图灵完备](https://simple.wikipedia.org/wiki/Turing_complete)（完全可编程）的智能合约平台，这个平台将向后兼容以太坊的虚拟机。这意味着 Rootstock 将能够执行为以太坊平台开发的任何智能合约，同时为自己的平台开发智能合约。

Rootstock aims to implement this versatile smart-contract functionality all while leveraging Bitcoin’s comparatively dominant userbase and value by acting as a two-way pegged sidechain. It is also being designed to be secured by the existing Bitcoin mining network, therefore not needing to incentivize miners to secure its own blockchain. Rootstock also aims to tackle the transaction scalability problem by implementing its own version of a multi-layered solution called [Lumino](https://uploads.strikinglycdn.com/files/9dcb08c5-f5a9-430e-b7ba-6c35550a4e67/LuminoTransactionCompressionProtocolLTCP.pdf). With this, it may be able to accomplish up to 20,000 transactions per second.

*Rootstock is aiming for [a launch by the end of 2017](https://www.coindesk.com/bitcoin-startup-rsk-launch-smart-contracts-sidechain-2017/). Overall, the platform aims to fit in perfectly alongside Bitcoin and if its claims hold true, it will undoubtedly bring unprecedented utility to the Bitcoin network.*

Rootstock 的目标是通过双向挂钩的侧链，利用比特币相对优势的用户基础和价值，同时实现这种多功能的智能合约功能。它也被设计成利用现有的比特币挖矿网络来保证安全，因此不需要激励矿工来保护自己的区块链。Rootstock 还旨在通过实施其自己版本的称为 [Lumino](https://uploads.strikinglycdn.com/files/9dcb08c5-f5a9-430e-b7ba-6c35550a4e67/LuminoTransactionCompressionProtocolLTCP.pdf) 的多层解决方案来解决交易可伸缩性问题。有了这个，它能够完成每秒高达20,000笔的交易。

*Rootstock 准备在[ 2017 年底推出](https://www.coindesk.com/bitcoin-startup-rsk-launch-smart-contracts-sidechain-2017/)。总的来说，这个平台的目标是与比特币完美契合，如果它的声明成立，它无疑将为比特币网络带来前所未有的功用。*

If you’ve gotten this far, congratulations! I hope you were able to learn something about the future of Bitcoin and are as excited about it as I am.

Bitcoin isn’t perfect and is faced with challenges that its community must work to solve. However, it is backed by an incredibly dedicated and thriving developer community that is working day in and day out to tackle these problems. There are constant innovations happening everyday, and I am sure by the time you finished reading this another new and exciting proposal for the Bitcoin blockchain popped up.

This article by no means covers everything out there; if there’s anything that you’re aware of that I didn’t mention, please mention them in the comments!

如果你已经看到这里，祝贺你！我希望你能够学习一些关于比特币未来的技术，并且像我一样为此感到激动。

比特币并不完美，面临着社区必须要解决的挑战。然而，它却得到了一个令人难以置信的热情的开发者社区的支持，他们每天都在努力解决这些问题。每天都有新的创新，并且我相信，当你读完这篇文章的时候，又会突然冒出有关比特币区块链的令人兴奋的新提议。

这篇文章并没有涵盖所有的新的技术。如果有什么你知道的，而我没有在这里提到，请在评论中告诉我！

Follow me on Twitter and Medium if you’re interested in more in-depth and informative write-ups like these in the future!
I’m a relative Bitcoin beginner myself so if there are any mistakes or if you have any feedback please don’t hesitate let me know!

BTC Address: 3MGguJhw1bm95tDQjZ3b8ySBwZLJ77CgG1

如果你期待更深入和有益的报导，请关注我的推特和 Medium。
我是一个比特币初学者，所以如果有任何错误，或者如果您有任何反馈，请不要犹豫，让我知道！

BTC地址：3MGguJhw1bm95tDQjZ3b8ySBwZLJ77CgG1

Here are some resources if you’re interested in learning more:
这里有一些资源，如果你有兴趣学习：

* [Mastering Bitcoin | 掌握比特币](https://github.com/bitcoinbook/bitcoinbook),  [Andreas M. Antonopoulos](https://medium.com/@aantonop) 撰写的综合性书籍

* [The Bitcoin Wiki | 比特币维基](http://bitcoin.it/)

* [The Bitcoin whitepaper | 比特币白皮书](https://lopp.net/pdf/bitcoin.pdf)

* [A collection of Bitcoin resources | 收集的比特币资源](https://lopp.net/bitcoin.html) by [Jameson Lopp](https://medium.com/@lopp)

* [This highly informative interview with Nick Szabos | 对尼克高度翔实的采访](https://www.google.ca/url?sa=t&rct=j&q=&esrc=s&source=web&cd=2&cad=rja&uact=8&ved=0ahUKEwiznZ-Oo-zXAhUW02MKHZ0aAhcQtwIILzAB&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3D3FA3UjA0igY&usg=AOvVaw0JIy-AaKaXyDsGm8psm7Qj) conducted by [Tim Ferriss](https://medium.com/@timferriss)

* [Ivan on Tech on Youtube](https://www.youtube.com/channel/UCrYmtJBtLdtm2ov84ulV-yg), who is absolutely amazing at breaking down technical Bitcoin concepts

Thanks to Emma Soolepp. 感谢 Emma Soolepp。

关键字：Bitcoin Technology Blockchain Finance Business 比特币 技术 区块链 金融 商业
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
