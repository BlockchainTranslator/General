## MedRec白皮书 第三部分



文章来自：A Case Study for Blockchain in Healthcare: “MedRec” prototype for electronic health records and medical research data

作者：Ariel Ekblaw, Asaph Azaria, John D. Halamka, MD, Andrew Lippman, MIT Media Lab, Beth Israel Deaconess Medical Center

译者：区块链中文字幕组 Chuan

时间：2018-04-08



> MedRec，一个去中心化的、使用区块链技术的病历管理系统。这个系统提供给病人全面的、不可篡改的检查结果，并且可以通过各种医疗机构和治疗中心查看他们的诊断信息。利用区块链独特的特性，MedRec可以管理授权、对数据保密、实现数据共享。



### Primary Software Modules主要软件模块

#### 1、Backend API Library后端API库

We construct multiple utilities, bundled in a backend library, to facilitate the system's operation. Our library abstracts the communications with the blockchain and exports a function-call API. Record management applications and their user interfaces can thus avoid the hurdles of working directly with the blockchain. One such hurdle is verifying that each sent transaction is accepted with high confidence by the network. Our library automatically handles the uncertainty of when transactions are mined and deals with cases when they are discarded. The backend library interacts with an Ethereum client to exercise the low-level formatting and parsing of the Ethereum protocol.

我们设计了多个实用功能，与后端库整合，来促进系统的运行效率。这个库抽象了与区块链的通讯细节，输出一个调用函数的 API。因此，病历管理应用和用户接口能够避开一些要与区块链直接进行交互的难关。其中一个是要作出这样的验证：每一个被发送的交易被这一网络高可信地接受。这个 API 库自动地处理交易什么时候被挖到这样的不确定情况，以及处理什么时候丢弃交易的情况。后端库与以太坊客户端建立连接来执行以太坊协议的低层格式和分析。

Steps 1 and 2 in Figure 2 illustrate our backend implementation of a scenario where a provider adds a record for a new patient. Using the Registrar Contract on the blockchain, the patient's identifying information is first resolved to their matching Ethereum address and the corresponding Summary Contract is located. Next, the provider uploads a new PPR to the blockchain, indicating their stewardship of the data owned by the patient's Ethereum address. The provider node then crafts a query to reference this data and updates the PPR accordingly. Finally, the node sends a transaction which links the new PPR to the patient's Summary Contract, allowing the patient node to later locate it on the blockchain.

图2中的步骤1和2演示了后端库实现的一个场景：医疗机构为一个新的病人添加一条记录。使用区块链上的登记员合约，病人的身份信息首先被转换为它们相匹配的以太坊地址，并定位对应的摘要合约。接下来，医疗机构上传新的PPR 到区块链，表明它们对病人的以太坊地址所拥有的数据的管理权。然后，医疗机构节点编写一个查询来查看这个数据，并相应地更新 PPR。最后，这个节点发送一个交易用于把新的 PPR 连接到病人的摘要合约，允许病人节点之后在区块链上查找它。

#### 2、Ethereum Client以太坊客户端

This component implements the full functionality required to join and participate in the Ethereum blockchain network. This handles a broad set of tasks, such as connecting to the peer-to-peer network, encoding and sending transactions and keeping a verified local copy of the blockchain. For our prototype implementation we use PyEthereum and the PyEthApp client.

这个组件执行的功能是加入和参与到以太坊区块链网络。它处理一组任务，比如：连接到点对点网络，编码并发送交易，保存一份验证过的区块链的本地备份。原型实现中，我们使用PyEthereum和PyEthApp客户端。

We modify the client to be aware of our mapping of identity and addresses. We then implement a service to locate the node's Summary Contract (SC), via Registrar Contract address lookup. This service runs continuously within the client to monitor real-time changes to the SC. In the event of an update, the service signals the EHR Manager to issue a user notification and, if necessary, sync the local database.

我们修改这个客户端来记录身份和地址的映射。然后，经过登记员合约的地址查找，我们执行一个服务来查找节点的摘要合约。这个服务一直在客户端运行来监测摘要合约的实时变化。在更新事件中，这一服务发送信息给电子病历管理者，让他发出一个用户提醒，并且，如果必要的话，同步本地数据库。

Steps 4 to 6 in Figure 2 continue the use case described above from the patient node perspective. The patient's modified Ethereum client continuously monitors her SC. Once a new block is mined with the newly linked PPR, the client issues a signal which results in a user notification. The user can then acknowledge or decline her communication with the provider, updating the Summary Contract accordingly. If the communication is accepted, our prototype implementation automatically issues a query request to obtain the new medical data. It uses the information in the new PPR to locate the provider on the network and connect to its Database Gatekeeper server.

图2中的步骤4到6从病人节点的角度继续上面的用例描述。病人设备上修改过的以太坊客户端持续地监测他的摘要合约。一旦一个新的区块被使用新连接的 PPR 挖到，这个客户端发出一个给用户提醒的信号。然后，这个用户能够承认或拒绝他与医疗机构之间的通信，相应地进行摘要合约的更新。如果这个通信被接受，我们的系统自动发出一个查询请求来获得新的医疗健康数据。它使用这个新的PPR中的信息来查找网络上的医疗机构，并连接到它的数据库守门人服务器。

#### 3、Database Gatekeeper数据库看门人

The Database Gatekeeper implements an off-chain, access interface to the node's local database, governed by permissions stored on the blockchain. The Gatekeeper runs a server listening to query requests from clients on the network. A request contains a query string, as well as a reference to the blockchain PPR that warrants permissions to run it. The request is cryptographically signed by the issuer, allowing the gatekeeper to confirm identities. Once the issuer's signature is certified, the gatekeeper checks the blockchain contracts to verify if the address issuing the request is allowed access to the query. If the address checks out, it runs the query on the node's local database and returns the result over to the client.

数据库看门人执行一个对节点的本地数据库的链外访问接口，由存储在区块链上的许可来管理。看门人运行一个服务监听来自于网络上的客户的查询请求。一个请求包括一个查询字符串，以及对区块链PPR的引用，这个PPR确保同意运行这个请求。这个请求被发布者加密签名，允许数据库看门人确认身份。一旦发布者的签名被验证，数据库看门人检查区块链合同来验证发出这个请求的地址是否被允许对这个查询可用。如果这个地址被确认，那么它允许查询在节点的本地数据，并返回结果给这个客户。

Steps 7 to 9 in Figure 2 illustrate how a patient retrieves personal data from the provider node. Note that our components similarly support third-parties retrieving patient-shared data: the patient selects data to share and updates the corresponding PPR with the third-party address and query string. If necessary, the patient's node can resolve the third party address using the Registrar Contract on the blockchain. Then, the patient node links their existing PPR with the care provider to the third-party's Summary Contract. The third party is automatically notified of new permissions, and can follow the link to discover all information needed for retrieval. The provider's Database Gatekeeper will permit access to such a request, corroborating that it was issued by the patient on the PPR they share.

图2中的步骤7到9演示了一个病人如何从医疗机构节点检索个人数据。我们的组件同样支持第三方检索病人共享的数据：病人选择数据来共享，并使用第三方地址和查询字符串来更新相应的PPR。

#### 4、EHR Manager电子病历管理者

We tie together all the software components previously mentioned with our EHR management and user interface application. The application renders data from local SQLite databases (designed to be interchangeable with other DB software) for viewing, and presents the users with update notifications, and data sharing and retrieval options. Our application is conveniently accessed through a web interface, built on a python backend framework. We are especially cognizant of compatibility for mobile devices.

我们将之前的几个组件与电子病历管理和用户接口应用连接到一起。这个应用使得来自本地数据库的数据可用、被查看，并向用户发送更新提醒，以及提供数据共享和检索的选项。我们的应用可以方便地通过web接口访问，搭建在python后端框架上。我们还特别在意对移动设备的兼容。

### MedRec Blockchain Mining MedRec区块链挖矿

We incentivize “miners” to participate in the network and contribute their computational resources to achieve a trustworthy, gradual advancement of the chain. We propose a model that engages the healthcare community in network stewardship—MedRec brings medical researchers and health care stakeholders to mine in the network. In return, the network beneficiaries, i.e. providers and patients, release access to aggregate, anonymized medical data as mining rewards. We explore this idea in our prototype by implementing a special function in the PPR contract. It requires care providers to attach a bounty query to any transaction they send updating the PPR. For example, this bounty query can be formulated to return the average iron levels in blood tests done by the provider, across all patients, in the previous week. When the block containing the record-update transaction is mined, the mining function automatically appends the block's miner as the owner of the bounty query. The miner can then collect it by simply issuing a request for this bounty to the provider's Database gatekeeper. Because it is signed by the provider as part of the transaction, the bounty query is safe from malicious alterations. This “bounty query” or data reward for mining enables medical researchers to access population-level insights into medical treatment and healthcare outcomes, potentially revolutionizing how data is gathered and accessed for research purposes. 

我们激励“矿工”参与到这个网络，并贡献它们的算力来实现一个可信的、逐渐改善的区块链应用。我们提出一个模型，让健康医疗社区参与到网络管理中 - MedRec把医疗研究人员和健康医疗行业的股东引入到这个网络中挖矿。作为回报，这个网络的受益方，也就是医疗机构和病人，释放对所有的、匿名的医疗数据的访问权作为挖矿奖励。在原型设计中我们探索了这个想法，通过执行PPR合约中的一个特别函数。它要求护理中心把一个奖赏查询附在他们发送的任何一个更新PPR的交易上。例如，这个奖赏查询可能被设计为返回医疗机构提供的血液检测中铁的平均含量。当包含更新记录的交易的区块被挖到时，挖矿函数自动地添加这个块的矿工为这个奖赏查询的拥有者。然后，这个矿工通过向医疗机构的数据库看门人发出请求来获得这个奖赏。因为它被医疗机构签名作为交易的一部分，所以这个奖赏查询是安全的，不会受到恶意的修改。这种“奖赏查询”或对挖矿的数据奖赏使得医学研究人员能够将对普通人的数据处理运用到治疗过程中，这有可能对数据的收集和访问的方式产生改变。



（续）

------

**区块链中文字幕组**

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号：w1791520555。

[点击查看 GITHUB 及更多的译文](https://github.com/BlockchainTranslator/EOS)

**本文译者介绍**

Chuan，区块链技术爱好者。欢迎加我的微信：youyuxiaochuan

译文版权所有，转载需完整注明以上内容。如有侵权，请与译者联系删除。



