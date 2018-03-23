> 本文翻译自：https://coincenter.org/entry/what-is-the-lightning-network
>
> 作者：[Elizabeth Stark](https://twitter.com/starkness),
> Coin Center研究员，闪电公司联合创始人，耶鲁大学法学院前讲师。
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator) [鱼](https://github.com/oscnet)
>
> 翻译时间：2018-3-25
>

# What is the Lightning Network and how can it help Bitcoin scale?

# 什么是闪电网络，为什么它能够解决比特币的可扩展性问题？

A plain-language explanation of the Lightning Network, a protocol for scaling and speeding up blockchains. While it was designed to solve some of the technical limitations of the Bitcoin blockchain, it can be implemented on top of any blockchain.

简单的来说，闪电网络，这是一个能解决可扩展性问题和加速区块链的协议。虽然它是为了解决比特币区块链的一些技术限制而设计的，但它也可以实施在其它区块链上。

Imagine if every computer had to store every e-mail, to receive any. That's how blockchains work. Lightning Network allows computers to make blockchain transactions, only storing the data they care about—their own money.

想象一下，如果每台电脑必须首先存储所有的电子邮件后，才可以收到邮件 :<......然而这就是区块链的工作方式。闪电网络允许计算机进行区块链交易，却只需要存储他们所关心的数据 --- 他们自己的资金。

Lightning Network is a protocol for scaling and speeding up blockchains. It was designed to solve some of the technical limitations of the Bitcoin blockchain, but could be implemented on top of any blockchain.

闪电网络是解决可扩展性问题和加速区块链的协议。它是为了解决比特币区块链的一些技术限制而设计的，但它也可以实施在其它任何区块链上。

Scalability was the first major motivator for Lightning, as Bitcoin's distributed nature greatly limits the transaction rate of the network. While Visa can process tens of thousands of transactions per second, Bitcoin's network is limited to less than 10 per second. Another motivator for Lightning's development is that the Bitcoin blockchain's "block confirmation time" is approximately 10 minutes long. That means it takes [10 minutes for a ][1][bitcoin transaction to confirm][1]. Further, transaction fees on the Bitcoin blockchain can run between 5 and 10 cents per transaction, rendering micropayments infeasible. Lightning Network, by contrast, can enable near-instant transactions, at a rate of thousands to millions per second, with fees of a fraction of a cent (or even free).

解决可扩展性问题是闪电的首要动力，因为比特币的分布式特性极大地限制了网络的交易速率。然而 Visa 每秒可以处理数万次交易，比特币网络每秒却只能处理不到 10 次交易。 闪电发展的另一个动力是比特币区块链的“区块确认时间”大约为 10 分钟。这意味着[一笔比特币交易的确认时间需要 10 分钟][1]。另外，比特币区块链每次交易的交易费用可能在 5 美分至 10 美分之间，使得无法进行小额支付。相比之下，闪电网络可以实现近乎即时的交易，速度可达每秒数千到数百万笔，费用却只有几分钱（甚至是免费）。

Lightning Network is based on a technology called [payment channels][2]. A two-party payment channel is created when both parties create a 2-out-of-2 [multi signature][3] transaction on the blockchain, with at least one party committing funds to the 2-of-2 ledger entry. Each person has one private key, and transactions spending from the ledger entry can now be made only if both keys sign. This initial transaction to open a channel takes 10 minutes (or whatever the normal block time is), but afterward the participants can transact with each other instantly using the funds allocated in the the channel. These instantaneous transactions are made by passing signed transactions back and forth, spending from the 2-of-2 ledger entry.

闪电网络基于一种被称为[支付通道][2]的技术。当双方在区块链上创建 2/2 （ N/M 的意思是一共有 M 个私钥，需要最少用 N 个私钥签名才能转帐。译者注）的[多重签名][3]交易时双方同时创建了支付通道，并且至少需要一方向 2/2 账目中注入资金。每个人都有一个私钥，并且现在只有在两个私钥都签名的情况下帐目中的资金才能支出。开通通道的初始交易需要 10 分钟（或正常的出块时间），但是之后参与者可以使用通道中分配的资金立即与对方进行交易。这些即时交易通过来回传递已签署的交易来完成，并从 这个 2/2 账目中支出。

Each transaction would be valid if broadcast to the network and included in the blockchain by the network's miners, but in a payment channel, those signed transactions are not broadcast until the participants want the channel to stop operating. Signed but unbroadcast transactions are exchanged using direct, peer-to-peer communication, and held like redeemable receipts by the participants.

如果交易被广播到网络并由矿工包含在区块链中，则交易是有效的，但在支付通道中，只有在参与者希望通道停止运作时，才会广播那些已签署的交易。已签署但未广播的交易使用直接的、点对点的通信进行交换，参与者可以把它视为可兑换的收据。

To use Lightning, two participants, Alice and Bob, create an initial transaction on the blockchain for $20, where each party has $10 of the value.

为了使用闪电网络，两位参与者 Alice 和 Bob 使用 20 美元资金在区块链上创建初始交易，双方都各持有 10 美元。

![][4]

This initial allocation can then be updated, such that Alice then has $5 of the total $20 value, and Bob has $15, and so on. When the participants have finished transacting with each other, the most recently exchanged transaction signature is broadcast to the network, finalizing the movement of the funds in the channel—some to one party and (if any remain) some back to the other.

这个初始的分配接下来就可以变动，如果 Alice 得到总价值 20 美元中的 5 美元， Bob 就有 15 美元，依此类推。当参与者完成彼此交易时，最近交换的交易签名被广播到网络，最终停止通道中的资金流动 - 资金转到一方并且（如果还有的话）剩下的资金会转到另一方。

Lightning takes the technology behind payment channels and creates a network of these channels, using "smart contracts" to ensure that the network can function in a decentralized capacity without counterparty risk. As an example, Alice may open a channel with Bob, who in turn has a channel with Carol, who has one open with Dave. If Alice wants to transact with Dave, she can send funds via Bob and Carol, and Dave will ultimately receive them. But, because of multi signature and smart contracts inherent in the design of Lightning, Alice doesn't need to trust Bob and Carol as an intermediaries—the protocol uses cryptography to ensure that the funds will either reach Dave through Bob and Carol or else be automatically refunded to Alice.

闪电使用基于支付通道的技术，并创建这些通道的网络，使用“智能合约”来确保网络以去中心化的方式运作，而没有交易对手风险。举例来说，Alice 可能会和 Bob 打开一个通道，而 Bob 则与 Carol 有一个通道，并与 Dave 打开一个通道。如果 Alice 想和 Dave 交易，她可以通过 Bob 和 Carol 发送资金，而 Dave 最终会收到。但是，由于闪电设计中存在的多重签名和智能合约，Alice 不需要相信作为中间人的 Bob 和 Carol  - 该协议使用密码学来确保资金要么通过 Bob 和 Carol 到达 Dave 要么自动退还给 Alice。

![][5]

Bob and Carol function as "nodes" on the network. Nodes on the Lightning Network are in some ways analogous to [miners on the Bitcoin network][6]. They function as the servers that process the transactions on the network in a decentralized manner. Like miners, they do not have control over the funds they help move. Bob cannot steal Alice's funds, as he will only receive the sender's incoming payment if he has already sent the outgoing payment to the recipient. Thus, receiving a payment is dependent on having already forwarded it. Lightning payments are conditional upon disclosure of a cryptographic secret, and knowledge of that secret allows for redemption from prior nodes (when Dave redeems from Carol, Carol can now redeem from Bob).

Bob 和 Carol 在网络上充当“节点”。闪电网络上的节点在某种程度上类似于[比特币网络上的矿工][6]。它们作为以去中心化方式处理网络事务的服务器。像矿工一样，他们无法控制他们所帮助移动的交易资金。Bob 不能窃取 Alice 的资金，因为只有他付款给收件人，才会收到发件人的付款。因此，能不能接收到付款取决于是否已经将资金转发。闪电支付的条件是破解加密的秘密，只有知道这个秘密才可以从以前的节点赎回。（当 Dave 从 Carol 处赎回时，Carol 才可以从 Bob 处赎回）。

What happens, though, if Bob goes offline? Do the funds stay forever in a 2-of-2 payment channel? To deal with unreliable nodes, Lightning has built-in smart contract mechanisms such that users can unilaterally close their channels. It uses a "hashed timelock contract" to ensure that if Bob disappears, Alice can always get her money back. There is a time value set on this contract, typically in hours or days, so that Alice can get repaid even if Bob's server is down.

但是，如果 Bob 离线了，会发生什么？这些资金是否永远保留在 2/2 支付通道中？为了处理不可靠的节点，闪电内置了智能合约机制，用户可以单方面关闭通道。它使用“散列时间锁定合约”来确保如果 Bob 消失了，Alice 总是可以拿回她的钱。此合约上设定了一个时间值，通常以小时或天为单位，这样即使 Bob 的服务器关闭，Alice 也可以得到她的钱。

Similarly, what happens if Alice sends funds from her multi signature address to Dave on the Lightning Network but then tries to renege? She could do this by broadcasting an older transaction to the blockchain, thereby attempting to close out the channel in the state it was before she sent a transaction to Dave. While Lightning software will delete these old transaction states, Alice could have changed the software to save it. If Alice tries to claim she still has her old balance, Dave's software (or other designated servers) will monitor the blockchain for such a transaction, and when it catches Alice's broadcasted transaction, she will lose all of her funds to Dave as a penalty. As a result, there is a disincentive for anyone to try to broadcast an old, invalid state.

同样，如果 Alice 将她的多重签名地址的资金通过闪电网络发送给 Dave，后来却试图反悔，会发生什么呢？她可以通过向区块链广播较旧的交易来达到目的，从而试图在向 Dave 发送交易之前的状态中关闭该通道。虽然闪电软件会删除这些旧的事务状态，但 Alice 可以更改软件以保存这些旧的事务状态。如果 Alice 试图声称自己仍旧拥有旧的余额，Dave 的软件（或其他指定的服务器）将监测区块链中这类的交易，当它捕捉到 Alice 广播的交易时，作为处罚，她将失去所有给 Dave 的资金。因此，任何人试图广播一个旧的无效状态，是极为不利的。

What if Alice and Bob are both online and willing to close their channel? If both parties cooperatively close a payment channel, the funds can be cleared to the blockchain in 10 minutes, the amount of time that it takes for a bitcoin transaction to confirm. Alice and Bob may have transacted thousands of times on Lightning Network in the interim.

如果 Alice 和 Bob 都在线并愿意关闭他们的通道呢？如果双方合作关闭支付渠道，则可以在 10 分钟内将资金清算到区块链中，这是比特币交易确认所需的时间。在此期间，Alice 和 Bob 可能在闪电网络上进行了数千次交易。

Lightning Network ultimately relies on the underlying blockchain, be it Bitcoin's or otherwise, for its security. In the case of Bitcoin, it uses the underlying proof-of-work algorithm that secures the entire network to secure it as well. The blockchain is the ultimate arbiter, or in effect an automated judge. With Lightning, you always know how the judge will decide, because it is pre-written into the transactions used to create the payment channels that make up the Lightning Network. This is a judge that cannot be cajoled or bribed. In effect, Lightning allows for a "local consensus" state which is ultimately enforced by the "global consensus" (the blockchain). This local consensus state does not have custodial trust similar to traditional models, as any participant can unilaterally close out and redeem their funds without the cooperation other participants. Ultimately, Lightning uses the underlying blockchain as a means to batch settle transactions that have occurred off-chain without counterparty trust.

闪电网络最终依靠底层区块链，无论是比特币还是其他。对安全，就比特币而言，它底层使用工作量证明算法来确保整个网络的安全。区块链是最终的裁决者，实际上是一个自动的“裁判”。借助闪电，您总能知道法官如何进行决定，因为它已预先写入构成闪电网络的付款通道的交易中。这是一个不能被诱导或贿赂的法官。实际上，闪电允许“地方共识”，并最终由“全球共识”（区块链）强制执行。这种地方共识状态不具有类似于传统模式的托管信任，
因为任何参与者都可以在没有其他参与者合作的情况下单方面关闭和赎回他们的资金。最终，闪电使用底层区块链作为一种手段来批量结算在没有对手信任的情况下发生的链外交易。

Lightning Network can work on the Bitcoin blockchain, on other blockchains, or it can be used to instantly transfer different assets between blockchains using "cross-chain atomic swaps." The consensus rules for each blockchain can be different, allowing for secure crossing of asset classes without custodial clearing agencies.

闪电网络可以在比特币区块链上工作，也可以在其他区块链上工作，也可以使用“跨链原子交换”在区块链之间即时传输不同资产。每个区块链的共识规则可能不同，允许在没有托管清算机构的情况下安全地更换资产类别。

With Lightning, small transactions or payments can flow through the network similar to how packets flow through the Internet. It has the potential to create new use cases that were not previously possible, such as machine-to-machine payments, content micropayments, and instant asset swaps.

借助闪电，小型交易或支付可以在网络中流动，非常类似于互联网中数据包的流动。它有可能创造以前不可能的新的用法，例如机器对机器的支付，内容微支付和即时资产互换。

_Elizabeth Stark is a Coin Center Fellow, Co-founder of Lightning, and former lecturer at Yale Law School._

_原作者 [Elizabeth Stark](https://twitter.com/starkness) 是 Coin Center 研究员，闪电公司联合创始人，耶鲁大学法学院前讲师。_

[1]: http://coincenter.org/entry/how-long-does-it-take-for-a-bitcoin-transaction-to-be-confirmed
[2]: https://coincenter.org/entry/what-are-micropayments-and-how-does-bitcoin-enable-them
[3]: http://coincenter.org/entry/what-is-multi-sig-and-what-can-it-do
[4]: http://coincenter.org/thumbs/1000x1000r/2016-09/lightning1.png
[5]: http://coincenter.org/thumbs/1000x1000r/2016-09/lightning2.png
[6]: http://coincenter.org/entry/what-is-bitcoin-mining-and-why-is-it-necessary

----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

鱼 区块链技术爱好者，欢迎加微信号交流：**oscnet**

版权声明：

版权所有，[Lightning Labs](https://lightning.engineering) 授权译者在 [区块链中文字幕组 (github.com/BlockchainTranslator)](https://github.com/BlockchainTranslator/)  和 [币乎（bihu.com）](http://www.bihu.com)
上发表。不得转载。

----------------------------------------------------
