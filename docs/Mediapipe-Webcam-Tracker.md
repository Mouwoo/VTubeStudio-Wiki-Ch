
除了使用 OpenSeeFace 和 [NVIDIA RTX 网络摄像头面捕](NVIDIA-Webcam-Tracker.md)进行跟踪之外，VTube Studio 现在还支持使用新的 **Google Mediapipe** 网络摄像头跟踪器进行高质量网络摄像头跟踪。质量与 NVIDIA 跟踪器大致相当，但不需要特殊硬件。

它直接包含在 VTube Studio 中（目前仅限 Windows），无需 DLC 或下载。

![Google Mediapipe跟踪器示例图](img/img/mediapipe_A_small.png)

![Google Mediapipe面部跟踪演示动图](img/img/mediapipe_face_example_A.gif){: height="" width="800px"}

## 如何获取？

Google Mediapipe 跟踪器仅适用于 Windows，但与 NVIDIA 跟踪器不同，不需要特殊的 GPU。该跟踪器直接包含在 VTube Studio 中，无需进一步下载或 DLC。

## 如何使用？

Google Mediapipe 跟踪器可以像常规 OpenSeeFace 网络摄像头跟踪器一样启动。

单击 **"捕捉质量"** 按钮后只需选择 **"[Google] Mediapipe Tracker"** 即可。这仅适用于 Windows。

首次启动跟踪器后，请确保至少校准一次，同时保持面无表情并直视屏幕。 VTube Studio 会记住校准数据，因此你不必每次启动跟踪器或重新启动 VTube Studio 时都执行此操作。

![Google Mediapipe跟踪器UI说明图](img/img/mediapipe_ui_explanation.png)

## 常见问题

### 与 NVIDIA/iPhone/iPad 跟踪比较？

就跟踪质量而言，我认为它相当不错，但不如 NVIDIA 跟踪。随着进一步的更新，它肯定会变得同样好，甚至更好。我还将考虑将其引入 VTube Studio 的 Android 版本。

嘴部追踪非常准确，眼球追踪也是如此。眨眼追踪也很好，但一如既往，根据你的眼睛形状/大小，它可能会更好或更差。你只需尝试一下并亲自看看即可。

Google Mediapipe 跟踪器的面部旋转范围比大多数其他跟踪器的限制要严格一些。如果你向下或向左/向右移动太多，它可能会失去跟踪。

它支持与 iOS 跟踪相同的参数，包括 **"Mouth X"** 和 **单边眉毛追踪**，但它目前 **不支持** **脸颊鼓起**和 **舌头跟踪**。该跟踪器正在积极开发中，因此很可能最终会添加这些跟踪器。

### 预计 CPU/GPU 占用率是多少？

在 CPU/GPU 使用率方面，它应该与 OpenSeeFace 网络摄像头跟踪相当。

### 关于手部追踪?

使用 Google Mediapipe 跟踪器时支持手部跟踪。

### 戴眼镜也能用吗？

我戴着眼镜尝试过，眼球追踪和眨眼追踪似乎效果相当好。当然，这也取决于网络摄像头的放置和照明。

### 正常的网络摄像头跟踪 （OpenSeeFace） 是否仍然可用？

当然！它作为主要网络摄像头跟踪器可用并将始终保持可用。这只是你可以尝试的另一个选项。

### 我可以使用我现有的模型还是需要更改内容？

参数范围/设置将尽可能接近 iOS 跟踪，因此你现有的所有模型都应该能够在没有任何更改的情况下工作（脸颊鼓起和舌头跟踪除外，因为它们目前不适用于此跟踪器）。