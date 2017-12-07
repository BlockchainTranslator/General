## Designing a simple and secure Ethereum wallet for the masses | 为大众设计一个简单而安全的以太坊钱包

(and why mnemonic seed phrases are a security hole)

（以及为什么助记种子短语是一个安全漏洞）

> 本文翻译自：https://blog.propsproject.com/designing-a-simple-and-secure-ethereum-wallet-for-the-masses-15e2d6d4d652

> 推荐 ： @咕噜 BIHU.COM

> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [鱼](https://github.com/oscnet)

> 翻译时间：2017-12-9

> 本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。

Today, there are two extremes when it comes to holding cryptocurrencies. On one hand, there is the bank-like approach of Coinbase, which takes full custody of funds. While this has clear advantages in user experience, there are large regulatory barriers and liability concerns, and it flies in the face of Nick Szabo’s famous maxim, “[Trusted third parties are security holes](http://nakamotoinstitute.org/trusted-third-parties/)”.

今天，持有加密货币有两个极端。一方面是Coinbase这种银行式的方式，充分保管资金。虽然这在用户体验上有明显的优势，但是监管壁垒和责任方面的问题还是很大的，而且在Nick Szabo着名的格言“ 受信任的第三方是安全漏洞 ” 方面却飞速发展。

The alternative is the opposite approach, giving users complete self-custody over their funds. Unfortunately, when you add millions of inexperienced mainstream users into the mix, this introduces an even larger security hole: user error.

另一种方法是相反的方法，给予用户完全的自我监管的资金。不幸的是，当您将数百万无经验的主流用户添加到混合中时，会引入更大的安全漏洞：用户错误。

![](https://cdn-images-1.medium.com/max/1600/1*PNVZpV3xZUefKf750qk43A.png)

If you’ve downloaded a mobile cryptocurrency wallet lately, you were probably asked to write down a 12 word mnemonic seed phrase like the above. This has become the gold standard in the industry, adopted by almost every wallet app. There’s just one issue: it’s setting users up for failure.

For starters, the timing is bad. You’ve just installed a shiny new app, you’re probably not at home, and you’re being asked to write something down and store it in a safe place. The odds that you actually do it are slim. More likely, you’re going to take a screenshot, write it down in a note or email it to yourself, without seriously considering who has access to these repositories.

如果你最近下载了一个移动加密货币钱包，你可能会被要求写上一个像上面这样的12个字的助记词。这已经成为业界的金标准，几乎每个钱包应用都采用这个标准。只有一个问题：设置用户失败。

对于初学者来说，时机不好。你刚刚安装了一个闪亮的新应用程序，你可能不在家，你被要求写下一些东西，并将其存储在一个安全的地方。你实际做的几率很渺茫。更可能的是，您将截取屏幕截图，将其记下来或通过电子邮件发送给自己，而不会认真考虑谁可以访问这些存储库。

Second, it’s a non-standard behavior. Of the millions of apps that users are accustomed to, none are asking you to write down secret phrases. Let’s be honest, it’s pretty strange, and you can’t blame users for not taking it seriously. Touch and Face ID have been training users towards faster, less complicated authentication. Seed phrases are a step in the wrong direction.

Finally, you’re being asked to write, in plain text, what essentially amounts to the keys of the kingdom. Even if you were to write a password down (which no one is dumb enough to do), an attacker would still need to know a) it’s a password and b) the username / service it belongs to. Seed phrases are instantly recognizable (12 random words from a predefined set), can easily be parsed out of your email / docs / photo library, and only require checking against a few services (Bitcoin, Ethereum, etc.).

其次，这是一个非标准的行为。在用户习惯的数百万个应用程序中，没有人要求您写下秘密短语。说实话，这很奇怪，你不能责怪用户不认真对待。触摸和脸部识别已经培养了用户更快，更简单的认证。种子短语是朝着错误的方向迈出的一步。

最后，你被要求用纯文字写出与王国的关键基本相同的东西。即使你写了一个密码（没有人愚蠢的做），攻击者仍然需要知道a）密码和b）它所属的用户名/服务。种子短语可以立即识别（从预定义的集合中随机选择12个字），可以很容易地从电子邮件/文档/照片库中解析出来，只需要检查一些服务（比特币，以太坊等）。

As developers, we can do better. Putting custody in the hands of users may solve for liability, but it won’t solve for security or adoption.

So, what’s the answer? Returning to Szabo, the important thing to realize is that trusted third parties are the issue. A solution that incorporates trustless third parties has the potential to strike the right balance between security and usability. Ideally, it would have the following properties:

作为开发者，我们可以做得更好。将保管权交给用户可能会解决责任，但不能解决安全问题或采纳问题。

那么，答案是什么？回到Szabo，要认识到的重要一点是可信任的第三方是问题。包含不可靠第三方的解决方案有可能在安全性和可用性之间取得适当的平衡。理想情况下，它将具有以下属性：

* If the user loses their device or forgets their password, the third party helps recover funds

* If the user is compromised, the third party helps to protect funds from the attacker

* If the third party is compromised or malicious, funds cannot be accessed


* 如果用户丢失设备或忘记密码，第三方帮助回收资金

* 如果用户受到攻击，第三方可以帮助保护攻击者的资金

* 如果第三方受到威胁或恶意，则不能访问资金

Importantly, the solution needs to assume that the user is inexperienced and accustomed to simple authentication methods, and should not encourage anti-patterns that risk security (e.g. writing down the private key in plain text). Here are a couple of potential examples:

重要的是，解决方案需要假定用户没有经验，并习惯于简单的身份验证方法，并且不应鼓励存在安全风险的反模式（例如以纯文本形式写私钥）。这里有几个潜在的例子：

### Solution #1: Blockchain | 解决方案＃1：区块链

The perfect example of trustless third parties in action is a blockchain. You rely on other actors to provide service, but you don’t need to trust them. If you wanted to implement wallet recovery on Ethereum, it might look something like this:

可靠的第三方在行动中的完美例子是区块链。你依靠其他角色来提供服务，但是你不需要相信他们。如果你想在以太坊实施钱包恢复，可能看起来像这样：

* Funds are held in a proxy wallet, with two authorized keys (primary and secondary)

* The primary key can spend funds, while the secondary key can only request to be made into the primary key, subject to a 30 day waiting period

* If such a request is made, it must be made in plain sight, and monitoring services could alert the primary key holder, giving them a chance to cancel it and void the secondary key

* 资金存放在一个代理钱包中，有两个授权密钥（主要和次要）

* 主钥匙可以花费资金，而副钥匙只能请求成为主钥匙，等待30天

* 如果提出这样的要求，则必须明确提出要求，而监测服务机构可以提醒主要持有人，让他们有机会取消并撤销次要钥匙


* When setting up an account, the wallet app would keep the primary key secure locally, and save the secondary key in your cloud storage (photos, gmail, iCloud, etc)

* The secondary key is easily accessible to you, in the case of emergency, and reasonably inaccessible to an attacker

* But even if an attacker did gain access, only the secondary key is discoverable, which still gives you a chance to prevent an attack

* 当设置一个帐户，钱包应用程序将保持主键在本地安全，并将辅助键保存在您的云存储（照片，Gmail，iCloud等）

* 在紧急情况下，您可以轻松访问辅助密钥，攻击者可以合理无法访问辅助密钥

* 但是即使攻击者获得了访问权限，也只有第二个关键是可以被发现的，这也给了你一个防止攻击的机会

While this is technically doable today, transaction fees and scalability means it’s probably some time before it makes sense to deploy in a production app aimed at millions of users.

虽然今天在技术上是可行的，但交易费用和可扩展性意味着，在面向数百万用户的产品应用中部署之前，可能还需要一段时间。

### Solution #2: Encrypted Backup Provider | 解决方案2：加密的备份提供程序

When it comes to finding the right balance between security and usability, password managers have already made great progress. For example, 1Password’s use of “[2 Secret Key Derivation](https://1password.com/files/1Password%20for%20Teams%20White%20Paper.pdf)”, which combines the user’s weak password with a strong random key, means that the password vault backups stored on their servers are essentially uncrackable.

Borrowing some of the concepts from these apps, a wallet might use the following strategy:

当要在安全性和可用性之间找到适当的平衡时，密码管理员已经取得了很大的进步。例如，1Password使用“ 2 Secret Key Derivation ”，将用户的弱密码与强大的随机密钥相结合，意味着存储在其服务器上的密码保险箱备份本质上是无法破解的。

借用这些应用程序的一些概念，钱包可能会使用以下策略：

* Store a backup of the user’s private key, that was encrypted locally on their device by a combination of their password and a random secret key

* Also store a second, “recovery backup” encrypted by the secret key alone

* The secret key is saved in the user’s iCloud KeyChain

* 存储用户私钥的备份，该私钥在其设备上通过密码和随机密钥的组合在本地加密

* 还要存储第二个“恢复备份”，只用密钥加密

* 密钥保存在用户的iCloud KeyChain中


* If the user loses their device, they can request the primary backup and decrypt it with their password and the secret key from iCloud

* If they forget their password, they can still decrypt the recovery backup with the secret key, but the backup provider (which doesn’t trust the user) can enforce a 30 day waiting period, during which they send notifications and give the true owner a chance to cancel the request

* An attacker needs to compromise two of three factors (password, iCloud or backup provider), in order to access the private keys

* 如果用户丢失设备，他们可以请求主备份，并使用他们的密码和来自iCloud的密钥进行解密

* 如果他们忘记了密码，他们仍然可以使用密钥解密恢复备份，但备份提供者（不信任用户）可以强制执行30天的等待期，在此期间，他们发送通知并给真正的所有者一个有机会取消请求

* 攻击者需要妥协三个因素中的两个（密码，iCloud或备份提供程序），才能访问私钥

Neither of these solutions protect against all possible scenarios, but they go a long way towards reducing the chances that a user loses access to their funds.

All in all, it’s important to note that seed phrases are not always a bad thing. For experienced users, they can be a convenient way to backup keys. Similarly, mobile custody is not a replacement for hardware wallets and more robust security solutions. However, the reality is that the majority of new users coming into the space will be technically inexperienced and using a mobile device. If we want to achieve mainstream adoption, these are the users we need to be designing for.

这些解决方案都不能保护所有可能的情况，但是它们大大减少了用户失去使用资金的机会。

总之，重要的是要注意，种子短语并不总是一件坏事。对于有经验的用户，他们可以成为备份密钥的便捷方式。同样，移动托管不是硬件钱包和更强大的安全解决方案的替代品。但实际情况是，进入太空的大多数新用户在技术上并不经验，并且使用移动设备。如果我们想要实现主流采用，那么这些就是我们需要为之设计的用户。

This is exactly the approach we’ve been taking with the [PROPS](https://propsproject.com/) wallet, that will be introduced to YouNow’s community of millions of users in Q1 2018. Rather than burdening users with a complicated setup process, we’re using mix of solutions like encrypted backups and biometric authentication to design an experience that aims to strike right balance between security and usability. We look forward to releasing it soon, and continuing to work with the community to develop a set of best practices that makes holding cryptocurrency accessible to anyone.

这正是我们用PROPS钱包所采用的方法，将在2018年第一季度推出到YouNow社区的数百万用户。而不是用复杂的设置过程给用户带来负担，我们正在使用混合的解决方案，如加密备份和生物认证来设计一个旨在在安全和可用性之间取得平衡的经验。我们期待尽快发布，并继续与社区合作，制定一套最佳实践，让任何人都可以访问加密货币。


----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

鱼 区块链技术爱好者，欢迎加微信号`oscnet`交流。

本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。

版权所有，转载需完整注明以上内容。

----------------------------------------------------
