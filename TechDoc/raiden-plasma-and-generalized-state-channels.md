Raiden, Plasma and Generalized State Channels --
------------------------------------------------------

> 本文翻译自：https://medium.com/@cryptovision/raiden-plasma-and-generalized-state-channels-a84af44bed98
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS)  [Xuming Meng](https://github.com/jonas-meng)
>
> 翻译时间：2017-11-12

---------------------------

# Raiden, Plasma and Generalized State Channels #
# Raiden, Plasma 和广义状态通道 #

With this article I would like to give a quick overview of the Raiden Network, Plasma and Generalized State Channels. All of these technologies have the same goal: **Help scaling Ethereum**. They are not the exact same thing though and they have their strengths and weaknesses by design. In the following I want to give a simple outline of each technology and its use case.

通过这篇文章，我想简要介绍一下Raiden Network(雷电网络)，Plasma和广义状态通道。 所有这些技术都有相同的目标：帮助扩展以太坊。他们不是完全一样的东西，并且他们在设计上各有自己的优缺点。下面我想简单介绍一下每种技术及其使用案例。

# Raiden Network #
Raiden is a network of nodes. Nodes establish payment channels to other nodes. A payment is routed through the network via multiple nodes, but each node only communicates with its direct neighbours. Each node has to hold the balance for the amount being moved. That’s why it will be hard to find a path through the network to move 1000 Ether because every node will have to hold that balance.

# Use Case: #
Transferring small amounts of Ether and ERC20 tokens almost instantly and reliably.

# 雷电网络 #
雷电网络是一个多节点网络。节点之间建立支付渠道。一通支付经过多个节点穿过网络，但每个节点只与其直接邻近节点进行通信。每个节点必须持有将要被转移的数目的余额。这就是为什么很难找到一个通过网络转移1000以太币的路径，因为每个节点将不得不持有这么多的余额。

# 用例：
几乎瞬间和可靠地传输少量的Ether和ERC20代币。

# Plasma #
Plasma aims to scale transactions by creating side chains that only interact with the main chain every once in a while. Plasma chains can even be nested (yeah, like Inception). Plasma is being actively developed by OmiseGo. In terms of fees and latency Plasma is probably inferior to Raiden, but it has a wider use case. Plasma chains need to be secured by “fraud proofs”.

# Use Case: #
Imagine OmiseGo running their own Plasma chain for all their users and business partners. They could do thousands of transactions back and forth every day within their plasma chain and only make a final settlement every other day to the Ethereum main net. From the OmiseGo Plasma chain, McDonald's Thailand could start its own Plasma chain, the 2nd layer chain, only for its users.

# Plasma #
Plasma旨在通过创造只与主链相互作用的侧链来扩大交易规模。Plasma链甚至可以嵌套（是的，就像Inception）。Plasma是由OmiseGo积极开发的。在费用和延迟方面，Plasma可能不如闪电网络，但它有更广泛的用途。Plasma链需要通过“欺诈证明”来保证安全。

# 用例： #
想象一下，OmiseGo为所有用户和业务合作伙伴运行自己的Plasma链。他们每天可以在Plasma链里来回进行数以千计的交易，并且每隔一天才会到以太坊主网进行最终结算。从OmiseGo Plasma链中，泰国的麦当劳可以启动自己的Plasma链，第二层链，仅供其用户使用。

# Generalized State Channels #
Shortly after Raiden concluded their ICO Liam Horne and Jeff Coleman came forward with announcing the development of generalized state channels funded by Vitalik himself.
The idea is that a Generalized State Channel can execute multiple actions between two parties with only the initial and final settlement happening on-chain. Generalized State channels work best where the interacting parties are somewhat constant.

#Use Case: #
Imagine a group of crypto exchanges that want to create a shared reserve of ERC20 tokens. They go on and create the pool with all the rules of lending, interest and so on in a smart contract on the main chain. Now all the actual lending and moving of funds can happen off-chain in a generalized state channels. Every month the state channel settles the most recent balances back to the main chain.

# 广义状态通道 #
在雷电网络结束他们的ICO不久，Liam Horne和Jeff Coleman就宣布由Vitalik自己资助的广义状态通道。这个想法是，一个广义的状态通道可以在双方之间执行多个动作，只有最初和最后的结算发生在链上。广义状态通道在交互方恒定的情况下效果最好。
 
# 用例： #
设想一组想要创建ERC20代币共享储备的加密货币交易所。他们在主链上的智能合约中创建贷款和利息等所有的规则池。现在所有的实际借贷和资金转移都可以在一个链外的广义状态通道发生。状态通道每个月都会把最近的余额结算回主链。

# Bonus: Lightning Network #
The Lightning Network is a scaling solution for Bitcoin and Litecoin. It makes use of State Channels, but there are various implementations of it.

# Bonus: Sharding #
Currently every node has to validate every transaction.
Sharding is an on-chain scaling solution. The idea is to split the network into multiple shards that only validate parts of the transactions. For transactions outside its own shard a node acts like a light client.

# 额外奖励：闪电网络 #
闪电网络是比特币和莱特币的缩放解决方案。它使用状态通道，但是它有各种各样的实现。

# 额外奖励：分片 #
目前每个节点都必须验证每个事务。
分片是一种链上缩放解决方案。这个想法是将网络分割成多个分片，只验证部分事务。对于自身分片之外的事务，节点就像一个轻客户端。

# Summary #
All of the introduced concepts try to scale Ethereum. None of them are direct competitors to each other as their concepts differ and therefore cover different use cases. Ask questions in the comments if anything is unclear or you want more details on a particular topic.

# 总结 #
所有引入的概念试图扩展以太坊。由于它们的概念不同，它们都不是直接竞争对手，从而涵盖了不同的使用案例。如果有什么不清楚的地方，可以在评论中提问，或者想要了解更多关于特定主题的细节。

----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

抖抖，在读博士，专注区块链技术研究与行业分析，jonas.meng.jm@gmail.com

本文由币乎社区（bihu.com）内容支持计划赞助。

版权所有，转载需完整注明以上内容。

----------------------------------------------------
