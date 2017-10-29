https://medium.com/dfinity/a-first-look-at-dfinit-ys-testnet-october-2017-8a94737bbc4
视频字幕翻译

By Haoshi Hu, Xuming Meng

Welcome DFINITY fans and thank you for watching. Today I've got a real treat for you.
欢迎 DFINITY 粉丝们，感谢您的关注。今天我要给你一个福利。

I'm gonna give you a peek at the DFINITY test network that we use to play with our blockchain computer technology.
我会给你们看看我们利用 DFINITY 测试网络来测试我们的区块链计算机技术。

This applies new cryptography to create a public blockchain that is extraordinarily fast and more secure than anything around today.
利用新的加密技术来创建一个非常快速并且币当今任何机器都安全的公共区块链。

This is of course the foundation for the DFINITY -- World Computer.
这当然是 DFINITY 的基础 - 世界电脑。

This is a virtual computer that's created by an open network that can increase its capacity on demand that we hope will host much of the world's business logic and data.
这是一个由开放网络创建的虚拟计算机，可以根据需求增加其容量，我们希望它能够承载世界各地的商业逻辑和数据。

The DFINITY computer is unstoppable and tamper-proof and makes it possible to create business systems that are much more secure, much more reliable, and highly interoperable, all at a fraction of the cost.
DFINITY 计算机是不可停止和防篡改的，并且可以创建更安全，更可靠和高度互操作的商业系统，所有这些都是花费一小部分的成本。

DFINITY will also host general Dapps, decentralized finance, decentralized social media systems and large scale open source businesses that compete with traditional intermediaries such as uber and eBay.
DFINITY 还将托管一般的去中心化应用，去中心化金融，去中心化社交媒体系统以及与传统中介机构（如uber和eBay）竞争的大型开源企业。

This is the future cloud, with these thoughts in mind， let's get started.
这是未来的云，让我们带着这些想法开始吧。

So, here we are, this is the Definity test network.
所以，我们到了，这就是 DFINITY 测试网络。

I'll cycle through the panels quickly to give you a quick overview.
我将快速通过面板来给你一个简要概述。

Network shows the nodes in the network that are collaborating to create the virtual computer.
网络显示正在协作创建虚拟计算机的网络中的节点。

There are 500 of them, they're just distributed around the worlds and places like Singapore and London.
这里有 500 个节点，分布在世界各地，如新加坡和伦敦。

Currently we're using Amazon spot instances to keep the costs down.
目前，我们正在使用 Amazon 竞价型实例来降低成本。

The recent blocks are, as you'd imagine the blocks being produced by the network, they're coming out at a furious rate.
最近区块是，正如你想象的那样，网络生产的这些区块，他们以惊人的速度被生产出来。

Test network exceeded two and a half million blocks this time.
测试网络已经超过了二百五十万块。

Random beacon is the random number being produced by the current group that is used to select the next group and is also used to drive all of the protocols we use.
随机数灯塔是由用于选择下一组的当前组产生的随机数，也用于驱动我们使用的所有协议。

So there is the single threshold relay that has to be fundamental to all of the DFINITY protocols and it produces the world's first unstoppable, unmanipulable, unpredictable randomness without any trusted parties.
所以这里有一个单阀值接力机制是所有 DFINITY 协议的基础，在没有任何信任方的情况下，它产生世界上第一个不可停止的，不可预测的，无法预测的随机性。

And we use this very special sequence of random numbers to drive all of our protocols, so you could really say that， you know，DFINITY involves lots of theories about how random numbers are applied.
我们使用这个非常特殊的随机数序列驱动我们所有的协议，所以你可以真的说，你知道，DFINITY 涉及很多关于如何应用随机数的理论。

Block Heights gives you the current block height and the time taken to create the current block.
区块高度为您提供当前区块高度和创建当前区块所需的时间。

Latency chart, you know, graphs that out, so you can see that blocks are coming out every half second on this test network.
延迟图表，你知道，把时间图像化，所以你可以看到，这个测试网络每隔0.5秒出块一次。

Now this is the where it gets really interesting, so DFINITY in normal operation produces finality in two blocks.
现在这是它变得非常有趣的地方， DFINITY 在正常操作中会在两个区块以内的确定最终共识。

Okay so that means we're reaching finality, you know, new computations are finalized in one second.
好的，所以这意味着我们要到达最终共识，你知道，新的计算在一秒钟内完成。

Now to put that in the perspective, Bitcoin requires six blocks and the block time is ten minutes, so an expectation is it finalizes transactions in 60 minutes, can take a bit longer can take less.
现在从这个角度来说，比特币需要6个区块确认，出块时间是 10 分钟，所以预期是在 60 分钟内完成交易，可能花费更长或者更短的时间。

Ethereum requires 737 blocks in a block times about 15 seconds so that works out in 10 minutes or 600 seconds to finalise computations.
以太网需要 737 个块，出块时间约为 15 秒，所以需要 10 分钟或 600 秒来完成，来完成当前的计算。

That is when, you know, say for example, you're running a financial exchange on Ethereum and you submitted an order and you know you think it's executed you've gotta wait 10 minutes before you can be sure sure the network has reorganized and that trade has really gone through.
那就是说，你知道的，比方说，你在以太网上处理一笔金融交易，你提交了一个订单，你知道，你认为这是它已经被执行，但是你必须等待 10 分钟才能确定网络已经重组，那笔交易真的完成了。

On DFINITY we're producing finality in a second on this test network, we will do tune it for the production network but you know this is running 600 times faster than Ethereum today.
在 DFINITY，我们将在这个测试网络上可以在一秒钟内产生最终共识，我们会对生产网络进行调整优化，但是您知道这个速度比 Ethereum 快了 600 倍。

so let's get back to the network and some of really exciting things about that.
所以让我们回到网络和一些真正令人兴奋的事情。

The green dots show you the current group that is collaborating to produce the current block and also select create a random number that selects the next group.
绿色点显示正在协作生成当前区块的当前组，并选择创建一个选择下一个组的随机数。

The fat green dot is the individual node in fact acted as a leader and proposed a block has been accepted by the group which is then notarized it.
大一些的绿点是单个节点，事实上是作为领导者，并且提出了一个组织接受并且被公认的区块。

So let's click on one of these, (whoops~) the track click on these coming out so fast (whoops).
所以，让我们点击其中的一个，（哎哟〜）的轨迹点击这些出来这么快（哎哟）。

Here we go, okay so you click on one of these blocks flying past, and let's go through the fields.
我们到这里，好吧，你点击其中一个飞快划过区块，让我们浏览这些区域。

Block height needs no explanation, the test networks produced just over two and a half million blocks.
区块高度不需要解释，测试网络刚生产了两百五十万块。

Beacon that's the random number produced by the previous group that selected the current group and placed a priority order on all the nodes in the network that might want to be the leader and propose a block.
随机数灯塔是由选出当前组的前一组产生的随机数，前一组对网络中所有想成为领导者和建议区块的节点上进行优先级排序。

Notarization is a threshold signature created by the group on the block and notarization is essential to this thing called probabilistic slot consensus, it is a process by which we drive much faster consistency and also remove problems like selfish mining and nothing at stake.
公证是由集体创建的阀值签名，公证对于这个称为概率时隙共识的事情至关重要，这是我们驱动更快一致性的过程，也消除了诸如自私采矿和无利害关系的问题。

Timestamp needs no explanation, this just means that if you took all of the nodes in the network, ordered them lexicographically by the public keys, it was the node 194 that acted as the leader to produce the block that group 99 accepted and notarized.
时间戳不需要解释，这只是意味着如果你把网络中的所有节点按照公共密钥顺序排列，那么它由节点194作为领导者产生的并由编号99的组接受和公证的区块。

So we can look at the group members here, there's only a hundred members in each group and the reason for that is we only have 500 nodes in the network, it wouldn't make sense to run a larger groups, but in the production network group size will be 400.
所以我们可以看看这里的小组成员，每个组中只有一百个成员，其原因是我们在网络中只有500个节点，运行更大的组是没有意义的，但是在生产网络组的人数将达到400人。

ok let's flick across to contracts, firstly I just want to say that you can't ensure anything from from this test network about what the production DFINITY world computer will look like and what our IDE is gonna to look like.
好吧，让我们简单的介绍一下合约，首先我只想说，你不能确保在这个测试网络的任何东西，关于生产环境中的 FINITY 世界电脑将是什么样子，我们的IDE将要看起来像什么。

This this stuff's really just been created to allow our engineers to play around, having said that, you know, we've got a fully functional virtual machine and the smart contracts written in a cut-down version of the Haskell language. 
这个东西真的只是为了让我们的工程师能够实验测试，话说回来，我们已经有一个功能齐全的虚拟机，并且以精简版本 Haskell 语言的编写的智能合约。

In the production of DFINITY Network, we won't have simple smart contracts, we'll have actors and you'll be able to write these actors using any language you like, you know, we'll have Java like languages, solidity, and functional languages.
在生产环境下的 DFINITY 网络时，我们将不会有简单的智能合同，我们将有执行者，您将能够使用您喜欢的任何语言编写这些执行者，我们知道我们将拥有类Java语言，Solidity，和函数式语言。

okay so let's do something simple to begin.
好的，让我们做一些简单的开始。

There's a system contract called status now that records a status for every user interacting with a system.
现在有一个称为状态的系统合约，记录每个用户与系统交互的状态。

So the moment is just us.
所以这一刻就是我们。

let's go to the status contract.
我们去看一下状态合约。

you can see it's recording Dom was here as my status.
你可以看到它的记录 Dom 在这里作为我的状态。

Okay if you're interested in the code of that system contract, there it is.
好的，如果你对该系统合约的代码感兴趣，那就是。

You can see there's a write method you can use to set the status, this thing uses a thing -  we use a thing called capability based security and this is, you know, the status identifiers unsealed and this is how, you know, it's my particular status is set.
你可以看到有一个写方法可以用来设置状态，这个东西使用一个东西 - 我们使用一种称为基于能力的安全性的东西，这就是，你知道的，状态标识符未被密封，这就是，你知道，我的特定状态如何被设置。

Okay hey let's go back to the the state and let's change it, so I'm going to create transaction that does just that, so instead of hello world I'll say "this is a demo", I'm gonna press the deploy contract button, this isn't a contract though I'm pressing the deploy contract because it doesn't define any methods.
好的，让我们回到状态栏，让我们改变一下，所以我要创建这样的事务，我不说你好，我会说“这是一个演示”，我要按部署合约按钮，这不是一个合同，虽然我按下了部署合同，因为它没有定义任何方法。

it's just a transient transaction so now let's deploy that.
这只是一个暂时的事务，所以现在让我们来部署。

And you can see almost immediately the status in the system status contract has been updated. very cool.
您几乎可以立即看到系统状态合约中的状态已更新。 很酷。

Let's go and look at daemons contracts so you know the DFINITY philosophy is that, DFINITY may be based on blockchain technology and all kinds of other crazy cryptography, but you know developers don't really want to be involved or limited by the mash nations of complex network protocols. They just want a simple virtual computer, they can upload their software to and that will run as they expect.
我们来看看守护进程的合同，所以你知道 DFINITY 的理念是，DFINITY 可能是基于区块链技术和各种其他疯狂的密码学，但是你知道开发人员真的不希望受到复杂的网络协议的限制。 他们只想要一个简单的虚拟电脑，他们可以上传他们的软件，并将按照预期运行。

Now one of the things that developers often want to create -- long-running processes that we often call daemons.
现在，开发人员经常想要创建的事情之一 - 长时间运行的进程，我们经常称之为守护进程。

And this contract here implements a daemon, it will run until it's either run out of gas or in fact it produces its producing a series of numbers, Once it's reached the number (one) it stops so this thing's gonna run until it runs out of gas or it reaches the number (one).
而这个合同在这里实行了一个守护进程，它会运行，直到它用完了燃料，实际上它产生了一系列的数字。一旦达到数字（一），它停止，所以这个东西将运行，直到它耗尽燃料或达到数字（一）。

So let's deploy that. Okay so let's go up here and have a look at its status and you can see that it's continually updating this number and it's gonna continue doing that until it's run over gas or it reaches another one.
所以我们来部署。 好吧，让我们来看看它的状态，你可以看到它不断地更新这个数字，它会继续这样做，直到它运行在燃料或达到另一数字一。

Looks like it's running out of gas, so why don't I do this again with some more gas I was rather annoying, okay okay so this one.
看起来它已经用完了燃料，所以为什么我不再用一些更多的燃料来做这件事我很烦人的好吧，所以这一个。

oops now I gave this one a whole lot more gas so this process should continue running until it gets the number one and see it's still going, still going, still going, still going, still going, come on still. okay yay it's reached the number one and it's stopped.
哎呀，现在我给了这么多的气体，所以这个过程应该继续运行，直到它得到第一，看到它仍然在继续，仍然继续，仍然继续，仍然继续下去。好吧，它已经达到数字一，它已经停止了。

Okay last thing I want to show you: here's a contract that defines an interface that creates a Dapps that allows you to interact with other contracts, obviously this contract would be created by a WYSIWYG designer or something like that.
好的最后一件事我想告诉你：这里是一个定义一个接口的合约，它创建一个去中心化的应用，允许你与其他合同进行交互，显然这个合同将由所见即所得的设计者创建。

Anyways, Let's deploy this. Here we go.
无论如何，我们来部署这个。 我们到了。

Copy its address.
复制其地址

you can see, by the way in the contract status view　What the contract code produced.
在合约状态视图中可以看到的合同代码生产的结果。

and now we've copied the address，let's type that into the Dapps browser，and, boom there you go the Dapps has come straight off the computer system.
现在我们已经复制了地址，我们将其输入到去中心化浏览器中，并且在那里您可以直接从计算机系统中直接进入去中心化应用。

We think this is a great model, you know, people don't need to do this to create Dapps, but you know since the capacity of the DFINITY computer can increase with demand, we expect that people will want to use it to, you know, store complete applications and sorts of data.
我们认为这是一个很好的模式，你知道，人们不需要这样做来创建去中心化应用，但是你知道，由于 DFINITY 计算机的容量随着需求的增加而增加，我们预计人们会想要使用它 你知道的，存储完整的应用程序和各种数据。

Of course the great advantage of storing your complete Dapps in contracts is that it's tamper proof, you know, if you have a Dapps that's created using truffle or something like that and, you know, for a web server if an attacker gets takes control of that web server, you know, they might be able to do all kinds of naughty things with this system.
当然，将完整的去中心化应用存储在合约中的巨大优势在于防篡改，如果您使用 truffle 或类似的东西创建了一个去中心化应用，，而且如果攻击者掌握了 那个 Web 服务器，你知道，他们可能能够做这种系统的各种调皮的事情。

You know everything's tamper and the level of security is greatly increased. Okay that's it for me I hope you enjoyed this quick peek at the DFINITY test network all right. thanks. bye.
你知道一切都是篡改，安全级别大大增加。 好的，这对我来说，希望你喜欢这个快速浏览DFINITY测试网络，谢谢再见。

----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

抖抖，在读博士，专注区块链技术研究与行业分析，欢迎加微信号:jonas-meng
胡灏石，ING工程师，专注区块链技术研究与行业分析，欢迎加微信号:hu358869

本文由币乎社区（bihu.com）内容支持计划赞助。

版权所有，转载需完整注明以上内容。

----------------------------------------------------




































































































