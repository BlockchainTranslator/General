### 区块链对健康医疗行业能带来什么改变

文章来自：https://medium.com/s/welcome-to-blockchain/what-could-blockchain-do-for-healthcare-59c17245448e

作者：Nicky Woolf

译者：区块链中文字幕组 Chuan

时间：2018-04-05



Even the world’s best health systems are typically fragmented. “You have hospitals, community clinics, general practitioners, specialists, diagnostic clinics, and so on,” says Matt Jackson, who leads blockchain research at Canada’s Institute on Governance.

甚至世界上那些最好的医疗系统通常都是各自一隅，缺乏连接。在加拿大政府研究中心负责区块链研究的Matt Jackson说，“你们有医院，有社区诊所，还有普通的执业医生，专科医生，诊断诊所等等。“

There are many reasons you might want to give someone access to your medical data. Maybe you just moved to a new city and want to give your new doctor access to your medical history, or perhaps you want to nominate a healthcare proxy in case of emergency or have your prescription sent to your pharmacy.

有许多方面的原因使你可能要把你的就医记录提供给别人使用。你可能刚搬到一座新城市，打算让你的新医生可以查看你的病史，或者你想指定一个医疗代理人，以防紧急情况或者把你的处方发送给药房。

Some places, like the UK or Canada, have viable national systems for exchanging patient records, but those can be vulnerable to hackers.

一些地方，如英国或加拿大，拥有可行的国家层面的医疗系统来实现病历信息的交换，但是，那容易遭到黑客的攻击。

In the United States, healthcare comes from a patchwork of private companies, which means the handling of patient data is even more fragmented. John Halamka, chief information officer at Beth Israel Deaconess Medical Center in Boston, Massachusetts, told [*MIT Technology Review*](https://www.technologyreview.com/s/608821/who-will-build-the-health-care-blockchain/) last year that there are 26 different electronic medical records systems in his home city alone.

在美国，整个医疗体系来自于私人公司的东拼西凑，这意味着对病人数据的处理甚至更加零散。去年，波士顿Beth Israel Deaconess医疗中心的CIO John Halamka对 *MIT技术评论* 说，单单在他的家乡就有26个不同的电子病历系统。

In 2016, Halamka teamed up with a group of scientists at MIT to try to find a solution to the problem using blockchain. They published their [white paper](http://dci.mit.edu/assets/papers/eckblaw.pdf) on the subject in August 2016, laying out their proposal for a system that would help all those disparate databases exchange data — a project they called MedRec.

2016年，Halamka和MIT的科学家组队，试图通过区块链来寻找这一问题的解决方案。他们在2016年发布了这个项目的[白皮书](http://dci.mit.edu/assets/papers/eckblaw.pdf)，陈述了他们对这一系统的设想；这个系统会帮助所有分散的数据库交换数据。这个项目的名称叫作 MedRec。

Andy Lippman, a senior research scientist at MIT, co-authored the paper with Halamka. The system they outlined was to use Ethereum software — which, unlike bitcoin, can integrate and execute smart contracts — to build a private blockchain, linking healthcare providers together and allowing them to share their data.

Andy Lippman，MIT的高级研究员，和Halamka共同合作写了这份白皮书。这个系统的框架是使用以太坊平台来搭建私有区块链（不像比特币，以太坊可以把合约整合进区块链来自动执行。），将病历的提供方连接到一起，让他们共享他们的数据。

On this blockchain, each of these such instructions by a patient creates a specific smart contract on the blockchain that only the patient can cryptographically sign.

在这个区块链上，病人发出的任一条指令在区块链上产生一份特定的智能合约，这份合约只能由这个病人加密签名。

Security is one benefit: “Distribution makes the system more secure, because there isn’t a single place of attack or failure,” Lippman says.

安全是它的一个好处：Lippman说，“分布式让系统更加安全，因为不存在一个单一的攻击点或故障点。“

Medical providers run a program module on their computer to access the database, as instructed by the smart contracts, which are initiated by the patient.

病历提供者在自己的电脑上运行一个程序模块来访问这个数据库，按照智能合约的指令要求，合约内容由这个病人在一开始确定好。

That module does three core things: First, it allows the healthcare provider access to the data when the blockchain is instructed to give it. Second, it executes the patient’s instructions as and when needed, sending data to a pharmacy or a specialist for referral — assuming the patient gives their consent. Third, the module allocates computing resources to maintaining the blockchain.

这个模块做三件重要的事情：第一，当区块链被要求执行提供病历数据的指令时，它允许病历提供方可以访问这个数据。第二，按照需求以及当需要的时候，它执行病人的指令，把数据发送到药房或发给专家用作参考 - 假定这个病人同意这样做。第三，这个模块把算力分布出去来维持这个区块链的运行。



### **Taking Back Control**拿回控制权

People close to the blockchain space often like to contextualize it by dividing the internet into three distinct eras.

对区块链熟悉的人喜欢把区块链置于互联网发展的3个截然不同的时代中。

The first, Web 1.0, is characterized by openness, based on a global consensus as to the mechanism for webpages. “Everyone agrees as a community that we are going to use HTML,” Lippman says, “and your browser can display pages from all kinds of different people, as opposed to one company making webpages one way, another their way.” However, as the internet matured, companies like Facebook and Google monopolized some areas of information — search data, social data — separating them into jealously guarded silos and databases. This is known as Web 2.0.

第一代互联网（Web 1.0）的特征是开放。网页的实现形式基于全球所有人的共识。Lippman说，“每个人都认同，作为一个地球村，我们将使用HTML。你的浏览器能够显示来自各式各样的人制作的网页，而不是一个公司用这种方式制作，另一个用别的方式制作。“可是，当互联网渐渐发展，Facebook和Google这样的公司在某些信息方面拥有了垄断地位，比如搜索数据和社交数据，并将它们分离并存储到自身控制的数据库里。这是Web 2.0时代。

The era to come — Web 3.0, according to enthusiasts — will use blockchain technology to allow people to take back control of their personal information, returning the internet to its individualistic roots and breaking the database monopolies.

按照对Web 3.0时代这一概念支持的人来说，它将会使用区块链技术来让人们拿回他们个人信息的控制权，让互联网回到普罗大众手里，打破数据库的垄断。

“The nice thing about medical records is there is no Facebook for medical records yet,” Lippman says. “So maybe we can, in a timely way, do what were doing, which is a universal, open, noncommercial design — almost as if were designing a web and HTML for medical records.”

Lippman说，“在医疗记录方面，最好的事就是到目前还没有像Facebook这样巨无霸的存在。所以，也许我们可以用一种适时的方式做我们在做的事情；它是通用的、开放的、非商业的设计，几乎就像为病例设计网站和HTML。“

“Web 2.0 is when a central authority essentially tracks you, uses that data to help you — and also monetizes that data for themselves by essentially renting the algorithms that result from it to advertisers,” says Diego Espinosa, CEO of Linnia, a startup that is trying to build an ambitious health and lifestyle data-sharing platform on the Ethereum blockchain.

Linnia 的CEO Diego Espinosa 说，“Web 2.0 时代，中央政府基本上都会跟踪你，使用获得的数据来帮助你 - 也通过这些数据赚钱，通过把数据进行算法处理后卖给广告商。”Linnia是一家初创公司，正尝试在以太坊区块链上搭建一个医疗和生活方式的数据共享平台。

“All of the Web 2.0 giants do that; that’s their business model. So Web 3.0 is: Now we own our data, we have agency over it, and we need *permission* for others to see it,” Espinosa continues.

Espinosa补充说，“Web 2.0时代的所有巨头拥有数据；那是他们的商业模型。Web 3.0则是：我们拥有自己的数据，我们对它可以指定代理，别人要使用这些数据需要我们的许可。“

“The reason blockchain makes that possible is we can have decent data that can also be trusted. The blockchain is an immutable database and has other attributes, like being able to have digitally signed attestations about us. Those two things have the ability for individuals to keep their data — but also have that data be trusted by others.”

”区块链使得这称为可能的原因在于：我们能够拥有像样的数据，这些数据也能够被信任。区块链是一个不可篡改的数据库，并拥有一些其他的特点，比如，能够对我们的身份证明进行数字化的签名。对个人来说，这两个特性让他们有能力保存自己的数据，并且让这些数据被其他人信任。“



### **Selling Our Own Data**出售数据

“The most interesting feature of blockchain in the health sector is the ability of patients to own and control their own health information,” says Jackson, from Canada’s Institute on Governance.

加拿大的政府研究中心的Jackson说，“在健康医疗方面，区块链最有趣的地方在于：病人能够拥有并控制自己的病历信息。”

“If all this information was linked to an identity patients control, they could decide who gets to see what. Maybe a knee specialist doesn’t need access your sexual health history. Blockchain could allow for this level of personal control.”

“如果这些所有信息被连接到病人可以控制的身份标识，那么他们能够决定谁可以看到什么样的内容。也许膝盖方面的一个专家并不需要查看你的生殖健康历史。区块链可以实现这种对个人信息层级的控制。“

“Not to mention,” Jackson continues, “that patients could actually profit from their health and demographic data, with the option to sell it to health research studies or drug discovery.”

Jackson补充说，“更不用说，病人实际上能够从他们自己的健康数据和人口统计方面的数据赚钱，选择把它们卖给健康医疗研究或者药物测试。“

That possibility has occurred to Espinosa, too. Linnea, unlike MedRec, is a commercial company; while it started out as “a data protocol for longitudinal health,” it has since widened in the scope and scale of its ambition.

这种可能性对Espinosa也是存在的。和MedRec不一样，Linnia是一个商业公司；尽管它一开始只是用作病历数据的数据层协议，但是之后它拓宽了他们的目标范围和规模。

For Espinosa, Linnea has become an opportunity to come up with an entirely new way of approaching health — and life.

对Espinosa来说，Linnia变成了一个机会，它提供一种完全崭新方式来解决健康和生命方面的问题。

“The idea was that it has to start with tracking,” Espinosa says. “I’m not necessarily talking about all the ins and outs of data when you went to a hospital. I’m talking about your genome, your nutrition, your fitness data. Even what your mother’s pregnancy was like; when you were born; your parents’ genome. Your microbiome. All of these things are important to maximizing your health over long periods of time, and yet we don’t track them.”

Espinosa说，“这个想法是它必须从追踪用户的数据开始。当你去医院时，我没有必要讨论检查结果的前因后果。我会谈论你的基因组，你的营养状况，你的健康程度。甚至你妈妈怀孕时的情况；你什么时候出生的；你父母的基因组。你的生物医学。从长期来看，所有这些东西对你的健康程度最大化是重要的，可是我们不会追踪它们。“

That data would then be kept on the blockchain, with permission for its transfer given by the patient to a provider via the system, like with MedRec, with the bonus that it’s not just for healthcare providers — we could just as easily send our data to “an insurance company that wants to give you a reward,” Espinosa says.

这些检查结果然后被保存到区块链上，需要经过病人的同意经由像MedRec这样的系统把数据传送给供应方。Espinosa说，“这不仅对病历的提供方来说是福利，我们也能够很容易的把我们的病历数据发送给想给我们一份保障的保险公司。"

“The holy grail for that is we use all this tracking to fuel machine-learning models,” Espinosa continues. “And those models will identify robust patterns that say, ‘If you do this in your twenties, here’s the impact in your fifties, so you don’t want to do that.’ And that causality, once it really gets established in people’s minds, can help them make the right decisions. '"

Espinosa补充说，“我们对此追求的目标是：我们使用所有这些追踪数据来推进机器学习模型的效率。这些模型将识别出健壮可用的模式；这个模式可以这样解释：‘如果你二十岁时做这个，50岁时，后果就是这样，所以你不想那样做。‘而且由于这种因果关系，一旦它在人们的头脑中固定，就能帮助他们作出正确的决定。‘“

“If we own our data, we have agency over our data, then we also own our health,” Espinosa says. “And that’s a sea change.”

Espinoa说，“如果我们拥有自己的数据，我们对我们的数据有控制权，那么我们也就把握住了自己的健康。这样的改变带来的可能性无限宽广。“



------

**区块链中文字幕组**

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号：w1791520555。

[点击查看 GITHUB 及更多的译文](https://github.com/BlockchainTranslator/EOS)

**本文译者介绍**

Chuan，区块链技术爱好者。欢迎加我的微信：youyuxiaochuan

译文版权所有，转载需完整注明以上内容。



本文源自新闻媒体 Medium，如有侵权，请与译者联系删除。

