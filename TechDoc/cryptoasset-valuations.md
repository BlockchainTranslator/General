On Value, Velocity and Monetary Theory -- A New Approach to Cryptoasset Valuations
论价值，流通速度和货币理论 -- 加密资产估值的新思路
------------------------------------------------------

> 本文翻译自：https://medium.com/blockchannel/on-value-velocity-and-monetary-theory-a-new-approach-to-cryptoasset-valuations-32c9b22e3b6f
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [shuke0327](https://github.com/shuke0327)
> 感谢币乎创始人咕噜荐文
> 翻译时间：2018-01-27

原文: https://medium.com/blockchannel/on-value-velocity-and-monetary-theory-a-new-approach-to-cryptoasset-valuations-32c9b22e3b6f
作者:  [Alex Evans](https://medium.com/@ahe4nc?source=post_header_lockup)

![1](http://upload-images.jianshu.io/upload_images/1084915-794466ad4d2d1570.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Valuation methodologies have historically lagged behind the development of the assets they represent. While the Dutch East India Company became the first entity to sell stocks on a public exchange in the early 1600s, it was not until the 1930s that a comprehensive framework for deriving the fundamental value of equity securities was developed. What Graham and Dodd benefited from in 1934 that their predecessors perhaps lacked was a broadly-accepted philosophy of disclosure (eventually codified in the Securities Act of 1933) and, more importantly, a reliable accounting system with unified measurement standards and practices— a common language for discussing value. Without rules of disclosure and requisite accounting conventions, current attempts at studying cryptoasset fundamentals will descend into the [Confusion of Confusions](https://en.wikipedia.org/wiki/Joseph_de_la_Vega) that described seventeenth century stock market investment advice.

估值方法在历史上一直落后于它们所代表的资产的发展。虽然在17世纪初，荷兰东印度公司就成为了第一个在公共交易所出售股票的实体，但直到20世纪30年代，才形成了一个全面的框架来判断股票证券的基本价值。让格雷厄姆和多德在1934年能够得到益处的信息披露理念(最终在1933年的《证券法案》中被编纂成册)，他们的前辈可没能拥有。更重要的是，他们也受益于一个具有统一衡量标准和实践的可靠会计体系——一种讨论价值的共同语言。没有信息披露规则和必要的会计惯例,　当前对于加密货币资产基本面的研究尝试，将陷入[乱中之乱](https://en.wikipedia.org/wiki/Joseph_de_la_Vega)所描述的17世纪股票市场投资的情况。

In this piece, I propose an extension to the prevailing methodology for valuing cryptoassets — one that I hope will alleviate confusion by clarifying the vocabulary used in discussions of value. In the first part of the post, I survey current debates on cryptoasset fundamentals and investigate their core monetary assumptions. I find current valuation models to insufficiently capture the complexities of these conversations, motivating a new approach, which I outline in the second part of this post. The proposed method intends to disjoin demand for commodities and demand for money by placing each asset in a broader economy of return expectations and friction constraints. It is important to note, before continuing, that valuation theorists generally [caution against](http://aswathdamodaran.blogspot.com/2017/10/the-bitcoin-boom-asset-currency.html) valuation of non-cash-flow-generating assets. As such, the methodologies outlined below remain largely exploratory and imprecise. Nonetheless, I believe these discussions to be valuable in developing directional insights on cryptoasset value, which can be a key lever for projects in optimizing their incentive structures (I write in more detail about this process of ‘mechanism design’ [here](https://medium.com/blockchannel/a-crash-course-in-mechanism-design-for-cryptoeconomic-applications-a9f06ab6a976)).

在这篇文章中，我提出了一种对评估加密资产的流行方法的扩展——我希望通过澄清关于价值讨论中所使用的术语来减少困惑。在文章的第一部分，我调查了当前关于加密资产的争论，并研究了他们核心的货币理论假设。我发现目前的估值模型不足以充分反映这些对话的复杂性，这启发了一种新的思路，我在本文的第二部分中进行了概述。该思路旨在将对大宗商品的需求和对货币的需求区分开，将每一项资产置于更广泛的回报预期和摩擦约束条件下。

在我们继续之前, 值得注意的是, 估值理论家通常会对不产生现金流的资产的估值提出[警告](http://aswathdamodaran.blogspot.com/2017/10/the-bitcoin-boom-asset-currency.html)。因此，下面概述的方法在很大程度上仍然是探索性的和不精确的。尽管如此,我相信这些讨论对于发展出对加密资产价值的洞见是有价值的，它可以成为项目的一个重要杠杆，用以优化他们的激励结构(对于"机制设计"的过程，我在[这篇文章](https://medium.com/blockchannel/a-crash-course-in-mechanism-design-for-cryptoeconomic-applications-a9f06ab6a976)中提到了更多的细节)。

## **A Review of Prevailing Cryptoasset Valuation Frameworks**
**对现行的加密资产估值框架的评估**

The prevailing approach to cryptoasset valuations is undoubtedly that most clearly articulated by Chris Burniske, which can be found in his [book](https://www.amazon.com/Cryptoassets-Innovative-Investors-Bitcoin-Beyond/dp/1260026671), as well as this [bandwidth token model](https://medium.com/@cburniske/cryptoasset-valuations-ac83479ffca7) (for brevity, I refer to this as the “INET model” from here on out). [Brett Winton](https://twitter.com/wintonark?lang=en)’s [social media token model](https://medium.com/@wintonARK/how-to-value-a-crypto-asset-a-model-e0548e9b6e4e) is largely similar in its approach. The type of asset being modeled in the above takes on different names depending on who you ask — appcoin, medium-of-exchange token, cryptocommodity, proprietary-payment token, utility token. Though each of these terms captures some subtlety, you may consider them interchangeable for our purposes below. The overarching idea is that such an asset serves as the exclusive form of payment that the network will accept in exchange for an underlying scarce resource that it provides (bandwidth, storage, computation, and so forth). 

加密货币资产估值的流行方法， 无疑是Chris Burniske的阐述最为清晰，这可以在他的[书中读到](https://www.amazon.com/Cryptoassets-Innovative-Investors-Bitcoin-Beyond/dp/1260026671), 也可以看下这种代币[带宽模型](https://medium.com/@cburniske / cryptoasset-valuations-ac83479ffca7)(为简便起见,我从现在开始称之为“INET模式”)。[Brett Winton](https://twitter.com/wintonark?lang=en)的[社交媒体代币模型](https://medium.com/@wintonARK / how-to-value-a-crypto-asset-a-model-e0548e9b6e4e)在很大程度上属于相似的方法。上述方法中所建模的资产类型，根据你的需要会有不同的名字，比如 appcoin, 交易媒介代币(medium-of-exchange token), 加密商品(cryptocommodity), 所有权支付代币( medium-of-exchange token),实用代币( utility token)。虽然这些术语都有一些微妙之处，但为了我们下文的目的，你可以认为它们是可互换的。最重要的观念是，这样的资产作为网络所接受的唯一的支付形式，以换取所提供的潜在的稀缺资源(带宽、存储、计算等等)。

The core thesis of current valuation frameworks is that utility value can be derived by (a) forecasting demand for the underlying resource that a network provisions (the network’s ‘GDP’) and (b) dividing this figure by the monetary base available for its fulfillment to obtain per-unit utility value. Present values can be derived from future expected utility values using conventional discounting. The theoretical framework that nearly all these valuation models employ is the [equation of exchange](https://en.wikipedia.org/wiki/Equation_of_exchange), MV=PQ. While you will see this formula appear in nearly all discussions of cryptoasset value, it is often given little explanation and even less theoretical treatment. I attempt to offer some clarity on this in below, but for now let’s review the basic terms of the equation. M refers to tokens in circulation and V refers to their ‘velocity’ or the number of times each token changes hands in a given period (though we will expand this definition later on). On the right side, P refers to price and Q to quantity (or transaction value in real terms if we are using the so-called Fisher formulation, MV=PT). The right-hand side is the “real economy,” or ‘GDP,’ while the left is the “monetary economy.” The two operate in parallel to each other.

当前估值框架的核心论点是，效用价值可以通过如下方式得出: (a)预测网络提供的标的资源的需求(the network’s ‘GDP’), (b)并将这个数字除以可用的货币基数，以获得单位效用的价值。现值可以用传统的折现法从未来的期望效用值中得到。几乎所有这些估值模型采用的理论框架都是[交换方程式](https://en.wikipedia.org/wiki/Equation_of_exchange),MV = PQ。虽然你会看到这个公式几乎在所有关于加密资产价值的讨论中出现，却很少得到解释，也更少会被进行理论处理。我试图在下文中给出一些清晰的解释，但是现在让我们先回顾一下这个等式的基本术语。M指的是流通中的代币数量，V指的是它们的“流通速度”，或者在给定的时间段内每个令牌交换的次数(虽然我们稍后会扩展这个定义)。在右边，P是指价格和Q指的是数量(如果我们使用所谓的费雪公式，MV=PT，则是实际交易价(transaction value in real terms) T）。右边是“实体经济”，即“GDP”，而左边是“货币经济”。这两者是平行的。

Returning to the models linked to above, both hard-code a constant velocity, project a money supply schedule, a price/quantity schedule, and use the aforementioned equality to derive value per coin. Of course, the output of the model is extremely sensitive to variations in the hard-coded values for both the discount rate and velocity, neither of which is explored in detail. This is not problematic per se as these models are intended to provide nothing more than directional insight. The problem has arisen as the discussion on value in the investment community has honed in on the “velocity” component, in what I will call the “velocity thesis.” The consequent lack of theoretical clarity in these discussions is a key motivator of this piece.

回到上面给出了链接的模型，在其中，都硬编码了一个固定的货币流动速度，预估了一个货币供应计划，一个价格/数量计划，并使用前面提到的等式来算出每个代币的价值。当然，模型的输出对贴现率和速度的硬编码值的变化都非常敏感，这两者都没有得到详细的讨论。这不是问题本身，因为这些模型的目的只是提供方向性的洞察。问题在于投资界对于价值的讨论总是集中在"流通速度"这一部分上，我称之为"流动速度论点"。在这些讨论中理论清晰性的缺失，是促使我去写这篇文章的主要驱动力。

## **The Velocity Thesis 货币流通速度论点**

To understand the current debates on velocity and value, I suggest reading the following if you have not already: [Crypto Valuation](https://www.slideshare.net/loukerner/cryto-valutaion-ryan-selkis) and [95 Crypto Theses for 2018](https://medium.com/@twobitidiot/95-crypto-theses-for-2018-ca7b74f8abcf) by [Ryan Selkis](https://twitter.com/twobitidiot); [The Blockchain Token Velocity Problem](https://www.coindesk.com/blockchain-token-velocity-problem/) by [Kyle Samani](https://twitter.com/KyleSamani?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor); [An (Institutional) Investor’s Take on Cryptoassets](https://s3.eu-west-2.amazonaws.com/john-pfeffer/An+Investor%27s+Take+on+Cryptoassets+v6.pdf) by [John Pfeffer](https://twitter.com/jlppfeffer?lang=en); [On Medium-of-Exchange Token Valuations](http://vitalik.ca/general/2017/10/17/moe.html) by [Vitalik Buterin](https://twitter.com/VitalikButerin?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor). I especially recommend the latter two as they form the inspiration for the approach detailed hereinafter.

想要理解当前对于加密货币流通速度与价值的争论，如果你还没有读过以下文章的话，我建议你读一下。
 [Crypto Valuation](https://www.slideshare.net/loukerner/cryto-valutaion-ryan-selkis) and [95 Crypto Theses for 2018](https://medium.com/@twobitidiot/95-crypto-theses-for-2018-ca7b74f8abcf) by [Ryan Selkis](https://twitter.com/twobitidiot); [The Blockchain Token Velocity Problem](https://www.coindesk.com/blockchain-token-velocity-problem/) by [Kyle Samani](https://twitter.com/KyleSamani?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor); [An (Institutional) Investor’s Take on Cryptoassets](https://s3.eu-west-2.amazonaws.com/john-pfeffer/An+Investor%27s+Take+on+Cryptoassets+v6.pdf) by [John Pfeffer](https://twitter.com/jlppfeffer?lang=en); [On Medium-of-Exchange Token Valuations](http://vitalik.ca/general/2017/10/17/moe.html) by [Vitalik Buterin](https://twitter.com/VitalikButerin?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor).　我尤其推荐阅读后两篇，因为他们启发了我下文中所阐述的思路。

**(Note: I refer to these and other pieces under the “velocity thesis” for short-hand convenience. This is not to suggest that the people listed above do not have significant points of disagreement with each other with respect to the concept of value (they do). To the extent possible, I attempt to highlight these differences.)**

**(注:我用“流通速度论点”来概述所引用的这些文章是为了方便起见。这并不是说上面列出的人在货币价值这一概念上没有明显的分歧(他们确实有分歧)。在可能的情况下，我会试图强调这些差异。)**

The uniting argument in the above articles is that tokens that are not store-of-value assets will generally suffer from high velocity at scale as users avoid holding the asset for meaningful periods of time, suppressing ultimate value. My claim here is that this thesis is directionally correct, but hard to operationalize. Much of the difficulty, in my view, derives from an inability to precisely define, measure, and project velocity over time. The first step to ameliorating this is to better understand the theoretical framework it derives from. Correspondingly, I find it instructive to take a step back and explain velocity more clearly before more formally restating the thesis.

上述文章中的共同论点是，不属于价值存储资产的代币，其规模会受到流通速度高这一特点的影响，因为用户会避免持有资产超过一定时间，从而抑制了最终的价值。我看法是，这一论题在方向上是正确的，但很难具有操作性。在我看来，很多困难都来自于无法精确地定义、度量和预估流通速度随时间的变化。改善这一状况的第一步是更好地理解它的理论框架。相应地，在重新开始讨这一主题前，我觉得退一步，更清楚地解释流通速度是很有意义的。

Most of the above articles define velocity as “the number of times money changes hands”, or formulaically as V=PQ/M, by reference to the equation of exchange. This, of course, leaves us none the wiser as to how to model velocity, as the equation of exchange is nothing more than an identity. MV=PQ just says that the money flow of expenditures is equal to the market value of what those expenditures buy, which is true by definition. The left and right sides are two ways of saying the same thing; it’s a form of double-entry accounting where each transaction is simultaneously recorded on both sides of the equation. Whether an effect should be recorded in M, V, P, or Q is, ultimately, arbitrary. To transform the identity into a tool with predictive potency, we need to make a series of assumptions about each of the variables. For example, monetarists assume M is determined exogenously, V is constant, and Q is independent of M and use the equation to demonstrate how increases in the money supply increase P (i.e. cause inflation). Initial M, Q, and P levels are usually separately estimated from different data sources, often leading to significant discrepancies. Meanwhile V is extremely hard to observe directly. As such, by convention, “[velocities] have generally been calculated as the numbers having the property that they render the equation correct. These calculated numbers therefore embody the whole of the counterpart to the statistical discrepancy.” (See [Friedman](http://www.nber.org/chapters/c11402.pdf)). 

上面的大多数文章都将速度定义为“金钱易手的次数”，或以V=PQ/M为公式表达，引用了交换方程式。当然，这让我们对如何为速度建模依然一无所知，因为交换的等式不过是一个恒等式(identity)。MV=PQ只是说，支出的资金流等于这些支出购买的市场价值，根据定义这是正确的。等式的左右两边是同一东西的两种说法;这是一种复式记账法的方式，每笔交易都同时记录在等式的两边。是否应该在M、V、P或Q中记录结果，最终是任意的。为了将恒等式转换成具有预测效力的工具，我们需要对每个变量进行一系列假设。例如，货币主义者假设M是由外源决定的，V是常数，Q是独立于M的，用这个方程来证明货币供应量增加会引起P的增长(即引起通货膨胀)。初始的M、Q和P的水平，通常根据不同的数据源分别估计，常常会导致显著的差异。与此同时，V非常难以直接观察。因此，按照惯例，“[流通速度]通常被计算为具能够使得方程式正确的数字。因此，这些计算出的数字对应于统计的整体差异。“(见[弗里德曼](http://www.nber.org/chapters/c11402.pdf))。


Based on this understanding, we can now make three observations about the velocity thesis:

基于上述理解，现在我们能够得出对于货币流通速度主题的三个观察：

1.) The first practical problem with velocity is that it’s frequently employed as a catch-all to make the two sides of the equation of exchange balance. It often simply captures the error in our estimation of the other variables in the model. Without further specification, saying that projects should minimize velocity is about as useful as saying that a business should attempt to maximize goodwill on its balance sheet. As velocity in its pure form is difficult to directly observe (the best attempt I am aware of is outlined in section 3.4 of the [BlockSci paper](https://arxiv.org/pdf/1709.02489.pdf)), current (tautological) definitions of velocity as PQ/M need to be reformulated to allow us to estimate velocity separately from the other variables and project its fluctuations over time. Returning to our historical analogy, we need to develop better accounting definitions before we can truly operationalize velocity and related concepts (e.g. PE, RoA, PB would all be meaningless if we could not agree on how to define and measure them across businesses and over time).

1.) 流通速度的第一个实际问题是，它经常被用作一种万能工具，以使交换方程式的两边平衡。它通常只是捕获了模型中我们对其他变量的估计错误。如果没有进一步的规范，比如说项目应该将流通降到最低，它的用处，就像说企业应该试图在其资产负债表上最大化其商誉一样。因为流通速度的纯粹形式很难直接观察(我知道的最好的尝试是[BlockSci 论文](https://arxiv.org/pdf/1709.02489.pdf)3.4节中概述的那样),当前(同义反复(taotological))将速度定义为PQ / M需要重新修改， 以允许我们能够独立于其他的变量评估流通速度，以及预估流通速度随时间的波动。回到我们的历史类比，我们需要建立更好的会计定义，然后才能真正让流通速度和相关概念具有可操作性(如果我们不能就如何定义以及如何跨商业领域跨时间衡量达成一致，那么如PE、RoA、PB这些概念将毫无意义)。

2.) If token value is equal to PQ/VM, we can agree that the problem is not “high” vs “low” velocity, as some writing the topic seems to suggest (though that certainly matters, all things being equal). The real question is how changes in velocity correlate with changes in PQ. Strong positive correlations approaching 1 effectively decouple token value from network transaction growth (note that while this is a drag on the upside, it is protective of value on the downside). If the two are uncorrelated, then token utility value grows (and declines) linearly with demand for the underlying utility (this is what happens in the INET model). Negative correlations act as a lever, generating outsized price swings relative to growth or decline in PQ. Therefore, we need to compare the growth rates of velocity and PQ to formalize the velocity thesis: The thesis states that if velocity grows faster than PQ, token utility value declines. Vitalik and Pfeffer argue that this will likely happen given sufficiently low transaction friction and superior return/store-of-value alternatives. The validity (or invalidity) of this prediction is not something we can explore thoroughly in current models.

2.) 如果代币价值等于PQ/VM，我们可以认为这个问题不是流通速度高低的问题，就像某些该主题的写作者似乎暗示的那样(尽管这确实很重要，所有的东西都相等)。真正的问题是速度变化如何与PQ的变化相关联。接近于1的强相关系数，有效地将代币价值与网络中交易的增长分离开来(注意，虽然这是上行的阻力，但它在下行时，对价值有保护作用)。如果两者是不相关的，那么代币的效用值随对底层效用的需求而线性增长(和下降)(这是在INET模型中发生的情况)。负相关效应是一种杠杆，它产生的价格波动与PQ的增长或下降有关。因此，我们需要对流通速度和PQ的增长率进行比较，以形成对流通速度的论题的形式化表述: 论文称，如果流通速度比PQ快，代币的效用值将下降。Vitalik和Pfeffer认为，这很可能会发生，如果交易摩擦足够低，而且有更好的回报/价值存储的替代选择的话。这一预测的有效性(或无效性)我们在当前模型中不做深入探讨。

3.) Before continuing, I would note, as a practical matter, that I would caution against the suggestions of some proponents of the velocity thesis for projects to create artificial velocity suppression mechanisms. I view staking, mint-and-burn, and other “sinks” as useful only to the extent that they genuinely improve governance and user experience as opposed to acting as artificial price props. Furthermore, I believe velocity can only be practically useful if it is precisely defined and measurable. Let the finance folk argue about it for now, but until you can define and measure it, I would say you can safely ignore it and go back to building. 

3.) 在继续之前，我要指出，实际上我将谨慎地反对一些人关于流通速度论题的一些提议，他们建议项目建立人工的流通速度抑制机制。我认为staking、mint-and-burn和其他“sinks”只有在真正改善治理和用户体验的范围内才有用，而不是充当人工控制价格的道具。此外，我认为，只有流通速度能精确定义和测量，它才会成为有实际用处的。现在让金融界人士去为之争论吧，但在你能定义和衡量它之前，我想说的是，你可以放心地忽略它，回到构建上去。

In sum, we can now concretely state that to support (or refute) the velocity thesis, we need to examine how velocity, PQ, and utility value relate to each other over time, requiring a way to operationalize velocity and project it over time. This, in turn, necessitates a slight departure from existing cryptoasset valuation methodology. 

总之，我们现在可以具体地说明，为了支持(或否定)流通速度的命题，我们需要研究流通速度、PQ和效用值如何随着时间的推移相互关联，从而需要一种方法来使得流通速度具有可操作性(operationalize)，并预测它随时间的变化。这反过来又需要对现有的密码资产评估方法论稍微偏离。

## **A Monetary Critique of the INET Model** 
    **对INET模型的货币理论批判**

Now that we’ve examined the velocity thesis in some detail, we can articulate six challenges that it presents to the INET model from the standpoint of monetary theory:

现在我们已经详细地研究了流通速度的论题，我们可以从货币理论的角度来阐述它给INET模型带来的6个挑战:

1.) Demand for money and demand for commodities are conceptually distinct and should be accordingly decoupled in monetary valuation models. In the INET model, demand for INET and demand for bandwidth are practically one and the same. We need to model demand for money separately from demand for commodities.

对货币的需求和对大宗商品的需求在概念上是截然不同的，因此在货币估值模型中应该是脱钩的。在INET模型中，对INET的需求和对带宽的需求实际上是相同的。我们需要把对货币的需求与对商品的需求分开。

2.) Cryptoassets are embedded in a broader asset universe. One way of looking at the INET model is as a single-good, single-asset economy. Utility tokens should instead be seen to compete with other assets for holders. As a corollary, expected returns of other assets should affect demand for the asset being modeled. 

加密资产处于更广的资产体系中。一种看待INET模式的方法是单一货物，单一资产经济。相反，效用代币应该被看作是与持有者的其它资产相竞争的。因此，其他资产的预期收益应该会影响被建模的资产的需求。

3.) Related to (2), transactional demand and speculative demand are conceptually distinct and have different drivers. In the INET model, speculative demand is captured in a supply reduction (HODLed coins are removed from circulation). If the asset is not a store of value, as per the velocity thesis, it may be more realistic to direct speculative demand to another asset and capture this store-of-value demand within the money demand curve.

3.)与(2)相关，交易需求和投机需求在概念上有所差别，并且有不同的驱动因素。在INET模型中，投机需求在供应减少中被捕获(被持有的货币，不再继续流通)。如果资产不是一种价值存储，根据流通速度的论点，直接对另一资产进行投机性需求，并在货币需求曲线中捕捉这种价值存储需求，可能会更加现实。

4.) Blockchain economies are (currently) highly frictional. These frictions could be in the form of transaction costs/fees, cognitive costs, illiquidity, inconvenience, and others. We need to model these frictions, project their behavior over time, and trace their effects on demand for different assets.

4). 区块链经济体(目前)处于高度摩擦状态。这些摩擦可能是以多种形式存在，交易成本/费用、认知成本、非流动性、不便性等。我们需要对这些摩擦进行建模，并衡量随时间推移它们的行为，并跟踪它们对不同资产需求的影响。

5.) Velocity (a) varies over time and (b) should be measurable in a way that is (at least somewhat) distinct from the other variables. I.e. In the INET model, velocity and PQ have no correlation, while price and PQ have a perfect 1.0 correlation coefficient. We instead need to model endogenous velocity as time-varying and distinct from the money supply term to better study the effects of PQ movements on value accretion.

5). 流通速度(a)随着时间的变化而变化，(b)应该以一种(至少在某种程度上)与其他变量不同的方式来衡量。在INET模型中，velocity和PQ没有相关性，而price和PQ有一个完美的1.0相关系数。相反，我们需要将内生流通速度建模为时变性的，且与货币供应的术语区分，以便更好地研究PQ的变化对价值增值的影响。

6.) Expanding on (5) payment patterns matter. In INET, patterns of payments don’t matter as long as they all sum to the same transactional volume. If users purchase one large token balance each year and spend it gradually over the year, the effects on value are different than if users made many small purchases to finance consumption as needed. We need a way of modeling different payment patterns and their effects on velocity and value.

6). 对(5)扩展一下，付款模式很重要。在INET中，支付模式并不重要，只要它们的总和是同样的交易规模就可以了。如果用户每年购买一次大额的代币数额，并在一年的时间内逐步消费， 这对于价值的影响，不同于用户在需要时购买大量的小额代币，来满足消费需求。我们需要方法来对建模不同的支付模式及其对流通速度和价值的影响。

More broadly, I believe the community’s understanding of cryptoasset value drivers has outgrown the simple articulation of value in the INET model. And Chris [seems to agree](https://twitter.com/cburniske/status/952625373614870534).

更广泛地说，我相信社区对加密资产价值驱动因素的理解已经超过了在INET模型中对价值的简单阐释。克里斯[似乎也同意这一点](https://twitter.com/cburniske/status/952625373614870534)。

原文:  https://medium.com/blockchannel/on-value-velocity-and-monetary-theory-a-new-approach-to-cryptoasset-valuations-32c9b22e3b6f
作者:  [Alex Evans](https://medium.com/@ahe4nc?source=post_header_lockup)

## **VOLT: A Two-Asset Model with Endogenous Velocity**
**VOLT: 内生流通速度的双资产模型**

In this section, I present an alternative cryptoasset valuation methodology that attempts to remedy the key problems identified in the last section. I model a fictitious utility token, VOLT, which can be exchanged by households to buy electricity at below-retail rates. Please note that while there are numerous projects targeting related use cases, this model in no way references these (it’s an entirely made-up example intended for illustrative purposes).

在这一节中，我提出了一种替代的密码资产评估方法，试图解决上一节中所识别出的关键问题。我建立了一个虚拟的实用(utility)代币，VOLT，它可以由家庭以低于零售价格的价格购买电力。请注意，虽然有许多项目针对相关的用例，但是这一模型没有引用它们(这是一个完全虚构的示例，用于说明的目的)。

The token is embedded in an economy with one good (electricity) and two assets: VOLT and a store-of-value asset that has a given expected rate of annual return. This is a frictional economy wherein users start with a fixed dollar amount at the beginning of each year in the store-of-value asset and must transfer their deposits to VOLT in order to finance their consumption of electricity, incurring transaction costs with each transfer. Note: You can select the store-of-value asset to be your favorite SoV cryptoasset or fiat-denominated security. This choice is of little importance to the functioning of the model as presented, except to the extent that it impacts your forecasted transaction costs.

代币内嵌在一个拥有一种货物(电力)和两种资产的经济中: VOLT 和一种具有给定预期年回报率的价值存储资产。这是一个有摩擦性的经济，用户在每年开始时有固定美元金额的价值存储资产，并且必须将他们的存款转换到VOLT ，以便为他们的电力消费提供资金，并在每次转账时产生交易成本。注意:您可以选择存储价值资产是哪一种，是你喜欢的SoV(Stock of  Value, 价值存储)加密资产，或是法币计价的证券。这一选择对所描述的模型的运作没有什么大影响，除非它影响到你对交易成本的预期。

I model VOLT ‘money demand’ using the [Baumol-Tobin](https://en.wikipedia.org/wiki/Baumol%E2%80%93Tobin_model) “cash inventories” approach. Given that this method is slightly more involved than the INET approach, I pause to explain the key intuitions and underlying formulas before moving on to the actual model.

我用[Baumol-Tobin](https://en.wikipedia.org/wiki/Baumol%E2%80%93Tobin_model)的 “货币存货” 的思路来对VOLT的“货币需求”进行建模。考虑到这种方法比INET方法稍微复杂一些，我先停下来解释关键的直观观念和基本的公式，然后再转向实际的模型。

Total spending, Y, is the amount (in USD) that users plan to spend on VOLT each year. This can be thought of as the total GDP of the VOLT economy. Users spend Y uniformly throughout the year. R is the expected return on the store of value asset. C is the transaction cost of moving balances from the SoV asset to VOLT. N is the number of transfers that users of VOLT complete each year to ensure smooth consumption of electricity. 

总花费，Y，是用户计划每年在VOLT上花费的金额(用美元表示)。这可以被看作是VOLT 经济体的总GDP。用户整年总共花费了Y。R是价值存储资产的预期收益。C是从 SoV 资产换为VOLT的交易成本。N是每年为确保对电力的平稳消耗，VOLT的用户所完成的交易量。

Users thus pay C*N in transaction fees each year. The average money balance held in VOLT each year is Y/2N. The return that VOLT users forgo each year is R*Y/2N. Therefore, users select N, subject to Y, R, and C, in order to minimize their total cost function: R*Y/2N + C*N. Taking the derivative of the total cost function with respect to N, we have:

因此，用户每年支付C*N的交易费用。VOLT 每年的平均余额为Y/2N。VOLT 用户每年放弃的回报是R*Y/2N。因此，用户选择N，限定Y、R和C，以使其总成本函数最小化: R*Y/2N + C*N。求总成本函数对N的导数，我们得到:

![2.png](http://upload-images.jianshu.io/upload_images/1084915-5c20cd5c3ee00db0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
etting this equal to zero and solving for N we obtain the cost-minimizing N value of:

将它的值设为0, 然后求解N的值，我们得到让成本最小化的N的值为:

![3.png](http://upload-images.jianshu.io/upload_images/1084915-335a320d4011fc99.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Finally, to get our money demand curve in terms of Y, C, and R, we plug the cost-minimizing N value back into the average money balance formula (Y/2N). We can now formulate our money demand function as:

最后，为了获得货币需求曲线，用Y, C和R来表示，我们把使成本最小化的N值代回到平均货币资产的公式(Y/2N)。现在我们可以把货币需求的方程写成:

![4.png](http://upload-images.jianshu.io/upload_images/1084915-f0c8d343610dbb31.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

We can thus say that VOLT ‘money demanded’ is equal to the cost-minimizing VOLT balance that users hold each year, which is a function of the GDP that the VOLT economy facilitates, the expected rate of return on the store-of-value asset, and the cost per transaction. 

因此我们可以说，VOLT的“货币需求”等于用户每年所持有的让成本最小化的VOLT余额，这是VOLT 经济所产生的GDP、价值存储资产的预期回报率以及每笔交易的成本的一个函数。

Incidentally, we now have the tools at our disposal to formulate a definition of velocity without direct reference to the other monetary term in the equation of exchange, M. Velocity here is equal to the annual GDP, Y, of the VOLT economy over the demand for VOLT balances (the cost-minimizing average balance), or, equivalently, two times the optimal number of transfers, 2N. In other words, if a user transfers one large balance at the start of the year, each VOLT token turns over twice: Once when the user trades her SoV balance for VOLT and again when she exchanges it for electricity. If she buys in two times for half of the amount each time, each VOLT turns over four times, and so forth. Equipped with this definition, we can abandon the fixed-velocity approach of INET and instead project velocity endogenously alongside money demand as a function of Y, R, and C. Note this is equivalent to saying that ‘money demanded’ is equal to GDP over velocity, implying that our final result should still conform to MV=PT.

另外, 我们现在有工具能够形成对流通速度的定义，而不直接引用货币交换方程式中的其它货币术语，M.。流通速度等于：Y -- VOLT经济的年度GDP除以对VOLT额度的需求(成本最小化的平均余额), 或者等价地，最优交易次数的两倍，2N。换句话说，如果用户在年初时进行了一次大额兑换，那么每一个VOLT代币都会翻转两遍: 一次，当用户用她的“SoV”的额度交换VOLT时，l以及当她把VOLT换成电的时候。如果她分了两次购买，每次买一半，那么每个VOLT代币都要流转四次，如此等等。有了这个定义, 我们可以放弃INET模型中的固定流通速度的思路, 而是内生地衡量流通速度，将货币需求作为Y, R和C的函数。注意，这相当于说“货币需求”等于国内生产总值除以流通速度, 这意味着我们的最终结果仍应符合MV = PQ（原作似乎有误，为MV=PT）。

The model I use in the next section can be found here: [https://docs.google.com/spreadsheets/d/1a1SzF2H1Y3twTvqAlGAwm8Q2jG-CPnP1Q-7qopN-4LE/edit#gid=428912142](https://docs.google.com/spreadsheets/d/1a1SzF2H1Y3twTvqAlGAwm8Q2jG-CPnP1Q-7qopN-4LE/edit#gid=428912142)

下一节我用到的模型在这里可以找到: [https://docs.google.com/spreadsheets/d/1a1SzF2H1Y3twTvqAlGAwm8Q2jG-CPnP1Q-7qopN-4LE/edit#gid=428912142](https://docs.google.com/spreadsheets/d/1a1SzF2H1Y3twTvqAlGAwm8Q2jG-CPnP1Q-7qopN-4LE/edit#gid=428912142)

I would appreciate reporting of any issues you find with the model (especially mechanical problems/bugs), so I can update the sheet to work for everyone else.

 如果你发现模型有任何问题(尤其是原理问题/bug)，欢迎告诉我，这样我就可以更新这张表，让它对其他人也有用。
![5.png](http://upload-images.jianshu.io/upload_images/1084915-861e55e8e7920f60.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### **Step 1: VOLT Supply Schedule VOLT 供应安排**

Despite the departure on other points, we still need to project both supply for VOLT tokens and residential electricity facilitated by the VOLT economy. Thankfully, Chris’ shoulders are there for us to stand on and I follow a virtually identical approach. With respect to money supply, the only theoretical difference is that I explicitly assume VOLT will have no HODLers as they will instead opt to hold the store-of-value asset (i.e. VOLT users are risk-averse). What is interesting about this point is that, in the model, each of the three functions of money is performed by a different asset: We have a separate Store-of-Value asset, while VOLT is the medium of exchange and USD is the internal unit of account. Reality will, of course, be more complicated.

尽管在其他方面有所不同，但我们仍然需要规划提供VOLT 代币供应和为VOLT经济体用到的电力供应。幸好我们可以站在Chris的肩膀上，我也遵循了一种几乎相同的思路。关于货币供应，唯一的理论区别是，我明确地假设了 VOLT没有坚定持有者(HODlers)，因为他们将会选择持有价值储存的资产(即，VOLT用户是风险规避型的)。有趣的是，在模型中，货币的三个功能都是由不同的资产来执行的:我们有一个单独的价值存储资产，而 VOLT 是交换媒介，而美元是内部的记账单位。当然，现实会更复杂。

I model a supply of 100K VOLT, 10% of which is issued to founders, vesting at 25% annually starting after a one-year cliff. Another 10% is issued to the foundation, of which 20% is spent annually and returned to circulation. Unlike INET, I model VOLT supply as inflationary, growing at a 3% annual rate. This is arbitrary and included mainly for variety’s sake.

我的建模中，有100K VOLT 的供应量，其中10%是发给创始人的，在一年的锁定期之后，每年以25%的比例出售。另外10%的资金被发放给基金会，其中每年花费20%的资金用于花费，重新进入市场流通。与INET不同的是，我定义 VOLT  的供应方式是通货膨胀型的，以每年3%的速度增长。这是任意的，主要是为了多样化的缘故而设定。

![6.png](http://upload-images.jianshu.io/upload_images/1084915-288ba49d9939f577.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


Total VOLT tokens in circulation are determined by the tokens already circulating, plus any tokens released by the founders or the VOLT foundation, plus new tokens created by the inflation mechanism each year.

已经流通的代币，加上创始人或VOLT 基金会释放的代币，再加上每年由通货膨胀机制创造的新的代币，决定了市场流通中VOLT代币的总数量。

### **Step 2: The VOLT Electricity Demand 步骤2:  VOLT 电力需求**

Note: For the electricity market, please open the notes in the assumption cells (highlighted on the top right of each cell) to see citations and additional notes. My aim here is to arrive at a value for GDP for the rest of the model to work, not to make any sort of claim about electricity markets. There are undoubtedly significant errors and oversimplifications in the assumptions.


注意:对于电力市场，请在假设的单元格(每个单元的右上方高亮显示)中打开注释，以查看引用和附加的说明。我在这里的目标，是得到一个GDP的值，能够让模型的其余部分可以生效，而不是要对电力市场提出任何批评。毫无疑问，在假设中会存在明显的错误和过度简化之处。

First, I assume a retail electricity price of $0.12 per kWh. I project this to stay flat as retail electricity prices have been relatively stable in recent years. I assume VOLT users can purchase electricity at $0.035 per kWh, an average price across U.S. wholesale markets. Again, I forecast no growth or decline in this price through 2028\. Average kWh consumption per U.S. household was 10,766 kWh per year in 2017\. Again, I project no change in this going forward. There were approximately 126 million U.S. households in 2017, which I assume will grow at 1% annually through 2028\. To simplify things, VOLT is assumed to only be available in the U.S and to be capable of addressing 10% of the U.S. residential electricity market at peak penetration. To avoid overestimating market penetration in earlier years (and underestimating in later years), I follow Chris in projecting an S-curve for adoption. This curve has VOLT entering ‘hypergrowth’ starting in 2023, with a deceleration in the rate of growth as VOLT approaches market saturation and maturity over time.

首先，我假设零售价为每千瓦时(kWh)0.12美元。由于近年来零售电价相对稳定，所以我计划保持不变。我假设VOLT用户可以以每千瓦时0.035美元的价格购买电力，这是美国批发市场的平均价格。同样，我预计这个价格不会在2028年之前增长或下降。2017年，美国家庭平均每年的电力消费为10, 766千瓦时。同样，我在这方面没有改变。2017年，美国大约有1.26亿户家庭，我估计，到2028年，美国家庭的年增长率将达到1%。为了简化，我们认为VOLT代币只在美国可用， 在峰值时，会在美国住宅电力市场中，占到10%。为了避免在早期高估市场的渗透率(以及在以后的几年里低估了)，我跟随Chris的思路设计了一条S曲线，以供采用。这条曲线从2023年开始进入“超级增长”，随着VOLT接近市场饱和和成熟，它的增长速度将会减慢。

![7.png](http://upload-images.jianshu.io/upload_images/1084915-60f33977690b1f70.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Using the adoption curve, I estimate VOLT to capture a given percentage of kWh consumed by households in the US each year. This kWh share is multiplied by the wholesale electricity price to derive a value for annual spending on VOLT (i.e. VOLT’s ‘GDP’).

利用这条曲线，我估计VOLT可以占据美国家庭每年消费的kWh的一定百分比。这一千瓦时的份额乘以批发电价，得到每年花费在VOLT的价值 (即VOLT 的“GDP”)。

![8.png](http://upload-images.jianshu.io/upload_images/1084915-aa69d99b60bf9adc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Again, the numbers are exclusively illustrative. If we needed to be more precise, for example, we might project adoption on a state-by-state or county-by-county basis (real-world electricity markets are highly localized) and specify a separate S-curve for each market.

再说一遍，这些数字只是用于说明的作用。如果我们需要更精确的话，比如，我们可以在州或县的基础上进行估计(现实世界的电力市场是高度本地化的)，并为每个市场指定一条单独的S曲线。


### **Step 3: Money Demand for VOLT Tokens 步骤3: VOLT 代币的货币需求**

To create the VOLT demand curve, I assume an expected rate of return on the store-of-value asset, a given initial transaction cost, and a transaction cost decline schedule.

为了创建VOLT需求曲线，我假定了价值存储资产的预期回报率，给定的初始交易成本，以及交易成本下降的时间表。

I assume a store-of-value asset with an expected return of 5% per year. Given that this essentially functions as a risk-free rate of return in our model, I would consider it quite an aggressive assumption (this just captures what I see as optimistic cryptoasset return expectations). You are obviously welcome (if not advised) to bring this value closer to a 3-month [Treasury Bill](https://ycharts.com/indicators/3_month_t_bill) (1.41% at the time of writing) or some other proxy of the risk-free rate (but remember to think about possible impacts on corresponding transaction cost assumptions). It may also be helpful to model some change in this value over time. However, ‘expectations’ are hard to project, so I just straight-line the value through 2028\. I would love to see some debate on how to best handle this set of assumptions.


我假设是一种价值存储资产的预期年回报率为5%。考虑到这本质上是我们模型中的无风险回报率，我认为这是一个相当激进的假设(这恰好正是我所认为对加密资产回报预期的乐观估计)。也当然欢迎(如果不是建议的话)你把这个值设为接近3个月[国债](https://ycharts.com/indicators/3_month_t_bill)(在撰写本文时1.41%)或其他代理的无风险利率(但是记住考虑可能影响相应的交易成本的假设)。随着时间的推移，对这个值进行建模也会有所帮助。然而，“期望”是很难推断的，所以我只是把它的价值用到了2028年。我很乐意看到一些关于如何最好地处理这一系列假设的辩论。

Transaction costs in the initial year are assumed to be $20 per transfer, which is arguably an underestimation. Remember that this number is a fully-loaded representation of friction in the VOLT economy. These costs could include (but are not limited to): network transaction fees (for example, average [BTC transaction fees](https://bitinfocharts.com/comparison/bitcoin-transactionfees.html) were at $30 and Ethereum’s [average gas cost](https://ethgasstation.info/) at $1.1 at the time of writing), exchange fees and spreads (e.g. Bittrex charges [0.25% commission](https://bittrex.com/fees) on trades), other costs resulting from illiquidity, any instability (real or anticipated) motivating the holding of precautionary VOLT balances to safeguard smooth consumption, the extent to which any given transaction constitutes a taxable event in the jurisdiction in question, time waiting for confirmations, implicit costs relating to asset custody and counterparty risk, inconvenience and cognitive load. I expect the ‘mental’ friction component to be the most significant for an average user. The better we can estimate and forecast the transaction cost parameter, the more accurate our model will be, so I would appreciate suggestions and debate on this point as well.

最初一年的交易成本假定为每次货币转换为20美元，这可以说是低估了。请记住，这个数字是VOLT 经济中一个完全负载的摩擦表示。这些成本可能包括(但不限于):网络交易费用(例如,平均[BTC交易费用](https://bitinfocharts.com/comparison/bitcoin-transactionfees.html)在30美元, Ethereum[平均gas成本](https://ethgasstation.info/)在撰写本文时1.1美元), 交易所费用和传播(如Bittrex收取[0.25%的交易佣金](https://bittrex.com/fees)),其它由于流动性不足产生的费用,任何不稳定(实际或预期的)会促使人们出于防御在账户中持有一定的VOLT，用于维护电力的顺利消费, 任何特定的交易在管辖范围内的应税事件的程度,  等待确认, 与资产托管和交易对手风险相关的隐性风险, 不便和认知负荷。我认为“心理”摩擦部分，对一般用户来说是最重要的。我们对交易成本参数的估计和预测越好，我们的模型就越准确，因此我也会对这一点提出建议和讨论。

As far as projecting how transaction costs will behave in the future, my main interest here is to numerically test the velocity thesis that states that utility token values will collapse alongside transaction costs in a frictionless future. To that aim, I find it most conceptually correct to model transaction cost declines in a similar manner to token adoption, using the familiar S-Curve. Here, friction could be said to decline for technological reasons (e.g. second-layer scaling solutions and cross-chain atomic swaps) as well as behavioral reasons (users become more comfortable with using cryptoassets in their daily lives). As such, transaction costs decline very slowly in initial years, but begin declining aggressively in 2023, the same year that VOLT enters hypergrowth (i.e. when mainstream users, not just early adopters, begin using the network as per the traditional S-curve “diffusion of innovation” theory). Ultimately, I assume a miniscule transaction cost in the final year, equal to $0.36 (essentially zero relative to the projected size of the average VOLT transfer of $270K in 2028).

在预测交易成本在未来会表现如何时，我的主要兴趣是通过对流通速度的论点进行数值测试，即在无摩擦的未来中，实用代币的价值将与交易成本一起崩溃。为了这个目的，我发现使用类似的S-Curve，采用与构建代币使用模型类似的方式对交易成本的下降进行建模，在概念上是正确的。在这里，可以说由于技术原因(例如第二层的伸缩解决方案和跨链的原子交换)以及行为原因(用户在日常生活中使用加密资产变得更加舒适)，可能会导致摩擦的减少。因此，在最初几年，交易成本的下降非常缓慢，但在2023年，即VOLT进入高速增长时(根据传统的S曲线“创新扩散”理论，主流用户，而不仅仅是早期的使用者开始使用这一网络)，交易成本开始大幅下降。最终，我假设在最后一年的交易成本很小，等于0.36美元(相对于2028年VOLT达到的平均交易额为$270K的规模来说，可以视作为零)。

![9.png](http://upload-images.jianshu.io/upload_images/1084915-25370448f6d8bed0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


Based on the formulas previously laid out, I calculate the optimal number of transfers per year as a function of VOLT GDP, the expected rate of return on the SoV asset, and the transaction cost. The amount transferred each time is the total spending in VOLT (VOLT GDP) over the number of transfers for that year. Similarly, the average VOLT held (VOLT demand function) is VOLT GDP over two times the number of transfers. This number times the expected rate of return on the SoV asset is the amount of return VOLT users forgo each year.

根据之前列出的公式，我计算出每年 作为VOLT GDP(VOLT)的函数的每年最优交易量，SoV资产的期望收益率，以及交易成本。每一次交易转账的金额，是用当年 VOLT 的消费总额(VOLT GDP)，除以当年的交易转账数量。同样的，VOLT的平均持有量(VOLT需求函数)是VOLT的GDP除以交易数量的两倍。这个数字乘以SoV资产的预期回报率，是用户每年放弃的回报率。

We calculate velocity directly as VOLT GDP over the annual VOLT money demand (average VOLT balance held). Remember that this can also be calculated as two times the number of transfers. Finally, utility value is calculated as Money Demanded/Money Supplied, or average VOLT balance held over the number of circulating VOLT tokens (MV=PQ solution). As such, we can restate the solution as VOLT GDP over the product of VOLT tokens in the float and velocity for that year.

我们计算的流通速度，是直接用VOLT GDP除以年度的VOLT 货币需求(VOLT的账户平均持有量)。记住，这也可以计算为转账数量的两倍。最后，效用价值被计算为货币需求/货币供应，或者说VOLT账户的平均值除以VOLT代币的流动次数(MV=PQ解决方案)。因此，我们可以将答案重新表述为VOLT的GDP除以VOLT代币在那一年的流动数量和流通速度的乘积之后，得到的结果。

Finally, we discount the future utility value in 2028 back to 2018\. The discount rate here differs slightly from INET, as we need to incorporate the risk-free rate (very high at 5%). Note that the resulting present value of $0.0244 in 2018 is more than ten times lower than per-token utility value for VOLT in that year. In other words, VOLT would have to be trading at an over a 90% discount to utility value in 2018 to yield a positive expected return for an investor intending to hold through 2028.

最后，我们将2028年的效用价值折算到2018年。这里的贴现率与INET略有不同，因为我们需要合并无风险利率(非常高的5%)。值得注意的是，到2018年，所产生的现值为0.0244美元，比当年VOLT的每代币的效用价值低10倍以上。换句话说，在2018年，VOLT的交易价格将比效用价值低90%以上，从而为有意持有到2028年的投资者带来积极的预期回报。

![10.png](http://upload-images.jianshu.io/upload_images/1084915-bdd7155624a0f416.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### **Step 4: Revisiting the Velocity Thesis**
**步骤4:  回顾货币流通速度的论点**

Plotting VOLT’s utility value over time, we see the velocity thesis’ core prediction in action as utility value peaks in 2025 and declines through 2028\. Viewed through the prism of the INET model, this would appear strange as between 2025 and 2028 VOLT GDP grows nearly 100%, yet utility value per token declines.

将VOLT的效用价值随着时间的推移的变化画出来，我们看到货币流动性论点的核心预测是生效的，即2025年效用值达到峰值，并在2028年下降。从INET模型的角度来看，2025年至2028年VOLT的GDP增长接近100%，但单个代币的效用价值却下降，这看起来很奇怪。

![11.png](http://upload-images.jianshu.io/upload_images/1084915-7ea1c6c79c354340.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

This decline would not register in the INET approach, as demand for the token and demand for the resource are treated as one and the same. To explain what is happening under the hood, we return to the core prediction of the velocity thesis: As friction in the cryptoeconomy declines, demand for utility tokens falls as velocity growth overtakes PQ growth.

这种下降不会在INET的思路中出现，因为对资源的需求和对代币的需求被视为相同的一个东西。为了揭示到底发生了什么，我们回到了流通速度论点的核心预测: 随着在加密经济中的摩擦减少，对效用代币的需求下降，因为流通速度的增长超过了PQ的增长。

![12.png](http://upload-images.jianshu.io/upload_images/1084915-2b765f528296b3a7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

As we can see, despite the fact that during 2026–2028 GDP still grows at a rapid (albeit decelerating) pace, velocity grows even faster, putting downward pressure on price. Conceptually, even though users buy nearly double the amount of electricity using VOLT in 2028 than they do in 2025, they are able to satisfy this higher demand while still holding nearly two-thirds less in VOLT balances on average. In other words, collapsing transaction costs allow them to hold more of their wealth in the store-of-value asset, making many smaller transfers of VOLT as opposed to few larger ones to avoid forgoing return, leading to higher velocity/lower money demand. While velocity is a function of GDP, it is also a function of transaction costs, which begin to register dramatic declines after 2025\. If, for example, we had projected transaction costs to decline at a steady rate, say 10%, the price decline would be delayed to 2028 as both velocity and GDP would fall together in the interim.

正如我们所看到的，尽管2026-2028年GDP仍在快速增长(尽管增速放缓)，但流通速度的增长甚至更快，这给价格带来了下行压力。从概念上讲，即使用户在2028年购买的电量几乎是2025年的两倍，但他们在VOLT上的余额减少近三分之二的情况下，仍然能够满足这一更高的需求。换句话说，交易成本的大幅下滑使他们能够持有更多的价值存储代币，进行多次更小额度的VOLT交易转换而不是进行较少次数但额度更大的转换，以避免收益的损失，这导致了更高的货币流通速度，和更低的货币需求量。虽然流通速度是GDP的函数，但它也是交易成本的函数，交易成本在2025年之后开始急剧下降。例如，如果我们预测交易成本以稳定的速度下降，比如10%，价格下降将推迟到2028年，因为速度和GDP都将在这段时间内下降。

![13.png](http://upload-images.jianshu.io/upload_images/1084915-eeae792ae612b6f9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

While we can deduce the strong correlation between velocity, VOLT GDP, and transaction costs just by looking at the formulas, the relation between GDP and utility value is what truly matters to our conclusion as per the velocity thesis.

虽然我们可以通过计算公式推导出流通速度、VOLT GDP和交易成本之间的强相关性，但根据流通速度的论点，对我们的结论而言GDP与效用值之间的关系才是真正重要的。

![14.png](http://upload-images.jianshu.io/upload_images/1084915-9a356b3bc3355fad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Here we see the how endogenous velocity allows us to decouple utility value from GDP growth. In the INET model, the correlation between GDP growth and INET value is a perfect 1:1 and the correlation between velocity and GDP growth is zero (velocity is fixed). In our model, the correlation between GDP growth and utility value is 0.34\. This is what is driving the result.


在这里，我们可以看到内生的流通速度是如何让我们将效用值与GDP增长脱钩的。在INET模型中，GDP增长与INET的价值之间的相关性是一个完美的1:1，流通速度与GDP增长率之间的相关性为零(速度是固定的)。在我们的模型中，GDP增长与效用值的相关性为0.34。这就是导致结果的原因。

The final point to note about our results is that the utility value of VOLT largely depends on factors outside of VOLT’s ecosystem. Namely, expected returns and transaction costs.

最后要注意的是，VOLT 的效用值很大程度上取决于VOLT 的生态系统之外的因素。即预期收益和交易成本。
![15.png](http://upload-images.jianshu.io/upload_images/1084915-53a7d370753581ec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


In the sensitivity analysis, we see that VOLT’s discounted future utility value varies significantly based on different inputs for C and R (values below our current discounted utility value projection are highlighted in red). This is where I would like to spend more time developing better estimates.

在敏感性分析(sensitivity analysis)中，我们看到 VOLT 的贴现未来效用值因C和R的不同输入而有很大的变动(低于我们预估贴现效用值的现值，用红色高亮显示)。我想在这上面花更多时间来优化，以便得到更好的估量。

## **Parting Thoughts 结语**

Our valuation techniques are ultimately only as good as our accounting standards, measurement tools, and theoretical understanding of value. To that aim, I hope this piece has clarified some of the theoretical valuation debates unfolding in the investment community and has offered some helpful tools for modeling the value of cryptoassets. There are undoubtedly countless mistakes and simplifications in this approach that I hope subsequent discussion will illuminate. I look forward to these debates.

我们的评估技术的好坏，最终只会和我们的会计标准、测量工具和对价值的理论理解一样的水平。为了达到这个目的，我希望这篇文章对现在投资社区中的估值的理论争辩做了部分澄清，并提供了一些有用的工具用于加密资产的价值建模。毫无疑问，在这种方法中有无数的错误和简化，我希望后续的讨论中能够加以阐明。我期待着这些辩论。

Many thanks to [Steven Mckie](https://twitter.com/Steven_McKie?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) for helping me think through this piece, [Oliver Beige](https://twitter.com/ecoinomia?lang=en) for kindly sanity checking the economic logic, as well as everyone cited above for their thought-provoking work on cryptoasset valuations and beyond.

非常感谢[Steven Mckie](https://twitter.com/Steven_McKie?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) 在我思考这篇文章时的帮助, 感谢 [Oliver Beige](https://twitter.com/ecoinomia?lang=en) 帮助进行了经济学逻辑上的审查,  感谢上面所提到的所有的人，感谢他们在加密资产估值及其它事情上所做出的发人深省的研究。

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
