> 本文翻译自：https://hackernoon.com/a-beginners-guide-to-blockchain-d04266844e7
>
> 作者：Febin John James， Author of Cloud Is a Piece of Cake
>
> 译者：区块链中文字幕组 Chuan
>
> 翻译时间：2018-04-02


### A Beginner’s Guide to Blockchain

### 区块链新手指南

I don’t get why people find it difficult to understand Blockchain. I wonder why I myself didn’t. It was in 2013 I first heard about Bitcoin (yea, too late). I was poor to purchase one, so tried mining it. If I had been successful, you wouldn’t be reading this. Later, I thought of studying its underlying technology, the Blockchain. But, I was too busy with my startup (that didn’t work out either).

我不明白为什么人们很难理解区块链。我也想知道为什么我自己也不明白。2013年，我第一次听说比特币。我没有钱，连一个都买不起，所以就尝试挖矿了。如果我那时成功了，你现在就不会在看这篇文章。后来，我想着研究一下它的底层技术－区块链。但是，我那时忙着自己的公司（也没能幸存下来）。

#### So what is this “Blockchain”? 区块链是啥东东？

There are two things. A block and a chain. At a very high level, it is just a chain of blocks. Since it’s inside computers, we can rule out the physical stuff. Here digital information is divided into blocks and linked together. For example consider the following blocks, each represent a country. Each of them contains the city names of the respective country.

有两样东西。块和链。说的更高级一点，它是块形成的链。因为它存在于计算机中，所以我们能够排除掉实体的东西。数字信息被划分成块并连接起来。比如，下面的这些块，每个代表一个国家。每个块都包含对应国家的一些城市名称。

Wait, there is something more. Each of these blocks has something called a hash. A hash is a set of characters (eg. “1hi515AHA5H” ). Hash is derived from the information contained in the block. The block of U.S.A has cities New York, Los Angeles, and Chicago. So the hash would be something like “NYLAC” (Technically that’s not the case, but you get the idea).

等等，还有些东西。每个块中还有个“哈希”的东西。哈希是一串字符（比如，“1hi515AHA5H”）。哈希是从块中包含的内容获得的。图中“U.S.A”块中包含的城市有纽约、洛杉矶和芝加哥。所以，它的哈希就有点像“NYLAC”（技术上来说，并不是这样，但是你明白这表示什么意思）。

Every successive block will contain the previous block’s hash. This is what binds them together (The force). If someone tampers the first block to add the city Boston. The new hash becomes “NYLACB”. However, the succeeding block of India has already stored the hash as “NYLAC”. This mismatch will break the chain. So the purpose of hash is to make sure no one tampers it.

每个后续的块将包含前一个块的哈希。这就是将它们绑定在一起。如果有人想篡改第一块，来把波士顿加进去。新的哈希就变成“NYLACB”。可是，后面的India块已经储存了前面块的哈希“NYLAC”。这种不一致就将破坏这个链的完整性。所以，哈希的目的是确保没有人篡改区块链上的内容。

What if someone changes the contents of a block and update the hash of successive blocks? This is possible but there is one thing I didn’t tell you. The data of the blockchain doesn’t lie in one computer. It is replicated in the computers of every user in the network. If you join a blockchain network, your computer will download these blocks. If someone tampers his version, the network will consider what majority say is correct.

要是有人改变一个块里的内容并更新后续块的哈希会怎么样？这是有可能的，但是有一件事我没跟你讲。区块链的数据并不是存储在一台电脑上。它被复制在区块链网络上的每一台电脑里。如果你加入这个区块链网络，那么你的电脑会把这些区块下载到本地。如果有人修改他电脑上区块中的内容，这个网络只认为网络上绝大多数电脑的内容才是正确的。

One more thing, in a Blockchain network, not only data but the program is also replicated. Computers collectively execute the program. Most internet apps are centralised. Consider Facebook, its data and program lies on its servers. Your computer requests information from Facebook’s server on a need to know basis. In case of blockchain, there is no central thing. It relies on its user’s computer to host its program. Yes, this means if every computer in the blockchain network switches off, it’s dead.

还有一件事，在区块链网络中，不仅数据，就连形成这一网络的程序也是可复制的。计算机集体执行这个程序。大多数互联网应用程序都是中心化的。比如，Facebook的数据和程序都在它的服务器上。你的电脑从Facebook的服务器上请求信息。以区块链为例，没有中心化的东西。它依赖用户的电脑来运行它的程序。是的，这意味着，如果网络上的所有电脑都关机的话，那么这个网络就没用了。

#### Public Blockchains 公有链

Does this mean Blockchain is formed by a group of people who keeps their computers running for goodwill? What is the use of these tamper-proof blocks?

这意味着区块链是被一组有意愿让他们的电脑一直运行的人形成的？这些防修改的区块有什么用？

Blockchain networks have one or more functionalities. Bitcoin is a digital currency and a payment system. Its tamper-proof blocks hold ledger of all transactions. The people who sacrifice their computers are called miners. They get rewarded in bitcoins .

区块链网络有一个或多个功能。比特币是一种数字货币、一种支付系统。它的防篡改区块包含所有交易的账本信息。那些“贡献”他们电脑资源的人被称作“矿工”。他们通过挖矿获得比特区作为奖励。

Ethereum has an additional functionality. It can host your code. Developing a blockchain from scratch and building your own community would be very difficult (Remember people has to sacrifice their computers for you?) . Ethereum takes care of the heavy lifting. You need to pay a fee depending on the computational costs.

以太坊还有个功能。你的程序代码可以运行在它上面。从头开发一个区块链，建立自己的社区是非常难的。以太坊关心这一难题。取决于计算成本你需要支付一笔费用。

Blockchain apps don’t have to be just payments systems or cryptocurrencies. It could be anything, like a social network, a learning platform like [LiveEdu](https://tokensale.liveedu.tv/), etc.

区块链应用程序不仅仅只是支付系统或加密货币。它的用途可以是多种多样，像社交网络，学习平台[LiveEdu](https://tokensale.liveedu.tv/)等等。

#### Private Blockchains 私有链

Bitcoin, Ethereum, etc are examples of the public blockchain. Anyone can be a part of it. What if we want to make a private blockchain network? Why would someone need a private blockchain for? Have a look at these stories.

比特币，以太坊等都是公有链的代表。任何一种都是它的一部分。如果我们想创建一个私有区块链会怎么样？为什么有人需要私有区块链？看看这些事例。

**Mark and Sara 马克和莎拉**

Mark hasn’t paid his rent for five months. When Sara questions he promise to pay later. She is helpless. She can’t afford a lawyer. Courts take eight months to almost a year to enforce action. The only option is to persuade Mark.

马克已经五个月没会租金了。莎拉问起的时候，他答应迟一点付。莎拉感到很无助。她也负担不起律师费。法院要花8个月到1年的时间来执行审判。唯一的选择就是说服马克。

**Joe’s business 乔伊的生意**

Joe is a businessman. He does business with different corporates on a frequent basis. A few months ago he signed a contract with a retailer. Though the conditions of the contract were met. The retailer refused to pay. These people take advantage of the legal system and persuade Joe to settle for less pay. Joe had such experiences before. In some cases, he went to court. The time and money he spent there cost him his profits.

乔伊是个商人。他经常和不同的公司有生意往来。几个月前，他和一家销售商签了合同。尽管合同中的条件已经具备，可是销售商拒绝付款。这些人利用法律系统，劝说乔伊少要一些。乔伊之前经历过这种情况。有时候，他会诉诸法律。可是，他花在上面的钱和精力抵得上他赚的钱。

**How do we help Sara and Joe? 我们怎么帮助莎拉和乔伊**

Have we solved this problem elsewhere? In Sara’s case, we need to make Mark pay the rent every month. A time-based trigger. Your calendar app uses such trigger to give you notifications of predefined events.

我们在别的地方解决过这种问题吗？以莎拉来说，我们需要让马克每月支付租金。一种基于时间的触发器。你的日历APP使用这样的触发器来发送预先定义的事件的提醒。

In Joe’s case, once terms of the agreement is met the party needs to pay. It’s a condition based trigger. Consider the last time you purchased an ebook from Amazon. Amazon will only deliver it once the payment is confirmed.

乔伊的情况则是，一旦合同的条款满足，对方需要付款。这是一种条件触发器。想想你上一次从亚马逊上买书的情况。亚马逊只有在支付被确认后才会寄出商品。

The point is computer programs execute such instructions consistently. It did when you clicked on this article, scrolled down, etc . In order to help Sara, we need to convert the agreements of the contract into code.

问题在于计算机程序能始终如一地执行这样的指令。为了帮助莎拉，我们需要将合约中的协议转换成代码。

***Pseudo code of the smart contract between Sara and Mark 莎拉和马克之间智能合约的伪代码***

`If today’s date is 30th and rent is not paid then
Transfer $500 from Mark’s account to Sara’s account`

`如果今天是30号，租金没有付的话，那么从马克的账户中转500块到莎拉的账户中。`

But where do we deploy this code? It should be deployed on computers of all parties involved. Sara’s and Mark’s bank will be part of a private Blockchain network. Joe and Sara will sign a coded contract(a.k.a smart contract). Then it’s deployed on the network. Both Mark’s and Sara’s bank will have a copy. On 30th of every month when the clock ticks 12.00. The agreed amount gets transferred from Mark’s account to Sara’s account. Joe started using smart contracts to enforce his clients to pay the agreed amount.

可是，我们要将这个代码部署在哪里？它应该被部署在涉及这件事的所有人员的电脑上。莎拉和马克开设账户的银行是私有区块链网络的一部分。乔伊和莎拉签署一个代码化的合同（又称为“智能合约”）。然后它就被部署在区块链网络上。马克和莎拉的开户银行都有一个备份。每个月的最后一天，当时钟敲响12下，合同中约定的金额就被从马克的账户转到莎拉的账户里。乔伊开始使用智能合约来要求他的客户支付双方之前谈好的钱款。

*Sara is happy because she doesn’t have to trust Mark’s consent to transfer rent. Joe’s glad because he doesn’t have to go to a court for justice. Instead, he can spend those efforts to grow his business.*

*莎拉很开心，因为她不必相信马克同意转账给他的话。乔伊很高兴，因为他无需上诉至法院要求裁决。相反，他可以把这些精力放在壮大他的生意上。*

Private blockchain will be restricted to the parties involved in the business. Joe won’t be a part of the Sara’s and Mark’s Blockchain network.

私有链被仅限于涉及到具体事务当中的人。乔伊不是莎拉和马克的区块链网络中的一部分。

#### The Way Ahead 再进一步

Now that you have some idea, you should take this course on edX(It’s free). It will teach you to build apps on Blockchain.

现在你应该有点明白区块链大概是怎么回事了，那么你可以[在edX上学习这门课](https://www.edx.org/course/blockchain-business-introduction-linuxfoundationx-lfs171x)（它是免费的）。这门课程将教会你如何在区块链上开发应用程序。





------

**区块链中文字幕组**

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号：w1791520555。

[点击查看 GITHUB 及更多的译文](https://github.com/BlockchainTranslator/EOS)

**本文译者介绍**
Chuan，区块链技术爱好者。欢迎加我的微信：youyuxiaochuan

译文版权所有，转载需完整注明以上内容。

