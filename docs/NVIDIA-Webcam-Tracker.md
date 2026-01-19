
<br/>

除了使用 OpenSeeFace 进行跟踪外，VTube Studio 现在还支持使用适用于 RTX GPU 的全新 **NVIDIA Broadcast Expression Tracker** 进行高质量、高性能的网络摄像头跟踪。

点击这里免费下载： https://store.steampowered.com/app/2178540/VTube_Studio__NVIDIA_Broadcast_Tracker

如果你没有 RTX 显卡，你可能需要查看 [Google Mediapipe面部捕捉](Mediapipe-Webcam-Tracker.md) 以获得相似的跟踪质量。

<br/>



[[img/img/nvidia_broadcast_logo_full.png]]

[[img/img/rtx_on_smol.png]]

(由 [@GiruteaCafe](https://twitter.com/GiruteaCafe)创作)

<br/>

该面捕使用 GPU 加速的 NVIDIA 机器学习技术，这使得它非常快速且高性能，即使在 60 FPS 下也只占用很少的 CPU/GPU 资源，因此它能够流畅地运行任何其他游戏。

<br/>

<img src="img/img/nvidia_tracker_example.gif" width="800" /> 

# 如何获取？

该跟踪器仅适用于 Windows，并且仅适用于 NVIDIA RTX GPU。

请从此处下载**免费 NVIDIA Broadcast Tracker DLC**进行使用: https://store.steampowered.com/app/2178540/VTube_Studio__NVIDIA_Broadcast_Tracker

[[[img/img/rtx_dlc_download.png]]](https://store.steampowered.com/app/2178540/VTube_Studio__NVIDIA_Broadcast_Tracker)

跟踪器文件相对较大（~2 GB），因此请确保你的硬盘上有足够的空间。

在启动 VTube Studio 之前，请确保 DLC 已下载并安装（在 DLC 窗口中设置复选标记）：

[[img/img/rtx_tracker_dlc_installed.png]]

# 如何使用？

NVIDIA Broadcast 跟踪器可以像常规 OpenSeeFace 网络摄像头跟踪器一样启动。单击 **"跟踪类型"**按钮后，选择 **"RTX - NVIDIA Broadcast"**（参见 1）。仅当你实际拥有支持 RTX 的 GPU 时，此功能才可用。

[[img/img/rtx_ui_explanation.png]]

1. 单击此按钮可选择新的 NVIDIA Broadcast 跟踪器。如果你的 GPU 不支持，则不可用。
2. 跟踪类型。如果你使用 NVIDIA Broadcast 跟踪器，此处仅提供"面部跟踪"。使用 NVIDIA Broadcast 跟踪器时，目前不支持手部跟踪。
3. 如果要限制跟踪 FPS，请使用此滑块进行操作。由于 VTube Studio 会将跟踪数据插值为 60 FPS，因此以高于 30 FPS 的速度运行跟踪不会对模型运动质量产生太大影响。
4. 跟踪初始化后单击一次。看向相机时单击以设置默认面部姿势和默认混合形状。
5. 单击此按钮可打开或关闭带有奇怪的面孔的外部跟踪预览窗口（参见 7）。
6. 单击此按钮可打开 blendshape 微调窗口。有关更多信息，请参阅下面的部分。
7. 外部跟踪预览窗口。对于检查混合形状是否正确校准非常有用。渲染 3D 脸部需要一些 CPU/GPU 资源，因此如果不需要，大多数时候应该将其关闭。你还可以使用普通的 **"X 按钮"** 来关闭此窗口。

跟踪器初始化并开始跟踪后，你可以单击跟踪预览屏幕（右下角）中的灰色齿轮图标以显示 Windows 网络摄像头配置窗口。

# 微调和校准

你可以微调跟踪器处理各个混合形状的方式。仅建议高级用户使用。

[[img/img/nvidia_tracker_finetuning.png]]

微调功能允许你通过修改 `偏移` 、`缩放` 和 `分量` 参数，设置跟踪器应用于 blendshape 值的函数。这些参数决定了如何计算实际的 blendshape 值。但是，你不能在 VTube Studio 中直接使用这些混合形状： VTS 使用自己的代码根据这些混合形状计算跟踪参数。

拖动滑块将显示当前用于计算混合形状的图表。X 轴显示输入值，Y 轴显示输出值。你还可以在 3D 脸部跟踪预览窗口中直接看到更改后的效果。

* `偏移`: **[由校准自动设定]** 定义了混合形状的零点。例如，如果这个值是 `0.5` ，那么混合形状输出将在输入达到 `0.5` 之前保持在 `0` 。
* `缩放`: **[由校准自动设定]** 定义了偏移后的陡峭程度。校准过程会计算这个值，使得斜率从偏移值开始，最终达到 `X=1`/`Y=1`.
* `指数`: 设置图形的曲率。这可以手动进行精细调整以获得所需的混合形状响应。

实际使用的函数为 `1 - max(0, 1 - max(x - OFFSET, 0) * SCALE) ^ EXPONENT`。 你可以在 [这里](https://www.desmos.com/calculator/a1hkhsp5ri) 查看它

# 常见问题

## 这个免费吗？

它是免费的（带有水印），就像常规的网络摄像头跟踪一样。无需额外购买。

## 为什么我无法获得完整的网络摄像头 FPS？

VTube Studio 会将跟踪数据插值至 60 FPS（或任何 VTS 运行速度），因此即使是低 FPS 网络摄像头跟踪数据也会表现平滑。以 30 FPS 和 60 FPS 运行的网络摄像头之间几乎没有明显的差异，因此如果你没有获得完整的帧速率，那应该不是什么大问题。

然而，从技术上讲，跟踪器应该能够以网络摄像头支持的完整 FPS 运行（至少高达 60 FPS）。如果你不是这种情况，你可以尝试以下操作：

### 1) 安装最新的NVIDIA GPU驱动

确保你的 GPU 驱动程序是最新的。你可以通过 [GeForce Experience](https://www.nvidia.com/de-de/geforce/geforce-experience/) 执行此操作，或者直接从此处下载适用于你的 GPU 的最新驱动程序：https://www.nvidia.com/download/index.aspx

### 2) 确保"弱光补偿"已关闭

如果你的相机具有"弱光补偿"模式，请确保它已关闭。否则，你的相机可能会降低帧速率以获得更好的照明。这当然会降低网络摄像头视频质量，所以要小心。有关详细信息，请观看此视频：https://www.youtube.com/watch?v=g02DBKjFXzs

你可以通过单击 VTube Studio 中跟踪预览窗口右下角的小齿轮图标来打开相机设置窗口。

<img src="img/img/tracker_webcam_config_win.png" width="490" /> 

这将打开以下窗口：（确保弱光补偿已关闭）

<img src="img/img/low_fps_low_light_compensation.png" width="578" /> 

### 3) 确保"抗闪烁"设置为 60 Hz

如果"防闪烁"设置为 50 Hz，则你的相机帧速率上限为 50 FPS。

<img src="img/img/low_fps_anti_flicker.png" width="578" /> 

### 4) 安装最新的摄像头驱动

如果你的相机有特殊的驱动程序或软件，请下载并安装它。例如，对于罗技相机，那就是罗技 G HUB。

### 5) 确保你的相机确实支持该FPS

在 VTube Studio 中仔细检查你的相机是否确实具有可用的 FPS 设置。如果它不在列出的设置中，则你的相机不支持它。

### 6) 确保你没有在 VTube Studio 中将 FPS 限制滑块设置为较低的值

你可以使用 VTube Studio 中网络摄像头选择屏幕上的"相机 FPS 限制"滑块进一步限制 FPS。确保你没有在那里设置下限。

### 7) 尝试其他视频格式和分辨率

如果你的相机支持多种视频格式，请尝试其他格式。例如，MJPEG 可能有点慢。你也可以尝试降低分辨率。1080p 和 720p 之间的跟踪质量差异很小甚至没有。

### 8) 尝试使用不同的 USB 端口

一些较旧的 USB 端口速度不够快，无法以高分辨率支持完整的 60 FPS 流，因为这可能是数据流过大。确保你没有使用 USB 延长线或 USB 集线器，并且相机直接连接到电脑背面的 USB 端口。

### 9) 以管理员身份运行 VTube Studio

有时，以管理员身份启动 VTube Studio 会有所帮助。查看 [此页面](Starting-as-Admin.md) 以获取更多信息。

### 10) 在 OBS 中检查你的相机

在 OBS 中打开你的网络摄像头，检查它是否真的为你提供了预期的 FPS。

## 为什么即使我的网络摄像头灯亮起，追踪器也无法启动？

跟踪器通过你的本地网络将跟踪数据发送到 VTube Studio，因此你的 Windows 防火墙可能会阻止它。确保添加 `"ExpressionApp.exe"` 
为防火墙例外。

该文件可以在 `Live2DModels` 文件夹旁边的 `MXTracker` 文件夹中找到。如果已添加，请 **尝试重新添加**。有时，当 .exe 文件被更新修改时，Windows 会使这些条目无效。

你可以这样进行添加: (只是一个例子, 将 `"vtube studio.exe"` 替换为 `"ExpressionApp.exe"`)

[[img/img/firewall_config.png]]

## 与iPhone / iPad跟踪比较？

在跟踪质量方面，它们非常相似。嘴巴追踪非常准确，眼球追踪也是如此。眨眼跟踪也很好，但一如既往的，根据你的眼睛形状/大小，它可能会更好或更差。你需要尝试一下，亲眼看看。

NVIDIA追踪器的面部旋转范围也非常大，因此在大多数情况下，即使面部移动速度很快，也不太可能丢失跟踪。我试着快速摇头，直到我头痛，从来没有设法让它失去跟踪。

它支持与 iOS 跟踪相同的参数，包括 **"Mouth X"** 和 **单边眉毛追踪**，但它目前 **不支持** **脸颊鼓起**和 **舌头跟踪** 等等。该跟踪器正在积极开发中，因此很可能最终会添加这些跟踪器。

## 所以我还需要iPhone吗？

使用 iPhone，所有跟踪都完全在手机上完成，因此 PC 中的 VTube Studio 将以最少的 CPU/GPU 使用率运行。这款新的NVIDIA跟踪器性能非常高，但仍会占用一些CPU / GPU资源。

如果你已经拥有iPhone并且对跟踪和设置感到满意，我建议你继续使用。

不过，不必使用多个设备真的很好，所以一定要尝试一下新的跟踪器，也许它对你来说可能是一个不错的选择。

## 是否支持VBridger？

对于初始版本，可能不是。但我肯定会支持VBridger团队让VBridger与新跟踪器联动，这样他们就可以在初始版本发布后添加支持。我们必须弄清楚这将如何运作，但我认为有几个好方法，应该不会太难。

我没有计划直接在 VTube Studio 中添加混合形状自定义或曲线编辑器。

_【译者注:当前版本的VBridger已经支持N卡面捕与谷歌面捕】_

## 预计 CPU/GPU 占用率是多少？

这取决于你的 CPU/GPU，但即使在高帧速率下，它也应该相当小。在我的 RTX 3080 上，以 60 FPS 和 1920x1080 网络摄像头分辨率运行跟踪器，CPU 和 GPU 使用率均保持在 10% 以下。

许多跟踪系统（但不是全部）可以在 NVIDIA RTX GPU 的机器学习优化 **张量核心**上执行。大多数视频游戏都不使用它们，因此它们不会干扰你的游戏。

## NVIDIA Broadcast 面部追踪器会改进吗？

我现在从NVIDIA获得的最新信息是，"虚拟形象和跟踪"是他们现在的首要任务，因此很可能会对这个跟踪器进行改进（这是一个不错的变化，因为苹果从未更新过他们的面部跟踪）。

因此，质量/速度的提高是可能的。

## 关于手部追踪?

该跟踪器目前不支持此功能，但 NVIDIA 正在尝试各种跟踪类型，因此如果最终添加它，我不会感到惊讶。不过我没有任何相关信息。

## 需要准备什么？

唯一的要求是 NVIDIA RTX 系列 GPU 和网络摄像头（任何网络摄像头都可以）。支持所有 RTX GPU，因此任何 RTX 20 系列、30 系列或（即将推出的）40 系列卡都可以，包括笔记本电脑 GPU。不支持 GTX GPU 或其他供应商的 GPU。目前的 Steam 调查显示，大约 30% 的用户拥有 RTX 卡，并且这一数字随着每一代新的 NVIDIA GPU 的推出而不断增加。

如果你不确定自己是否拥有 RTX GPU，请按照 [本指南](https://www.tomsguide.com/how-to/what-graphics-card-do-i-have) 进行查找。如果你的 GPU 名称以"NVIDIA GeForce RTX"开头，则你拥有受支持的 GPU。

## 戴眼镜也能用吗？

我戴着眼镜尝试过，眼球追踪和眨眼追踪似乎效果相当好。当然，这也取决于网络摄像头的放置和照明。

## 正常的网络摄像头跟踪 （OpenSeeFace） 是否仍然可用？

答案是肯定的！它是可用的，并将始终作为主要的网络摄像头跟踪器保持可用。这只是你可以尝试的另一种选择。

## 我可以使用我现有的模型还是需要更改内容？

参数范围/设置将尽可能接近 iOS 跟踪，因此你现有的所有模型都应该能够在没有任何更改的情况下工作（脸颊鼓起和舌头跟踪除外，因为它们目前不适用于此跟踪器）。

## 我应该为此购买 RTX GPU 吗？

取决于你。当前的 OpenSeeFace 跟踪器已经非常好了，所以如果这对你有用，那么现在不需要更新你的 GPU（除非你无论如何都要这样做）。

我建议等到更新出来，然后看看其他人做的比较。我认为这个新的跟踪器绝对是一个不错的选择。

此外，如果你已经使用 VTS iPhone 跟踪或 VBridger 并且你对它感到满意，那么现在可能没有太多理由更改你的设置。


