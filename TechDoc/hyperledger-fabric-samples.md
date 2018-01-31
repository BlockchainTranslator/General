# Hyperledger Fabric Samples | 超级账本 Fabric 案例

> 本文翻译自：http://hyperledger-fabric.readthedocs.io/en/latest/samples.html
>
> 译者：[区块链中文字幕组 胡亮](https://github.com/gumoon)
>
> 翻译时间：2018-1-28

>**Note** | **注意**

>If you are running on Windows you will want to make use of the Docker Quickstart Terminal for the upcoming terminal commands. Please visit the [Prerequisites](http://hyperledger-fabric.readthedocs.io/en/latest/prereqs.html) if you haven’t previously installed it.

>如果你在 Windows 系统上运行，你会想使用容器的快速开始终端来执行命令。如果还没有安装，请访问 [先决条件](http://hyperledger-fabric.readthedocs.io/en/latest/prereqs.html) 查看相关说明。

>If you are using Docker Toolbox on Windows 7 or macOS, you will need to use a location under `C:\Users` (Windows 7) or `/Users` (macOS) when installing and running the samples.

>如果你正在 Winodows7 或者 macOS 上使用容器工具箱，你将需要分别在 `C:\Users` （Windows 7）和 `/Users` （macOS）目录下安装和运行例子。

>If you are using Docker for Mac, you will need to use a location under `/Users`, `/Volumes`, `/private`, or `/tmp`. To use a different location, please consult the Docker documentation for [file sharing](https://docs.docker.com/docker-for-mac/#file-sharing).

>如果你正在 Mac 机器上运行容器，你将需要使用 `/Users`, `/Volumes`, `/private`, 或 `/tmp` 任一目录或其子目录。若想使用其他目录，请查看容器文档：[文件共享](https://docs.docker.com/docker-for-mac/#file-sharing)。

>If you are using Docker for Windows, please consult the Docker documentation for [shared drives](https://docs.docker.com/docker-for-windows/#shared-drives) and use a location under one of the shared drives.

>如果你正在还是Windows版的容器，请查看容器文档：[共享驱动器](https://docs.docker.com/docker-for-windows/#shared-drives), 然后使用任一共享驱动器下的目录。

Determine a location on your machine where you want to place the Hyperledger Fabric samples applications repository and open that in a terminal window. Then, execute the following commands:

确定了存放超级账本案例应用库的目录后，打开终端窗口，执行以下命令：

```
git clone -b master https://github.com/hyperledger/fabric-samples.git
cd fabric-samples
```

## Download Platform-specific Binaries | 下载特定平台的二进制文件
Next, we will install the Hyperledger Fabric platform-specific binaries. This process was designed to complement the Hyperledger Fabric Samples above, but can be used independently. If you are not installing the samples above, then simply create and enter a directory into which to extract the contents of the platform-specific binaries.

接着，我们将安装超级账本 Fabric 对应平台二进制文件。这些二进制可执行文件是为上面说的超级账本 Fabric 案例设计的，但是，它可以独立使用。如果你没有安装上文提到的例子，只要创建一个目录，然后把二进制文件解压缩到那个目录。

Please execute the following command from within the directory into which you will extract the platform-specific binaries:

请在你想解压二进制包的目录，执行以下命令：

```
curl -sSL https://goo.gl/6wtTN5 | bash -s 1.1.0-preview
```

>**Note** | **注意**

>If you get an error running the above curl command, you may have too old a version of curl that does not handle redirects or an unsupported environment.

>如果 curl 命令执行出错，可能是你的 curl 版本太旧了，以至于不能处理重定向或开发环境不存在 curl 命令。

>Please visit the [Prerequisites](http://hyperledger-fabric.readthedocs.io/en/latest/prereqs.html) page for additional information on where to find the latest version of curl and get the right environment. Alternately, you can substitute the un-shortened URL: [https://github.com/hyperledger/fabric/blob/master/scripts/bootstrap.sh](https://github.com/hyperledger/fabric/blob/master/scripts/bootstrap.sh)

>请访问 [先决条件](http://hyperledger-fabric.readthedocs.io/en/latest/prereqs.html)页获取关于哪里能找到最新版本的 curl 和获取正确的开发环境的额外信息。另外，你可以替换命令中的短网址为：[https://github.com/hyperledger/fabric/blob/master/scripts/bootstrap.sh](https://github.com/hyperledger/fabric/blob/master/scripts/bootstrap.sh)

>**Note** | **注意**

>You can use the command above for any published version of Hyperledger Fabric. Simply replace ‘1.1.0-preview’ with the version identifier of the version you wish to install.

>你可以使用上面的命令下载任意公开的超级账本 Fabric 版本。只要替换 '1.1.0-preview' 为你想安装的版本的版本标识符即可。

The command above downloads and executes a bash script that will download and extract all of the platform-specific binaries you will need to set up your network and place them into the cloned repo you created above. It retrieves four platform-specific binaries:

以上命令下载并且执行一个批处理脚本，接着下载并解压缩所有特定平台的用于建立fabric网络的二进制文件。然后把它们移动到上面克隆的版本库（案例库）中：它取回四个平台相关二进制文件：

* `cryptogen`,
* `configtxgen`,
* `configtxlator`, and
* `peer`

and places them in the `bin` sub-directory of the current working directory.

然后，把他们放到当前工作目录的 `bin` 子目录中。

You may want to add that to your PATH environment variable so that these can be picked up without fully qualifying the path to each binary. e.g.:

为了使用时不需要带全路径，你可以把它们添加到 PATH 环境变量中。如：

```
export PATH=<path to download location>/bin:$PATH
```

Finally, the script will download the Hyperledger Fabric docker images from Docker Hub into your local Docker registry and tag them as ‘latest’.

最后，脚本会从 Docker Hub 下载超级账本 Fabric 容器镜像到本地容器注册器并且标记他们为：'latest'。

The script lists out the Docker images installed upon conclusion.

脚本结尾会输出已安装的容器镜像列表。

Look at the names for each image; these are the components that will ultimately comprise our Hyperledger Fabric network. You will also notice that you have two instances of the same image ID - one tagged as “x86_64-1.x.x” and one tagged as “latest”.

看看每个镜像的名字,它们将最终组成我们的超级账本 Fabric 网络。你会注意到有两个实例具有相同的镜像ID-一个标记为："x86_64_1.x.x"，另一个标记为“latest"。

>**Note** | **注意**

> On different architectures, the x86_64 would be replaced with the string identifying your architecture.
> 不同平台架构， x86_64 字符串会替换为对应架构的标识。

> **Note** | **注意**

> If you have questions not addressed by this documentation, or run into issues with any of the tutorials, please visit the Still Have Questions? page for some tips on where to find additional help.
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


