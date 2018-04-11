

> 文章节选自：https://viral.media.mit.edu/pub/medrec
>
> 作者：Ariel Ekblaw, Asaf Azaria
>
> 译者：区块链中文字幕组 Chuan
>
> 时间：2018-04-11



### MedRec: Medical Data Management on the Blockchain

### 区块链上的病历管理系统MedRec





#### 概述

Electronic  Medical Records (EMRs) crave innovation. Years of regulation have  stifled tech development in medical data management, while an array of  incompatible back-end systems and fragmented data trails limit patients'  ability to engage with their medical history. We demonstrate MedRec as a  solution tuned to the needs of patients, the treatment community, and  medical researchers. MedRec applies novel, blockchain smart contracts to  create a decentralized content-management system for your  healthcare  data, across providers. The MedRec authentication log governs medical  record access, while providing means for auditability and data sharing. A  modular design integrates with providers' existing, local data storage  solutions, enabling interoperability and making our system convenient  and adaptable. As a key feature of our work, we engage the medical  research community with an integral role in the protocol. Medical  researchers provide the "mining" necessary to secure and sustain the  authentication log on a private, Ethereum network, in return for  privacy-preserving, medical metadata in the form of "transaction fees."

电子病历渴望有根本性的改变。目前的管理系统和数据的凌乱使得病人对自己的就医记录无能为力。MedRec 作为一种解决方法来满足病人、诊疗中心、医学研究人员的需求。MedRec 使用区块链智能合约来创建一个面向医疗健康数据的去中心化的内容管理系统。在提供行为审计和数据共享的同时，通过身份验证日志对病历的访问进行管理。关键的一点是把医疗研究团体纳入进来，作为系统中不可或缺的一部分。医疗研究人员提供必要的“挖矿”来保证并维护私有的以太坊网络上的身份验证日志，来换取以“交易手续费”形式的带有隐私的医疗元数据。

#### From fragmented access to comprehensive access数据从碎片化到整体

Patients  interact with a staggering number of health care providers through the  course of their lives-- from pediatrician, to university physician,  dentist, employer health plan provider, specialists, and more. At each  stage, they leave data scattered across a particular jurisdiction's  system.  This leads to a fragmented data trail and decaying ease of access, as  providers often retain primary data stewardship.

每个人从出生到死亡，每个阶段的看病记录分散各处。同时，这些数据通常还被掌握在各种医疗机构的手上。

Our  MedRec prototype enables patients with one-stop-shop access to their  medical history across multiple providers: smart contracts on an  Ethereum blockchain  aggregate data pointers (references to medical records that are stored  elsewhere) into "patient-provider relationships." These contract data  structures are stored on the blockchain and associate references to  disparate medical data with ownership and viewership permissions and  record retrieval location. This provides an immutable data-lifecycle  log, enabling later auditing. We include a cryptographic hash of the  record in the smart contract to establish a baseline of the original  content and thus provide a check against content tampering. The raw  medical record content is never stored on the blockchain, but rather  kept securely in providers' existing data storage infrastructure.

MedRec 让病人一站式获取自己在各个医疗机构的看病历史：以太坊上的智能合约把数据指针（指向看病记录）汇集到“病人-医疗机构关系”中。这些合约的数据结构存储在区块链上，并把对分散各处的看病记录的引用与所有权、查看许可和病历检索地点关联起来。在智能合约中加入了看病记录的加密哈希来建立原始数据的基线，从而能够检查数据是否被篡改。原始的看病记录不会被存储在区块链上，而是被保存在医疗机构现有的数据存储设备上。

MedRFrom obscurity to clarityec  facilitates reviewing, sharing and posting of new records via a  flexible user interface, designed to reflect best-practices from the Blue Button health record competition.  We abstract away the blockchain technology to focus on usability for  the medical record use case. The interface includes a notifications  system to alert users when a new record has been posted on their behalf  or shared with them.

MedRec通过灵活的用户接口使新的看病记录的查看、共享和发布非常容易。我们去除区块链的抽象技术，来专注于病历的可用性。当一个新记录被以用户的名义发布时或者共享给他们时，这一接口还包括一个消息推送系统来向用户发出提醒。

#### From data rigidity to data sharing数据从严格管控到共享

Interoperability  challenges between different provider systems pose significant barriers  to effective data sharing. Patients face hurdles in authorizing data  exchange (with other consulting physicians or even family members) due  to the lack of a common interface or standard system that orchestrates record access across databases.  MedRec provides streamlined data sharing functionality by updating  viewership permissions on the relevant data pointers. With pointers to  patient data aggregated in smart contracts on the blockchain, we can  offer a single, common interface where patients chose when, and with  whom, they share their data.

不同医疗机构的管理系统之间的协同配合问题对数据的有效共享产生重要的阻碍。由于缺乏通用的接口或者标准系统来管理跨数据库的病历访问，病人在授权数据交换时面临着一些阻碍。MedRec 通过更新相关的数据指针的查看许可让数据共享变得流畅起来。通过指向区块链上的智能合约里汇集的病人数据的指针，我们能够提供单一的、通用的接口，病人可以选择什么时候以及和谁共享他们的数据。

#### From obscurity to clarity数据从混乱到清晰

Though some data trickles through to researchers from clinical studies,  surveys and teaching hospitals, we note a growing interest among  patients, care providers and regulatory bodies to responsibly share more  data, and thus enable better care for others.

研究人员缓慢地收集临床研究和调查方面的数据。由于病人、护理机构和监管部门越来越有兴趣来分享更多的数据，从而能够帮助其他人获得更好的治疗。

With  MedRec, we incentivize medical researchers and other healthcare  stakeholders to participate in the blockchain network as "miners". These researchers can now obtain greater clarity in their  investigations by earning census level, anonymized metadata in return  for contributing the computational resources that sustain the network.

通过 MedRec，对医疗研究人员还有医疗健康行业的利益相关方提供激励措施让他们参与到区块链网络“挖矿”。研究人员通过贡献维护网络正常运转的算力，来获得人口统计层面的、匿名的数据，从而能够对他们的研究调查获得更清晰的认识。

#### Designing for patient agency病人获得数据的代理权

Patients benefit from a holistic, transparent  view of their medical history. MedRec restores patient agency by empowering users with a focal point  for access and review of their medical history, and an easy mechanism  for sharing their data across medical jurisdictions. Patients can  authorize a new doctor to review their record and obtain a second  opinion. Furthermore, the  authorization log persists in the distributed network, providing crucial  back-up and restore functionality. Patients can leave and rejoin the  system multiple times, for arbitrary periods, and regain access to their  history by downloading the latest blockchain from the network.

设计这一系统的初衷就是让病人对他们的就医历史有更全面的、清晰的认识。MedRec 赋予病人拥有一个对他们就医历史数据的访问和查看的中心点，以及一个简单的机制来共享他们在不同医疗机构之间的数据。病人可以授权一个新医生查看他们的病历，获得对健康状况的其他诊断。此外，授权日志一直运行在分布式网络上，提供重要的备份和恢复功能。病人可以随时加入或离开这个系统，并且可以从网络上下载最新的区块链重新获得对他们看病记录的访问权。

#### 数据经济

The  MedRec mining model, where researchers earn metadata as a mining  incentive, enables the emergence of data economics by writing in the  research community from the very beginning.  Medical researchers mine in  the network while network beneficiaries (i.e. providers and patients)  release access to aggregate, anonymized medical data as transaction  "fees" that become mining rewards. Researchers can influence the  metadata rewards that providers release by selectively choosing which  transactions to mine and validate. Providers are then incentivized to  match what researchers are willing to accept, within the boundaries of  proper privacy preservation. Patients and providers can limit how much  of their data is included in the available mining bounties.

挖矿模型（研究人员获得元数据作为一种挖矿激励）使得数据经济成为可能。参与到网络中的病人和医疗机构把对汇总的、匿名的医疗数据提供出来作为交易费来对挖矿进行奖赏，同时，医疗研究人员在网络中挖矿。通过有选择地对哪些数据来进行挖矿和验证，研究人员可以影响医疗机构释放的奖赏。然后，在适当地保护隐私这一条件下，医疗机构被激励去匹配研究人员愿意接受什么样的数据。病人和医疗机构能够限制他们的多少数据被用于挖矿奖赏。

The "cost" to mine on MedRec will be  held constant across participants, thus equalizing access to data and  bringing in stakeholders outside of just academia and Big Pharma. We can  envision the broader "research" community on MedRec also including  public health organizations, the CDC, regulated healthcare NGOs,  insurance companies and other stakeholders in the healthcare industry.  Because the MedRec blockchain remains private, networks of providers can  decide on the proper process and qualifications for onboarding new  research entities into the system. This prevents rogue, unregulated  entities from joining the mining network.

在 MedRec 上挖矿的“成本”在参与者之中将保持不变，从而使得对数据有同等的访问权，并吸引学术界和大型制药公司外的利益相关方加入进来。可以预见到，MedRec 上将包括更广泛的研究团体，如：公共医疗机构，疾控中心，医疗健康非营利性组织，保险公司和医疗健康行业的其他利益相关方。由于 MedRec 区块链是私有链，所以医疗机构能够基于合适的手续和资格来决定把新的研究方加入到系统里。这可以防止恶意的、不受监管的机构加入到挖矿网络。



------

**区块链中文字幕组**

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号：w1791520555。

[点击查看 GITHUB 及更多的译文](https://github.com/BlockchainTranslator/EOS)

**本文译者介绍**

Chuan，区块链技术爱好者。欢迎加我的微信：youyuxiaochuan

译文版权所有，转载需完整注明以上内容。

如有侵权，请与译者联系删除。

