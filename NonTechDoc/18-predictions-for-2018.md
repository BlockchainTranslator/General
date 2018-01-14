## 18 Blockchain Predictions for 2018 | 18 个对 2018 年区块链的预测

> 本文翻译自：https://media.consensys.net/18-predictions-for-2018-7a376ea7bd4b
>
> 作者：Andrew Keys
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator) [鱼](https://github.com/oscnet)
>
> 翻译时间：2018-1-10
>
> 本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。

![](https://cdn-images-1.medium.com/max/1600/0*SejpCTS8tWM22WcC.jpg)

### 1. Bitcoin is the generation 0 of blockchain technology… the opening act… the gateway drug … the first inning … MySpace. | 比特币是区块链技术的第一代...开幕...药引...第一局... 。

We must thank her for her work, as none of the following technology would be available without Satoshi’s Bitcoin, but we’re about to go much, much, further. While Satoshi converged a database structure with peer-to-peer networking, cryptographic tokenization, consensus formation algorithms, and game theoretical economic incentivization to create a means for trustless digital storage and transmission of value, the “[Digital Gold](https://www.amazon.com/Digital-Gold-Bitcoin-Millionaires-Reinvent/dp/006236250X)” use case, is only one use case.

我们必须感谢她及她所做地工作，没有中本聪的比特币，就没有以下所谈论的的各种技术，我们将在这方面走得更远。虽然中本聪将数据库跟点对点网络、加密标记化、共识形成算法以及游戏理论的经济激励融合，创建了一种无需信任的数字存储和价值传输手段，“[数字黄金](https://www.amazon.com/Digital-Gold-Bitcoin-Millionaires-Reinvent/dp/006236250X)”只是它其中一个用法。

**Bitcoin as a digital store of value is the least interesting use of blockchain … There, I said it.**

**在那里，我就说了，比特币作为价值的数字存储是区块链应用中最没趣的用途...**。

Far more interesting are programmable money, programmable asset transfer, and shared, tamper-resistant business logic. People fixated on Bitcoin are missing the fact that we’re verging upon the next generation of the world-wide-web.

The Bitcoin protocol is the world’s largest modern-day abacus; it only enables us to move a bead (or coin) from one side to the other. The ability to do this on a global, permissionless substrate is not trivial. But I can’t overemphasize the limited scope of this initial design, due to its use of a virtual machine which isn’t Turing-complete.

Here’s an example of a [Bitcoin script](https://en.bitcoin.it/wiki/Script):

更有趣的是可编程货币、可编程资产转移和共享的防篡改业务逻辑。专注于比特币的人们将会错过我们正在接近下一代万维网的事实。

比特币协议是世界上最大的现代算盘; 它使我们只能将珠子（或硬币）从一边移到另一边。在全球性的、无需许可的基础上要做到这一点并不是微不足道的。我不能过分强调这个初始设计的功能限制，就因为它使用了一个不是图灵完备的虚拟机。

这是一个比特币脚本的例子：

scriptPubKey: OP_DUP OP_HASH160 <pubKeyHash> OP_EQUALVERIFY

OP_CHECKSIG

scriptSig: <sig> <pubKey>

The above script should serve to explain the inherent limitations of the Bitcoin scripting language. [Ethereum can be thought of as Bitcoin + everything else](https://medium.com/@ConsenSys/ethereum-bitcoin-plus-everything-a506dc780106), with a high level software language reminiscent of Javascript.

While still being able to store and transmit value (the single Bitcoin use case), we’re also able to program our agreements using Ethereum. Here are two examples of typical agreements that are now easily codified using Ethereum’s Solidity programming language.

上面的脚本应该能解释比特币脚本语言固有的局限性。[以太坊可以被认为是 比特币+](https://medium.com/@ConsenSys/ethereum-bitcoin-plus-everything-a506dc780106)，使用一个类似 Javascript 的高级软件语言。

虽然仍然能够存储和传输价值（同比特币一样），但我们还可以使用以太坊来设计我们达成的协议。
这里有两个典型协议的例子，这些协议现在很容易使用以太坊的 Solidity 编程语言编写。

A Loan | 贷款

![](https://cdn-images-1.medium.com/max/1600/1*2u8JgmcvbYXxtpDARNwYVw.png)

An Initial Public Offering or Crowdfunding

首次公开募股或众筹

![](https://cdn-images-1.medium.com/max/1600/1*pcanWG7sWJjHiahjvXUExA.png)

Our agreements are turning from Microsoft Word documents written by attorneys and recognized by notaries into agreements bound by code, transacting assets that are natively digital.

As the Internet commoditized the cost for communication, Ethereum commoditizes our costs of agreement and trust.

我们的协议正在从由律师撰写并由公证人承认的微软 Word 文档转变为由软件代码组成的协议，交易资产原生数字化了。

互联网将通信成本商品化，以太坊将我们的协议和信任成本商品化。

### 2. 2018 in blockchain years is the equivalent of 1994 to the 1996 boom of the Internet. | 2018年对区块链来说，相当于1994年至1996年的互联网繁荣时期。

Intranets First

Similar to the evolution of the Internet that began on private Intranets, [permissioned blockchains](https://azure.microsoft.com/en-us/blog/ethereum-blockchain-as-a-service-now-on-azure/) will give way to the permissionless blockchains once they successfully achieve scalability and privacy.

内联网先行

和从私有内联网上开始发展的互联网演变类似，一旦成功实现可扩展性和隐私性，[许可链](https://azure.microsoft.com/en-us/blog/ethereum-blockchain-as-a-service-now-on-azure/)将让位给公有链。

The Stack

The next generation of the internet will be a “stack” comprised of: (1) a decentralized transaction layer (the strongest of which I believe to be Ethereum); (2) a decentralized file storage layer ([IPFS](https://ipfs.io/) and [Swarm](https://github.com/ethersphere/swarm) are early leaders); (3) a decentralized messaging layer ([Matrix](http://matrix.org/) or [Whisper](https://github.com/ethereum/wiki/wiki/Whisper) are strong candidates); and (4) a high throughput computing resource ([Golem](https://golem.network/) is an example of attempting to accomplish this).

堆栈

下一代互联网将是一个“堆栈”，由以下各层的组成：（1）一个去中心化的交易层（我认为其中最强的一个是以太坊）; （2）去中心化的文件存储层（ [IPFS](https://ipfs.io/)) 和 [Swarm](https://github.com/ethersphere/swarm) 是早期的领导者）; （3）去中心化的消息传递层（ [Matrix](http://matrix.org/) 或 [Whisper](https://github.com/ethereum/wiki/wiki/Whisper) 是强有力的候选人）; 和（4）高吞吐量计算资源（ [Golem](https://golem.network/) 是试图完成这个的一个例子）。

Standards

As Jeremy Millar [noted](https://media.consensys.net/the-birth-of-enterprise-ethereum-in-2017-ebe7f7abed92) at the inception of the [Enterprise Ethereum Alliance](http://www.entethalliance.org/), blockchain technologies will be helped tremendously in 2018 through formal standardization processes similar to when Java evolved into Java 2 Enterprise Edition through standardization of database and web API’s to be the most widely used software language on Earth.

标准

正如 Jeremy Millar 在[企业以太坊联盟](http://www.entethalliance.org/)成立时[指出](https://media.consensys.net/the-birth-of-enterprise-ethereum-in-2017-ebe7f7abed92)的那样，如同 Java 通过对数据库和 Web API 的标准化演变成 Java 2 企业版 ，从而成为在地球上最广泛使用的开发语言。2018年，区块链技术借助正规的标准化流程，将得到极大的助力。

Consumer Facing Applications

Early use cases of consumer facing Internet applications in the 90’s were gambling, pornography, and games.

Interestingly, we’re seeing frontrunners on Ethereum in the same genres with [Spankchain](https://spankchain.com/), [Fun Fair](https://funfair.io/), [Virtue Poker](https://virtue.poker/), and [Crypto Kitties](https://www.cryptokitties.co/) consumer facing applications on Ethereum.

面向消费者的应用

90年代消费者在互联网上的早期应用是赌博，色情和游戏。有趣的是，我们看到了 [Spankchain](https://spankchain.com/)，[Fun Fair](https://funfair.io/)，[Virtue Poker](https://virtue.poker/) 和 [Crypto Kitties](https://www.cryptokitties.co/) 等以太领先者的应用，这些面向消费者的以太坊上应用也跟早期互联网发展相类似。

### 3. Ethereum will continue to be the largest blockchain developer ecosystem in 2018 by many multiples. | 2018 以太坊将继续成为最大的区块链开发者生态系统。

[Developers, developers, developers, developers, developers](https://www.youtube.com/watch?v=KMU0tzLwhbE)… you get the point.

The ecosystems with the most developers typically win. I don’t see how permissioned blockchains that lack cryptoeconomic incentives will ever stand against public permissionless ecosystems.

Ethereum already has a thriving developer community. [Truffle](http://truffleframework.com/dashboard/), the smart contract developer framework, has 250,000+ developer downloads. [Infura](https://infura.io/), which can be seen as an Akamai for Ethereum and IPFS, now handles over 2 billion requests per day and smoothly scaled to peak at 4.5 billion requests per day one day in December. [MetaMask](https://metamask.io/), which brings Ethereum seamlessly to browsers, has over 500,000 active users.

[开发人员，开发人员，开发人员，开发人员，开发人员](https://www.youtube.com/watch?v=KMU0tzLwhbE) ... 你领会我的意思了吧。

拥有最多开发者的生态系统通常能赢得胜利。我认为那些些缺乏加密经济激励机制的许可链将永远无法与有着公共许可的生态系统对抗。

以太坊已经有了一个蓬勃发展的开发者社区。[Truffle](http://truffleframework.com/dashboard/) 是智能合约开发者框架，拥有25万以上的开发者下载量。[Infura](https://infura.io/) 可以看作以太坊和 IPFS 的 Akamai (译者注：是一家内容分发网络和云服务提供商，世界上最大的分布式计算平台之一)，现在每天处理超过 20 亿个请求，并在12月份顺利达到到每天峰值 45 亿个请求量。[MetaMask](https://metamask.io/) 将以太坊无缝地引入浏览器，拥有超过 500,000 个活跃用户。

### 4. Blockchain will be a vessel of good. | 区块链将是一艘好船。

As the world takes note of the societal implications of blockchain technology, we will see an uptick in humanitarian applications in 2018.

In 2017 [we saw](https://qz.com/1118743/world-food-programmes-ethereum-based-blockchain-for-syrian-refugees-in-jordan/) the World Food Program employ Ethereum to distribute 1.4 million food vouchers to 10,500 Syrian refugees in Jordan. And it is aiming for one million transactions, per day. This innovative program, dubbed “Building Blocks”, demonstrates how database efficiency will deliver tangible benefits to the most vulnerable. I applaud the World Food Program’s efforts and believe that its success is a sign of great things to come.

随着区块链技术的社会影响不断扩大，2018年我们将看到其在有关人道主义上的应用的增长。

2017年，我们[看到](https://qz.com/1118743/world-food-programmes-ethereum-based-blockchain-for-syrian-refugees-in-jordan/)世界粮食计划署使用以太坊区块链向约旦的 10,500 名叙利亚难民分发了 140 万张食物券。它的目标是每天 100 万笔交易。
这个被称为“积木”的创新应用，展示了数据库如何有效率地为最弱势群体带来切实利益。我赞赏世界粮食计划署的努力，并相信这次它的成功将成为以后伟大事迹的标志。

### 5. Enterprises will take the training wheels off | 企业将正式发车

As permissionless blockchains continue their scalability and privacy upgrade process, permissioned blockchains will continue to lose the developer mindshare and potentially lose their client base similar to how AOL, Prodigy, and Compuserve services lost out to the Internet. There will be narrow use-cases for intranet-like permissioned blockchains, just as [SWIFT](https://www.swift.com/) never touched the internet, but the long tail will be using permissionless protocols.

Intranets were great training wheels, until the Internet was pervasive. The same trajectory will occur with permissioned blockchains in 2018 and beyond.

由于无许可区块链继续其解决可扩展性和隐私地升级地过程，因此类似于 AOL、Prodigy 和 Compuserve 服务在互联网上的失败，许可链将继续失去开发人员的青睐，并可能失去他们的客户基础。如同内联网一样，许可链的应用会变得很狭窄。正如 [SWIFT](https://www.swift.com/) (银行结算系统) 一样从未接触互联网，由于长尾效应 (译注：是指那些原来不受到重视的销量小但种类多的产品或服务由于总量巨大，累积起来的总收益超过主流产品的现象。在互联网领域，长尾效应尤为显著) 的存在，无许可协议将更为流行。

在互联网普及前，内联网是一个很好的用于培训练习的轮子。2018年及以后，许可链将出现同样的发展轨迹。

### 6. Proof of Stake changes the blockchain consensus game | 权益证明将改变区块链共识的游戏规则

On New Years Eve ’17, the Ethereum research team dropped the [testnet alpha of Casper](https://t.co/4BL9Ztq2vy), named after the Greediest Heaviest Observed SubTree protocol. All eyes in the blockchain space will be watching the transition of Ethereum from proof of work to proof of stake.

A proof-of-work consensus algorithm is an economic measure to deter denial of service attacks and other service abuses such as spam on a blockchain by requiring some work from the service requester, usually by processing complex equations on a GPU or ASIC computer.

17年除夕，以太坊研究团队放弃了以幽灵协议 GHOST 命名的 [Casper 的 alpha 版本测试网络](https://t.co/4BL9Ztq2vy)。区块链空间中的所有人都将关注以太坊从工作量证明到权益证明的过渡。

工作量证明共识算法是一种经济措施，通过需要服务请求者一定量的工作（通常是在 GPU 或 ASIC 计算机上处​​理复杂方程运算）来阻止拒绝服务攻击和区块链上的其他服务滥用（类似垃圾邮件）。

In proof-of-stake public blockchains, like Ethereum’s upcoming Casper implementation, a set of validators each bet on blocks they deem likely to be validated, and the weight of each validators vote depends on the size of its deposit. Punishments are levied on bad actors who bet on more than one block at a certain depth or who don’t participate when they are supposed to.

Benefits of proof-of-stake include:

在权益证明公开链上，如以太坊即将推出的 Casper 实施方案中，一组验证者在他们认为可能被验证的区块上下注，每个验证者投票的权重取决于其存款的大小。并对下注在一个块以上的，或者应该参与时却不参与的不良行为者进行惩罚。

证明权益的好处包括：

* The ability to reduce the large electricity consumption and hardware costs to secure a blockchain. It is estimated the Bitcoin electric consumption will trend toward equivalent consumption of the country of [Denmark](https://spectrum.ieee.org/energy/policy/the-ridiculous-amount-of-energy-it-takes-to-run-bitcoin) by 2020.

* Due to reduced energy consumption, token issuance isn’t necessarily intrinsic to the securitization of the network. Negative net issuance could occur, whereby tokens are actually burned thereby reducing the supply and increasing value per token.

* 51% attacks become exponentially more expensive, as you risk what you stake. Vlad Zamfir often explains that “if you participate in a failed 51% attack, PoS will burn your ASIC farm down”.

* 降低大量电力消耗和硬件成本并确保区块链安全。预计到2020年，比特币[挖矿消耗的电力将等同丹麦一个国家的电量消费](https://spectrum.ieee.org/energy/policy/the-ridiculous-amount-of-energy-it-takes-to-run-bitcoin)。

* 由于减少了能源消耗，网络证券化的本质并不一定就是代币发行。也可能发生负净发行，通过代币确实被销毁，从而减少了代币的供应量、增加了代币价值。

* 成倍地增加了51％的攻击的成本，因为你承担了你所赌注的风险。弗拉德·赞菲尔（Vlad Zamfir）经常解释说：“如果你参加51％攻击，PoS 将会把你的 ASIC 芯片烧毁“。

### 7. Token Fever — Not so fast on the SAFT. | 代币在发烧 - 但 SAFT（未来代币简单协议）进展不快。

As Earth continues to realize the advantages of natively digital assets for everything ([natural resources](http://veridium.io/), [fiat](https://www.coindesk.com/santander-vies-become-first-bank-issue-digital-cash-blockchain/), [gold](https://www.coindesk.com/santander-vies-become-first-bank-issue-digital-cash-blockchain/), [music](https://ujomusic.com/), loyalty points, [Madonna concert tickets](http://www.madonna.com/), software, [real estate](https://medium.com/@pangeaGO/stop-selling-your-upside-how-blockchain-can-unlock-value-in-real-estate-through-fractional-b492400b47a?source=linkShare-6940659ec4e7-1515328751), IoT device registration, [stocks](https://www.tzero.com/), [electrons](https://gridplus.io/), etc.) on global distributed ledgers, regulation will be necessary. Regulators will be empowered to create smart contract software specifications and develop tests that compliant companies must pass.

随着全球逐渐意识到原生数字资产（包括自然资源，法定地址，黄金，音乐，忠诚点，麦当娜演唱会门票，软件，房地产，物联网设备注册，股票，电子等）在全球分布式分类账上的优势，监管将是必要的。监管机构将被授权创建智能合同软件规范，开发针对合规公司必须通过的测试软件。

With respect to the tokenization regulatory process, I’m thankful to Marco Santori, Juan Batiz-Benet, and Jesse Clayburgh for taking the first crack at self-regulation through the [SAFT](https://www.cooley.com/~/media/cooley/pdf/reprints/saft-project-whitepaper.ashx) whitepaper (hat-tip to [Y-Combinator’s SAFE](https://www.ycombinator.com/docs/SAFE_Primer.rtf)), but I’m not convinced that the well-intentioned SAFT is right for most tokenization projects.

关于代币化监管流程，我很感谢 Marco Santori，Juan Batiz-Benet 和 Jesse Clayburgh 通过 [SAFT](https://www.cooley.com/~/media/cooley/pdf/reprints/saft-project-whitepaper.ashx) 白皮书（[Y-Combinator 的 SAFE]((https://www.ycombinator.com/docs/SAFE_Primer.rtf)）让我第一次了解有关自律监管方面的机遇，但是我并不相信本意善良的 SAFT 能适合绝大多数的代币化项目。

ConsenSys began the [Brooklyn Project](https://media.consensys.net/announcing-the-brooklyn-project-for-token-launches-22ba89279f5f) to embark on a journey of self-regulatory best practices and the bright legal minds of Cardozo Law and the ConsenSys legal team wrote an exquisite paper detailing the limitations of the SAFT.

ConsenSys 的 [Brooklyn](https://media.consensys.net/announcing-the-brooklyn-project-for-token-launches-22ba89279f5f) 项目开始了有关自律监管的最佳实践之旅，聪明的 Cardozo Law 和 ConsenSys 法律团队写了一篇精美的论文，详细描述了 SAFT 的局限性。

[Token Foundry](http://tokenfoundry.io/) will be the first platform to allow regulatory compliant utility token launches without using a SAFT — meaning everyone (not just accredited people on Sand Hill Rd.) will be able to participate and purchase tokens in an initial sale, thereby continuing to democratize venture capital.

I imagine the SAFT debate will continue to evolve into 2018 to further the best practices for tokenization. I look forward to seeing ConsenSys’ tokenization best practices public unveiling in 2018.

[Token Foundry](http://tokenfoundry.io/) 将成为第一个在不使用 SAFT 的情况下发布符合法规要求的公用事业代币的平台 - 这意味着每个人（不只是 Sand Hill Rd 的认证人员）将能够在最初的销售中参与和购买代币，从而使得风险资本的民主化继续下去。

我想，有关 SAFT 的辩论2018年将会继续，以进一步推广代币化的最佳实践。我期待看到 ConsenSys 在 2018 年公开发布的代币化最佳实践。

### 8. The blockchain ecosystem will ramp up their educational resources tremendously. | 区块链生态系统将极大增加教育资源。

“Education is the most powerful weapon you can use to change the world.” — Nelson Mandela

“教育是你可以用来改变世界的最有力的武器。” - 纳尔逊·曼德拉

Until recently, the ones learning have been software engineers, but in ’18 there will be customized educational programs for policy makers, lawyers, project managers, executives, and MBA’s to understand the implications this technology has on their respective fields. ConsenSys Academy has rolled out many of these endeavors already, and has some exciting initiatives coming in the new year.

一直到近期，学习区块链的大都是软件工程师，但是在18年之后，为了让其了解这项技术对各自领域的影响，将会为政策制定者、律师、项目经理、高级管理人员以及工商管理硕士定制教育计划。康森斯学院已经开展了许多这些工作，并且在新的一年里会有一些令人兴奋的举措。

### 9. The IRS and their equivalents globally will be demanding their pound of flesh. | 美国国税局及其全球同行将对此征税。

“Nothing can be said to be certain, except death and taxes.” — Ben Franklin

“除了死亡和税收，没有什么可以说是确定的。” - 本·富兰克林

There is already a precedent in [US vs. Coinbase Inc., et al](https://www.scribd.com/document/365954979/365893210-US-v-Coinbase-Order?irgwc=1&content=10079&campaign=Skimbit%2C%20Ltd.&ad_group=78380X1529106X7864b4a5877e1d5d7166c4abc8dd2aee&keyword=ft750noi&source=impactradius&medium=affiliate#from_embed). where an exchange has had to divulge their user-base’s trading history. I expect similar outreach to other exchanges. Software like [Balanc3](https://www.balanc3.net/) is being used to track the p&l of a person or company’s digital assets as well as trading history. Pay your taxes.

在[美国 Coinbase 交易所等](https://www.scribd.com/document/365954979/365893210-US-v-Coinbase-Order?irgwc=1&content=10079&campaign=Skimbit%2C%20Ltd.&ad_group=78380X1529106X7864b4a5877e1d5d7166c4abc8dd2aee&keyword=ft750noi&source=impactradius&medium=affiliate#from_embed)已经开了先例。交易所(在国家要求下)不得不泄露其用户基础的交易历史。我预料其他交易将也会有类似的情况。像 [Balanc3](https://www.balanc3.net/) 这样的软件正在用来追踪个人或公司的数字资产的损益和交易历史。以便缴纳税款。


### 10. People will take control of their online identities | 我们将真正拥有在线身份的控制权

We will continue to see the growing trend wherein people, companies, and machines manage their identity self-sovereignly rather then by a third party service provider like a bank, Facebook, or another internet service provider.

Interestingly, governments will increasingly find themselves as attestors to these self-sovereign identities, similar to how [Zug, Switzerland](https://www.econotimes.com/Swiss-city-of-Zug-to-offer-blockchain-based-digital-identity-to-residents-793681) is attesting to citizens identity usage with uPort, Ethereum leading self-sovereign identity solution.

我们将继续看到个人、公司和机器能自主地管理自己的身份，而不是使用像银行，Facebook 或其他互联网服务提供商那样的第三方服务提供商。

有趣的是，各国政府将越来越多地发现自己是这些自我主权身份的证明者。类似于瑞士的楚格使用 uPort ，一个太坊上的自我主权身份解决方案，对公民身份进行登记证明，

### 11. In 2018, governments and regulatory bodies will mandate the use of blockchain to track and trace high value assets. | 2018年，政府和监管机构将使用区块链技术来跟踪和追踪高价值资产

“The supply chain stuff is really tricky” — Elon Musk

“供应链的东西真的很棘手 - ”Elon Musk

Companies and organizations will realize that for the first time, it is possible to offload basic track and trace infrastructure to the public chain. This will lead to a decrease in cost and regulatory burden, and an increase in customer brand loyalty. These two trends will set the stage for a shared track and trace infrastructure supported by the public chain.

Major Fortune 50 companies are already demanding public chain track and trace use cases for which they are using the [Viant](http://viant.io/) platform to build their solutions.

第一次，企业和组织将意识到可以将用于追踪的基础设施转移到公共链上。以减少成本和监管负担，提高客户品牌忠诚度。这个趋势将为由公链支持的共享追踪基础设施奠定基础。

主要的财富 50 强公司已经开始努力使用公共链来跟踪，并研究相关使用案例，他们使用 Viant 平台来构建他们的解决方案。

### 12. The evolution of law will continue to intersect computer science. | 法律的演变将继续与计算机科学相交叉。


“The first thing we do, let’s kill all the lawyers” — Shakespeare

“我们做的第一件事，就是杀死所有的律师” - 莎士比亚

The lawyers of tomorrow will need to understand fundamental future aspects of computer science as much as legal precedent.

未来的律师将来需要像了解判例一样，了解计算机科学的基础基本未来方向。

Using [OpenLaw](https://openlaw.io/), lawyers can create, deploy, and edit next-generation legal agreements relying on Ethereum and IPFS. Here are great examples of [restricted stock grant purchase](https://www.youtube.com/watch?v=l7edU35m8OI), [standard agreement for equity](https://www.youtube.com/watch?v=iphsRWQoFDI), and an [ERC20-token purchase agreement](https://www.youtube.com/watch?v=iOYFcbzfPPs).

使用 [OpenLaw](https://openlaw.io/) ，律师可以使用以太坊和 IPFS 来创建、部署和编辑下一代法律协议。以下这些就是很好的例子：如 [限购股票购买](https://www.youtube.com/watch?v=l7edU35m8OI)、[股权标准协议](https://www.youtube.com/watch?v=iphsRWQoFDI)以及 [ERC20代币购买协议](https://www.youtube.com/watch?v=iOYFcbzfPPs)。


Enterprise Ethereum Alliance has [formed a working group](https://entethalliance.org/ethereum-enterprise-alliance-legal-industry-working-group-press-release/) with many of the leading law firms and legal schools to ensure the legal industry can adapt.

为确保法律行业能够适应这些变化，企业以太坊联盟已经与许多领先的律师事务所和法学院[组成了工作组](https://entethalliance.org/ethereum-enterprise-alliance-legal-industry-working-group-press-release/)。

### 13. “For the first time, open source, peer-to-peer protocol developers can monetize their project on a protocol level” — Olaf Carlson-Wee
| 第一次，开源的点对点协议开发人员可以在协议层面通过他们的项目获利” - Olaf Carlson-Wee

For the first time we’ll be able to incentivize and monetize open source work, which will feel like adding a match to nitroglycerin in a Cambrian explosion of new blockchain technology paradigms. With new tokenized projects like [Bounties.Network](https://bounties.network/) and [Gitcoin](https://gitcoin.co/), we’re adding a cryptoeconomic layer to software engineering.

第一次，我们能够为开源开发工作人员提供物质和货币奖励。这感觉好象是在类似寒武纪大爆发的新的区块链技术
中加入硝酸甘油炸药。使用新的代币化项目，比如 [Bounties.Network](https://bounties.network/) 和 [Gitcoin](https://gitcoin.co/)，就好象我们在软件工程中加入了一个数字经济层。

### 14. [BUGS](https://www.brooklynbugs.com/) begone: smart contract audits will be a necessity in 2018 | BUGS：2018年，智能合约的审计将成为必要

For decades software engineers created code with bugs, which was somewhat inconsequential as software primarily served as a communication mechanism. As we transition to an Internet of Value with digitally tokenized assets, bugs can mean potential loss of capital. We don’t need to re-dance the [polka](https://paritytech.io/blog/security-alert.html) or revel in the [DAO-Saster](https://en.wikipedia.org/wiki/The_DAO_%28organization%29) of 2017, and 2016 respectively to agree that smart contract security audits are necessary.

Superstars like [Phil Daian](https://pdaian.com/) and [ConsenSys Diligence](https://media.consensys.net/introducing-consensys-diligence-cf38f83948c) will become the heroes of smart contract security audit and this could be one of the largest niches/job markets within the blockchain ecosystem.

几十年来，软件工程师开发的代码总会伴随着错误，当软件主要用作通信机制方面时问题还不是很大。但当我们转到
使用数字标记资产的价值互联网时，就可能就会引起潜在的资金损失。我们不能重蹈类似于[polka](https://paritytech.io/blog/security-alert.html) 或  2016、2017年的[DAO-Saster](https://en.wikipedia.org/wiki/The_DAO_%28organization%29) 的错误。智能合约的安全审计是非常有必要的。

[Phil Daian](https://pdaian.com/) 和 [ConsenSys Diligence](https://media.consensys.net/introducing-consensys-diligence-cf38f83948c) 等超级明星将成为智能合约安全审计的方面的英雄，这方面可能是区块链生态系统中存在的最大的商机和就业市场。

### 15. Don’t just regulate blockchain….regulate THROUGH the blockchain. |不仅要管理区块链...还要通过区块链进行管理。

2018 will be the year of G-to-C and G-to-G (Government to Citizen and Government to Government) — laws, regulations, treaties written in smart contracts, making it 100x cheaper and more straightforward to comply with them and 100x cheaper and easier to do appropriate oversight without having to subpoena personal and company records.

2018年将是 G-to-C (政府对公民) 和 G-to-G（政府对政府）之年 - 以智能合同书写的法律、法规、条约，
将比用原来方式便宜 100 倍，并且能够让人们更明确的遵守它们。因为没有必要传唤个人及公司，监管也将百倍地省钱和省力。

### 16. Stablecoins are coming | 稳定币即将到来

Stablecoins are the basis of financial instruments for hedging and derivatives that will be necessary for this [wild-west](https://www.coindesk.com/coindesk-most-influential-2017-5-joe-lubin/) industry to cross the chasm to safe and more easily used financial products. [Maker DAO](https://makerdao.com/), [VariabL](https://variabl.io/), and [Basecoin](http://www.getbasecoin.com/) are attempting this from the startup eco-system, but I think this is a great space for an enterprise banking incumbent to provide value, liquidity, and validity to the digital asset ecosystem.

I predict we’ll see a bulge bracket bank blockchain-based stablecoin in 2018 if they can get it through compliance.

稳定币是对冲和金融衍生工具的基础，是这个粗放狂野的产业跨越鸿沟成为安全、更容易使用的金融产品的必要条件。[Maker DAO](https://makerdao.com/), [VariabL](https://variabl.io/), 和 [Basecoin](http://www.getbasecoin.com/) 正在试图从这个创业生态系统解决这个问题，但我认为这是一个为数字资产生态系统提供价值、流动性和有效性的企业银行的重要空间。

我预计，如果他们能通过合规审核，2018 年我们将看到一个由投资银行集团发行的基于区块链的稳定币。

### 17. Tangoing with Contango | 将与期货结合在一起跳探戈舞

After witnessing the first bitcoin futures products on regulated U.S. exchanges that are cash-settled in 2017, I foresee the market will evolve to physically settled offerings to avoid [banging the close](https://www.wsj.com/articles/bitcoin-futures-manipulation-101-how-banging-the-close-works-1513425600) to manipulate futures. Moreover, we’ll see other digital asset derivatives, such as ether.

These derivative contracts will provide forward pricing curves that are necessary to the genesis and evolution of digital asset exchange traded funds.

在见证了2017年在美国交易所上市的第一批比特币期货产品之后，我预计市场将会演变为实物结算，以避免通过[操纵收盘价](https://www.wsj.com/articles/bitcoin-futures-manipulation-101-how-banging-the-close-works-1513425600)来操纵期货。此外，我们将看到除比特币外其他的数字资产衍生品，如以太。

这些衍生合约将提供数字资产交易所基金的产生和发展必要的远期定价曲线。

### 18. The total market cap of blockchain-based digital assets will exceed $2 trillion U.S. dollars by January 1, 2019. | 截至2019年1月1日，基于区块链的数字资产总市值将超过2万亿美元。

“New Car, Caviar, Four Star Daydream” — Pink Floyd

“新车，鱼子酱，四星白日梦” - Pink Floyd

The price of ether will exceed $2,000 in 2018. Ether will continue to outperform bitcoin, and the total market cap of ether will exceed that of bitcoin in 2018. Bitcoin’s governance issues, reluctance to evolve, and extremely high fees could lead it to its demise. Bitcoin Cash has a serious chance of eclipsing Bitcoin. The market cap of Filecoin will exceed that of bitcoin by 2023.

There will be a crypto-winter, though not in ’18, as the industry is in the spring of its youth.

以太的价格将在2018年超过2000美元。以太将继续超越比特币，以太的总市值将在2018年超过比特币。比特币的治理问题、不思发展问题以及极高的交易费都可能导致其死亡。比特币现金有极大的机会超过比特币。Filecoin 的市值将在2023年超过比特币。

加密货币市场的冬天肯定会来，但是当然不会是在18年，因为这个行业正处于青春期的春天。

Interesting times,
AK
(@ConsenSysAndrew)

一个有趣的时代，
AK
(@ConsenSysAndrew)

Andrew is a co-founder of ConsenSys Capital, the financial services offering constellation at ConsenSys including ConsenSys Ventures, Token Foundry, and ConsenSys Capital Asset Management. Previously, Andrew served as head of global business development of ConsenSys and co-founded ConsenSys Enterprise, catalysed Enterprise Ethereum Alliance, and co-developed the Microsoft Ethereum global blockchain offering.

Andrew 是 ConsenSys Capital 的联合创始人，ConsenSys Ventures，Token Foundry 和 ConsenSys Capital Asset Management 等 ConsenSys 的金融服务提供商。此前，Andrew 曾担任 ConsenSys 全球业务发展主管，并联合创立了 ConsenSys Enterprise，促成以太坊企业联盟，共同开发了 Microsoft 以太全球区块链服务。


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
