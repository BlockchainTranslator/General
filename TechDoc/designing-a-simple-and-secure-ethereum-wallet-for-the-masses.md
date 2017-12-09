## Designing a simple and secure Ethereum wallet for the masses | 为大众设计一个简单而安全的以太坊钱包

(and why mnemonic seed phrases are a security hole)

（以及为什么短语助记词是一个安全漏洞）

> 本文翻译自：https://blog.propsproject.com/designing-a-simple-and-secure-ethereum-wallet-for-the-masses-15e2d6d4d652

> 推荐 ： @咕噜 BIHU.COM

> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator/EOS) [鱼](https://github.com/oscnet)

> 翻译时间：2017-12-9

> 本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。

Today, there are two extremes when it comes to holding cryptocurrencies. On one hand, there is the bank-like approach of Coinbase, which takes full custody of funds. While this has clear advantages in user experience, there are large regulatory barriers and liability concerns, and it flies in the face of Nick Szabo’s famous maxim, “[Trusted third parties are security holes](http://nakamotoinstitute.org/trusted-third-parties/)”.

目前，持有加密货币有两个极端方法。一种是放在象 Coinbase 这样的交易所，采用类似银行的方式，使资金将得到充分保管。虽然这种方式在用户体验上有明显优势，但存在较大的监管风险和责任问题，也违背了尼克·萨博的名言:“[受信任的第三方是安全漏洞](http://nakamotoinstitute.org/trusted-third-parties/)”。

The alternative is the opposite approach, giving users complete self-custody over their funds. Unfortunately, when you add millions of inexperienced mainstream users into the mix, this introduces an even larger security hole: user error.

相反，另一种方法是将资金交给用户完全自我管理。不幸的是，对于数百万无经验的主流用户，这种方法存在更大的安全漏洞：由于用户操作失误引起的安全问题。

![](https://cdn-images-1.medium.com/max/1600/1*PNVZpV3xZUefKf750qk43A.png)

If you’ve downloaded a mobile cryptocurrency wallet lately, you were probably asked to write down a 12 word mnemonic seed phrase like the above. This has become the gold standard in the industry, adopted by almost every wallet app. There’s just one issue: it’s setting users up for failure.

For starters, the timing is bad. You’ve just installed a shiny new app, you’re probably not at home, and you’re being asked to write something down and store it in a safe place. The odds that you actually do it are slim. More likely, you’re going to take a screenshot, write it down in a note or email it to yourself, without seriously considering who has access to these repositories.

如果你最近下载了一个移动加密货币钱包，它可能会要求你记下一个类似于上图这样的，12个字的助记词。这几乎已经成为业界的黄金标准，几乎所有钱包应用都采用这个标准。但是存在一个问题：将用户放置于失败的风险中。

对于初学者来说，时机往往不对。你刚刚安装了一个闪亮的新应用程序，有可能不在家，却被要求写下助记词，并将它存放在一个安全的地方。实际这样做的几率很渺茫。更有可能的是，您把这个屏幕截图下来，将它记在便条上或通过电子邮件发送给自己，而不会认真思考下这样做存在的风险：哪些人可以访问到这些内容。

Second, it’s a non-standard behavior. Of the millions of apps that users are accustomed to, none are asking you to write down secret phrases. Let’s be honest, it’s pretty strange, and you can’t blame users for not taking it seriously. Touch and Face ID have been training users towards faster, less complicated authentication. Seed phrases are a step in the wrong direction.

Finally, you’re being asked to write, in plain text, what essentially amounts to the keys of the kingdom. Even if you were to write a password down (which no one is dumb enough to do), an attacker would still need to know a) it’s a password and b) the username / service it belongs to. Seed phrases are instantly recognizable (12 random words from a predefined set), can easily be parsed out of your email / docs / photo library, and only require checking against a few services (Bitcoin, Ethereum, etc.).

其次，这不是标准方式。在用户已经习惯熟悉的数百万个应用程序中，没有哪个会要求你写下这类秘密短语。说实话，这显得很奇葩，所以我们不能单方面责怪用户没有认真对待、并正确处理。用户已经习惯了指纹和人脸识别等更快、更简单的认证。使用助记词显然是朝着错误的方向迈出了一步。

最后，你被要求记下这些英文短语，而这些短语助记词的重要性基本上相当于王国的钥匙。如果采用密码，即使你把密码写在某处（几乎没有人会愚蠢地这么做），黑客仍然需要知道 a）密码和 b）密码所属的用户名及提供服务的地址。但助记词短语可以立即识别出来（它只是从预先定义的集合中随机选择的12个单词），所以可以很容易地从电子邮件/文档/照片库中提取出来，而且只需要检查很少的几个服务（如比特币，以太坊等）。

As developers, we can do better. Putting custody in the hands of users may solve for liability, but it won’t solve for security or adoption.

So, what’s the answer? Returning to Szabo, the important thing to realize is that trusted third parties are the issue. A solution that incorporates trustless third parties has the potential to strike the right balance between security and usability. Ideally, it would have the following properties:

作为开发者，其实我们可以做得更好。将保管权交给用户，可能会减少我们要承担的责任，但并没有解决安全问题以及用户使用的问题。

那么，如何解决这个问题？回到尼克·萨博的名言，重要的是，要认识到问题在于可信任的第三方上。
通过在安全性和可用性之间取得适当的平衡，我们设计了一个包含不可靠第三方的解决方案。理想情况下，它将具有以下属性：

* If the user loses their device or forgets their password, the third party helps recover funds

* If the user is compromised, the third party helps to protect funds from the attacker

* If the third party is compromised or malicious, funds cannot be accessed


* 如果用户丢失设备或忘记密码，第三方能帮助用户取回资金

* 如果用户受到攻击，第三方可以帮助保护用户资金安全

* 即使第三方受到威胁、恶意访问或入侵，他们也不能使用用户资金

Importantly, the solution needs to assume that the user is inexperienced and accustomed to simple authentication methods, and should not encourage anti-patterns that risk security (e.g. writing down the private key in plain text). Here are a couple of potential examples:

重要的是，解决方案假定用户是没有经验的，且习惯于简单的身份验证方法，并且不应鼓励存在安全风险的反模式（例如以纯文本形式写下私钥）。这里有几个潜在的例子：

### Solution #1: Blockchain | 解决方案＃1：区块链

The perfect example of trustless third parties in action is a blockchain. You rely on other actors to provide service, but you don’t need to trust them. If you wanted to implement wallet recovery on Ethereum, it might look something like this:

事实上应用无信任的第三方的完美例子就是区块链。你依靠其他人来提供服务，但是你不需要信任他们。如果想在以太坊中实施钱包恢复，可能看起来是这样的：

* Funds are held in a proxy wallet, with two authorized keys (primary and secondary)

* The primary key can spend funds, while the secondary key can only request to be made into the primary key, subject to a 30 day waiting period

* If such a request is made, it must be made in plain sight, and monitoring services could alert the primary key holder, giving them a chance to cancel it and void the secondary key

* 资金存放在一个代理钱包中，有两个授权密钥（主钥匙和副钥匙）

* 主钥匙可以用来管理使用资金，而副钥匙只能请求成为主钥匙，但是需要等待30天以后

* 副钥匙请求成为主钥匙，必须明确提出要求，而监测服务机构可以提醒主钥匙持有人，让他们有机会取消请求并撤销次要钥匙


* When setting up an account, the wallet app would keep the primary key secure locally, and save the secondary key in your cloud storage (photos, gmail, iCloud, etc)

* The secondary key is easily accessible to you, in the case of emergency, and reasonably inaccessible to an attacker

* But even if an attacker did gain access, only the secondary key is discoverable, which still gives you a chance to prevent an attack

* 当创建一个帐户时，钱包应用程序安全地将主钥匙存放在本地，并将副钥匙保存在您的云存储上（照片，Gmail，iCloud等）

* 在紧急情况下，您可以轻松访问副钥匙，但攻击者无法合理访问

* 但是即使攻击者获得了访问权限，也只能发现副钥匙，这也给了你一个防止攻击的机会

While this is technically doable today, transaction fees and scalability means it’s probably some time before it makes sense to deploy in a production app aimed at millions of users.

虽然这个方案今天在技术上是可行的，但出于交易费用和可扩展性能考虑，可能还需要一段时间，才能在针对 数百万的用户中部署产品应用。

### Solution #2: Encrypted Backup Provider | 解决方案2：提供加密备份

When it comes to finding the right balance between security and usability, password managers have already made great progress. For example, 1Password’s use of “[2 Secret Key Derivation](https://1password.com/files/1Password%20for%20Teams%20White%20Paper.pdf)”, which combines the user’s weak password with a strong random key, means that the password vault backups stored on their servers are essentially uncrackable.

Borrowing some of the concepts from these apps, a wallet might use the following strategy:

当要在安全性和可用性之间找到适当的平衡时，密码管理方案已经取得了很大的进步。例如，1Password 使用“[双密钥导出](https://1password.com/files/1Password%20for%20Teams%20White%20Paper.pdf))”，将用户的弱密码与强大的随机密钥相结合，意味着存储在其服务器上的密码备份本质上是无法破解的。

借用这些应用程序的一些概念，钱包可能会使用以下策略：

* Store a backup of the user’s private key, that was encrypted locally on their device by a combination of their password and a random secret key

* Also store a second, “recovery backup” encrypted by the secret key alone

* The secret key is saved in the user’s iCloud KeyChain

* 存储用户私钥的备份，在其设备上使用密码和随机密钥的组合在本地加密该私钥

* 还要存储第二个“用于恢复的备份”，只用密钥加密

* 密钥保存在用户的 iCloud 钥匙串中


* If the user loses their device, they can request the primary backup and decrypt it with their password and the secret key from iCloud

* If they forget their password, they can still decrypt the recovery backup with the secret key, but the backup provider (which doesn’t trust the user) can enforce a 30 day waiting period, during which they send notifications and give the true owner a chance to cancel the request

* An attacker needs to compromise two of three factors (password, iCloud or backup provider), in order to access the private keys

* 如果用户丢失设备，他们可以请求主备份，并使用他们的密码和来自 iCloud 的密钥进行解密

* 如果他们忘记了密码，他们仍然可以使用密钥解密恢复备份，但备份提供者（即服务商，服务商不用信任用户）可以强制执行30天的等待期，在此期间，他们发送通知，并给真正的所有者一个机会来取消请求

* 攻击者需要搞定三个因素中的两个（密码、iCloud、备份提供者），才能访问私钥

Neither of these solutions protect against all possible scenarios, but they go a long way towards reducing the chances that a user loses access to their funds.

All in all, it’s important to note that seed phrases are not always a bad thing. For experienced users, they can be a convenient way to backup keys. Similarly, mobile custody is not a replacement for hardware wallets and more robust security solutions. However, the reality is that the majority of new users coming into the space will be technically inexperienced and using a mobile device. If we want to achieve mainstream adoption, these are the users we need to be designing for.

这些解决方案都不能在所有可能的情况下提供有效保护，但是它们大大减少了用户损失资金的机会。

总之，重要的是要注意，短语助记词并不总是一件坏事。对于有经验的用户，可以成为备份密钥的便捷方式。同样，移动托管也不是硬件钱包和更强大的安全解决方案的替代品。但实际情况是，多数新用户使用移动设备并且没有技术上的经验。如果我们想要实现主流应用，那么这些就是我们需要为之设计的用户。

This is exactly the approach we’ve been taking with the [PROPS](https://propsproject.com/) wallet, that will be introduced to YouNow’s community of millions of users in Q1 2018. Rather than burdening users with a complicated setup process, we’re using mix of solutions like encrypted backups and biometric authentication to design an experience that aims to strike right balance between security and usability. We look forward to releasing it soon, and continuing to work with the community to develop a set of best practices that makes holding cryptocurrency accessible to anyone.

这正是我们在 [PROPS](https://propsproject.com/) 钱包上所采用的方法，它将在2018年第一季度推出给 YouNow 社区的数百万用户。为了减少给用户带来负担的复杂设置过程，我们正在使用混合的解决方案，如加密备份和生物认证，从而设计出一个旨在安全和可用性之间取得平衡的产品。我们期待尽快发布，并继续与社区合作，开发出一套让任何人都可以使用加密货币的最佳实践方案。


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
