# Byzantine political economy
# 拜占庭政治经济

> 本文翻译自：https://medium.com/@cryptoeconomics/byzantine-political-economy-de25bf8f047e
>
> 原文作者：Chris Berg, Sinclair Davidson 与 Jason Potts  
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [龙心小台](https://github.com/xnylong/EOS)
> 
> 原文发表时间：2017-10-24
>
> 翻译时间：2018-03-22

*Chris Berg, Sinclair Davidson and Jason Potts are from the [RMIT Blockchain Innovation Hub](http://sites.rmit.edu.au/blockchain-innovation-hub/), the world’s first social science research centre into the economics, politics, sociology, and law of blockchain technology.*

*本文作者为 Chris Berg，Sinclair Davidson 和 Jason Potts，他们 来自 [RMIT 区块链创新中心](http://sites.rmit.edu.au/blockchain-innovation-hub/)，这是世界上第一个深入研究关于区块链技术的经济、政治、社会学和法律的社会科学研究中心。*

For more than three decades economists and cryptographers have been working on the same problem.

三十多年来，其实经济学家和密码学家一直在研究同样的问题。

Neither species has recognised their own work in the other.
双方却都未发现这个事实。

But it turns out that the question of how to coordinate a society and how to ensure communication can be trusted is the same question differently phrased.

然而，事实证明，如何协调一个社会，与如何保证值得信赖的沟通，其实是同一个问题的不同表述。

Our argument in this essay is simple: What cryptographers call byzantine fault tolerance and economists call robust political economy is the same thing.

我们在本文中的论点很简单：**密码学家所谓的拜占庭容错与经济学家所谓的强大的政治经济学是一回事。**

This observation turns out to have some significant consequences for understanding the history of economic thought and the directions of institutional cryptoeconomics.

这一观察结果对于理解经济思想史和[制度加密经济学](https://medium.com/@cryptoeconomics/the-blockchain-economy-a-beginners-guide-to-institutional-cryptoeconomics-64bf2f2beec4)的方向具有重要意义。

But to explain why, let’s quickly revisit one of the most important debates in the history of economics.

不过为了解释其原因，让我们先快速回顾一下经济史上最重要的辩论之一。

## The socialist calculation debate 社会主义计算辩论

Economists from Adam Smith on have sought to explain the wealth of nations — why some nations are prosperous and others are not. By the twentieth century this debate had coalesced into a debate about which of two economic systems (communist central planning or capitalist decentralised markets) were more likely to bring prosperity.

从亚当斯密开始，经济学家们便一直试图解释国家的财富 - 为何一些国家富裕，而另一些国家则不富裕。 到了二十世纪，这场辩论变为一场关于两个经济体系中的哪一个（共产主义中央计划或资本主义分散市场）更有可能带来繁荣的辩论。

Smith argued that market societies were characterised by spontaneous orders. Social order came from market incentives.

史密斯认为，市场社会以自发秩序为特征。 社会秩序来自市场激励。

Karl Marx objected that the state (or some central coordinating authority) could produce superior outcomes to the market through conscious, deliberate planning.

卡尔马克思反对说，国家（或一些中央协调机构）可以通过有意识的精心规划，在市场上创造出更优越的结果。

Before the socialist calculation debate the liberal critique of socialism focused on the problem of incentives— how could a socialist community convince people to work hard if the product from their labour was redistributed? (See, for example, the discussion of socialism in Bruce Smith’s 1887 book Liberty and Liberalism.)

在社会主义计算辩论之前，对社会主义的自由主义批评集中在**关于激励的问题**上 - 社会主义社区如何说服人们努力工作，如果他们的劳动产品被重新分配的话？ （例如，参见布鲁斯史密斯 （Bruce Smith) 1887年的 [“自由与自由主义”](http://oll.libertyfund.org/titles/296#lf0306_head_011) 一书中关于社会主义的讨论。）

In 1920 the Austrian economist Ludwig von Mises published Economic Calculation in the Socialist Commonwealth. In this essay, Mises made a new, fundamental critique of socialist planning —the problem of information.

1920年，奥地利经济学家路德维希·冯·米塞斯（Ludwig von Mises ）出版了[“在社会主义联邦中的经济计算”](https://mises.org/library/economic-calculation-socialist-commonwealth)一文。 在此文中，米塞斯对社会主义计划提出了一个新的、根本性的批判 - **关于信息的问题**。

In a market economy, Mises argued, prices constitute signals about the highest value use of a good or service, providing a guide for what goods were in demand, and which were in a glut.

米塞斯认为，在市场经济中，价格构成了对商品或服务的最高价值使用的信号，使人们知道什么商品供不应求，什么商品供过于求。

But a socialist system has no prices. As one of us has described Mises’ argument,

*但社会主义制度没有价格*。 正如我们其中一位人士所描述的米塞斯的论点，

> *How would [a socialist planner] decide whether to send rubber to Tyre Factory 12 or Hose Factory 7? In a market economy, the factory that needed the rubber most would be willing to pay the highest price. But there is no natural price system in socialism — consumer prices are decided by the planner, and rubber allocated according to their diktat.*

> *[社会主义计划者]如何决定是将橡胶送到轮胎工厂还是软管工厂？ 在市场经济中，最需要橡胶的工厂愿意支付最高的价格。 但是社会主义没有自然的价格体系 - 消费者的价格是由计划者决定的，橡胶按其勒令分配。*

###### Friedrich Hayek and Ludwig von Mises

###### 弗里德里希·哈耶克 与 德维希·冯·米塞斯

Mises’ critique of socialism was extended and elaborated by Lionel Robbins and Friedrich Hayek. Hayek turned this argument into one of the greatest essays in economics: ‘The Use of Knowledge in Society’, where he described prices as a decentralised knowledge network.

米塞斯对社会主义的批判由莱昂内尔·罗宾斯 (Lionel Robbins) 和弗里德里希·海耶克（Friedrich Hayek）进行了扩展与阐述。 哈耶克将这一论点转化为经济学中最重要的文章之一：[“社会中的知识的使用”](http://www.econlib.org/library/Essays/hykKnw1.html)，其中，他将价格描述为去中心化的知识网络。

Centralised computer socialism 中心化计算机社会主义

The Mises and Hayek argument today is well known, particularly after they seemed to be proven right by the fall of the Berlin Wall. By contrast, their opponents in the debate are less read today.

如今，米塞斯和哈耶克的论点是众所周知的，特别是在他们的论点似乎被柏林墙的倒塌证明正确之后。 相比之下，他们在辩论中的对手如今更鲜为人知。

Mises and Hayek’s criticism was answered by the Polish economist Oskar Lange and extended by Hayek’s Russian-born student Abba Lerner.

米塞斯和哈耶克的批判得到了波兰经济学家奥斯卡兰格（Oskar Lange) 的回答，并由哈耶克的俄罗斯裔学生阿巴勒纳 （Abba Lerner）延伸。

Lange and Lerner accepted the importance of the price system in organising economic activity. But they argued that this system could be simulated mathematically.

兰格与勒纳接受了价格体系在组织经济活动中的重要性。 但他们认为，这个系统可以用数学模拟。

Working firmly in the equilibrium economics school Vilfredo Pareto and Léon Walras, **they imagined the price system as computational machine. In On the Economic Theory of Socialism**, published first in 1936 and 1937, Lange concluded that a socialist economy could simulate the effect of the price system by trial and error.

均衡经济学派的坚定拥护者 Vilfredo Pareto 和 Léon Walras，**将价格体系想象成计算机器**。 在1936年和1937年首次发表的[“社会主义经济理论”](https://archive.org/details/in.ernet.dli.2015.263328)中，兰格认为，社会主义经济可以通过反复试验来模拟价格体系的影响。

Lange revisited his argument 30 years later. “Were I to rewrite my essay today my task would be much simpler”, wrote Lange:

30年后，兰格重新审视了他的论点。 “如果今天我要重写我的论文，那么我的任务会简单得多，“ 兰格写道：

> *My answer to Hayek and Robbins would be: so what’s the trouble? Let us put the simultaneous equations on an electronic computer and we shall obtain the solution in less than a second. The market process with its cumbersome tâtonnements appears old-fashioned. Indeed, it may be considered as a computing device of the pre-electronic age.*

> *我对哈耶克和罗宾斯的回答会是：那有什么困难？ 让我们把联立方程式放在电子计算机上，我们将在不到一秒的时间内获得解决方案。 而市场流程繁琐，需要反复试错才能达到平衡，与计算机的解决方案相比，显得老旧过时。 事实上，市场的反复试错方式可能被认为是电子时代之前的计算方式。*

Not only could computers simulate the market but the computer could conduct long range planning and implement that plan — “a function which the market never was able to perform”.

计算机不仅可以模拟市场，而且可以进行长期规划并实施该计划 - “这是市场永远无法执行的功能”。

## How decentralised is Hayek’s market, really? 哈耶克的市场到底有多分散？

It is typical to cast these two visions of the economy as Lange’s centralised planned economy and Hayek’s decentralised market.

我们通常将这两种经济理念称为兰格的中央计划经济和哈耶克的分散市场。

**But Hayekian decentralisation still has a lot of centralisation in it.**

**但哈耶克的分散化仍然有很多中心化的地方。**

Here the Marxists are right. Free markets have an awful lot of state involvement in them. Property is private but its enforcement relies heavily on public authorities — the legal system courts, sheriffs, police.

在此，马克思主义者是对的。 自由市场中仍有许多国家参与的部分。 财产是私人的，但其执法严重依赖于公共职能部门 - 法律体制中的法院、警长与警察。

But what both the Hayekians and the Marxists missed is that property rights are not only about enforcement. They’re about the identification and verification of property rights. And (right now) the state does most of that.

但哈耶克学派与马克思主义者都未提及的是，产权不仅仅是执法，还涉及了产权的识别与验证。 而且（目前）其中的大部分工作是由国家完成的。

As we argued in our previous essay, so much of what the modern state does is endorse, manage, and verify ledgers of social relations. The state manages the property titles register. It manages ledgers of social security entitlements. It manages the ledgers of who is a citizen and who can therefore participate in political bargaining.

正如我们在[上一篇文章](https://medium.com/@cryptoeconomics/the-blockchain-economy-a-beginners-guide-to-institutional-cryptoeconomics-64bf2f2beec4)中所论证的，**现代国家所做的很多事情是支持、管理与验证社会关系的账簿**。 国家管理着财产产权登记册。 国家管理着社保权利的账簿。 国家管理着记录了公民身份并由此决定是否可以参与政治活动的账簿。

This is a very big, important, and largely unappreciated function that the state fulfills. The state does is in charge of these crucial ledgers because it is a large ‘trusted’ entity. But of course how much we can trust the state is questionable.

这是国家实现的一个非常重要的，却常不被赏识的功能。 国家确实负责管理这些重要的账簿，因为国家是一个庞大的“可信任”实体。 但当然，我们对国家的可信程度保持一定的怀疑态度。

The invention of the blockchain presents us with new institutional choices.

区块链的发明为我们提供了新的制度选择。

### A new typology of political economy 一种新型的政治经济学

In our new typology of political economy, political ideas are arranged in a grid of centralised and decentralised economies, and centralised and decentralised ledgers.

在我们的新型政治经济学里，政治理念被安排在中心化与分散化经济，以及中心化与分散化账簿的网格中。

In **Lange’s computer socialism**, the economy is centralised and the ledger is centralised — the state is a planning machine, both managing the ledger and executing a global plan.

在**兰格的计算机社会主义**中，经济是中心化的，账簿是中心化的 - 国家是一个计划机器，既管理账簿又执行全球计划。

In **pre-Marxist communalism**, such as the scheme devised by the Welsh utopian socialist Robert Owen, economic planning is centralised but the relevant jurisdiction — that is, the ledger-providing authority — consists of subnational groups of voluntary, socialistic communities.

在**马克思主义之前的社会主义制度**中，例如由威尔士乌托邦社会主义者罗伯特欧文（Robert Owen）设计的制度中，经济计划是中心化的，但相关的管辖权 - 即提供账簿的当局 - 由自愿的地方社会团体组成。

**Hayekian distributed capitalism** has a decentralised economy — planning is done by individuals rather than the state — yet the state still organises, records, verifies and updates the ledgers of identities, rights, obligations, and entitlements.

**哈耶克分布式资本主义**为分散式经济 - 计划由个人而非国家完成 - 但国家仍然组织、记录、核实和更新记录着身份、权利、义务和权益的账簿。

By contrast, in a cryptoeconomy both the economy and the ledgers are decentralised. Blockchains take the state out of both planning and verification.

与此相反，在加密经济中，经济和账簿都是分散化的。 区块链使得计划与验证过程都不再需要国家参与。

### Information and incentives 信息与激励

**Markets work because they align incentives into productive work and they harness distributed information productively.**

**市场能够运作是因为能将激励措施与生产性工作结合起来，并有效利用分布式信息。**

In the second half of the twentieth century the **public choice school** extended the incentives critique to encompass the incentives of the planners themselves. How could a socialist commonwealth ensure that planners worked in society’s interest, rather than their own personal interest?

在二十世纪下半叶，**公共选择学派**将对于激励的批评扩展到对计划者本身所受激励的讨论。 社会主义联邦怎么能确保规划者为了社会的利益而不是自己的个人利益工作？

Today, what scholars now call a ‘robust political economy’ (see [Mark Pennington’s book](https://www.e-elgar.com/shop/robust-political-economy?___website=uk_warehouse) and [this paper by Peter T. Leeson and J. Robert Subrick](http://www.peterleeson.com/Robust_Political_Economy.pdf)) is an economic system structured to deal with the twin problems of **information** and **incentives**. How can we coordinate action — make exchanges, build relationships and communities — in a world of incomplete information and potential rentseeking?

今天，学者们所说的“强大的政治经济学”（参见[Mark Pennington 的书](https://www.e-elgar.com/shop/robust-political-economy?___website=uk_warehouse)，以及 [Peter T. Leeson 和 J. Robert Subrick 撰写的这篇论文](http://www.peterleeson.com/Robust_Political_Economy.pdf)），是一个用于处理**信息**与**激励**的双重问题的经济体系。 我们如何能够在一个信息不健全和存在潜在“寻租活动”的环境中协调关于交易、构建关系与社区的行动（译者注：“寻租”指的是为垄断社会资源，得到垄断利润所从事的非生产性寻利活动。常指政府运用行政权力对企业和个人的经济活动进行干预和管制，妨碍了市场竞争的作用，从而创造了少数有特权者取得超额收入的机会。）？

Turns out, cryptographers and computer scientists have been working on these two problems as well.

事实证明，密码学家和计算机科学家也一直在研究这个关于信息与激励的双重问题。

### The Byzantine Generals’ Problem 拜占庭将军问题

Distributed computing systems have to deal with what is known as the Byzantine Generals’ Problem.

分布式计算系统必须处理所谓的拜占庭将军问题。

This problem was first expressed in 1982. Imagine a Byzantine army surrounding an enemy city. 

[这个问题首次在1982年被提出](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/12/The-Byzantine-Generals-Problem.pdf)。想象一下拜占庭军队围绕了一座敌城。

###### Illustration from the 12th century Madrid Skylitzes, a history of Byzantium between 811 and 1057 

###### 插图来自12世纪 Madrid Skylitzes，811  年到 1057 年的拜占庭历史

The army consists of divisions, each headed up by a general, and they need to establish a consensus about when exactly to launch their attack on the city.

拜占庭军队由各部队组成，每个部队由一名将军领导，他们需要就何时发起对城市的袭击达成共识。

Centralised command is out of the question. No individual general has line of sight to all the generals — or the authority to impose consensus on the whole army at once. They can only communicate by messenger.

集中化的命令是不可能的。 没有哪个将军知道所有将军的想法，亦无权强制使整个军队立即达成共识。 他们只能通过信使进行沟通。

**So there’s an information problem.** The generals need a system — an algorithm — that allows all generals to agree on a consensus.

**所以在此存在一个信息上的问题。** 这些将军需要一个系统 - 一种算法 - 来允许所有将军达成共识。

**The problem is made even harder because it’s not certain that all generals are loyal.** Some have been paid off by the enemy, and are actively trying to disrupt the plan. The traitorous generals don’t want the loyal generals to come to a consensus.

**使问题变得更加困难的是 ，不一定所有将军都是忠诚的。** 有些将军被敌人收买，并积极试图破坏作战计划。 背叛者们不希望忠诚的将军们达成共识。

Thus Byzantine Generals’ Problem describes the challenge of a) achieving consensus in distributed, decentralised systems b) when information flows imperfectly, and c) in the presence of adversaries.

因此，拜占庭将军问题阐述了以下挑战：a）在分布式、分散的系统中， b）信息流动并非完美时，以及 c）存在作恶者时，如何达成共识。

**Blockchains achieve Byzantine fault tolerance in part by treating it as an incentive problem.** The Bitcoin proof-of-work mechanism incentivises good behaviour, makes it extremely expensive to attack the network, and reduces the payoffs for a successful attack.

**区块链实现了拜占庭式容错的部分原因是将其视为激励问题。** 比特币的工作量证明机制激励了良好的行为，使攻击网络的成本变得极其高昂，并降低了成功攻击的收益。

The so-called ’51 per cent’ attack on Bitcoin — the possibility that a majority of hashing power could coordinate and then undermine the network — is what would happen if more than half the generals were traitors. (Of course, that itself would be hard to coordinate.)

所谓的对比特币的“51％”攻击 - 即大部分算力合谋并破坏网络的情况- 指的便是当超过一半的将军背叛时，会发生的情况。 （当然，51%攻击本身很难协调。）

### Two fields together 两个领域的结合

A decision to attack a city simultaneously is just a narrow slice of the general economic problem: how to coordinate activity in when information is incomplete, communication is imperfect, and people can be lazy, opportunistic, and self-interested.

如何同时攻击一座城市只是整个经济问题的一个小缩影：如何在信息不完整、沟通不完善以及当人们可能是懒惰的、机会主义与利己主义的情况下协调活动。

What computer scientists have been trying to solve *algorithmically*, economists have been trying to solve *constitutionally*.

计算机科学家一直试图通过*算法*解决的问题，经济学家一直试图从*宪法*上解决。

Where cryptographers have found their solutions in *public key cryptography and proof of work mechanisms*, economists have found solutions in *markets, regulation, and institutions*.

在密码学家已经在*公钥密码学和工作量证明*中找到解决方案之时，经济学家已经在*市场、法规与机构*中找到了解决方案。

Blockchains bring these two fields together. They turn constitutional questions into algorithmic questions, and algorithmic questions into constitutional ones.

区块链将这两个领域结合在了一起。 区块链将宪法问题变成了算法问题，而算法问题变成了宪法问题。

## Byzantine political economy 拜占庭政治经济

One way to see this is as a curious historical instance of two largely unrelated fields (computer science and economics) somewhat simultaneously working on a structurally similar problem (decentralised coordination) and arriving at the same type of solutions (consensus protocols and market institutions).

一种看待该情况的方式是将其看成一件独特的历史事例，即两个基本上不相关的领域（计算机科学和经济学），同时研究了一个结构相似的问题（分散式协调问题），并得出相同类型的解决方案（共识协议和市场机构）。

**But a more interesting perspective is that blockchain technology actually joins these worlds together in reality.** Blockchains can provide the secure fault tolerant decentralised layer for property rights information and its verification and updating whenever that information changes, which can support a decentralised economic layer of markets.

**但更有趣的一个观点是，区块链技术实际上将两个世界融合在了一起。** 区块链可以为产权信息即验证提供安全的、可容错的去中心化层，并在信息发生变化时即使更新，从而支持分散经济层的市场。

The socialists were wrong in their hopeful quest that (centralised) computers would replace markets. Actually, it is decentralised computers (blockchains) than can replace governments.

社会主义者希望追求（中心化）电脑取代市场是错误的。 实际上，去中心化的计算机（区块链）才可将其取代。

Markets always need governance, and the limits of a market society were always the ability of the state to provide those services of record keeping, validation and verification of transactions in property rights. In return, the state levied taxation to fund these services. Blockchains are a new technology of fault tolerant governance that can furnish the governance to underpin a market economy and society.

市场总需要治理，而市场社会的限制始终取决于国家提供保存记录、确认和核实产权交易的服务的能力。 作为回报，国家征税以资助这些服务。 区块链是一种新的容错治理技术， 可以为市场经济和社会提供支撑。

**We call this Byzantine Political Economy.**

**我们将其称为拜占庭政治经济。**

---------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

版权声明：

版权所有，经 Jason Potts 授权译者在[区块链中文字幕组（github.com/BlockchainTranslator)](github.com/BlockchainTranslator)和[币乎(bihu.com)](bihu.com)上发表。不得转载。


----------------------------------------------------
