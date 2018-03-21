Triple Entry Accounting  三式记账法

===========

> 本文翻译自:  [http://iang.org/papers/triple_entry.html](http://iang.org/papers/triple_entry.html)
> 原标题:  Triple Entry Accounting
> 作者:  [Ian Grigg](http://iang.org)
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [荆凯](https://github.com/shuke0327)
> 感谢:  本文由币乎社区（http://www.bihu.com）内容支持计划奖励。特此致谢
> 翻译时间：2018-02-01
---------------------------


> **Abstract:**The digitally signed receipt, an innovation from financial cryptography, presents a challenge to classical double entry bookkeeping. Rather than compete, the two melded together form a stronger system. Expanding the usage of accounting into the wider domain of digital cash gives 3 local entries for each of 3 roles, the result of which I call*triple entry accounting*.
> 
> This system creates bullet proof accounting systems for aggressive uses and users. It not only lowers costs by delivering reliable and supported accounting, it makes much stronger governance possible in a way that positively impacts on the future needs of corporate and public accounting.


> **摘要:**数字签名收据是金融密码学的一项创新，它对传统的复式记账法提出了挑战。 使这两者结合而非相互竞争，能够形成更强大的体系。将会计的使用范围扩大到数字现金的更广泛领域，为3个角色提供了3份本地记录，我称之为*三式记账法( triple entry accounting)*.
> 
>该系统为激进的用途和用户提供了无懈可击的(bullet proof)会计系统。它不仅提供可靠的会计支持降低成本，而且使得更强有力的治理成为可能，从而对企业和公共会计的未来需求产生积极的影响。



## Introduction 简介

This paper brings together financial cryptography innovations such as the Signed Receipt with the standard accountancy techniques of double entry bookkeeping.

本文将金融密码学的创新如签名收据(Signed Receipt), 以及复式记账法(double entry bookkeeping)的标准会计技术这两者结合。

The first section presents a brief backgrounder to explain the importance of double entry bookkeeping. It is aimed at the technologist, and accountancy professionals may skip this. The second section presents how the Signed Receipt arises and why it challenges double entry bookkeeping.

第一部分是简要的背景介绍，以解释复式记账法的重要性。它是写给是技术人员的，会计专业人员可以跳过这一部分。第二部分介绍签名收据(Signed Receipt )如何产生，又为何会挑战复式记账法(double entry bookkeeping)。

The third section integrates the two together and the Conclusion attempts to predict wider ramifications into Governance issues.

第三部分将两者相结合，结论部分试图预测对治理问题的更广泛的影响。

### Credits 致谢

This paper benefitted from comments by Graeme Burnett and Todd Boyle[TB]http://iang.org/papers/triple_entry.html#ref_TB).

这篇论文受益于 Graeme Burnett 和 Todd Boyle[TB](http://iang.org/papers/triple_entry.html#ref_TB)的评论.

## A Very Brief History of Accounting - 极简会计史

Accounting or accountancy is these days thought to go back to the genesis of writing; the earliest discovered texts have been deciphered as simple lists of the counts of animal and food stock. The Sumerians of Mesopotamia, around 5000 years ago, used*Cuneiform*or wedge shaped markings as a base-60 number form, which we still remember as seconds and minutes, and squared, as the degrees in a circle. Mathematics and writing themselves may well have been derived from the need to add, subtract and indeed account for the basic assets and stocks of early society.

如今，会计或会计学(Accounting or accountancy )被认为可以追溯到书写的起源;经过解读发现，所发现的最早的文字是动物和所存食品数量的简单列表。大约在5000年前，美索不达米亚的苏美尔人使用*楔形文字(Cuneiform)*或楔形标记用作六十进制( base-60 number form)，这个我们今天仍然用作时间计数，其平方，则是圆的度数。早期社会对基本资产和存货的加减计算和记账的需要，很可能就是数学和书写出现的缘由。

### Single Entry 单式记账法

Single entry bookkeeping is how 'everyone' would do accounting: start a list, and add in entries that describe each asset. A more advanced arrangement would be to create many lists. Each list or 'book' would represent a category, and each entry would record a date, an amount, and perhaps a comment. To move an asset around, one would cross it off from one list and enter it onto to another list.

单式记帐法是“每个人”记账时都会用的方法:创建一个列表，添加描述每种资产的条目。更进阶的做法是创建许多列表。每个列表或“账簿(book)”都代表一种类别，每个条目都记录着日期、金额，可能还会有注释。要移动资产，就把它从一个列表中划掉，然后输入到另一个列表中。

Very simple, but it was a method that was fraught with the potential for errors. Worse, the errors could be either accidental, and difficult to track down and repair, or they could be fraudulent. As each entry or each list stood alone, there was nothing to stop a bad employee from simply adding more to the list; even when discovered there was nothing to say whether it was an honest mistake, or a fraud.

非常简单，但这一方法很有可能出错。更糟糕的是，这些错误可能出于失误，很难追踪和修复，或者它们也可能是故意欺诈。由于每个条目或每个列表都是单独的，所以没有什么可以阻止一个坏员工向列表中添加更多内容;即使被发现了，也没有什么办法可以分辨只是失误，还是欺诈。

Accounting based on single entry bookkeeping places an important limitation on the trust of the books. Likely, only the owner's family or in times long past, his slaves could be trusted with the enterprise's books, leading to a supportive influence on extended families or slavery as economic enterprises.

基于单式记帐的会计方法对账本的信任有着重要的限制。有可能只能是企业主的家人，或者在很久之前，他的奴隶，才可以被信任，能管理企业的账簿，这导致了对大家族和奴隶制经济企业的支持性影响。

### Double Entry 复式记账法

[Double Entry bookkeeping](http://en.wikipedia.org/wiki/Double-entry_book-keeping)adds an additional important property to the accounting system; that of a clear strategy to identify errors and to remove them. Even better, it has a side effect of clearly firewalling errors as*either*accident*or*fraud.

[复式记账法](http://en.wikipedia.org/wiki/Double-entry_book-keeping)为会计系统增加了额外的重要特性; 即，一种清晰的策略，可以识别并消除错误。更妙的是它的附加影响，可以很明确的区分(firewalling )*意外*或者*欺诈*所产生的错误。

This property is enabled by means of three features, being the separation of all books into two groups or sides, called*assets*and*liabilities*, the redundancy of the duplicative*double entries*with each entry having a match on the other side, and the*balance sheet equation*, which says that the sum of all entries on the asset side must equal the sum of all entries on the liabilities side.

有三种属性，使得上述特性成为可能: 将所有的账簿分为两组或者两侧，称为*资产*和*负债*；冗余重复的*复式条目*的存在 -- 每个条目在另外一侧都有对应的条目；以及*资产负债表等式*，是指在资产一侧的条目的总值等于在负债一侧的条目的总值。

A correct entry must refer to its counterparty, and its counterpart entry must exist on the other side. An entry in error might have been created for perhaps fraudulent reasons, but to be correct at the local level, it must refer to its counterparty book. If not, it can simply be eliminated as an incomplete entry. If it does refer, the existance of the other entry can be easily confirmed, or indeed recreated depending on the sense of it, and the loop is thus closed.

一个正确的条目必须涉及到它的交易对手方，交易对方的对应条目必须存在于另一侧。可能由于欺诈的原因产生了错误的条目，但为了能够在本地层面上(at the local level)修正，它必须关联到其交易对象的账簿。如果没有，可以简单地将它当作是不完整的条目而删除。如果它确实提到了，就可以很容易地确认其它条目的存在，或者根据需要可以重新创建，这一循环就此闭合。

Previously, in single entry books, the fraudster simply added his amount to a column of choice. In double entry books, that amount has to come from somewhere. If it comes from nowhere, it is eliminated above as an accidental error, and if it comes from somewhere in particular, that place is identified. In this way, fraud leaves a trail; and its purpose is revealed in the other book because the value taken from that book must also have come from somewhere.

以前，在单式记账法的账簿中，诈骗者只要把数量加到一列的记录中就行了。在复式记账法中，这一数额必须来自某个地方。如果它没有来由，就会将它作为一个偶然的错误排除在外，如果它来自某个特定的地方，那么就可以确认来源。这样，欺诈就留下了痕迹; 其目的就会在另外一本账簿中揭露出来，因为从那本账簿中所记录的数值，也应该来自某个地方。

This then leads to an audit strategy. First, ensure that all entries are complete, in that they refer to their counterpart. Second, ensure that all movements of value make sense. This simple strategy created a record of transactions that permitted an accountancy of a business, without easily hiding frauds in the books themselves.

这就导向了一种审计的策略。首先，确保所有条目都完整，即它们都对应另一侧的条目。第二，确保所有的数值变动都有意义。根据这一简单的策略所创造的交易记录，可以让企业会计无法在账本中轻易地隐瞒欺诈行为 。

### Which Came First - Double Entry or the Enterprise?

复式记账法和企业，谁先出现？

Double Entry bookkeeping is one of the greatest discoveries of commerce, and its significance is difficult to overstate. Historians think it to have been invented around the 1300s AD, although there are suggestions that it existed in some form or other as far back as the Greek empire. The earliest strong evidence is a 1494 treatise on mathematics by the Venetian Friar[Luca Pacioli](http://www-groups.dcs.st-andrews.ac.uk/~history/Mathematicians/Pacioli.html). In his treatise, Pacioli documented many standard techniques, including a chapter on accounting. It was to become the basic text in double entry bookkeeping for many a year.

复式记账法是商业上最伟大的发现之一，其重要性再怎么强调也不为过。历史学家认为它是在公元1300年左右发明的，尽管有人认为，早在希腊帝国时期，复式记账法就以各种各样的形式存在了。最早的强有力的证据是1494年威尼斯修士(Luca Pacioli)(http://www-groups.dcs.st-andrews.ac.uk/ ~历史/数学/ Pacioli.html)的数学论文。在他的论文中，Pacioli记录了许多标准的技术，有一章是写会计的。许多年里，这是复式记账法的基本文本形式。

Double Entry bookkeeping arose in concert with the arisal of modern forms of enterprise as pioneered by the Venetian merchants. Historians have debated whether Double Entry was invented to support the dramatically expanded demands of the newer ventures then taking place surrounding the expansion of city states such as Venice or whether Double Entry was an enabler of this expansion.

复式记账法的兴起，与以威尼斯商人为开路先锋的现代企业形式的崛起相一致。历史学家们在争论，是先有了像威尼斯这样的城邦扩张，才导致了复式记账法的发明以满足新资本急剧扩张的需要，或者是复式记账法的出现促成了这一扩张。

Our experiences weigh in on the side of enablement. I refer to the experiences of digital money issuers. Our own first deployment of a system was with a single entry bookkeeping system. Its failure rate even though coding was tight was such that it could not sustain more than 20 accounts before errors in accounting crept in and the system lost cohesion. This occurred within weeks of initial testing and was never capable of being fielded. The replacement double entry system was fielded in early 1996 and has never lost a transaction (although there have been some close shaves.

我们的经验让我更支持后一观点，即复式记账法的出现促成了扩张。我指的是我们作为数字货币发行者的经验。我们部署的第一个系统是单式记账系统。即使编程很严格，它的失败率却很高，支持不到20个帐户就会出差错，并且系统失去了内聚力（cohesion）。这在最初测试的几周内就发生了，并且系统永远无法部署(fielded)。更换了复式记账法的系统在1996年初部署, 从未丢失一笔交易(尽管有几次险些出错).

Likewise, the company DigiCash BV of the Netherlands fielded an early digital cash system into a bank in the USA. During its testing period, the original single entry accounting system had to be field replaced with a double entry system for the same reason - errors crept in and rendered the accounting underneath the digital cash system unreliable.

同样，荷兰的DigiCash BV公司也将早期的数字现金系统部署到了美国的一家银行。在测试期间，由于同样原因，不得不以复式记账法系统代替原有的单式记账系统：错误的发生，使得数字现金系统底层的会计系统不可靠。

Another major digital money system lasted for many years on a single entry accounting system. Yet, the company knew it was running on luck. When a cracker managed to find a flaw in the system, an overnight attack allowed the creation of many millions of dollars worth of value. As this was more than the contractual issue of value to date, it caused dramatic contortions to the balance sheet, including putting it in breach of its user contract and at dire risk of a 'bank run'. Luckily, the cracker deposited the created value into the account of an online game that failed shortly afterwards, so the value was able to be neutralised and monetarily cleansed, without disclosure, and without scandal.

另一个主要的数字货币系统使用单式记账法系统持续了很多年。然而，这个公司知道全靠运气。骇客一旦设法在系统中找到一个漏洞，一夜之间的攻击，就可以创造出值数百万美元的价值。由于这不仅仅是合同价值问题，它给资产负债表会造成戏剧性的扭曲，包括将其置于违反用户合同的境地，并面临着“银行挤兑”的可怕风险。幸运的是，骇客将所创造的价值存入了一个在线游戏的账户中，这个游戏很快就失败了，所以这些价值被中和了，被彻底的清除，没有披露，没有丑闻。

In the opinion of this author at least, single entry bookkeeping is incapable of supporting any enterprise more sophisticated than a household. Given this, I suggest that evolution of complex enterprises required double entry as an enabler.

至少在笔者看来，单式记账法无法支撑任何复杂度比家庭更高的企业。鉴于此，我认为复杂企业的发展需要复式记账法作为其促成因素。

### Computing Double Entry in Quick Time 计算复式记账法速览

Double Entry has always been the foundation of accounting systems for computers. The capability to detect, classify and correct errors is even more important to computers than it is to humans, as there is no luxury of human intervention; the distance between the user and the bits and bytes is far greater than the distance between the bookkeeper and the ink marks on his ledgers.

复式记帐一直是计算机会计系统的基础。识别错误、对错误分类和纠正错误的能力，对于计算机而言要比对人类来说要重要的多，因为不存在奢侈的人类干预行为；用户和数位及字节之间的距离，要远比簿记员和他账簿上的墨迹的距离遥远得多。

How Double Entry is implemented is a subject in and of itself. Computer science introduces concepts such as*transactions*, which are defined as units of work that are*atomic*,*consistent*,*isolated*, and*durable*(or ACID for short). The core question for computer scientists is how to add an entry to the assets side, then add an entry to the liabilities side, and not crash half way through this sequence. Or even worse, have another transaction start half way through. This makes more sense when considered in the context of the millions of entries that a computer might manage, and a very small chance that something goes wrong; eventually something does, and computers cannot handle errors of that nature very well.

复式记账如何实现，这自成一个主题。计算机科学引入了一些概念，比如　*事物*，这些概念被定义为具有原子性、一致性、独立性和持久性(或简称为ACID)的工作单元。计算机科学家的核心问题是如何在资产一侧增加一个条目，然后在负债方面增加一个条目，而不会在这个序列过程中半路崩溃。甚至更糟糕，半路开始了另外一次事物。当考虑到计算机可能管理数百万条目这一情境，而且出错的可能性要很小，这就更有意义了; 最终，有些事情确实会出错，而计算机不能很好地处理这种性质的错误。

For the most part, these concepts simply reduce to "how do we implement double entry bookkeeping" ? As this question is well answered in the literature, we do no more than mention it here.

在大多数情况下，这些概念只会简化为一个问题“我们如何实现复式记账”? 由于这一问题在文献中得到了充分的解答，在这里我们只是简单提一下。

## A Slightly Less Brief History of the Signed Receipt
签名收据的历史，稍微多介绍一点

Recent advances in financial cryptography have provided a challenge to the concept of double entry bookkeeping. The digital signature is capable of creating a record with some strong degree of reliabilty, at least in the senses expressed by ACID, above. A digital signature can be relied upon to keep a record safe, as it will fail to verify if any details in the record are changed.

最近金融密码学的发展对复式记账法的概念提出了挑战。至少在上面的ACID层面上，数字签名能够创造出具有一定可靠性的记录。记录的安全性可以依赖数字签名来确保，因为若修改了记录中的任何细节，它将无法验证通过。

If we can assume that the the record was originally created correctly, then later errors are revealed, both of an accidental nature and of fraudulent intent. (Computers very rarely make accidental errors, and when they do, they are most normally done in a clumsy fashion more akin to the inkpot being spilt than a few numbers.) In this way, any change to a record that makes some sort of accounting or semantic sense is almost certainly an attempt at fraud, and a digital signature makes this obvious.

如果我们可以假定这个记录最初是正确创建的，那么就可以揭露出之后所出现的错误，不论是意外出错，还是出于欺骗而有意为之。(电脑很少会出现意外错误，而当它出错时，它们通常会以一种笨拙的方式进行，更类似打翻墨水瓶，而不会是一些数字错误。)通过这种方式任何对记录的更改，如果具有会计上的意义或者语义上的意义，就几乎可以肯定是欺诈，数字签名使这一点显而易见。

### The Digital Signature and Digital Cash 数字签名和数字现金

A digital signature gives us a particular property, to whit:
数字签名为我们提供了一个特殊的特性，简言之:

> *"at a given point in time, this information was seen and marked by the signing computer."*

> *在某一特定时间点，签名的计算机会见到并且标记这一信息。*

There are several variants, with softer and harder claims to that property. For example,*message digests*with*entanglement*form one simple and effective form of signature, and*public key cryptosystems*provide another form where signers hold a private key and verifiers hold a public key([MB](http://iang.org/papers/triple_entry.html#ref_MB)). There are also many ways to attack the basic property. In this essay I avoid comparisons, and assume the basic property as a reliable mark of having been seen by a computer at some point in time.

根据对该特性的声明的严格程度的不同，会存在几种变体。例如,带*缠结*的*消息摘要*组成了一种简单高效的签名形式, 而 **公钥加密系统**则是另一种形式, 签名者持有私钥，验证者拥有公钥([MB](http://iang.org/papers/triple_entry.html#ref_MB))。还有很多抨击该基础属性的观点（ There are also many ways to attack the basic property）。在这篇文章中，我避免比较，并假定上述基本属性是在某个特定时间点上已经被计算机所见到过的可靠标记。

Digital signatures then represent a new way to create reliable and trustworthy entries, which can be constructed into accounting systems. At first it was suggested that a variant known as the*blinded signature*would enable digital cash[DC](http://iang.org/papers/triple_entry.html#ref_DC). Then,*certificates*would circulate as rights or contracts, in much the same way as the share certificates of old and thus replace centralised accounting systems([RAH](http://iang.org/papers/triple_entry.html#ref_RAH)).

数字签名则代表了一种创建可靠可信赖的条目的新方法，可以将它构建到会计系统中。起初有人建议一个称为*盲签*的变体，将使数字现金成为可能([DC](http://iang.org/papers/triple_entry.html#ref_DC))。然后,证书(*certificates*)将作为权利或合同来流通, 就像旧式的股份证书一样,　从而取代中心化的会计体系([RAH](http://iang.org/papers/triple_entry.html#ref_RAH))。

These ideas took financial cryptography part of the way there. Although they showed how to strongly verify each transaction, they stopped short of placing the the digital signature in an overall framework of accountancy and governance. A needed step was to add in the redundancy implied in double entry bookkeeping in order to protect both the transacting agents and the system operators from fraud.

这些观点在金融密码学中占了一席之地。尽管他们展示了如何对每一笔交易进行强效验证，但他们并没有把数字签名放到会计和治理的总体框架中。所需要的步骤是增加复式记账法中存在的冗余性，以保护交易代理和系统操作人员免受欺诈。

### The Initial Role of a Receipt  收据最初的作用 

![trible_1.png](http://upload-images.jianshu.io/upload_images/1084915-ed93d6e27a0a5c0f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Designs that derived from the characteristics of the Internet, the capabilities of cryptography and the needs of governance led to the development of the*signed receipt*([GH](http://iang.org/papers/triple_entry.html#ref_GH)). In order to develop this concept, let us assume a simple three party payment system, wherein each party holds an authorising key which can be used to sign their instructions. We call these players*Alice*,*Bob*(two users) and*Ivan*(the Issuer) for convenience.


*签名票据*的设计来源于互联网的特点、 密码学的功能和治理的需要([GH](http://iang.org/papers/triple_entry.html#ref_GH))。为了对这一概念进行阐释，让我们假设存在一个简单的三方支付系统，其中每一方持有一个授权密钥，可以用来签署他们的指令。为了方便起见，我们把这些参与者称为*Alice*， *Bob*(两个用户)和*Ivan*(发行人)。

When Alice wishes to transfer value to Bob in some unit or contract managed by Ivan, she writes out the payment instruction and signs it digitally, much like a cheque is dealt with in the physical world. She sends this to the server, Ivan, and he presumably agrees and does the transfer in his internal set of books. He then issues a receipt and signs it with his signing key. As an important part of the protocol, Ivan then reliably delivers the signed receipt to both Alice and Bob, and they can update 
their internal books accordingly.

当Alice想要将某单位的价值或者Ivan(发行人)所管理的合同转移给Bob时，她写下支付指令，进行数字签名，就像在物理世界里处理支票一样。她把这个发给了服务商, Ivan, 假定他同意后，在内部的一组账簿中处理了转账。然后，Ivan填开一张收据，并用他的签名密钥来签署。作为协议的重要组成部分，Ivan可靠地将签名收据传递给Alice和Bob, 他们也相应更新了自己的内部账簿。

### The Receipt*is*the Transaction 收据即交易 

Our concept of digital value sought to eliminate as many risks as possible. This was derived simply from one of the high level requirements, that of being extremely efficient at issuance of value. Efficiency in digital issuance is primarily a function of support costs, and a major determinant of support costs is the costs of fraud and theft.

我们的数字价值的观念旨在尽可能地消除风险。它从一个高层次的需求中产生，即在发行价值方面想要非常高的效率。数字价值发行的效率根本上是支持成本的函数，而欺诈和盗窃的成本则是支持成本的主要决定因素。

One risk that consistently blew away any design for efficient digital value at reasonable cost was the risk of*insider fraud*. In our model of many users and a single centralised server, the issuers of the unit of digital value (as signatory to the contract) and any governance partners such as the server operators are powerful candidates for insider fraud. Events over the last few years such as the mutual funds and stockgate scandals are canonical cases of risks that we decided to address.

任何想要在合理的成本下得到有效率的数字价值的设计，都会面临的一种风险是*内部欺诈的风险*。在我们的多用户和单一中心化服务器的模型中，数字价值单位的发行者(作为合约的签署人)以及任何治理的参与者如服务器运营商，都很有可能成为内部的诈骗人员。过去几年发生的事件比如共同基金和股票丑闻，都是我们所要处理风险的典型案例。

In order to address the risk of insider fraud, the written receipt was historically introduced as being a primary source of evidence. Mostly forgotten to the buying public these days, the purpose of a written receipt in normal retail trade is not to permit returns and complaints by the customer, but rather to engage her in a protocol of documentation that binds the shop attendant into safekeeping of the monies. A good customer will notice fraud by the shop attendant and warn the owner to look out for the monies identified by the receipt; the same story applies to the invention of the cash till or register, which was originally just a box separating the owner's takings from the monies in the shop attendant's pockets. We extend this primary motive into the digital world by using a signed receipt to bind the Issuer into a governance protocol with the users.

为了解决内部欺诈的风险，在历史上引入了书面收据作为主要的证据来源。现在，消费大众中绝大部分人都忘记了，在通常的零售交易中，书面收据的目的不是为了让顾客可以退货和发起投诉，而是让顾客参与到一份文件协议中，使得店员不至于在钱上冬手脚。顾客会注意到店员的欺诈行为，并提醒店主注意收据所记录的钱; 同样的故事也适用于收银机的发明，它最初只是一个盒子，把店主的收入和商店服务员口袋里的钱分开。我们将这个主要动机扩展到数字世界，通过签名收据的使用，使得发行者绑定到用户的治理协议中。

We also go several steps further forward. Firstly, to achieve a complete binding, Alice's original authorisation is also included within the record. The receipt then includes all the evidence of both the user's intention and the server's action in response, and it now becomes a*dominating record*of the event. This then means that the most efficient record keeping strategy is to drop all prior records and keep safe the signed receipt.

我们还向前进了几步。首先，为了实现完整的绑定结合，Alice的原始授权也包含在记录中。收据现在包含了用户意图和服务器的相应行为的所有证据，成了事件的*主导记录*。这意味着，保存记录的最有效的策略是丢掉以前的所有记录，保存好签名收据。

This domination effects both the Issuer and the user, and allows us to state the following principle:
> *The User and the Issuer hold the same information.*

这一主导(的设计)对发行者和用户都有影响，并允许我们陈述如下原则:
> *用户和发行人持有相同的信息*。

As the signed receipt is delivered from Issuer to both users, all three parties hold the same dominating record for each event. This reduces support costs by dramatically reducing problems caused by differences in information.

当签名收据由发行者发送给两个用户时，这三方对每一事件都有着相同的主导记录。这使得由于信息差异所导致的问题显著下降，从而降低了支持成本。

Secondly, we bind a signed contract of issuance known as a*Ricardian Contract*into the receipt([IG2](http://iang.org/papers/triple_entry.html#ref_IG2)). This invention relates a digitally signed document securely to the signed receipt by means of a unique identifier called a*message digest*, again provided by cryptography. It provides strong binding for the unit of account, the nature of the issue, the terms, conditions and promises being made by the Issuer, and of course the identity of the Issuer.

其次,我们把一个叫做**李嘉图合约**的签名发行合约与收据绑定([IG2](http://iang.org/papers/triple_entry.html#ref_IG2))。这一发明通过名为*消息摘要*的独特辨识符(密码学的另一贡献)， 将数字签名文件与签名收据安全关联。这将记账单位、发行的属性(the nature of the issue)、条款、发行人的条件和承诺，当然还有发行人的身份，都强有力的绑定在了一起。

Finally, with these enabling steps in place, we can now introduce the principle:

> *The Receipt*is*the Transaction.*

最后，经过这些步骤铺垫，我们现在可以提出该原则:
> *收据即交易*

Within the full record of the signed receipt, the user's intention is expressed, and is fully confirmed by the server's response. Both of these are covered by digital signatures, locking these data down. A reviewer such as an auditor can confirm the two sets of data, and can verify the signatures.

在签名收据的完整记录中，用户的意图得到表达，并且由服务器的响应完全确认。数字签名将这两者都包含在内，把数据锁定。评审者如审计员，可以确认这两组数据并验证签名。

![trible_2.png](http://upload-images.jianshu.io/upload_images/1084915-ca96cf15cc126d34.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## The Signed Receipt as a Bookkeeping system  作为记账系统的签名收据

The principle of the Receipt as the Transaction has become sacrosact over time. In our client software, the principle has been hammered into the design consistently, resulting in a simplified accounting regime, and delivering a high reliability. Issues still remain, such as the loss of receipts and the counting of balances by the client side software, but these become reasonably tractable once the goal of receipts as transactions is placed paramount in the designer's mind.

随着时间的推移，“收据即交易”的原则已经变得毋庸置疑了。在我们的客户端软件中这一原则一直贯彻在设计之中，带来的好处是简化了会计制度，可靠性也很高。尽管问题仍然存在，比如丢失收据和客户端软件的余额计数问题，但是只要“收据即交易”这一目标在设计者心中处于最重要的位置，上述问题都可以得到相应处理。

### As Single Entry  作为单式记账系统

In order to calculate balances on a related set of receipts, or to present a transaction history, a book would be constructed on the fly from the set. This amounts to using the Signed Receipt as a basis for single entry bookkeeping. In effect, the bookkeeping is derived from the raw receipts, and this raises the question as to whether to keep the books in place.

为了计算一组相关收据的余额，或展现一笔交易的历史，账本可以从这组收据中自动构建出来。这相当于使用了签名收据(Signed Receipt)来作为单式记账法的基础。实际上，账本衍生自原始收据，这就提出了一个问题: 是否还要保留这些账本。

The principles of Relational Databases provide guidance here. The*fourth normal form*directs that we store the primary records, in this case the set of receipts, and we construct derivative records, the accounting books, on the fly<small>[[4NF](http://iang.org/papers/triple_entry.html#ref_4NF)]</small>.

关系型数据库的原则在这里提供了指导。*第四范式*指导我们保留主记录, 即我们这里所说的一组收据,  可以动态创建出派生的记录和账本。

### Recovering Double Entry 复式记账的恢复

Similar issues arise for Ivan the Issuer. The server has to accept each new transaction on the basis of the available balance in the effected books; for this reason Ivan needs those books to be available efficiently. Due to the greater number of receipts and books (one for each user account), both receipts and books will tend to exist, in direct contrast to fourth normal form. A meld between relationally sound sets of receipts and double entry books comes to assist here.

类似的情况也出现在发行人Ivan身上。服务器必须在受影响的账簿中可用账户余额的基础上，接受每一笔新的交易; 因此，Ivan需要这些账本能够有效的使用。由于收据和账簿(每个用户帐户都有一本)的数量较大，收据和账簿倾向于都存在，这与第四范式正好相反。将可靠的关联收据和复式记账簿融合，会有所帮助。

Alice and Bob both are granted a book each within the server's architecture. As is customary, we place those books on the liabilities side. Receipts then can be placed in a separate single book and this could be logically placed on the assets side. Each transaction from Alice to Bob now has a logical contra entry, and is then represented in 3 places within the accounts of the server. Yet, the assets side remains in fourth normal form terms as the liabilities entries are derived, each pair from one entry on the assets side.

在服务器的架构中给予Alice和Bob每人一本账本。按照惯例，我们把这些账本放在负债一侧。收据可以放在单独的一本账本中，这在逻辑上可以放在资产侧。从Alice到Bob的每笔交易现在都有一个逻辑对销分录(contra entry)，在服务器的帐户中有三处呈现。然而，资产侧仍然保持第四范式，因为负债项是派生出来的，每一对都来自资产一侧的一个条目。

By extension, a more sophisticated client-side software agent, working for Alice or Bob, could employ the same techniques. At this extreme, entries are now in place in three separate locations, and each holding potentially three records.

通过扩展，一个更复杂的为Alice和Bob工作的客户端软件代理，可以使用相同的技术。在这种极端情况下，条目现在存在三个不同的位置上，每一个都可能有三条记录。

### Triple Entry Accounting  三式记账法

The digitally signed receipt, with the entire authorisation for a transaction, represents a dramatic challenge to double entry bookkeeping at least at the conceptual level. The cryptographic invention of the digital signature gives powerful evidentiary force to the receipt, and in practice reduces the accounting problem to one of the receipt's presence or its absence. This problem is solved by sharing the records - each of the agents has a good copy.

具有完整交易授权的数字签名收据，至少在概念层面上代表了对复式记账法的巨大挑战。数字签名这一密码学的发明为收据提供了强有力的证据力量，并且在实践中将会计问题减小至一个问题，即收据存在与否。这一问题通过共享记录来解决——每个代理都有一份完整的副本。

In some strict sense of relational database theory, double entry book keeping is now redundant; it is normalised away by the fourth normal form. Yet this is more a statement of theory than practice, and in the software systems that we have built, the two remain together, working mostly hand in hand.

在一些严格的关系数据库理论中，复式簿记是冗余的; 它被第四范式归一化了(normalised away)。然而，这更多的是一种理论阐述而非实践，在我们构建的软件系统中，两者共同存在，联手工作。

Which leads to the pairs of double entries connected by the central list of receipts; three entries for each transaction. Not only is each accounting agent led to keep three entries, the natural roles of a transaction are of three parties, leading to three by three entries.

这就导致了复式账目由收据的中心列表所链接; 每笔交易有三个条目。不只每个会计代理要保留三份条目，一笔交易天然就是包含三方的，这就使得三方各自有三份条目（leading to three by three entries.）。

We term this*triple entry bookkeeping*. Although the digitally signed receipt dominates in information terms, in processing terms it falls short. Double entry book keeping fills in the processing gap, and thus the two will work better together than apart. In this sense, our term of triple entry bookkeeping recommends an advance in accounting, rather than a revolution.

我们为之命名为“三式记账法”。虽然数字签名收据在信息方面占主导作用，但在处理方面它却并不擅长。复式簿记填补了处理上的空白，因此两者一起工作会比分开更好。从这个意义上说，我们的“三重记账法”的概念是对会计的改进建议，而非革命。

### Software Considerations 软件方面的考虑

The precise layout of the entries in software and data terms is not settled, and may ultimately become one of those ephemeral*implementation issues*. The signed receipts may form a natural asset-side contra account, or they may be a separate non-book list underlying the bookkeeping system and its two sides.

软件和数据方面的条目没有得到精确布局，可能会最终成为短暂的*实现问题*之一。签名收据可以形成一个自然的资产侧对销账户，或者可能会是簿记系统和(资产和负债)两侧的一个底层的单独非账簿列表。

Auditing issues arise where construction of the books derives from the receipts, and normalisation issues arise when a receipt is lost. These are issues for future research.

从收据构建账簿会出现审计方面的问题；而当收据丢失时会计标准化问题就会出现。这些都是未来要研究的问题。

Likewise, it is worth stating that the technique of signing receipts works both with private key signatures and also with entanglement message digest signatures; whether the security aspects of these techniques is adequate to task is dependent on the business environment.

同样，值得说明的是，签名收据的技术既适用于私钥签名，也适用于缠结消息摘要签名(entanglement message digest signatures); 这些技术在安全方面是否胜任要视业务环境而定。

### Roles of the Agents 代理的角色

It will be noted that the above design of triple entry bookkeeping assumed that Alice and Bob were agents of some independence. This was made possible, and reflected the usage of the system as a digital cash system, and not as a classical accounting system.

有人会指出，上述三式记账法的设计假设是Alice和Bob是某些独立的代理。这有可能，并反映了将系统用作数字现金系统的用途，而非用作传统的会计系统。

Far from reducing the relevance of this work to the accounting profession, it introduces digital cash as an alternate to corporate bookkeeping. If an accounting system for a corporation or other administrative entity is recast as a system of digital cash, or*internal money*, then experience shows that benefits accrue to the organisation.

这并没有降低该项工作与会计职业的相关性，而是将数字现金作为公司账簿的替代品。如果一个公司或其他行政实体的会计系统被重塑为数字现金系统，或*内部货币*，那么经验表明该组织将因此获益。

Although the core of the system looks exactly like an accounting system, each department's books are pushed out as digital cash accounts. Departments no longer work so much with budgets as have control over their own corporate money. Fundamental governance control is still held within the accounting department by dint of their operation of the system, and by the limited scope of the money as only being usable within the organisation; the accounting department might step in as a*market maker*, exchanging payments in internal money for payments in external money to outside suppliers.

虽然这个系统的核心看起来就像一个会计系统，但每个部门的账簿都让位给了数字现金账户。各部门不再像控制自己的公司资金那样在预算之内工作。借助于会计的系统操作，以及由于资金只能在组织内部使用的限制，基本的管理控制仍由会计部门内部把控;会计部门可能会作为一个*做市商*介入，将内部资金的支付转换成对外部供应商的支付。

We have operated this system on a small scale. Rather than be inefficient on such a small scale, the system has generated dramatic savings in coordination. No longer are bills and salaries paid using conventional monies; many transactions are dealt with by internal money transfers and at the edges of the corporation, formal and informal agents work to*exchange*between internal money and external money. Paperwork reduces dramatically, as the records of the money system are reliable enough to quickly resolve questions even years after the event.

我们已经小规模地运行了这个系统。该系统在如此小的规模上并没有造成效率低下，而是在协调方面产生了巨大的节约。不再用传统货币支付账单和工资; 许多交易都是通过内部资金转移处理的，在公司的边界处，正式和非正式的代理人对内部资金和外部资金进行交换。由于数字货币系统的记录足够可靠，即使在事件发生多年后也能够迅速解决问题，因此文书工作大幅减少。

The innovations present in internal money go beyond the present paper, but suffice to say that they answer the obvious question of why this design of triple entry accounting sprung from the world of digital cash, and has relevence back to the corporate world.

内部资金的创新超出了本篇论文的范围，但可以肯定的是，这回答了一个显而易见的问题，即为什么三式记账法起源于数字现金世界，又与商业世界相关联。

## Patterns of Commerce 商业模式

Todd Boyle looked at a similar problem from the point of view of small business needs in an Internet age, and reached the same conclusion - triple entry accounting([1](http://iang.org/papers/triple_entry.html#ref_1)). His starting premises were that:

Todd Boyle 从互联网时代小型业务的角度，对类似的问题进行了探讨，然后得到了相同的结论 -- 三式记账法。他的前提是:

1.  The major need is not accounting or payments, per se, but patterns of exchange - complex patterns of trade;
2.  Small businesses could not afford large complex systems that understood these patterns;
3.  They would not lock themselves into proprietary frameworks;

1.  主要的需求不是会计或支付, 而是交换的模式 -- 交易的复杂模式;
2.  小公司承担不起应用这些模式的大型复杂系统;
3.  他们不想将自己锁定在专有框架中;

From those foundations, Boyle concluded that therefore what is needed is a shared access repository that provides arms-length access. Fundamentally, this repository is akin to the classic double-entry accounting ledger of transaction rows ("GLT" for General Ledger - Transactions), yet its entries are dynamic and shared.

以此为基础，Boyle总结，因此，需要的是一个可共享访问的存储库，能够方便的访问。根本上说，这个存储库类似于典型的复式记账法分类帐，由交易行组成("GLT" ，代表总分类帐-交易)，但是它的条目是动态和共享的。

Simple examples will help. When Alice forms a transaction, she enters it into her software. Every GLT transaction requires naming her external counterparty, Bob. When she posts the transaction, her software stores it in her local GLT and also submits it to the shared repository service's GLT.

一个简单的例子会有所帮助。当Alice有了一笔交易时，她将交易输入自己的软件中。每笔GLT交易都需要写明她的外部交易对方，Bob。当她提交了交易时，软件将其存储在本地的GLT中，并将其提交给共享存储库服务的GLT。

The Shared Transaction Repository ("STR") then forwards the transaction on to Bob. Both Bob and Alice are now expected to store the handle to the transaction as an index or stub, and the STR then stores the entire transaction.

共享交易存储库(“STR”)然后将交易转发给Bob。现在，预期Bob和Alice会将交易的处理作为索引或存根存储起来，然后STR将整笔交易存储起来。

Boyle's ideas are logically comparable to Grigg and Howland's, although they arive from different directions (the STR is Grigg's Ivan, above) and are not totally equivalent. Where the latter limited themselves to payments, the accuracy of amounts, and protection with hard cryptographic shells, Boyle looked at wider patterns of transactions, and showed that the STR could mediate these transactions, if the core shared data could be extracted and made into a single shared record. Boyle's focus was on the economic substance of the transaction.

Boyle的观点在逻辑上与 Grigg 和 Howland的观点类似，尽管他们从不同的方向出发(Boyle文中的STR 就是 Grigg 上文中的 Ivan)，且并不完全相同。后者将研究范围限定在交易、数额准确性、具有坚实加密学外壳的保护等方面，Boyle 则研究了更广泛的交易模式，并表明如果可以将核心共享数据提取并转换为单条共享记录的话，则可以用STR协调这些交易。Boyle的关注点在于交易的经济实质。

### Extending the Humble Invoice  对微不起眼的发票的延伸

Imagine a simple invoicing procedure. Alice creates an invoice and posts it to her software (GLT). As she has named Bob, the GLT automatically posts it to Ivan, the STR, and he forwards it to Bob. At this point Bob has a decision to make, accept or reject. Assuming acceptance, his software can then respond by sending an acceptance message to Ivan. The STR now assembles an accepted invoice record to replace the earlier speculative invoice record and posts that threeways. At some related time (to do with payment policy) Bob also posts a separate transaction to pay for the invoice. This could operate in much the same way as a separate transaction, linking directly to the original invoice.

想象一个简单的发票程序。Alice创建了一张发票并将其提交给她的软件(GLT)。她指定了Bob，GLT会自动将其发送给Ivan，即STR(共享交易存储库), 并将其转发给Bob。此时，Bob需要决定，接受或拒绝。假设接受，他的软件可以通过向Ivan发送一条接收信息来回应。STR 现在收集了一份已接受的发票记录，以取代先前的提议性的(speculative)发票记录, 并将其提交给三方。在某个相应的时间(与支付政策有关)Bob也会发布一笔支付发票的交易。这可以像单独的事务一样操作，直接链接到原始的发票。

Now, as the payment links back, and the invoice is a live transaction within the three entries in the three accounting systems, it is possible for a new updated invoice record to refer back to the payment activity. When the payment clears, the new record can again replace the older unpaid copy and promulgate to all three parties.

现在，因为支付又链接回了发票，并且发票在三式记账法中是三个条目中的实时事务，所以更新的发票记录可能会指回到支付行为去。当付款结清完成时，新记录可以再次取代旧的未付款副本，并向所有的三方公布。

### Patterns of Transactions 交易模式

Software could be written to facilitate and monitor this flow and similar flows. If the payments system is sufficiently flexible, and integrated with the needs of the users, if might be possible to merge the above invoice with the payment itself, at the Receipts level. Seen in this light, the Signed receipt of Ricardo is simply the smallest and simplest pattern within the more general set of patterns. We could then suggest that the narrow principle of*the Receipt is the Transaction*could be extended into *The Invoice is the Transaction*.

可以编写软件以促成和监视这一交易流和类似的流程。如果支付系统具有足够的灵活性并与用户的需求相结合，也许可以在收据级别上，将上述发票与付款本身合并。从这个角度看，李嘉图合约的签名收据只是一组更普遍的模式中的一个最小化最简单的模式。 我们可以提议"收据即交易"的狭义原则，可以扩展为*发票即交易*的原则。

A particular transaction in business almost never stands alone. They come in patterns. For example offers and acceptances form a wider transaction but seldom encapsulate the entire fulfillment and payment cycle. Even if there has been a payment accompanying a PO message, the customer then waits for fulfillment.

在商业上一笔特定的交易几乎从不会单独存在。他们会形成模式。例如，要约与承诺组成了更广义的交易，但很少能覆盖整个的履约和支付流程。即使付款伴随PO信息一起，客户也需要等待配送。

There is a large body of science and literature built around these*patterns of transactions*. These have been adopted by the Business Process workgroup of ebXML and other standards bodies, where they are called "Commercial Transactions." Where however the present work distinguishes itself is in breaking down these transactions into the atomic elements. It is to that we now turn.

有大量的科学和文献围绕着这些*交易模式*展开。这些已经被Business Process workgroup of ebXML和其他标准组织所采用，称之为为“商业交易”。然而，目前的工作与众不同之处在于，会将这些交易分解为原子化的元素。我们现在转向这一点。

## The Requirements of Triple Entry Accounting 三式记账法的要求

The implementation of Triple Entry Accounting will in time evolve to support patterns of transactions. What has become clear is that double entry does not sufficiently support these patterns, as it is a framework that breaks down as soon as the number of parties exceeds one. Yet, even as double entry is "broken" on the net and unable to support commercial demands, triple entry is not widely understood, nor are the infrastructure requirements that it imposes well recognised.

三式记账法的实现将会及时演变以支持交易模式。现在已经清楚，复式记账法并不能充分地支持这些模式，因为一但参与者的数量超出一个，这个框架就会崩溃。然而，即使复式记账法在网络上"崩溃"，不能支持商业需求，三式记账法也并没有得到广泛理解，三式记账法对基础设施的需求也没有得到很好的辨别。

Below are the list of requirements that we believed to be important ([2](http://iang.org/papers/triple_entry.html#ref_2)) ([3](http://iang.org/papers/triple_entry.html#ref_3)).

下面的需求列表是我们认为比较重要的.

**1  Strong Pseudonymous, At Least**. As there are many cycles in the patterns, the system must support a clear relationship of participants. At the minimum this requires a nymous architecture of the nature of Ricardo or AADS. (This requirement is very clear, but space prevents any discussion of it.)

**1 强匿名性，这是最起码的**。由于模式中有许多循环，系统必须支持参与者之间的清晰关系。至少需要一个具有Ricardo 或者 AADS的特性的署名架构。(这个要求很清楚，但限于篇幅不作讨论了。)

**2 Entry Signing**. In order to neutralise the threats to and by the parties, a mechanism that freezes and confirms the basic data is needed. This is signing, and we require that all entries are capable of carrying digital signatures (see 1, above, which suggests public key signatures).

**2 条目签名**。为了消除源自各方和施于各方的威胁，需要一种冻结和确认基本数据的机制。这就是签名，我们要求所有的条目都能携带数字签名(上文1中的提议是公钥签名)。

**3  Message Passing**. The system is fundamentally one of message passing, in contrast to much of the net's connection based architecture. Boyle recognised early on that a critical component was the generic message passing nature, and Systemics proposed and built this into Ricardo over the period 2001-2004 ([4](http://iang.org/papers/triple_entry.html#ref_4)).

**3 消息传递**。 该系统从根本上来说是一个消息传递的系统，这与大多数网络的基于连接的架构形成了对比。Boyle 早就认为通用的信息传递特性是一个核心的组成部分，在2001-2004年期间，Systemics 公司计划并将其构建到Ricardo合约之中。

**4  Entry Enlargement and Migration**. Each new version of a message coming in represents an entry that is either to be updated or added. As each message adds to a prior conversation, the stored entry needs to enlarge and absorb the new information, while preserving the other properties.

**4  条目的扩张和迁移**。传入消息的每个新版本都表示，一个条目要么更新，要么添加。当每个消息添加到先前的会话时，存储的条目需要扩张以吸收新信息，同时保留其他属性。

**5 Local Entry Storage and Reports**. The persistent saving and responsive availability of entries. In practice, this is the classical accounting general ledger, at least in storage terms. It needs to bend somewhat to handle much more flexible entries, and its report capabilities become more key as they conduct instrinsic reconciliation on a demand or live basis.

**5  本地条目的存储和报告**。条目的持久保存和有效响应性。实际上，这是典型的会计总分类账，至少在存储方面是这样。它需要稍微改动以处理更灵活的条目，并且其报告能力变得更加关键，因为要在需求和动态的基础上要进行内部的协调。

**6 Integrated Hard Payments**. Trade can only be as efficient as the payment. That means that the payment must be at least as efficient as every other part; which in practice means that a payment system should be built-in at the infrastructure level. C.f., Ricardo.

**6  整合硬性支付**。交易的效率只会跟支付一样。这意味着支付必须至少和其他部分一样有效; 实际上这意味着支付系统应该内置在基础设施的级别。比如, Ricardo合约。

**7 Integrated Application-Level Messaging**. As distinct to the messaging at the lower protocol levels (1 above), there is a requirement for Alice and Bob to be able to communicate. That is because the vast majority of the patterns turns around the basic communications of the agents. There is no point in establishing a better payment and invoice mechanism than the means of communication and negotiation. This concept is perhaps best seen in the SWIFT system which is a messaging system, first and foremost, to deliver instructions for payments.

**7 整合应用层消息**。与较低的协议级别(上述第一条)的消息传递不同，Alice和Bob需要能够进行通信。这是因为绝大多数的模式都围绕着代理的基本交流展开。把支付和发票机制做得比交流和协商的方式更好，是没有意义的。这个概念在SWIFT系统中可能最为明显，它首先是一个消息传递系统，传递支付指令。

## Conclusion 结论

Double Entry bookkeeping provides evidence of intent and origin, leading to strategies for dealing with errors of accident and fraud. The financial cryptography invention of the signed receipt provides the same benefits, and thus challenges the 800 year reign of double entry. Indeed, in evidentiary terms, the signed receipt is more powerful than double entry records due to the technical qualities of its signature.

复式簿记提供了意图和来源的证据，有策略可以去处理由失误和欺诈引起的错误。签名收据的金融密码学发明提供了同样的好处，挑战了已存在800年的复式记账法的帝国。事实上由于签名的技术质量，在证据方面签名收据比复式记账法记录更为有效。

There remain some weaknesses in strict comparison with double entry bookkeeping. Firstly, in the Ricardo instantiation of triple entry accounting, the receipts themselves may be lost or removed, and for this reason we stress as a principle that*the entry is the transaction*. This results in three active agents who are charged with securing the signed entry as their most important record of transaction.

与复式记账法严格比较，仍存在一些不足之处。首先，在三式记账法的李嘉图实例中，票据本身可能会丢失或被删除，因此我们强调了原则，*记录即交易*。结果是参与的三方代理被要求要将签名条目作为他们最重要的交易记录保护好。

Secondly, the software ramifications of the triple entry system that are less convenient than that offered by double entry bookkeeping. For this reason, we expand the information held in the receipt into a set of double entry books; in this way we have the best of both worlds on each node: the evidentiary power of the signed entries and the convenience and local crosschecking power of the double entry concept.

其次，三式记账法的相应软件没有复式记账法所提供的软件那么容易使用。为此，我们将收到的信息扩大为一套复式账簿; 这样，我们在每个节点上都能够将两者的优势结合起来: 签名条目的证据性能力，以及复式记账的本地化交叉验证的能力。

Both of these imperitives meld signed receipts in with double entry bookkeeping. As we end up with a logical arrangement of three by three entries, we feel the term*triple entry bookkeeping*is useful to describe the advance on the older form.

这两者都将签名收据与复式记账法结合。我们得到的结果是一个三乘三条目的合逻辑的安排，因此，我们认为“三式记账法”这个词可以用来描述相对旧有形式的进步。

### Drawing in the Agents  吸引代理

To fully benefit from triple entry bookkeeping, we have to expand accounting systems out to agents and offer them direct capabilities to do transactions. That is, we make the agents stakeholders by giving them internal money ([5](http://iang.org/papers/triple_entry.html#ref_5)). Use of digital cash to do company accounts empowers the use of this concept as a general replacement for accounting using books and departmental budgets, and is an enabler for verifying and auditing the centralised accounts system by way of signed receipts.

为了从三式记账法中充分受益，我们必须将会计系统扩展给代理，并为他们提供交易的直接能力。即，我们通过给予代理内部现金，让他们也成为利益相关方。使用数字现金进行公司会计管理，使得这一概念成为使用账簿和部门预算的会计体系的通用替代品， 通过签名收据的方式，促成对中心化会计系统的核查和审计。

### Solving Frauds 解决欺诈问题

Once there, governance receives substantial benefits. Accounts are now much more difficult to change, and much more transparent. It is our opinion that various scandals and failures of governance would have been impossible given these techniques: the mutual funds scandal would have shown a clear audit trail of transactions and thus late timing and otherwise perverted or dropped transactions would have been clearly identified or eliminated completely([NG](http://iang.org/papers/triple_entry.html#ref_NG)). The emerging scandal in the USA known as*Stockgate*would have been impossible as forgery of shares and value for manipulative trading purposes is revealed by signed receipts. Likewise, Barings would still be a force in investment banking if accounts had been organised around easily transparent digital cash with open and irreducible signed receipts that evidence invisible accounts (*88888*). Enron style scandals would have permitted more direct "follow the money" governance lifting the veil on various innovative but economically meaningless swaps.

一旦上述实现了，管理将从中获得巨大收益。现在，账户变得更加难以改变，而且更加透明。我们认为，如果这些技术存在的话，各种丑闻和治理失败问题将不复存在:  共同基金丑闻将会留下清晰可见的痕迹供审计追踪,  因此之后择时交易和其他形式的篡改或删除的记录，就能够被清晰地辨认出来，或者被彻底清除掉。在美国被称为“Stockgate”的丑闻将会成为不可能，因为处于操纵交易的目的而伪造股票和价格，都能通过签名收据得到披露。同样地，如果围绕着简单的数字现金来组织会计体系，有着公开不可消除的签名收据，隐匿的账户就会留下证据(*88888*)，那么巴林银行就不会倒闭，现在仍然会是投资银行中的实力派。安然(Enron)类型的丑闻，将允许进行更直接的“跟踪金钱式”的管理方式，把蒙在各种创新但在经济上毫无意义的互换把戏的面纱揭开。

## References 参考文献

 **[TB]**A draft form of this paper credited Todd Boyle as an author, but this was later withdrawn at his request due to wider differences between the views.

**[LP]**Friar Luca Pacioli, [Summa de Arithmetica, Geometria, Proportioni et Proportionalita](http://www.acsac.org/2001/papers/110.pdf) 1494, Venice.

**[IG1]**Ian Grigg "[The Twilight Zone](http://www.financialcryptography.com/mt/archives/000442.html)," Financial Cryptography blog 16th April 2005

**[MB]**Entanglement is discussed in: Petros Maniatis and Mary Baker, "Secure History Preservation through Timeline Entanglement," Proc. 11th USENIX Security Symposium,  August 2002.

**[DC]**David Chaum, "Achieving Electronic Privacy," Scientific American, v. 267, n. 2 Aug 1992.

**[RAH]**Robert A. Hettinga "[The Book-Entry/Certificate Distinction](http://www.shipwright.com/rants/rant_02.html)" 1995, Cypherpunks

**[GH]**Gary Howland "[Development of an Open and Flexible Payment System](http://www.systemics.com/docs/sox/overview.html)1996, Amsterdam, NL.

**[IG2]**Ian Grigg "[The Ricardian Contract](http://iang.org/papers/ricardian_contract.html),"<cite>First IEEE International Workshop on Electronic Contracting(WEC) 6th July 2004

**[4NF]**E.F. Codd, "[A Relational Model of Data for Large Shared Data Banks](http://iang.org/papers/triple_entry.html),"Comm. ACM 13 (6), June 1970, pp. 377-387.

**[1]**Todd Boyle, "[GLT and GLR: conceptual architecture for general ledgers](http://ledgerism.net/GLT-GLR.htm)," Ledgerism.net, 1997-2005.

**[2]**Todd Boyle, "[STR software specification](http://www.ledgerism.net/STR.htm)," Goals, 1-5\. This section adopts that numbering convention.

**[3]**Ian Grigg, various design and requirements documents, Systemics, unpublished.

**[4]**A substantial part of the programming and design was conducted by Edwin Woudt (first demo, SOX layers, UI) and Jeroen van Gelderen (message passing client architecture).

**[5]**Using internal money instead of an accounting system is not a new idea but has only been recently experienced: Ian Grigg,[How we raised capital at 0%, saved our creditors from an accounting nightmare, gave our suppliers a discount and got to bed before midnight.](http://iang.org/rants/systemics_psd.html) Informal essay (rant), 7 Jul 2003.

**[NG]**James Nesfield and Ian Grigg "[Mutual Funds and Financial Flaws](http://iang.org/papers/mutual_funds.html)," U.S. Senate Finance Subcommittee 27th January, 2004

--------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

荆凯(shuke0327) 区块链技术爱好者，程序员，坚信区块链将会改变潮水的方向，欢迎关注我的公众号: 增长之道

本文由币乎社区（bihu.com）内容支持计划奖励。

版权所有，转载需完整注明以上内容。

----------------------------------------------------