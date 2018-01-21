# Prerequisites | 先决条件

> 本文翻译自：http://hyperledger-fabric.readthedocs.io/en/latest/prereqs.html
>
> 译者：[区块链中文字幕组 胡亮](https://github.com/gumoon)
>
> 翻译时间：2018-1-21

## Install cURL | 安装 cURL

Download the latest version of the cURL tool if it is not already installed or if you get errors running the curl commands from the documentation.

如果你还没有安装 cURL 工具，或者运行文档里的 curl 命令报错的话，请下载最新版本的 cURL 工具。

>**Note** | **注意**

>If you’re on Windows please see the specific note on [Windows extras](#windows-extras) below.
>如果你使用的是 windows 操作系统，请留意下面 [Windows 附录](#windows-extras) 段落里特定的注解。

## Docker and Docker Compose 
You will need the following installed on the platform on which you will be operating, or developing on (or for), Hyperledger Fabric:

在你运行或开发超级账本 Fabric 的机器上，你还需要安装对应平台的 Docker 和 Docker Compose。

* MacOSX, *nix, or Windows 10: Docker Docker version 17.06.2-ce or greater is required. | MacOSX、类unix、或 Windows 10：安装 Docker 17.06.2-ce 以上版本。
* Older versions of Windows: Docker Toolbox - again, Docker version Docker 17.06.2-ce or greater is required. | 老版本的 Windows：安装 Docker 工具箱，Docker 17.06.2-ce 以上版本。

You can check the version of Docker you have installed with the following command from a terminal prompt:

在终端运行以下命令来检查你安装的 Docker 版本：

`docker --version`

>**Note** | **注意**

>Installing Docker for Mac or Windows, or Docker Toolbox will also install Docker Compose. If you already had Docker installed, you should check that you have Docker Compose version 1.14.0 or greater installed. If not, we recommend that you install a more recent version of Docker.
>在 Mac 或 Windows 上安装 Docker 或者 Docker 工具集，会同时安装 Docker Compose。如果你已经安装了 Docker，检查一下 Docker Compose 的版本是否大于等于 1.14.0。如果没有，推荐你安装一个更新版本的 Docker。

You can check the version of Docker Compose you have installed with the following command from a terminal prompt:

在终端运行以下命令来检查你安装的 Docker Compose 版本：

`docker-compose --version`

## Go Programming Language | Go 编程语言
Hyperledger Fabric uses the Go programming language 1.9.x for many of its components.

超级账本 Fabric 的若干组件使用 1.9.x 版本的 Go 编程语言编写。

Given that we are writing a Go chaincode program, we need to be sure that the source code is located somewhere within the `$GOPATH` tree. First, you will need to check that you have set your `$GOPATH` environment variable.

考虑到我们会使用 Go 语言来编写链码程序，所以，我们需要确保源码在 `$GOPATH` 配置的路径下。首先，检查一下是否设置了 `$GOPATH` 环境变量。

```
echo $GOPATH
/Users/xxx/go
```

If nothing is displayed when you echo `$GOPATH`, you will need to set it. Typically, the value will be a directory tree child of your development workspace, if you have one, or as a child of your `$HOME` directory. Since we’ll be doing a bunch of coding in Go, you might want to add the following to your `~/.bashrc`:

如果你执行 `echo $GOPATH` 命令没有显示任何内容的话，那么你需要设置它。通常，把它设置为你的开发目录的子目录或者你的 `$HOME` 目录的子目录。因为会经常使用 Go 来开发，你可能想添加配置到 `~/.bashrc` 文件中。

```
export GOPATH=$HOME/go
export PATH=$PATH:$GOPATH/bin
```

## Node.js Runtime and NPM | Node.js 运行时和 NPM
If you will be developing applications for Hyperledger Fabric leveraging the Hyperledger Fabric SDK for Node.js, you will need to have version 6.9.x of Node.js installed.

如果你想使用超级账本 Fabric Node.js 语言的 SDK 来开发基于超级账本 Fabric 的应用程序，你需要安装 6.9.x 版本的 Node.js。

>**Note** | **注意**

>Node.js version 7.x is not supported at this time.
>当前不支持 7.x 版本的 Node.js。

[Node.js](https://nodejs.org/en/download/) - version 6.9.x or greater

>**Note** | **注意**

>Installing Node.js will also install NPM, however it is recommended that you confirm the version of NPM installed. You can upgrade the npm tool with the following command:
>安装 Node.js 的同时也会按照 NPM，然而，推荐你确认安装的 NPM 版本。你可以使用以下命令更新 npm 工具：

`npm install npm@3.10.10 -g`

## Python

>**Note** | **注意**

>The following applies to Ubuntu 16.04 users only.
>以下内容仅适用于 Ubuntu 16.04 用户。

By default Ubuntu 16.04 comes with Python 3.5.1 installed as the `python3` binary. The Fabric Node.js SDK requires an iteration of Python 2.7 in order for `npm install` operations to complete successfully. Retrieve the 2.7 version with the following command:

Ubuntu 16.04 默认安装了 Python 3.5.1。然而，Fabric Node.js SDK 要求 Python 2.7 版本才能完成 `npm install` 。使用以下命令检索 Python 2.7 版：

`sudo apt-get install python`

Check your version(s): 

检查版本：

`python --version`

## Windows extras | Windows 附录
If you are developing on Windows 7, you will want to work within the Docker Quickstart Terminal which uses [Git Bash](https://git-scm.com/downloads) and provides a better alternative to the built-in Windows shell.

如果你在 Windows 7 系统上开发，你会想使用 Docker Quickstart 终端，它使用 [Git Bash](https://git-scm.com/downloads) 来提供了一个Windows 内嵌 shell 的替代品。

However experience has shown this to be a poor development environment with limited functionality. It is suitable to run Docker based scenarios, such as [Getting Started](http://hyperledger-fabric.readthedocs.io/en/latest/getting_started.html), but you may have difficulties with operations involving the `make` and `docker` commands.

然后，经验告诉我们，这是一个只有有限功能的差的开发环境。它适合运行 Docker 基础场景，像 [从这里开始](http://hyperledger-fabric.readthedocs.io/en/latest/getting_started.html)，但是，如果涉及 `make` 和 `docker` 命令时就有困难了。

On Windows 10 you should use the native Docker distribution and you may use the Windows PowerShell. However, for the Download Platform-specific Binaries command to succeed you will still need to have the `uname` command available. You can get it as part of Git but beware that only the 64bit version is supported.

在 Windows 10 上，你应该使用原生的 Docker 发行版，并且可以使用 Windows PowerShell。然而，为了成功下载特定平台的二进制文件，你仍然需要有 `uname` 命令可用。它作为 git 的一部分提供，但是，只有64位的Git版本支持。

Before running any `git clone` commands, run the following commands:

在运行 `git clone` 命令之前，运行以下命令：

```
git config --global core.autocrlf false
git config --global core.longpaths true
```

You can check the setting of these parameters with the following commands:

使用以下命令检查这些参数设置：

```
git config --get core.autocrlf
git config --get core.longpaths
```

These need to be `false` and `true` respectively.

他们需要分别是 `false` 和 `true`。

The `curl` command that comes with Git and Docker Toolbox is old and does not handle properly the redirect used in [Getting Started](http://hyperledger-fabric.readthedocs.io/en/latest/getting_started.html). Make sure you install and use a newer version from the [cURL downloads page](https://curl.haxx.se/download.html)

Git 和 Docker 工具集自带的 `curl` 命令是旧的，不能适当的处理 [从这里开始](http://hyperledger-fabric.readthedocs.io/en/latest/getting_started.html) 文档里面的重定向。确保你安装并且使用一个更新的版本。[cURL 下载页](https://curl.haxx.se/download.html)

For Node.js you also need the necessary Visual Studio C++ Build Tools which are freely available and can be installed with the following command:

为了使用 Node.js ，你需要 Visual Studio C++ 构建工具。它是免费的，可以使用以下命令安装：

`npm install --global windows-build-tools`

See the [NPM windows-build-tools page](https://www.npmjs.com/package/windows-build-tools) for more details.

更多详情请查看 [NPM windows-build-tools 页](https://www.npmjs.com/package/windows-build-tools) 

Once this is done, you should also install the NPM GRPC module with the following command:

一旦以上做完了，你还应该使用以下命令安装 NPM GRPC 模块：

`npm install --global grpc`

Your environment should now be ready to go through the [Getting Started](http://hyperledger-fabric.readthedocs.io/en/latest/getting_started.html) samples and tutorials.

到现在为止，你已经准备好运行 [从这里开始](http://hyperledger-fabric.readthedocs.io/en/latest/getting_started.html) 案例和手册的开发环境。

>**Note** | **注意**

>If you have questions not addressed by this documentation, or run into issues with any of the tutorials, please visit the [Still Have Questions](http://hyperledger-fabric.readthedocs.io/en/latest/questions.html)? page for some tips on where to find additional help.
>如果你的问题没有记录在这个文档中，或者使用该手册是遇到了问题，请访问 [仍然有问题](http://hyperledger-fabric.readthedocs.io/en/latest/questions.html) 页，那里会有一些提示告诉你怎么找到额外的帮助。

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

