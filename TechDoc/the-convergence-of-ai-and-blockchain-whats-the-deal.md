## The convergence of AI and Blockchain: what’s the deal? | AI与区块链的融合

> 本文翻译自：https://hackernoon.com/the-convergence-of-ai-and-blockchain-whats-the-deal-60c618e3accc

> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [鱼](https://github.com/oscnet)

> 翻译时间：2017-12-5

Why a decentralized intelligence may affect our future

为什么去中心化的人工智能可能会影响我们的未来

![](https://cdn-images-1.medium.com/max/2000/1*xJ9uihFO6wBW5RfyEVbuEQ.jpeg)
Image Credit: [Zapp2Photo/Shutterstock](https://www.shutterstock.com/gallery-4342153p1.html?utm_source=datafloq&utm_medium=ref&utm_campaign=datafloq) | 图片来源：[Zapp2Photo / Shutterstock](https://www.shutterstock.com/gallery-4342153p1.html?utm_source=datafloq&utm_medium=ref&utm_campaign=datafloq)

It is undeniable that AI and blockchain are two of the major technologies that are catalyzing the pace of innovation and introducing radical shifts in every industry. Each technology has its own degree of technical complexity as well as business implications but the joint use of the two may be able to redesign the entire technological (and human) paradigm from scratch.

This article wants to give a flavor of the potentialities realized at the intersection of AI and Blockchain and discuss standard definitions, challenges, and benefits of this alliance, as well as about some interesting player in this space.

不可否认的是，AI和区块链是促进创新步伐的两大主要技术，并在每个行业引入根本的变化。每种技术都有自己的技术复杂程度以及商业意义，但是将两者结合起来使用可能会从头开始重新设计整个技术（和人类）范式。

本文将介绍AI和区块链实现交集后展示的潜力，并讨论这个同盟的标准定义，存在的挑战和好处，以及这个领域的一些有趣的玩家。

### I. Setting the stage | 设置舞台

![](https://cdn-images-1.medium.com/max/1600/1*0DmlnC7dvdgIHLD7zP8ddg.png)
Image Credit: [4zevar/Shutterstock](https://www.shutterstock.com/g/4zevar) | 图片来源：[4zevar / Shutterstock](https://www.shutterstock.com/g/4zevar)

I have been talking and writing about AI since a while now, so I will not waste any time defining what it is and what is not (if you want to know more about it, you can check [my explanation](https://medium.com/@Francesco_AI/artificial-intelligence-what-it-is-and-why-now-4e4431942623) or a [brief history of AI](https://medium.com/@Francesco_AI/a-brief-history-of-ai-baf0f362f5d6)).


However, I never touched upon blockchain and cryptocurrencies so far, so I will dedicate this first block to describe what it is and how it works.

A blockchain is a **secure distributed immutable database shared by all parties in a distributed network** where transaction data can be recorded (either on-chain for basic information or off-chain in case of extra attachments) and easily audited.

我一直进行有关 AI 的谈论和写作已经有一段时间了，所以我不会浪费任何时间来定义它是什么，它不是什么（如果你想了解更多的信息，你可以点击查看[我的解释](https://medium.com/@Francesco_AI/artificial-intelligence-what-it-is-and-why-now-4e4431942623)或[AI简史](https://medium.com/@Francesco_AI/a-brief-history-of-ai-baf0f362f5d6)） 。

不过，因为我从来没有触及过区块链和加密货币，所以我首先会描述它是什么以及它是如何工作的。

区块链是**分布式网络中由所有各方共享的安全的分布式不可变数据库**，其中交易数据可以被记录在上面（在区块链上保存基本信息，或者在链下保存附加信息及附件等），并且容易审计。


  >#### A blockchain is a secure distributed immutable database shared by all parties in a distributed network

  >#### 区块链是分布式网络中由所有各方共享的安全的分布式不可变数据库

Put simply (with Bank of England’s words), the blockchain is “a technology that allows people who don’t know each other to trust a shared record of events”.


The data are stored in rigid structures called **blocks**, which are connected to each other in a **chain** through a hash (each block also includes a timestamp and a link to the previous block via its hash). The blocks have a header, which includes metadata, and a content, which includes the real transaction data. Since every block is connected to the previous one, as the number of participants and blocks grow, it is extremely hard to modify any information without having the network consensus.

The network can validate the transaction through different mechanisms, but mainly through either a “proof-of-work” or a “proof-of-stake”. A **proof-of-work** (Nakamoto, 2008) asks the participants (called “miners”) to solve complex mathematical problems in order to add a block, which in turn require a ton of energy and hardware capacity to be decoded. A **proof-of-stake** (Vasin, 2014) instead tries to solve this energy efficiency issue attributing (roughly) more mining power to participants who own more coins (there are many variations of it and some skepticism around its famous “nothing at stake” problem — see [Buterin’s blog post](https://blog.ethereum.org/2014/11/25/proof-stake-learned-love-weak-subjectivity/) to know more on this).

简而言之（用英格兰银行的话来说），区块链就是“一种让不相识的人相互信任其事件数据记录的技术”。

数据存储在被称为**块**的固定结构中，块通过哈希值被相互连接成链（在每个块中还包括时间戳和前一个块的哈希链接）。这些块具有包括元数据的头部和包括真实交易数据的内容。由于每个区块都与前一个区块相连，随着参与人数和区块数量的增加，在没有网络共识的情况下修改任何信息是非常困难的。

网络可以通过不同的机制来验证交易，但主要是通过“ 工作证明 ”或“ 证明权益 ”。一个证明的工作（中本聪，2008）要求参与者（称为“ 矿工 ”）来解决，以增加一个块，而这又需要一吨能源和硬件能力要解码复杂的数学问题。一个验证的股权（Vasin，2014），而不是试图解决这一能源效率问题归因（大约）多采力量谁拥有更多的硬币（也有它的许多变化和各地著名的一些怀疑“参与者没有受到威胁 ”问题 - 请参阅Buterin的博客文章以了解更多信息）。


Additional mechanisms are the Byzantine-fault-tolerant algorithm (Castro and Liskov, 2002), the Quorum slicing (Mazieres, 2016), as well as variations of the Proof-of-stake (Mingxiao et al., 2017), but we will not get into those now.


The final characteristic that needs to be explained is the category of blockchain based on the different network access permission, i.e., whether it is free for anyone to view it (**permissionless vs permissioned**) or to participate in the consensus formation (**public vs private**). In the former case, anyone can access and read or write data from the ledger, while in the latter one predetermined participants have the power to join the network (and of course only in the public permissionless case a reward structure for miners has been designed).

其他的机制是拜占庭容错算法（Castro和Liskov，2002），Quorum分片（Mazieres，2016）以及股权证明（Mingxiao等，2017）的变化，但是我们将不要进入那些现在。

最后一个需要说明的特点是基于不同的网络访问权限的区块链的类别，即是否任何人都可以免费查看（允许或不允许）或者参与共识形成（公共还是私人）。在前一种情况下，任何人都可以访问和读取或写入分类帐中的数据，而在后一种情况下，预先确定的参与者有权加入网络（当然，只有在公共许可的情况下，矿工的奖励结构才被设计出来） 。


It should be clear by now the intrinsic power of this technology, which is not simply a disruptive innovation but rather a foundational technology that aims to “change the scope of intermediation” (Catalini and Gans, 2017). Distributed ledger technologies will indeed reduce both the costs of verification and networking, influencing then the market structure and eventually allowing the creation of new marketplaces. Iansiti and Lakhani (2017) also drew a brilliant parallel between blockchain and TCP/IP in a recent work (which I highly recommend), showing how blockchain is slowly going through the four phases that identify previous foundational technologies such as the TCP/IP, i.e., single-use, localized use, substitution, and transformation. As they explained, the “novelty” of such a technology makes it harder for people to understand the solution domain, while its “complexity” requires a larger institutional change to foster an easy adoption.


However, it is also true that the blockchain is shifting the traditional business models distributing value in an opposite way with respect to previous stacks: if it made more sense to invest in applications rather than protocol technologies fifteen years ago, in a blockchain world the value is concentrated in the shared protocol layer and only marginally at the application level (see the [“**Fat Protocol**” theory](http://www.usv.com/blog/fat-protocols) by Joel Monegro).

目前应该清楚这种技术的内在力量，这不仅仅是一个破坏性的创新，而是一个旨在“ 改变中介范围 ” 的基础技术（Catalini and Gans，2017）。分布式账本技术的确会降低验证和联网的成本，影响当时的市场结构，并最终允许创建新的市场。Iansiti和Lakhani（2017）在最近的一个工作（我强烈推荐）中也提出了区块链和TCP / IP之间的一个很好的平行关系，说明区块链是如何缓慢地经历了四个阶段，即识别TCP / IP等先前的基础技术，即单次使用，本地化使用，替代和转换。正如他们解释的那样，“ 新奇”这种技术使得人们难以理解解决方案领域，而其“复杂性”则需要更大的制度变革来促进轻松采用。

然而，区块链也正在改变传统商业模式的分配价值，与以前的筹码相反：如果在十五年前投资于应用程序而不是协议技术更合理，在区块链世界中，价值集中在共享的协议层，并且只在应用程序层面很小（参见Joel Monegro 的“ Fat Protocol”理论）。

> #### It’s a stack with “fat” protocols and “thin” applications (Joel Monegro).
> #### 这是一个与“胖”协议和“瘦”应用程序（Joel Monegro）的堆栈。

To conclude this introductory section, I will just mention on the fly the possibility for the blockchain to not simply allow for transactions but also the possibility to create **(smart) contracts** that are triggered by specific events and threshold and that are traceable and auditable without effort.

总结这个介绍性的部分，我只是提到区块链不仅仅允许交易的可能性，而且还可以创建由特定事件和阈值触发并且可以不费力地追踪和审计的（智能）契约。


#### Bonus Paragraph: Initial Coin Offerings (ICOs) | 奖金段落：初始硬币提供（ICO）

A big hype is nowadays surrounding this new phenomenon of the Initial Coin Offerings (ICOs). Even if many people are pouring money into that because of its resemblance to the most common (and valuable) Initial Public Offerings (IPOs), an ICO is nothing more than a **token sale**, where a token is the smallest functional unit of a specific network (or application).


ICOs experts (if any) will forgive my approximate definition, but an ICO is a hybrid concept that has elements of a **shares allocation**, a **pre-sales/crowdfunding** campaign, and a **currency** with a limited power and application’s domain.

现在围绕着这个初始硬币提供（ICO）的新现象的一个大炒作。即使很多人因为与最常见的（和有价值的）首次公开发行（IPOs）相似而投入了大量资金，ICO只不过是一种令牌销售，其中令牌是特定网络中最小的功能单元（或应用程序）。

ICO专家（如果有的话）会原谅我的近似定义，但是ICO是一个混合概念，具有股票分配，售前/众筹活动以及权力和应用程序有限的货币。

It is definitely an interesting innovation that introduces new unregulated ways to raise capitals, but it also poses several issues to an unprepared community. I am happy to receive feedback on this, but I would distill the key points of an ICO evaluation in what follows:

这绝对是一个有趣的创新，它引入了新的不受管制的筹集资金的方式，但也给一个毫无准备的社区带来了一些问题。我很高兴收到这方面的反馈意见，但是我会提炼一下ICO评估的关键点：

* a token has an additional utility with respect to the exchange of value and companies selling token with the **only goal of raising capital are sending a bad signal** to the market. Tokens are needed to create a users’ base and to incentivize stakeholders to participate in the ecosystem at the earliest stage. **A good white paper is not enough**;

* Be wary of token sales that are **uncapped**;

* Be wary of token sales that have **no time limit**;

* Be wary of token sales that do not clearly state the (present and future) **number** as well as the **value of the token** (it could sound absurd, but you may be surprised of how non-transparent an ICO can look like).


* 令牌在价值交换方面具有额外的效用，出售令牌的公司的唯一目标是筹集资金，这些都向市场发出了不好的信号。需要标记来创建用户基础，并
激励利益相关者尽早参与生态系统。一张好的白皮书是不够的。

* 警惕令牌销售额是不封顶 ;

* 警惕没有时间限制的令牌销售;

* 谨慎的销售，不清楚（现在和未来）号码以及令牌的价值（这听起来可能荒谬，但你可能会惊讶于ICO可能是不透明的）。

### II. How AI can change Blockchain | AI如何改变区块链

![](https://cdn-images-1.medium.com/max/1600/1*X7Qoyy_VLe9DJ90qqJi2qg.png)

Image Credit: [Phonlamai Photo/Shutterstock](https://www.shutterstock.com/g/PhonlamaiPhoto) | 图片来源：Phonlamai照片/ Shutterstock


Although extremely powerful, a blockchain has its own limitations as well. Some of them are technology-related while others come from the old-minded culture inherited from the financial services sector, but all of them can be affected by AI in a way or another:

一个 lthough非常强大，一个blockchain都有自己的局限性。其中有些是与技术有关的，有些则来自金融服务界遗留下来的头脑文明，但都可能受到AI的影响：

* **Energy consumption**: mining is an incredibly hard task that requires a ton of energy (and then money) to be completed (O’Dwyer and David Malone, 2014). AI has already proven to be very efficient in [optimizing energy consumption](https://blog.google/topics/environment/deepmind-ai-reduces-energy-used-for/), so I believe similar results can be achieved for the blockchain as well. This would probably also result in lower investments in mining hardware;

* **Scalability**: the blockchain is growing at a steady pace of 1MB every 10 minutes and it already adds up to 85GB. Satoshi (2008) first mentioned “blockchain pruning” (i.e., deleting unnecessary data about fully spent transactions in order to not hold the entire blockchain on a single laptop) as a possible solution but AI can introduce new decentralized learning systems such as **federated learning**, for example, or new data sharding techniques to make the system more efficient;

* **Security**: even if the blockchain is almost impossible to hack, its further layers and applications are not so secure (e.g., the DAO, Mt Gox, Bitfinex, etc.). The incredible progress made by machine learning in the last two years makes AI a fantastic ally for the blockchain to guarantee a secure applications deployment, especially given the fixed structure of the system;

* 能源消耗：开采是一项非常艰巨的任务，需要耗费大量的能源（然后是资金）才能完成（O'Dwyer和David Malone，2014）。AI已经证明在优化能源消耗方面非常高效，所以我相信区块链也可以实现类似的结果。这可能也会导致对采矿硬件的投资减少;

* 可扩展性：区块链每10分钟以1MB的速度稳步增长，已经达到了85GB。Satoshi（2008）首先提到“ 区块链修剪 ”（即删除不必要的关于完全花费的交易的数据，以便不把整个区块链放在一台笔记本电脑上）作为一种可能的解决方案，但是人工智能可以引入新的分散式学习系统，或者使用新的数据分片技术来提高系统的效率;

* 安全性：即使区块链几乎不可能破解，它的更多层和应用程序也不是很安全（例如，DAO，Mt Gox，Bitfinex等）。机器学习在过去两年中所取得的惊人进展，使得AI成为区块链的绝佳盟友，以保证应用程序的安全部署，尤其是考虑到系统的固定结构;

* **Privacy**: the privacy issue of owning personal data raises regulatory and strategic concerns for competitive advantages (Unicredit, 2016). Homomorphic encryption (performing operations directly on encrypted data), the **Enigma project** (Zyskind et al., 2015) or the **Zerocash project** (Sasson et al., 2014), are definitely potential solutions, but I see this problem as closely connected to the previous two, i.e., scalability and security, and I think they will go pari passu;

* **Efficiency**: Deloitte (2016) estimated the total running costs associated with validating and sharing transactions on the blockchain to be as much as $600 million a year. An intelligent system might be eventually able to compute on the fly the likelihood for specific nodes to be the first performing a certain task, giving the possibility to other miners to shut down their efforts for that specific transaction and cut down the total costs. Furthermore, even if some structural constraints are present, a better efficiency and a lower energy consumption may reduce the **network latency** allowing then faster transactions;

* 隐私：拥有个人数据的隐私问题引发了对竞争优势的监管和战略考虑（Unicredit，2016）。Enigma项目（ Zyskind等，2015）或Zerocash项目（Sasson等，2014）同态加密（直接对加密数据执行操作）绝对是潜在的解决方案，但是我认为这个问题与前两个，即可扩展性和安全性，我认为他们会同行 ;

* 效率：德勤（2016）估计，与验证和分享区块链交易相关的总运营成本每年高达6亿美元。一个智能系统可能最终能够即时计算特定节点成为第一个执行某项任务的可能性，从而使其他矿工有可能关闭其针对该特定交易的努力并降低总成本。此外，即使存在一些结构约束，更好的效率和更低的能量消耗可以减少网络延迟，从而允许更快的事务;


* **Hardware**: miners (and not necessarily companies but also individuals) poured an incredible amount of money into specialized hardware components. Since energy consumption has always been a key issue, many solutions have been proposed and much more will be introduced in the future. As soon as the system becomes more efficient, some piece of hardware might be converted (sometimes partially) for neural nets use (the mining colossus Bitmain is doing exactly this);

* **Lack of talent**: this is leap of faith, but in the same way we are trying to automate data science itself (unsuccessfully, to my current knowledge), I don’t see why we couldn’t create virtual agents that can create new ledgers themselves (and even interact on it and maintain it);

* **Data gates**: in a future where all our data will be available on a blockchain and companies will be able to directly buy them from us, we will need help to grant access, track data usage, and generally make sense of what happens to our personal information at a computer speed. This is a job for (intelligent) machines.

* 硬件：矿工（不一定是公司，也包括个人）将大量资金投入到专门的硬件组件中。由于能源消耗一直是一个关键问题，因此提出了许多解决方案，未来还将引入更多的解决方案。一旦系统变得更有效率，一些硬件可能会被转换（有时是部分的），用于神经网络的使用（挖掘巨人Bitmain正在做这个）。

* 缺乏人才：这是信念的飞跃，但同样我们正在努力实现数据科学本身的自动化（不成功，以我目前的知识），我不明白为什么我们不能创建虚拟代理来创建新的分类账他们自己（甚至互动和维护）;

* 数据门：未来我们的所有数据都将在区块链上提供，而公司将能够直接从我们这里购买，我们将需要帮助来授予访问权限，跟踪数据使用情况，并且通常会了解我们的个人信息以计算机速度的信息。这是（智能）机器的工作。

### III. How Blockchain can change AI | 区块链如何改变AI

![](https://cdn-images-1.medium.com/max/1600/1*gByP8WZVK_zRxik_hGpZDQ.png)
https://datafloq.com/read/how-cognitive-computing-can-revolutionize-business/3317

In the previous section, we quickly touched upon the effects that AI might eventually have on the blockchain. Now instead, we will make the opposite exercise understanding what impact can the blockchain have on the development of machine learning systems. More in details, blockchain could:

在之前的章节中，我们很快就谈到了人工智能最终会对区块链造成的影响。相反，我们现在正好相反，了解区块链对机器学习系统的发展有什么影响。更详细地说，区块链可以：

* **Help AI explaining itself (and making us believe it)**: the AI black-box suffers from an explainability problem. Having a clear audit trail can not only improve the trustworthiness of the data as well as of the models but also provide a clear route to trace back the machine decision process;

* **Increase AI effectiveness**: a secure data sharing means more data (and more training data), and then better models, better actions, better results…and better new data. Network effect is all that matter at the end of the day;

* 帮助AI解释自己（并让我们相信它）：AI黑盒遭受可解释性问题。清晰的审计跟踪不仅可以提高数据的可信性，还可以提高模型的可信度，也为追溯机器决策过程提供了一条清晰的途径。

* 提高人工智能的有效性：一个安全的数据共享意味着更多的数据（和更多的训练数据），然后更好的模型，更好的行动，更好的结果...和更好的新数据。网络效应在一天结束的时候是重要的。

* **Lower the market barriers to entry**: let’s go step by step. Blockchain technologies can secure your data. So why won’t you store all your data privately and maybe sell it? Well, you probably will. So first of all, blockchain will foster the **creation of cleaner and more organized personal data**. Second, it will allow the emergence of **new marketplaces**: a **data marketplace** (low-hanging fruit); a **models marketplace** (much more interesting); and finally even an **AI marketplace** (see what [Ben Goertzel](https://medium.com/@bengoertzel) is trying to do with [SingularityNET](https://singularitynet.io/)). Hence, easy data-sharing and new marketplaces, jointly with blockchain data verification, will provide a more fluid integration that lowers the barrier to entry for smaller players and shrinks the competitive advantage of tech giants. In the effort of lowering the barriers to entry, we are then actually solving two problems, i.e., providing a **wider data access** and a more efficient **data monetization mechanism**;

* 降低进入市场的障碍：让我们一步一步来。区块链技术可以保护您的数据。那么为什么你不能私下存储所有的数据，也许会出售它？那么，你可能会。首先，区块链将促进创建更清洁，更有组织的个人数据。其次，它将允许出现新的市场：一个数据市场（低挂果实）; 一个模型市场（更有趣）; 最后甚至是一个AI市场（请参阅Ben Goertzel正在尝试使用SingularityNET）。因此，简单的数据共享和新的市场以及区块链数据验证将提供更加流畅的整合，从而降低小企业进入的门槛，缩小高科技巨头的竞争优势。为了降低进入门槛，我们实际上解决了两个问题：提供更广泛的数据访问和更高效的数据货币化机制;

* **Increase artificial trust**: as soon as part of our tasks will be managed by autonomous virtual agents, having a clear audit trail will help **bots to trust each other** (and us to trust them). It will also eventually increase every **machine-to-machine interaction** (Outlier Ventures, 2017) and transaction providing a secure way to share data and coordinate decisions, as well as a robust mechanism to reach a quorum (extremely relevant for swarm robotics and multiple agents scenarios). [Rob May](https://medium.com/@robmay) expressed a similar concept in one of his last newsletters (that I highly recommend — [you should definitely subscribe](https://inside.com/campaigns/inside-ai-2017-09-03-3149/sections/commentary-17321));

* **Reduce catastrophic risks scenario**: an AI coded in a DAO with specific smart contracts will be able to only perform those actions, and nothing more (it will have a limited action space then).

* 增加人为信任：只要部分任务由自主虚拟代理管理，拥有清晰的审计跟踪将有助于机器人互相信任（我们相信他们）。它还将最终增加每个机器对机器的交互（Outlier Ventures，2017），交易提供了一个安全的方式来共享数据和协调决策，以及一个强大的机制达到法定人数（与群体

* 机器人和多个代理非常相关场景）。罗布·梅（Rob May）在他最近的一个通讯中表达了类似的概念（我强烈建议 -  你一定要订阅）。
减少灾难性风险情景：在DAO中使用特定的智能合约编码的AI只能执行这些操作，而只能执行这些操作（其时将具有有限的操作空间）。

In spite of all the benefits that AI will receive from an interaction with blockchain technologies, I do have one big question with no answer whatsoever.

> *AI was born as in an open-source environment where data was the real moat. With this data democratization (and open-source software) how can we be sure that AI will prosper and will keep being developed? What would be the new moat? My only guess at the moment? Talent…*

尽管AI可以从与区块链技术的互动中获得所有的好处，但我确实有一个大问题，没有任何答案。

> *人工智能诞生于数据是真正的护城河的开源环境中。有了这个数据民主化（和开源软件），我们怎么能确定AI会繁荣，并将继续发展？新的护城河会是什么？我现在唯一的猜测是？天赋…*


### IV. Decentralized Intelligent Companies | 分散的智能公司

![](https://cdn-images-1.medium.com/max/1600/1*PFg1uE4iLrUoWLBHLdfCEw.png)
Image Credit: [Wit Olszewski/Shutterstock](https://www.shutterstock.com/g/witolszewski) | 图片来源：Wit Olszewski / Shutterstock

There are plenty of landscapes of blockchain and cryptocurrencies startups out there. I am anyway only interested in those companies working at the intersection (or the convergence, as someone calls it) of AI and blockchain, which apparently are not that many. They are mainly concentrated in San Francisco area and London, but there are examples in New York, Australia, China, as well as some European countries.

They are indeed so few of them that is quite hard to classify them into clusters. I usually like to try to understand the underlying patterns and the type of impact/application certain groups of companies are having in the industry, but in this case is extremely difficult given the low number of data points so I will simply categorize them as follows:

这里有很多blockchain的风景和cryptocurrencies初创公司在那里的。我无论如何只对那些在AI和区块链交汇处工作的公司感兴趣（或者说人们称之为融合），这显然不是那么多。他们主要集中在旧金山地区和伦敦，但在纽约，澳大利亚，中国以及一些欧洲国家也有例子。

他们确实很少，很难将它们分类。我通常喜欢尝试了解某些​​公司在行业中所具有的基本模式和影响/应用类型，但在这种情况下，由于数据点数量较少，所以我将简单地将它们分类如下：

* **Decentralized Intelligence**: [TraneAI](http://www.trane.ai/) (training AI in a decentralized way); [Neureal](http://neureal.net/) (peer-to-peer AI supercomputing); [SingularityNET](https://singularitynet.io/) (AI marketplace); [Neuromation](https://neuromation.io/en/) (synthetic datasets generation and algorithm training platform); [AI Blockchain](https://ai-blockchain.com/) (multi-application intelligence); [BurstIQ](https://www.burstiq.com/) (healthcare data marketplace); [AtMatrix](https://www.atmatrix.org/) (decentralized bots); [OpenMined](https://openmined.org/) project (data marketplace to train machine learning locally);

* **Conversational Platform**: [Green Running](https://www.greenrunning.com/) (home energy virtual assistant); [Talla](https://talla.com/) (chatbot); [doc.ai](https://doc.ai/) (quantified biology and healthcare insights);

* 分散式智能：TraneAI（以分散方式培训AI）; Neureal（点对点AI超级计算）; SingularityNET（AI市场）; Neuromation（合成数据集生成和算法培训平台）; AI区块链（多应用智能）; BurstIQ（医疗数据市场）; AtMatrix（分散机器人）; OpenMined项目（在本地培训机器学习的数据市场）;

* 会话平台：绿色运行（家庭能源虚拟助手）; 塔拉（chatbot）; doc.ai（量化的生物学和医疗保健见解）;

* **Prediction Platform**: [Augur](https://augur.net/) (collective intelligence); [Sharpe Capital](https://sharpe.capital/) (crowd-source sentiment predictions);

* **Intellectual Property**: [Loci.io](https://locipro.com/) (IP discovery and mining);

* **Data provenance**: KapeIQ (fraud detection on healthcare entities); [Data Quarka](http://dataquarks.com/) (facts checking); [Priops](http://priops.com/) (data compliance); [Signzy](https://signzy.com/) (KYC)

* 预测平台：Augur（集体智慧）; 夏普资本（人群来源情绪预测）;

* 知识产权：Loci.io（IP发现和挖掘）;

* 数据来源：KapeIQ（医疗机构欺诈检测）; 数据夸克（事实核查）; Priops（数据符合性）; Signzy（KYC）

* **Trading**: [Euklid](https://www.euklid.com/) (bitcoin investments); [EthVentures](https://ethventures.io/) (investments on digital tokens). For other (theoretical) applications in finance, see Lipton (2017);

* **Insurance**: [Mutual.life](https://mutual.life/en/) (P2P insurance), [Inari](http://www.inari.io/) (general);

* **Miscellaneous**: [Social Coin](https://thesocialcoin.com/?lang=en) (citizens’ reward systems); [HealthyTail](http://healthytail.org/) (pet analytics); [Crowdz](https://www.crowdz.io/) (e-commerce); [DeepSee](https://www.deepsee.io/) (media platform); [ChainMind](http://www.chainmind.com/) (cybersecurity).

* 交易：Euklid（比特币投资）; EthVentures（数字令牌投资）。对于金融领域的其他（理论）应用，见Lipton（2017）;

* 保险：Mutual.life（P2P保险），Inari（普通）;

* 杂项：社会硬币（公民奖励制度）; HealthyTail（宠物分析）; Crowdz（电子商务）; DeepSee（媒体平台）; ChainMind（网络安全）。

A few general comments:

几个一般的评论：

* It looks interesting that many AI-blockchain companies have **larger advisory board than teams**. It might be an early sign that the convergence is not fully realized yet and there are more things we don’t understand that those ones we know;

* I am personally very excited to see the development of the first category (**decentralized intelligence**) but I also see a huge development in **conversational** and **prediction platforms** as well as **intellectual property**. I grouped other examples under “miscellaneous” because I don’t think at this stage they represent a specific category but rather only single attempt to match AI and blockchain;

* 看起来有趣的是，许多AI区块链公司拥有比团队更大的咨询委员会。这可能是一个早期的迹象，说明融合还没有完全实现，还有更多的东西我们不明白，那些我们知道;

* 我个人非常高兴看到第一类（分散式情报）的发展，但是我也看到了对话和预测平台以及知识产权方面的巨大发展。我把其他的例子归类为“杂项”，因为我不认为在这个阶段它们代表了一个特定的类别，而只是一次尝试匹配AI和区块链;

* **Those companies are incredibly hard to evaluate**. The websites are often cryptic enough to not really understand what they do and how (a bit paradoxical if you want to buy the blockchain transparency paradigm) and technology requires a high tech-education to be fully assessed. Cutting through the hype is a demanding task and this makes it very easy to be fooled. But let me give you a concrete example: **ever heard of Magos AI?** In the effort of researching companies for this post, I found myself reading several articles on this forecasting blockchain AI-driven platform company (W[ired](https://www.wired.it/economia/start-up/2017/10/04/magos-la-startup-vuole-prevedere-futuro-ai-blockchain/), [Prnewswire](https://www.prnewswire.com/news-releases/magos-ai-a-neural-network-based-forecasting-platform-gathers-700000-on-its-ongoing-ico-300526569.html), etc.), which just did an ICO for over half a million dollars and that made great promises on its deliverables. The website didn’t work — weird, if you consider that they need to share material/information on the ICOs. But you know, it might happen. I made then an extra effort because I read it on Wired and I was curious to know more about it. I was able to find its co-founders, which I couldn’t find eventually on Linkedin. Weird again. Well, there are people who do not like socials, fair enough, especially if you consider that until three months ago there was no proof of the company existence whatsoever. Let me look into the rest of the team. Nothing even there, and no traceable indications of their previous experiences (except for the CTO master in analytics, that I found no proof of). I tried to then dig into the technology: white papers, blue papers, yellow papers, you name it. I only found reviews of them, no original copies. Final two steps: I don’t consider myself an expert in blockchain at all, but I read, a lot. And I also believe I am fairly knowledgeable when it comes to AI and what is happening in the industry. These guys claimed they created 5 different neural nets that could achieve the same accuracy in complex different domains than Libratus (or DeepStack) reached in Poker, but I never heard of them — very weird. Well, you know what? Maybe I could write them and meet them to understand. Their address points to the AXA office in Zurich. Ah.

* 这些公司难以置信地难以评估。这些网站往往足够隐晦，不能真正理解他们做什么和怎么做（如果你想购买区块链透明模式有点矛盾），技术需要高科技教育得到充分评估。通过炒作是一个艰巨的任务，这使得它很容易被愚弄。但是让我给你一个具体的例子：曾经听说过Magos AI？在研究公司对这个岗位的工作，我发现自己读这个预测blockchain AI-驱动平台公司几篇文章（W IRED，美通社等），刚刚做了一个超过50万美元的ICO，并对其交付成果作出了很大的承诺。如果你认为他们需要分享ICO的材料/信息，那么这个网站就行不通了。但是你知道，这可能会发生。我做了一个额外的努力，因为我在Wired上读过它，我很想知道更多。我能够找到它的联合创始人，我最终不能找到Linkedin。奇怪了。那么，有些人不喜欢社交活动，尤其是如果你考虑到三个月前没有公司存在的证据。让我看看其他的团队。没有什么，也没有可追溯的迹象表明他们以前的经验（除了CTO掌握分析，我发现没有证据）。我试图深入研究这项技术：白皮书，蓝纸，黄纸，你的名字。我只找到他们的评论，没有正本。最后两个步骤：我根本不认为自己是区块链专家，但我读了很多。而且我也相信我对AI和业内正在发生的事情有相当的了解。这些人声称他们创造了5个不同的神经网络，可以在复杂的不同领域达到相同的准确度比在达到扑克室Libratus（或DeepStack），但我从来没有听说过他们 - 非常奇怪。那么，你知道什么？也许我可以写他们，并会见他们理解。他们的地址指向了位于苏黎世的安盛办事处。啊。而且我也相信我对AI和业内正在发生的事情有相当的了解。这些人声称他们创造了5个不同的神经网络，可以在复杂的不同领域达到相同的准确度比在达到扑克室Libratus（或DeepStack），但我从来没有听说过他们 - 非常奇怪。那么，你知道什么？也许我可以写他们，并会见他们理解。他们的地址指向了位于苏黎世的安盛办事处。啊。而且我也相信我对AI和业内正在发生的事情有相当的了解。这些人声称他们创造了5个不同的神经网络，可以在复杂的不同领域达到相同的准确度比在达到扑克室Libratus（或DeepStack），但我从来没有听说过他们 - 非常奇怪。那么，你知道什么？也许我可以写他们，并会见他们理解。他们的地址指向了位于苏黎世的安盛办事处。啊。

After 5 minutes of research, I finally Google the two key words: “Magos scam”. It seems these guys took the money and disappeared. They are surely building the 6 neural net somewhere, so stay tuned.

My point here is that exponential technologies are fantastic and can advance mankind, but as much as the benefits increase also the potential “negative convergence” increases exponentially. Stay alert.

经过5分钟的研究，我终于在谷歌的两个关键词：“魔鬼骗局”。看来这些人拿走了钱，消失了。他们确实在某处建立了6个神经网络，敬请关注。

我的观点是，指数技术是非常棒的，可以推动人类，但随着利益的增加，潜在的“ 负面趋同 ”也会呈指数级增长。保持警惕。


### V. Conclusion | 结论

![](https://cdn-images-1.medium.com/max/1600/1*x8NJVuyt13o92Oz7k6-BfA.png)
Image Credit: Sasun Bughdaryan/Shutterstock | 图片来源：Sasun Bughdaryan / Shutterstock

Blockchain and AI are the two extreme sides of the technology spectrum: one fostering centralized intelligence on close data platforms, the other promoting decentralized applications in an open-data environment. However, if we find an intelligent way to make them working together, the total positive externalities could be amplified in a blink.

There are of course technical and ethical implications arising from the interaction between these two powerful technologies, as for example how do we edit (or even forget) data on a blockchain? Is an [**editable blockchain**](https://www.coindesk.com/accenture-awarded-patent-editable-blockchain-tech/) the solution? And is not an AI-blockchain pushing us to become data hoarder?

Honestly, I think the only thing we can do is keep experimenting.

锁链和人工智能是技术领域的两个极端：一个是培养关闭数据平台的集中式智能，另一个是在开放数据环境中推动分散式应用。但是，如果我们找到一个聪明的方法来使它们一起工作，总的积极的外部效应就可以在一瞬间被放大。

当然这两种强大的技术之间的交互会产生技术和伦理上的影响，例如我们如何编辑（甚至忘记）区块链上的数据？是可编辑区块链解决方案吗？而不是AI区块链推动我们成为数据囤积者？

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

本文由币乎社区（bihu.com）内容支持计划赞助。

版权所有，转载需完整注明以上内容。

----------------------------------------------------