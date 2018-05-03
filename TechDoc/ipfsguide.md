文章来自：https://hackernoon.com/a-beginners-guide-to-ipfs-20673fedd3f

作者：Addaquay



## IPFS新手指南



The Interplanetary File System (IPFS) is a peer-to-peer (p2p) filesharing system that aims to fundamentally change the way information is distributed across & beyond the globe. IPFS consists of several innovations in communication protocols and distributed systems that have been combined to produce a file system like no other. So to understand the full breadth and depth of what IPFS is trying to achieve, it’s important to understand the tech breakthroughs that make it possible.

星际文件系统IPFS是点对点的文件共享系统，它的目的在于从根本上改变信息分发的方式。IPFS由几个在通信协议和分布式系统方面的重要创新所组成。为了能够全方面地理解IPFS，重要的是要搞清楚它背后的一些技术突破。

### **Communication Protocols & Distributed Systems** 通信协议&分布式系统

For two people to exchange information, they need common sets of rules that define how & when information is transmitted. These rules are broadly known as communication protocols, but that’s quite a mouthful so we simply call it language. If you’ve ever been to a foreign country where you don’t speak the native tongue, you’ve probably experience a failure (or lack) of communication protocols. This was the case with computers; they were unable to communicate with each other and existed as isolated computational devices until the early 1980’s when the first communication protocols for computing were invented.

对两个交换信息的人来说，他们需要共同的规则来确定如何以及何时传送信息。这些规则广义上被称为通信协议，但是，那个太拗口，所以，我们就简单地称它为语言。如果你曾去过国外，在那里你不能讲自己的母语，那么你大概会遭遇到无法沟通的情况。对电脑来说就存在这种情况：它们不能相互通信，孤立地存在着，直到20世纪80年代发明了第一代计算通信协议。

> *“protocols are to communication what programming languages are to computations”*

协议就是通信，就如同编程语言就是运算。

In computers, communication protocols usually exist in bundles (called a protocol suite) of several layers. For example, the [Internet protocol](https://en.wikipedia.org/wiki/Internet_Protocol) suite consists of 4 layers, each of which is responsible for specific functions. In addition to communication protocols, an important relationship to understand is the basic structure of the interconnections between the computers. This is known as the [system architecture](https://en.wikipedia.org/wiki/Distributed_computing). Several exist, but the two types relevant to us are **client-server** and **peer-to-peer networks**.

在计算机方面，通信协议通常存在于许多层的软件包（称为协议套件）中。例如，互联网协议套件由4层组成，每一层负责具体的功能。除了通信协议，理解重要关系就是电脑之间的相互连接的基本结构。这称被为系统架构。有好几种，但是跟我们相关的两个就是客户端－服务器和点对点网络。

The internet is dominated by client-server relationships, which rely on the Internet Protocol suite. Of these, Hypertext Transfer Protocol ([HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol)) is the basis for communication.

互联网是由客户端－服务器的关系构成的，这依赖于互联网协议套件。其中，超文本传输协议HTTP是通信的基础。

Data is stored in centralized servers and accessed by location-based addressing. This makes it easier to distribute, manage, secure the data, and to scale the capacity of both servers and clients. However there are many weaknesses in the realms of security, privacy and efficiency: control of the server translates to control of the data. This means your data can be accessed, altered and removed by any party with control of the server; this could be an entity with legitimate authority over the server or a malicious hacker. In location-based addressing, data is identified by where it is located rather its content. This limitation means you have to go to all the way to specific location to access a piece of data, even if that same data is available somewhere closer. There is also no way of telling if the data has been altered, since the client only needs to know where it is, not what it is.

数据被存储在中心服务器上，通过基于地点的寻址来访问。这就很容易做到对数据进行分发和管理并保证其安全，以及对服务器和客户端的性能进行扩容。可是，在安全、隐私和效率方面，这种方式存在许多缺点：控制服务器就变成了控制数据。这意味着数据能够被任何控制服务器的人访问、修改和删除；这可能是进行服务器的审查部门或者居心不良的黑客。在基于地点的寻址方面，数据通过它所在的位置而不是其内容来进行识别。这种局限性表明你得到指定的地点来访问数据，即使这个数据可能存在于某个更近的地点。也没有任何方法来识别数据是否被修改，因为客户端只需要知道它在哪儿，而不是要知道它的内容。

But the client-server model and HTTP have served the internet pretty reliably for most of its history. This is because the HTTP web is highly effective for moving around small files like text and images. In the first two decades of the web, the size of the average web page has only increased from ~2 kilobytes to ~2 megabytes.

但是客户端－服务器模型和超文本传输协议那么多年来让互联网非常可靠地运行。这是因为超文本传输协议对于传递如文本和图片这样的小文件来说非常高效。在互联网发展的前20年，网页大小平均只从2K字节增加到2M字节。

HTTP is great for loading websites but it wasn’t designed for the transfer of large amounts data (like audio and video files). These constraints possibly enabled the emergence and mainstream success of alternative filesharing systems like Napster (music) and BitTorrent (movies and pretty much anything).

超文本传输协议很适合于加载网站内容，但是它不是设计用来传输大容量数据（比如音频和视频）。这些限制可能使得如 Napster 和 BitTorrent 这样的文件共享系统出现并获得大范围的使用。

Fast forward to 2018, where on-demand HD video streaming and big data are becoming ubiquitous; we are continuing the upward march of producing/consuming more and more data, along with developing more and more powerful computers to process them. Major advancements in cloud computing have helped sustain this transition, however the fundamental infrastructure for distributing all this data has remained largely the same.

快速来到2018年，按需服务的高清视频流和大数据变得无处不在；我们持续地在产生/消耗越来越多的数据，并制造越来越强的电脑来处理这些数据。云计算的发展帮助维持这种过渡期，可是分发这些数据的基本结构很大程度上仍旧维持原样。

### **The InterPlanetary File System 星际文件系统**

IPFS attempts to address the deficiencies of the client-server model and HTTP web through a novel p2p file sharing system. This system is a synthesis of several new and existing innovations. IPFS is an open-source project created by [Protocol Labs](https://protocol.ai/), an R&D lab for network protocols and former Y Combinator startup. Protocol Labs also develops complementary systems like [IPLD](https://ipld.io/) and [Filecoin](https://coincentral.com/filecoin-beginners-guide-largest-ever-ico/), which will be explained below. Hundreds of developers around the world contributed to the development of IPFS, so its orchestration has been a massive undertaking. Here are the main components:

IPFS试图通过P2P文件共享系统解决客户端－服务器模型和超文本传输协议的缺点。这个系统整合了新的和现有的技术。IPFS是Protocol Labs创建的开源项目。他们也开发了像IPLD和Filecoin这样的配套系统。全世界上百名开发人员促进了IPFS的发展，所以它的管理是个巨大任务。以下是它的主要组成部分：

**Distributed Hash Tables 分布式哈希表**

A [hash table](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/) is a data structure that stores information as key/value pairs. In distributed hash tables (DHT) the data is spread across a network of computers, and efficiently coordinated to enable efficient access and lookup between nodes.

哈希表这种数据结构存储如“键/值”对的信息。使用分布式哈希表，数据被分布在连网的计算机上，并且被有效地协调来实现节点间的高效访问和查找。

The main advantages of DHTs are in decentralization, fault tolerance and scalability. Nodes do not require central coordination, the system can function reliably even when nodes fail or leave the network, and DHTs can scale to accommodate millions of nodes. Together these features result in a system that is generally more resilient than client-server structures.

分布式哈希表的主要优点是去中心化、容错性和可扩容性。节点不需要中心来协调，甚至当节点发生故障或者离开网络时，这个系统还是可以稳定地运转，而且分布式哈希表能够扩容来容纳上百万个节点。这些特征结合到一起产生了比客户端－服务器结构更加灵活的系统。

**Block Exchanges 区块交换**

The popular file sharing system Bittorrent is able to successfully coordinate the transfer of data between millions of nodes by relying on an innovative data exchange protocol, however it is limited to the torrent ecosystem. IPFS implements a generalized version of this protocol called BitSwap, which operates as a marketplace for any type of data. This marketplace is the basis for [Filecoin](https://filecoin.io/): a p2p storage marketplace built on IPFS.

广受欢迎的文件共享系统Bittorrent能够有效地协调上百万个节点之间的数据传递，通过一种创新的数据交换协议，可是它对于数据流生态系统来说还是存在局限的。IPFS实现了这一数据交换协议的普及版本BitSwap，它为任何一种类型的数据提供了流通的平台。这种方法成为FIlecoin技术的基础：一种建立在IPFS上的点对点存储平台。

**Merkle DAG 默克尔有向无环图**

A merkle DAG is a blend of a [Merkle Tree](https://hackernoon.com/merkle-trees-181cb4bc30b4) and a Directed Acyclic Graph ([DAG](https://en.wikipedia.org/wiki/Directed_acyclic_graph)). Merkle trees ensure that data blocks exchanged on p2p networks are correct, undamaged and unaltered. This verification is done by organizing data blocks using [cryptographic hash](https://simple.wikipedia.org/wiki/Cryptographic_hash_function) functions. This is simply a function that takes an input and calculates a unique alphanumeric string (hash) corresponding with that input. It is easy to check that an input will result in a given hash, but incredibly difficult to guess the input from a hash.

默克尔有向无环图混合了默克尔树和有向无环图DAG。默克尔树确保在网络上交换的数据块是正确的、没有被毁坏、没有被篡改。这个验证过程是通过使用加密哈希函数对数据区块进行组织完成的。它就是一个简单的函数；接受一个输入，进行计算，然后输出一个与输入对应的唯一字符串。很容易验证一个输入肯定会有一个哈希值，但是几乎不可能从一个哈希值猜到输入的是什么内容。

The individual blocks of data are called ‘leaf nodes’, which are hashed to form ‘non-leaf nodes’. These non leaf nodes can then be combined and hashed, until all the data blocks can be represent by a single root hash. Here’s an easier way to conceptualize it:

每个数据块称为“叶子节点”，它们被哈希计算生成“非叶子节点”。这些非叶子节点然后被两两结合并哈希计算，直到所有的数据块通过一个简单的根哈希来表示。

A DAG is a way to model topological sequences of information that have no cycles. A simple example of a DAG is a family tree. A merkle DAG is basically a data structure where hashes are used to reference data blocks and objects in a DAG. This creates several useful features: all content on IPFS can be uniquely identified, since each data block has a unique hash. Plus the data is tamper-resistant because to alter it would change the hash, as shown below:

DAG是一种对没有环路的信息拓扑序列进行建模的方法。一个简单DAG的例子就是家族树。默克尔DAG基本上是这样的数据结构：哈希值被用来指向DAG中的数据块和对象。这产生几个有用的特征：IPFS上的所有内容能够被唯一地识别，因为每个数据块拥有唯一的哈希值。另外，由于是防篡改的，因为改变数据就会哈希值发生变化。

The central tenet of IPFS is modeling all data on a generalized merkle DAG. The significance of this security feature is hard to overstate. 

IPFS的中心原则就是对广义默克尔DAG上的数据进行建模。这种安全性很难说是言过其实。

**Version Control Systems 版本控制系统**

Another powerful feature of the Merkle DAG structure is that it allows you to build a distributed version control system ([VCS](https://en.wikipedia.org/wiki/Distributed_version_control)). The most popular example of this is Github, which allows developers to easily collaborate on projects simultaneously. Files on Github are stored and versioned using a merkle DAG. It allows users to independently duplicate and edit multiple versions of a file, store these versions and later merge edits with the original file.

默克尔DAG结构的另一个强大特征是：它允许你搭建分布式版本控制系统(VCS)。现在最流行的就是Github，它允许开发人员在项目上同步进行协作。Github上的文件通过使用l默克尔DAG的结构来存储和版本控制。它允许用户独立地复制并且编辑多个版本的文件，存储它们，之后合并这些对原文件的编辑修改。

IPFS uses a similar model for data objects: as long as objects corresponding to the original data, and any new versions are accessible, the entire file history can be retrieved. Given that data blocks are stored locally across the network and can be cached indefinitely, this means that IPFS objects can be stored permanently.

IPFS使用相似的模型来处理数据对象：只要有对应于原始数据的对象，以及可以访问任何新的版本，整个的文件历史都能够被检索到。考虑到数据块被存储在本地以及能够无限地缓存，这意味着IPFS对象能够被永久地储存。

Additionally, IPFS does not rely on access to Internet protocols. Data can be distributed in [overlay networks](https://en.wikipedia.org/wiki/Overlay_network), which are simply networks built on another network. These features are notable, because they are core elements in for a censorship-resistant web. It could be a useful tool in promoting free speech to counter the prevalence of [internet censorship](http://www.visualcapitalist.com/internet-censorship-map/) around the world, but we should also be cognizant of the potential for abuse by bad actors.

此外，IPFS不依赖于互联网协议。数据能够分布在覆盖网络里，这是在其它网络上搭建的网络。这些特征很重要，因为它们是反审查网络的核心部分。它也非常有助于推动自由言论来抵制互联网审查的盛行，但是我们也应该意识到它可能被滥用的后果。

**Self-certifying File System 自证文件系统**

The last essential component of IPFS we’ll cover is the Self-certifying File System ([SFS](https://en.wikipedia.org/wiki/Self-certifying_File_System)). It is a distributed file system that doesn’t require special permissions for data exchange. It is “self-certifying” because data served to a client is authenticated by the file name (which which is signed by the server). The result? You can securely access remote content with the transparency of local storage.

IPFS最后一个重要部分是自证文件系统SFS。它是一种分布式文件系统，不需要特别的许可来进行数据交换。能够“自证”是因为给客户端提供的数据通过文件名来验证（由服务器进行签名）。这带来什么结果？你可以安全地访问远程内容就像对本地存储的操作一样。

IPFS builds on this concept to create the InterPlanetary Name Space (IPNS). It is an SFS that uses [public-key cryptography](https://medium.com/@vrypan/explaining-public-key-cryptography-to-non-geeks-f0994b3c2d5) to self-certify objects published by users of the network. We mentioned earlier that all objects on IPFS can be uniquely identified, but this also extends to nodes. Each node on the network has a set of public keys, private keys and a node ID which is the hash of its public key. Nodes can therefore use their private keys to ‘sign’ any data objects they publish, and the authenticity of this data can be verified using the sender’s public key.

IPFS利用这个概念创建了星际命名空间（IPNS）。它是一种自证文件系统，使用公钥加密来对网络上用户发布的内容进行自证。IPFS上的所有对象都可能被唯一地识别，对节点来说也是如此。网络上的每个节点有一组公钥，私钥和由公钥哈希表示的节点ID。因此，节点能够使用它们的私钥来对任何的数据对象进行“签名”，这个数据的真实性通过发送者的公钥来进行验证。



**So why is all this important? 为什么这一切很重要？**

IPFS provides high throughput, low latency, data distribution. It is also decentralized and secure. This opens up several interesting and exciting use cases. It can be used to deliver content to websites, globally store files with automatic versioning & backups, facilitate secure filesharing and encrypted communication.

IPFS提供高吞吐量，低延迟，数据分布。它也是去中心化的、安全的。这带来了一些有趣的、令人兴奋的使用场景。它可以用来提交内容到网站，使用自动的版本控制和备份来分布式地存储文件，实现安全的文件共享和加密通信。

Below are a few interesting projects being built on IPFS:以下是一些搭建在IPFS上的项目：

[Akasha](https://akasha.world/), *a Next-Generation social network* Akasha，下一代社交网络

[Balance3](https://www.balanc3.net/#/), *a triple-entry accounting platform* Balance3，3层审计平台

[BlockFreight](https://blockfreight.com/), *an open network for global freight* BlockFreight，全球货运开放网络

[Digix](https://digix.global/), *a platform for tokenizing physical gold* Digix，实体黄金通证化平台

[Infura](https://infura.io/), *an infrastructure provider for DApps* Infura，去中心化应用的基础设施提供商

[Livepeer](https://livepeer.org/), *a decentralized live-video streaming platform* Livepeer，去中心化实时流媒体平台

[Origin](https://www.originprotocol.com/en), *a peer-to-peer marketplace for the sharing economy* Origin，点对点的共享经济市场

[uPort](https://www.uport.me/), *a self-sovereign identity system* uPort，自主身份管理系统

IPFS is interoperable with smart contracts and blockchain data, so it can add reliable, low-cost storage capacity to the ethereum ecosystem. The attempt to make Ethereum blockchain data natively accessible on IPFS is a separate protocol known as [IPLD](https://ipld.io/) (InterPlanetary Linked Data).

IPFS内带智能合约功能和区块链数据，所以它能够为以太坊生态带来可靠的、低成本的存储性能。使以太坊区块链数据在IPFS本地进行访问可以通过来IPLD完成。

**Challenges 挑战**

Despite the impressive performance of IPFS, a few issues are yet to be fully resolved. Firstly, the content addressing on IPNS is currently not very user-friendly. Your typical IPNS link looks like this:

尽管IPFS这些令人惊叹的表现，仍旧有一些问题还没有完全解决。首先，IPNS上的内容寻址当前并不用户友好。IPNS的链接通常看起来是这样的：

*ipfs.io/ipns/QmeQe5FTgMs8PNspzTQ3LRz1iMhdq9K34TQnsCP2jqt8wV/*

These links can be shortened to simpler names using a Domain Name System (DNS), but this introduces an external point-of-failure for content distribution. The content can however be still accessible through the original IPNS address. Some users also report that IPNS can be slow at resolving domain names, with delays of up to a few seconds. It’s not clear exactly what the root of this issue is.

这样的链接可以被缩短成使用域名命名系统的名字，但是这对内容分发来说就带来了外部的故障点。可是，内容仍旧能够通过原始的IPNS地址来访问。一些用户也反映，IPNS使用域名命名系统可能会变慢。现在还不清楚这个问题的根源是什么。

*Update* : *On 03/26/2018, IPNS released an upgrade with an experimental feature to speed up publishing/resolving. Details available *[*here*](https://blog.ipfs.io/34-go-ipfs-0.4.14#ipns-improvements)

更新：2018年3月26日，IPNS发布了升级程序，来提升发布的速度。具体详细可以访问<https://blog.ipfs.io/34-go-ipfs-0.4.14#ipns-improvements>

On IPFS there is also little incentive for nodes to maintain long term backups of data on the network. Nodes can choose to clear cached data to save space, meaning theoretically files can end up ‘disappearing’ over time if there are no remaining nodes hosting the data. At current adoption levels this isn’t a significant issue but in the long term, backing up large amounts of data requires strong economic incentives.

在IPFS上，对节点来说，没有多少动力来长期地维护数据的备份。节点可以选择清除缓存数据来节省空间，这意味着，理论上，如果没有节点留下来存储数据，那么文件可能会随着时间最终而“消失”。当前，这个问题还不算严重，但是从长期来看，备份大容量数据需要强烈的经济手段的刺激。

**Getting Started 如何开始**

IPFS is a highly ambitious endeavor, and obviously the precise mechanics of how the system functions are far more complex than what has been described in this guide. You don’t have to be an expert to *use *IPFS, so if any of the advantages or use cases seem useful or appealing to you, download IPFS & get started [here](https://ipfs.io/docs/getting-started/). 

IPFS是一个极有野心的尝试，这一系统如何运转的精巧设计远远比上面所讲的内容复杂的多。如果你对其中的某些内容感兴趣，可以下载IPFS，[从这里开始学习](https://ipfs.io/docs/getting-started/)。

Using IPFS is quite remarkable and understanding the technical wizardry that makes it possible is even more exciting. If successful, IPFS and its complementary protocols could provide resilient infrastructure for the next generation of the web. The web that was promised to be distributed, secure, & transparent.

使用IPFS带来的结果是非常显著的，明白让它运行起来的科技魔力让人更加兴奋。如果成功的话，IPFS和它的配套协议能够为下一代互联网提供灵活的基础架构。这个网络将会是分布式的、安全的、透明的。

