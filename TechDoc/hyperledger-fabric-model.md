 Hyperledger Fabric Model | 超级账本 Fabric 项目模型
------------------------------------------------------

> 本文翻译自：https://hyperledger-fabric.readthedocs.io/en/latest/fabric_model.html
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [shuke0327](https://github.com/shuke0327)
>
> 翻译时间：2017-11-05

This section outlines the key design features woven into Hyperledger Fabric that fulfill its promise of a comprehensive, yet customizable, enterprise blockchain solution:

这一部分概括了超级账本 Fabric项目的关键设计特征，这些特征使其能够兑现承诺，成为既有广泛性又可定制的企业级区块链解决方案:

[Assets](http://hyperledger-fabric.readthedocs.io/en/release/fabric_model.html#assets) - Asset definitions enable the exchange of almost anything with monetary value over the network, from whole foods to antique cars to currency futures.

[资产](http://hyperledger-fabric.readthedocs.io/en/release/fabric_model.html#assets) - 资产定义使得从天然食品到古董车、到货币期货的几乎任何东西都可以货币化，通过网络进行交易。

[Chaincode](http://hyperledger-fabric.readthedocs.io/en/release/glossary.html#chaincode) - Chaincode execution is partitioned from transaction ordering, limiting the required levels of trust and verification across node types, and optimizing network scalability and performance.

[链码](http://hyperledger-fabric.readthedocs.io/en/release/glossary.html#chaincode) -
链码执行，从交易排序中分离，限制了请求的信赖级别，跨节点类型的验证，优化网络的扩展性和性能。

[Ledger Features](http://hyperledger-fabric.readthedocs.io/en/release/fabric_model.html#ledger-features) - The immutable, shared ledger encodes the entire transaction history for each channel, and includes SQL-like query capability for efficient auditing and dispute resolution.
[Ledger Features](http://hyperledger-fabric.readthedocs.io/en/release/fabric_model.html#ledger-features) - 不可改变的共享账本对每个通道的全部交易历史进行编码，包含了类SQL的查询能力，用于有效审计和解决纠纷。

[Privacy through Channels](http://hyperledger-fabric.readthedocs.io/en/release/fabric_model.html#privacy-through-channels) - Channels enable multi-lateral transactions with the high degrees of privacy and confidentiality required by competing businesses and regulated industries that exchange assets on a common network.

[通过通道实现私有性](http://hyperledger-fabric.readthedocs.io/en/release/fabric_model.html#privacy-through-channels) - 通道使得多方交易具有高度的私有性和机密性，这是在通用网络上进行资产交易的相互竞争的商业和受监管的行业所需要的。

[Security & Membership Services](http://hyperledger-fabric.readthedocs.io/en/release/fabric_model.html#security-membership-services) - Permissioned membership provides a trusted blockchain network, where participants know that all transactions can be detected and traced by authorized regulators and auditors.

[安全性 & 会员服务](http://hyperledger-fabric.readthedocs.io/en/release/fabric_model.html#security-membership-services) -  带权限的会员制提供了可信的区块链网络，参与者知道，被授权的管理者和审计人员可以侦测和追踪所有的交易。

[Consensus](http://hyperledger-fabric.readthedocs.io/en/release/fabric_model.html#consensus) - a unique approach to consensus enables the flexibility and scalability needed for the enterprise.

[共识](http://hyperledger-fabric.readthedocs.io/en/release/fabric_model.html#consensus) -达成共识的独特方式，提供了企业所需的灵活性和可扩展性。

### Assets 资产

Assets can range from the tangible (real estate and hardware) to the intangible (contracts and intellectual property). Hyperledger Fabric provides the ability to modify assets using chaincode transactions.
Assets are represented in Hyperledger Fabric as a collection of key-value pairs, with state changes recorded as transactions on a [Channel](http://hyperledger-fabric.readthedocs.io/en/release/glossary.html#channel) ledger. Assets can be represented in binary and/or JSON form.

资产可以囊括从有形资产(房地产和硬件)到无形资产(合同和知识产权)。超级账本 Fabric 提供了使用链码交易来修改资产的能力。在超级账本 Fabric 中，资产表现为一组键值对的集合，状态的更改被记录为 [通道](http://hyperledger-fabric.readthedocs.io/en/release/glossary.html#channel)账本上的交易。资产可以以二级制和/或JSON的格式表示。

You can easily define and use assets in your Hyperledger Fabric applications using the [Hyperledger Composer](https://github.com/hyperledger/composer) tool.

在你的超级账本Fabric应用中，很容易用[Hyperledger Composer](https://github.com/hyperledger/composer) 工具来定义和使用资产。

### Chaincode 链码

Chaincode is software defining an asset or assets, and the transaction instructions for modifying the asset(s). In other words, it’s the business logic. Chaincode enforces the rules for reading or altering key value pairs or other state database information. Chaincode functions execute against the ledger’s current state database and are initiated through a transaction proposal. Chaincode execution results in a set of key value writes (write set) that can be submitted to the network and applied to the ledger on all peers.

链码是定义资产以及运行交易指令修改资产的软件。换言之，链码是业务逻辑。链码执行规则，读取或修改键值对，或者其它状态数据库的信息。链码方法针对账本的当前状态数据库执行操作，是通过一项交易提案发起的。链码执行会产生一组键值对的写入操作，可以被提交到网络中并应用到所有 peers 节点的账本之上。


### Ledger Features 账本特征

The ledger is the sequenced, tamper-resistant record of all state transitions in the fabric. State transitions are a result of chaincode invocations (‘transactions’) submitted by participating parties. Each transaction results in a set of asset key-value pairs that are committed to the ledger as creates, updates, or deletes.
The ledger is comprised of a blockchain (‘chain’) to store the immutable, sequenced record in blocks, as well as a state database to maintain current fabric state. There is one ledger per channel. Each peer maintains a copy of the ledger for each channel of which they are a member.

账本是fabric中所有状态转换的不可篡改的有序记录。状态转换是由参与者提交的链码调用(交易)的结果。每一笔交易会产生一组提交到账本中的资产键值对，进行创建，更新或者删除操作。账本包含一条在区块中存储不可篡改的有序记录的区块链(链)，也包括一个状态数据库，维护当前的 fabric 状态。每个通道都有账本，每个 peer 节点会对他们所属的每条通道都维护一份账本副本。

*   Query and update ledger using key-based lookups, range queries, and composite key queries
*   Read-only queries using a rich query language (if using CouchDB as state database)
*   Read-only history queries - Query ledger history for a key, enabling data provenance scenarios
*   Transactions consist of the versions of keys/values that were read in chaincode (read set) and keys/values that were written in chaincode (write set)
*   Transactions contain signatures of every endorsing peer and are submitted to ordering service
*   Transactions are ordered into blocks and are “delivered” from an ordering service to peers on a channel
*   Peers validate transactions against endorsement policies and enforce the policies
*   Prior to appending a block, a versioning check is performed to ensure that states for assets that were read have not changed since chaincode execution time
*   There is immutability once a transaction is validated and committed
*   A channel’s ledger contains a configuration block defining policies, access control lists, and other pertinent information
*   Channel’s contain
     [Membership Service Provider](https://hyperledger-fabric.readthedocs.io/en/latest/glossary.html#msp)
    instances allowing for crypto materials to be derived from different certificate authorities

*  使用基于键的查找，范围查询，和复合键查询来进行账本的查询和更新
*  使用一门富查询语言进行只读查询(如果使用CouchDB作为状态数据库的话)
*  只读历史查询 - 从账本历史中查找键，用于数据验证的场景
*  交易包含从链码上读取(读操作)和写入(写操作)的带版本的键值对
*  交易包含每一个背书节点的签名，并提交给排序服务节点
*  将交易排序到区块中，从排序服务节点传递到通道上的peer节点
*  Peers 节点根据背书策略验证交易，执行策略
*  在附加区块之前，需要执行版本检查，确保自链码执行的时刻起，所读取的资产的状态未曾变更
*  交易一经验证和提交，就不可篡改
*  通道的账本包含了可配置的区块，其中定义了策略，访问控制清单，以及其他的相关信息
*  通道包含[会员服务提供者（Membership Service Provider）](http://hyperledger-fabric.readthedocs.io/en/release/glossary.html#msp) 实例，允许从不同的证书颁发机构所产生的加密材料

See the [Ledger](http://hyperledger-fabric.readthedocs.io/en/release/ledger.html) topic for a deeper dive on the databases, storage structure, and “query-ability.”
想要深入了解数据库，存储结构和“查询能力”，请查看[账本主题](http://hyperledger-fabric.readthedocs.io/en/release/ledger.html)。

### Privacy through Channels 通过通道实现私有性

Hyperledger Fabric employs an immutable ledger on a per-channel basis, as well as chaincodes that can manipulate and modify the current state of assets (i.e. update key value pairs). A ledger exists in the scope of a channel - it can be shared across the entire network (assuming every participant is operating on one common channel) - or it can be privatized to only include a specific set of participants.

超级账本Fabric 在每个通道的基础上，使用不可篡改账本，以及可以操作和修改资产当前状态(比如，更新键值对)的链码。账本在通道的范围之内 - 可以在整个网络中共享（假设所有参与者都在同一条通用通道中运作） - 或者为某些特定的参与者所私有。

In the latter scenario, these participants would create a separate channel and thereby isolate/segregate their transactions and ledger. In order to solve scenarios that want to bridge the gap between total transparency and privacy, chaincode can be installed only on peers that need to access the asset states to perform reads and writes (in other words, if a chaincode is not installed on a peer, it will not be able to properly interface with the ledger). To further obfuscate the data, values within chaincode can be encrypted (in part or in total) using common cryptographic algorithms such as AES before appending to the ledger.

在后一情景中，参与者会创建单独的通道，从而隔离/分隔他们的交易和账本。为了解决需要跨越整体透明性与私有性的桥梁的场景，可以只将链码安装在需要那些需要访问资产状态、运行读写操作的节点上(换句话说，如果一个peer节点没有安装链码，该节点就不能与账本交互). 为了进一步混淆数据，可以使用常见的加密算法，比如AES，在添加到账本之前加密（部分加密或者整体加密）链码中的值。

### Security & Membership Services 安全性 & 会员服务

Hyperledger Fabric underpins a transactional network where all participants have known identities. Public Key Infrastructure is used to generate cryptographic certificates which are tied to organizations, network components, and end users or client applications. As a result, data access control can be manipulated and governed on the broader network and on channel levels. This “permissioned” notion of Hyperledger Fabric, coupled with the existence and capabilities of channels, helps address scenarios where privacy and confidentiality are paramount concerns.

超级账本 Fabric 支持由已知身份的成员所组成的交易网络。使用公钥架构（Public Key Infrastructure）产生加密证书，与机构、网络组件和终端用户或客户端程序相绑定。结果是，在广域网中可以在通道级别对数据访问的控制进行操作和监管。超级账本 Fabric 这一“许可”的概念，再加上通道的存在和能力，帮助解决将隐私和机密视为首要问题的场景。

See the [Membership Service Providers (MSP)](http://hyperledger-fabric.readthedocs.io/en/release/msp.html) topic to better understand cryptographic implementations, and the sign, verify, authenticate approach used in Hyperledger Fabric.

查看[Membership Service Providers (MSP)](http://hyperledger-fabric.readthedocs.io/en/release/msp.html) ，可以更好的理解密码学实现机制，以及在超级账本Fabric 中所用到的签名，验证和认证方法。

### Consensus  共识机制

In distributed ledger technology, consensus has recently become synonymous with a specific algorithm, within a single function. However, consensus encompasses more than simply agreeing upon the order of transactions, and this differentiation is highlighted in Hyperledger Fabric through its fundamental role in the entire transaction flow, from proposal and endorsement, to ordering, validation and commitment. In a nutshell, consensus is defined as the full-circle verification of the correctness of a set of transactions comprising a block.

在分布式账本技术中，共识最近成为单一函数中特定算法的同义词。然而，共识并不只是单单就交易顺序达成一致，在超级账本Fabric项目中高度强调了这一分别，在整个交易流程中，从提议到背书，到排序，验证和提交，共识都起到了重要作用。简而言之，共识被定义为对组成区块的一组交易的正确性进行验证的整个过程。

Consensus is ultimately achieved when the order and results of a block’s transactions have met the explicit policy criteria checks. These checks and balances take place during the lifecycle of a transaction, and include the usage of endorsement policies to dictate which specific members must endorse a certain transaction class, as well as system chaincodes to ensure that these policies are enforced and upheld. Prior to commitment, the peers will employ these system chaincodes to make sure that enough endorsements are present, and that they were derived from the appropriate entities. Moreover, a versioning check will take place during which the current state of the ledger is agreed or consented upon, before any blocks containing transactions are appended to the ledger. This final check provides protection against double spend operations and other threats that might compromise data integrity, and allows for functions to be executed against non-static variables.

当一个块中交易的顺序和结果符合公开策略的检查标准时，才最终达成共识。这些检查和平衡发生在交易的生命周期之中，包括使用背书策略决定哪些特定成员必须为一笔特定的交易背书，也包括确保这些策略得到执行的系统链码。在提交之前，peers 节点会使用系统链码确保已经提供了足够的背书，并且这些背书由正当的实体产生。另外，还会进行版本检查，在将包含交易的任何区块附加到账本上之前，就当前的账本状态达成一致共识。这一最终检查提供了保护，避免双重支付操作以及其它可能会损坏数据完整性的威胁，并允许对非静态变量执行方法。

In addition to the multitude of endorsement, validity and versioning checks that take place, there are also ongoing identity verifications happening in all directions of the transaction flow. Access control lists are implemented on hierarchal layers of the network (ordering service down to channels), and payloads are repeatedly signed, verified and authenticated as a transaction proposal passes through the different architectural components. To conclude, consensus is not merely limited to the agreed upon order of a batch of transactions, but rather, it is an overarching characterization that is achieved as a byproduct of the ongoing verifications that take place during a transaction’s journey from proposal to commitment.
Check out the [Transaction Flow](http://hyperledger-fabric.readthedocs.io/en/release/txflow.html) diagram for a visual representation of consensus.

除了多方背书、验证和版本检查之外，在交易流程的各个方向都有持续的身份验证。访问控制列表是在网络的层次结构上实现的（从排序服务下到通道中），而且，当交易提案通过不同的架构组件时，还会反复签署、验证和验证有效负载（payloads）。最后，共识不只局限于一组交易的一致顺序约定，而是一种总体的描述，它是在交易从提案(proposal)到提交(commitment)的过程中所发生的持续验证的副产品。
