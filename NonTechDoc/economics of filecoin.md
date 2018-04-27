

文章来自：https://medium.com/@ryanshea/the-economics-of-filecoin-a8d826774674

作者：Ryan Shea，Co-founder of Blockstack

译者：区块链中文字幕组 Chuan



## The economics of filecoin Filecoin经济学

*How it stacks up against Bitcoin, Ethereum, Zcash & Tezos*
*它如何与比特币、以太坊、Zcash以及Tezos相提并论*



At Blockstack, we’re thinking very hard about crypto-economic system design, particularly as we approach the release of our own mining system and token sale for the Blockstack network.

在Blockstack（译者注：一个去中心化的操作系统），我们认真思考加密货币经济体系设计，尤其是当我们自己的挖矿系统发布以及Blockstack网络的代币销售临近时。

Bitcoin, Ethereum, Zcash and Tezos have been the networks that we’ve studied most extensively, given that they are truly independent systems with differentiating factors, strong teams, and very promising market opportunities.

比特币、以太坊、Zcash和Tezos是我们研究最多的区块链网络，考虑到它们是真正独立的系统，都带有不同的基因，强大的团队和非常有前景的市场机会。

Beyond these three, Filecoin particularly intrigued us as we see it shares the aforementioned properties as well. And with the Filecoin sale coming up, I thought this was a great opportunity to share some analysis we’ve been doing on the economics of the system and how it compares to Bitcoin, Ethereum, Zcash and Tezos.

除了这三个以外，Filecoin尤其让我们眼前一亮，因为我们认为它也具有上述的特性。由于Filecoin代币销售日期迫近，我认为这是个很棒的机会来分享一些我们对这个系统的经济学分析，以及它跟比特币、以太坊、Zcash和Tezos相比表现如何。



### Supply 供应量

The Filecoin supply has four components: the miner supply, the Protocol Labs supply, the Filecoin Foundation supply, and the sale supply.

Filecoin供应量由4部分组成：矿工的供应量，Protocol Labs持有的，Filecoin基金会所持的，以及用于销售的代币。

The miner supply follows an exponential decay curve with a half life of 6 years. We’ll explore that some more below.

矿工的供应量遵循一个6年的半衰期的指数衰减曲线。

The Protocol Labs supply and the Filecoin Foundation supply each vest over a period of 6 years.

Protocol Labs持有的和Filecoin基金会所持的代币是6年的授权期限。

The sale supply, meanwhile, has variable amounts of vesting. The main sale has vesting over a period of 6 months while the advisor sale allowed participants to vest over periods of 1, 2 or 3 years. For the purposes of this graph, I averaged the vesting out at 1 year.

与此同时，用于销售的代币则有不同的vest周期。主要销售有一个6个月的授予期限，而顾问销售允许参与人有1年、2年或3年的授予期限。对于这张图，平均的授予期限是1年。

The total number of Filecoin that will ever be created is 2B.

Filecoin的代币总量是20亿。



### Supply as a % of Supply After N Years N年后供应量的占比

As mentioned earlier, the Filecoin miner supply schedule follows an exponential decay curve with a half life of 6 years. This is similar to the Bitcoin supply schedule, but with two important differences.

前面提到，Filecoin矿工供应量进度表遵循一个6年的半衰期的指数衰减曲线。这类似于比特币供应量的进度安排，但是有两个重要的区别。

First, the half life of Filecoin is 6 years while the half life of Bitcoin is 4 years. Second, while Bitcoin’s exponential decay is sampled every 4 years, Filecoin’s is sampled every month, leading to a smoother drop-off in the rate of coins mined in each block.

首先，Filecoin的半衰期是6年，而比特币是4年。其次，尽管比特币的指数衰减每4年抽样，但是Filecoin每月取样，这带来的结果就是在每个区块中挖矿速度下降的更加平缓。

You can see from the graph below that Filecoin is a smoother variant of the Bitcoin exponential decay curve. Note that the graph uses yearly sampling, so some of the smoothness of the Filecoin curve could not be adequately captured.

从下图中可以看出，Filecoin跟比特币的指数级衰减曲线相比更加平滑。请注意，图中使用的年度抽样，所以Filecoin的平滑性可能没有被充分地展示出来。



### Annual Supply Growth 年度供应量增加

The growth in the supply of Filecoin is approximately that of Bitcoin for each year that passes, with two exceptions. First, the curve is smoother as it is sampled every month instead of every 4 years. Second, the Filecoin supply growth includes the amount that is being sold in the sale and distributed to Protocol Labs and the Filecoin Foundation, which means that a greater amount is released in the first year.

Filecoin供应量的增加大概与比特币每年释放的数量差不多，但是有两个例外。首先，当按照每月而不是每4年进行抽样的时候，曲线更加平滑。其次，Filecoin供应量增加包含在销售中被卖出的数量以及被分发到Protocol Labs和Filecoin基金会的数量，这意味着更多的Filecoin是在第一年释放的。

You can see the annual supply growth in the chart below:

下面这个图显示了年度供应量增加的情况。



Please note that the Ethereum supply numbers are completely speculative after year 3. Empirically the miner supply increased the total supply by about 11M coins in year 1 and 7M coins in year 2. This number has been decreasing and rapidly approaching 0 as a result of the fork bomb. After Ethereum has migrated over to proof-of-stake, Vitalik has said that the annual inflation rate will be somewhere between 0.5% and 2.0%. I’ve chosen to go with 2.0% for now.

请注意：以太坊供应量在第3年后完全是猜测的。根据经验，矿工供应量增加了总供应量，在第1年达到1100万个代币，第2年则是700万个代币。这个数字一直在减少，由于分叉危险的原因快速地接近于0。在以太坊将工作量证明改为权益证明后，Vitalik说，年通胀率将在0.5%到2%之间。到目前为止，我选择的是2%。



### Creator Ownership 创建者所有权

The Filecoin creator ownership (factoring in the amount going to both Protocol Labs and the Filecoin Foundation) is somewhat higher than the known creator ownerships of Ethereum and Zcash and the estimated creator ownership of Bitcoin (Satoshi’s holdings).

Filecoin 创建者所有权（把后续的数量放入Protocal Labs和Filecoin基金会）比已知的以太坊和Zcash的创建者所有权以及比特币的创始人所有权（中本聪的持有量）要高一些。

Whether that’s a good thing or a bad thing is up to the community to judge. One could say it’s not good for the creators and associated entities to take up such a sizable portion of the protocol tokens. On the other hand, this could be a very good thing for the system if a large portion of the Protocol Labs tokens are reserved for a future financing round, as it would further capitalize the business and provide them the extra fuel they need to compete with AWS.

这是好是坏由社区来判断。人们可能会说创始人和相关人员持有那么高比例的协议代币不是一件好事。另一方面，如果Protocol Labs持有的大量代币用于未来融资，那么这可能对这个系统是好的，因为它会为公司注入资本，为他们提供所需要的额外支持来与AWS竞争。

You can see creator ownerships over time graphed below:

从下图中可以看出创始人拥有量creator ownership的变化情况。



We can break the creator supply amount down further and see that 25% of this amount goes to the Filecoin Foundation while 75% of this amount goes to Protocol Labs. That means that Protocol Labs will end up with 15% of the total final supply while the Filecoin Foundation will end up with 5% of the total final supply.

我们把创始人持有量进一步分解，可以看出持有量的25%流向Filecoin基金会，而75%则流向Protocol Labs。这意味着Protocal Labs最终将获得总供应量的15%，而Filecoin基金会可以获得总供应量的5%。



### Coin Price  代币价格

As a bonus, here’s an analysis of the Filecoin price and what it means for your ownership of the network, as benchmarked against the figures for Bitcoin, Ethereum, and Zcash.

下面是Filecoin价格的分析以及这对你持有的币意味着什么，以比特币、以太坊和Zcash的价格为参照。



Assuming a Filecoin price of 2, it would cost 37.22 to buy 1 one-hundred-millionth of all of the Filecoin tokens that will be minted over the next 20 years.

假设Filecoin价格为2美元，接下来20年要被挖的1亿个Filecoin代币中，则需要花37.22美元才能买到1个。



Meanwhile, it would cost 42.43 to buy the equivalent percentage of the Zcash network. Similarly, to buy equivalent percentages of Bitcoin, Ethereum, and Tezos, you’d have to spend 684.92, 345.31, and 3.18, respectively.

同时，要花费42.43美元来购买同等比例的Zcash代币。同样地，购买相同比例的比特币、以太坊和Tezos，分别需要花费684.92美元，345.31美元和3.18美元。



Here’s a graph that further illustrates the difference: 

下面的图进一步表明了这种差异。



### Conclusion

The Protocol Labs team has taken quite a few learnings from its predecessors and incorporated them into the design of an entirely novel protocol.

Protocol Labs团队从前辈身上获取了一些教训，并把它们结合到全新的协议设计中。

Protocol Labs has taken the exponential decay curve of Bitcoin and improved upon it. They’ve created some interesting dynamics with their token sale. And they’re setting a new precedent with CoinList.

Protocol Labs采用了比特币的指数级衰减曲线，并在此基础上加以改善。他们对自己的代币销售采用了一些有趣的推动措施。他们和CoinList树立了新的先例set a new precedent with CoinList。

Disclosure: I participated in the Filecoin advisor sale and I’m a big fan of Juan and the Protocol Labs team. The article above contains my personal analysis only, not investment advice. Information I have about Filecoin and Protocol Labs may be inaccurate and should not form the basis for any investment decision.

以上只是我个人分析，不构成投资建议。





