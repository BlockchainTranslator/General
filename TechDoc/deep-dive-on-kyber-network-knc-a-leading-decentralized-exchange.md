> 本文翻译自：https://medium.com/@jakehallac/deep-dive-on-kyber-network-knc-a-leading-decentralized-exchange-c32e2ba3a02
>
> 作者：Jake Hallac
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator) [鱼](https://github.com/oscnet)
>
> 翻译时间：2018-2-20
>

Deep Dive on Kyber Network (KNC): A Leading Decentralized Exchange
==================================================================

This post will dive into [KyberNetwork](https://medium.com/@KyberNetwork), an exciting Singapore-based project that is working to facilitate **instantaneous exchange of cryptotokens** without reliance on a traditional centralized exchange.

**Current Project Status**: The [project’s mainnet pilot](https://blog.kyber.network/kyber-network-mainnet-pilot-is-now-live-a90366e2a0ef) is officially live on the Ethereum blockchain as of February 11th, 2018 and will run until April 2018.

*   During the pilot phase, only Kyber Network’s whitelisted ICO contributors will be granted access to the platform. They are starting with 10 tokens at the outset, with more to be added in the near future.

深入 Kyber Network（KNC）：一个领先的去中心化交易所
================================================

这篇文章将深入 [KyberNetwork](https://medium.com/@KyberNetwork)，一个令人兴奋的新加坡项目，该项目致力于在不依赖传统的中心化交易所的的情况下提供**数字货币的即时交易**。

**项目当前状态**：该[项目的主网测试](https://blog.kyber.network/kyber-network-mainnet-pilot-is-now-live-a90366e2a0ef) 2018 年 2 月 11 日开始正式在以太坊区块链上运行，并持续到 2018 年 4 月。

* 在测试阶段，只有 Kyber Network 的 ICO 白名单才能参加测试。初始发放 10 个通证（tokens，也译作代币，本文全部译为通证）用于测试，以后会增加更多的测试用通证。

### \*\*\*If you’re new to cryptocurrencies, scroll to the bottom of this page where I include educational resources, podcasts, and other useful tools to help you learn about the space.\*\*\*

### \*\*\*如果您是加密货币的新手，请滚动到此页面的底部，那里我列举了一些学习资源，播客和其他有用的工具，能帮助您了解加密货币。\*\*\*

![](https://cdn-images-1.medium.com/max/1600/1*sdYHlyYnyaEwpDLF-PiO_Q.png)

### What is Kyber Network?

Kyber Network is an ambitious project aiming to offer **decentralized token exchange capabilities** to users on the Ethereum protocol in addition to **payment APIs** that will allow merchants to process payments in any tokens

By early 2019, **Kyber Network hopes to allow cross-chain trading** and hopes to leverage the future success of interoperability-focused projects such as [Cosmos](https://cosmos.network/about) and [Polkadot](https://polkadot.io/).

### 什么是 Kyber Network？
Kyber Network 是一个雄心勃勃的项目，旨在在以太坊协议上提供**去中心化的通证交易功能**，另外还提供可让商家处理任意的通证付款功能的**支付 API**。

到 2019 年初，**Kyber Network 期望能够进行跨链交易**，并希望能够借助于未来专注于互操作性的项目如 [Cosmos](https://cosmos.network/about) 和 [Polkadot](https://polkadot.io/) 等的成功。

### How does Kyber Network Work?

Kyber Network aspires to guarantee liquidity and offer instantaneous on-chain conversions **by leveraging independently-managed reserve pools.**

*   This means that unlike centralized exchanges, **Kyber Network does not hold consumer funds in escrow nor keep a global order-book.**

### Kyber Network 如何工作？
Kyber Network 希望**通过利用独立管理的储备池**来保证流动性并提供即时链上转换。

*   这意味着，与中心化交易所不同，**Kyber Network 既不在第三方保存用户的资金，也不保存全局订单。**

**Here’s the simplified process (explained in more detail below)**

1.  Users initiate trade requests (either a market order or specifying a minimum conversion rate);
2.  Kyber Network fetches the best conversion rate offered amongst all of its externally-managed reserves; and
3.  A smart contract will then execute an atomic transaction and the user will receive their requested tokens directly to their wallet.

**简化的过程说明（下面有更详细地解释）**

1.  用户发起交易请求（采用市场订单或指定最低转换率）;
2.  Kyber Network 在其所有外部管理储备池中提供的转化率中取得最佳转化率。
3.  然后智能合约执行原子交易，用户就能在他们的钱包中直接收到交易的通证。

### What is Kyber Network Token (KNC) and Why does it have value?

#### KNC Token Type

Utility Token

#### **KNC Supply**

There are currently 134,132,697 KNC tokens in circulation.

#### KNC Allocation

19.5% of KNC tokens are held by the Kyber Network project, 19.5% are held by founders, advisors, and seed investors, and 61% is held by the general public.

### 什么是 Kyber Network 通证（KNC），它为什么有价值？

#### KNC通证类型

应用通证

#### **KNC 供应**
目前流通的有 134,132,697 个 KNC 通证。

#### KNC 分配
Kyber Network 项目持有 19.5％ 的 KNC 通证，19.5％ 由创始人，顾问和种子投资者持有，61％ 由公众持有。


#### **KNC Use Cases**

**First, Reserve managers use KNC to pay Kyber Network a small fraction of the transaction (the transaction fee)**. This is equivalent to reserve managers making payment in exchange for the right to be able to operate on KNC.

**Second, Kyber Network has stated that it will pay partners in KNC for every trade that they introduce to Kyber Network.** This includes wallets, blockchain explorers, and on-chain smart contracts.


#### KNC 用例

**首先，储备管理者用 KNC 向 Kyber Network 支付交易的一小部分（交易费用）**。这相当于储备管理者用在交易中的付款以换取在 KNC 上操作的权利。

**其次，Kyber Network 已经表示，对于合作伙伴向 Kyber Network 推出的每笔交易，它会用 KNC 支付报酬。** 包括钱包、blockchain explorers (区块链探索者)和链上智能合约。

#### **KNC Inflation/Deflation**

All tokens that are paid in transaction fees by the reserves are burned by the Kyber Network, thus permanently decreasing a portion of the token’s supply. This means that, by design, **there will be upward pressure on the price of KNC as trading volume increases.**

### KNC 通货膨胀/通货紧缩

所有由储备池支付的交易费用的通证均被 Kyber Network 销毁，从而永久性减少通证的供应量。这意味着，在设计上，随着交易量的增加，KNC 的价格将面临上涨的压力。

*   Note that because the fees are taken as a percentage of the “coins in circulation”, **the total supply of KNC will never be exhausted.**

#### In this [Reddit post](https://www.reddit.com/r/CryptoCurrency/comments/7qy8d6/kyber_network_an_introduction/) from January 2018, Kyber Network writes that:

> **“This token utility model was cocreated and advised by Vitalik (Co-founder of Ethereum), a similiar model can be found in his blog post **[**here**](http://vitalik.ca/general/2017/10/17/moe.html)**”**


*  请注意，因为这些费用是以“流通中的通证”的百分比来计算的，**所以 KNC 的总量是永远不会完全耗尽的。**

#### Kyber Network 在2018年1月的这篇[Reddit post](https://www.reddit.com/r/CryptoCurrency/comments/7qy8d6/kyber_network_an_introduction/) 文章中写道：

> **“通证的应用模型是由 Vitalik（Ethereum联合创始人）共同创建和建议的，类似的模型可以在他的 **[**博客文章中**](http://vitalik.ca/general/2017/10/17/moe.html)** 找到 ”**

### How does Kyber Network Facilitate Instantaneous Transactions?

The following diagram from the [Kyber Network whitepaper](https://home.kyber.network/assets/KyberNetworkWhitepaper.pdf) depicts how the network functions:

###  Kyber Network 怎样来做到即时交易？
以下来自 [Kyber Network 白皮书](https://home.kyber.network/assets/KyberNetworkWhitepaper.pdf)的图表描述了网络的实现：

![](https://cdn-images-1.medium.com/max/1600/1*Euu2me4gay_ysYxl_0cxMA.png)

(Source: Kyber Network [Whitepaper](https://home.kyber.network/assets/KyberNetworkWhitepaper.pdf))

**In order to further explain how the Kyber Network system functions, I’m going to go through each network participant one-by-one.**

**Here are the four entities:**

1.  **The User;**
2.  **The Reserve Contributor;**
3.  **The Reserve Manager; and**
4.  **The Kyber Network Operator**.

**为了进一步解释 Kyber Network 系统的运作，下面逐一介绍网络的所有参与者。**

**有种四个实体：**

1. **用户;**
2. **储备贡献者;**
3. **储备管理者; 和**
4. **Kyber Network 运营商**。

### First, we have the Users.

**Who are Users?** They are entities who want to execute trades. They can be individual users, smart contracts, or merchants.

**Permissible Actions**: Users can query conversion rates and execute trades (from their digital or hard wallet).

### 首先，介绍用户。
**谁是用户？** 想要执行交易的实体。它可以是个人用户、智能合约或商家。

**允许的行为**：用户可以（从他们的数字钱包或硬钱包中）查询转换率并执行交易。

Here’s what the Users get from Kyber Network:

1.  **Instantaneous (atomic)** **and Trustless Exchange**: Kyber Network does not ever hold user tokens, so there is no risk of users getting hacked. Kyber Network simply facilitates an on-chain transaction between the user’s wallet and reserves via smart contracts.
2.  **Minimal Fees**: Users only pay the gas fee to pay for the transaction on the Ethereum network (which is common on all exchanges). No additional service/transaction fees are charged.
3.  **Some Level of Customer Support**: Kyber Network uses [ZenDesk](https://www.zendesk.com), a reputable customer service company, to field inbound support tickets, and offers a [FAQ Page](https://kybernetwork.zendesk.com/hc/en-us/sections/360000119052-FAQ) on its website to memorialize common user questions.
4.  **No Sign-up Required**: Currently, no sign-up is necessary for token exchanges up to $3,000. Kyber Network does require sign up and KYC checks for exchanges over $3,000.
5.  **Minimalist User Experience:** The user interface will be similar to that of [ShapeShift](https://shapeshift.io/#/coins) as Kyber Network does not have a global order-book, but instead derives exchange rates from multiple market APIs and shows the user the best rate among all the reserve managers.

以下是用户能从 Kyber Network 得到的：

1. **即时（原子）**、**无需信任的交易**：Kyber Network 永远不会持有用户的通证，所以不存在被黑客攻击的风险。Kyber Network 通过智能合约简化了用户钱包与储备池之间的在链交易。
2. **最低的收费**：用户只需支付以太坊网络的交易费用（这在所有交易所都是常见的）。不收取额外的服务/交易费用。
3. **一定程度的客户支持**：Kyber Network 使用著名的客户服务公司[ZenDesk](https://www.zendesk.com)来提供现场帮助支持，对常见的用户问题在其网站上提供[FAQ Page 常见问题页面](https://kybernetwork.zendesk.com/hc/en-us/sections/360000119052-FAQ)。
4. **无需注册**：目前，无需注册即可获得高达 3000 美元的通证兑换。对 3000 美元以上的兑换，Kyber Network 需要注册并需进行 KYC。
5. **极简用户体验**：用户界面与 [ShapeShift](https://shapeshift.io/#/coins) 相似，因为 Kyber Network 没有全局订单簿，而是从多个市场的 API 中获得汇率，从所有储备池中取出最佳汇率给用户。

*   A quick look at the Kyber Network website is enough to see that that they are focused on offering an intuitive and user-friendly interface:

看一下 Kyber Network 网站设计就足以看出他们专注于提供直观和用户友好的界面：

![](https://cdn-images-1.medium.com/max/1600/1*2lpNPAUSNSRAFETA3K34tw.png)

Source: Kyber Network Homepage (2/13/2018)

### Second, we have the Reserve Contributors.

**Who are Reserve Contributors?** They are entities who pool their tokens into an externally-managed reserve to allow Kyber Network’s smart contracts to access it.

**Permissible Actions**: Reserve Contributors can contribute reserves and withdraw funds from the reserve.

**Reserve Contributors** earn a profit on the spread between the base rate (determined by Kyber Network) and the rate that the user pays.

*   Kyber Network will employ transparent fund management, so that contributors of the reserve can track all trading activities done by reserve managers. In addition, Kyber Network will put restrictions in place to only allow reserve managers to transfer funds to predefined addresses.

### 其次，我们有储备贡献者。
**谁是储备贡献者？** 将他们的通证汇集到外部管理的储备中以允许 Kyber Network 的智能合约访问它的实体。

**允许的行为**：储备贡献者可以提供储备并从储备中提取资金。

**储备贡献者** 通过基准利率（由Kyber Network 确定）和用户支付的利率之间的利差获利。

* Kyber Network 将采用透明的资金管理，储备提供者可以查看储备管理者完成的所有交易活动。此外，Kyber Network 将限制只允许储备管理者将资金转移到预先指定的地址。

### Third, we have the Reserve Managers.

**Permissible Actions**: Reserve Managers can only set their own conversion rate.

**Kyber Network** will need to institute restrictions on Reserve Managers to prevent bad actors from derailing the system. Kyber Network highlights the following in their whitepaper:

### 第三，我们有储备管理者。

**允许的操作**：储备管理者只能设置自己的转换率。

**Kyber Network** 对储备管理者进行必要限制，防止他们有使系统失灵的不良行为。Kyber Network 在他们的白皮书中强调了以下内容：

1.  **Required KYC Checks**: To be a reserve manager, you will have had to pass all Kyber Network’s KYC checks, and helps to commit to good service (low spreads and sufficient liquidity)
2.  **Bounded Reserve Spread**: Kyber Network may consider bounding the reserve spread on different tokens to prevent reserve managers from offering outrageous prices.
3.  **Investigate on a case**-**by-case basis**: Kyber Network offers guidance to reserve managers and should a price differ from the system rate by a certain amount, Kyber Network will investigate the issue.

*   Kyber Network will also be developing a **reserve dashboard** software to help reserve managers manage their reserve portfolio.

1. **要求 KYC**：作为储备管理者，必须通过所有 Kyber Network 的 KYC 检查，并能提供良好的服务（能提供低利差和充足的流动性）
2. **有限储备利差**： Kyber Network 可能会考虑在不同的通证上限制储备利差，以防止储备管理者提供过高的价格。
3. **逐个调查**：Kyber Network 会对储备管理者提供指导，如果价格与系统费率有一定的差异，Kyber Network 将对该问题进行调查。

* Kyber Network 还将开发储备仪表板软件，帮助储备管理者管理他们的储备资产组合。

### Fourth, we have the KyberNetwork Operators.

**Permissible Actions**: KyberNetwork Operators can list/delist new exchange pairs and add/remove reserves.

*   At first, the Kyber team will act as the **KyberNetwork Operator** to bootstrap the platform in the early phases. Kyber Network intends to set up a proper decentralized governance to take over this task in the future.

### 第四，我们有 KyberNetwork 运营商。

**允许的行为**：KyberNetwork 运营商可以列出/删除新​​的交换对并添加/删除储备。

* 首先，在早期阶段 Kyber 团队将作为 KyberNetwork 运营商来引导启动平台。Kyber Network 打算在未来建立一个适当的去中心化治理方案，然后由它们来接管这项任务。

### Team

[Loi Luu](https://medium.com/@loiluu) (CEO) is a CS PhD researcher at the National University of Singapore. In addition to having strong technical capabilities, he is also clearly passionate about Kyber Network’s mission, and is great at promoting Kyber Network without being promotional (which is a great quality in any CEO).

*   I would highly recommend listening to [**Luu’s interview on the Crypto 101 Podcast**](https://soundcloud.com/crypto101podcast/kyber-network-w-ceo-loi-luu-the-framework-for-payments)  from 2/10/2018.
*   [**Here**](https://www.forbes.com/sites/luuloi/2018/01/26/blockchain-adoption-how-close-are-we-really/#2ced866ad9dc) is a concise and thoughtful Forbes opinion piece that Luu wrote about Blockchain Adoption.
*   Luu was also recently selected to the 30 Under 30 List for ForbesVietnam

### 团队
[Loi Luu](https://medium.com/@loiluu) （CEO）是新加坡国立大学的 CS 博士研究员。除了拥有强大的技术能力之外，显然他还对 Kyber Network 的使命充满热情，并且还非常擅长在没有宣传的情况下推广 Kyber Network（这是任何首席执行官的优秀品质）。

* 我强烈建议您听取在 [**Crypto 101 Podcast 上对 Luu 的采访**](https://soundcloud.com/crypto101podcast/kyber-network-w-ceo-loi-luu-the-framework-for-payments)  

* [**这**](https://www.forbes.com/sites/luuloi/2018/01/26/blockchain-adoption-how-close-are-we-really/#2ced866ad9dc)
是 Luu 写的一篇介绍区块链应用的简明扼要的福布斯评论文章。

* Luu 最近还入选了福布斯越南的30个30岁以下名单

![](https://cdn-images-1.medium.com/max/1600/1*71orWe0FKCkSq_RotMiqFA.png)

(Source: Kyber Network Twitter, 1/29/2018)

**Yaron Velnver** (CTO) is a CS PhD. His research focused on aspects of game theory incentives in blockchain protocols and formal verification of smart contracts.

**Victor Tran** (Lead Engineer) has experience developing and building infrastructure for social marketing platforms and ad networks.

**Yaron Velnver**（CTO）是 CS 博士。他的研究集中在区块链协议中的博弈论激励方面以及智能合约的形式验证。

**Victor Tran**（首席工程师）具有为社交营销平台和广告网络开发和构建基础设施的经验。

### Advisors

Vitalik Buterin (Founder of Ethereum) is the most notable advisor to the project.

*   **Vitalik was involved with the design of the platform and token utility design**, but Kyber Network notes that they do not engage with him as frequently as they did in the past (December 2017 Reddit AMA)

### 顾问

Vitalik Buterin（以太坊创始人）是该项目最著名的顾问。

* **Vitalik 参与了平台和通证应用的设计**，但 Kyber Network 指出，现在他们间的交往没有像过去那样频繁（在 2017 年 12 月 Reddit AMA 上）

### Investors

Kyber Network has a list of top-notch investors behind it in the blockchain space including [Pantera Capital](https://www.panteracapital.com), Danhua Capital, Hyperchain, Fenbushi, Signum, and FBG

### 投资者
Kyber Network 拥有一批在区块链领域的顶级投资者，包括[Pantera Capital](https://www.panteracapital.com), Danhua Capital, Hyperchain, Fenbushi, Signum, 和 FBG

### Partnerships

#### [**ICON (ICX)**](https://blog.kyber.network/new-strategic-partnership-announcement-kyber-network-icon-78bd0f572820)

*   **ICON is one the largest blockchain networks in the world aiming to build a decentralized network that allows independent blockchains with different governances to transact with one another without intermediaries.**
*   **Partnership Details**: Kyber Network will connect its token conversion services to ICON’s inter-blockchain network and is intended to bring Kyber Network one step closer to supporting cross-chain transactions, thereby delivering utility for different decentralized applications across chains.

> “The token exchange system is a key component of the inter-blockchain ecosystem…Our partnership with Kyber Network brings us one step closer to inter-chain token exchange.” — J.H. Kim (ICON Foundation Council Member)

### 合作伙伴
[**ICON (ICX)**](https://blog.kyber.network/new-strategic-partnership-announcement-kyber-network-icon-78bd0f572820)

* **ICON 是世界上最大的区块链网络之一，旨在建立一个去中心化的网络，允许具有不同治理的各种独立的区块链在没有中介的情况下彼此进行交易。**
* **合作伙伴详情**：Kyber Network 将其通证转换服务连接到 ICON 的内部区块链网络，旨在使 Kyber Network 进一步支持跨链交易，从而为不同的跨链去中心化应用提供实用性。

> “通证交易系统是区块链间生态系统的关键组成部分......我们与 Kyber Network 的合作关系使我们向链间通证交易迈进了一步。” - JH Kim（ICON基金会理事会成员）

#### [**Ripio Credit Network (RCN)**](https://blog.kyber.network/rcn-partners-with-kyber-network-to-extend-worldwide-credit-d656dcdaf2a5)

*   **Ripio Credit Network** is a global credit network protocol based on cosigned smart contracts. It has 170K users, and is trying to expand from Latin America to the global P2P lending market. RCN smart contracts connect agents with information on the borrower’s identity to agents that analyze the borrower’s credit risk impartially and a cosigner acts as a re-insurer that distributes and reduces the lender’s risk, and at the same time, helps to improve the contract conditions by retaining access to the borrower’s local legal system
*   **Partnership Details**: Kyber Network will provide the conversion services (as an on-ramp and off-ramp partners) necessary for credit exchanges and wallet providers to integrate the RCN protocol. Once RCN network is fully deployed in Q2 2018, both parties will pilot test.

#### [**Ripio Credit Network (RCN)**](https://blog.kyber.network/rcn-partners-with-kyber-network-to-extend-worldwide-credit-d656dcdaf2a5)

* **Ripio Credit Network** 是基于共同签署的智能合约的全球信用网络协议。它拥有 17 万用户，并正试图从拉丁美洲扩展到全球 P2P 借贷市场。RCN 通过智能合约将借款人、代理人、委托人连接起来，将借款人身份相关的信息连接到代理人，代理人公平地分析借款人的信用风险，委托人充当分配和降低贷方风险的再保险人，并同时通过保留对借款人当地法律的使用权来帮助改善合同条件
* **合作伙伴详情**：Kyber Network 将提供信用交换和钱包提供商整合 RCN 协议所需的转换服务（作为入站和出站合作伙伴）。一旦 RCN 网络在2018年第二季度全面部署，双方将进行 pilot 测试（pilot 测试：在实时操作条件下验证系统组件或整个系统，在投入生产之前验证系统的主要功能，译注）。

#### [**Wanchain (WAN)**](https://blog.kyber.network/kyber-network-wanchain-partnership-announcement-ef574b181610)

*   **Wanchain** is a universal cross-chain protocol with private cross-chain smart contracts and token exchange privacy protection.
*   **Partnership Details**: Kyber Network intends to collaborate with Wanchain, which raised $36mm in its October 2017 ICO, in three major areas:

1.  Both parties will share marketing, PR, community and partnership building contacts when relevant.
2.  Kyber Network will also work to build out a decentralized exchange on the Wanchain platform.
3.  Both parties will collaborate on PeaceRelay Project, which is aimed at allowing communication and interaction between Ethereum-forked blockchains

### [**万维链 (WAN)**](https://blog.kyber.network/kyber-network-wanchain-partnership-announcement-ef574b181610)

* **万维链**是一种通用的跨链协议，具有私有交叉链智能合约和通证交易隐私保护功能。
* **合作伙伴详情**：Kyber Network 有意与万维链合作，万维链在其 2017 年 10 月的 ICO 中募集了 3600 万美元，三个主要合作领域：

1. 当有相关时，双方将共享营销、公关、社区和合作伙伴关系建立等方面。
2. Kyber Network 将努力在万维链平台上建立一个去中心化的交易所。
3. 双方将在 PeaceRelay 项目上进行合作，此项目旨在允许以太坊分叉链之间的沟通和互动

#### [**CoinManager**](https://blog.kyber.network/announcement-kyber-network-partners-with-coinmanager-f345014a8e12)

*   **CoinManager** is South Korea’s largest portfolio tracker and wallet provider, with 350K active users.
*   **Partnership Details**: Kyber Network will integrate its service into CoinManager’s wallet, such that CoinManager users have access to seamless and instantaneous in-app token conversion.

#### [**CoinManager**](https://blog.kyber.network/announcement-kyber-network-partners-with-coinmanager-f345014a8e12)

* **CoinManager** 是韩国最大的投资组合跟踪应用和钱包提供商，拥有35万活跃用户。
* **合作伙伴详情**：Kyber Network 将其服务整合到 CoinManager 的钱包中，以便 CoinManager 用户可以进行无缝且即时的应用内通证交易。

#### [**Coinduck**](https://blog.kyber.network/kyber-network-enters-partnership-with-coinduck-to-popularize-cryptopayments-in-korea-a992134494da)

*   **Coinduck** is the world’s first Ethereum payment service that brings easy Ether transactions into everyday purchases in Korea.
*   **Partnership Details**: Kyber Network will integrate its token conversion protocol such that Coinduck will be able to expand its payment service beyond just Ether to all ERC-20 tokens.

#### [**Coinduck**](https://blog.kyber.network/kyber-network-enters-partnership-with-coinduck-to-popularize-cryptopayments-in-korea-a992134494da)

* **Coinduck** 是全球首个以太坊支付服务，使韩国的日常购物可以轻松使用以太坊交易。
* **合作伙伴详情**：Kyber Network 将整合其通证交易协议，以便 Coinduck 能够将其支付服务扩展支持到以太坊以外的所有 ERC-20 通证。

#### [**Change**](https://blog.kyber.network/kyber-network-is-ready-for-change-new-collaboration-announcement-85f9b7bf8b62)

*   **Change** is a mobile app that aims to become a one-stop decentralized platform for payments, storage, investments, P2P loans, and fund transfers in Singapore.
*   **Partnership Details**: Kyber Network will integrate its protocol with the Change Wallet to allow more users to exchange ERC-20 tokens with very little fuss. Change customers will be able to use Kyber Network’s on-chain conversion services to send and receive different cryptocurrencies without ever leaving the wallet or using any other interface.

#### [**Change**](https://blog.kyber.network/kyber-network-is-ready-for-change-new-collaboration-announcement-85f9b7bf8b62)

* **Change** 是一个移动应用程序，旨在成为新加坡集支付、存储、投资、P2P贷款和资金转移的一站式去中心化平台。
* **合作伙伴详情**：Kyber Network 将其协议与 Change 钱包整合在一起，让更多用户可以轻松交易 ERC-20 通证。Change 用户将无需离开钱包或使用任何其他界面，就能够使用 Kyber Network 的链上转换服务发送和接收不同的加密货币。

#### [**imToken**](https://blog.kyber.network/kyber-network-partners-with-imtoken-5d883a0831bf)

*   **imToken** is China’s leading mobile wallet app with 350K users worldwide. It supports multi-tokens, third-party DApps, HD-Wallet, address book, transaction push notifications, and access to exchanges.
*   **Partnership Details**: Kyber Network will integrate their protocol with the imToken wallet, essentially allowing users to make instant token conversions without ever having to leave the comfort and familiarity of their wallet. This integration guarantees liquidity for imToken users and allows them to seamlessly manage a variety of digital assets.

#### [**imToken**](https://blog.kyber.network/kyber-network-partners-with-imtoken-5d883a0831bf)

* **imToken** 是中国领先的移动钱包应用程序，全球用户达到35万。它具有支持多种通证、第三方 DApps、HD-Wallet、地址簿、交易推送通知以及查询交易所信息等功能。
* **合作伙伴详情**：Kyber Network 将他们的协议与 imToken 钱包整合在一起，从而允许用户实现即时通证交易，而无需离开他们舒适和熟悉的钱包界面。这种整合保证了 imToken 用户的流动性，并使他们能够无缝地管理各种数字资产。


#### **Huobi**

*   **Huobi** is a centralized exchange with about $900mm in daily trading volume.
*   **Partnership Details**: Kyber Network has commenced an integration with Huobi, so that they can use the exchange for price feeds as well as to rebalance their portfolio.

#### **火币**

* **火币** 是一个中心化交易所，每日交易量约 900 万美元。
* **合作伙伴详情**：Kyber Network 已开始与火币进行整合，以便他们可以使用交易所进行价格投放，并重新平衡其投资组合。

### Technical Roadmap

**February 11th, 2018**: Mainnet launches and supports trading between ETH and 10 other tokens during pilot phase until April 2018

*   First version of Kyber Network; partnering with Jaxx, MyEtherWallet, and Status

### 技术路线图

**2018年2月11日**：上主网，从试点阶段开始一直到 2018 年 4 月支持 ETH 与其他 10 个通证之间的交易

* Kyber Network 的第一个版本; 与 Jaxx、MyEtherWallet 和 Status 合作


**Q2 2018**: Supports trading between arbitrary token pairs

*   Kyber Network will work with other partners to build APIs to allow users in their platforms to efficiently withdraw in preferred tokens.

**2018年第二季度**：支持任意通证对之间的交易

* Kyber Network 将与其他合作伙伴一起构建 API，以允许其平台上的用户能有效地使用设置的优先通证进行提现。

**Q3 2018**: Supports the trading of more advanced financial instruments

*   Plans to work with decentralized HF platforms that allow people to invest in trustless HFs

**Early 2019**: Supports cross-chain trading

*   Either using chain relays or interchain communication protocols

**2018年第三季度**：支持更先进的金融工具交易

* 计划与去中心化的 HF 平台合作，允许人们在无需信任的 HF 平台上进行投资

**2019年初**：支持交叉链交易

* 使用链中继或链间通信协议

### Community

**Kyber Network is highly transparent about company developments** within its community and with the general public. Both Loi Luu (CEO) and Lewis Abela (Marketing & Communications) post regularly on social media. While based out of Singapore, the project is global and has Telegram Groups and Medium Pages available for English, Korean, and Chinese speakers.

### 社区

**Kyber Network 面对社区和普通公众，对公司发展情况保持高度透明**。Loi Luu（首席执行官）和 Lewis Abela（市场与传播）都定期在社交媒体上发布消息。该项目位于新加坡之外，是全球性的，并为英语，韩语和中文用户提供电报组和 Medium 页面。

**Kyber Network has 63K followers on Twitter, 7K members in their Telegram Group (16K on the Announcement Channel), and 3K users typically online in their Subreddit page.** In addition, their GitHub is active with 2,934 total commits for repositories updated within the last 3 days (1,738 of these are focused on Kyber Network’s wallet).

**Additionally, Kyber Network also has regular developer meetups.** For example, on January 20th, they hosted 200 people in Seoul and awarded two teams $30K each to further develop projects built on Kyber Network.

**Kyber Network 在 Twitter 上拥有 6万多的关注者，电报组有七千个成员（公告频道上有1万6），通常在 Subreddit 页面上有 3 千用户在线。** 此外，他们的 GitHub 在最近 3 天内进行了 2,934 次代码更新（其中 1,738 次更新主要有关 Kyber Network 的钱包）。

**此外，Kyber Network 还定期举行开发者聚会**。例如，1 月 20 日，他们在首尔进行了 200 多人的聚会，并分别向两个团队授予了 3 万美元，用于进一步开发基于 Kyber Network 的项目。

**Google Trends** also seems to indicate increased public interest in Kyber Network as evidenced by the increase in searches not seen since Kyber Network had its ICO:

**谷歌趋势** ICO 以来搜索量的增加也表明了公众对 Kyber Network 兴趣的增加：

![](https://cdn-images-1.medium.com/max/1600/1*Tf0uq-HLa2gyVLDms8M-NQ.png)

Source: Google Trends (“Kyber Network”)

### Pre-Mortem (Risks)

The following are potential (hypothetical) reasons why Kyber Network might fall short in its mission to become a successful decentralized exchange:

### 潜在的失败风险

Kyber Network 也有可能失败，不能完成其成为去中心化交易所的任务，以下是一些潜在的（假想的）因素：

1.  **Kyber Network is unable to achieve mainstream user adoption** due to poor UI/UX, inability to exchange fiat currency, slow order processing, and/or slow cancellation.
2.  **Kyber Network falls short with respect to its technical roadmap** due to development mistakes or shortcomings of other technology projects that Kyber Network relies.
3.  **Kyber Network is unable to onboard reserve managers/reserve contributors** and Kyber Network remains the sole reserve pool.
4.  **Other decentralized exchanges outcompete Kyber Network** and achieve mainstream adoption and/or more decentralization faster than Kyber Network. Developer talent and users consolidate around the most successful ones.
5.  **Kyber Network (and other decentralized exchanges) encounter surprising pushback from regulators.** Regulators argue that decentralized exchanges facilitate AML/KYC violations and don’t want cryptocurrency trading to be decentralized.


1. 由于 UI/UX 设计不好、无法兑换法定货币、订单处理缓慢、取消订单缓慢等原因，**Kyber Network 有可能不被主流用户采用**。
2. 由于 Kyber Network 所依赖的其他技术项目的发展不利或存在的缺点，**Kyber Network 达不到其技术路线图指示的目标**。
3. **Kyber Network 没有其它的预备队管理者/储备提供者**， Kyber Network 依然是唯一的储备。
4. **其他去中心化交易所胜过 Kyber Network**，比 Kyber Network 更快实现主流采用和/或更加去中心化。使得开发人才和用户集合在最成功的交易所周围。
5. **Kyber Network（和其他去中心化交易所）遭遇监管机构出人意料的回绝**。监管机构认为，去中心化的交易促进了 AML/KYC 的违规，并且不希望加密货币交易去中心化。

In my opinion,

Risk #1 **is mitigated because Kyber Network is investing time and energy into its wallet and its merchant API.** Both of these areas of development are crucial because they widen Kyber Network’s market opportunity to beyond today’s exchanges (which are mostly for speculative buying/selling). In addition, we have seen the success of ShapeShift, which has a similar user interface. Finally, Kyber Network doesn’t have to compete with Coinbase and provide the absolute best user experience. **If Kyber Network can provide competitive liquidity and fees, it can win a substantial amount of market volume by winning over intermediate and advanced users.**

我的观点是，

**由于 Kyber Network 将时间和精力投入到其钱包及其商家 API 中，降低了风险#1**。这两个发展领域都是至关重要的，因为它们扩大了 Kyber Network 的市场机会，超越今天的交易所（其主要是投机性买入/卖出）。另外，我们看到了 ShapeShift 的成功，它具有类似的用户界面。最后，Kyber Network 不必与 Coinbase 竞争，并提供绝对最佳的用户体验。**如果 Kyber Network 可以提供具有竞争力的流动性和费用，它可以赢得中高级用户的青睐，从而得到大量的市场份额。**

Risk #2 is mitigated because Kyber Network (i) has an active developer community as evidenced by its frequent meetups and active GitHub, (ii) has a leadership team with strong technical capabilities, and (iii) has a track record of meeting its milestones in the past. Nevertheless, **Kyber Network is ambitious with respect to its development for cross-token and cross-chain interoperability trading, and is vocal about its reliance on the success of other projects such as Melonport, Polkadot, and Cosmos.**

对于 #2 风险，由于 Kyber Network（i）它的频繁聚会和活跃的 GitHub，证明其拥有一个活跃的开发者社区，（ii）拥有一支技术能力强的领导团队，（iii）并且过去拥有实现其里程碑能力的历史记录，这些都降低了风险 #2。尽管如此，**Kyber Network 在跨通证和跨链互操作性交易方面雄心勃勃，并且对其依赖其他项目的成功，如 Melonport、Polkadot 和 Cosmos 直言不讳。**

Risk #3 is mitigated because Kyber Network has $50mm+ to bootstrap the project and provide liquidity for users. Kyber Network can mitigate this risk by winning over whales and centralized exchanges who have unused reserve capacity, while simultaneously establishing partnerships with wallet providers and other payment services. **However, Kyber Network faces the same problem that plagues traditional platform companies, and that is, you need one side of the network to provide value to the other.**

因为 Kyber Network 有五千多万美元来启动项目并为用户提供流动性，这降低了风险#3。Kyber Network 可以通过赢得未使用储备容量的鲸鱼和中心化交易所，同时与钱包提供商和其他支付服务建立伙伴关系，来降低这一风险。**然而，Kyber Network 面临着困扰传统平台公司的相同问题，也就是说，需要网络的一方为另一方提供价值**。

Risk #4 **This risk is mitigated because there can be multiple winners in this space**. According to Nathan Sexer at ConsenSys, there are 170+ cryptocurrency exchanges and 99% of those are centralized exchanges. There is no reason why there cannot be multiple successful decentralized exchanges with different system design and different customer segments. **However Kyber Network does face competition from ShapeShift, which is an existing non-custodial exchange that does not take counterparty risk**.

Risk #5 is mitigated because Kyber Network’s unique system design allows it to leverage liquidity of other exchanges and token holders, while at the same time **preventing security breaches and unsafe store of information, funds and private keys.**

对于风险 #4， **在这个领域可能有多个赢家。** ConsenSys 的 Nathan Sexer 表示，有 170 多个加密货币交易所，其中99％是中心化交易所。没有理由不能有多个针对不同的系统设计和不同的客户群体的去中心化交易所。**然而，Kyber Network 确实面临着来自 ShapeShift 的竞争，ShapeShift 是个现存的不存在交易对手风险的非保管型交易所。**

由于 Kyber Network 独特的系统设计使其能够利用其他交易所和通证持有者的流动性，同时 **防止安全漏洞和不安全的信息存储、资金和私钥存储。**，因此降低了风险 #5，

### One Potential Tailwind

One potential tailwind for Kyber Network is the **increasing frequency and magnitude of hacks on centralized exchanges.** If this trend continues, Kyber Network could see increasing developer interest and user adoption.

**Major Hacks of Centralized Exchanges**

### 潜在的推动力

Kyber Network 的一个潜在的推动力是 **中心化交易所被黑的频率及危害程度越来越大。** 如果这种趋势继续下去，Kyber Network 就能被越来越多的开发者和用户使用。

**中心化交易所的主要黑客攻击记录**

*   **March 2014**: ~$473mm stolen from Mt. Gox (Japan)
*   **January 2015**: ~$5mm stolen from Bitstamp (Luxembourg)
*   **August 2016**: ~$66mm stolen from Bitfinex (TBD)
*   **February 2018**: ~$170mm of NANO stolen from BitGrail (Italian)
*   **January 2018**: ~$400mm of NEM stolen from Coincheck (Japanese)

* **2014年3月**：从 Mt. Gox（日本）偷走约47亿3百万美元
* **2015年1月**：从Bitstamp（卢森堡）盗走大约5万美元
* **2016年8月**：Bitfinex（TBD）被盗6千6百万美元
* **2018年2月**：BitGrail（意大利）盗约1亿7千万美元的 NANO
* **2018年1月**：Coincheck（日本）盗约4亿美元的 NEM

In addition, continued hacks (and media coverage of such hacks) of other entities (i.e., wallets, ICOs, etc.) may indirectly prove to be a tailwind for Kyber Network given its focus on instantaneous and secure token exchange.

此外，针对其他实体（如钱包，ICO等）的持续攻击（以及媒体对此类攻击的报导）可能间接推动 Kyber Network，因为它专注于即时和安全的通证交易。

**Other Major Hacks (ex-centralized exchanges)**

*   **June 2016**: ~$50mm stolen from DAO
*   **July 2017**: ~$7mm stolen from CoinDash (CDT)
*   **July 2017**: ~$32mm stolen from Parity Multisig Wallet
*   **July 2017**: ~$8mm stolen from Veritaseum wallet
*   **August 2017**: ~$500K stolen from Enigma (ENG)
*   **November 2017**: ~$31mm stolen from Tether

**其他主要攻击（非中心交易所）**

* **2016年6月**：从 DAO 偷走约 5 千万美元
* **2017年7月**：从 CoinDash（CDT）盗走约 7 百万美元
* **2017年7月**：从 Parity Multisig 钱包中盗走约 3 千 2 百万美元
* **2017年7月**：从 Veritaseum 钱包中盗走约 8 百万美元
* **2017年8月**：从 Enigma（ENG）盗走约 50 万美元
* **2017年11月**：从 Tether 盗走约3千1百万美元

### Fundraising and Trading Information

#### KNC Token Sale

In September 2017, Kyber Network [held its token sale](https://www.financemagnates.com/cryptocurrency/news/kyber-network-ico-raises-60-million-little-day/) and raised 200,000 ETH, worth about $60mm at the time.

### 筹款和交易信息

### KNC 通证销售

2017 年 9 月，Kyber Network 公司进行了[通证销售活动](https://www.financemagnates.com/cryptocurrency/news/kyber-network-ico-raises-60-million-little-day/)，并在当时筹集了200,000 ETH，价值约6千万美元。

#### KNC Price Information

According to CoinMarketCap, **Kyber Network currently has a market capitalization of $357mm.**

It’s current price is $2.53, which is **57% off from its all-time high** of $5.90 on January 9th, 2018.

#### KNC 价格信息

根据 CoinMarketCap，**Kyber Network 目前的市值为3亿5千7百万美元。**

目前的价格为 2.53 美元，与2018年1月9日的历史最高价 5.90 美元相比 **下降了 57％**。

#### Active Exchanges

KNC is available for trading on the following exchanges: Binance, Huobi, Coinnest, and OKEx. Its 24hr trading volume is ~$10mm.

### 交易所

KNC 可在以下交易所进行交易：Binance、Huobi、Coinnest 和 OKEx。其 24 小时交易量约为 1 千万美元。

### **Links to Official Kyber Network Channels**

*   [_Website_](https://kyber.network/)
*   [_Reddit_](https://www.reddit.com/r/kybernetwork/)
*   [_Telegram_](https://t.me/kybernetwork)
*   [_Twitter_](https://twitter.com/KyberNetwork?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor)
*   [_Medium_](https://blog.kyber.network)
*   [_GitHub_](https://github.com/KyberNetwork)
*   [_YouTube_](https://www.youtube.com/channel/UCQ-8mEqsKM3x9dTT6rrqgJw)

### 官方 Kyber Network 频道链接

*   [_网站_](https://kyber.network/)
*   [_Reddit_](https://www.reddit.com/r/kybernetwork/)
*   [_电报群_](https://t.me/kybernetwork)
*   [_Twitter_](https://twitter.com/KyberNetwork?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor)
*   [_Medium_](https://blog.kyber.network)
*   [_GitHub_](https://github.com/KyberNetwork)
*   [_YouTube_](https://www.youtube.com/channel/UCQ-8mEqsKM3x9dTT6rrqgJw)

### Additional Readings on Decentralized Exchanges
### 关于去中心交易的补充阅读资料

[Nathan Sexer](https://medium.com/@nathan.sexer) (CCO [VariabL](https://medium.com/@VariabL) and resident at [ConsenSys](https://medium.com/@ConsenSys)) recently wrote the [**State of Decentralized Exchanges, 2018**](https://media.consensys.net/state-of-decentralized-exchanges-2018-276dad340c79). It’s a great overview of the space. He does a great job of highlighting all of the related projects out there and their innovative business models.

[Michael Oved](https://medium.com/@ovedm606) (Co-founder of AirSwap and resident at ConsenSys) also adds useful perspective by discussing how the [AirSwap Team](https://medium.com/@airswap) is using the Swap protocol (which went live February 1st, 2018) to create a decentralized exchange platform in his post titled [**The Market Maker’s Guide to Decentralized Exchange**](https://blog.airswap.io/airswap-and-novogratz-partner-to-provide-liquidity-on-decentralized-exchanges-d16518b440dd)**.**

[Noam Levenson](https://medium.com/@noamlevenson) (CEO and Co-founder of Edenblock) does an excellent job of comparing and contrasting Kyber Network with the 0x Protocol in [**this Medium Post**](https://medium.com/@noamlevenson/kyber-network-v-0x-decentralized-exchanges-ed116a8faec4)

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
