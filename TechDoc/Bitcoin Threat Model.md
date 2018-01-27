> 本文翻译自：https://github.com/JWWeatherman/bitcoin_security_threat_model/blob/master/README.md
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator) [鱼](https://github.com/oscnet)
>
> 翻译时间：2018-1-20
>
> 本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。


![alt text](http://res.cloudinary.com/loristeeth/image/upload/c_scale,w_800/v1510175135/tm_big_logo_wxtnbt.png "Bitcoin code vortex")
# Bitcoin Threat Model
### A security review of the Bitcoin cryptocurrency
# 比特币威胁模型
### 对加密货币比特币的安全审查

---

# Motivation
The Bitcoin threat model is intended to help developers, investors and users better understand the security of Bitcoin. Threats are assumed to be any activity designed to prevent Bitcoin from accomplishing its mission to become cash (including a unit of account). Under each threat is a description of the threat, the safety features designed to protect against the threat, and any past examples of attacks executing the threat. Bitcoin can be attacked directly by making the software behave in a way that is ineffective as cash or by attacking the humans that are needed to support the software.

# 动机
比特币威胁模型旨在帮助开发者，投资者和用户更好地理解比特币的安全性。所有旨在阻止比特币实现现金（包括用作记帐单位，货币的主要用途之一，译者注）功能的任何活动都视为威胁。在每种威胁之下是对威胁的描述，为防范威胁而设计的安全特性以及任何执行威胁攻击的例子。对比特币的直接攻击可以通过影响软件运行而使比特币的功能失效，也可以直接攻击比特币软件的支持人员。

# Conclusion
Currently there are no threats that have been identified that could prevent or significantly slow adoption of Bitcoin as cash. However, new threats could be discovered or existing threats may prove to be more impactful. Given the impact Bitcoin is likely to have, and the frequency and intensity of past attacks, this remains a real possibility.

# 结论
目前还没有任何已经确定的威胁可以阻止或显着减缓比特币作为现金使用的功能。但是，可能会发现新的威胁，或者现有的威胁可能会变得更有影响力。考虑到比特币可能产生的影响以及过去攻击的频率和强度，这仍然具有现实的可能性。

# Introduction
The Bitcoin threat model is intend to help developers, investors and users better understand the security of Bitcoin. Threats are assumed to be any activity designed to prevent Bitcoin from accomplishing its mission to become cash (including a unit of account).

Under each threat is a description of the threat, the safety features designed to protect against the threat, and any past examples of attacks executing the threat. Bitcoin can be attacked directly by making the software behave in a way that is ineffective as cash or by attacking the humans that are needed to support the software.

# 介绍
比特币威胁模型旨在帮助开发者，投资者和用户更好地理解比特币的安全性。威胁定义为旨在阻止比特币实现其成为现金（包括记帐单位）功能的任何活动。

在每种威胁之下是对威胁的描述，为防范威胁而设计的安全特性以及任何执行威胁攻击的例子。
对比特币的直接攻击可以通过影响软件运行而使比特币现金功能失效，也可以直接攻击比特币软件的支持人员。

Threats are categorized as one of the following:

* **Prevent Adoption** - These threats have a reasonable chance of preventing Bitcoin from being adopted as cash.
* **Significantly Slow Adoption** - These threats have a reasonable chance of significantly slowing the adoption of Bitcoin as cash.
* **No Impact on Adoption** - These threats do not have a reasonable chance of significantly slowing the adoption of Bitcoin as cash.

Currently there are no threats that have been identified that could prevent or significantly slow adoption of Bitcoin as cash. However, new threats could be discovered or existing threats may prove to be more impactful. Given the impact Bitcoin is likely to have, and the frequency and intensity of past attacks, this remains a real possibility.

威胁被分类为以下之一：

* **阴止使用** - 这些威胁存在合理的机会阻止比特币作为现金使用。
* **显著减慢使用率** - 这些威胁存在合理的机会，能显著减慢比特币作为现金的使用率。
* **对使用没有影响** - 这些威胁没有合理的机会显著减慢比特币作为现金的使用率。

目前还没有任何已经确定的威胁可以阻止或显着减缓比特币作为现金使用的功能。但是，可能会发现新的威胁，或者现有的威胁可能会变得更有影响力。考虑到比特币可能产生的影响以及过去攻击的频率和强度，这仍然具有现实的可能性。

---

# Software Threats
Software threats are threats that take advantage of security flaws within the software to prevent Bitcoin from becoming cash.

# 软件威胁
软件威胁是利用软件中的安全漏洞来阻碍比特币作为现金使用的威胁。

## Creating a transaction
Owners of Bitcoin can send their Bitcoin to another user by creating a digitally signed transaction and broadcasting it to the Bitcoin network. The piece of software that creates transactions is called a "wallet." For a transaction to be accepted by the network it must be digitally signed using the owners private key. Keeping the private keys secret is also handled by the Bitcoin wallet software.

## 创建交易
比特币的所有者可以通过创建一个数字签名的交易并将其传播到比特币网络来将他们的比特币发送给另一个用户。创建交易的软件被称为“钱包”。对于网络接受的交易，必须使用所有者的私钥进行数字签名。保持私钥的秘密性也是由比特币钱包软件来实现。

### An attacker could steal a users private keys to steal their bitcoin.
If an attacker can gain access to a users private key he can send the associated bitcoin to himself.

### 攻击者可以窃取用户的私钥来窃取比特币。
如果攻击者可以访问用户的私钥，他就可以将其相关的比特币发送给自己。

**Safety Features**
* Because each Bitcoin user maintains his own private keys an attacker can only steal from one person at a time. This greatly reduces the incentive for a attacker because in most centralized systems such as banks, credit reporting agencies and brokerages a successful attack could result in access to the funds of thousands of users.

* As long as thefts of private keys is not systemic it will not prevent the adoption of Bitcoin as cash. This is especially true as long as theft of private keys remains more difficult than the theft government money.

* Hardware wallets are gaining in popularity and they make theft of private keys nearly impossible without physical access to the device and password or pin number. This is a level of security that is far higher than is common in banking.

**安全特性**
* 由于每个比特币用户都拥有自己的私钥，因此攻击者毎次只能窃取一个人的私钥。这大大降低了攻击者的积极性，因为在大多数中心化系统（如银行，信用报告机构和经纪商）中，一次成功的攻击可能导致数千用户的资金失窃。

* 只要盗用私钥不是系统性的，就不能阻止比特币的使用。尤其在窃取私钥比盗窃政府资金更为困难的情况下。

* 硬件钱包越来越受欢迎，在不能物理访问设备和没有密码或PIN码时，私钥的窃取几乎是不可能的。这样的安全水平远高于普通的银行业。

**Past Attacks**
* Bitcoin owner has private keys stolen in 2011 when keeping private keys safe was much harder,
https://bitcointalk.org/index.php?topic=16457.msg214423#msg214423
* Bitcoin owners give away their private keys on Sheep (that is the name of the service,
https://www.theverge.com/2013/12/2/5167670/sheep-marketplace-bitcoin-heist-nets-at-least-5-million-owners-blamed
* Bitcoin owners give away their private keys on MtGox, https://www.wired.com/2014/03/bitcoin-exchange/

**曾有的攻击**

* 2011年有比特币所有者私钥被盗，当时保持私钥安全还比较困难
https://bitcointalk.org/index.php?topic=16457.msg214423#msg214423
* Sheep（一个在线地下集市，译者注）比特币私钥被盗，
https://www.theverge.com/2013/12/2/5167670/sheep-marketplace-bitcoin-heist-nets-at-least-5-million-owners-blamed
* MtGox 门头沟事件
https://www.wired.com/2014/03/bitcoin-exchange/

**No Impact on Adoption**
* Although users need to be careful to keep their private keys safe, Bitcoin remains the most secure digital asset.

**对使用没有影响**
* 尽管用户需要小心保管私钥，但比特币仍然是最安全的数字资产。

### An attacker could use a quantum computer to guess everyone's private keys.
If an attacker could gain access to everyone's private keys he could steal every bitcoin.

### 攻击者可以使用量子计算机来猜测每个人的私钥。
如果攻击者可以获取私钥，他就可以窃取所有比特币。

**Safety Features**
* The private key is so large that it would take more energy than is produced by the sun in its entire lifetime to power a computer capable of guessing it.

**安全特性**
* 私匙拥有足够的长度，以至于计算机需要比太阳在整个生命周期中所产生的更多的能量才能计算。

**Past Attacks**
* There have been no known attempts to perform this attack.

**曾有的攻击**
* 目前没有发现已知的此类攻击尝试


**No Impact on Adoption**
* This attack is probably impossible. It is very unlikely that quantum computing or any other field of scientific research will result in such a drastic rewriting of our understanding of the basic laws of physics that guessing private keys would become possible.

**对使用没有影响**
* 这种攻击几乎是完全不可能的。量子计算或任何其他科学领域的研究不可能导致我们对物理学基本定律理解的大幅改写，从而使猜测私钥成为可能。

## Broadcasting a transaction to the network
After a transaction is created it is relayed over the Bitcoin network.

## 广播交易到网络
创建交易后，交易通过比特币网络进行转发。

### An attacker could broadcast a fake transaction to the network in order to steal bitcoins.
If an attacker could convince the network that a transaction was legitimate he could transfer bitcoins from a victims balance to his own account.

### 攻击者可以通过向网络广播伪造的交易来窃取比特币
如果攻击者可以让网络认为此交易是合法的，他可以将比特币从受害者帐号转移到他自己的帐户。

**Safety Features**

* The Bitcoin network will reject any transactions that are not digitally signed by the private keys of the owner of the bitcoins.
* If a flaw in the digital signature mechanism is discovered the Bitcoin network could consider any transactions after the flaw was discovered to be invalid. This would be far from ideal as some legitimate transactions could be ignored, but this possibility reduces the incentives for attackers to attempt this attack.
* Digital signatures are a fundamental building block of computer security and have proven to be effective and secure in many applications including Bitcoin.

**安全特性**

* 比特币网络将拒绝任何未通过比特币所有者的私钥进行数字签名的交易。
* 一旦发现数字签名机制存在缺陷，比特币网络可以在发现缺陷后视任何交易为无效。虽然一些合法的交易也将被忽略，这种情况远非完美，但是这种可能性的存在减少了攻击者尝试这种攻击的理由。
* 数字签名是计算机安全的基本组成部分，在包括比特币在内的许多应用中已被证明是有效和安全的。

**Past Attacks**
* There have been no known attempts to perform this attack.

**曾有的攻击**
* 没有发现已知进行这种攻击的尝试。

**No Impact on Adoption**
* It is unlikely that a flaw will be discovered that allows an attacker to forge a digital signature.

**对使用没有影响**
* 允许攻击者伪造数字签名的缺陷不太可能被发现。

### An attacker could broadcast a large number of transactions that pay himself in order to clog the network.
Because anyone can broadcast a transaction on the Bitcoin network it is possible for an attacker to broadcast a large number of transactions that transfer bitcoins to themselves. The Bitcoin network has no way to distinguish between legitimate transactions and transactions created with the intention of clogging the network. If the network is unable to process legitimate transactions Bitcoin would not be suitable as cash.

### 攻击者可以通过广播大量的付费交易来阻塞网络。
由于任何人都可以在比特币网络上广播交易，因此攻击者可能会广播大量将比特币发送到自己的交易。比特币网络将无法区分合法交易和以堵塞网络为目的而创建的交易。如果网络无法处理合法交易，比特币将不合适作为现金来使用。

**Safety Features**
* Bitcoin transactions are processed in order of the fees associated with the transaction. This makes congesting the network with frivolous transactions costly.
* Layer two and side chain networks allow Bitcoin transactions to be consolidated. This decreases demand for space for transactions making more room for both legitimate and frivolous transactions.
* Layer two and side chains technologies allow Bitcoin transactions to be consolidated. This increases the amount of fees that can be paid for legitimate transactions since each single transaction actually represents a batch of transactions. This will make this attack more expensive as frivolous transactions would have even more difficulty outbidding legitimate transactions.
* Bitcoin limits the number of transactions that can be processed using a "block size" limit. This ensures that clogging the network would require competing for space through fees.

**安全特性**
* 比特币交易按交易费(矿工费)高低顺序处理。这使得造成网络繁琐的无价值的交易成本高昂。
* 第二层和侧链网络使得比特币可以合并交易。为合法交易和无价值的交易提供了更多空间，这减少了对交易空间的需求，
* 第二层和侧链技术使得比特币可以合并交易。因为每一笔交易实际上代表了一批交易，这样就增加了可以为合法交易支付的费用。也将使这种攻击显得更为昂贵，使得无价值的交易会更加困难，因为它出的矿工费得要比合法交易来得高。
* 比特币使用“块大小”限制了处理交易的数量。这确保为了堵塞网络，需要通过交易费来竞争交易的存储空间。

**Past Attacks**
* Bitcoin spam attacks in 2015-2017,
https://bravenewcoin.com/news/bitcoin-spam-attack-stressed-network-for-at-least-18-months-claims-software-developer/
* Bitcoin investor is fearful this will prevent Bitcoin from becoming cash,
https://steemit.com/cryptocurrency/@superfreek/btc-spam-attack-200-000-unconfirmed-transactions-halts-bitcoin
* Bitcoin spam attack is used as support for attack 2.5.3.,
https://bitcoinmagazine.com/articles/curious-case-bitcoins-moby-dick-spam-and-miners-confirmed-it/

**过去的攻击**
* 比特币垃圾邮件攻击2015-2017， https://bravenewcoin.com/news/bitcoin-spam-attack-stressed-network-for-at-least-18-months-claims-software-developer/
* 比特币投资者担心这会阻止比特币成为现金， https://steemit.com/cryptocurrency/@superfreek/btc-spam-attack-200-000-unconfirmed-transactions-halts-bitcoin
* 比特币垃圾邮件攻击被用来支持 attack 2.5.3， https://bitcoinmagazine.com/articles/curious-case-bitcoins-moby-dick-spam-and-miners-confirmed-it/

**No Impact on Adoption**
* Although this attack has been performed regularly in recent months its only effect has been occasional transaction delays and higher fees. It has not significantly slowed adoption. This is partially due to the fact that Bitcoin is so early in its evolution to become money that it is still in the "store of value" stage and partially because investors are aware that new features are on the way that will make this attack impractical.

**对使用没有影响**
* 尽管近几个月来这种袭击事件经常发生，但其唯一的影响是偶尔的交易延迟和较高的交易费用。它没有显着减慢比特币的采用速度。部分是由于比特币在成为货币的道路上，处于发展的早期阶段，以至于它仍处于“储值”的阶段。另外部分原因在于投资者意识到比特币正在发展中的新特性正在使这种攻击变得不切实际。

### An attacker could identify the participants in transactions through network traffic analysis
Bitcoin transactions are broadcast across the Internet by the sender. If an attacker can view network traffic and discover the source and destination of transactions this would make Bitcoin less suitable for cash.

### 攻击者可以通过网络流量分析来识别交易中的参与者
比特币交易由发送者在互联网上广播。如果攻击者可以监控网络流量来发现交易的来源和目的地，这会使比特币不太适合做为现金使用。

**Safety Features**
* Bitcoin destination addresses are randomly generated for each transaction and not tied to an individuals identity.
* Bitcoin is an open source project with growing participation and regular contributions from the top cryptographers and software security experts. It is likely that additional safety features will be added to address this issue soon.
* Bitcoin transactions can be sent from anonymous networks such as free wifi hotspots at coffee shops. However this is still a major inconvenience and it can still reveal the senders general location.

**安全特性**
* 比特币的目的地址是为每笔交易随机生成的，并不与个人身份绑定。
* 比特币是一个开源项目，参与人数不断增加，来自顶级密码专家和软件安全专家经常贡献代码。有可能很快就会增加额外的安全功能来解决这个问题。
* 比特币交易可以从匿名网络发送，例如通过咖啡店的免费 wifi 热点。虽然这不是很方便，并仍然有可能泄露发件人的位置。

**Past Attacks**
* The NSA collects and stores all Internet traffic.
It is reasonable to assume all Bitcoin transactions are archived
and analyzed so that they are easily readable and tied to individuals.,
https://www.theguardian.com/world/interactive/2013/jul/31/nsa-xkeyscore-program-full-presentation
Access to this data may currently be limited to the thousands of employees
and contractors that work for governments friendly to the US,
but it is likely that this data will be more broadly distributed through a leak
or hack if it hasn't been already.,
https://en.wikipedia.org/wiki/XKeyscore

* BlockCypher has developed a graph network analysis system which link's activity on the bitcoin blockchain, and attempts to resolve activity back to individuals. They also run machine learning models against each bitcoin transaction to "score" it's association with gambling/drugs/etc. This system is partially detailed in the following talk given at a big data conference.,
https://www.youtube.com/watch?v=8ELUDY1-ee0

**过去的攻击**
* NSA 收集和存储所有的互联网流量。所以这样的假设是合理的，即所有的比特币交易都将被存档和分析，使之易于阅读并且与个人绑定
https://www.theguardian.com/world/interactive/2013/jul/31/nsa-xkeyscore-program-full-presentation
目前，能获得这些数据的仅限于为美国政府提供服务的数千名员工和承包商，但这些数据有可能被泄露或被黑客攻击，使之被广泛的传播开来，
https://en.wikipedia.org/wiki/XKeyscore

* BlockCypher 开发了一个图形网络分析系统，分析比特币在区块链上的活动，并试图解析个人活动。他们还对比特币交易数据进行人工智能分析，对交易与赌博/毒品等的关联度进行“评分”。这个系统在以下大数据会议的演讲中有部分详细说明， https://www.youtube.com/watch?v=8ELUDY1-ee0

**No Impact on Adoption**
* Bitcoin transactions can be tied to the senders by analyzing network traffic, however unless Bitcoin transactions become less secure than government money transactions this is unlikely to prevent Bitcoin from becoming cash. It is also likely that additional safety features will be added before this flaw has a significant impact on adoption.

**对采用没有影响**
* 比特币交易可以通过分析网络流量来与发起交易者相关联，但是除非比特币交易比政府的货币交易更不安全，否则不能阻止比特币成为现金。在这个缺陷产生重大影响之前，很有可能会增加额外的安全功能来解决这个问题。

### An attacker could identify the participants in a transaction through public transaction data.
Bitcoin transactions are published on the public ledger and they contain the source, destination, approximate time and amount of each transaction. If it is possible for an attacker to discover the people involved in a transaction this would make Bitcoin less attractive as cash.

### 攻击者可以通过公共的交易数据来识别出交易中的参与者。
比特币交易是在公共总账上公布，它们包含每笔交易的来源、目的地、大致时间和金额。如果攻击者有可能发现参与交易的人，这会降低特币的吸引力。

**Safety Features**
* Bitcoin destination addresses are randomly generated for each transaction and not tied to an individuals identity.
* Even with this fault, Bitcoin remains more secure than government money transactions.
* Bitcoin is an open source project with growing participation and regular contributions from the top cryptographers and software security experts. It is likely that additional safety features will be added to address this issue soon.

**安全特性**
* 比特币的目的地址由每笔交易随机生成，并不跟个人身份绑定。
* 即使有这个问题，比特币仍然比政府的法币交易更安全。
* 比特币是一个开源项目，参与的人数不断在增加之中，来自顶级密码专家和软件安全专家经常贡献代码。有可能很快就会增加额外的安全功能来解决这个问题。


**Past Attacks**
* Ross Ulbrict's transactions are traced by the FBI.,
https://www.wired.com/2015/01/prosecutors-trace-13-4-million-bitcoins-silk-road-ulbrichts-laptop/

**过去的攻击**

* Ross Ulbrict 的交易被联邦调查局跟踪，
https://www.wired.com/2015/01/prosecutors-trace-13-4-million-bitcoins-silk-road-ulbrichts-laptop/

**Medium Risk**
* Bitcoin transactions can be tied to the senders by analyzing the public ledger, however unless Bitcoin transactions become less secure than government money transactions this is unlikely to prevent Bitcoin from becoming cash. It is also likely that additional safety features will be added before this flaw has a significant impact on adoption.

**中等风险**
* 比特币交易可以通过分析公共分类账将交易发起人联系起来，但是除非比特币交易比政府的货币交易更不安全，否则不会阻止比特币成为现金。在这个缺陷产生重大影响之前，很有可能会增加额外的安全功能来解决这个问题。

## Confirming Bitcoin transactions
Bitcoin transactions are confirmed through a process called mining. To prevent double spending of transactions they are grouped together and a difficult math problem is solved using this set of transactions, and the previous set of transactions, as inputs. Sets of transactions are called "blocks." The math problem is so difficult that a significant amount of money, must be spent on electricity in order to solve the problem. The person that solves the math problem is rewarded with bitcoin, in the form of transaction fees included by the senders of transactions, and a "block reward" where additional bitcoins are created. Solving this math problem is called "finding a block." Everyone running mining software is competing to be the first to find the next block.

## 比特币交易的确认
比特币交易通过一个称为挖矿的过程来确认。为了防止双重支出交易（双花），交易被分组在一起，并且使用当前交易集和前一组交易作为输入解决一个困难的数学问题。交易集称为“块”。数学问题非常困难，为了解决这个问题必须花费大量的电力。解决数学问题的人将得到交易发送者的交易费用，及创建的额外比特币的“块奖励”作为回报。解决这个数学问题又称“找到一个块”。每个正在运行挖矿软件的人都争着成为第一个找到下一个区块的人。

### An attacker could run mining software in order to prevent transactions from being confirmed.
Because anyone is able to download and run the software that confirms transactions on the Bitcoin network it is possible for an attacker to mine blocks without including transactions.

### 攻击者可以运行挖矿软件，来阻止交易的确认。
因为任何人都可以下载并运行在比特币网络上确认交易的软件，攻击者有可能生成不包括交易的块。

**Safety Features**
* Transactions include transaction fees. If an attacker ignores these transactions, he will not be able to collect the associated transaction fees.
* If an attacker ignores a transaction in a block, it is likely that he will not be the miner that solves the next block so he will have only succeeded in delaying the transaction for a short period of time.
* In order to delay a transaction for a longer period of time an attacker would need to dedicate more computing power to the network. This would be expensive because he would have to spend a lot of money on electricity and computer hardware and his only reward would be in bitcoins that would be less valuable as a result of his actions.
* The value of Bitcoin has been increasing rapidly since it was created. Many individuals with the funding and knowledge to execute this attack would gain more from investing in Bitcoin than from attacking it.
* Unlike other proof of work systems the Bitcoin proof of work doesn't generate anything desirable to the marketplace beyond securing the network. This prevents attacks like these from being partially subsidized through the sale of the other proof of work outputs.
* Bitcoin mining uses cutting edge chip design to produce computer power as efficiently as humanly possible. This means that an attacker could not easily develop more effective hardware in order to make this attack more cost effective.
* This attack would increase fees. Increased fees would incentivize others to mine blocks with the transactions and this would increase the cost of the attack.

**安全特性**

* 交易包括交易费用。如果攻击者不确认这些交易，他将无法取得相关的交易费用。
* 如果攻击者忽略了区块内的交易，他很可能不会成为找到下一个区块的矿工，所以他只能延迟一段时间的交易。
* 为了使交易延迟更长的时间。攻击者需要为网络提供更多的计算能力，而这将是昂贵的，因为他将不得不在电力和计算机硬件上花费大量的金钱，而他唯一的能得到的奖励就是比特币，这使得他的行为不那么有价值。
* 自创建以来，比特币的价值一直在快速增长。拥有资金和知识来执行攻击的人，投资比特币将比攻击获得更多的收益。
* 与其他工作量证明系统不同，比特币工作证明除了保护网络外，并不产生市场上任何可用的东西。这可以防止类似的攻击通过销售其他工作量证明来得到部分补贴。
* 比特币挖矿使用尖端的芯片设计，尽可能高效地产生计算机能力。这意味着攻击者无法轻易地通过开发更有效的硬件，来使这种攻击更具成本效益。
* 这类攻击会使交易费增加。费用的增加会激励其他人来挖矿，从而增加攻击的成本。

**Past Attacks**
* Miners are creating blocks without any transactions.,
https://bitcoinmagazine.com/articles/why-do-some-bitcoin-mining-pools-mine-empty-blocks-1468337739/

**过去的攻击**
* 矿工正在创建不包含任何交易的块。 https://bitcoinmagazine.com/articles/why-do-some-bitcoin-mining-pools-mine-empty-blocks-1468337739/

**No Impact on Adoption**
* The only effect of this attack would be to increase fees and fees are unlikely to go high enough to significantly slow adoption as investors anticipate that this attack will be less effective in the future.

**对采用没有影响**
* 这类攻击的唯一影响是增加了交易费用，交易费不可能高到足以大大减缓比特币的使用，因为投资者预计这种攻击在未来将不太有效。

### An attacker could run mining software in order to double spend bitcoins.
Because anyone is able to download and run the software that confirms transactions on the Bitcoin network it is possible for a bad actor to mine blocks without including transactions.

If the attacker sends bitcoin he could delay that transaction until a new transaction, using the same funds, is confirmed by the network. This would make the initial transaction invalid after it was relayed across the network.

### 攻击者可以运行挖矿软件，以实现比特币的双花。
因为任何人都可以下载和运行在比特币网络上确认交易的软件，所以攻击者有可能挖出不包含交易的块。

如果攻击者发出一笔比特币交易，然后他延迟这笔交易被网络确认的时间，一直到使用相同金额的新交易被网络确认为止。确认的交易在网络传输开来后会使初始的交易无效。

**Safety Features**
* The cost of executing this attack increases exponentially as the transaction moves further back into the block history because the Bitcoin network considers the longest (valid) history to be correct.
* Many Bitcoin wallets don't display a transaction completely finalized until it is at least 6 blocks old.
* Layer 2 technologies such as the lightning network reduce this threat because transactions are confirmed instantly.
* Unlike other proof of work systems the Bitcoin proof of work doesn't generate anything desirable to the marketplace beyond securing the network. This prevents attacks like these from being partially subsidized through the sale of other proof of work outputs.

**安全特性**
* 由于比特币网络认为最长（有效）的块链是正确的，如果交易回退到更早的块历史上，执行这类攻击的成本会呈指数级增长。
* 许多比特币钱包不会显示末完全确定的交易，一直到区块链上这个交易块后至少有 6 个块被确认。
* 闪电网络等第2层技术可以减少这种威胁，因为交易是即时确认的。
* 与其他工作量证明系统不同，比特币工作证明除了保护网络外，不产生市场上可用的任何东西。这可以防止类似的攻击通过出卖其他工作量证明得到部分补贴。

**No Impact on Adoption**
This attack is not cost effective.

**对采用没有影响**
这种攻击不符合成本效益。

### An attacker could exploit a flaw in the proof of work algorithm to fake the performance of work.
If an attacker is able to find a flaw in the proof of work algorithm he could obtain the benefits of transaction fees and block rewards without doing the work required to secure the Bitcoin network.

### 攻击者可以利用工作量证明算法中的缺陷来伪造工作量。
如果攻击者能够发现工作量证明算法中的缺陷，他就可以获得交易费及块奖励，而无需进行保护比特币网络所需的工作。

**Safety Features**
* The proof or work algorithm is based on the SHA-256 hash algorithm. This algorithm has been in use for over a decade and is critical to most digital security applications and it is believed to be secure.
* The Bitcoin proof of work has been in use on the Bitcoin network for over 8 years and the only flaw uncovered to date only allowed the attacker to fake ~20% of his work.

**安全特性**
* 工作量证明算法基于 SHA-256 哈希算法。这种算法已经使用了十多年，这个算法对于大多数数字安全应用来说都是至关重要的，而且它被认为是安全的。
* 比特币工作量证明已经在比特币网络上使用了 8 年以上，迄今为止发现的唯一漏洞是允许攻击者伪造他工作量的 20％。


**Past attacks**
* Attackers discover a way to fake work.,
https://www.asicboost.com/

**过去的攻击**
* 攻击者发现一种伪造工作量的方法，
https://www.asicboost.com/

**No Impact on Adoption**
* Although past attacks have been successful they were a result of a known design flaw (transaction malleability) that has been fixed.

**对采用没有影响**
* 尽管过去有过成功的攻击，但这是因为原来已知的设计缺陷（交易延展性）所引起，现在已经修复。

### An attacker could steal all of the hardware used to confirm Bitcoin transactions.
If an attacker could gain control of all of the hardware used to confirm Bitcoin transactions he could prevent some or all Bitcoin transactions.

### 攻击者可以窃取所有用于确认比特币交易的硬件。
如果攻击者可以控制用于确认比特币交易的所有硬件，他就可以阻止一些或全部比特币交易。


**Safety Features**

* Bitcoin mining is decentralized. Mining computers are located in many geographic areas that are under the control of various criminal organizations that are hostile to one another. Even if all mining hardware could be found, coordination between hostile groups, that may see Bitcoin as a lesser threat to their interests than to their rivals,
seems unlikely.
* The Bitcoin protocol was designed to keep incentives for mining in a single location as small as possible. For example the delay between a miner finding a block and the rest of the miners knowing about this discovery is short.
* Miners are, to some degree, aware of this threat. This encourages miners to remain anonymous and keep their locations secret. If this attack is attempted this awareness will be greatly increased.

**安全特性**
* 比特币挖矿是去中心化的。用于挖矿的计算机位于多个地理区域，有些地区还处于彼此敌对的各种犯罪组织的控制之下。即使能找到所有的挖矿硬件，敌对组织之间似乎也不大可能协调，因为比特币对其利益的威胁要小于其对手。
* 比特币协议旨在在单个地点尽可能少地鼓励挖矿。例如，矿工发现一个块与其它矿工知道这一发现之间的延误很短。
* 矿工在一定程度上意识到了这种威胁。这鼓励矿工保持匿名，并对地点保密。如果有此类攻击尝试，会大大引起矿工们的警惕心理。

### An attacker could claim to be Satoshi and remove a safety feature from the next version of Bitcoin.
Satoshi Nakamoto is the name of the author of the original Bitcoin white paper and software. Because he is so well respected  in the Bitcoin community he, or someone pretending to be him, could attempt to remove a security feature in the next version of Bitcoin.

### 攻击者可以声称是中本聪，并从下一个版本的比特币中删除安全功能。
中本聪是原来比特币白皮书和软件作者的名字。因为他在比特币界非常受人尊敬，所以他或者假装成他的人可能会试图在下一个版本的比特币中删除安全功能。

**Safety Features**

* Satoshi Nakamoto disappeared from the Bitcoin community years ago. Since that time many well respected developers and security researchers have become experts in Bitcoin and the design and implementation decisions that keep it secure. Convincing the best security researchers in the world to remove a safety feature in Bitcoin would not be easy, even by someone with the reputation of Satoshi.
* Impersonating Satoshi is difficult because he retains ownership of bitcoin balances. Anyone claiming to be Satoshi should be able to provide proof of his identity by sending those bitcoins.
* In some debates people have attempted to use Satoshi's vision, or intention as support for their position. In these cases an appeal to the authority of Satoshi has generally undermined the argument because it distracts from the technical advantages and disadvantages of a given design or implementation decision.

**安全特性**

* 中本聪已在几年前从比特币社区消失。自那时以来，许多备受尊敬的开发人员和安全研究人员成为了比特币专家，确保了设计和实施的安全性。说服世界上最好的安全研究人员去掉比特币中的安全功能并不是一件容易的事，即使是一个有着中本聪信誉的人也是如此。
* 冒充中本聪是困难的，因为他有一些比特币地址的所有权。任何自称是中本聪的人需要通过发送这些比特币来证明他的身份。
* 在一些辩论中，人们会试图用中本聪的愿景或意图来支持他们的立场。在这些情况下，诉诸于中本聪的权威通常会削弱其论点。因为它对忽略了对给定设计或实现决策的技术利弊分析。

**Past Attacks**
* Craig Wright impersonates Satoshi in order to remove the block size limit.,
https://dankaminsky.com/2016/05/02/validating-satoshi-or-not/

**过去的攻击**
* Craig Wright 为了消除块大小限制冒充中本聪， https://dankaminsky.com/2016/05/02/validating-satoshi-or-not/

### An attacker could remove a safety feature from the next version of Bitcoin to enable a new capability.
In all software projects there is a tension between adding new features or capabilities and maintaining safety features. This is often exacerbated by the fact that safety features often prevent software from being used certain desirable ways. As an example cars have speed limiters to prevent a car from driving as fast as the engine will allow but it does prevent users from racing at top speed.

Even in the most effective software projects the security vs features trade off decisions become heated and political. If an attacker is able to convince the community that a new feature is more important than an existing safety feature, the safety feature would be removed.

### 攻击者为了启用新的功能在下一个版本的比特币中删除安全功能。
在所有软件项目中，有时添加新的特性或功能与保证安全是相互矛盾的。更糟的是，软件的安全功能常常会限制用户对软件使用需求。举例来说，汽车使用限速器来防止发动机以最快允许速度行驶，的确限制了用户以最快速度行驶的可能。

即使在最有效的软件项目中，安全与功能之间的权衡决定也会变得激烈和政治化。如果攻击者能够说服社区新的功能比现有的安全功能更重要，那么这个安全功能有可能将被删除。

**Safety Features**
* The Bitcoin technical community has the best software security experts working diligently to keep Bitcoin secure.
* Because the Bitcoin software is currently securing over 60 Billion USD in value the technical community is slaw to make changes that could introduce security vulnerabilities.
* Side chains allow new features to be developed and deployed using bitcoin as the asset, without changing the Bitcoin network or protocol. It is likely that any significant change in the future will be deployed onto a side chain before those features are included into Bitcoin itself.

**安全特性**
* 比特币技术社区拥有最好的软件安全专家，他们正在努力保证比特币的安全。
* 由于比特币软件目前的价值已经超过 600 亿美元，技术社区对可能引发安全漏洞的改变非常慎重。
* 不用更改比特币网络或其协议，侧链就可以以比特币作为资产来开发和部署新的功能。有可能未来的任何重大变化很可能会先部署到侧链上，然后再把这些功能部署到比特币上。

**Past Attacks**
* Segwit 2x attempts to remove the block size limit safety feature.,
https://medium.com/@jimmysong/segwit2x-what-you-need-to-know-about-the-2mb-hard-fork-27749e1544ce
* Bitcoin XT attempts to remove the block size limit safety feature.,
https://medium.com/faith-and-future/why-is-bitcoin-forking-d647312d22c1
* Bitcoin Classic attempts to remove the block size limit safety feature.,
https://bitcoinclassic.com/

**过去的攻击**
* Segwit 2x 尝试取消块大小的限制这一项安全功能。，
https://medium.com/@jimmysong/segwit2x-what-you-need-to-know-about-the-2mb-hard-fork-27749e1544ce
* Bitcoin XT 尝试取消块大小的限制这一项安全功能。， https://medium.com/faith-and-future/why-is-bitcoin-forking-d647312d22c1
* Bitcoin Classic 尝试取消块大小的限制这一项安全功能。，
https://bitcoinclassic.com/

**No Impact to Adoption**
* This attack is unlikely to be successful.

**对采用没有影响**
* 这种攻击不太可能成功。

### An attacker could create a copy of Bitcoin (aka fork) that is missing a safety feature and trick people into using it.
Because Bitcoin is an open source project anyone can copy the code and build their own version of Bitcoin. If they can convince someone that their version of Bitcoin is the real Bitcoin they will have successfully removed that safety for those users.

### 攻击者可以通过复制代码来创建（又名分叉）一个缺少安全功能的比特币，并诱骗人们使用它。
由于比特币是一个开源项目，任何人都可以复制代码并构建他们自己的比特币版本。如果他们能说服别人，让人相信他们的比特币版本才是真正的比特币，他们可以为这些用户将安全特性移除。

**Safety Features**
* If investors are deceived into using a version of Bitcoin that lacks the safety features of Bitcoin that does not reduce the security of Bitcoin.
* While siphoning off investors from Bitcoin would delay Bitcoin from becoming money in the near term, it would accelerate the education of investors regarding the safety features of the real Bitcoin and this would accelerate Bitcoin becoming cash.
* Side chains allow new versions of Bitcoin to be created while still using Bitcoin as an asset. New versions of Bitcoin will likely be tested as a side chain before those features are implemented into the original Bitcoin. This would give people more time to understand any changes being proposed.
* It would be very difficult to promote a version of Bitcoin without the Bitcoin community exposing the attempt as an attack.
* While it is still possible some investors would be deceived they would almost certainly understand there is a significant controversy and if they made the wrong choice they would be more immune to this attack in the future.
* By it very nature this attack involves creating a new digital asset that doesn't work as well as Bitcoin as cash. This fact will eventually become clear to all investors making this attack ineffective over time.

**安全特性**
* 如果投资者被欺骗而使用缺乏安全功能的比特币版本，但这并没有降低比特币的安全性。
* 尽管从比特币中骗离投资者将会使比特币在短期内无法成为货币，但它将加速对投资者关于真正的比特币安全特性的教育。而这将加速比特币成为现金的过程。
* 侧链允许创建新版本的比特币，并仍然使用比特币作为资产。比特币的新版本可能会作为一个侧链先进行测试，然后才会将这些功能应用到比特币中。这会使人们有更多的时间了解正在提出的任何改变。
* 如果比特币社区把这个企图视为为攻击，这个比特币的版本就会很难推广。
* 仍有可能会有一些投资者被骗，但是他们几乎可以肯定地了解到这是一个重大的争议，如果他们做出了错误的选择，以后他们将对这类攻击免疫。
* 这种攻击非常自然地创造了一种新的数字资产，但它的运行会不及比特币那样完美。最终会让所有的投资者看清楚这个事实，所以随着时间的推移，这个攻击就无效了。

**Past Attacks**
* Bitcoin Cash attempts to remove the block size limit safety feature.,
https://web.archive.org/web/20170928124716/https://www.bitcoincash.org/

**过去的攻击**
* 比特币现金尝试删除块大小限制的安全功能。， https://web.archive.org/web/20170928124716/https://www.bitcoincash.org/

**No Impact to Adoption**
* This threat is unlikely to impact adoption. The Bitcoin Cash fork attack was well funded and benefited from a major design flaw in Bitcoin (transaction malleability) that has now been fixed and a method for deploying controversial changes (miner signaling) that is unlikely to be used in the future and it still had negligible effect on the adoption of Bitcoin.

**对采用没有影响**
* 这种威胁不太可能影响到比特币的采用。比特币现金分叉攻击获得了充足的资金，受益于现在已经被修复的一个比特币（交易延展性）的主要设计缺陷，同时受益于有争议的变化的部署方法（矿工信令），这种改变在未来不太可能使用，所以对比特币的影响可以忽略不计。

### An attacker could create a variety of implementations of Bitcoin in order to add a security flaw.
If an attacker is able to create a new implementation of the Bitcoin software that is not thoroughly reviewed by Bitcoin security experts he could introduce a subtle security flaw that is not discovered before it is deployed.

Currently the vast majority of expertise is focused on a single repository and this makes it very difficult for a flaw to go undiscovered.

If an attacker could create one or more Bitcoin implementations of Bitcoin it would at minimum spread out the efforts of security experts and at most prevent some implementations from being reviewed before deployment.

### 攻击者为添加安全漏洞可以创建比特币的各种实现
如果攻击者能够创建一个不经过比特币安全专家完全审查的比特币软件的新实现，那么他可能会在部署前引入一个没有发现的细微安全缺陷。

目前绝大多数的专业知识都集中在一个存储库上，这使得缺陷很难不被发现。

如果攻击者可以创建一个或多个比特币实现，它可能会分散安全专家的工作，使其对某些实现末能进行严格审查从而使软件部署出去。

**Safety Features**
* The Bitcoin development community is aware of this attack and has been very vocal about the need to prevent it.
* Bitcoin development is very difficult and it would be difficult to recruit competent developers to participate in this attack.
* The Bitcoin development community does review other implementations and has offered security fixes both to protect Bitcoin and to expose the poor quality of some implementations before they are adopted by the unwitting.

**安全特性**
* 比特币开发社区意识到这种攻击，并一直非常强调需要防止这类攻击。
* 比特币的开发非常困难，招募有能力的开发者参与这样攻击是很困难的。
* 比特币开发社区确实对其他的实现进行了审查，并提供了安全补丁，以保护比特币和在它们被无意中采用前揭露一些低质量的实现。

**Past Attacks**
* Bitcoin Unlimited contained security flaws that would have been caught in code review.,
https://bitcoinmagazine.com/articles/security-researcher-found-bug-knocked-out-bitcoin-unlimited/
* Bitcoin ABC contained security flaw that would have been caught in code review.,
https://reviews.bitcoinabc.org/rABCb7d5bda29c07cd80c900e3ddd6a9a37a2b23f347
* Bitcoin XT contained a security flaw that could have been cough in code review.,
https://www.reddit.com/r/bitcoinxt/comments/43lty6/current_bitcoin_xt_contains_a_network_splitting/

**过去的攻击**
* 比特币无限包含可在代码审查时发现的安全漏洞， https://bitcoinmagazine.com/articles/security-researcher-found-bug-knocked-out-bitcoin-unlimited/
* 比特币ABC包含可在代码审查时发现的安全漏洞， https://reviews.bitcoinabc.org/rABCb7d5bda29c07cd80c900e3ddd6a9a37a2b23f347
* 比特币XT包含可在代码审查时发现的安全漏洞， https://www.reddit.com/r/bitcoinxt/comments/43lty6/current_bitcoin_xt_contains_a_network_splitting/

## Observing confirmed transactions
In order for a transaction to be completed the receiver must be confident the transaction has been irreversibly confirmed by the Bitcoin network. this is performed by Bitcoin "node" software. This software maintains a copy of the longest set of transactions presented to it that are valid. The node software considers a transaction valid if it is structured correctly, digitally signed by the bitcoin owner, and does not attempt to transfer more bitcoin than is available to the sender. Some Bitcoin wallets do not contain the node software, but instead connect to a remote node to confirm that a transaction is completed. This is called an SPV (Simple Payment Verification) wallet.

## 观察已确认的交易
为了完成交易，接收方必须确信交易已经被比特币网络不可逆转地确认。这是由比特币“节点”软件执行的。

该软件维护着一个最长链的有效交易的一个拷贝。只有块结构正确、并由比特币所有者进行了数字签名，而且转出的金额要小于发送人所拥有的金额，节点软件才认为交易是有效的。某些比特币钱包不包含节点软件，而是连接到远程节点来确认交易的完成。这被称为SPV（简单支付验证）钱包。

### An attacker could create a less secure digital asset and trick people into buying it.
If an attacker can trick investors into using his digital asset as cash it could prevent Bitcoin from becoming cash (unit of account).

### 攻击者可能会创造一个不太安全的数字资产，并诱骗人们购买。
如果攻击者可以欺骗投资者使用他的数字资产作为现金，它可能会阻碍比特币做为现金使用的功能。

**Safety Features**
* If a digital asset is less secure than Bitcoin it is also less suitable as cash. Eventually this reality will be understood by investors and they will abandon the less secure coin.
* Many members of the Bitcoin community are technically literate and obsessed by the technology and the incentive structure that makes Bitcoin secure.
* No criminal organizations in the world have been successful at keeping security flaws secret.
* Digital assets contain the greatest rewards for identifying security flaws. Security researchers and hackers are highly incentivized to find every security flaw.
* Effort spent on promoting flawed digital assets is most effective when targeting people that are new to the technology because existing members of the community are more difficult to deceive. The net effect of this attack is to educate people of the value of Bitcoin.

**安全特性**
* 如果某个数字资产不如比特币安全，那么它也不太适合作为现金使用。最终投资者会发现这个事实，并将放弃使用这种不太安全的数字货币。
* 比特币社区的许多成员都精通技术，痴迷于让比特币安全的技术和激励机制。
* 世界上任何犯罪组织都没能够成功地将安全漏洞保密。
* 数字资产具有对发现安全缺陷的人给予最大回报的特性。安全研究人员和黑客对发现的每一个安全缺陷都会非常高兴。
* 花费在促进有缺陷的数字资产上的努力针对技术新人来说是最有效的，因为现有的社区成员更难以欺骗。这种攻击的净效果是对人们比特币的价值地教育。

**Past Attacks**
* Ethereum has no maximum limit of Ether and no built in difficulty adjustment.,
https://github.com/ethereum/wiki/wiki/White-Paper
* Ripple does not use proof of work and requires trusted "validators.",
https://ripple.com/consensus-whitepaper/
* Bitcoin cash removed the block size safety feature,
https://www.bitcoincash.org/
* Litecoin removed the cutting edge chip design safety feature.,
https://litecoin.info/

**过去的攻击**
* 以太坊没有发行数量限制，也没有内置的难度调整。https://github.com/ethereum/wiki/wiki/White-Paper
* 瑞波 （Ripple） 不使用工作量证明，需要可信的“验证人”，
https://ripple.com/consensus-whitepaper/
* 比特币现金删除了限制块大小这一项安全特性，
https://www.bitcoincash.org/
* 莱特币（Litecoin） 移除了针对先进的芯片设计设置的安全功能，
https://litecoin.info/

**No Impact on Adoption**
* Although the market cap falsely indicates otherwise, Bitcoin adoption has not been slowed by past attacks and likely has been accelerated.

**对采用没有影响**
* 尽管市值错误地表明了其他情况（可能是指数字货币的市值变动，译者注），但过去的攻击并没有减缓比特币的使用速度，而且可能已经加速。

### An attacker could create a more secure digital asset so that investors will abandon Bitcoin.
If an attacker could create a more secure digital asset investors would abandon Bitcoin and adopt this new asset as cash.

### 攻击者可以创建一个更安全的数字资产，从而让投资者放弃比特币。
如果攻击者可以创建一个更安全的数字资产，投资者将放弃比特币，并将这个新资产作为现金使用。

**Safety Features**
* The vast majority of cryptography experts are working on Bitcoin.
* As an open source project Bitcoin is able to incorporate any advances discovered in other projects.
* Digital assets benefit from "network effects" for adoption. A new Digital asset would be starting at a great disadvantage in this regard.
* Crypto-currencies require proof of work to secure the network. Bitcoin has the greatest amount of work by several orders of magnitude.
* If a new digital asset is more secure and honors past Bitcoin transactions it would, be an upgrade to Bitcoin, not a competitor of Bitcoin.

**安全特性**
* 绝大多数密码学专家正在为比特币工作。
* 作为一个开源项目，比特币能够将任何在其他项目中发现的进步都纳入其中。
* 数字资产受益于“网络效应”。一个新的数字资产在这方面将处于极大的劣势。
* 加密货币需要工作证明来保护网络。比特币的工作量最大，其它加密货币跟比特币比有着数量级的差距。
* 如果一个新的数字资产更安全并且使用过去的比特币交易数据，那么它将是比特币的升级，而不是比特币的竞争者。

**Past Attacks**
* This attack would result in improved Bitcoin security. It is not really an attack when properly understood.

**过去的攻击**
* 这种攻击会导致比特币安全性的提高。确切理解，这并不是真正的攻击。

**No Impact on Adoption**
* This attack would result in improved Bitcoin security. It is not really an attack when properly understood.

**对采用没有影响**
* 这种攻击会导致比特币安全性的提高。确切理解，这并不是真正的攻击。

### An attacker could mine invalid Bitcoin blocks to remove a safety feature from Bitcoin
If an attacker could make the network accept blocks that don't include a safety feature he would have effectively removed that safety feature.

### 攻击者可能通过挖掘无效的比特币区块来消除比特币的安全功能
如果攻击者可以使网络接受不包含安全功能的块，就能有效地移除该安全功能。


**Safety Feature**
* The Bitcoin network enforces the rules that include safety features on every Bitcoin node, miner and wallet. As a result blocks mined without the safety feature will simply be ignored by the Bitcoin network.

**安全特征**
* 比特币网络强制执行包含在每个比特币节点、矿工和钱包上的安全规则。因此，所有不符合安全规则的块将被比特币网络忽略。

**Past Attacks**
* Segwit 2x,
https://medium.com/@jimmysong/segwit2x-what-you-need-to-know-about-the-2mb-hard-fork-27749e1544ce

* 过去的攻击
* Segwit 2x，
https://medium.com/@jimmysong/segwit2x-what-you-need-to-know-about-the-2mb-hard-fork-27749e1544ce

**No Impact on Adoption**
* This attack is not effective, but it could be used to support a misinformation campaign, a fork to remove a safety feature, or a new digital asset that is missing a safety feature.

**对采用没有影响**
* 这种攻击没有效果，但消除安全功能的分叉，或者缺少安全功能的新数字资产可以用来进行虚假宣传活动。

### An attacker could deceive a Bitcoin node into thinking a transaction did or did not get confirmed.
Because Bitcoin nodes accept information from any other computer running the Bitcoin node software it is possible to provide a node or a group of nodes false information about the current state of a transaction.

### 一个攻击者可能会欺骗一个比特币节点，认为这个交易得到或没有得到证实。
由于比特币节点接受来自运行比特币节点软件的其他任何计算机的信息，因此可以为节点或一组节点提供关于当前交易状态的虚假信息。

**Safety Features**
* Bitcoin nodes form a peer-to-peer network and obtain copies of transactions from multiple nodes. An attacker would need to prevent a node from communicating with all innocent nodes in order for this attack to be successful.
* In order to provide a set of false transactions that appear valid the attacker would need to perform the proof of work required by the current network difficulty making this attack expensive.
* As soon as a node discovers that a longer block chain exists with valid transactions it immediately accepts this new set of transactions as correct and discards its previous set of transactions.
* Satellite connections allow nodes to download a copy of the block chain even if they are using an Internet connection that keeps them ignorant of a longer valid chain of transactions.
* If a node owner is concerned that he may be the victim of a network split attack he could wait until he receives physical media containing the longest block from another physical location.
* Absolute censorship is difficult for a short period of time and nearly impossible, for a longer period of time, as evidenced by the Chinese governments serious, yet ineffective, efforts to censor the Internet.
* In many ways this is not an attack on Bitcoin directly, but an attack on the Internet itself. Building a secure Internet is becoming more and more important and there are several efforts underway to accomplish this goal. As Bitcoin and other digital assets become more important the motivation to create a secure Internet will grow.
* In order to make this attack more cost effective more nodes would need to be deceived at the same time. However, the more nodes are deceived into trusting an invalid chain of transactions the more likely it becomes that the victims become aware of the attack and stop trusting their node software.

**安全特性**
* 比特币节点形成一个点对点网络，并从多个节点获取交易的副本。为使这种攻击成功，攻击者需要防止节点与所有正常节点进行通信。
* 为了提供一组看起来有效的虚假交易，攻击者需要执行当前网络难度所需的工作量证明，使得这种攻击很昂贵。
* 只要节点发现有一个较长的链存在有效的交易，它会立即接受这个新的一组交易，并丢弃其前一组交易。
* 卫星连接允许节点下载块链，即使他们正在使用局联网连接让他们不能发现更长的有效交易链。
* 如果节点拥有者担心他可能是网络分裂攻击的受害者，他可以在收到从其它地方拿来的包含最长块链的数据的物理介质后再验证交易。
* 短时间内，绝对的审查制度很难在实现，而且几乎是不可能的。长期来讲，中国政府严厉而无效地审查互联网的努力也表明绝对的审查制度是几乎不可能实现的。
* 在许多方面，这不是直接对比特币的攻击，而是对互联网本身的攻击。建立一个安全的互联网正变得越来越重要，有很多人正为实现这一目标而努力。随着比特币和其他数字资产变得越来越重要，创造安全互联网的动力也将会增长。
* 为了使这种攻击更具成本效益，需要同时欺骗更多的节点。然而，当越来越多的节点被欺骗从而信任无效的交易链，那么就会有越来越多的受害者觉察到攻击，从而不再信任他们的节点软件。

### An attacker could deceive a Bitcoin partial node (SPV client) into thinking a transaction did or did not get confirmed by the Bitcoin network.

In some cases, such as operating on a mobile phone, the Bitcoin client software can't perform the full validation of the Bitcoin transaction history. To the degree that the client doesn't perform complete validation safety features are discarded.

* Bitcoin client software that doesn't perform complete validation of the Bitcoin transaction history often connects to another computer that it trusts to perform this full validation on its behalf. While this is not ideal, because an attacker could pretend to be this trusted computer, it does provide greater security than outright skipping validation.
* The Bitcoin community encourages users to run a full node, especially when acting as a merchant, or accepting large amounts of Bitcoin from untrusted parties.
* In order for this vulnerability to effective Bitcoin as a whole attacks would need to become systemic and this would likely result in the awareness required to encourage full nodes.

### 一个攻击者可能会欺骗一个比特币部分节点（SPV客户端），使其认为交易没有被比特币网络确认或没有确认。
在某些情况下，比如在手机上操作，比特币客户端软件无法执行比特币交易历史的全面验证。如果客户没有执行完整的验证，即意味着安全功能的丢弃。

* 不执行比特币交易历史的完整验证的比特币客户端软件通常连接到其信任的另一台计算机，由另一台计算机代表它来执行完整验证。虽然这并不是理想状态，因为攻击者可以伪装成这个可信的计算机，但它比直接跳过验证还是具更高的安全性。
* 比特币社区鼓励用户运行一个完整的节点，尤其是作为商人，或者是在接受来自不受信任方的大量比特币时。
* 一般来说，需要系统性的攻击才能使攻击对比特币有效，而这样会导致鼓励全节点的运行。

### An attacker could introduce security flaws into Bitcoin mining hardware in order to break the security of Bitcoin.
If an attacker included a "back door" in mining hardware before it was shipped to the buyer he could gain control of the majority of the Bitcoin computing power.

### 攻击者可能会将安全漏洞引入比特币挖掘硬件，以破坏比特币的安全。
在用户收到矿机前，如果攻击者可以在矿机硬件中设置“后门”，那么他就可以控制大部分比特币计算能力。

**Safety Features**
* The Bitcoin network is not effected by the specific owners of mining hardware. The attacker would be as legitimate a Bitcoin miner as the previous owners before control of the hardware was stolen.
* As the new "owner" of Bitcoin hardware he would be equally as incentivized to use these resources to secure the Bitcoin network as the rightful owners.
* Once the physical owners of hardware discovered the hardware was not behaving according to their wishes they would remove the security flaw.

**安全特性**
* 比特币网络不受采矿硬件的具体所有者的影响。在硬件被窃取之前，攻击者就像以前的所有者一样，是合法的比特币矿商。
* 作为比特币硬件的新“拥有者”，他将如同合法的所有者一样同样被激励使用这些资源来保护比特币网络。
* 一旦硬件的物理所有者发现硬件运行不符合他们的意愿，他们将消除安全漏洞。

**Past Attacks**
* Bitmain, the most popular mining hardware manufacturer, includes a backdoor.,
http://www.antbleed.com/

**No Impact to Adoption**
* Even if successful this attack would probably have no effect on the Bitcoin network.

**过去的攻击**
* Bitmain，最流行的挖掘硬件制造商，包含了一个后门，
http://www.antbleed.com/

**对采用没有影响**
* 即使成功，这个攻击也可能对比特币网络没有影响。

# Human Threats
Bitcoin can be attacked by attacking the humans that support the Bitcoin software as network operators, investors, merchants, developers or hardware manufacturers.

# 人为的威胁
可以通过攻击支持比特币软件的人来攻击比特币，如网络运营商，投资者，商家，开发人员或硬件制造商。

## Network Operators
People that run the software needed to support Bitcoin can be attacked.

## 网络运营商
运行支持比特币的软件的人可能会受到攻击。

### An attacker could threaten to harm an individual or group mining bitcoin.
Bitcoin mining is a critical part of the Bitcoin network. Without functioning mining software no new Bitcoin transactions could be trusted.

### 攻击者可能会威胁伤害个人或团体挖掘比特币。
比特币挖矿是比特币网络的重要组成部分。没有正常运行的挖矿软件，就不会有可信的比特币交易。

**Safety Features**

* Bitcoin mining can be done anonymously. In the most extreme case a Bitcoin miner could obtain new transactions and distribute discovered blocks via sneaker net. Before this extreme however Bitcoin miners could use anonymizing technology such as VPNs or Tor.
* Bitcoin mining is decentralized. No single person controls all of the Bitcoin mining computer power and Bitcoin mining equipment is distributed across the globe.
* Even if a large miner was intimidated into action there is little damage he could do to the Bitcoin network. Double spending is not cost effective. Delaying specific transactions would have limited effect. He could not create invalid bitcoins or steal bitcoins.
* An attacker that intimidates a miner has effectively stolen the mining equipment and would be best served by mining bitcoins for profit and securing the network.

**安全特性**
* 比特币挖矿可以匿名完成。在最极端的情况下，比特币矿工可以通过[球鞋网络](https://zh.wikipedia.org/wiki/%E7%90%83%E9%9E%8B%E7%B6%B2%E8%B7%AF)（使用移动物理媒介的方式传输电子信息,包括但不限于磁带、软盘、CD、U盘、移动硬盘等，译者注）来获得新的交易和分发所发现的块。当然，在到达这个极端前，比特币矿工可以使用 VPN 或 Tor 等匿名技术。
* 比特币采矿是去中心化的。没有一个人能控制所有比特币挖矿计算机的算力，并且比特币的挖矿设备分布在全球各地。
* 即使一个大矿工因为被恐吓而采取攻击行为，对比特币网络的损害也很微小。因为双花不符合成本效益。试图延迟具体交易的效果也很有限。攻击者无法创建无效的比特币或窃取比特币。
* 威胁矿工的攻击者因为已经有效地窃取了采矿设备，所以最好的办法是挖比特币来获取利润并保护网络。

**No Impact to Adoption**
* Although the attack is possible it is unlikely that it would succeed in disrupting the Bitcoin network for any significant period of time.

**对采用没有影响**
* 虽然这种攻击是可能的，但是在任何相当长的一段时间内，都不可能成功地破坏比特币网络。

### An attacker could threaten to harm node individual or group running a Bitcoin node
Bitcoin nodes are critical to the Bitcoin network. Without a network of functioning nodes new transactions could not be relayed.

### 攻击者可能会威胁运行比特币节点的个人或小组
比特币节点对比特币网络至关重要。没有功能节点的网络，新的事务就不能中继传播。

**Safety Features**
* Nodes simply validate and relay transactions. Even if a node operator was intimidated into action he could at most slightly delay the relay of traffic and deceive any partial nodes that trusted him to validate transactions (not a best practice for significant transactions).
* Nodes can be operated anonymously. In the most extreme example node operators could run software on computers not owned by them.
* Nodes could download all new transactions using Satellite connections and transmit new transactions hidden inside pictures and using burner phones.
* Nodes could use anonymizing technology such as VPNs or Tor to hide their physical location.
* Peer to peer networks such, as BitTorrent and Bitcoin, have proven extremely difficult, if not impossible, to shut down. This is in spite of the fact that well funded industries and governments have attempted to shut them down in the past.

**安全特性**
* 节点只是验证和转发交易。即使一个节点运营商被吓倒了，他最多只能稍微延迟一下流量的转发，部分信任他并通过他来验证交易的节点被欺骗（对重要的交易这不是最优方法）
* 节点可以匿名操作。在最极端的例子中，节点操作员可以在不属于他们的计算机上运行软件。
* 节点可以使用卫星连接下载所有新的交易，也可以通过隐藏在图片中数据信息或 “burner phone”（一种用完即扔、可以保护隐私的手机，译者注）来传播交易。
* 节点可以使用 VPN 或 Tor 等匿名技术来隐藏自己的物理位置。
* 像 BitTorrent 和比特币这样的点对点网络已经证明，即使有可能但也是非常难以关闭的。尽管如此，过去资金充足的一些行业和政府都曾试图关闭这个行业，但事实上都没有成功过。

**No Impact to Adoption**
* Although the attack is possible it is unlikely that it would succeed in disrupting the Bitcoin network for any significant period of time.

**对采用没有影响**
* 虽然这种攻击是可能的，但是在任何相当长的一段时间内，它都不可能成功地破坏比特币网络。

## Investors
Without Investors Bitcoin would have no market value and be unsuitable as cash.

## 投资者
没有投资者比特币将没有市场价值，将会不适合比特币作为现金来使用。

### An attacker could extort the private keys from an investor.
An attacker could threaten to harm a Bitcoin investor unless he handed over the private keys to his bitcoin holdings.

### 攻击者可以从投资者那里索取私钥。
攻击者可能会威胁要损害比特币投资者，除非他交出自己持有的比特币的私钥。

**Safety Features**
* Many Bitcoin investors are anonymous making extortion difficult.
* Bitcoin investors have unknown balances making extorting all of the bitcoin held by an investor difficult.
* Even if this became a common problem for Bitcoin investors it would not be a threat to Bitcoin becoming money unless it was easier to extort a Bitcoin investor than an investor in government money.
* Many Bitcoin wallets make it easy to create false bitcoin balances making it appear that they have been emptied by an attacker when bitcoin holdings remain.
* Public advocates of Bitcoin are often careful to own only a small amount of bitcoin because they are security experts and very aware of this threat.
* Bitcoin allows multi signature addresses that would require an attacker to extort multiple people, simultaneously, in order to steal bitcoin
* Criminal organizations are comprised of acting individuals. Senior decision makers would gain greater personal benefits by becoming investors in Bitcoin than attempting to prop up its organization's competing cash.

**安全特性**
* 许多比特币投资者都是匿名的，使得敲诈勒索他们很困难。
* 很难知道比特币投资者的比特币持有数，使得要勒索一个投资者所持有的比特币难度增大。
* 即使这成为比特币投资者的一个普遍问题，也不会成为对比特币的威胁，除非勒索比特币投资者比勒索投资政府资金的投资者更容易。
* 许多比特币钱包可以很容易地通过设置来显示错误的比特币余额，看起来好象他们已经被攻击者掏空了其实并不是。
* 比特币的公众支持者经常会小心地只拥有少量的比特币，因为他们是安全专家，非常了解这种威胁。
* 比特币允许多个签名地址，这要求攻击者为了窃取比特币要同时勒索多个人。
* 犯罪组织由行为人组成。高级决策者通过成为比特币投资者，比试图支持其组织的竞争资金，将能获得更大的个人利益。

**No Impact to Adoption**
* While the threat to an individual investor may be high Bitcoin offers more investor security than the assets it competes with so it is unlikely that extorted private keys will prevent Bitcoin from becoming money.

**对采用没有影响**
* 尽管对个人投资者的威胁可能很大，但比特币提供给投资者的安全性能要高于与其它竞争的资产，因此勒索私人密钥不太可能阻止比特币成为现金。

### An attacker could deceive investors regarding the utility of Bitcoin.
If investors were tricked into believing Bitcoin is less useful as money than another asset they would sell. If this could be achieved at sufficient scale Bitcoin would not become cash.

### 攻击者可能会欺骗投资者关于比特币的效用。
如果投资者被欺骗，认为比特币不如其它的资产有用，他们就会卖出比特币。如果这个规模足够大，比特币就不会成为现金。


**Safety Features**
* To the extent that this attack is only partially successful it would inoculate investors to future deception.
* This attack would be impossible to maintain for a long period of time.
* Access to information has been increasing at a rapid rate for the last 50 years and it seems unlikely that this trend will reverse.

**安全特性**
* 从某种程度上说，这种攻击只能是部分成功，它将使投资者能预防未来的骗局。
* 这种攻击是不可能长时间保持的。
* 在过去的50年里，获取信息的速度一直在快速增长，这种趋势似乎不大可能逆转。

**Past Attacks**

* False story that the "Bitcoin network" was hacked.,
https://www.wired.com/2014/03/bitcoin-exchange/
* False story that Bitcoin can't become cash because its supply is limited.,
https://www.theatlantic.com/business/archive/2013/12/why-bitcoin-will-never-be-a-currency-in-2-charts/282364/
* False story that Bitcoin can't become cash because its price is *currently* volatile.,
http://www.businessinsider.com/goldman-completely-debunks-all-the-arguments-for-bitcoin-2014-3
* Head of JP Morgan says Bitcoin is a fraud and can be shut down by governments.,
https://www.bloomberg.com/news/articles/2017-09-12/jpmorgan-s-ceo-says-he-d-fire-traders-who-bet-on-fraud-bitcoin

**过去的攻击**

* “比特币网络”遭到黑客攻击的虚假新闻。 https://www.wired.com/2014/03/bitcoin-exchange/
* 比特币因为它的供应有限所以不能成为现金的虚假新闻。 https://www.theatlantic.com/business/archive/2013/12/why-bitcoin-will-never-be-a-currency-in-2-charts/282364/
* 比特币不能成为现金的虚假新闻，因为它的价格目前是波动的。 http://www.businessinsider.com/goldman-completely-debunks-all-the-arguments-for-bitcoin-2014-3
* 摩根大通的负责人说，比特币是一种欺诈行为，可以被政府关停。 https://www.bloomberg.com/news/articles/2017-09-12/jpmorgan-s-ceo-says-he-d-fire-traders-who-bet-on-fraud-bitcoin


**No Impact to Adoption**
* In spite of the fact that these attacks have been constant and well funded, Bitcoin adoption has been rapid and has arguably been faster than the technical advancements, needed for Bitcoin to become cash.

**对采用没有影响**
* 尽管这些攻击持续不断，而且资金充足，但比特币的使用率增长很快，可以说比比特币成为现金所需的技术进步更快。

### An attacker could threaten to harm Bitcoin investors if they don't sell or hand over their bitcoin.
This is a duplicate of the threat: An attacker could extort the private keys from an investor. Using the threat of violence to force someone to hand over their private keys is essentially the same attack. The only difference is that this attack may be more likely to be attempted by larger criminal organization that have violent control over a population within a specific geography, whereas the other attack may be more likely to be attempted by individual criminals or smaller criminal organizations, but the safety features and the technical nature of the attack is identical.

### 如果比特币投资者不出售或交出比特币，攻击者可能会威胁损害比特币投资者。
这个和攻击者可以向投资者勒索私钥的威胁的一样。使用暴力威胁迫使某人交出其私钥是本质上同样的攻击。唯一的区别在于，这种攻击可能更有可能被大型犯罪组织在对特定地理区域内的人口进行暴力控制，而另一种攻击可能更可能由个人罪犯或较小的犯罪组织企图进行，但攻击的安全特征和技术性质是相同的。


### An attacker could threaten to harm anyone that attempts to buy or sell bitcoin.

If an attacker can make it impossible to buy or sell bitcoin he wouldn't have to force existing investors to sell or hand over bitcoin because an asset that can't be sold can't become money.

### 攻击者可能会威胁到任何试图购买或出售比特币的人。
如果攻击者使买卖比特币成为不可能，他就不必强迫现有的投资者出售或交付比特币，因为无法出售的资产不能成为金钱。



**Safety Features**
* As more of the world savings moves into digital assets this becomes a more difficult attack because digital assets can more easily be exchanged for one another anonymously.
* It is possible to buy and sell bitcoin anonymously through decentralized exchanges. In these exchanges the buyer can send cash through the mail and the seller can send bitcoin after the payment is received. The buyer relies on the reputation of the seller, including the number of previously successful sales, to avoid being ripped off. Millions of dollars in these type of Bitcoin transactions are executed daily at the time of this writing.
* As the threat of violence in commerce becomes a greater issue the utility of Bitcoin becomes more obvious. This could backfire on the attacker and accelerate the move from assets, such as physical cash, bank account balances, centrally controlled stocks and bonds, and precious metals into bitcoin because it is more difficult to steal.
* As the number of people that own bitcoin increases the more a given population would resist this attack.
* Some assets are more valuable specifically because they represent rebellion or resistance to the threat of violence. This could increase interest in Bitcoin in areas where it is prohibited by a corrupt government or other criminal organization.

**安全特性**
* 随着越来越多的世界储蓄转移到数字资产中，攻击变得更加困难，因为数字资产可以更容易地匿名交换。
* 通过去中心化交易可以匿名买卖比特币。在这些交易中，买方可以通过邮件发送现金，卖方可以在收到付款后发送比特币。买方依靠卖方的声誉，包括以前成功销售的数量，以避免被宰。在撰写本文时，每天有数百万美元这种类型的比特币交易发生。
* 随着商业暴力的威胁成为一个更大的问题，比特币的效用变得更加明显。这可能会对攻击者造成不利影响，并加速实物现金，银行账户余额，集中控股的股票和债券以及贵金属等资产转向比特币，因为偷取比特币更加困难。
* 随着拥有比特币的人数的增加，抵抗这种攻击的特定人就越多。
* 有些资产更具有价值，因为它们代表着对暴力威胁的反抗或抵制。这可能会增加腐败政府或其他犯罪组织禁止的地区对比特币的兴趣。

**No Impact to Adoption**
* Even the announcement that China, previously thought to be one of the most important regions for Bitcoin, will ban all Bitcoin transactions merely caused transactions to move to decentralized exchanges.

**对采用没有影响**
* 甚至是中国，以前被认为是比特币最重要的地区之一，也将禁止所有比特币交易。但也仅仅导致比特币交易转移到去中心化的交易所的影响。

**Past Attacks**
* China ban's Bitcoin exchanges.,
https://www.theverge.com/2017/9/18/16326078/chinese-regulators-ban-cryptocurrency-platforms-bitcoin

**过去的攻击**
* 中国禁止的比特币交易所。
https://www.theverge.com/2017/9/18/16326078/chinese-regulators-ban-cryptocurrency-platforms-bitcoin

## Bitcoin Merchants
In order for Bitcoin to become electronic cash (including a unit of account) merchants, that sell goods or services, must accept bitcoin for payment. If an attacker can prevent merchants from accepting bitcoin he would prevent Bitcoin from becoming cash.

## 比特币商家
为了使比特币成为电子现金（包括记帐单位），商家销售商品或服务，必须接受比特币支付。如果攻击者可以阻止商人接受比特币，他会阻止比特币成为现金。

### An attacker could threaten to harm anyone accepting bitcoin as payment.
An attacker could threaten merchants with direct violence or they could tell merchants that they must perform free labor or pay money, if they accept bitcoin in order to prevent Bitcoin from becoming cash (including the unit of account).

### 攻击者可能会威胁任何接受比特币付款的人。
为了防止比特币成为现金（包括记帐单位），攻击者可以用直接的暴力手段威胁商人，也可以告诉商人如果他们接受比特币，他们必须付出免费劳动或者付钱。

**Safety Features**
* Bitcoin transactions, like paper cash transactions, are difficult for governments to tax. This provides significant financial incentive for merchants to accept bitcoins secretly and to provide a "regular price" and a "bitcoin or cash price." In the USA this "cash price" is often 20% - 30% lower because sales tax, income tax, and payroll taxes to the business owner can easily exceed 60%. This means that the merchant is paid an additional 30% as compensation for the risk involved in making a "secret transaction."
* Attackers are aware that as they increase the cost of "in the open" transactions they increase the benefits of secret transactions. This makes these type of attacks risky as they could result in the loss of existing avenues of extortion.

**安全特性**
* 跟纸币现金交易一样，比特币交易对于政府来说是很难征税的。这为商家提供了重要的财务激励，以便秘密地接受比特币并提供“正常价格”和“比特币或现金价格”。在美国，这个“现金价格”通常低20％ - 30％，因为销售税，所得税和企业主的工资税可以轻易超过60％。这意味着商家有额外的30％作为进行“秘密交易”的风险的补偿。
* 攻击者知道，由于他们增加了“公开”交易的成本，他们就增加了秘密交易的好处。这使得这类攻击有风险，因为它们可能会导致现有敲诈勒索途径的丧失。

**Medium Risk**
* Although it is unlikely this attack could prevent Bitcoin from becoming cash it could possibly slow adoption.

**中等风险**
* 虽然这种攻击不太可能阻止比特币成为现金，但可能会延缓采用。


**Past Attacks**
* US Government requires capital gain tax calculation on every $1 cup of coffee transaction.,
https://www.thebalance.com/how-bitcoins-are-taxed-3192871

**过去的攻击**
* 美国政府要求每消费1美元的咖啡交易就要缴纳资本增值税。
https://www.thebalance.com/how-bitcoins-are-taxed-3192871

## Bitcoin Developers
Bitcoin developers are critical for the continued improvement of Bitcoin software. Without Bitcoin developers the Bitcoin code would not be improved and could become unusable if vulnerabilities discovered in the future are not repaired.

## 比特币开发商
比特币开发人员对比特币软件的持续改进至关重要。如果没有比特币开发人员，比特币代码将不会被改进，如果未来发现的漏洞未被修复，则可能无法使用。

### An attacker could threaten to harm anyone contributing to Bitcoin software.
If an attacker could convince developers that contributing to Bitcoin is likely to result in their death or kidnapping it is possible that Bitcoin would fail to become cash.

### 攻击者可能会威胁损害比特币软件开发人员。
如果攻击者威胁开发者，对比特币软件作出贡献可能导致他们的死亡或遭到绑架，比特币成为现金就会失败。

**Safety Features**
* Bitcoin development can be done anonymously. In fact the original white paper author and first Bitcoin developer, known as Satoshi Nakamoto, has an identity that remains unknown.
* Bitcoin is the result of over 30 years of research and development by the cypher punk community. This community has included the very best software security researchers and cryptographers that have invested the most basic building block of Internet and computer security (Public Key Cryptography). If any group could operate anonymously, and effectively, it would be this community.
* If a security researcher that is part of a criminal organization discovered a way to significantly improve Bitcoin the best way to profit from this knowledge would be to purchase a large amount of Bitcoin on margin and then anonymously publish the code. The market price of Bitcoin would increase and he would make a large amount of money. In this way, even well funded organizations that wish to destroy Bitcoin development would likely end up funding improvements through "reverse-corruption."
* There are a large and growing number of Bitcoin developers.

**安全特性**
* 比特币开发可以匿名完成。事实上，原来的白皮书作者和第一个比特币开发者中本聪，他的身份还是未知的。
* 比特币是密码朋克社区超过 30 年的研究和开发的结果。这个社区包括了最好的软件安全研究人员和密码学家，并形成了互联网和计算机安全最基本的组成部分(公钥密码术)。如果有一个组织可以匿名运作而且高效的话，那就是这个社区。
* 如果作为犯罪组织一部分的安全研究人员发现了一种显着提高比特币的方法，那么从这些知识中获利的最好方法就是以保证金购买大量比特币，然后匿名发布代码。比特币的市场价格会上涨，他会赚很多钱。通过这种方式，即使是那些希望摧毁比特币发展的资金雄厚的组织，也有可能通过“反腐败”来改善资金状况。
* 现在有很多开发人员，并且开发人员正变得越来越多。

**Past Attacks**
* Satoshi stopped contributing to Bitcoin out of fear of harm.,
https://bitcointalk.org/index.php?topic=1813452.0
* Tim May left the cypherpunk mailing out of fear of the US Government after 9/11.,
https://www.youtube.com/watch?v=TdmpAy1hI8g&t=2654s (42:30)

**过去的攻击**
* 由于担心受到迫害，中本聪停止了对比特币开发的贡献。
https://bitcointalk.org/index.php?topic=1813452.0
* 9月11日之后，Tim May 因为担心美国政府迫害退出了加密社区邮件列表。
https://www.youtube.com/watch?v=TdmpAy1hI8g&t=2654s (42:30)

**No Impact to Adoption**
* Given the roots of the Bitcoin development community it is unlikely that this attack would be successful.

**对采用没有影响**
* 考虑到比特币开发社区的根基，这种攻击不可能成功。

### An attacker could bribe or extort a Bitcoin developer into introducing a security flaw into Bitcoin.
If an attacker could get flawed code into the next version of Bitcoin he could destroy the features of Bitcoin that make it useful as money.

### 攻击者可能通过贿赂或勒索比特币开发人员引入比特币安全漏洞。
如果攻击者能够将有缺陷的代码加入到下一个版本的比特币中，他可能会破坏比特币的成为有用现金的功能。

**Safety Features**
* Bitcoin code reviewed by hundreds of software security experts before any change is introduced. It would be very hard to construct a change that contained a security flaw that wouldn't be noticed by the Bitcoin community at large.
* The Bitcoin community is very risk averse. It is aware that the success of Bitcoin would result in the destruction, or at least a drastic reduction in funding, of many monopolies and other criminal organizations. As a result it is hyper vigilant regarding code changes.
* Side chains will allow new features to be tested with millions or billions of dollars worth of bitcoin before exposing all of Bitcoin to the risk associated with any new feature or change. As more money is available for an attacker, without being a threat to the core Bitcoin network, the more unlikely it is that a flaw will remain undiscovered until it is implemented in Bitcoin.
* A Bitcoin developer will only have one chance to introduce a flaw if he is caught as his credibility will be destroyed.

**安全特性**
* 数百名软件安全专家在进行任何更改之前，都会先审查比特币代码。构建一个不会被比特币社区注意到的安全缺陷的变更将是非常困难的。
* 比特币社区非常厌恶风险。它意识到比特币的成功会导致许多垄断组织和其他犯罪组织的破坏，或至少大幅度减少资金。因此，对代码更改非常警惕。
* 在将所有比特币暴露在新特性或变化相关的风险之前，侧链将允许新功能使用数百万或数十亿美元的比特币进行测试。在不用对比特币核心网络构成威胁的情况下，攻击者可以获得越多的金钱。更不可能的是在更改应用之前，漏洞还未被发现。
* 比特币开发者只有一次机会引入漏洞，如果被抓住，他将没有任何信誉可言。

**Past Attacks**
* Mike Hearn attempts to remove block limit safety feature,
https://blog.plan99.net/the-resolution-of-the-bitcoin-experiment-dabb30201f7
* Gavin Andresen attempts to remove block limit safety feature,
https://www.coingecko.com/buzz/gavin-andresen-unlimited-block-size-fine)

**过去的攻击**
* Mike Hearn 试图删除块限制的安全功能
https://blog.plan99.net/the-resolution-of-the-bitcoin-experiment-dabb30201f7
* 加文·安德烈森试图删除块限制安全功能。
https://www.coingecko.com/buzz/gavin-andresen-unlimited-block-size-fine）

**No Impact to Adoption**
* Although it appears this attack has been attempted more than once in recent years no security flaws have been introduced to Bitcoin.

**对采用没有影响**
* 尽管近年来这种攻击似乎已经不止一次地发生过，但比特币还没有被引入过任何安全缺陷。

## Bitcoin Hardware Manufacturers
Bitcoin hardware manufactures produce hardware for mining. This mining hardware is critical for confirming Bitcoin transactions.

## 比特币硬件厂商
比特币硬件制造商生产挖矿硬件。挖矿硬件对于确认比特币交易至关重要。

### An attacker could threaten to harm Bitcoin mining hardware manufacturers if they sell to the public.
If cutting edge Bitcoin mining hardware was no longer available it would make confirming transactions less secure. This could reduce the security of Bitcoin enough to prevent it from becoming cash.

### 攻击者可能以威胁损害比特币挖矿硬件制造商来阻止矿机出售。
如果先进的比特币矿机不再可用，那么确认交易就会变得不那么安全。这可能会降低比特币的安全性。

**Safety Features**
* Mining hardware makes confirming transactions more efficient, but this action may motivate the Bitcoin community enough to overcompensate for the loss of efficiency using less efficient hardware.
* There are currently more than one mining hardware manufacturer based in more than one geographic region. And it seems likely that more competition in the mining hardware space will result in more manufacturers over time. This would make this attack more difficult over time.
* As the amount of computing power decreases on the network the rewards for operating mining hardware increases. If this attack was executed it would make Bitcoin mining more profitable and this would attract additional manufacturers and mining operators.

**安全特性**
* 矿机使得确认交易更有效率，但是这种行动可能会充分激励比特币社区过度补偿由于使用效率较低的硬件造成的算力损失。
* 目前在不止一个地理区域内有多个挖矿硬件制造商。而且，挖矿硬件领域的竞争可能会随着时间的推移而导致更多的制造商。所以随着时间的推移这种攻击更加困难。
* 随着网络中算力的减少，运营挖矿硬件的收益也随之增加。如果这个攻击被执行，这将使得比特币矿业获利更多，这将吸引更多的制造商和挖矿人员。


**Past Attacks**
* No past attacks have been disclosed.

**过去的攻击**
* 尚未发现此类攻击事件。

**No Impact on Adoption**
* It is unlikely this attack would significantly slow adoption.

**对采用没有影响**
* 这种攻击不太可能明显地缓慢比特币的采用。

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
