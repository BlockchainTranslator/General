##New Bitcoin Wallet Experience — Thinking Outside The Block
##比特币钱包新体验——区块之外的思考
This idea has been in me for a long time now and I mentioned it in many places, for example in ZeroLink’s specification, because it does not only provide fun user experience, but it also incentivizes more conscious Bitcoin wallet usage, which is a must for privacy. In the previous version of HiddenWallet I implemented a privacy oriented coin control, where I believe I provided a decent user experience, however that approach was just a compromise, what I really wanted to do is a fully visualized wallet.
这个想法已经在我脑海里盘亘了很久了，我也在例如零链（ZeroLink）的规范中等多个地方提到过它。因为它不仅仅提供了有趣的用户体验，而且还激励了比特币钱包更谨慎的使用，这是隐私的必要条件。在上一版本的隐藏钱包（HiddenWallet）我实现了一个隐私导向的投币控制，并相信我提供了一个体面的用户体验，但这个方法知识一个折中，我真正想做的是一个完全可视化的钱包。

###Traditional Wallet UX
###传统钱包用户体验
Think about how a Bitcoin wallet looks like today. Developers are using the most basic building blocks they have. Tabs, Menus, Lists and Tables. That’s all it is.
想一下目前的比特币钱包都长什么样子。开发人员都是使用最基本的构建模块。选项卡、菜单栏、列表和表格。嗯，这就是所有用到的。
![Alt text](./0403_0.png)

Image result for hiddenwallet
隐形钱包的图片

From another point of view, a Bitcoin wallet is an attempt to translate what’s happening on the blockchain towards the users. However, let’s think outside the box and ask the question: can we do it differently? And the answer is: definitely maybe.
从另一个角度来看，比特币钱包尝试做的是将区块链上发生的事情传达给用户。 然而，让我们跳出固有思维模式并思考这个问题：我们可以做得稍微不同吗？ 问题的答案是：绝对可能。

###Visualized Wallet UX
###可视化钱包用户体验
Imagine you open your wallet and you don’t meet with the usual tabs, lists and tables, but with a bunch of circles.
想象一下你打开钱包，但是你看到的不是常规的选项卡、列表和表格，而是一堆圆圈。
![Alt text](./0403_1.png)

Hmm? Does it remind you of something? Yes, it’s like opening your physical wallet, those bubbles are coins, these coins have values:
怎么样？它有没有让你想起某些事情呢？对的，这就像你打开你的实体钱包一样，这些圈圈代表硬币，分别对应不同的价格：
![Alt text](./0403_2.png)

However, unlike physical coins, these coins also have histories:
但是，与实体硬币不同的是，这些硬币是有历史记录的：
![Alt text](./0403_3.png)

Those rectangles are Bitcoin transactions and those coins are transaction outputs. You can also show what is not inside in your wallet:
而方形的框框代表比特币交易，这些硬币是交易的输出。你也可以有哪些输出是不在你的钱包里面：
![Alt text](./0403_4.png)

It’s much better if your wallet can do labeling so the data makes sense.
为了使数据显示有意义，如果钱包能做备注就最好啦。
![Alt text](./0403_5.png)

Confirmations? Unspent coins? There are so many ways to play with the colors, shapes, shadows, opacity, etc…
证明？未花费硬币？这些可以用诸如颜色、形状、阴影、不透明度等来表示。

If you click somewhere to generate a receive address.
如果点一下某处，你可以创建一个接收地址。
![Alt text](./0403_6.png)

Build a transaction by dragging coins from my wallet and dropping them into a basket:
可以通过把硬币从钱包里面拖出来，然后扔进篮子里来创建一个交易：
![Alt text](./0403_7.png)

Such user experience makes Bitcoin wallets more fun, more importantly it helps its users’ to make educated decisions whenever making a transaction, therefore improving their privacy.
这种用户体验能使比特币钱包更有趣，更重要的它可以帮助用户做交易的时候做出更明智的决定，因此提高了他们的隐私。

When I designed ZeroLink, this is what I meant by “Visualized Wallet User Experience.”
当我设计零链（ZeroLink）的时候，这就是我所说的“可视化用户使用体验”的意思。

While I don’t promise I will roll this out, right now, as I am reworking HiddenWallet (with Lucas) to be a privacy preserving light client (it is full block downloading SPV wallet today) I am putting down the building stones, so I will be able to roll this out.
然而至少到目前为止，我不能保证会推出这个，因为我正在（和 Lucas ）重新设计隐形钱包（HiddenWallet），使其能成为保护隐私的轻量级客户端（目前它已经是一个可下载的全结点轻钱包）。知道我把这些工作都完成后，我才会有机会推出这个可视化钱包。

At last I leave you with an NBitcoin code snippet, what I am working on right now. Here I modeled a circle in my picture, a coin, which I named SmartCoin, because there is already a Coin object in NBitcoin:
最后，给你展示一下我现在正在着手工作的，一个 NBitcoin 代码片段。 在这里，我模拟了照片中的一个圆圈（也就是一个硬币），我把它命名为 SmartCoin ，因为 NBitcoin 中已经有一个 Coin 对象：
![Alt text](./0403_8.png)
