
> 本文翻译自：https://docs.decentraland.org/docs/command-line-interface
>
> 译者：[区块链中文字幕组](https://github.com/BlockchainTranslator) [鱼](https://github.com/oscnet)
>
> 翻译时间：2018-2-1
>

 本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。

## Command Line Interface v0
A step-by-step introduction to Decentraland's Command Line Interface

## 命令行接口
一步步教你使用 Decentraland 命令行接口

---
### What is the Decentraland Command Line Interface?
The Decentraland Command Line Interface (CLI) allows you to create, deploy, and manage your scenes in a development environment that does not reside on the block-chain or IPFS (InterPlanetary File System). After generating your new Decentraland scene locally on your own machine, you can immediately begin editing your scene using a text editor of your choice. After testing your scene locally, you can use the CLI to upload your content to IPFS.

### 什么是 Decentraland 命令行接口？
Decentraland 命令行接口 ( CLI ) 允许您在不使用区块链或 IPFS (行星际文件系统) 的开发环境下创建、部署和管理您的场景。在您自己的机器上本地生成新的 Decentraland 场景之后，您可以使用您选择的文本编辑器开始编辑您的场景。在本地测试您的场景之后，您可以使用 CLI 将您的内容上传到 IPFS。

### Why do I need the CLI?
The CLI is designed to help you create and manage Decentraland scenes quickly by operating “off-chain”. With a local development environment, you can more rapidly design, test, and tweak your scenes before uploading any content to IPFS.

### 为什么我需要 CLI?
CLI 的设计目的是在本地开发环境中帮助你链下快速创建和管理 Decentraland 场景。在内容上传至 IPFS 前，您可以更快速地设计、测试和调整您的场景，

### Where can I get the CLI?
> **Note:**
>
>Please make sure that you have the following installed before beginning your CLI installation
>* [Python 2.7.14](https://www.python.org/downloads/)
>* [node.js](https://nodejs.org/en/) with the [npm](https://www.npmjs.com/get-npm?utm_source=house&utm_medium=homepage&utm_campaign=free%20orgs&utm_term=Install%20npm) package manager (npm is bundled with node.js)
>* [IPFS](https://ipfs.io/docs/install/)

###  CLI 如何安装?

> **注意:**
>
>在 CLI 安装之前，请确保您已经安装了以下安装程序。
>* [Python 2.7.14](https://www.python.org/downloads/)
>* [node.js](https://nodejs.org/en/) with the [npm](https://www.npmjs.com/get-npm?utm_source=house&utm_medium=homepage&utm_campaign=free%20orgs&utm_term=Install%20npm) package manager (npm is bundled with node.js)
>* [IPFS](https://ipfs.io/docs/install/)
>

>If you are running Windows, make sure to add Python to your Windows Path. You will also want to set your PYTHON environment variable.
Navigate to your Control Panel > System > Advanced > Environment. Select PATH, click Edit, and add PYTHON C:\Python27\python.exe to the end of the list.

>如果是 Windows 操作系统，请将 Python 添加到 Windows 路径中。您还需要设置 PYTHON 环境变量。打开您的控制面板 > 系统 > 高级 > 环境。选择 PATH，单击 Edit，并添加 PYTHON C:\Python27\python.exe 到列表的末尾。

You will first want to create a new, empty directory in which to install the CLI. We recommend giving this a recognizable name, like “cli” or “decentraland”. Next, open your terminal and navigate to your new directory.

您首先需要创建一个新的空目录来安装 CLI。我们建议给它一个可识别的名字，比如 “cli” 或““decentraland”。接下来，打开您的终端并导航到您的新目录。

The Decentraland CLI is distributed via [npm](https://www.npmjs.com/get-npm?utm_source=house&utm_medium=homepage&utm_campaign=free%20orgs&utm_term=Install%20npm). You can install the CLI with:

Decentraland CLI 通过 npm 发布。你可以用以下命令安装 CLI:

`npm install -g decentraland`

### How do I use the CLI?
**Create your new Decentraland scene**

To create a new Decentraland scene, start by creating an empty directory for your scene. Next, open your terminal, navigate to that directory, and run:

### CLI 如何使用？
**创建新 Decentraland 场景**。

要创建一个新的 Decentraland 场景，首先创建一个空的目录。接下来，打开终端，导航到该目录，然后运行:

`dcl init`

This will generate a new scene using the default structure outlined below within the working directory.

You will be prompted to enter various descriptive metadata that will be stored in your scene.json manifest file.


>Note:
>
When prompted to enter your parcels, use the format `x,y; x,y; x,y` when specifying their coordinates.

这将在工作目录下以默认结构生成一个新的场景。

您将被提示输入将存储在 scene.json 文件中的各种描述性元数据参数。

>注意：
当提示输入您的地块时，请使用`x,y; x,y; x,y`格式指定坐标。

![](https://files.readme.io/eb79e79-cli_1.png)

The CLI will prompt you to continue after reviewing your scene metadata and will provide the option to create a new project with a blank sample scene.

在检查场景元数据无误之后，CLI 将提示您继续进行，并将提供选项以创建一个空白示例场景的新项目。

![](https://files.readme.io/7eea7a0-cli_2.png)

The following commands are available for the `init` command:

* `--help` Returns usage information for `init`
* `-p <path>`, `--path <path>` Allows you to specify a location in which to generate your new scene.
* `--boilerplate` Generates a new scene including a sample scene.

`init` 可以使用以下参数

* `--help` 显示 `init` 使用方法
* `-p <path>`, `--path <path>` 指定生成的场景的目录.
* `--boilerplate` 在生成新场景时包括一个示例场景.

**Decentraland Scene Structure**

Decentraland scenes are built from various components organized within the following folders and files. All of these assets can be found within the directory containing your new scene.

**Decentraland 场景目录结构**

Decentraland 场景是由以下文件夹和文件中组织的各种组件构建的。所有这些都可以在包含您的新场景的目录中找到。

**audio**

A folder containing any background music or audio files that can be played or triggered within your scene.

>Audio within Decentraland scenes will be supported in a future release. Stay tuned!

**audio**

包含任何可以在您的场景中播放或触发的背景音乐或音频文件的文件夹。

在 Decentraland 场景中音频将在未来的版本中得到支持。请继续关注!

**models**

A folder containing any **.gltf assets**, .obj 3D image files, and supporting .mtl material settings files required to render your scene.

>Shaders and lights included in .gltf files will not be decoded.

**models**

包含用来渲染您的场景的 .gltf 文件、.obj三维图像文件、.mtl 材质设置文件的文件夹。

>包含着色器和灯光的 .gltf 文件不会被解码。

**scene.html**

A plain html file containing the [A-Frame](https://aframe.io/) markup for your scene. To learn more about A-Frame, please [refer to their documentation](https://aframe.io/docs/0.7.0/introduction/). If you create a new project with a sample scene, this file will include a generic example.

**scene.html**

一个纯 html 文件，包含使用[A-Frame](https://aframe.io/) 设计的场景。要了解更多关于 A-Frame 的信息，请[参考他们的文档](https://aframe.io/docs/0.7.0/introduction/)。如果您创建一个带有示例场景的新项目，该文件将包含一个通用示例场景。

**scene.json**

The scene.json file is a JSON formatted manifest for a scene or parcel of land. It contains a description of your scene, a list of any assets needed to render your scene, contact information for the parcel owner, and security settings. For more information and an example of a scene.json file, please visit the [Decentraland specification proposal](https://github.com/decentraland/proposals/blob/master/dsp/0020.mediawiki).

**scene.json**

scene.json 是一个 json 格式文件，用来表明一个场景或地块。
它包含您的场景描述、渲染场景时所需的材质列表、地块所有者的联系信息以及安全设置。更多信息和 scene.json 文件示例，请访问 [Decentraland 规范建议](https://github.com/decentraland/proposals/blob/master/dsp/0020.mediawiki)。

**textures**

A folder containing any textures needed for your scene. You can upload textures as .png and .jpg files.

For additional information on creating the content for your scene, including tips and best practices, [check out our wiki!](https://wiki.decentraland.org/index.php?title=Creating_Content)

**textures**

包含您的场景所需的纹理的文件夹。你可以使用 .png 和 .jpg 文件上传纹理。

更多有关为您的场景创建内容的信息，包括提示和最佳实践，[请查看我们的 wiki!](https://wiki.decentraland.org/index.php?title=Creating_Content)

### Run your new scene locally
To build your scene locally, run:

`dcl start`

This will spin up a simple http server with hot-reloading, allowing you to preview your scene within your browser by visiting the provided address:

### 本地运行场景
运行以下命令在本地建立场景：

`dcl start`

命令将启动一个简单的具有热加载功能 http 服务器，使用以下的地址可以让你在浏览器中预览你的场景。

`http://localhost:2044`

![](https://files.readme.io/717cb11-cli_3.png)


### Upload your scene to IPFS
In order to upload your scene, you must have IPFS (InterPlanetary File System) installed locally on your machine. [You can download IPFS here](https://ipfs.io/docs/install/).

After you have downloaded and installed IPFS, begin running the IPFS daemon with:

### 上传场景到 IPFS
为了上传场景，你必需在本地电脑上先安装 IPFS (星际文件系统)。[你可以下此下载 IPFS](https://ipfs.io/docs/install/)。

`ipfs daemon`

For additional help with IPFS, [please refer to their documentation](https://ipfs.io/docs/getting-started/).

To begin uploading your scene, enter:

有关 IPFS 的更多帮助信息，[请查看它们的文档](https://ipfs.io/docs/getting-started/)。

上传场景，输入以下命令：

`dcl upload`

You can specify which IPFS daemon API port to use with the option `-p, --port <number>`. By default, the port is set to `5001`.

Once the upload is complete, the CLI will provide an IPFS Folder Hash and an IPNS Link.


使用 `-p, --port <number>` 选项可以指定 IPFS 守护程序 API 的端口。缺省使用 `5001` 端口。

当上传完成时，会提供一个 IPFS 文件文件夹散列值和一个 IPNS 链接。

To link your scene to Ethereum, simply run

`dcl link`

This takes the IPNS link and updates your scene metadata in the Ethereum blockchain to point to the content that you have uploaded to IPFS. This has to be done only once, since the IPNS link doesn’t change even if you make subsequent uploads.

为了将你的场景跟以太坊关连，可以简单地运行：

`dcl link`

此命令将更新以太坊区块链上的场景元数据以及 IPNS 链接，使它指向你上传到 IPFS 中的内容。只需要运行一次就可以了，因为 IPNS 链接是不变的，即使你后续又多次上传也是一样的。

You can run both the `upload` and `link` commands together by running

`dcl push`

This will upload your scene to IPFS, update IPNS, and link to Ethereum all in one go.

也可以将 `upload` 和 `link` 命令结合在一起：

`dcl push`

这将上传场景到 IPFS、更新 IPNS、链接到以太坊等操作一次完成。

### Command Reference
For a list of all possible commands within the CLI, enter help.

Command  |  Description |  Options
--|---|--
`help`  | Provides help for a given command.  | `[command]`
`exit`  | Exits the CLI.  |  
`init`  | Generates new Decentraland scene using the default scene directory structure.  | `--help` `-p`, `--path` `<path>` `--boilerplate`
`start`, `run`  | Starts a local development server.  |  
`upload`  | Uploads your scene to IPFS and updates the IPNS link.  |  `-p`, `--port` `<number>`
`link`  | Links the IPNS hash of your scene to the Ethereum blockchain  |  
`push`  | Uploads to IPFS, updates IPNS, and links Ethereum in one go.  |  

### 命令参考
使用 help 命令，能显示 CLI 中的所有可能命令的列表。

Command  |  Description |  Options
--|---|--
`help`  | 对指定命令显示帮助信息 | `[command]`
`exit`  | 退出 CLI.  |  
`init`  | 使用缺省目录结构创建一个新的 Decentraland 场景 | `--help` `-p`, `--path` `<path>` `--boilerplate`
`start`, `run`  | 开启本地开发服务 |  
`upload`  | 上传场景到 IPFS 并且更新 IPNS 链接 |  `-p`, `--port` `<number>`
`link`  | 将场景的 IPNS 哈希值跟以太坊区块链关连 |  
`push`  | 一步完成上传到 IPFS、更新 IPNS、链接到以太坊功能 |  


Copyright © 2017 Decentraland. All rights reserved.

----------------------------------------------------

#### 区块链中文字幕组

致力于前沿区块链知识和信息的传播，为中国融入全球区块链世界贡献一份力量。

如果您懂一些技术、懂一些英文，欢迎加入我们，加微信号:w1791520555。

[点击查看项目GITHUB，及更多的译文...](https://github.com/BlockchainTranslator/EOS)

#### 本文译者简介

鱼 区块链技术爱好者，欢迎加微信号交流：**oscnet**

本文由[币乎社区（bihu.com）](http://www.bihu.com)内容支持计划奖励。

版权所有，转载需完整注明以上内容。

----------------------------------------------------
