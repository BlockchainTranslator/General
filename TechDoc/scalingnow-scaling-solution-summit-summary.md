> 本文翻译自：https://medium.com/@web3/scalingnow-scaling-solution-summit-summary-be30047047bf
> 作者：Web3 Foundation Team
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator) [鱼](https://github.com/oscnet)
>
> 翻译时间：2018-3-29
>

# ScalingNOW! — Scaling Solution Summit Summary – Web3 Foundation Team – Medium

# ScalingNOW！— 可扩展性解决方案峰会摘要 – Web3 基金会 – Medium

![][1]

The two-day ScalingNOW! workshop in Barcelona brought many teams together from across the blockchain space and from around the globe to share their ideas on scaling solutions. Once the teams touched down on Sunday night, the discussions began over the welcome dinner and it was clear that everyone was excited to get cracking.

为期两天的巴塞罗那 ScalingNOW！专题研讨会，集合了来自区块链界和全球各地的许多团队，他们一起分享交流了各自在可扩展性问题上的解决方案。团队刚在周日晚上抵达，热烈的讨论就在欢迎晚宴上开始了，很明显的，所有人对破解这个难题都感到非常激动。

In addition to this blog post we have created a detailed spreadsheet of the scaling solutions that presented at the workshop:

除了这篇博文之外，我们还创建了电子表格，详细介绍了研讨会上展示的可扩展性问题解决方案：

[**Scaling Solution Summary Spreadsheet**][2]

In this post, we will recap our findings from the first day of the event. We will briefly cover the purpose of the event, what scalability means, the leading solutions to scalability in the near term and some of our thoughts on the current state of the solutions.

在这篇文章中，我们将从活动的第一天开始回顾。简要介绍活动的目的，什么是可扩展性问题，近期可扩展性问题的主要解决方案以及我们对解决方案当前状态的一些想法。

### **The Objective**

### **目标**

![][3]

Pre-conference multi-team dinner!

会前团队晚宴！

We believe that in the current ecosystem ["scalability is still the key obstacle facing blockchain"][4]. Teams around the world are building scaling solutions, but until now they have been working in moderate isolation without much cross-team collaboration.

我们认为在当前的生态系统中[“可扩展性仍是区块链面临的主要问题”][4]。世界各地的团队都在想方设法以解决可扩展性问题，但是一直以来，都是各自为政，很少有跨团队的协作。

The ScalingNOW! event was also an opportunity for those teams working on scaling solutions to meet each other as well as meeting the DApp developers (on day 2) affected by high fees. To be invited, teams needed to be working on a scaling a solution meant for deployment either now or in the next few months.

ScalingNOW！对于那些致力于解决扩展性问题的团队以及 DApp 开发人员（第2天）来说，是一个相互交流的机会。被邀请的团队都需要在当前或未来几个月内部署可扩展性问题的解决方案。

This topic is extremely significant for the Web3 Foundation because both long and short term scaling solutions are necessary in order for the Foundation's vision to materialise.

这对于 Web3 基金会来说非常重要，因为不管是面向长期的还是而向短期的可扩展性解决方案，对实现基金会的愿景都是必要的。

In the short term we can solve some of the scalability issues with a Proof of Authority (POA) side chain which can be linked to Ethereum via a bridge. Parity Technologies presented Parity Bridge and discussed how it can utilise low-cost POA networks to mitigate high fees. While this helps in the short term, the bridge is also one of the core elements of Polkadot (a longer term scaling solution stewarded by the Web3 Foundation).

在短期内，我们可以通过权威证明（POA）侧链来解决一些可扩展性问题，这些侧链可以桥接到以太坊。Parity Technologies 展示了 Parity Bridge 技术，并讨论了它如何利用低成本的 POA 网络来降低高额手续费用。短期内对解决可扩展性的问题有所帮助，而且 Parity Bridge 也是波卡 (Polkadot, 一个由 Web3 基金会支持的长期可扩展性解决方案）的核心要素之一。

### **What is scalability?**

### **什么是可扩展性？**

In the context of Ethereum, we define scalability as the capacity of the main network to improve performance (throughput, latency) as the number of users (DApps) increases, without making a difference to the users' experience (gas prices, transaction times). The network architecture must be able to adapt to new demands as adoption increases, not the other way around.

在以太坊的环境中，我们将可扩展性定义为主网的容量，随着用户数量（DApp）的增加，其性能（吞吐量，延迟）也相应提高，而不会对用户体验（如 gas 价格，交易时间）产生影响。 随着使用率的增加，网络架构必须能够适应新的需求，而不是相反。

We saw the scaling issue most clearly when CryptoKitties hit peak activity. Transactions on Ethereum quickly became very expensive and the network slowed down.

当以太猫游戏达到活动高峰期时，我们很清楚地看到了可扩展性问题的存在。很快地以太坊交易费变得极高，网络也慢如蜗牛。

Dieter Shirley, a developer from CryptoKitties stated that "70% of gas is being consumed on smart contracts and we aren't optimised for that. Also, the model of storing everything forever just doesn't scale."

来自以太猫的开发人员 Dieter Shirley 表示：“ 70％ 的 gas 在运行智能合同之中被消耗掉了，我们没有对此进行优化，而且其永久存储数据的模式不能规模化。”

### **Main Solutions — State Channels and Sidechains**

### **主要解决方案 - 状态通道和侧链**

The two main solutions that are ready for use today are state channels and sidechains. These solutions move some of the transaction logic off-chain, but ultimately rely on the main chain for final settlement.

状态通道和侧链是现在可以使用的两个主要解决方案。这两个解决方案将部分交易逻辑移到链外，但最终结算依靠主链进行。

There was also an alternative solution presented by the TrueBit team (more details are given later in this piece).

TrueBit 团队提供了另一种解决方案（更多细节将在本文后面给出）。

**State Channels** provide a direct one-to-one interaction between two addresses (for example, two users). The bulk of the computation involved in the interactions between users are calculated and communicated off-chain in a cryptographically secure fashion; however, the final settlement of balances occur on the mainnet Ethereum chain.

**状态通道** 提供两个地址（例如两个用户）之间的直接一对一交互。涉及用户间交互的大量计算都是以密码安全的方式进行链下计算并传递的；但是，最终的余额结算在以太坊主网链上进行。

Attendee projects: µRaiden, Counterfactual, FunFair, SpankChain, Decentraland.

参与项目：μRaiden，Counterfactual，FunFair，SpankChain，Decentraland。

**Sidechains**, also known as bridged chains or parachains, are chains that run in parallel to the main Ethereum chain. These chains will have their own consensus mechanism which does not have to be the same type of mechanism as deployed on Ethereum. For example, it is possible to have a Proof-of-Authority (PoA) or a Proof-of-Stake (PoS) sidechain. These chains are not fully independent but ultimately rely upon Ethereum for final settlement. However, they do provide for multiple users to temporarily interact with each other off-chain.

**侧链**，也称为桥链（bridged chains）或平行链（parachains），是与以太坊主网链平行运行的链。这些链使用自己的共识机制，不必同以太坊上部署的共识机制相同。例如，这些侧链有可能采用权威证明（PoA）或权益证明（PoS）机制。这些链并不完全独立，并最终依靠以太坊进行结算。但是，它们确实提供了链下多用户之间临时相互交互的功能。

Attendee projects: Parity Technologies, POA Network, Cosmos, Plasma.

参与项目：Parity Technologies, POA Network, Cosmos, Plasma。

### **Timeline**

### **时间表**

In order to help guide DApp developers we are providing the following timeline to show which scaling solutions are ready _"NOW!"_ and which solutions will be ready in the near future.

为了帮助指导 DApp 开发人员，我们提供了以下时间表，用来指示哪些可扩展性解决方案 _“现在”_ 已经可以使用， 哪些需要在不久的将来才能就绪。

> **NOW!**

> **现在！**

* µRaiden — ERC20 & 223 State Channel.

* μRaiden - ERC20 和 223 状态通道

* Decentraland — Custom / Purpose-built State Channel.

* Decentraland — 定制/专用状态通道

* Parity Tech — Sidechain Bridge.

* Parity Tech — 侧链桥接

* POA Network — Sidechain solution.

* POA Network — 侧链解决方案

> **< 4 months**

> **< 4 个月**

* FunFair — Generalised State Channel.

* FunFair - 广义状态通道。

> **< 6 months**

> **< 6 个月**

* Cosmos — Sidechain solution (interoperating blockchains).

* Cosmos — 侧链解决方案（互操作区块链）

> **~ 6 months**

> **〜 6 个月**

* Counterfactual — Generalised State Channel.

* Counterfactual — 广义状态通道

* TrueBit — Off-chain solution for computationally-heavy DApps.

* TrueBit — 针对大计算量的 DApp 的链外解决方案

> **< 9 months**

> **< 9 个月**

* Plasma — Hierarchical Sidechain solution..

* Plasma — 分层侧链解决方案

### **Project Summaries —** State Channel Solutions

### **项目总结 -** 状态通道解决方案

In this section we will summarise the key points regarding the state channel scaling solutions presented by those who visited Barcelona.

本节，我们将总结参加巴塞罗那的团队提出的状态通道可扩展性解决方案的关键点。

> **µRaiden**

> **μRaiden**

* **What**: A state channel exclusively for tokens (only the ERC20 and ERC223 standards). If you want to use your own tokens you need to deploy your own contract.

* **说明**：专用于通证（仅限于 ERC20 和 ERC223 标准）的状态通道。如果您想使用自己的通证，则需要自己部署智能合约。

* **When**: Ready!

* **时间**：已就绪！

* **Security**: Relies on the main chain to be secure, live, and useable. It is not possible to open more chains than main chain can handle. At the moment µRaiden doesn't yet understand and obey whitelists or blacklists: this a problem when the channel closes.

* **安全**：依靠主链的安全性，已在线可使用。打开比主链可处理的更多链是不可能的。目前，μRaiden 还不能理解处理白名单或黑名单：当通道关闭时，这是一个问题。

* In addition, users must keep private keys safe

* 另外，用户必须保证私钥的安全

* **Useability**: A payment receiver has to run a light client or a full node as they need to check the transaction. The sender doesn't need to do so since they are the ones who open the channel and knows its state. There is a gas cost of 100k to open the channel, but apparently less to close it.

* **可用性**：付款接收方必须运行轻客户端或完整节点，因为他们需要检查交易。而付款方则不需要，因为是他们打开通道并且知道其状态。打开通道需要 100k 的 gas 成本，但显然关闭时不用这么多。

> **Counterfactual**

> **Counterfactual**

* **What**: Looking into creating a generalised state channel beyond payments: the team suggested that their channels could be used for playing chess (with smart contract to mediate) or more generally as a means exchanging of information.

* **说明**：研究创建不仅仅用于支付的广义状态通道：团队说他们的通道还可以用于下棋（通过智能合约进行），或者更一般地可以作为信息交换的手段。

* **When**: in 6 months.

* **时间**： 6 个月内。

* **Security**: Instant finality from the perspective of the state channel: i.e. the settlement of payment is instant, but only if the other party is available. This assumes the underlying chain is also live and secure. The only acknowledged attack on the state channel is if someone reports an out-of-date (old state) and then refuses to respond. If counterparty is cost minimising they can slow down transaction (DOS), which costs, but this doesn't allow for stolen funds.

* **安全性**：从状态通道的角度来看即时结算：假定底层链在线并且安全，只有当另一方在线时，付款结算才是即时的。对状态通道的唯一确认的攻击是，如果有人广播过时的状态（旧状态），然后就拒绝回应。如果交易对手使用成本最小化策略，他们就可以减慢交易速度（DOS），但是资金不会被盗。

* **Useability**: Aiming to provide an API so developers don't need to know exactly how their code works in order to use it. The use of state channels is suggested to provide response times seen with web applications; however, the team was keen point out that not all problems can be put into a channel ("not channeliseable").

* **可用性**：旨在提供一个 API，以便开发人员不需要确切知道他们的代码如何工作就能使用。建议状态通道提供 Web 应用程序类似的响应时间；然而，该团队敏锐地指出，并非所有问题都可以让通道来解决（“不可通道化”）。

> **FunFair**

> **FunFair**

* **What**: Building a casino app which is directly P2P via a one-on-one state channel: i.e. a gambler vs a casino. FunFair are creating the app but will not act as the casino. Their state channel works in the following way:

* **说明**：通过一对一状态通道建立一个直接的 P2P “赌场”应用：即 “赌徒”与“赌场”。 FunFair 正在创建应用，但不会充当“赌场”。他们的状态通道按以下方式工作：

1. open channel,

1. 开放渠道，

2. lock funds,

2. 锁定资金，

3. play game,

3. 玩游戏，

4. close channel and release funds (settle balances).

4. 关闭通道并释放资金（结算余额）。

* FunFair said that their state channel is general and not just limited to payment transfers, but it has an off-chain state machine. They also stated that they developed a solution to create a shared random no scheme alongside state channel: this is to enable provable fairness.

* FunFair 表示，他们的状态通道是一般性的，不局限于支付转账，而是有一个链下的状态机。他们还表示，他们制定了一个解决方案，为了实现可证明的公平，在状态通道旁边建立一个共享的随机方案。

* **When**: Have launched an minimum viable product already, but expect more in 4 months. Code will eventually be published.

* **时间**：已经推出了最小可行产品，但是离代码最终发布还需要 4 个月以上。

* **Security**: Lots of different things can go wrong. The games are web applications which can be vulnerable to the usual web security problems (this is off-chain); however, all transactions are signed as with regular Ethereum transactions, but users must manage own private keys.

* **安全**：有很多可能出现问题。游戏是一个 Web 应用，所以它容易受到 Web 安全问题的影响（链下）；然而，所有的交易都是通过普通的以太坊交易进行签名，用户必须管理好自己的私钥。

* **Useability**: Opening a channel takes 15–20 seconds. The number of transactions is not capped by the FunFair state machine but by how many open connections Ethereum can handle.

* **可用性**：打开一个通道需要 15 - 20 秒。交易数量不受 FunFair 状态机限制，而是由以太坊能够处理的开放连接数所限制。

> **SpankChain**

> **SpankChain**

* **What**: Still at the early stages of thinking and planning out what their state channel solution will look like. Want to create a generalised state channel that does more than just payment.

* **说明**：仍处于思考和规划状态通道解决方案的初期阶段。想要创建一个不局限于支付的广义状态频道。

* **When**: No indication yet. Only just put an idea together about a month ago.

* **时间**：尚未清楚。一个月前才有想法。

* **Security**: No indication yet.

* **安全性**：不清楚。

* **Useability**: No indication yet.

* **可用性**：不清楚。

> **Decentraland**

> **Decentraland**

* **What**: The project is a virtual world where parcels of land have been sold. The auction already happened (December 2017) and was all off-chain.

* **说明**：该项目是一个虚拟的世界，土地已经出售。并已经进行了拍卖（2017年12月），并且都是在链下进行的。

* **When**: Happened (December 2017, custom solution). New use-cases and solutions possible but no date indicated for completion.

* **时间**：发生时（2017年12月，定制解决方案）。可能会有新的使用案例和解决方案，但没有表明完成的日期。

* **Security**: The auction had a trusted set up, but was fully verifiable. Some users ran scripts (off-chain) to validate that the state transitions were fully valid.

* **安全**：拍卖有一个信赖设置，但可以完全验证。一些用户使用脚本（脱链）来验证状态转换的有效性。

* **Useability**: The solution was custom built for the Decentraland auction which means that a lot of work could be involved to adapt it to another project. It should be noted that the state transitions had to be completely serialisable which limits throughput: 10s-100s requests per second, and theoretical it could handle 1000s if is limited commitment failures.

* **可用性**：该解决方案是为 Decentraland 拍卖而定制的，这意味着如果要在其它项目中使用，可能会涉及许多工作。应该注意的是，状态转换必须完全串行化，这限制了吞吐量：每秒 10s-100s 的请求数，在承诺失败（commitment failures）的条件下，理论上它可以处理 1000s。

### **General problems with state channels**

### **状态通道的一般性问题**

* Vulnerable to denial of service attacks

* 易受拒绝服务攻击

* Ethereum must be deposited and locked-up while channel is in use

* 在使用通道时，资金必须在以太坊中存放并锁定

* There is a challenge for application developers to change the way they design apps: they need to build with state channels in mind.

* 应用程序开发人员面临挑战，需要改变他们设计应用程序的方式：他们需要考虑构建状态通道。

* There is a dependency on multi-signature contracts. We've seen a range of attacks against these in the last year which highlights a potential risk if relied upon heavily. Hopefully, these become more robust over time.

* 对多重签名合约有依赖性。我们在去年看到了一系列的针对性攻击，如依赖过度，就会凸显出潜在的风险。希望随着时间的推移系统会变得更加强壮。

* Existing tools need to start integrating state channel functionality. Currently, limited progress has been made here.

* 现有工具需要开始集成状态通道功能。目前，在这方面取得的进展有限。

* Lack of a general timestamping service.

* 缺乏一般性时间戳服务。

* Not all applications are "channeliseable".

* 并非所有的应用都是“可通道化”的。

* State channels work in applications where you know the other parties in advance, although this isn't strictly necessary it does invoke a certain amount of trust before creating the channel.

* 状态通道工作在对其他各参与方事先有所了解的应用中，虽然这并非严格必要，但创建通道之前还是需要有一定程度的信任。


### **Project Summaries** — Sidechain Solutions

### **项目总结**  - 侧链解决方案

![][5]

Web3 Foundation Executive Director Peter Czaban presents to ScalingNOW!

Web3 基金会执行主任 Peter Czaban 在 ScalingNOW！中介绍

In this section we will summarise the key points of the solutions who visited Barcelona and are working on a sidechain solution to scaling.

在本节中，我们将总结巴塞罗那研讨会上有关扩展性问题中侧链解决方案的要点。

> **Parity Technologies**

> **Parity Technologies**

* **What**: The team have [created a bridge][6] contract that can connect a POA network and the main Ethereum blockchain. The current test bridge allows transfers of ERC20 tokens, but the team are working on a generalised bridge that allows for arbitrary message passing. This is a test of the technology which be used to connect chains together Polkadot, naturally the Web3 Foundation is supportive of this technology

* **说明**：团队已经[创建了一个桥式][6]合约，可以连接到 POA 网络和以太坊主链。在目前的测试中可以传输 ERC20 通证，但该团队正在开发允许任意消息传递的通用桥接器。这是 Polkadot 对链与链相互连接的技术测试，当然 Web3 基金会支持这项技术。

* **When**: ERC20 test bridge is ready. A general bridge with arbitrary message passing is expected to be 2 months away.

* **时间**：ERC20 测试桥（bridge）准备就绪。预计 2 个月后能实现传递任意消息的通用桥（bridge）。

* **Security**: This solution requires more trust than other solutions as it currently works with POA chains. If authority compromised than the bridge is compromised. The identity of the node has to be at stake: transparency to call people out.

* **安全**：该解决方案比其他方案需要更多的信任，因为它目前与 POA 链一起工作。如果权威受到损害，那么桥就会受到威胁。节点的身份就处于危险之中：赤裸裸地向人们发起了挑战。

* **Useability**: Can deploy a dapp on the test net and then use exact same dapp on the mainnet. The code is the same.

* **可用性**：可以在测试网上部署 dapp，然后在主网上使用完全相同的 dapp。代码是一样的。

* Cross-chain transaction speeds are limited by the slowest chain; while the sidechain can be faster than the Ethereum mainnet, this solution doesn't allow for the same throughput rates as state channels. Message passing in both directions should be less than 100000 gas each direction.

* 跨链交易速度受速度最慢的链的限制；虽然侧链可能比以太坊主网更快，但该解决方案不允许与状态通道相同的吞吐量。双向传递的消息必须每个方向都不于 100000 gas。

> **POA Network**

> **POA 网络**

* **What**: The team have created a Proof-of-Authority (POA) Network which is a public Ethereum sidechain that uses a POA consensus mechanism with independent validators. It relies upon the Parity Bridge.

* **说明**：团队已经创建了一个权威证明（POA）网络，该网络是一个公开的以太坊侧链，使用 POA 共识机制和独立验证器。它依赖于 Parity Bridge。

* The POA Network team are also working on an open source block explorer which is a valuable resource for the community.

* POA 网络团队也在开发一个开源区块浏览器，这对社区来说是一个宝贵的资源。

* The team have also created a deployment playbook for people to spin up a POA network quickly. This allows for a horizontal scaling using parity bridges.

* 为了快速建立 POA 网络，团队还创建了部署角本。这允许使用 parity bridges 进行水平扩展。

* **When**: Now! Deployment tools also exist.

* **时间**：现在！部署工具也已经完成。

* **Security**: The considerations are similar to those of Parity (previous solution). There is a dynamic list of validators that vote to add / remove each other. Need to compromise 51% to compromise finality.

* **安全**：与 Parity（以前的解决方案）类似。有一个动态的验证者列表，可以通过投票来添加/删除。最终妥协需要 51％ 作恶。

* **Useability**: Writing a DApp for the POA network is the same for Ethereum: they are just solidity contracts (No new SDKs). There are some new security design considerations plus there is some set up involved, but the team have created playbooks to help developers get up and running.

* **可用性**：为 POA 网络编写 DApp 与以太坊相同：它们仅是 solidity 合约（没有新的 SDK）。有一些新的安全设计及涉及到的设置，但是团队已经创建了帮助开发人员启动并运行的角本。

* Block times are about 5 seconds (which allows for 3x throughput compared to Ethereum).

* 出块时间约为 5 秒（与以太相比，可以提供 3 倍的吞吐量）。

> **Cosmos**

> **Cosmos**

* **What**: The Cosmos team are working on 3 different areas to improve scaling: (1) consensus algorithm, (2) state machine, (3) multiple interoperating chains.

* **说明**：Cosmos 团队正在三个不同领域开展工作以改善可扩展性能：（1）共识算法，（2）状态机，（3）多个互操作链。

* 1\. Tendermint — is an asynchronous POS algorithm which provides Byzantine Fault Tolerance. It is suggested to be faster than synchronous POS without suffering other security issues.

* 1\. Tendermint - 是一种提供拜占庭容错的异步 POS 算法。我们认为在不遭受其他安全问题的情况下比同步 POS 更快。

* 2\. A new state machine being developed by the team which is not Turing complete, but will allow for application-specific blockchains.

* 2\. 团队开发了的新的状态机，它不是图灵完备的，但将允许使用应用特定的区块链。

* 3\. As there is a limit for a single blockchain there is a clear need a multi blockchain solution which allows for intercommunication.

* 3\. 由于单个区块链的限制，因此显然需要允许相互通信的多区块链解决方案。

* **When**: (1) Tendermint core exists, (2) Cosmos SDK 99% done, (3) about 70% done so probably another 3–4 months away.

* **时间**：（1）Tendermint 核心已经完成，（2）Cosmos SDK 99％ 完成，（3）目前已经 70％ 左右完成，全部完成大概还需要 3-4 个月。

* **Security**: Cosmos will offer 3 different types of chains: (1) sovereign, (2) hosted, and (3) hybrid (similar to Plasma).

* **安全**：Cosmos 将提供3种不同类型的链：（1）主权链，（2）托管链和（3）混合链（类似于 Plasma）。

1. _Sovereign blockchains are fully independent and have their own validators (to find consensus), but can be bridged._

1. _主权链是完全独立的，并有自己的验证者（以寻求共识），但可以桥接._

2. _Hosted don't have their own consensus mechanism._

2. _寄托管链没有自己的共识机制。_

3. _Hybrid chains have their own validators, but absorb some security properties form the Cosmos hub (a set of 100 validators)._

3. _混杂链具有自己的验证者，但吸收了 Cosmos hub（一组 100 个验证者）的一些安全属性._

_There is finality in 1 block using tendermint; however, there can be liveness issues, if more than a third of validators go offline. In that case the network halts (fail safe)._

_tendermint 在 1 个区块后确认结果；然而，如果超过三分之一的验证者脱机，则可能存在活跃性问题。在这种情况下，网络将关闭（失效保护）._

* **Useability**: The Cosmos team believe that Tendermint scales well. The Ethereum specific version of their algorithm (Ethermint) can do 200/300 txs per second and they hope their Cosmos SDK will improve that. If Geth does 200/300, It was guess that Parity can do 500. Not 1000s per second. The Hub has 1–3 second block times. It possible to have interoperability between Cosmos and Ethereum.

* **可用性**：Cosmos 团队认为 Tendermint 具有很好的可扩展性。他们算法中的以太坊特定版本（Ethermint）每秒可以达到 200/300 txs，他们希望他们的 Cosmos SDK 能够改善这一点。如果 Geth 是 200/300，那么猜测 Parity 可以做到 500，而不是每秒 1000。中心枢纽有 1-3 秒的出块时间。 Cosmos 和以太坊之间可能具有互操作性。

> **Plasma**

> **Plasma**

* **What**: Hierarchical sidechains on Ethereum. The aim is to move a lot of smart contract computation onto sidechains rather than being performed on the main chain.

* **说明**：以太坊的分层侧链。目标是将大量智能合约计算从主链转移到侧链上执行。

* **When**: Soon. For simple apps it could be done in a few months.

* **时间**：很快。简单的应用程序可以在几个月内完成。

* **Security**: In simplest form: child chain with own consensus mechanism (POS). If that fails then fail back to root chain to settle. It's the responsibility of everyone holding value on side chain to notice if something goes wrong, and to exit. There could be congestion if everyone tried to exit at the same time, and doubly bad if there was a busy ICO happening at the same time. Ultimate finality is on the main chain.

* **安全性**：最简单的形式：子链具有自己的共识机制（POS）。如果失败了，那么就回到根链来解决问题。每个人都有责任在侧链上锁定资金，并注意是否出现问题并退出。如果所有人都试图同时退出，那么可能会出现拥堵，如果同时正进行着一个繁忙的 ICO，那么结果会非常糟糕。最终的确认是在主链上。

* **Useability**: Users will need to deposit and withdraw funds. The team expect transaction through to be an order of magnitude higher (10x) than is present with Ethereum.

* **可用性**：用户需要存入和提取资金。该团队预计交易量将比以太坊目前的交易量高出一个数量级（10 倍）。

### **General problems with sidechains**

### **侧链的一般性问题**

* In a POA network you need to explicitly trust the authorities.

* 在 POA 网络中，您需要明确信任权威。

* Tooling can be an issue, although at least one team (POA Network) is working on an open source block explorer.

* 工具可能是一个问题，但至少有一个团队（POA 网络）正在开发一个开源的区块浏览器。

* Can't offer transfers as quickly as state channels do (although allow for many-to-many transactions).

* 不能像状态通道那样快速地提供转账（尽管允许多对多的交易）。

* Dependent on the root chain for complete settlement.

* 取决于根链以完成结算。

### **Project Summaries** — Alternative solutions

### **项目总结**  - 替代解决方案

> **TrueBit**

> **TrueBit**

* **What**: Allows for computation to be offloaded to an off-chain virtual machine, but there is a smart contract on-chain. Tasks are created through the TrueBit contract, but clients pick them off and run them. There are three layers in the TrueBit solution.

* **说明**：允许计算卸载到链下虚拟机运行，但链上有一个智能合约。任务是通过 TrueBit 合约创建的，但客户选择并运行它们。TrueBit 解决方案分三层。

1. _Computational layer (bottom): WASM VM running off and on chain. There is an expectation that this will be able to work with Polkadot._

1. _计算层（底部）：WASM 虚拟机运行在链路上。期望这将能够与 Polkadot 一起工作._

2. _Dispute resolution (verification game)._

2. _争议的解决（验证竞赛）_

3. _Incentives (top): determines how much original task paid, how solver and challenger selected._

3. _激励（顶部）：决定原始任务支付的金额，如何选择解算者和挑战者_

_Bottom: Computation layer: 6 months._

_底部：计算层：6个月._

_Middle: Verification game. 6 months._

_中间件：验证竞赛。 6个月。_

_Top: Incentive layer. Never? It evolves._

_顶部：激励层。视项目演变及发展情况。_

* **Security**: Just need a single honest verifier: as long as one person checks work of solver they'll prove the incorrectness. It is possible to delay execution of task by challenging it at the cost of a deposit (submit bogus challenges, at every turn you lose your deposit). Note that dispute resolution is done via Ethereum. There could be an availability issue as data is on IFPS which must be live with the published data also being live.

* **安全性**：只需要一个诚实的验证者：只需一人检查求解器的工作就能验证错误。通过以存款损失为代价来延迟执行任务是可能的（即提交虚假挑战，但每次都将损失存款）。请注意，争议解决是通过以太坊完成的。由于 IFPS 上的数据必需与发布的数据共存，有可能存在有效性问题。

* **Useability**: Any application on ethereum can use TrueBit, ideal for those applications which can't fit into gas limit. The cost of running an application on TrueBit = TrueBit gas cost * number of the steps to run on TrueBit.

* **可用性**：以太坊上的任何应用都可以使用 TrueBit，非常适合那些不适合有 gas 限制的应用。在 TrueBit 上运行应用程序的成本 = TrueBit gas 成本 * 在 TrueBit 上运行的步骤数。

* The ether gas cost: verification game is log(n); N is the no of steps in computation.

* 以太 gas 成本：验证竞赛是 log（n）; N 是计算步骤中的序号。

* Log(n): This assumes a binary search and take the midpoint.

* Log（n）：一个二进制搜索并取中点。

* For some simple computations using Ethereum is faster, but past the crossover point it is faster to offload the computation to TrueBit.

* 对于一些简单计算还是使用以太坊速度更快，但通过交叉点后，将计算卸载到 TrueBit 运行会更快。

* State channels can be implemented in the future which would help to speed up the verification game process.

* 状态通道可以在未来实施，这将有助于加速验证竞赛过程。

* The team have a desire to all the task giver to have as easy a time as possible and to let them pay using any token. This is a problem which can be solved by decentralised exchange.

* 团队希望让所有的任务提供者尽可能简单，并可使用任意通证支付。这个问题可以使用去中心化交易来解决。

[1]: https://cdn-images-1.medium.com/max/1600/1*LS-njHhbYnQ21xt3lbW1Nw.png
[2]: https://docs.google.com/spreadsheets/d/1GAiRJGn347Nt90sOhqNBFf7bEZORqzm46LWHaeVsxUs/edit#gid=0
[3]: https://cdn-images-1.medium.com/max/1200/1*ar8jX7WxbJZBWFlxBmNM9Q.png
[4]: https://medium.com/@web3/investigating-short-term-scaling-solutions-for-ethereum-a5951fee8967
[5]: https://cdn-images-1.medium.com/max/1600/1*0Rh6mTsVn33Dt61iwrwqqg.png
[6]: https://paritytech.io/bridging-the-dapp-scaling-now-with-parity-bridge/


----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/General)

#### 本文译者简介

鱼 区块链技术爱好者，欢迎加微信号交流：**oscnet**

版权声明：

版权所有，未经同意，不得转载。

----------------------------------------------------
