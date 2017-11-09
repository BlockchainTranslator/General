Hyperledger Fabric Transaction Flow  -- 超级账本 Fabric 项目的交易流程图
------------------------------------------------------

> 本文翻译自：http://hyperledger-fabric.readthedocs.io/en/latest/txflow.html
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS)  [荆凯(shuke0327)](https://github.com/shuke0327)
>
> 翻译时间：2017-11-08

---------------------------


# Transaction Flow 交易流程

This document outlines the transactional mechanics that take place during a standard asset exchange. The scenario includes two clients, A and B, who are buying and selling radishes. They each have a peer on the network through which they send their transactions and interact with the ledger.

本篇文档概述了标准的资产交易过程中发生的交易机制。

![](http://hyperledger-fabric.readthedocs.io/en/latest/_images/step0.png)

**Assumptions　假设**

This flow assumes that a channel is set up and running. The application user has registered and enrolled with the organization’s certificate authority (CA) and received back necessary cryptographic material, which is used to authenticate to the network.

在这一流程中，假设已经创建和运行了通道。程序的用户使用机构证书注册，并获取了加密材料，用于在网络之中认证。

The chaincode (containing a set of key value pairs representing the initial state of the radish market) is installed on the peers and instantiated on the channel. The chaincode contains logic defining a set of transaction instructions and the agreed upon price for a radish. An endorsement policy has also been set for this chaincode, stating that both `peerA` and `peerB` must endorse any transaction.

链码（包含一组键值对，表示萝卜市场的初始状态)，安装到peers节点，并且在通道上实例化。链码包含了定义一组交易指令的逻辑，并就萝卜的价格达成一致。也设定了链码的背书策略，两个节点`peer A`和`peer B` 都必须为所有的交易背书。

![](http://hyperledger-fabric.readthedocs.io/en/latest/_images/step1.png)

## 1.  Client A initiates a transaction 客户端A发起交易

What’s happening? - Client A is sending a request to purchase radishes. The request targets
 `peerA` and `peerB` , who are respectively representative of Client A and Client B. The endorsement policy states that both peers must endorse any transaction, therefore the request goes to `peerA` and  `peerB` .

发生了什么？  客户端 A发起购买萝卜的请求。请求目标是`peer A`和`peer B`，分别代表客户A和客户B。

Next, the transaction proposal is constructed. An application leveraging a supported SDK (Node, Java, Python) utilizes one of the available API’s which generates a transaction proposal. The proposal is a request to invoke a chaincode function so that data can be read and/or written to the ledger (i.e. write new key value pairs for the assets). The SDK serves as a shim to package the transaction proposal into the properly architected format (protocol buffer over gRPC) and takes the user’s cryptographic credentials to produce a unique signature for this transaction proposal.

下一步，构建了交易提案。程序使用支持的SDK 利用api生成交易提案。提案请求会调用链码函数，对账本进行读写（如，为资产写入新的键值对）。SDK作为一个shim，将交易提案打包为正确的架构格式(协议缓冲区在gRPC上)，并获取用户的密码凭证，从而为该交易提案生成唯一的签名。

![](http://hyperledger-fabric.readthedocs.io/en/latest/_images/step2.png)

## 2.  Endorsing peers verify signature & execute the transaction 验证peers节点验证签名并执行交易

The endorsing peers verify (1) that the transaction proposal is well formed, (2) it has not been submitted already in the past (replay-attack protection), (3) the signature is valid (using MSP), and (4) that the submitter (Client A, in the example) is properly authorized to perform the proposed operation on that channel (namely, each endorsing peer ensures that the submitter satisfies the channel’s *Writers* policy).

The endorsing peers take the transaction proposal inputs as arguments to the invoked chaincode’s function. The chaincode is then executed against the current state database to produce transaction results including a response value, read set, and write set. No updates are made to the ledger at this point. The set of these values, along with the endorsing peer’s signature is passed back as a “proposal response” to the SDK which parses the payload for the application to consume.

*{The MSP is a peer component that allows them to verify transaction requests arriving from clients and to sign transaction results(endorsements). The Writing policy is defined at channel creation time, and determines which user is entitled to submit a transaction to that channel.}*

背书节点验证(1) 交易提案是完整的,(2)过去尚未提交(重放攻击保护),(3)签名是有效的(使用MSP),和(4)提交者（在这个例子中是客户A)得到了正确授权，可以在该通道执行操作(即,每个背书节点都都会确保提交者能够满足通道的 *写入者* 的策略).

背书节点将输入的交易提案作为调用链码函数的参数。然后，chaincode针对当前的状态数据库执行操作，产生交易结果，包括一个响应值、读取集和写入集。在此时还不会更新账本。这些值的集合以及背书人的签名，作为一个“提案响应”传回给SDK，以解析有效载荷，供程序使用.

*{MSP是一个对等节点组件，允许它们验证从客户端到达的交易请求，签署交易结果(背书)。写入策略在通道创建时定义，并确定哪个用户有权向该通道提交交易}*

![](http://hyperledger-fabric.readthedocs.io/en/latest/_images/step3.png)

## 3.  Proposal responses are inspected 对提案响应进行检查

The application verifies the endorsing peer signatures and compares the proposal responses to determine if the proposal responses are the same. If the chaincode only queried the ledger, the application would inspect the query response and would typically not submit the transaction to Ordering Service. If the client application intends to submit the transaction to Ordering Service to update the ledger, the application determines if the specified endorsement policy has been fulfilled before submitting (i.e. did peerA and peerB both endorse). The architecture is such that even if an application chooses not to inspect responses or otherwise forwards an unendorsed transaction, the endorsement policy will still be enforced by peers and upheld at the commit validation phase.

应用程序验证背书节点的签名并对提案响应进行比较，以确定提案响应是否相同。
如果链码只查询账本，应用程序会检查查询的相应，通常不会将事务提交给排序服务 （Ordering Serivce）.如果客户端应用程序打算将事务提交给排序服务节点来更新账本，应用程序将在提交之前，会确定是否符合了指定的背书策略(即，是否peerA和peerB都做了背书)。
这样的架构，即使应用程序选择不检查响应，或选择转发未经背书的交易，对等节点仍然会强制执行背书策略，并在提交验证阶段维持原状。

![](http://hyperledger-fabric.readthedocs.io/en/latest/_images/step4.png)

## 4. Client assembles endorsements into a transaction 节点将背书组合进交易之中

The application “broadcasts” the transaction proposal and response within a “transaction message” to the Ordering Service. The transaction will contain the read/write sets, the endorsing peers signatures and the Channel ID. The Ordering Service does not need to inspect the entire content of a transaction in order to perform its operation, it simply receives transactions from all channels in the network, orders them chronologically by channel, and creates blocks of transactions per channel.

应用程序在“交易信息”中，将交易提案和响应向排序服务“广播”。交易将包含读/写集,支持peers节点签名和通道的ID。排序服务不需要检查一笔交易中的全部内容来执行其操作, 它只是从网络中的所有通道中接收交易, 分通道按时间顺序, 为每个通道创建交易区块。

![](http://hyperledger-fabric.readthedocs.io/en/latest/_images/step5.png)

## 5.  Transaction is validated and committed 验证交易和提交交易

The blocks of transactions are “delivered” to all peers on the channel. The transactions within the block are validated to ensure endorsement policy is fulfilled and to ensure that there have been no changes to ledger state for read set variables since the read set was generated by the transaction execution. Transactions in the block are tagged as being valid or invalid.

交易区块被“传递”到通道上的所有对等节点。对区块中的交易进行验证，以确保背书策略得到满足，并确保在交易执行生成了读取集之后，读取集变量的账本状态没有发生变更。区块中的交易被标记为有效或无效。
![](http://hyperledger-fabric.readthedocs.io/en/latest/_images/step6.png)

## 6. Ledger updated 账本更新

Each peer appends the block to the channel’s chain, and for each valid transaction the write sets are committed to current state database. An event is emitted, to notify the client application that the transaction (invocation) has been immutably appended to the chain, as well as notification of whether the transaction was validated or invalidated.

每个对等节点将区块附加到通道的区块链上，对于每笔有效交易，写入集将提交到当前的状态数据库。事件发出后，通知客户端应用程序此交易(调用)已不可篡改地附加到区块链上，并通知该笔交易是是否有效。

**Note**: See the swimlane diagram to better understand the server side flow and the protobuffers.

**注意**: 查看泳道图，以更好地理解服务器端的流程和协议缓冲区。

----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

荆凯，程序员，相信区块链终将改变潮水的方向．欢迎加微信号:shuke0327，也可以关注公众号: 增长之道

本文由币乎社区（bihu.com）内容支持计划赞助。

版权所有，转载需完整注明以上内容。

----------------------------------------------------
