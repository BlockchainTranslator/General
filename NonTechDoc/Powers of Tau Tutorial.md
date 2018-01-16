> 本文翻译自：https://github.com/ebfull/powersoftau/wiki
>
> 作者：ebfull
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator) [鱼](https://github.com/oscnet)
>
> 翻译时间：2018-1-16
>
> 本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。

# Powers of Tau Tutorial | “Tau 的力量”活动教程
So, you want to participate in the **Powers of Tau** ceremony? This is a guide that will walk you through the steps, but it's important to go over why the ceremony exists and what the threat model is _first_.

你想参与 **Tau 的力量** 活动吗？此文是引导你完成参与相关步骤的一个指导, 同时了解为什么需要这个活动，哪个风险模型是_首要_的等问题也是非常重要的。

* **Why does the ceremony exist?** I highly recommend reading our [blog post](https://z.cash.foundation/blog/powers-of-tau/) announcing the ceremony to understand the motivations. In short, zk-SNARKs are awesome, but the parameter setup for them is currently really expensive and risky. Powers of Tau is a ceremony which takes the most expensive parts of parameter setups and performs them in a single, gigantic, communal ceremony for the benefit of all. The result is that individual parameter setups are cheaper and more scalable.

* **为什么需要这么一个活动？** 我强烈建议阅读我们的[博客文章](https://z.cash.foundation/blog/powers-of-tau/)来理解活动的目的。简而言之,虽然 zk-SNARKs 非常棒, 但是目前它们的参数设置非常复杂并且存在失误的风险。Powers of Tau 是一个活动仪式, 为了所有人的便利，通过执行一个单一的, 巨大、公共的活动，取消了参数设置中最困难的部分。从而使单个参数设置更容易，并且更具伸缩性。

* **What is the threat model? How does the ceremony succeed?** The ceremony succeeds as long as one participant is successful in destroying some random information they used to participate. Thus, the threat model is an adversary capable of compromising every participant, or every participant being dishonest and colluding with each other. Ensuring a diversity in the approaches each participant takes is essential for reducing the ways in which an adversary could attempt to compromise each participant.

* **什么是风险模型？活动如何算成功？** 只要有一名参与者成功地破坏了他们曾经参与的一些随机信息，这个活动就成功了。因此，风险模型就是一个能够让每个参与者陷入风险的攻击者，或者每个参与者都是不诚实的，互相勾结。为了减少攻击者针对每个参与者的破坏方式，确保每个参与者采取不同的方法是至关重要的。

* **Who is allowed to participate?** Everybody is allowed to participate! We'll be running the ceremony until about February 2018, so that lots of people can contribute. Only one participant goes at a time, and sometimes the process requires several hours, so we need to carefully schedule people. Also, because we're trying to "finish" sometime in February, we'll prioritize reputable people if there are lots of requests to participate.
* **How do I participate?** The ceremony is currently coordinated by Sean Bowe. If you're comfortable, you can publicly request to participate on the [`zapps-wg` mailing list](https://lists.z.cash.foundation/mailman/listinfo/zapps-wg). You can also privately contact Sean (`sean@z.cash`) to request to participate.

* **那么哪些人可以参与？** 每个人都可以！我们活动将持续到2018年2月, 让更多的人参与。一次只能有一个参与者, 有时候这个过程需要几个小时, 所以我们需要仔细安排大家的时间表。另外, 因为我们正在努力争取在二月份的某个时候"完成"工作, 如果要求参与的人比较多, 我们将优先考虑那些信誉良好的参与者。
* **如何参与？** 活动目前由 Sean Bowe 协调。如果你感兴趣, 你可以在[zapps-wg  邮件列表](https://lists.z.cash.foundation/mailman/listinfo/zapps-wg) 上公开要求参与。也可以私下联系肖恩（sean@z.cash）请求参加。

## What's the process like? | 参与的步骤？
When it's your turn, you'll be sent a `challenge` file that's about 1.2 GB in size. You need to run a [program written in Rust](https://github.com/ebfull/powersoftau) on this `challenge` file. This program will randomly sample some information (called the toxic waste), perform a computation, and spit out a `response` file. Then, you have to upload the `response` file to us. We'll send instructions for that as well.

轮到你的时候, 你会收到一个大小为 1.2 GB 的 `challenge` 文件。你需要运行一个[用 Rust 编写的程序](https://github.com/ebfull/powersoftau)来使用这个 `challenge` 文件。这个程序将随机抽取一些信息(称为有毒废物) , 执行计算后输出一个 `response` 响应文件。然后, 你必须将这个 `response` 文件上传给我们。收到文件的同时我们也会发送此操作的指南给你。

The ceremony succeeds so long as at least one person's toxic waste is destroyed. Some participants might be convinced it's destroyed just by restarting their computer afterward. Others may want to go further:

只要至少有一个人的有毒废物被破坏, 活动就成功了。一些参与者可能相信，破坏这个信息仅仅通过重新启动他们的计算机就可以了。其他的人可能希望更进一步:

* You might want to destroy the computer afterward.
* You may want to use DVDs to form an air gap for communicating with the machine.
* You may want to use an auditable process for computing your `response` file which reduces the risk of the machine being backdoored.
* You may want to use someone else's code. As an example, check out devrandom's build process for the powersoftau code which uses an old version of the Rust compiler compiled from pure C.
* 你可能想在之后破坏电脑。
* 为了与机器进行通信你可能需要使用 dvd 来形成一个空隙
* 您可能需要使用一个可审计的流程对您的 `response` 文件进行运算，这样可以少机器被植有木马后门的风险。
* 你可能想用其它人的代码。举个例子, 检出(checkout) devrandom 的 powersoftau 代码的构建过程, 它使用了一个纯 C 编译的旧版本的 Rust 编译器。

Of course, you can just keep it simple too and just run the code and restart your computer after you've sent the `response` file, if you think your machine is not compromised. What's important is that there is diversity in the approaches people take, so that there are fewer ways an adversary could compromise everyone's contribution.

We ask that participants write an attestation afterwards describing what they did and any pertinent hashes of files or code involved. PGP signing and posting to the zapps-wg mailing list is preferred.

当然, 如果你认为你的机器没有受到威胁，你也可以简单的运行代码，然后发送 `response` 文件后重启动您的计算机。重要的是, 人们采取的方法是多样化的, 从而使攻击者破坏每个人的贡献的方法更少。

我们要求参与者事后写一份描述他们做了什么以及涉及的文件或代码的相关哈希证明，推荐使用 PGP 签名并在 zapps-wg 邮件列表上发表。

## How does the code work? | 代码是如何工作的？

Let's say that you've been sent the `challenge` file. The code is [on github](https://github.com/ebfull/powersoftau). Grab it, and put the `challenge` file in that directory.

假设你已经收到了 `challenge` 文件。程序代码存放在 [github](https://github.com/ebfull/powersoftau) 上，下载文件, 并把 `challenge` 文件存放在此下载目录中。

The code is written in Rust, so to compile it, you'll need a [Rust compiler](https://www.rust-lang.org). You can run this command inside the `powersoftau` directory once you have the compiler:

代码是用 Rust 编写的, 所以要编译它, 需要一个 [Rust 编译器](https://www.rust-lang.org/)。一旦有了编译器, 就可以在 `powersoftau` 目录中运行此命令:

```
cargo run --release --bin compute
```

This will start by asking you to supply some extra random information to improve the entropy of the secret randomness your machine samples. It will then perform a large computation that could take an hour or longer.

When the computation is finished, it will spit out a `response` file and it will print a hash of the `response` file.  This hash is very important: it's the only way you (or others) know that you participated in the ceremony. You're encouraged to post this hash publicly after you're done participating.

程序会首先要求您提供一些额外的随机信息，以提高你的电脑样本的私密随机性。然后它将会进行一个非常大的运算, 有可能需要一个小时或更长的时间。

当计算完成, 它会输出一个 `response` 响应文件, 以及响应文件的对应的哈希值。这个哈希值非常重要: 这是你(或其他人)证明你参加了活动的唯一方法。你最好在完成参与后公开发布这个哈希值。

You also need to upload the `response` file to us after you're done. The `response` and `challenge` files are not secret, so you are free to publish them, but we will host a mirror of what you upload.

At this point it's your job to make sure the toxic waste was destroyed from the machine. So, do whatever makes you feel comfortable!

你还需要在完成后将 `response` 响应文件上传给我们。`response` 和 `challenge` 件不是私密的, 所以你可以自由公布, 我们也将会备份保存你上传的文件。

在这一点上, 你的工作是确保破坏机器中有毒废物。所以, 做任何让你感觉舒服的事情吧！

### Dummy challenge file | 虚拟的 challenge 文件
If you want to test this process out with a dummy challenge file, you can run `cargo run --release --bin new` to create one. Just remember to delete the `challenge` and `response` files before you actually participate in the ceremony.

如果你想用一个虚拟的 challenge 文件来测试整个过程, 你可以运行`cargo run --release --bin new` 来新建一个。但是不要忘记在你真正参加活动之前删除 `challenge` and `response` 文件。

## When do I get a challenge file? | 我什么时侯能拿到 challenge 文件
We'll need to schedule you in. One way to do this is to post to our [mailing list](https://lists.z.cash.foundation/pipermail/zapps-wg/) and ask to participate. Give some rough estimate of when you can participate. If you're uncomfortable doing this, you can also privately ask to participate: shoot an email to `sean@z.cash` and ask for a time slot.

Once it's your turn, you'll be sent a `challenge` file and a way to upload the `response` file when you're done.

我们会为你安排时间。一种方法是发送到我们的[邮件列表](https://lists.z.cash.foundation/pipermail/zapps-wg/)并要求参与。
填上你大概估计能参与的时间。如果你不愿意这样做, 你也可以私下要求参与: 给 `sean@z.cash` 发一封电子邮件, 附加一个要求参与的时间段。

当轮到你的时候, 你就会收到一个 `challenge` 文件和一个在完成后上传 `response` 传响应文件的方法。

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
