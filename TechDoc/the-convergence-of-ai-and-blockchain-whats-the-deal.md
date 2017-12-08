## The convergence of AI and Blockchain: what’s the deal? | 人工智能与区块链的融合

> 本文翻译自：https://hackernoon.com/the-convergence-of-ai-and-blockchain-whats-the-deal-60c618e3accc

> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [鱼](https://github.com/oscnet)

> 翻译时间：2017-12-5

> 本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。

**Why a decentralized intelligence may affect our future**

**为什么去中心化的人工智能可能会影响我们的未来**

![](https://cdn-images-1.medium.com/max/2000/1*xJ9uihFO6wBW5RfyEVbuEQ.jpeg)
Image Credit: [Zapp2Photo/Shutterstock](https://www.shutterstock.com/gallery-4342153p1.html?utm_source=datafloq&utm_medium=ref&utm_campaign=datafloq) | 图片来源：[Zapp2Photo / Shutterstock](https://www.shutterstock.com/gallery-4342153p1.html?utm_source=datafloq&utm_medium=ref&utm_campaign=datafloq)

It is undeniable that AI and blockchain are two of the major technologies that are catalyzing the pace of innovation and introducing radical shifts in every industry. Each technology has its own degree of technical complexity as well as business implications but the joint use of the two may be able to redesign the entire technological (and human) paradigm from scratch.

This article wants to give a flavor of the potentialities realized at the intersection of AI and Blockchain and discuss standard definitions, challenges, and benefits of this alliance, as well as about some interesting player in this space.

不可否认，人工智能（AI）和区块链是促进创新步伐的两大主要技术，它们使得每个行业产生了根本性的变化。两种技术都有自己的技术复杂度及商业意义，但是将两者结合起来使用，则可能将重构整个技术范式（和人类范式）。

本文将介绍人工智能和区块链实现交集后展示的潜力，并讨论这个同盟的标准定义，存在的挑战和好处，以及给大家介绍一下这个领域的一些有趣的玩家。

### I. Setting the stage | 设置舞台

![](https://cdn-images-1.medium.com/max/1600/1*0DmlnC7dvdgIHLD7zP8ddg.png)
Image Credit: [4zevar/Shutterstock](https://www.shutterstock.com/g/4zevar) | 图片来源：[4zevar / Shutterstock](https://www.shutterstock.com/g/4zevar)

I have been talking and writing about AI since a while now, so I will not waste any time defining what it is and what is not (if you want to know more about it, you can check [my explanation](https://medium.com/@Francesco_AI/artificial-intelligence-what-it-is-and-why-now-4e4431942623) or a [brief history of AI](https://medium.com/@Francesco_AI/a-brief-history-of-ai-baf0f362f5d6)).


However, I never touched upon blockchain and cryptocurrencies so far, so I will dedicate this first block to describe what it is and how it works.

A blockchain is a **secure distributed immutable database shared by all parties in a distributed network** where transaction data can be recorded (either on-chain for basic information or off-chain in case of extra attachments) and easily audited.

我进行有关人工智能的谈论和写作已经有一阵子了，因此我不想再浪费时间来定义它是什么，或者它不是什么（如果你想了解更多的信息，你可以点击查看[我的解释](https://medium.com/@Francesco_AI/artificial-intelligence-what-it-is-and-why-now-4e4431942623)或[人工智能简史](https://medium.com/@Francesco_AI/a-brief-history-of-ai-baf0f362f5d6)） 。

不过，因为我以前没有接触过有关区块链和加密货币，所以我会首先说明一下它是什么以及它是如何工作的。

区块链是**分布式网络中由各方共享安全的分布式不可变数据库**，交易数据可以被记录在上面（在区块链上保存基本信息，或者在链下保存附加信息或附件），并且它非常容易审计。


  >#### A blockchain is a secure distributed immutable database shared by all parties in a distributed network

  >#### 区块链是分布式网络中由各方共享的安全的分布式不可变数据库

Put simply (with Bank of England’s words), the blockchain is “a technology that allows people who don’t know each other to trust a shared record of events”.


The data are stored in rigid structures called **blocks**, which are connected to each other in a **chain** through a hash (each block also includes a timestamp and a link to the previous block via its hash). The blocks have a header, which includes metadata, and a content, which includes the real transaction data. Since every block is connected to the previous one, as the number of participants and blocks grow, it is extremely hard to modify any information without having the network consensus.

The network can validate the transaction through different mechanisms, but mainly through either a “proof-of-work” or a “proof-of-stake”. A **proof-of-work** (Nakamoto, 2008) asks the participants (called “miners”) to solve complex mathematical problems in order to add a block, which in turn require a ton of energy and hardware capacity to be decoded. A **proof-of-stake** (Vasin, 2014) instead tries to solve this energy efficiency issue attributing (roughly) more mining power to participants who own more coins (there are many variations of it and some skepticism around its famous “nothing at stake” problem — see [Buterin’s blog post](https://blog.ethereum.org/2014/11/25/proof-stake-learned-love-weak-subjectivity/) to know more on this).

简而言之（用英格兰银行的话来说），区块链就是“一种让不相识的人相互信任其数据记录的技术”。

数据存储在被称为**块**的固定结构中，块通过哈希值相互连接成**链**（在每个块中还包括时间戳和链接到前一个块的哈希）。这些块的头部包含元数据，内容部分由真实交易数据组成。由于每个区块都与前一个区块相连，随着参与人数和区块数量的增加，在没有网络共识的情况下修改任何信息是非常困难的。

网络可以通过不同的机制来验证交易，但主要是通过"工作量证明"或"权益证明"。**工作量证明**（中本聪，2008）要求参与者（被称为“矿工”）通过解决复杂的数学问题来增加一个块，这个数学问题需要巨大的能源和硬件能力来解码。**权益证明**（Vasin，2014）则试图通过把更多的的算力给予拥有更多代币的参与者来解决这一能源效率的问题（它们有很多不同之处，并对其著名的"无利害关系"问题有点怀疑 - 请参阅[Buterin的博客文章](https://blog.ethereum.org/2014/11/25/proof-stake-learned-love-weak-subjectivity/)以了解更多信息）。

Additional mechanisms are the Byzantine-fault-tolerant algorithm (Castro and Liskov, 2002), the Quorum slicing (Mazieres, 2016), as well as variations of the Proof-of-stake (Mingxiao et al., 2017), but we will not get into those now.


The final characteristic that needs to be explained is the category of blockchain based on the different network access permission, i.e., whether it is free for anyone to view it (**permissionless vs permissioned**) or to participate in the consensus formation (**public vs private**). In the former case, anyone can access and read or write data from the ledger, while in the latter one predetermined participants have the power to join the network (and of course only in the public permissionless case a reward structure for miners has been designed).

其它的机制还有拜占庭容错算法（Castro和Liskov，2002），Quorum 分片（Mazieres，2016）以及改进的权益证明（Mingxiao等，2017），但是现在我们将不讨论这些。

最后一个需要说明的是根据其不同的网络访问权限，我们把区块链分成几个类别，即是否任何人都可以免费查看（**允许或不允许**）或者参与共识形成（**公共的还是私有的**）。在前一种情况下，任何人都可以访问和读取或写入帐本中的数据，而在后一种情况下，预先确定的参与者有权加入网络（当然，只有在公共许可的情况下，才设计出针对矿工的激励结构）。

It should be clear by now the intrinsic power of this technology, which is not simply a disruptive innovation but rather a foundational technology that aims to “change the scope of intermediation” (Catalini and Gans, 2017). Distributed ledger technologies will indeed reduce both the costs of verification and networking, influencing then the market structure and eventually allowing the creation of new marketplaces. Iansiti and Lakhani (2017) also drew a brilliant parallel between blockchain and TCP/IP in a recent work (which I highly recommend), showing how blockchain is slowly going through the four phases that identify previous foundational technologies such as the TCP/IP, i.e., single-use, localized use, substitution, and transformation. As they explained, the “novelty” of such a technology makes it harder for people to understand the solution domain, while its “complexity” requires a larger institutional change to foster an easy adoption.


However, it is also true that the blockchain is shifting the traditional business models distributing value in an opposite way with respect to previous stacks: if it made more sense to invest in applications rather than protocol technologies fifteen years ago, in a blockchain world the value is concentrated in the shared protocol layer and only marginally at the application level (see the [“**Fat Protocol**” theory](http://www.usv.com/blog/fat-protocols) by Joel Monegro).

目前我们已经清楚这种技术的内在力量，这不仅仅是一个破坏性的创新，更是一个旨在 “改变仲裁范围” 的基础性技术（Catalini and Gans，2017）。分布式账本技术的确会降低验证和联网的成本，影响当时的市场结构，并最终允许创建新的市场。Iansiti和Lakhani（2017）在最近的一个工作（我强烈推荐）中也聪明地提出了区块链和 TCP/IP 之间的一些相似之处，如同先前的基本技术如 TCP/IP, 区块链是如何缓慢地经历了四个阶段，即单次使用，本地化使用，替代和转换。正如他们说明的那样，这种技术的“新颖性”使得人们很难理解它的解决方案领域，而其“复杂性”则需要更大的制度变革从而促进其被轻松采用。

不管怎样，区块链正在改变传统商业模式的分配价值，在十五年前投资于应用程序而不是协议技术上是正确合理的，在区块链世界中，与之前的方式正好相反：价值集中在共享的协议层，应用程序层面则被边缘化（参见Joel Monegro 的[“胖协议”理论](http://www.usv.com/blog/fat-protocols)）。

> #### It’s a stack with “fat” protocols and “thin” applications (Joel Monegro).
> #### 这是一个与“胖”协议和“瘦”应用程序的组合（Joel Monegro）。

To conclude this introductory section, I will just mention on the fly the possibility for the blockchain to not simply allow for transactions but also the possibility to create **(smart) contracts** that are triggered by specific events and threshold and that are traceable and auditable without effort.

为了总结这个介绍性的部分，我还要简单的提到一点：区块链不仅仅允许交易，还可以创建由特定事件和阈值触发并且可以不费力地追踪和审计的**（智能）合约**。

#### Bonus Paragraph: Initial Coin Offerings (ICOs) | 奖金段落：首次公开发售数字代币（ICO）

A big hype is nowadays surrounding this new phenomenon of the Initial Coin Offerings (ICOs). Even if many people are pouring money into that because of its resemblance to the most common (and valuable) Initial Public Offerings (IPOs), an ICO is nothing more than a **token sale**, where a token is the smallest functional unit of a specific network (or application).


ICOs experts (if any) will forgive my approximate definition, but an ICO is a hybrid concept that has elements of a **shares allocation**, a **pre-sales/crowdfunding** campaign, and a **currency** with a limited power and application’s domain.

现在一个大炒作正围绕着首次公开发售数字代币（ICO）的新现象而进行。很多人在此投入大量资金，因为它跟常见的（有价值的）首次公开发行（IPO）很相似。但ICO只不过是一种**代币销售**，代币是特定网络（或应用）中的最小的功能单元。

ICO专家（如果有的话）请原谅我的这个近似的定义，ICO是一个混合概念，它具有**股权分配**、**预售/众筹**等功能活动、以及具有有限权力和应用领域的**货币**。

It is definitely an interesting innovation that introduces new unregulated ways to raise capitals, but it also poses several issues to an unprepared community. I am happy to receive feedback on this, but I would distill the key points of an ICO evaluation in what follows:

这绝对是一个有趣的创新，它引入了新的不受管制的筹集资金的方式，但也给毫无准备的社区带来了一些问题。我很高兴收到这方面的反馈意见，下面是我提炼的有关ICO评估的关键点：

* a token has an additional utility with respect to the exchange of value and companies selling token with the **only goal of raising capital are sending a bad signal** to the market. Tokens are needed to create a users’ base and to incentivize stakeholders to participate in the ecosystem at the earliest stage. **A good white paper is not enough**;

* Be wary of token sales that are **uncapped**;

* Be wary of token sales that have **no time limit**;

* Be wary of token sales that do not clearly state the (present and future) **number** as well as the **value of the token** (it could sound absurd, but you may be surprised of how non-transparent an ICO can look like).


* 代币在价值交换方面具有额外的功用，出售代币的公司的**唯一目标是筹集资金，这向市场发出了不好的信号**。代币销售有利于创建用户基础，并激励利益相关者尽早参与生态系统。**但是仅有一个好的白皮书是不够的**。

* 警惕**不封顶**的代币销售;

* 警惕**没有时间限制**的代币销售;

* 警惕（现在和未来）代币的**发行数量**和**代币价值**不清楚的代币销售（这听起来可能荒谬，但你可能会惊讶于有些ICO是多么地不透明）。

### II. How AI can change Blockchain | 人工智能如何改变区块链

![](https://cdn-images-1.medium.com/max/1600/1*X7Qoyy_VLe9DJ90qqJi2qg.png)

Image Credit: [Phonlamai Photo/Shutterstock](https://www.shutterstock.com/g/PhonlamaiPhoto) | 图片来源：[Phonlamai Photo/Shutterstock](https://www.shutterstock.com/g/PhonlamaiPhoto)


Although extremely powerful, a blockchain has its own limitations as well. Some of them are technology-related while others come from the old-minded culture inherited from the financial services sector, but all of them can be affected by AI in a way or another:


区块链虽然非常强大，但也有其自身的局限性。 其中有些局限性是与技术有关的，有些则是由于金融服务界遗留下来的古老思想文化，但这些都可能受到人工智能的某种影响：

* **Energy consumption**: mining is an incredibly hard task that requires a ton of energy (and then money) to be completed (O’Dwyer and David Malone, 2014). AI has already proven to be very efficient in [optimizing energy consumption](https://blog.google/topics/environment/deepmind-ai-reduces-energy-used-for/), so I believe similar results can be achieved for the blockchain as well. This would probably also result in lower investments in mining hardware;

* **Scalability**: the blockchain is growing at a steady pace of 1MB every 10 minutes and it already adds up to 85GB. Satoshi (2008) first mentioned “blockchain pruning” (i.e., deleting unnecessary data about fully spent transactions in order to not hold the entire blockchain on a single laptop) as a possible solution but AI can introduce new decentralized learning systems such as **federated learning**, for example, or new data sharding techniques to make the system more efficient;

* **Security**: even if the blockchain is almost impossible to hack, its further layers and applications are not so secure (e.g., the DAO, Mt Gox, Bitfinex, etc.). The incredible progress made by machine learning in the last two years makes AI a fantastic ally for the blockchain to guarantee a secure applications deployment, especially given the fixed structure of the system;

* **能源消耗**：采矿是一项非常艰巨的任务，需要耗费大量的能源（然后是资金）才能完成（O'Dwyer和David Malone，2014）。AI 已经证明在[优化能源消耗](https://blog.google/topics/environment/deepmind-ai-reduces-energy-used-for/)方面非常高效，所以我相信区块链也可以实现类似的结果。这可能也会导致对采矿硬件的投资减少;

* **可扩展性**：区块链容量以每10分钟增加1MB的速度稳步增长，现在已经达到了85GB。中本聪（2008）首先提到”区块链修剪”（即删除不必要的，完全花费的交易的数据，以便可以把整个区块链数据放在一台笔记本电脑上）作为一种可能的解决方案，但是人工智能可以引入新的去中心化学习系统如**联合学习**（Federated Learning，一种分布式机器学习方法，由谷歌推出。译者注），或者使用新的数据分片技术来提高系统的效率;

* **安全性**：虽然区块链几乎不可能破解，但是它的上层协议和应用程序就不是那么的安全（如 DAO，Mt Gox，Bitfinex等事件）。机器学习在过去两年中所取得的惊人进展，使得AI成为区块链的绝佳盟友，以保证应用程序的安全部署，尤其是考虑到系统的固定结构;

* **Privacy**: the privacy issue of owning personal data raises regulatory and strategic concerns for competitive advantages (Unicredit, 2016). Homomorphic encryption (performing operations directly on encrypted data), the **Enigma project** (Zyskind et al., 2015) or the **Zerocash project** (Sasson et al., 2014), are definitely potential solutions, but I see this problem as closely connected to the previous two, i.e., scalability and security, and I think they will go pari passu;

* **Efficiency**: Deloitte (2016) estimated the total running costs associated with validating and sharing transactions on the blockchain to be as much as $600 million a year. An intelligent system might be eventually able to compute on the fly the likelihood for specific nodes to be the first performing a certain task, giving the possibility to other miners to shut down their efforts for that specific transaction and cut down the total costs. Furthermore, even if some structural constraints are present, a better efficiency and a lower energy consumption may reduce the **network latency** allowing then faster transactions;

* **隐私**：对拥有个人数据所引起的隐私问题，引发了对竞争优势的监管和战略考虑（Unicredit，2016）。同态加密（直接对加密数据执行操作），** Enigma 项目**（ Zyskind 等，2015）或 **Zerocash 项目**（Sasson等，2014）绝对是潜在的解决方案，但我认为这个问题与前两个问题，即可扩展性和安全性紧密相连，我认为它们会同步地发展;

* 效率：德勤（2016）估计，与验证和分享区块链交易相关的总运营成本每年高达6亿美元。一个智能系统可能最终能够快速计算出，特定节点成为第一个执行某项任务的可能性，使得其他矿工放弃针对该特定交易的工作成为可能从而降低总成本。此外，即使存在一些结构约束，更好的效率和更低的能量消耗可以减少**网络延迟**，从而得到更快的事务处理能力;

* **Hardware**: miners (and not necessarily companies but also individuals) poured an incredible amount of money into specialized hardware components. Since energy consumption has always been a key issue, many solutions have been proposed and much more will be introduced in the future. As soon as the system becomes more efficient, some piece of hardware might be converted (sometimes partially) for neural nets use (the mining colossus Bitmain is doing exactly this);

* **Lack of talent**: this is leap of faith, but in the same way we are trying to automate data science itself (unsuccessfully, to my current knowledge), I don’t see why we couldn’t create virtual agents that can create new ledgers themselves (and even interact on it and maintain it);

* **Data gates**: in a future where all our data will be available on a blockchain and companies will be able to directly buy them from us, we will need help to grant access, track data usage, and generally make sense of what happens to our personal information at a computer speed. This is a job for (intelligent) machines.

* **硬件**：矿工（不一定是公司，也包括个人）将大量资金投入到专门的挖矿硬件中。由于能源消耗一直是一个关键问题，因此提出了许多解决方案，未来还将引入更多的解决方案。一旦系统变得更有效率，一些硬件可能会被转换（有时是部分的）用于神经网络的使用（矿业巨头比特大陆正在做这个事情）。

* **缺乏人才**：这是信念的飞跃，但同样我们正在努力实现数据科学本身的自动化（尚末成功，以我目前的了解），我不明白为什么我们不能创建虚拟代理，通过它来创建新的账薄（甚至能跟它互动和维护它）;

* **数据门**：未来我们的所有数据都将在区块链上提供，而公司将能够直接从我们这里购买这些数据，我们将需要帮助来授予访问权限，跟踪数据使用情况，而且通常能够以计算机速度理解我们的个人信息会发生什么情况。这就是（智能）机器的工作。

### III. How Blockchain can change AI | 区块链如何改变AI

![](https://cdn-images-1.medium.com/max/1600/1*gByP8WZVK_zRxik_hGpZDQ.png)
https://datafloq.com/read/how-cognitive-computing-can-revolutionize-business/3317

In the previous section, we quickly touched upon the effects that AI might eventually have on the blockchain. Now instead, we will make the opposite exercise understanding what impact can the blockchain have on the development of machine learning systems. More in details, blockchain could:

在之前的章节中，我们很快地谈到了人工智能最终会对区块链造成的影响。现在，相反的我们将会了解区块链对机器学习系统的发展有何影响，更详细地说，区块链可以：

* **Help AI explaining itself (and making us believe it)**: the AI black-box suffers from an explainability problem. Having a clear audit trail can not only improve the trustworthiness of the data as well as of the models but also provide a clear route to trace back the machine decision process;

* **Increase AI effectiveness**: a secure data sharing means more data (and more training data), and then better models, better actions, better results…and better new data. Network effect is all that matter at the end of the day;

* **帮助 AI 解释自己（并让我们相信它）**：AI 黑盒遭受可解释性问题。清晰的审计跟踪不仅可以提高数据的可信性，还可以提高模型的可信度，也为追溯机器的决策过程提供了一条清晰的途径。

* **提高人工智能的有效性**：一个安全的数据共享意味着更多的数据（和更多的训练数据），然后更好的模型，更好的行动，更好的结果...和更好的新数据。在一天结束时，网络效应才是最重要的。

* **Lower the market barriers to entry**: let’s go step by step. Blockchain technologies can secure your data. So why won’t you store all your data privately and maybe sell it? Well, you probably will. So first of all, blockchain will foster the **creation of cleaner and more organized personal data**. Second, it will allow the emergence of **new marketplaces**: a **data marketplace** (low-hanging fruit); a **models marketplace** (much more interesting); and finally even an **AI marketplace** (see what [Ben Goertzel](https://medium.com/@bengoertzel) is trying to do with [SingularityNET](https://singularitynet.io/)). Hence, easy data-sharing and new marketplaces, jointly with blockchain data verification, will provide a more fluid integration that lowers the barrier to entry for smaller players and shrinks the competitive advantage of tech giants. In the effort of lowering the barriers to entry, we are then actually solving two problems, i.e., providing a **wider data access** and a more efficient **data monetization mechanism**;

* **降低进入市场的障碍**：让我们一步一步来。区块链技术可以保护您的数据。那么为什么你不能私下存储所有的数据，以后也许还能将它出售？是的，你有可能想这样做。首先，区块链将促进**创建更清洁，更有组织的个人数据**。其次，它将允许出现**新的市场**：一个**数据市场**（低挂果实）; 一个**模型市场**（更有趣）; 最后甚至是一个**AI市场**（看看[Ben Goertzel](https://medium.com/@bengoertzel)正用[SingularityNET](https://singularitynet.io/)来做什么）。因此，简单的数据共享和新的市场以及区块链数据验证将提供更加流畅的整合，从而降低小企业进入的门槛，缩小高科技巨头的竞争优势。为了降低进入门槛，我们实际上解决了两个问题：提供**更广泛的数据访问**和更高效的**数据货币化机制**;

* **Increase artificial trust**: as soon as part of our tasks will be managed by autonomous virtual agents, having a clear audit trail will help **bots to trust each other** (and us to trust them). It will also eventually increase every **machine-to-machine interaction** (Outlier Ventures, 2017) and transaction providing a secure way to share data and coordinate decisions, as well as a robust mechanism to reach a quorum (extremely relevant for swarm robotics and multiple agents scenarios). [Rob May](https://medium.com/@robmay) expressed a similar concept in one of his last newsletters (that I highly recommend — [you should definitely subscribe](https://inside.com/campaigns/inside-ai-2017-09-03-3149/sections/commentary-17321));

* **Reduce catastrophic risks scenario**: an AI coded in a DAO with specific smart contracts will be able to only perform those actions, and nothing more (it will have a limited action space then).

* **增加人为信任**：只要部分我们的工作由自主虚拟代理管理，拥有清晰的审计跟踪将有助于**机器人互相信任**（我们相信他们）。它还将最终增加每个**机器与机器的交互**（Outlier Ventures，2017），增加提供了一个安全的方式来共享数据和协调决策地交易，以及一个强大的机制达到法定人数（对群体机器人和多个代理情景非常有意义）。[罗布·梅（Rob May）](https://medium.com/@robmay)在他的最近一篇时事通讯中表达了类似的概念（我强烈建议 -  你一定要[订阅](https://inside.com/campaigns/inside-ai-2017-09-03-3149/sections/commentary-17321)）。

* **减少灾难性风险情景**：在DAO中使用特定的智能合约编码的AI只能执行这些操作，而不会再有任何其他操作（因此它将具有有限的操作空间）。

In spite of all the benefits that AI will receive from an interaction with blockchain technologies, I do have one big question with no answer whatsoever.

> *AI was born as in an open-source environment where data was the real moat. With this data democratization (and open-source software) how can we be sure that AI will prosper and will keep being developed? What would be the new moat? My only guess at the moment? Talent…*

尽管AI可以从与区块链技术的互动中获得所有的好处，但我确实有一个大问题，没有任何答案。

> *人工智能诞生于开源环境中，这其中数据才是真正重要的护城河。当这个数据民主化（和开源软件），我们怎么能确定AI会繁荣，并将继续发展？新的护城河会是什么？我现在唯一的猜测是？天赋…*


### IV. Decentralized Intelligent Companies | 去中心化的智能公司

![](https://cdn-images-1.medium.com/max/1600/1*PFg1uE4iLrUoWLBHLdfCEw.png)
Image Credit: [Wit Olszewski/Shutterstock](https://www.shutterstock.com/g/witolszewski) | 图片来源：[Wit Olszewski / Shutterstock](https://www.shutterstock.com/g/witolszewski)

There are plenty of landscapes of blockchain and cryptocurrencies startups out there. I am anyway only interested in those companies working at the intersection (or the convergence, as someone calls it) of AI and blockchain, which apparently are not that many. They are mainly concentrated in San Francisco area and London, but there are examples in New York, Australia, China, as well as some European countries.

They are indeed so few of them that is quite hard to classify them into clusters. I usually like to try to understand the underlying patterns and the type of impact/application certain groups of companies are having in the industry, but in this case is extremely difficult given the low number of data points so I will simply categorize them as follows:

那里有大量的区块链和加密货币初创公司的风景。但我只对那些结合（或者说人们称之为融合）了AI和区块链的公司感兴趣，这显然并不多。他们主要集中在旧金山地区和伦敦，纽约，澳大利亚，中国以及一些欧洲国家也有一些。

他们确实很少，很难将它们分类。我通常喜欢尝试了解某些公司在行业中具有的底层模式和影响/应用类型，但在这种情况下，由于数据点数量较少，所以我将简单地将它们分类如下：

* **Decentralized Intelligence**: [TraneAI](http://www.trane.ai/) (training AI in a decentralized way); [Neureal](http://neureal.net/) (peer-to-peer AI supercomputing); [SingularityNET](https://singularitynet.io/) (AI marketplace); [Neuromation](https://neuromation.io/en/) (synthetic datasets generation and algorithm training platform); [AI Blockchain](https://ai-blockchain.com/) (multi-application intelligence); [BurstIQ](https://www.burstiq.com/) (healthcare data marketplace); [AtMatrix](https://www.atmatrix.org/) (decentralized bots); [OpenMined](https://openmined.org/) project (data marketplace to train machine learning locally);

* **Conversational Platform**: [Green Running](https://www.greenrunning.com/) (home energy virtual assistant); [Talla](https://talla.com/) (chatbot); [doc.ai](https://doc.ai/) (quantified biology and healthcare insights);

* **去中心化的智能**：[TraneAI](http://www.trane.ai/)（以去中心化的方式培训 AI ）; [Neureal](http://neureal.net/))（点对点AI超级计算）; [SingularityNET](https://singularitynet.io/)（AI 市场）; [Neuromation](https://neuromation.io/en/)（合成数据集生成和算法培训平台）;
[AI Blockchain](https://ai-blockchain.com/)（多应用智能）; [BurstIQ](https://www.burstiq.com/)（医疗数据市场）; [AtMatrix](https://www.atmatrix.org/)（分散机器人）;
[OpenMined](https://openmined.org/) 项目（在本地培训机器学习的数据市场）;

* **会话平台**：[Green Running](https://www.greenrunning.com/)（家庭能源虚拟助手）;
[Talla](https://talla.com/)（聊天机器人）;
[doc.ai](https://doc.ai/)（量化的生物学和医疗保健）;

* **Prediction Platform**: [Augur](https://augur.net/) (collective intelligence); [Sharpe Capital](https://sharpe.capital/) (crowd-source sentiment predictions);

* **Intellectual Property**: [Loci.io](https://locipro.com/) (IP discovery and mining);

* **Data provenance**: KapeIQ (fraud detection on healthcare entities); [Data Quarka](http://dataquarks.com/) (facts checking); [Priops](http://priops.com/) (data compliance); [Signzy](https://signzy.com/) (KYC)

* **预测平台**：[Augur](https://augur.net/)（集体智慧）;
[Sharpe Capital](https://sharpe.capital/) （人群情绪预测）;

* **知识产权**：[Loci.io](https://locipro.com/)（IP发现和挖掘）;

* **数据跟踪**：KapeIQ（医疗机构欺诈检测）;
[Data Quarka](http://dataquarks.com/)（事实核查）;
[Priops](http://priops.com/)（数据符合性）;
[Signzy](https://signzy.com/)（KYC）

* **Trading**: [Euklid](https://www.euklid.com/) (bitcoin investments); [EthVentures](https://ethventures.io/) (investments on digital tokens). For other (theoretical) applications in finance, see Lipton (2017);

* **Insurance**: [Mutual.life](https://mutual.life/en/) (P2P insurance), [Inari](http://www.inari.io/) (general);

* **Miscellaneous**: [Social Coin](https://thesocialcoin.com/?lang=en) (citizens’ reward systems); [HealthyTail](http://healthytail.org/) (pet analytics); [Crowdz](https://www.crowdz.io/) (e-commerce); [DeepSee](https://www.deepsee.io/) (media platform); [ChainMind](http://www.chainmind.com/) (cybersecurity).

* **交易**：[Euklid](https://www.euklid.com/)（比特币投资）;
[EthVentures](https://ethventures.io/)（数字代币投资）。对于金融领域的其他（理论）应用，见Lipton（2017）;

* **保险**：[Mutual.life](https://mutual.life/en/)（P2P保险），
[Inari](http://www.inari.io/)（普通）;

* **其它**：[Social Coin](https://thesocialcoin.com/?lang=en)（公民奖励制度）;
 [HealthyTail](http://healthytail.org/)（宠物分析）;
[Crowdz](https://www.crowdz.io/)（电子商务）;
[DeepSee](https://www.deepsee.io/)（媒体平台）;
[ChainMind](http://www.chainmind.com/)（网络安全）。

A few general comments:

几个一般的评论：

* It looks interesting that many AI-blockchain companies have **larger advisory board than teams**. It might be an early sign that the convergence is not fully realized yet and there are more things we don’t understand that those ones we know;

* I am personally very excited to see the development of the first category (**decentralized intelligence**) but I also see a huge development in **conversational** and **prediction platforms** as well as **intellectual property**. I grouped other examples under “miscellaneous” because I don’t think at this stage they represent a specific category but rather only single attempt to match AI and blockchain;

* 看起来有趣的是，许多 AI 区块链公司拥有**比团队更大的咨询委员会**。这可能是一个早期的迹象，说明融合还没有完全实现，在这方面，我们所知有限，更多的是未知;

* 我个人非常高兴看到第一类（**去中心化的智能**）的发展，但是我也看到了**对话**和**预测平台**以及**知识产权**方面的巨大发展。我把其他的例子归类为“其它”，因为我不认为在这个阶段它们代表了一个特定的类别，而只是一次匹配AI和区块链的尝试;

* **Those companies are incredibly hard to evaluate**. The websites are often cryptic enough to not really understand what they do and how (a bit paradoxical if you want to buy the blockchain transparency paradigm) and technology requires a high tech-education to be fully assessed. Cutting through the hype is a demanding task and this makes it very easy to be fooled. But let me give you a concrete example: **ever heard of Magos AI?** In the effort of researching companies for this post, I found myself reading several articles on this forecasting blockchain AI-driven platform company (W[ired](https://www.wired.it/economia/start-up/2017/10/04/magos-la-startup-vuole-prevedere-futuro-ai-blockchain/), [Prnewswire](https://www.prnewswire.com/news-releases/magos-ai-a-neural-network-based-forecasting-platform-gathers-700000-on-its-ongoing-ico-300526569.html), etc.), which just did an ICO for over half a million dollars and that made great promises on its deliverables. The website didn’t work — weird, if you consider that they need to share material/information on the ICOs. But you know, it might happen. I made then an extra effort because I read it on Wired and I was curious to know more about it. I was able to find its co-founders, which I couldn’t find eventually on Linkedin. Weird again. Well, there are people who do not like socials, fair enough, especially if you consider that until three months ago there was no proof of the company existence whatsoever. Let me look into the rest of the team. Nothing even there, and no traceable indications of their previous experiences (except for the CTO master in analytics, that I found no proof of). I tried to then dig into the technology: white papers, blue papers, yellow papers, you name it. I only found reviews of them, no original copies. Final two steps: I don’t consider myself an expert in blockchain at all, but I read, a lot. And I also believe I am fairly knowledgeable when it comes to AI and what is happening in the industry. These guys claimed they created 5 different neural nets that could achieve the same accuracy in complex different domains than Libratus (or DeepStack) reached in Poker, but I never heard of them — very weird. Well, you know what? Maybe I could write them and meet them to understand. Their address points to the AXA office in Zurich. Ah.

* **这些公司难以置信地难以评估**。他们的网站往往做得非常隐晦，不能真正理解他们正在做什么和怎么做（这跟你想购买的公开透明模式的区块链有点矛盾），而技术需要高科技教育人才的努力才能充分发挥。过份炒作是一个艰巨的任务，这使得它很容易被愚弄。但是让我给你一个具体的例子：曾经听说过 Magos AI 吗？我在为这篇文章进行研究的公司中，我发现自己阅读了关于这个预测区块链AI驱动的平台公司的几篇文章，（[Wired](https://www.wired.it/economia/start-up/2017/10/04/magos-la-startup-vuole-prevedere-futuro-ai-blockchain/), [Prnewswire](https://www.prnewswire.com/news-releases/magos-ai-a-neural-network-based-forecasting-platform-gathers-700000-on-its-ongoing-ico-300526569.html) 等），刚刚做了一个超过50万美元的ICO，并对其交付成果作出了很大的承诺。
网站不可思异地挂了，
如果你认为他们需要分享ICO的材料和信息，但是你知道，这可能会发生。我做了一个额外的努力，因为我在Wired上读过它，我很想知道更多。我能够找到它的联合创始人，我最终不能找到它的Linkedin信息。奇怪了。那么，有些人不喜欢社交活动。公平的，特别是如果你考虑到三个月前，没有任何公司存在的证据。让我看看其他的团队。也没有，
也没有可追溯的迹象表明他们以前的经验（除了 CTO 有analytics技能，但我没有发现证据）。我试图深入研究这项技术：白皮书，蓝皮书，黄皮书，凡你想得起的 不管什么，我只找到他们的评论，找不到正本。
最后两个步骤：我根本不认为自己是区块链专家，但我读了很多。而且我也相信我对AI和业内正在发生的事情有相当的了解。
这些人声称他们创造了5个不同的神经网络，可以在复杂的不同领域达到与Libratus (or DeepStack)在扑克上达到的
相同的准确度。但我从来没有听说过他们 - 非常奇怪。那么，你知道什么？也许我可以写他们，并会见他们来理解。他们的地址指向了位于苏黎世的安盛办事处。

 After 5 minutes of research, I finally Google the two key words: “Magos scam”. It seems these guys took the money and disappeared. They are surely building the 6 neural net somewhere, so stay tuned.

 My point here is that exponential technologies are fantastic and can advance mankind, but as much as the benefits increase also the potential “negative convergence” increases exponentially. Stay alert.

 经过5分钟的研究，我终于在谷歌的两个关键词：“魔鬼骗局”。看来这些人拿走了钱，消失了。他们确实在某处建立了6个神经网络，敬请关注。

 我的观点是，指数技术是非常棒的，可以推动人类，但随着利益的增加，潜在的“ 负面问题 ”也会呈指数级增长。请保持警惕。


### V. Conclusion | 结论

![](https://cdn-images-1.medium.com/max/1600/1*x8NJVuyt13o92Oz7k6-BfA.png)
Image Credit: Sasun Bughdaryan/Shutterstock | 图片来源：Sasun Bughdaryan / Shutterstock

Blockchain and AI are the two extreme sides of the technology spectrum: one fostering centralized intelligence on close data platforms, the other promoting decentralized applications in an open-data environment. However, if we find an intelligent way to make them working together, the total positive externalities could be amplified in a blink.

There are of course technical and ethical implications arising from the interaction between these two powerful technologies, as for example how do we edit (or even forget) data on a blockchain? Is an [**editable blockchain**](https://www.coindesk.com/accenture-awarded-patent-editable-blockchain-tech/) the solution? And is not an AI-blockchain pushing us to become data hoarder?

Honestly, I think the only thing we can do is keep experimenting.

区块链和人工智能是技术领域的两个极端：一个使用封闭的数据平台来培养中心化的智能，另一个是在开放数据平台中推动去中心化应用。
但是，如果我们找到一个聪明的方法来使它们一起工作，总的积极的外部效应就可以在一瞬间被放大。

当然这两种强大的技术之间的交互会产生技术和伦理上的影响，例如我们如何编辑（甚至忘记）区块链上的数据？是可编辑的区块链解决方案吗？而不是AI区块链推动我们成为数据囤积者？

老实说，我认为我们唯一能做的就是不断尝试。

### References

Castro, M., Liskov, B. (2002). “Practical Byzantine Fault Tolerance and Proactive Recovery”. ACM Transactions on Computer Systems, 20(4): 398–461.

卡斯特罗，米，Liskov，B。（2002）。“实用的拜占庭容错和主动恢复”。ACM Transactions on Computer Systems， 20（4）：398-461。

Catalini, C., Gans, J. S. (2017). “Some Simple Economics of the Blockchain”. MIT Sloan School Working Paper: 5191–16.

Catalini，C.，Gans，JS（2017）。“区块链的一些简单的经济学”。麻省理工学院斯隆学院工作文件： 5191-16。

Deloitte (2016). “Blockchain Enigma. Paradox. Opportunity”. White Paper.

德勤（2016）。“区块链Enigma。悖论。机会”。白皮书。

Iansiti, M., Lakhani, K. R. (2017). “The Truth About Blockchain”. Harvard Business Review, January–February 2017: 118–127.

Iansiti，M.，Lakhani，KR（2017）。“关于区块链的真相”。哈佛商业评论，2017年1月 - 2月：118-127。

Lipton, A. (2017). “Blockchains and Distributed Ledgers in Retrospective and Perspective”. [arXiv:1703.01505](https://arxiv.org/abs/1703.01505).

Lipton，A。（2017）。“区块链和分布式账本的回顾与展望”。arXiv：1703.01505。

Mazieres, D. (2016). “[The stellar consensus protocol: A federated model for internet-level consensus](https://www.stellar.org/papers/stellar-consensus-protocol.pdf)”. White Paper.

Mazieres，D.（2016）。“ 恒星共识协议：互联网水平共识的联合模型 ”。白皮书。

Mingxiao, D., Xiaofeng, M., Zhe, Z., Xiangwei, W., Qijun, C. (2017). “A Review on Consensus Algorithm of Blockchain”. 2017 IEEE International Conference on Systems, Man, and Cybernetics (SMC) Banff Center, Banff, Canada, October 5–8, 2017

Mingxiao，D.，Xiaofeng，M.，Zhe，Z.，Xiangwei，W.，Qijun，C。（2017）。“区块链共识算法综述”。2017年IEEE关于系统，人机和控制论的国际会议（SMC）加拿大班夫Banff中心，2017年10月5 - 8日


Nakamoto, S. (2008). “[Bitcoin: A Peer-to-Peer Electronic Cash System](https://bitcoin.org/bitcoin.pdf)”. White Paper.

Nakamoto，S。（2008）。“ 比特币：对等电子现金系统 ”。白皮书。

O’Dwyer, K. J., Malone, D. (2014). “Bitcoin mining and its energy footprint”. 25th IET Irish Signals & Systems Conference 2014 and 2014 China-Ireland International Conference on Information and Communications Technologies (ISSC 2014/CIICT 2014), Limerick, pp. 280–285.

O'Dwyer，KJ，Malone，D.（2014）。“比特币采矿及其能源足迹”。第25届IET爱尔兰信号与系统会议2014年和2014年中国 - 爱尔兰信息和通信技术国际会议（ISSC 2014 / CIICT 2014），利默里克，第280-285页。


Outlier Ventures (2017). “Blockchain-Enabled Convergence”. White Paper.

Outlier Ventures（2017）。“区块链启用收敛”。白皮书。

Sasson, E. B., Chiesa, A., Garman, C., Green, M., Miers, I., Tromer, E., Virza, M. (2014). “Zerocash: Decentralized anonymous payments from bitcoin”. In Security and Privacy (SP), 2014 IEEE Symposium on, pp. 459–474.

Sasson，EB，Chiesa，A.，Garman，C.，Green，M.，Miers，I.，Tromer，E.，Virza，M.（2014）。“Zerocash：从比特币分散匿名支付”。在“ 安全与隐私”（SP），2014 IEEE Symposium on，第459-474页。

Unicredit (2016). “Blockchain Technology and Applications from a Financial Perspective”. Technical Report.

Unicredit（2016）。“从金融角度看区块链技术和应用”。技术报告。

Vasin, P. (2014). “[BlackCoin’s Proof-of-Stake Protocol v2](http://www.blackcoin.co/blackcoin-pos-protocol-v2-whitepaper.pdf)”. White Paper.

Vasin，P。（2014）。“BlackCoin的放弃证明协议v2”。白皮书。

Zyskind, G., Nathan, O., Pentland, A. (2015). “Enigma: Decentralized computation platform with guaranteed privacy”. arXiv:1506.03471.

Zyskind，G.，Nathan，O.，Pentland，A。（2015）。“Enigma：保证隐私的分散式计算平台”。arXiv：1506.03471。

keywords: Blockchain Artificial Intelligence Machine Learning Data Science Big Data


----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

鱼 区块链技术爱好者，欢迎加微信号`oscnet`交流。

本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。

版权所有，转载需完整注明以上内容。

----------------------------------------------------
