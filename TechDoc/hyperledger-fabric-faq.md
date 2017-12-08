Hyperledger Fabric FAQ　| 　超级账本 Fabric 项目问答
--------------------------

> 本文翻译自：http://hyperledger-fabric.readthedocs.io/en/release/Fabric-FAQ.html
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [荆凯](https://github.com/shuke0327)
>
> 翻译时间：2017-12-03

---------------------------


## Endorsement 背书

**Endorsement architecture　背书架构**

Ｑ.  How many peers in the network need to endorse a transaction?
一笔交易需要多少个背书节点的背书?

A. The number of peers required to endorse a transaction is driven by the endorsement policy that is specified at chaincode deployment time.

交易所需要的背书节点数量，受背书政策的驱动，在链码部署时候指定。

Ｑ.  Does an application client need to connect to all peers?
一个应用节点需要连接到所有的对等节点么?

A. Clients only need to connect to as many peers as are required by the endorsement policy for the chaincode.
只需要连接到链码的背书政策所要求的节点数量就好了。

## Security & Access Control　安全性 & 访问控制

**Data Privacy and Access Control 数据私密性和访问控制**

Ｑ.  How do I ensure data privacy?　如何保证数据私密性？

A. There are various aspects to data privacy. First, you can segregate your network into channels, where each channel represents a subset of participants that are authorized to see the data for the chaincodes that are deployed to that channel.

数据私密性有多方面。首先，可以将网络分为多个通道，每条通道表示参与者的一个子集，被授权可以访问部署到该通道的链码的数据。

 Second, within a channel you can restrict the input data to chaincode to the set of endorsers only, by using visibility settings. The visibility setting will determine whether input and output chaincode data is included in the submitted transaction, versus just output data. 

第二，在通道内部，可以使用可见性的设置，限制输入到链码的数据，只对背书节点可见。可见性设置会决定输入和输出数据是否包含在提交的交易中，或者仅仅输出数据包含在内。

Third, you can hash or encrypt the data before calling chaincode. If you hash the data then you will need to provide a means to share the source data. If you encrypt the data then you will need to provide a means to share the decryption keys. 

第三，在调用链码之前，可以对数据哈希计算或者加密。如果哈希话，需要提供可以分享源数据的方式。如果加密了数据，就需要提方法来分享解密的密钥。

Fourth, you can restrict data access to certain roles in your organization, by building access control into the chaincode logic. 

第四，可以限定组织中特定角色对数据的可见性，通过把访问控制构建到链码的逻辑之中来实现这一点。

Fifth, ledger data at rest can be encrypted via file system encryption on the peer, and data in-transit is encrypted via TLS.

第五，其余的账本数据可以通过文件系统加密来加密，而传输中的数据则通过TLS加密。

Q.  Do the orderers see the transaction data?　排序节点可以看到交易数据么？

A. No, the orderers only order transactions, they do not open the transactions. If you do not want the data to go through the orderers at all, and you are only concerned about the input data, then you can use visibility settings. The visibility setting will determine whether input and output chaincode data is included in the submitted transaction, versus just output data. Therefore, the input data can be private to the endorsers only. If you do not want the orderers to see chaincode output, then you can hash or encrypt the data before calling chaincode. If you hash the data then you will need to provide a meansto share the source data. If you encrypt the data then you will need to provide a means to share the decryption keys.

不会，排序节点只是对交易进行排序，并不会打开交易。如果您不希望数据通过排序节点，而您只关心输入数据，那么您可以使用可见性设置。可见性设置将确定提交的交易中是否包含输入和输出的链码数据，或者可以只包括输出数据。因此，输入数据只是对背书节点可见的私有数据。如果不希望排序节点看到链码的输出，你可以在调用链码之前对数据进行哈希化或加密。如果您对数据进行哈希，则需要提供共享源数据的方式。如果对数据进行加密，则需要提供一种方法，共享解密的密钥。

## Application-side Programming Model　应用程序端的编程模型

**Transaction execution result | 交易执行结果**:

Q.  How do application clients know the outcome of a transaction?

A. The transaction simulation results are returned to the client by the endorser in the proposal response. If there are multiple endorsers, the client can check that the responses are all the same, and submit the results and endorsements for ordering and commitment. Ultimately the committing peers will validate or invalidate the transaction, and the client becomes aware of the outcome via an event, that the SDK makes available to the application client.

交易的模拟结果在提案响应中由背书节点返回给客户端。如果有多个背书节点，客户端可以检查响应是否相同，并提交结果和背书，以进行排序和提交(commitment)。最终，提交节点将验证交易是否有效，并且客户端通过事件得知结果，事件是SDK为应用客户端提供的。

**Ledger queries　账本查询**:

Q.  How do I query the ledger data? 　怎样可以查询账本数据？

A. Within chaincode you can query based on keys. Keys can be queried by range, and composite keys can be modeled to enable equivalence queries against multiple parameters. For example a composite key of (owner,asset_id) can be used to query all assets owned by a certain entity. These key-based queries can be used for read-only queries against the ledger, as well as in transactions that update the ledger.

If you model asset data as JSON in chaincode and use CouchDB as the state database, you can also perform complex rich queries against the chaincode data values, using the CouchDB JSON query language within chaincode. The application client can perform read-only queries, but these responses are not typically submitted as part of transactions to the ordering service.

在chaincode中，可以基于键查询。可以按范围查询密钥，也可以对复合键进行建模，以支持针对多个参数的等价查询。例如，复合键(owner，asset_id)可以用来查询某个实体拥有的所有资产。这些基于键的查询可以用于针对账本的只读查询，也可以用于更新账本的交易。

如果在chaincode中将资产数据建模为JSON并使用CouchDB作为状态数据库，您还可以使用chaincode中的CouchDB JSON查询语言对chaincode数据值执行复杂的富查询。应用程序客户端可以执行只读查询，但是这些响应通常不作为交易的一部分提交给排序服务。

Q.  How do I query the historical data to understand data provenance?
怎么查询历史记录以了解数据来源?

A. The chaincode API `GetHistoryForKey()` will return history of values for a key.
chaincode API的`GetHistoryForKey()`将返回键的历史值。

Q. How to guarantee the query result is correct, especially when the peer being queried may be recovering and catching up on block processing?

Q: 如何保证查询结果是正确的，特别是当被查询的节点可能正在恢复并追赶区块处理时?

A. The client can query multiple peers, compare their block heights, compare their query results, and favor the peers at the higher block heights.

A: 客户端可以查询多个对等节点，比较它们的区块高度，比较它们的查询结果，并选择较高块高度的节点。

## Chaincode (Smart Contracts and Digital Assets)　链码(智能合约和数字资产)

Q.  Does Hyperledger Fabric support smart contract logic?  超级账本支持智能合约逻辑么？

A. Yes. We call this feature [Chaincode](https://hyperledger-fabric.readthedocs.io/en/release/glossary.html#chaincode) . It is our interpretation of the smart contract method/algorithm, with additional features.

chaincode is programmatic code deployed on the network, where it is executed and validated by chain validators together during the consensus process. Developers can use chaincodes to develop business contracts, asset definitions, and collectively-managed decentralized applications.

是的。我们称这个特性为[链码](https://hyperledger-fabric.readthedocs.io/en/release/glossary.html # Chaincode)。这是我们对智能合约方法/算法的解释，并具有额外的特点。

链码是在网络上部署的编程代码，在共识过程中，它将被区块链验证人执行和验证。开发人员可以使用链码来开发商业合约、资产定义和集体管理的去中心化应用程序。

Q.  How do I create a business contract? 如何创建业务合约?

A. There are generally two ways to develop business contracts: the first way is to code individual contracts into standalone instances of chaincode; the second way, and probably the more efficient way, is to use chaincode to create decentralized applications that manage the life cycle of one or multiple types of business contracts, and let end users instantiate instances of contracts within these applications.

Ａ:通常有两种方法来开发业务合约:第一种方法是将单个合约编码到链码的独立实例中;第二种方法(可能是更有效的方法)是使用链码创建去中心化应用，管理一种或多种类型业务合约的生命周期，并让最终用户在这些应用程序中对业务合约的实例进行实例化。

Ｑ.  How do I create assets? 如何创建资产?

A. Users can use chaincode (for business rules) and membership service (for digital tokens) to design assets, as well as the logic that manages them.

There are two popular approaches to defining assets in most blockchain solutions: the stateless UTXO model, where account balances are encoded into past transaction records; and the account model, where account balances are kept in state storage space on the ledger.

Each approach carries its own benefits and drawbacks. This blockchain technology does not advocate either one over the other. Instead, one of our first requirements was to ensure that both approaches can be easily implemented.


A. 用户可以使用链码(用于业务规则)和成员服务(用于数字令牌)来设计资产，以及管理资产的逻辑。

在大多数区块链解决方案中，有两种流行的定义资产的方法:　无状态的UTXO模型，其中的帐户余额被编码成过去的交易记录;帐户模型，帐户余额保存在账本上的状态存储空间之中。

两种方法各有优缺点。这种区块链技术既不支持另一种技术，也不提倡另一种技术。相反，我们的第一个要求是确保两种方法都可以很容易地实现。

Q.  Which languages are supported for writing chaincode? 编写链码支持哪些编程语言 ?

A. Chaincode can be written in any programming language and executed in containers. The first fully supported chaincode language is Golang.Support for additional languages and the development of a templating language have been discussed, and more details will be released in the near future.It is also possible to build Hyperledger Fabric applications using [Hyperledger Composer](https://hyperledger.github.io/composer/).

A . 链码可以用任何编程语言编写，并在容器中执行。第一个完全支持的链码语言是Golang。我们已经讨论了对其他语言的支持和模板语言的开发，并将在不久的将来发布更多的细节。开发超级账本程序，还可以用(Hyperledger Composer)(https://hyperledger.github.io/composer/)。

Q.  Does the Hyperledger Fabric have native currency? 超级账本有原生代币吗?

A. No. However, if you really need a native currency for your chain network, you can develop your own native currency with chaincode. One common attribute of native currency is that some amount will get transacted (the chaincode defining that currency will get called) every time a transaction is processed on its chain.

Ａ:不。然而，如果你真的需要一个原生代币，你可以用链码开发你自己的原生代币。原生代币的一个常见属性是，每次在其链上处理交易时，某些数量的金额将被交易(定义该货币的chaincode将被调用)。

## Differences in Most Recent Releases　最近发行版的差异[](https://hyperledger-fabric.readthedocs.io/en/release/Fabric-FAQ.html#differences-in-most-recent-releases "Permalink to this headline")

Q.  As part of the v1.0.0 release, what are the highlight differences between v0.6 and v1.0?
作为v1.0.0版本的一部分，v0.6和v1.0之间的突出区别是什么?

A. The differences between any subsequent releases are provided together with the [Release Notes](http://hyperledger-fabric.readthedocs.io/en/latest/releases.html). Since Fabric is a pluggable modular framework, you can refer to the [design-docs](https://wiki.hyperleger.org/projects/fabric/design-docs) for further information of these difference.

任何后续版本之间的差异都与(发布说明)一起提供(http://hyperledger-fabric.readthedocs.io/en/latest/releases.html)。由于超级账本Fabric 项目是一个可插拔的模块化的框架,您可以参考(设计文档)(https://wiki.hyperleger.org/projects/fabric/design-docs)来了解这些差异的进一步的信息。

Q.  Where to get help for the technical questions not answered above?
对于上述没有提到的技术问题，去哪里寻求帮助？

A.  Please use  [StackOverflow](https://stackoverflow.com/questions/tagged/hyperledger).
请使用 [StackOverflow](https://stackoverflow.com/questions/tagged/hyperledger).

--------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

荆凯 区块链技术爱好者，相信区块链会带来新的改变，欢迎加微信号:shuke0327

本文由币乎社区（bihu.com）内容支持计划奖励。

版权所有，转载需完整注明以上内容。

----------------------------------------------------
