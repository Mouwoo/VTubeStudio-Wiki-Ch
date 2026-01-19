## 重要！！首先阅读以下内容： 我应该如何使用 OBS 进行录制/推流？

* 不要使用绿幕。VTube Studio 支持使用各种捕获方法获取 *透明背景* 。
* 在 Windows 上，建议使用 **Spout2** 。它速度很快，而且不会捕获 VTube Studio UI。有关详细信息，请参阅下一节。
* 在 macOS 上，使用普通的游戏捕获或 NDI，它也支持透明视频流。但是，NDI 的性能可能不是很高。

## 使用 Spout2 推流无 UI（透明背景）内容到 OBS

**仅适用于 Windows** 。这是 VTube Studio **推荐** 的 OBS 捕获方法，因为:

* 它速度很快（而且几乎不占用CPU）。
* 视频质量高且支持透明度（无需绿幕）。
* 它不捕获 VTube Studio UI。
* 它同时支持任意数量的 VTube Studio 窗口（有关如何多次启动 VTube Studio 的信息，请参阅 [此处](Starting-without-Steam.md) ）。

为了能够使用它，您必须首先安装 OBS 的 Spout2 插件。

### ⚠️ 重要提示：官方 Spout2 安装指南（在其网站上，[链接已删除]）提到“调整输出大小（源大小）”。如果您阅读了官方指南，请不要执行此步骤，因为它可能会破坏您的 OBS 场景！！！！！！ ⚠️

您可以从这里下载 Spout2 OBS 插件: https://github.com/Off-World-Live/obs-spout2-plugin/releases

不同的 OBS 版本有不同的插件版本（例如 OBS v27、28、29...）。确保您下载适合您的 OBS 版本的 Spout2 插件版本。

**如果安装失败** ，请尝试使用其他安装程序（它们有两个，一个“手动”，一个“自动”）。另外，尝试以管理员身份运行安装程序。

然后，在 VTube Studio 中打开 Spout2。

[[img/img/turn_on_spout2.png]]

最后，在OBS中创建一个Spout2源，如下所示。

*注意* ：您也可以在此处直接选择 **“VTubeStudioSpout”** ，而不是“第一个可用来源”。如果您有多个处于活动状态的 VTube Studio 窗口，它们将显示为 **“VTubeStudioSpout2”** 、 **“VTubeStudioSpout3”** ...

[[img/img/obs_spout2_settings.png]]

如果您想使用透明背景（您一定会的），请确保您已在 VTube Studio 中选择了“Color Picker背景”并且打开“透明推流”。

[[img/img/obs_2.png|width=526px]]

## 使用普通游戏捕获（透明背景）推流到OBS

在 PC 上的 VTube Studio 中，选择 **Color Picker背景** 。在 Windows 上，您可以在此处使用“透明推流”选项，这将使窗口在 OBS 中录制时窗口背景透明， **因此您无需使用绿幕/色度键** 。

[[img/img/obs_2.png|width=526px]]

**在 macOS 上，OBS 不支持此功能** ，因此请在此处选择您想要的任何颜色。您可以使用 **“色度键”** 滤镜从 OBS 中的视频捕获中删除该颜色。请记住，您不能在 Live2D 模型中使用该颜色，否则模型的某些部分也可能是透明的。

在 OBS 中添加背景，然后为 VTube Studio 添加捕获。为此，请选择 **“游戏捕获”** 。这支持透明背景，但仅适用于 Windows。

在 macOS 上，此选项称为 **“Syphon 客户端”** ，但在 macOS 10.14 Mojave 后不起作用（请参阅 https://github.com/zakk4223/SyphonInject），因此您需要使用常规窗口捕获和色度键滤镜。

<p float="left">
  <img src="img/img/obs_4.png" width="394" /> 
  <img src="img/img/obs_5.png" width="394" /> 
</p>

您的捕获现已激活。在 macOS 上，您需要添加一个滤镜来删除绿色（或您选择的任何颜色）背景，使用 **右键单击您的捕获 → 滤镜 → 添加滤镜 → 色度键** 。

现在，您可以直接在 VTube Studio 或 OBS 中移动/缩放/旋转角色，将其放置在屏幕上的任何位置。

或者，您可以使用 VTube Studio 中的 **虚拟网络摄像头功能** 或 **NDI** 创建网络摄像头推流，然后直接在 Zoom、Discord 等应用程序中使用它（请参阅常见问题解答）。

## 使用 NDI 推流无 UI（透明背景）内容到 OBS

建议使用OBS“游戏捕捉”来录制VTS窗口。或者，您可以使用虚拟网络摄像头或 Newtek NDI（Network Device Interface,网络设备接口）创建可用作 OBS 等软件的输入的视频流。

NDI 流的质量和延迟非常好。它还支持透明背景（不需要色度/颜色键）并且不记录 VTube Studio UI。使用 NDI 时，VTS 的 CPU 利用率可能会增加。 OBS 插件适用于 macOS 和 Windows。

**OBS 插件页面:** https://obsproject.com/forum/resources/obs-ndi-newtek-ndi%E2%84%A2-integration-into-obs-studio.528/

**OBS 插件下载 (Win/Mac):** https://github.com/Palakis/obs-ndi/releases/tag/4.9.1 

要使用 NDI，请从上面链接的 GitHub 页面下载插件（Windows 为 .exe，macOS 为 .pkg）并安装。在 VTube Studio 中，打开 **摄像头设置选项卡** 中的 **NDI** 开关。可以但不建议同时启用 NDI 和虚拟网络摄像头。

VTube Studio 允许您在 NDI 4 和 5 之间进行选择。如果 NDI 5 在您的 PC 上运行没有延迟，建议使用 NDI 5。顺便说一句，VTube Studio 创建的 NDI 流将在您的整个本地网络中可见，因此您甚至可以让 OBS 在不同的 PC 上运行，并且它将能够从 VTube Studio 读取 NDI 流（除非防火墙或网络安全）设置阻止它）。

与仅支持一个流的虚拟网络摄像头不同，如果您打开了多个 VTube Studio 实例，它们都将在 OBS 中显示为不同（编号）的 NDI 源。

在OBS中，建议进行以下设置：

[[img/img/obs_ndi.png]]

## 使用虚拟摄像头推流无 UI（透明背景）内容到 OBS

这与 NDI 的工作原理类似。只需 **在 VTube Studio 设置中打开虚拟摄像头** ，转到颜色选择器背景并确保您已选中 **“在 OBS 中透明”** 。

在 OBS 中，您现在应该看到一个名为 **“VTubeStudioCam”** 的摄像头。使用以下设置（分辨率除外）将其添加到场景中:

[[img/img/obs_virtual_webcam_settings.png]]

## OBS 的常见问题

### 虚拟摄像头不显示或显示为绿色！

确保您实际上已在 VTube Studio 中打开虚拟摄像头。转到 VTube Studio 中的相机设置并检查 `"Activate Virtual Webcam"` 是否已打开。

### OBS无法捕获VTube Studio

尝试以管理员身份启动 OBS 和 VTS。有关如何执行此操作的更多信息，请查看 [此页面](Starting-as-Admin.md) 。

此外，某些应用程序（例如 **“RTSS Rivatuner”** ）会阻止 OBS 捕获某些应用程序（例如 VTube Studio）。

### 我的游戏捕获或 Spout2 捕获不起作用！

确保 OBS 以管理员身份运行。

另外，如果您使用的是笔记本电脑（或多 GPU PC）并且游戏捕获或 Spout2 捕获显示为黑色/不可见，则 VTube Studio 和 OBS 可能在不同的 GPU 上运行。许多笔记本电脑都会有一个集成显卡（包含在 CPU 中）和一个独立显卡。确保 OBS 和 VTS 都在独立显卡上运行。

这里详细解释了如何做到这一点: https://obsproject.com/kb/gpu-selection-guide

[[[img/img/gpu_selection_obs.png]]](https://obsproject.com/kb/gpu-selection-guide)




