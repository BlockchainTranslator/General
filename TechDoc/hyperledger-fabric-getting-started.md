# Getting Started | 从这里开始

> 本文翻译自：http://hyperledger-fabric.readthedocs.io/en/latest/getting_started.html
>
> 译者：[区块链中文字幕组 胡亮](https://github.com/gumoon)
>
> 翻译时间：2018-1-23

## Install Prerequisites | 预备安装
Before we begin, if you haven’t already done so, you may wish to check that you have all the [Prerequisites](http://hyperledger-fabric.readthedocs.io/en/latest/prereqs.html) installed on the platform(s) on which you’ll be developing blockchain applications and/or operating Hyperledger Fabric.

开始开发或者使用超级账本 Fabric 之前，如果你还没有做这一步，你要去检查一下所有[预备安装](http://hyperledger-fabric.readthedocs.io/en/latest/prereqs.html) 的软件是否已经安装在你的机器上了。

## Install Binaries and Docker Images | 安装二进制包和Docker镜像
While we work on developing real installers for the Hyperledger Fabric binaries, we provide a script that will [Download Platform-specific Binaries](http://hyperledger-fabric.readthedocs.io/en/latest/samples.html#binaries) to your system. The script also will download the Docker images to your local registry.

为了真实的在超级账本 Fabric 上开发，我们提供一个脚本来[下载特定平台的二进制包]((http://hyperledger-fabric.readthedocs.io/en/latest/samples.html#binaries))到你的系统。

## Hyperledger Fabric Samples | 超级账本 Fabric 案例
We offer a set of sample applications that you may wish to install these [Hyperledger Fabric Samples](http://hyperledger-fabric.readthedocs.io/en/latest/samples.html) before starting with the tutorials as the tutorials leverage the sample code.

我们提供案例程序。在开始阅读手册并试验手册中的例子代码之前，你可能想安装这些[超级账本 Fabric 案例](http://hyperledger-fabric.readthedocs.io/en/latest/samples.html)。

## API Documentation | 接口文档
The API documentation for Hyperledger Fabric’s Golang APIs can be found on the godoc site for [Fabric](http://godoc.org/github.com/hyperledger/fabric). If you plan on doing any development using these APIs, you may want to bookmark those links now.

超级账本 Fabric Go语言版的接口文档，可以在 [Fabric](http://godoc.org/github.com/hyperledger/fabric) godoc 站点找到。如果你计划使用这些接口来开发，你可能想现在就收藏这些链接。

## Hyperledger Fabric SDKs | 超级账本 Fabric SDKs
Hyperledger Fabric intends to offer a number of SDKs for a wide variety of programming languages. The first two delivered SDKs are the Node.js and Java SDKs. We hope to provide Python and Go SDKs soon after the 1.0.0 release.

* [Hyperledger Fabric Node SDK documentation](https://fabric-sdk-node.github.io/).
* [Hyperledger Fabric Java SDK documentation](https://github.com/hyperledger/fabric-sdk-java).

超级账本 Fabric 想要为各种编程语言提供 SDKs。首先提供的是 Node.js 和 Java 语言的 SDKs。我们希望在 1.0.0 版本发布后提供 Python 和 Go 语言版的 SDKs。

## Hyperledger Fabric CA | 超级账本 Fabric 证书认证服务
Hyperledger Fabric provides an optional [certificate authority service](http://hyperledger-fabric-ca.readthedocs.io/en/latest) that you may choose to use to generate the certificates and key material to configure and manage identity in your blockchain network. However, any CA that can generate ECDSA certificates may be used.

超级账本 Fabric 提供一个可选的 [证书认证服务](http://hyperledger-fabric-ca.readthedocs.io/en/latest)，你可以选择已经生成的证书和私钥来配置和管理区块链网络上的身份。然后，任何可以生成 ECDSA 证书的证书认证服务都可以使用。

## Tutorials | 教程
We offer four initial tutorials to get you started with Hyperledger Fabric. The first is oriented to the Hyperledger Fabric **application developer**, [Writing Your First Application](http://hyperledger-fabric.readthedocs.io/en/latest/write_first_app.html). It takes you through the process of writing your first blockchain application for Hyperledger Fabric using the Hyperledger Fabric [Node SDK](https://github.com/hyperledger/fabric-sdk-node).

为了让你入门，我们提供了四本初级教程。第一本面向超级账本 Fabric 应用开发者，[编写你的首个应用程序](http://hyperledger-fabric.readthedocs.io/en/latest/write_first_app.html)。它带你经历使用 [Node SDK](https://github.com/hyperledger/fabric-sdk-node) 为超级账本 Fabric 编写区块链应用的整个过程。

The second tutorial is oriented towards the Hyperledger Fabric network operators, [Building Your First Network](http://hyperledger-fabric.readthedocs.io/en/latest/build_network.html). This one walks you through the process of establishing a blockchain network using Hyperledger Fabric and provides a basic sample application to test it out.

第二本教程面向超级账本Fabric网络运维人员, 叫 [构建你的首个网络](http://hyperledger-fabric.readthedocs.io/en/latest/build_network.html)。该手册带你体验使用超级账本 Fabric 构建一个区块链网络，并且提供一个简易的例子应用来测试它。

Finally, we offer two chaincode tutorials. One oriented to developers, [Chaincode for Developers](http://hyperledger-fabric.readthedocs.io/en/latest/chaincode4ade.html), and the other oriented to operators, [Chaincode for Operators](http://hyperledger-fabric.readthedocs.io/en/latest/chaincode4noah.html).

最后，我们提供两个关于链码的教程。一个面向开发者, 叫 [链码 for Developers](http://hyperledger-fabric.readthedocs.io/en/latest/chaincode4ade.html), 另一个面向运维人员，叫做 [链码 for Operators](http://hyperledger-fabric.readthedocs.io/en/latest/chaincode4noah.html)。

>**Note** | **注意**

>If you have questions not addressed by this documentation, or run into issues with any of the tutorials, please visit the [Still Have Questions?](http://hyperledger-fabric.readthedocs.io/en/latest/questions.html) page for some tips on where to find additional help.
>如果你的问题没有记录在这个文档中，或者使用该手册是遇到了问题，请访问 [仍然有问题?](http://hyperledger-fabric.readthedocs.io/en/latest/questions.html) 页，那里会有一些提示告诉你怎么找到额外的帮助。

----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/)

#### 本文译者简介

胡亮 区块链技术爱好者，欢迎加微信号:haobaba-huliang

本文由币乎社区（bihu.com）内容支持计划赞助。

版权所有，转载需完整注明以上内容。

----------------------------------------------------

