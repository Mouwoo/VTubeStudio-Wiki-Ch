VTube Studio提供了一些示例模型。它们中绝大多数为Live2D Inc.所有，所以若想在直播中使用，请务必阅读 **["隐私政策与许可"](Privacy-Policy,-Licensing-and-Further-Terms.md)** 章节。

本章节涵盖了如何将你自己的Live2D模型载入VTube Studio。希望你此时已经拥有了自己的Live2D模型，并对Live2D及其运作原理（如Live2D参数）有基础的了解。

## 我可以在哪里获得模型？

如果你想知道如何获取（或制作）VTube Studio 模型，请查看 [此页面](Models.md) 

## 为VTube Studio准备你的Live2D模型

实际上，你不需要为了让你的Live2D模型适配VTube Studio而做任何特别的准备。正如稍后 **“VTS参数设置”** 章节中所解释的，你可以将任何面部追踪参数映射到任何Live2D参数上，所以理论上你可以随意选择参数ID与其范围。

然而，依旧建议遵守默认ID与参数范围（最小值/最大值）。还请注意，对VTube Studio很重要的只有Live2D的参数ID，而非参数名。 

当你的模型制作完毕后，通过 **通过文件→导出运作档→导出为.moc3文件** 进行模型导出。

请务必选择以下设置：

* “输出版本”设置为“SDK 3.0”或“SDK 3.3”或“SDK 4.0”（推荐）**最新版本的VTS已经支持“SDK 5.0”**。
* “导出物理模拟设定文件（physics3.json）”若不导出，模型将没有物理效果。请务必用该方法导出物理模型，而非单独从模型中导出，因为这是唯一能确认模型（在.model3.json
文件中）“注册”物理文件并可用于VTube Studio的方法。若物理文件没有被注册，VTube Studio将会使用它在模型文件夹中找到的第一个文件。
* 输出类型：SDK

它将创造一个含有以下文件的文件夹（忽略标红文件）。若模型稍后在VTube Studio中加载失败，请确认没有文件缺失。

[[img/img/files_akari.png]]

关于上述文件作用的概述：

* **\<model\>.model3.json**
  * 主要的Live2D模型索引文件。
  * 人类可读（能够在文件编辑器中打开/编辑）。
  * 有引用其余所有文件。VTube Studio需要该文件。
* **\<model\>.moc3**
  * 模型的二进制文件。包含所有模型数据，如顶点、变形器、参数等。
* **\<model\>.cdi3.json**
  * 模型显示信息文件。目前不会在VTube Studio中使用。
  * 人类可读。
* **\<model\>.physics3.json**
  * 有关于物理设置的所有信息。
  * 人类可读。
* **\<model\>.\<resolution\> (此处为：akari.4096)**
  * 包含你的纹理文件。VTube Studio也支持拥有多层和/或高清纹理的文件。请注意，在手机端使用高清纹理可能会导致卡顿，甚至应用崩溃。

在进行下一步前，请确认你的文件夹内包含以上所有文件。我一般给该文件夹取名为 **\<model\>_vts**，但你可以随意命名。

如果你想使用Live2D动画与Live2D表情，将它们也放在该文件夹内，或放于一个子文件夹中（参见上方截图中的两个文件夹）。表情与动画的运作方式会在稍后解释。你也可以在文件夹中加一个模型图标（任意文件名.png或.jpg，
推荐512x512像素）。

## 将你的Live2D模型载入VTube Studio

将你的模型文件夹放入VTube Studio中的“Live2DModels”文件夹中。在不同平台上，该文件夹的位置不同。在Steam版本中，你可以用该按钮打开文件夹：

[[img/img/open_data_folder.png]]

[[img/img/model_data_folder.png]]

启动VTube Studio。当软件启动时，它会自动找寻新的Live2D模型文件，并在相同文件夹中新建一个VTube Studio模型（VTS模型， **\<Live2D-Model-Name\>.vtube.json**）。该文件为人类可读，且包含了你的VTube Studio模型设置的所有信息。

你现在应该可以在模型选择栏中找到你的模型。若没有，请确定没有文件缺失且日志中没有报错。

## 在 iPhone/Android 上获取模型

**注意:** 如果你只想使用手机进行跟踪，则不需要在智能手机上安装该模型，但它可以很好地为 Twitter/TikTok 制作短视频。

你可以使用上述方法手动将模型加载到手机上。但是 VTube Studio 具有将模型从 PC/Mac 直接发送到智能手机的功能。只需在 PC/Mac 应用程序中打开模型，通过 WiFi 或 USB 连接智能手机，然后按这个按钮。

如果你的智能手机上已有该模型，将会直接进行覆盖。

[[img/img/send_model_to_phone_1.png]]

## 自动设置

当载入一个新的Live2D模型时，你将被要求进行“自动设置”。自动设置也可以在模型加载后手动进行（在设置中的模型一栏）。

[[img/img/auto_setup.png]]

当进行iOS/网络摄像头或Android端的自动设置时，VTube Studio会自动在模型中查找默认Live2D参数。VTube Studio会假设你使用默认Live2D参数ID与参数名，并据此进行VTube Studio设置。你可以在这里查看更多默认ID相关内容: https://docs.live2d.com/zh-CHS/cubism-editor-manual/standard-parameter-list/

如果你没有使用默认ID，则需要手动设置模型。这将在 **\"VTS参数设置\"** 章节中进一步解释。

或者，你可以在此菜单中从另一个模型复制设置，包括参数设置、表达式、动画等。有关详细信息，请查看 "[在模型间复制配置](Copy-config-between-models.md)" 章节。

模型现已准备就绪。当然，你或许还要进行微调，但它现在理应能动了。在iOS，你可能需要在安装应用后先打开相机预览，在那之后模型才会运动。 

整个过程在该视频中也有解释：

**[VTube Studio] 载入自定义Live2D模型 -** https://www.youtube.com/watch?v=AssUd6EtFXw



