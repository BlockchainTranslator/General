> 文章来自：A Case Study for Blockchain in Healthcare: “MedRec” prototype for electronic health records and medical research data
>
> 作者：Ariel Ekblaw, Asaph Azaria, John D. Halamka, MD, Andrew Lippman, MIT Media Lab, Beth Israel Deaconess Medical Center
>
> 译者：区块链中文字幕组 Chuan
>
> 时间：2018-04-08



*MedRec，一个去中心化的、使用区块链技术的病历管理系统。这个系统提供给病人全面的、不可篡改的检查结果，并且可以通过各种医疗机构和治疗中心查看他们的诊断信息。利用区块链独特的特性，MedRec可以管理授权、对数据保密、实现数据共享。*



### Prototype Evaluation原型评估

MedRec gives patients an immutable log of their medical history, which is not only comprehensive, but also accessible and credible. This restores patient agency, as participants are now more fully informed of their medical history and any modifications to it. Through permission management on the blockchain, we enable patient-vetted data exchange between medical jurisdictions and an interoperable content management system for the physicians supervising these records. The blockchain ledger keeps an auditable history of medical interactions between patients and providers, likely relevant for regulators and payers (e.g. insurance) in the future. Below, we consider the security, privacy and interoperability implications of this project and discuss our in-situ deployment testing.

MedRec 为病人提供一个不可篡改的就医历史的记录。它不仅内容很全面，而且易于访问和可信。这恢复病人对个人健康数据的代理权，因为参与者现在能够更加全面了解他们的就医历史以及对它作出的修改。通过在区块链上的许可管理，我们使得医疗系统的管辖问题和医生管理病历的协同内容管理系统之间交换病人已审查的数据成为可能。区块链账簿保存一份病人和医疗机构之间看病记录的可审查的历史。下面从安全性、隐私和协同的意义来进行介绍。

First, on robustness and security: our blockchain implementation enjoys several key properties of decentralization. MedRec enjoys a strong failover model, relying on the many participating entities in the system to avoid a single point of failure. Medical records are stored locally in separate provider and patient databases; copies of authorization data are stored on each node in the network. Because both the raw medical data and global authorization log stay distributed, our system does not create a central target for content attack—a crucial consideration in an age of cyberattacks and data leaks. Though some blockchains experience robustness challenges from a scaling limit on the “block size” or storage capacity [12], these parameters can be modified to optimize for other performance requirements in a private blockchain network. Notably, MedRec does not claim to address the security of individual provider databases—this must still be managed properly by the local IT system admin. 

健壮性和安全性方面：我们的区块链实现方案利用了去中心化的几个关键特点。MedRec 拥有强大的故障切换模型，依赖这个系统中许多的参与方来避免单个故障点的产生。就医记录被存储在本地独立的医疗机构和病人数据库里；授权数据的备份被存储在网络的每个节点里。因为原始医疗数据和全局的授权日志保持分布式的特点，所以我们的系统并不会创建一个会遭到内容攻击的中心目标。尽管一些区块链承受来自于区块大小的扩容限制或者存储能力的健壮性挑战，但是这些因素可以被修改来为其他性能要求作出优化。值得注意的是，MedRec 并没有声称解决个体医疗机构数据库的安全，这必须仍然由本地IT系统管理员来处理。

Regarding privacy, use of blockchain technology introduces several limitations. The pseudonymous property of transactions currently allows for data forensics, or inferring patterns of treatment from frequency analysis. Without any disclosure of name or PII, one could infer that some entity has repeatedly interacted with another network entity through analysis of network traffic.One potential solution is to make the blockchain a “permissioned” structure, where only pre-approved, white-listed nodes are allowed read access to the ledger. This would prevent rogue actors from extracting frequency-based insights from the blockchain records. Furthermore, encryption can be introduced in the off-blockchain data syncing steps to safeguard against accidental or malicious content access. 

隐私方面：使用区块链技术产生了几个缺陷。当前，交易的虚假性考虑到数据的取证allow for data forensics，或者从频率分析中推断治疗模式。不泄露姓名，人们也能够从网络流量分析中推断出某个实体一再地与另一个实体有所联系。一个可能的解决方案是使区块链成为一个“被许可的”结构，其中，只有前期被同意的、白名单上的节点被允许对账簿进行读取操作。这将防止恶意节点从区块链中的看病记录里抽取出某些以频率为参考的数据。另外，加密可以被引入链外数据同步过程来保护偶然的或者恶意的内容访问。

Regarding interoperability: by integrating with providers' existing data storage infrastructure, we facilitate continued use of their existing systems. Building on the principle of interoperability, we have designed the system with flexibility to support open standards for health data exchange. In addition, MedRec is source agnostic, i.e. able to receive data from any number of endpoints (physician offices, hospital servers, patient home computers, et cetera). We have developed MedRec not as a proprietary system, but as a set of open APIs to facilitate EHR review and exchange. MedRec is a layer that can be added to existing provider backends with minimal orchestration, thanks to the embedded logic in our Database Gatekeeper utility.

协同方面：通过整合医疗机构现有的数据存储基础结构，我们可以让现有系统持续使用。以协同原则为基础，我们设计了这个系统，可以灵活地支持医疗数据交换的开放标准。此外，MedRec 能够从任意的终端接收数据，比如医生办公室、医院的服务器、病人家里的电脑等等。我们开发的 MedRec 不是作为一个专用系统，而是作为一组开放的API来促进电子病历的检查和交换。由于我们的数据库看门人程序内嵌的逻辑，MedRec 作为一个应用层，只需要极少的适配就能够被添加到现存的医疗机构的后端。

### 在国家医疗健康重大项目背景下的MedRec

### MedRec in the context of national healthcare priorities

In the analysis below, we refer to MedRec by name to suggest how such a project might address national healthcare priorities, likely as part of a larger suite of blockchain solutions to which we hope to contribute.

通过MedRec，我们目的在于这样一个项目也许能够解决国家医疗健康当务之急的问题，它可能作为对我们希望改善的事情而采用的区块链解决方案的一个组件。

Most importantly, the MedRec model restores comprehensive patient agency over healthcare information—across providers and treatment sites, empowering citizens with the data they need to make informed decisions around their care. By giving patients a long-term, trusted log of their information with data sharing functionality built-in, the MedRec system directly addresses the ONC Interoperability Roadmap’s first Outcome: “Individuals have access to longitudinal electronic health information, can contribute to the information, and can direct it to any electronic location” [16]. The MedRec patient record would reflect the many facets of health data, by accepting not just physician data, but also data from the patient’s Fitbit, Apple HealthKit, 23andMe profile, and more. Patients can build a holistic record of their medical data and authorize others for viewership.

更重要的是，MedRec 模型恢复病人对医疗健康信息全面代理权 — 这些信息交叉存储在各种医疗机构和治疗中心，赋予公民利用他们需要的数据来对就医作出更深思的决定。通过给予病人一份长期的、可信的看病历史记录，配以内嵌的数据共享功能，MedRec 直接解决国家医疗健康信息技术协调办公室（ONC， the Office of the National Coordinator for Health Information Technology）的协同路线图的第一个后果：“个人能够访问电子病历的历史信息，可以促进信息的改善，能够将它发送到任意一个设备接收点。” MedRec 的病人记录能够反映出健康数据的许多方面的情况，通过接收的不仅有医生的检查结果，还有病人的穿戴式设备的数据。病人能够建立一个自身健康数据的所有记录，并可以授于其他人可以查看的权利。

MedRec data can also feed into emerging technologies for predictive analytics, allowing patients to learn from their family histories, past care and conditions to better prepare for healthcare needs in the future. By employing open APIs like MedRec, machine learning and data analysis layers could be added to repositories of healthcare data to enable a true “learning health system” [16]. Due to the linked interoperability between provider databases in a MedRec network, better-unified access to data could facilitate a wide range of trend discovery. MedRec’s modularity could support an additional analytics layer for disease surveillance and epidemiological monitoring, physician alerts if patients repeatedly fill and abuse prescription access (e.g. part of the national problem with narcotics abuse [17]), personal dashboards that show patients emerging trends in their own health, etc.

MedRec的数据也能够融入新兴的技术来进行预测性分析，让病人从他们的家族史、过去的检查和患病情况中有所了解，来更好地为未来的医疗健康需求作准备。通过利用像 MedRec 这样开放的API，机器学习和数据分析层能够被加入到医疗健康数据源，一个真正的自学习的系统变得可能。由于 MedRec 网络中医疗机构的数据库之间的交互协同性，对数据的更好的统一能够有利于发现更大范围的发展趋势。MedRec 的模块化能够支持辅助的分析层来进行疾病的调查和传染性疾病的监测，如果病人重复地提交处方申请，医生可以发出警告；在个人设备上显示他们健康情况的倾向。

MedRec’s community model, where medical researchers (and potentially other regulated stakeholders in the healthcare industry) can obtain insightful, population-wide data on medical treatment offers an unprecedented opportunity to achieve goals for precision medicine and evidence-based research. By leveraging a data orchestration system like MedRec where the records would already be gathered, organized and available for analysis, this type of research can be achieved with significantly less overhead than traditional research trials, which often require expensive recruitment procedures and in-person access to patients.

MedRec的社区模型提供的功能：医疗研究人员能够获得关于治疗结果的更多有用数据。它为实现精准医疗和基于证据发现的研究提供一个前所未有的机会。通过利用一个如 MedRec 这样的数据管理系统，其中看病记录被收集、组织、预处理为分析所用，这种类型的研究能够比传统的研究试验方法花费极少的费用，因为传统的研究试验经常需要开销不低的招募过程和对病人的一对一拜访。

The MedRec smart contract structure serves as one model for a “Health Care Directory and Resource Location,” secured with public key cryptography and enabled with crucial properties of provenance and data integrity. This blockchain directory model supports the ability to “grow and change dramatically throughout its lifetime— adding new participants and changing organizational relationships” through stateful updates to the smart contracts [16]. A blockchain log could provide clarity for communicating authorization “across the Health IT ecosystem,” and an audit log for subsequent inquiries into use of such permissions and access patterns. With this functionality, the system would serve as a “Consistent Representation of Authorization to Access Electronic Health Information” [16].

MedRec智能合约设计作为一个模型用于“健康医疗机构目录和资源分布点”，通过公钥加密保障它的安全，并配以如来源和数据完整性这些重要的属性。通过对智能合约的状态更新，这一区块链目录模型支持“生命期里急剧增长和变化”的能力；加入新的参与者，组织关系的关系。区块链日志能够对不同医疗IT系统之间发送授权信息的过程一览无遗，审计日志也可清晰地记录对使用许可和访问模式的查询过程。利用这一功能，这个系统可作为权威代表来访问电子病历信息。

Fundamentally, the MedRec project strives to enable Precision Medicine and holistic understanding of patient medical status without creating a centralized repository of data. Centrally-stored data has often proved disastrous in our modern age of cyberattacks and data leaks. Therefore, MedRec leverages a decentralized, blockchain architecture to enable local, separate storage but coordinated viewing of the data from the patient perspective. We believe MedRec fits squarely in the White House’s goals for the ONC to “support the development of interoperability standards and requirements that address privacy and enable secure exchange of data across systems” [20]. Because MedRec is a system of open APIs, we hope to integrate with other key layers in the healthcare IT stack of the future.

基本上，MedRec 项目努力的目标是：使得精准医疗和对病人健康状态的全面了解成为可能，而无需创建一个中心化的数据源。当前，网络攻击和数据泄露这一常态使得集中式存储的数据经常面临灾难性的危险。因此，MedRec 充分利用分布式的区块链设计来实现本地的、分布式的存储，并且从病人角度来看对数据的查看是有组织的、有规范的。因为MedRec是一个开放式的API的系统，所以，我们希望在未来的医疗健康IT系统中整合进其他关键的层级。

### 下一步的工作

As we look to take MedRec from a research prototype to a meaningful tool for enterprise, government and patient use, we have identified several thrusts of future work. First, we continue our process of actively engaging with healthcare stakeholders across the industry, from hospitals and provider offices, to pharmaceutical companies, to insurance companies, to healthcare startups, U.S. Government institutions and more. We are currently in the process of gathering functionality requirements and additional use-case scenarios to improve the design of all aspects of the MedRec system. In future months, we hope to complete additional rounds of security testing, including third-party penetration testing and a bug bounty program.

在把MedRec这一研究原型变成一个为企业、政府和病人所用的工具时，我们认清了接下来工作要解决的问题。首先，我们j将继续积极与健康医疗行业人员建立可信的关系，包括医院和医疗机构的办公人员、制药公司、保险公司、医疗健康创业公司，政府机构等等。我们当前正搜集功能需求和其他的用例场景，来改善 MedRec 系统各方面的设计。接下来的几个月，我们希望完成几轮的安全测试，包括第三方的渗透测试和漏洞奖赏方案。

Though the MedRec backend is already designed to be flexible with many database architectures, we are exploring custom integration requirements for InterSystems Caché technology, which underpins many hospital backends across the nation and supports EPIC’s record management platform [21]. Our goal is to make MedRec an interoperability layer that can be seamlessly added to existing EPIC.

尽管 MedRec 后端已经被设计为灵活地适应许多数据库结构，但是我们正在为InterSystems Caché （注：一个医疗系统数据库）探索定制整合需求，这将支持国内的许多医院后端以及 EPIC 的病历管理平台。我们的目标是让MedRec 成为一个协同层，它可以被无缝地加到现有的 EPIC。

### 结论

The MedRec prototype provides a proof-of-concept system, demonstrating how principles of decentralization and blockchain architectures could contribute to secure, interoperable EHR systems. Using Ethereum smart contracts to orchestrate a content-access system across separate storage and provider sites, the MedRec authentication log governs medical record access while providing patients with comprehensive record review, care auditability and data sharing. We look forward to continued work on the MedRec project infrastructure, following the ONC’s call for policy and technical components of an interoperable health IT stack. We remain committed to the principles of open source software and will release our research framework on GitHub.

MedRec原型提供一个利用某种方法来解决问题的系统，演示了分布式原则和区块链设计如何创建安全的、协同的电子病历系统。通过使用以太坊智能合约来设计一个在分开的存储和医疗机构之间的内容访问系统，在提供病人可以全面的查看病历、审计护理中心以及数据共享的时候，MedRec 审计日志可以管理病历的访问权。我们期望在 MedRec 项目的基础架构上继续已有的研究，并遵循 ONC 对一个协同交互的健康医疗IT系统的的规则和技术的要求。我们遵守开源软件的规则，将在GitHub上发布我们的研究进展。



------

**区块链中文字幕组**

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号：w1791520555。

[点击查看 GITHUB 及更多的译文](https://github.com/BlockchainTranslator/EOS)

**本文译者介绍**

Chuan，区块链技术爱好者。欢迎加我的微信：youyuxiaochuan

译文版权所有，转载需完整注明以上内容。如有侵权，请与译者联系删除
