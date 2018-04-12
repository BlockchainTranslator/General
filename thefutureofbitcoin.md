### 闪电网络是比特币的未来

>本文翻译自：https://medium.com/@kingonly/the-future-of-bitcoin-3187aefe2746
>
>作者：Roy Sheinfeld
>
>译者：区块链中文字幕组 Chuan
>
>翻译时间：2018-04-01

In recent years, Bitcoin and its underlying infrastructure, the Blockchain, have been proven to be safe and reliable technologies. However, despite its continued popularity and high-demand from businesses, Bitcoin still cannot be used as a functional currency to date. Some of the few merchants that had accepted Bitcoin as a payment option, like Valve, removed their support for Bitcoin. Another example is Stripe, a leading payment processing firm for online businesses, ended its Bitcoin support due to lengthy transaction times and growing fees. The fact that out of the leading 500 internet sellers, just three accept Bitcoin indicates that Bitcoin is becoming less popular among merchants and users for use in everyday commerce. Instead, Bitcoin is perceived to be a modern day equivalent to gold as consumers holding it prefer to profit from its price increase rather than spend it on products and goods that could be purchased via fiat currencies. Peter Thiel recently stated that Bitcoin is “like bars of gold in a vault that never move”, adding that it is too cumbersome to be used as a payment system.

最近几年，比特币及其底层结构 — 区块链 — 已经被证实是安全、可靠的技术。可是，尽管比特币不断被大众熟知以及来自商业层面的需求不断增大，到目前为止它仍旧不能被运用在实际生活中。为数不多的商户中有一些之前接受使用比特币进行支付，比如Valve，现在取消了对比特币的支持。Stripe，一家领先的处理线上交易支付的公司，由于较长的交易时间和不断增加的手续费，结束了对使用比特币支付的支持。前500家线上销售商中，只有三家接受比特币，这一事实表明：日常交易中，比特币的使用在商户和顾客中的热度正减弱。相反的情况，现在比特币被设想成等同于黄金，因为持有它的消费者更喜欢从它的涨幅中获利，而不是把它用于购买本可以用法币就能买到的商品上。最近，Peter Thiel 指出，比特币就像“保险柜里从来没动过的金块”，并说它过于笨重并不能用作支付系统。

I don’t agree. I believe that the success of Bitcoin will be greatly impacted by its tradability and its ability to impact our everyday commerce. However, in order for that to happen, we need to face Bitcoin’s shortcomings which prevent it from being accepted by consumers and merchants as a functional currency:

我不认同他的说法。我认为，影响比特币的成功很大原因在于它的可交易量和它对我们日常交易的影响能力。然而，要让比特币被广泛接受，我们需要面对比特币以下的不足，而这些不足会阻碍它被消费者和商户接受其为一种可实际使用的货币。

1.Payment is not instantaneous. The Blockchain contains blocks, where each block documents several transactions. As soon as a block has been filled with transactions, it needs to be added to the chain before starting to record transactions on the next block. However, before a block can be added to the chain, there is some processing that needs to be done to ensure that everyone agrees with the contents it contains. This process is called mining. With the Blockchain architecture, a payment is accepted once a transaction has been mined into a block. However, on average, it takes between 9 to 10 minutes to mine a block.

1.支付不是即时的。区块链包含区块，每个块记录若干交易。当一个块容纳下它能接受的交易量，开始在下一个块上记录交易信息之前，它就需要被添加到链上。可是，在区块被添加到链上之前，需要完成一些处理过程来确保每个节点认同区块包含的内容。这个过程称之为“挖矿“。由于区块链的结构设计，一旦一笔交易被挖出添加到区块里，这一支付就被确认了。然而，平均来说，要花上9到10分钟才能挖出一个块。

2.Lack of scalability. In order to maintain its decentralized nature, the Blockchain limits a block size to 1MB. Because of the block size and the minimum delay between blocks mining, the Blockchain is only able to process 2 to 12 transactions per second. For Bitcoin to play a meaningful role as a payment system, transaction processing power needs to increase by at least 3 orders of magnitude.

2.缺乏可扩展性。为了维持它的去中心化的特质，区块链将块的大小限制为1MB。由于区块大小和出块的间隔，区块链每秒只能处理2~12笔交易。为了比特币在支付环节发挥出重要的作用，交易处理能力需要增加至少3个数量级。

3.High cost of transactions fee. Transactions speed limit is causing network congestion, with thousands of transactions waiting to be confirmed and delays reaching several hours. The nature of the Blockchain architecture (in which miners can be incentivize to include a transaction in a block sooner than others) inherently drives an increase in transaction fees, as users are willing to pay higher fees to get their transaction at the front of the queue. Unfortunately, any temporary decrease in transaction fee can be attributed to lower transaction volume, which defeats the purpose…

3.交易手续费太高。交易速度的受限引起网络堵塞，数千笔交易等着被确认，并且延迟时间会达好几个小时。区块链结构的特性本质上就推升了交易手续费的增加，因为用户愿意支付更高的手续费来让他们的交易排在队列的前面。不幸的是，交易手续费临时减少的原因可能都被归结为更低的交易量，这使得这一目的难以实现...

Lightning Network (LN) lays the foundation in which Bitcoin can be evolved to become a functional currency. Lightning Network offers an off-chain transaction model which addresses the current Blockchain deficiencies. This model enables:
闪电网络（LN）的基础在于比特币能够被改进为一种具有实用价值的货币。闪电网络提供一种链外交易模型来解决当前区块链的不足。这一模型能够实现以下特点：

1.Instant Payments. Lightning-fast Blockchain payments without worrying about block confirmation times. Security is enforced by Blockchain smart-contracts without creating a on-Blockchain transaction for individual payments. Payment speed measured in milliseconds to seconds.

1.即时支付。闪电般地快速支付，不用担心区块的确认时间。安全问题由区块链的智能合约保障，无需为单独的支付创建一个链上交易。支付速度以毫秒为单位，最慢也只需要几秒。

2.Scalability. Capable of millions to billions of transactions per second across the network. Capacity is better than legacy payment rails by many orders of magnitude. Payments are now possible without custodians.

2.可扩展性。网络上可以容纳每秒上百万到数十亿笔交易。通道能力比传统的支付要高出许多个数量级。无需托管就可以完成支付。

3.Low Cost. By transacting and settling off-Blockchain, Lightning Network allows for exceptionally low fees, which enables instant micropayments.

3.低手续费。通过链外交易，闪电网络实现极低的手续费，使得即时小额支付成为可能。

The innovation behind LN is that not all transactions are required to be recorded on the Blockchain. In cases where two parties transact a few times among themselves, they can bypass the recording of transactions on the Blockchain and carry them off the Blockchain (off-chain). LN’s fundamental technology is a local two ­party consensus, also known as a payment channel. When two parties are ready to transact, a payment channel is opened and recorded on the Blockchain (an on-chain action). From now on, the parties can transact any number of times through this payment channel and it can stay open for any duration. The only time the parties interact with the Blockchain again will be when they would want to close the channel. Then, the parties record the final status of the transactions that occurred through the channel on the Blockchain. This notion of payment channel enables the creation of a network of payment channels such that it would be only rarely required to transaction on the Blockchain. Meaning, all payment channels can be connected to enable tractions between parties that do not have a direct payment channel between them. In this architecture, because on-chain interactions are reduced to a minimum, transactions are happening at lightning speed.

闪电网络背后的创新是：并不是所有的交易都需要在主链上进行记录。有些场合，双方相互之间交易几次，他们可以避开在主链上对交易进行记录，而在链外完成。闪电网络的基础技术是一个局部的双方共识，也被称之为支付通道。当两方准备交易时，在主链上打开一个支付通道并记录下来（链上的一次操作）。这时，两方可以通过这个支付通道完成任意次数的交易，而且这个通道可以保持不断开。双方跟主链再次发生交互的时候就是他们想关闭这个通道。然后，双方记录下通过这个通道的所有交易的最终状态。支付通道这个概念使得创建一个支付通道网络成为可能，这样就几乎不再要求在主链上进行交易。意思是，所有的支付通道能够被连接，使得两方之间的交易不必在相互之间有直连的支付通道。由于这种结构设计，链上交互被减少到最低程度，所以交易就能够迅速完成。

Lightning Network is a potential breakthrough in transforming Bitcoin to be used as a functional, tradeable currency. LN can help Bitcoin to deliver on its promise, but, in order to do so, most of everyday transactions will need to be processed via LN payment channels, while the Blockchain will only exist as a secure fallback to ensure honest commerce. IMHO, Bitcoin’s success depends on Lighting Network’s ability to flourish as vibrant network, relying on the security infrastructure provided by the Blockchain, but reducing Blockchain transactions to a minimum.

闪电网络的潜在的技术革新能将比特币转变为具有实用价值、可交易的货币。闪电网络能够帮助比特币达成它的希望，但是，为了做到这一点，大多数的日常交易都需要经过闪电网络的支付通道处理，而区块链将只作为安全的备选方案来保证诚信交易。我认为，比特币的成功取决于闪电网络的顺利发展，区块链提供的安全底层技术的支持，以及区块链上的交易量降到最低。

---
**区块链中文字幕组**

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号：w1791520555。

[点击查看 GITHUB 及更多的译文](https://github.com/BlockchainTranslator/EOS)

**本文译者介绍**

Chuan

区块链技术爱好者。欢迎加我的微信：youyuxiaochuan

本文源自新闻媒体 Medium，如有侵权，请与译者联系删除。
