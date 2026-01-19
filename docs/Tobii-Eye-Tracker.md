## 什么是 Tobii 追踪器？

在 **Windows** 上，你可以使用 [Tobii Eye Tracker 5 或 4C](https://gaming.tobii.com/product/eye-tracker-5/) 来改进你的眼睛和头部跟踪数据。

其他 Tobii 追踪器 **未得到官方支持或测试**。

这些是特殊的跟踪器，你可以将其附加到屏幕底部。它们不进行任何面部特征跟踪（例如嘴巴、眉毛等），但可以 **非常准确地跟踪** 你的 **头部位置/旋转和眼睛在屏幕上的注视位置**。

![Tobii Eye Tracker 5](img/img/tobii_tracker_img.png)

_**重要提示:**_ 如果你使用 **Tobii 4C 追踪器**，并且除了眼动追踪之外还想使用头部追踪，则需要安装特殊的 Beta 版驱动程序版本的 **Tobii Experience**。 了解更多请查看 [此页面](https://help.tobii.com/hc/zh-cn/articles/4408130344337-Tobii-Core%E6%A0%B8%E5%BF%83%E8%BD%AF%E4%BB%B6%E4%B8%8D%E5%86%8D%E6%94%AF%E6%8C%81%E5%A4%B4%E9%83%A8%E8%BF%BD%E8%B8%AA%E5%8A%9F%E8%83%BD)。 下面将更详细地描述。

## 如何使用？

你可以在以下屏幕上设置 Tobii 眼球和头部跟踪（仅在 Windows 上显示）：

![Tobii Eye Tracker Setup](img/img/tobii_basic.png)

确保你的 Tobii 眼动仪已连接到你的 PC 并且可以正常工作（在 VTube Studio 之外）。为确保正常工作，请遵循 Tobii 为跟踪器提供的设置指南，包括 **安装所有必需的驱动程序/软件** 以及 **正确校准 Tobii 跟踪器**。

### 对于 Tobii 眼动仪 5

1.  前往 https://gaming.tobii.com/zh/getstarted/

2.  选择 `"Tobii"`

3.  选择 `"Tobii Eye Tracker 5"`

4.  点击 `"下载驱动"` 安装 `"Tobii 驱动"`。

5.  运行 `"Tobii 驱动"` ，确保它与你的设备配合良好并进行校准。

### 对于 Tobii 眼动仪 4C
对于 Tobii 眼动仪 4C，**除非你使用测试版驱动程序，否则不支持头部跟踪**。 如果你这样做，你可能会失去一些 Tobii-Windows-Accessibility 功能。

如果你不使用测试版驱动程序，则只能在 VTube Studio 中使用眼动追踪功能。

1.  前往 https://gaming.tobii.com/zh/getstarted/

2.  选择 `"Tobii"`

3.  选择 `"Tobii Eye Tracker 4C"`

4.  选择 `"Tobii Experience - 仅限测试版"`，然后点击 `"下载驱动"` 安装 `"Tobii 驱动"`。 如果你不想安装测试版本，选择 `"Tobii眼动追踪核心软件"` 安装（但是你会失去头部追踪）。

5.  运行 `"Tobii 驱动"` ，确保它与你的设备配合良好并进行校准。

## 我可以在 VTube Studio 中用它做什么？

VTube Studio 可以使用 Tobii 跟踪器来 **改进** 来自网络摄像头或 iOS/Android 设备的头部跟踪和眼动跟踪。根据你打开的选项，它会执行以下操作：

*  当 Tobii 跟踪器检测到头部时，会 **覆盖 iPhone/网络摄像头捕捉的头部X/Y/Z位置和旋转参数**。

 这个位置/旋转参数非常平滑和精准。最重要的是，当你眨眼时，它 **不会** 有令人讨厌的点头。

*  当 Tobii 追踪器检测到眼睛时，会 **覆盖 iPhone/网络摄像头捕捉的的眼睛X/Y参数**。

 如果打开此功能，只要 Tobii 追踪器仍然能检测到你的眼球，VTube Studio 就会确保眼睛不会完全闭上。这解决了当你低头看时（例如看向键盘或绘图板）时闭眼的问题。这种方法效果很好，因为 Tobii 追踪器位于屏幕下方并且非常精准，因此它能够判断眼睛是否仍然睁着。

你还可以可视化你注视的位置。该位置将在 VTube Studio 窗口中显示为白色气泡/圆圈。注视圈的坐标是跟踪器安装屏幕内的 X/Y 注视坐标，因此仅当 VTube Studio 位于该屏幕上且处于全屏模式时，显示的位置才会准确。

## 可以在没有任何其他网络摄像头/手机跟踪的情况下单独使用 Tobii 跟踪器吗？

这是可能的， **但不推荐**。 Tobii 追踪器不支持眉毛/嘴巴等面部特征跟踪。因此，如果你单独使用 Tobii 跟踪器，你可能无法获得你想要的一般跟踪质量。

## Tobii 智能设备出现闪烁问题

确保你没有意外地将跟踪器设置为仅跟踪一只眼睛。你可以在 **Tobii Experience** 应用程序中执行此操作。

![Tobii Eye Tracker Settings: Only track one eye](img/img/tobii_experience_eyes_on.png)