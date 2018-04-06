文章来自：A Case Study for Blockchain in Healthcare: “MedRec” prototype for electronic health records and medical research data

作者：Ariel Ekblaw, Asaph Azaria, John D. Halamka, MD, Andrew Lippman, MIT Media Lab, Beth Israel Deaconess Medical Center

译者：区块链中文字幕组 Chuan

时间：2018-04-06



#### Abstract

A long-standing focus on compliance has traditionally constrained development of fundamental design changes for Electronic Health Records (EHRs). We now face a critical need for such innovation, as personalization and data science prompt patients to engage in the details of their healthcare and restore agency over their medical data. In this paper, we propose MedRec: a novel, decentralized record management system to handle EHRs, using blockchain technology. Our system gives patients a comprehensive, immutable log and easy access to their medical information across providers and treatment sites. Leveraging unique blockchain properties, MedRec manages authentication, confidentiality, accountability and data sharing—crucial considerations when handling sensitive information. A modular design integrates with providers' existing, local data storage solutions, facilitating interoperability and making our system convenient and adaptable. We incentivize medical stakeholders (researchers, public health authorities, etc.) to participate in the network as blockchain “miners”. This provides them with access to aggregate, anonymized data as mining rewards, in return for sustaining and securing the network via Proof of Work. MedRec thus enables the emergence of data economics, supplying big data to empower researchers while engaging patients and providers in the choice to release metadata. The purpose of this paper is to expose, in preparation for field tests, a working prototype through which we analyze and discuss our approach and the potential for blockchain in health IT and research.

#### 摘要

长久对既有形式的遵循使得对电子病历的改变一直受限。MedRec，一个去中心化的、使用区块链技术的病历管理系统。这个系统提供给病人全面的、不可篡改的检查结果，并且可以通过各种医疗机构和治疗中心查看他们的诊断信息。利用区块链独特的特性，MedRec管理授权、保密、责任和数据共享 — 当处理敏感内容时，这些都是重要的考量因素。模块设计整合了医院现存的本地数据存储方案，促进协同操作，使系统便于使用并具有适应性。通过激励措施让医疗机构的股东（研究人员，公共健康权威人士等等）作为“矿工”参与到这个网络中。作为挖矿的奖励，这为他们提供了能够访问累积的、匿名的数据，用以换取他们用工作量证明来维持和保障网络的安全。MedRec让数据经济变得可能，把大数据提供给研究人员，同时使病人和各种医疗机构有提供元数据的选择。



#### Introduction 引言

EHRs were never designed to manage multi-institutional, life time medical records. Patients leave data scattered across various organizations as life events take them away from one provider's data silo and into another. In doing so they lose easy access to past data, as the provider, not the patient, generally retains primary stewardship (either through explicit legal means in over 21 states, or through default arrangements in the process of providing care) [1]. Through the HIPAA Privacy Rule, providers can take up to 60 days to respond (not necessarily to comply) to a request for updating or removing a record that was erroneously added [2]. Beyond the time delay, record maintenance can prove quite challenging to initiate as patients are rarely encouraged and seldom enabled to review their full record [1], [2]. Patients thus interact with records in a fractured manner that reflects the nature of how these records are managed.

电子病历从来都不是被设计用来管理多机构的病历记录。病人的看病记录分散在不同的机构中，当他们就医时，他们要从一所医院中获取数据，再导入另一所医院。他们也不太容易查看过去的看病记录，因为医院一般保留主要的管理权。因此，病人与自己的看病记录之间的联系是零零散散的，这也反应出这些病历被管理的本质。

Interoperability challenges between different provider and hospital systems pose additional barriers to effective data sharing. This lack of coordinated data management and exchange means health records are fragmented, rather than cohesive [3]. Patients and providers may face significant hurdles in initiating data retrieval and sharing due to economic incentives that encourage “health information blocking.” A recent ONC report details several examples on this topic, namely health IT developers interfering with the flow of data by charging exorbitant prices for data exchange interfaces [4].

不同的医疗机构和医院系统之间的协调操作问题对数据共享也产生进一步的阻碍。缺乏数据之间的合作和交换手段意味着看病记录是到处分散的，而不是统一的。

When designing new systems to overcome these barriers, we must prioritize patient agency. Patients benefit from a holistic, transparent picture of their medical history [3]. This proves crucial in establishing trust and continued participation in the medical system, as patients that doubt the confidentiality of their records may abstain from full, honest disclosures or even avoid treatment. In the age of online banking and social media, patients are increasingly willing, able and desirous of managing their data on the web and on the go [3]. However, proposed systems must also recognize that not all provider records can or should be made available to patients (i.e. provider psychotherapy notes, or physician intellectual property), and should remain flexible regarding such record-onboarding exceptions [5], [6].

为了克服这些障碍，新系统的设计中，我们必须优先考虑病人代理。病人能够从他们的看病记录获益。这个系统证明在医疗系统中建立信任和持续的参与是非常重要的，因为病人对检查结果的可信度的怀疑会阻碍他们真心提供这些数据。但是，我们这一系统必须认清，不是所有的医疗机构记录都能够或应该供病人所用，应该对一些例外情况保持灵活处理。

In this work, we explore a blockchain structure applied to EHRs. We build on this distributed ledger protocol originally associated with Bitcoin [8]. The blockchain uses public key cryptography to create an append-only, immutable, timestamped chain of content. Copies of the blockchain are distributed on each participating node in the network. The Proof of Work algorithm used to secure the content from tampering depends on a “trustless” model, where individual nodes must compete to solve computationally-intensive “puzzles” (hashing exercises) before the next block of content can be appended to the chain. These worker nodes are known as “miners,” and the work required of miners to append blocks ensures that it is difficult to rewrite history on the blockchain.

我们探索将区块链技术应用到电子病历管理中。区块链使用公钥密码来创建一个链，链上的内容是只能添加的、不可篡改的、并加上了时间戳。区块链的副本被分散到这个网络中的每个参与的节点上。工作量证明算法用来保证内容不被篡改，其中，在下一个内容块被添加到链上之前，每一个节点必须通过竞争来解决集中算力的谜题（哈希计算）。这些工作节点被称为“矿工”，要求矿工完成添加块的工作量确保很难在区块链上重写过去的数据。

Our MedRec blockchain implementation addresses the four major issues highlighted above: fragmented, slow access to medical data; system interoperability; patient agency; improved data quality and quantity for medical research. We build on the work of Zyskind et al. [9] to assemble references to data and encode these as hashed pointers onto a blockchain ledger. We then organize these references to explicitly create an accessible bread crumb trail for medical history, without storing raw medical data on the blockchain. Our system supplements these pointers with on-chain permissioning and data integrity logic, empowering individuals with record authenticity, auditability and data sharing. We build robust, modular APIs to integrate with existing provider databases for interoperability. A novel data-mining scheme is proposed to sustain the MedRec network and bring open, big data to medical researchers. We present MedRec not as the panacea for medical record management, but as a foray into this space to demonstrate innovative EHR solutions with blockchain technology.

MedRec区块链方案解决四个主要的问题：碎片化、查询病历的效率低下；系统的协同操作；病人代理；改进检查结果数据的质量和数量以供研究所用。在Zyskind等人工作的基础上，我们整理了对数据的引用，并将之编码为哈希指针放到区块链账簿上。然后，对这些引用进行整理，创建一个可用的的就医记录的导引软件，而无需把原始数据存储到区块链上。这一系统将这些指针补充上链许可和数据完整性逻辑，使得个人对数据具有权威、审核和分享的权利。我们创建健壮的、模块化的应用程序接口来整合现存的医疗机构数据库，改善协同操作。我们提出一个数据挖掘方案来维护MedRec网络，并将开放的、大量的数据提供给医疗研究人员。MedRec并不是病历管理的万能方法，而是对把区块链技术运用到电子病历管理解决方案的探索之举。


（续）
------

**区块链中文字幕组**

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号：w1791520555。

[点击查看 GITHUB 及更多的译文](https://github.com/BlockchainTranslator/EOS)

**本文译者介绍**

Chuan，区块链技术爱好者。欢迎加我的微信：youyuxiaochuan

译文版权所有，转载需完整注明以上内容。



