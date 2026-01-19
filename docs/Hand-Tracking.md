VTube Studio 支持使用 **[Google MediaPipe](https://developers.google.com/mediapipe)进行实验性的手部追踪**, 目前 **仅支持 Windows 和 macOS (需要最新的macOS版本)**。

你可以将网络摄像头手部跟踪与网络摄像头面部跟踪或智能手机面部跟踪结合起来。

手部跟踪参数可用于直接控制 Live2D 参数（包括各个手指的参数）或检测手势，然后触发快捷键来激活手势、动画等。

请记住，这是一个实验性功能，跟踪远非完美。未来可能会有改进，但就目前而言，至少玩起来很有趣。

## 激活手部追踪

在 VTube Studio 网络摄像头设置中，选择 `仅使用手部捕捉` 或 `同时使用面部和手部捕捉`. 如果你使用 iPhone 进行面部追踪，则应在此处选择 `仅使用手部捕捉`然后打开网络摄像头。现在应该可以追踪你的双手。追踪器需要一秒钟才能检测到你的手。

快速的手指移动是可以的，但是快速的手部移动会使其立即失去跟踪，所以要小心。

![VTube Studio手部追踪界面1](img/img/vts_hands_1.png)

跟踪预览下方的圆圈显示手指角度（全蓝色表示手指伸直，全白表示手指完全弯曲）。下面的栏显示每手掌的“手掌开放度”。中间的两个点表示手的距离。所有这些以及手位置（相对于中心）和手角度都可以用作跟踪参数（“输入”）。

下面显示检测到的手势。右手和左手各可以有一个手势（如图左和右所示）。此外，还有一些需要双手的特殊姿势。它们将显示在中间。

## 使用手势触发快捷键

在快捷键选项卡上，你将找到“手势”按钮。单击该按钮将显示以下窗口，其中包括手部跟踪预览：

![VTube Studio手部追踪界面2](img/img/vts_hands_2.png)

在这里，你可以创建一个将激活快捷键的手势组合。你可以为左手选择一种手势，为右手选择一种手势，或者选择“双手手势”（三角形手势或 ["is-for-me?"](https://img2.imgtp.com/2024/03/13/kgmS7ou9.png) 手势）。你也可以只选择一只手的手势。

你可以选择是否必须检测两个手势才能激活快捷键（使用 AND/OR），并配置是否也允许镜像手势。

最后，你可以设置一个时间来规定检测到手势多长时间才能激活快捷键。

如果快捷键用于激活表情，你还可以将其设置为仅在检测到手势时表情才处于活动状态。

## 使用手部跟踪参数作为输入

你可以使用手部跟踪参数作为 VTube Studio 模型的跟踪输入来控制 Live2D 参数。同样，这些可能不可靠，因此请谨慎使用。

如果你的模型包含具有下面列出的确切参数 ID 的 Live2D 参数，则 **自动设置**还会为这些参数自动创建映射。

以下参数可用:

* **特殊**

  `HandLeftFound`: 如果当前能检测到左手，则为 1，否则为 0。

  `HandRightFound`: 如果当前能检测到右手，则为 1，否则为 0。

  `BothHandsFound`: 如果当前能同时检测到双手，则为 1，否则为 0。

  `HandDistance`: 双手之间的距离（如果都能检测到）。

* **手的位置**

  `HandLeftPositionX`: 到中心的 X 距离（左手）。向外为 10，中间为 0，向内（向右）为 -10。
  
  `HandLeftPositionY`: 到中心的 Y 距离（左手）。上为10，中为0，下为-10。

  `HandLeftPositionZ`: 到中心的 Z 距离（左手）。靠近相机的是 10，远离相机的是 -10。

  `HandRightPositionX`: 到中心的 X 距离（右手）。向外为 10，中间为 0，向内（向左）为 -10。

  `HandRightPositionY`: 到中心的 Y 距离（右手）。上为10，中为0，下为-10。

  `HandRightPositionZ`: 到中心的 Z 距离（右手）。靠近相机的是 10，远离相机的是 -10。

* **手的角度**

  `HandLeftAngleX`: 左手左/右旋转。介于 +/- 180 之间。

  `HandLeftAngleZ`: 左手向左/向右倾斜。介于 +/- 180 之间。

  `HandRightAngleX`: 右手左/右旋转。介于 +/- 180 之间。

  `HandRightAngleZ`: 右手向左/向右倾斜。介于 +/- 180 之间。

* **手指** (全部介于 0 和 1 之间，其中 0 表示手指卷曲，1 表示手指完全伸直)

  `HandLeftOpen`: 左手张开

  `HandRightOpen`: 右手张开

  `HandLeftFinger_1_Thumb`: 左手拇指

  `HandLeftFinger_2_Index`: 左手食指

  `HandLeftFinger_3_Middle`: 左手中指

  `HandLeftFinger_4_Ring`: 左手无名指

  `HandLeftFinger_5_Pinky`: 左手小指

  `HandRightFinger_1_Thumb`: 右手拇指

  `HandRightFinger_2_Index`: 右手食指

  `HandRightFinger_3_Middle`: 右手中指

  `HandRightFinger_4_Ring`: 右手无名指

  `HandRightFinger_5_Pinky`: 右手小指