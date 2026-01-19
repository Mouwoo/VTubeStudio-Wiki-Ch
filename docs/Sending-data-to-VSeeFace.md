你可以在iPhone/iPad上使用VTube Studio将blendshape追踪数据传输到电脑端的[VSeeFace](https://www.vseeface.icu/)上，由此把iPhone的高质量追踪应用到你的3D模型上。该功能在VTube Studio的iOS版本中**完全免费**，所以你不必为使用它而购买专业版（当然，无论如何都十分感谢你的支持）。

**对于开发人员:** 想要创建自己的应用程序来接收来自 VTube Studio 的跟踪数据？查看 [此页面](https://github.com/DenchiSoft/VTubeStudioBlendshapeUDPReceiverTest) ❤️

## VSeeFace是什么？

VSeeFace是由Emiliana（[@emiliana_vt](https://twitter.com/emiliana_vt)）制作的集免费与高自由度于一身、支持面部与手部追踪VRM与[VSFAvatar](https://www.vseeface.icu/#vsfavatar)形象的、适用于**3D VTuber**（与Live2D相对应）的木偶程序。

它主要使用网络摄像头追踪控制3D VTuber形象，但最近通过各类第三方应用，包括VTube Studio，增加了对高质量iPhone追踪的支持。

使用该功能完全无需PC/Mac端的VTube Studio。你的iPhone/iPad可以直接通过本地网络（不支持USB连接）连接到电脑端的VSeeFace。

如果你是一名有iPhone的3D VTuber，体验一下VSeeFace吧！！

## 如何在VSeeFace中使用VTube Studio来控制3D模型？

### VSeeFace设置

首先，在VSeeFace中按通常流程设置你的3D模型，不需要额外添加设置。当你在iPhone/iPad上使用VTube Studio与VSeeFace联动时，它会完全支持iOS blendshapes。

### VTube Studio设置

接着，在iPhone/iPad上[下载](Introduction-&-Requirements.md)并启动VTube Studio。关于受支持的iOS设备列表，详见“[简介&必要环境](Introduction-&-Requirements.md)”页面。

在VTube Studio中，主菜单上有三个图标与VSeeFace相关。

* **[1]:** 摄像头预览。将会显示带有面部遮罩的脸。
  
  **注意：请务必在安装iPhone/iPad后至少点按该图标一次，否则将无法初始化追踪。**

  在使用VTube Studio与VSeeFace时，你可以自行选择开启或关闭该界面。

* **[2]:** 快速校准

  在不显示摄像头预览的情况下立即进行校准。

  将会把当前面部位置重设为“平视镜头”。

  VTube Studio也可以在横屏下运行，但请务在旋转iPone/iPad至横屏后进行至少一次校准。

  还可以通过打开相机预览并单击它来触发校准。

* **[3]:** 设置。
  
  还可以通过打开相机预览并单击它来触发校准。

![VSeeFace联动设置界面1](img/img/vseeface_setup_1.png){: height="" width="1024px"}

要想查看VSeeFace设置，你需要在主菜单中打开设置栏并下拉到第一栏的最底部。

设置界面如下：

![VSeeFace联动设置界面2](img/img/vseeface_setup_2.png){: height="" width="512px"}

你只需点击“启用”即可。VTube Studio现在可以将blendshape数据传输至VSeeFace了。一旦VSeeFace连接成功（若没有，则继续停留在设置界面），屏幕将自动调暗，进入节能状态。要关闭该状态，可以选择停用“直播模式”（在第一栏中稍微向上拉，它在“推流至电脑（WiFi）”下方）。

**注意**：要想查看VSeeFace所需的IP/端口，请点按“显示IP列表”。

### 连接VSeeFace

回到电脑端运行中的VSeeFace。打开“设置”并选择“通用设置”。下拉到该部分：

![VSeeFace联动设置界面3](img/img/vseeface_setup_3.png){: height="" width="1100px"}

在追踪软件的下拉菜单中选择“VTube Studio”，并输入你在VTube Studio中查看到的IP/端口（这是你的手机IP）。这里应该使用IPv4。目前端口保持 **21412** 不变。

请确保勾选了接收所有数据，包含“接收面部特征”（blendshapes），“接收头部运动”与“接收眼睛注视”。如果你已经使用blendshapes捕捉眼部，则不必勾选“接收眼睛注视”。

VSeeFace现在应自动连接到VTube Studio并启用追踪。如果你在“启用”追踪时退出了iPhone/iPad端的VTube Studio，它会自动在下一次启动VTube Studio时重新启动。

最后，上拉检查/优化其他设置，如追踪敏感度、注视强度等。

在VTube Studio中，建议保持相机预览关闭，并调暗屏幕，以在节能的同时确保iPhone/iPad不会发热。你也可以/应该在使用时保持充电。设备在正常情况下应该不会过热，尤其是较新的设备。较旧的设备（如iPhone X）可能会温度偏高，但不应过热。

## 连接问题解决方案（iPhone/iPad无法连接）

如果VSeeFace与VTube Studio无法建立连接，通常会与网络问题有关。可能是以下情况之一：

* 防火墙或杀毒软件/安全软件阻挡了连接。为进行测试，请将VSeeFace添加为例外或者暂时关闭这些软件。请确保在测试后重新打开这些软件。

* 你的电脑与iPhone/iPad不在同一WiFi/本地网络下。如果你的路由器有多个WiFi网络，请尝试所有网络。

* 请确保电脑上的网络没被设置为“隐私”。

这些问题都在章节 [连接问题&解决方案](Connection-Issues-&-Troubleshooting.md) 中有进一步解释。该页面上列举的所有问题也适用于VSeeFace连接。

你可以在VSeeFace官网上查阅更多针对于VSeeFace常见问题的信息：https://www.vseeface.icu/

## 可以在哪里得到帮助？

如果你需要VTube Studio的使用帮助，请到 [VTube Studio Discord](https://discord.gg/VTubeStudio) 询问。

如果你对于VSeeFace有任何疑问或建议，请至[@Virtual_Deat](https://twitter.com/Virtual_Deat) Discord的#**vseeface**频道：https://discord.gg/BjBgk7k