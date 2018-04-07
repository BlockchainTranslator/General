> 文章来自：A Case Study for Blockchain in Healthcare: “MedRec” prototype for electronic health records and medical research data
>
> 作者：Ariel Ekblaw, Asaph Azaria, John D. Halamka, MD, Andrew Lippman, MIT Media Lab, Beth Israel Deaconess Medical Center
>
> 译者：区块链中文字幕组 Chuan
>
> 时间：2018-04-07



### MedRec白皮书 第二部分



#### System Implementation系统实现

#### Overview概要

For MedRec, the block content represents data ownership and viewership permissions shared by members of a private, peer-to-peer network. Blockchain technology supports the use of “smart contracts,” which allow us to automate and track certain state transitions (such as a change in viewership rights, or the birth of a new record in the system). Via smart contracts on an Ethereum blockchain [10], we log patient-provider relationships that associate a medical record with viewing permissions and data retrieval instructions (essentially data pointers) for execution on external databases. We include on the blockchain a cryptographic hash of the record to ensure against tampering, thus guaranteeing data integrity. Providers can add a new record associated with a particular patient, and patients can authorize sharing of records between providers. In both cases, the party receiving new information receives an automated notification and can verify the proposed record before accepting or rejecting the data. This keeps participants informed and engaged in the evolution of their records.

对MedRec来说，区块内容指的是一个私有的、点对点的网络中成员共享的数据所有权和查看许可权。区块链技术支持“智能合约“，这让我们能够自动地跟踪某些状态的转变（比如，查看权利的变化，或者系统中新增了一条记录）。通过以太坊上的智能合约，我们记录下病人和医疗机构之间的关系，这一关系把一条看病记录与查看许可和数据检索指令（本质上是数据指针）建立关联，用于在外部数据库执行。我们对看病记录进行加密哈希处理放到区块链上，来保证内容不被篡改，从而确保数据的完整性。医疗机构能够添加病人的一条新的看病记录，并且病人可以授权他的看病记录在不同医疗机构之间的共享。在这两种情况下，接受新信息的一方接收自动的提醒，并能够在接受或拒绝数据之前验证提交的这一记录。这使得参与者了解他们看病记录的情况，并参与到看病记录的改进过程中。

MedRec prioritizes usability by also offering a designated contract which aggregates references to all of a user's patient-provider relationships, thus providing a single point of reference to check for any updates to medical history. We handle identity confirmation via public key cryptography and employ a DNS-like implementation that maps an already existing and widely accepted form of ID (e.g. name, or social security number) to the person's Ethereum address. A syncing algorithm handles data exchange “off-chain” between a patient database and a provider database, after referencing the blockchain to confirm permissions via our database authentication server.

MedRec通过提供一份指定的合约优先考虑可用性，这一合约汇集对一个用户所有的医患关系的引用，从而提供一个单一的引用点来检查对病历的任何更新。我们通过公钥密码来处理身份确认，使用类似DNS的实现方法：将一个现存的、被广泛接受的ID形式（如，姓名或社保号）映射到这个人的以太坊地址。在援引区块链来确认经过数据库授权服务器的许可后，同步算法在链外处理病人数据库和医疗机构数据库之间的数据交换。

#### 区块链背景

Originally designed for keeping a financial ledger, the blockchain paradigm can be extended to provide a generalized framework for implementing decentralized compute resources [10]. Each compute resource can be thought of as a singleton state-machine that can transition between states via cryptographically-secured transactions. When generating a new state-machine, the nodes encode logic which defines valid state transitions and upload it onto the blockchain. From there on, the blocks journal a series of valid transactions that, when incrementally executed with the state from the previous block, morph the state-machine into its current state. The Proof of Work consensus algorithm and its underlying peer-to-peer protocol secure the state-machines' state and transitioning logic from tampering, and also share this information with all nodes participating in the system. Nodes can therefore query the state- machines at any time and obtain a result which is accepted by the entire network with high certainty.

最初，区块链被设计用来保存金融账本，后来扩展到为实现去中心化的算力提供一个泛化的框架。每一个算力可以被想象为一个单一状态机，这个状态机能够实现被加密保护的交易的状态之间的转变。当产生新的一个状态机时，节点对定义了有效的状态转变的逻辑进行编码，并且把它上传到区块链上。之后，各个区块记录下一连串有效的交易，当连同之前的区块状态一起递增地执行时，这些交易使这个状态机的状态转变成它的当前状态。工作量证明共识算法及其底层的点对点协议保护状态机的状态和状态转变逻辑防止被篡改，并将这个信息分享给系统中所有的参与节点。因此，节点可以在任何时候查询状态机，获得一个被整个网络高度接受的结果。

This transaction-based state-machine generalization of the blockchain is informally referred to as smart contracts. Ethereum is the first to attempt a full implementation of this idea. It builds into the blockchain a Turing-complete instruction set to allow smart-contract programming and a storage capability to accommodate on-chain state. 

这种以交易为基础的区块链的状态机泛化被称作智能合约。以太坊是第一个尝试完全实现这一想法的。它将一个图灵完备指令集编译到区块链上，来允许智能合约开发以及存储链上状态。

We utilize Ethereum's smart contracts to create intelligent representations of existing medical records that are stored within individual nodes on the network. We construct the contracts to contain metadata about the record ownership, permissions and data integrity. The blockchain transactions in our system carry cryptographically signed instructions to manage these properties. The contract's state- transition functions carry out policies, enforcing data alternation only by legitimate transactions. Such policies can be designed to implement any set of rules which govern a particular medical record, as long as it can be represented computationally. For example, a policy may enforce that separate transactions representing consent are sent from both patients and care providers, before granting viewing permissions to a third party.

我们利用以太坊的智能合约来创建对现存的病历的代码化表示，这些看病记录被存储在网络上每个节点内。我们构建一些合同来包含关于看病记录的所有权，查看许可权和数据完整性的元数据。这一系统里的区块链交易携带加密签名的指令来管理这些属性。合同的状态转变函数执行制定的策略，只有合法的交易才执行数据的更改。这些策略能够被设计用来执行任意管理特定的看病记录的规则集合，只要它能被代码化表示。例如，一个策略也许要求：在授权查看许可给第三方之前，分布各处的包含许可内容的交易能够从病人和医疗机构发出。

To navigate the potentially large amount of record representations, our system structures them on the blockchain by implementing three types of contracts. Figure 1 illustrates the contract structures and relationships.

为了可以遍历大量的代码化表示的病历，我们的系统通过执行3种类型的合同对它们进行结构化处理，放到区块链上。图1中演示了合约的结构和关系。

#### 智能合约结构

**Registrar Contract登记员注合约**

This global contract maps participant identification strings to their Ethereum address identity (equivalent to a public key). We intentionally use strings rather than the cryptographic public key identities directly, allowing the use of already existing form of ID. Policies coded into the contract can regulate registering new identities or changing the mapping of existing ones. Identity registration can thus be restricted only to certified institutions. The RC also maps identity strings to an address on the blockchain.

这个全局合约把参与者身份字符串映射到他们的以太坊地址（等同于公钥）。我们有意采用字符串而不是直接使用加密公钥地址，这可以允许使用现存的ID形式。策略被代码化写入合约，能够规范登记新身份或改变现存身份的映射。因此，身份登记可以被仅限于认证过的机构。这个登记员合约也映射身份字符串到区块链上的一个地址。

**Patient-Provider Relationship Contract (PPR) 病人与医疗机构的关系合约（PPR）**

A Patient-Provider Relationship Contract is issued between two nodes in the system when one node stores and manages medical records for the other. The PPR defines an assortment of data pointers and associated access permissions that identify the records held by the care provider. Each pointer consists of a query string that, when executed on the provider's database, returns a subset of patient data. The query string is affixed with the hash of this data subset, to guarantee that data have not been altered at the source. Additional information indicates where the provider's database can be accessed in the network, i.e. hostname and port in a standard network topology. The data queries and their associated information are crafted by the care provider and modified when new records are added. To enable patients to share records with others, a dictionary implementation (hash table) maps viewers’ addresses to a list of additional query strings. Each string can specify a portion of the patient's data to which the third party viewer is allowed access.

PPR发生在系统中两个节点之间，其中一个节点为另一个节点存储并管理病历。PPR定义各种数据指针以及关联的访问许可，这些访问许可识别由护理中心掌握的看病记录。每个指针由一个查询字符串组成，当在护理中心的数据库上执行查询时，这个查询字符串返回一个病人数据的子集。查询字符串前面加上这个数据子集的哈希值，来保证数据不会被更改。其他的信息表明医疗机构的数据库在网络上可以从哪里来访问，也就是标准的网络拓扑中的主机名和端口。这个数据查询和其相关联的信息由护理中心编写，并且当有新记录添加时对其进行修改。为了使得病人能够和其他人共享自己的看病记录，设计一个词典（哈希表）来把查看者的地址映射到一个查询字符串列表上。每个字符串能够指定病人的数据可以供哪一些第三方查看。

**Summary Contract (SC) 摘要合约(SC)**

This contract functions as a bread crumb trail for participants in the system to locate their medical record history. It holds a list of references to Patient-Provider Relationship contracts (PPRs), representing all the participant's previous and current engagements with other nodes in the system. Patients, for instance, would have their SC populated with references to all care providers they have been engaged with. Providers, on the other hand, are likely to have references to patients they serve and third-parties with whom their patients have authorized data sharing. The SC persists in the distributed network, adding crucial backup and restore functionality. Patients can leave and rejoin the system multiple times, for arbitrary periods, and always regain access to their history by downloading the latest blockchain from the network. As long as there are nodes participating in the network, the blockchain log is maintained.

这个合约的功能是为系统的参与者提供一个导引来定位他们的病历。它包含一个对PPR的引用清单，表明这个参与者以前的和当前的与系统中其他节点的所有往来情况。例如，病人会把他们的摘要合约包含他们联系的所有护理中心。另一方面，护理中心的情况则可能是，他们的摘要合约包含了他们服务的病人和他们的病人授权可以数据共享的第三方。这个摘要合约一直在这个分布式网络上，添加重要的备份和恢复功能。病人可以多次离开、重新加入这个系统，并且通过从网络上下载最新的区块链数据库重新获得对他们病历内容的访问。只要有节点参与到这个网络中，区块链的日志就得以保存。

The SC also implements functionality to enable user notifications. Each relationship stores a status variable. This indicates whether the relationship is newly established, awaiting pending updates and has or has not acknowledged patient approval. Providers in our system set the relationship status in their patients' SC whenever they update records or as part of creating a new relationship. Accordingly, the patients can poll their SC and be notified whenever a new relationship is suggested or an update is available. Patients can accept, reject or delete relationships, deciding which records in their history they acknowledge.

摘要合约还包含提醒用户的功能。每个关系存储一个状态变量。这表明关系是否是新建立的，还是等待稍后更新，以及是否接受病人的同意。无论他们何时更新看病记录，医疗机构就在他们病人的摘要合约中设置这一关系的状态，或把这一关系的状态作为创建新状态的一部分。相应地，无论何时有新的关系出现或者有可用的更新时，病人可以对他们的摘要合约进行检查，并接收提醒。病人能够接受、拒绝或删除这些关系，决定他们认可病历中的哪些记录。

#### 系统节点描述System Node Description

We design the components of our system nodes to integrate with existing EHR infrastructure. We assume that many nodes, and in particular care providers, already trustfully manage databases with patient data stored on servers with network connectivity. Our design introduces four software components: Backend Library, Ethereum Client, Database Gatekeeper and EHR Manager. These can be executed on servers, combining to create a coherent, distributed system. 

我们设计系统的组件时，整合了现存的电子病历基础结构。我们认为，许多节点值得信任，尤其是护理中心，他们管理那些存储在服务器上的病人数据库。我们的设计引入了四个软件组件：后端API库，以太坊客户端，数据库守护者和电子病历管理者。这些都能够在服务器上被执行，整合起来产生一个前后一致的、分布式的系统。

Patient nodes in our system contain the same basic components as providers. An implementation of these can be executed on a local PC or even a mobile phone. Their local database can be one of many lightweight database implementations. The databases can function merely as cache storage of the patient's medical data. Missing data can be retrieved from the network at any time by following the node's Summary Contract.

病人节点像护理中心节点一样包含同样的基本组件。它们的实现可以在本地电脑或者手机上执行。本地数据库可以采用轻量级的数据库来实现。这些数据库的功能仅作为病人医疗健康数据的缓存。丢失的数据能够依照节点的摘要合约在任何时候从网络上检索获得。



（续）



------

**区块链中文字幕组**

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号：w1791520555。

[点击查看 GITHUB 及更多的译文](https://github.com/BlockchainTranslator/EOS)

**本文译者介绍**

Chuan，区块链技术爱好者。欢迎加我的微信：youyuxiaochuan

译文版权所有，转载需完整注明以上内容。





