你可以使用 [Sony mocopi 追踪器](https://www.bhphotovideo.com/c/product/1794690-REG/sony_qmss1_uscx_mocopi_mobile_motion_capture.html) 在 VTube Studio 中实现身体动作的动作捕捉。

***

### 本页面提供日语和中文教程：
* 日语教程：https://sony.co.jp/en/Products/mocopi-dev/jp/documents/VTubeStudio/mocopi_VTubeStudio_HowTo.html
* 中文教程：https://sony.co.jp/en/Products/mocopi-dev/zh-cn/documents/VTubeStudio/mocopi_VTubeStudio_HowTo.html

***

VTube Studio 会将你的 3D 身体动作转换为可轻松用于 2D 模型的追踪参数，包括身体移动、头部动作、腿部动作以及手臂/手部动作。

VTube Studio 可在 **Windows** 和 **macOS** 系统上接收并使用 mocopi 数据。

![mocopi_example_dance](img/img/mocopi_example_dance.gif)

## 示例模型
Sony mocopi 团队提供了一个示例 Live2D 模型，该模型已为 VTube Studio 配置完成，可直接使用所有支持的 mocopi 参数。若你想试用 mocopi 功能，或需要参考示例模型来制作自己的模型，可在此处免费下载：

https://www.sony.co.jp/en/Products/mocopi-dev/en/downloads/DownloadInfo.html#RAYNOS

需下载的文件为 `RAYNOS-chan-avatar_for_VTubeStudio_v1.0.0.zip`

**注意**：该模型可免费用于直播，但可能存在部分使用限制。请在下载前阅读附带的《角色许可协议》。

## 配置方法
第一步是设置 mocopi 设备，使其向 VTube Studio 发送数据。mocopi 设备无法直接连接 VTube Studio，需借助 mocopi **iOS/Android 应用**或 Windows **电脑应用**。

* **mocopi iOS/Android 应用**：运行于智能手机，接收来自 mocopi 追踪器的数据，再通过本地网络/Wi-Fi 将数据发送至 VTube Studio。
  
  免费使用。
  
  更多信息：https://www.sony.co.jp/en/Products/mocopi-dev/en/documents/ReceiverPlugin/SendData.html

* **mocopi 桌面电脑应用**：直接运行于电脑，接收来自 mocopi 追踪器的数据。此方式需配备 [Sony mocopi 传感器数据接收器](https://www.bhphotovideo.com/c/product/1878122-REG/sony_qmpr1_sensor_data_receiver_for.html)，并通过 USB 连接电脑。数据同样通过本地网络（同一台电脑内）发送至 VTube Studio。
  
  电脑应用需**按月订阅**才能使用 USB 传感器数据接收器。
  
  更多信息：https://www.sony.co.jp/en/Products/mocopi-dev/en/documents/mocopiPC/HowTo_mocopiPC.html

通常，这两款应用的使用方法一致：连接 mocopi 设备后，配置与 VTube Studio 的连接。配置连接时，需在 VTube Studio 的 mocopi 设置页面查看自身的 IP 地址和所选端口，再将该 **IP 地址**和 **端口**填入 mocopi 应用的第三方连接配置中。

之后，在 mocopi 应用中点击“开始发送数据”，并确保 VTube Studio 中的 mocopi 接收器已开启。此时 VTube Studio 会显示连接已建立，mocopi 追踪数据即可正常使用。

![mocopi_1](img/img/mocopi_1.png)

## 支持的参数
默认情况下，VTube Studio 在模型设置的追踪参数列表中隐藏 mocopi 追踪参数。若需使用 mocopi，需在 VTube Studio 的 mocopi 配置中开启 **“显示追踪参数”**。

**关于 mocopi 追踪参数范围的重要说明**：以下列表标注的参数范围仅为 VTube Studio 对新参数映射使用的默认最小值/最大值。对于部分参数（如范围标注为 [-30, 30] 的 `MocopiAngleX`），其实际数值可能远超该范围；而范围标注为 [-180, 180] 的参数，数值无法超出此范围——当参数达到范围一端时，会跳至另一端（360° 循环，以 0 为中心，双向各 180°）。

如需了解参数及动作范围的更多细节，建议参考 Sony 提供的 mocopi Live2D 示例模型（链接见上文）。

在 VTube Studio 的 mocopi 设置中开启“显示追踪参数”后，将提供以下参数：

* `MocopiConnected`
  
  范围：[0, 1]
  
  说明：VTube Studio 的 mocopi 接收器关闭或无数据接收时为 0；接收到 mocopi 数据时为 1。

* `MocopiHipAngleZ`

  范围：[-30, 30]

  说明：臀部摆动角度。负值为向左，正值为向右。

* `MocopiAngleX`

  范围：[-30, 30]

  说明：头部左右旋转（摇头）。

* `MocopiAngleY`

  范围：[-30, 30]

  说明：头部上下旋转（点头）。

* `MocopiAngleZ`

  范围：[-30, 30]

  说明：头部左右倾斜。

* `MocopiBodyAngleX`

  范围：[-10, 10]

  说明：身体左右旋转。

* `MocopiBodyAngleY`

  范围：[-10, 10]

  说明：身体前后倾斜旋转。

* `MocopiBodyAngleZ`

  范围：[-10, 10]

  说明：身体左右倾斜旋转。

* `MocopiBodyPositionX`

  范围：[-1, 1]

  说明：身体绝对位置：X 轴。

* `MocopiBodyPositionY`

  范围：[-1, 1]

  说明：身体绝对位置：Y 轴。

* `MocopiBodyPositionZ`

  范围：[-1, 1]

  说明：身体绝对位置：Z 轴。

* `MocopiUpperArmLeftAngleY` / `MocopiUpperArmRightAngleY`

  范围：[-90, 90]

  说明：上臂前后旋转。

* `MocopiUpperArmLeftAngleZ` / `MocopiUpperArmRightAngleZ`

  范围：[-180, 180]

  说明：上臂上下旋转（360° 旋转）。

* `MocopiLowerArmLeftAngleX` / `MocopiLowerArmRightAngleX`

  范围：[-180, 180]

  说明：手腕旋转（360° 旋转）。

* `MocopiLowerArmLeftAngleY` / `MocopiLowerArmRightAngleY`

  范围：[-90, 90]

  说明：前臂前后旋转。

* `MocopiLowerArmLeftAngleZ` / `MocopiLowerArmRightAngleZ`

  范围：[-180, 180]

  说明：前臂弯曲（360° 旋转）。当上臂向内时，数值可变为负值。

* `MocopiUpperLegLeftAngleY` / `MocopiUpperLegRightAngleY`

  范围：[-30, 30]

  说明：大腿前后旋转。

* `MocopiUpperLegLeftAngleZ` / `MocopiUpperLegRightAngleZ`

  范围：[-30, 30]

  说明：大腿左右旋转。

* `MocopiLowerLegLeftAngleY` / `MocopiLowerLegRightAngleY`

  范围：[-30, 30]

  说明：小腿前后旋转。

* `MocopiLowerLegLeftAngleZ` / `MocopiLowerLegRightAngle`

  范围：[-30, 30]

  说明：小腿左右旋转。

## 与摄像头/iOS/Android 追踪结合使用
使用 mocopi 时，所有常规追踪参数仍可正常工作，可与基于摄像头或智能手机的面部追踪结合使用。

若需用 mocopi 实现头部旋转追踪，可使用以下参数：`MocopiAngleX`、`MocopiAngleY`、`MocopiAngleZ`。

当 VTube Studio 中的 mocopi 接收器关闭，或未接收到 mocopi 追踪器数据时，这些参数会自动切换为使用摄像头或智能手机追踪器提供的头部追踪数据。

当 VTube Studio 停止接收 mocopi 追踪器数据时，所有 mocopi 追踪参数都会逐渐回归至 0。

## 故障排除与常见问题
### 若有多个 mocopi 追踪器同时发送数据怎么办？
VTube Studio 一次仅能接收一个 mocopi 追踪器的数据，其他额外追踪器发送的数据会被忽略。

### 把 mocopi 智能手机应用切到后台后，数据发送中断，该如何解决？
在 Android 设备上，根据设备型号不同，应用在失去焦点时可能会被限制访问蓝牙或本地网络，以此节省电量，这会导致后台运行的 mocopi 应用与 mocopi 追踪器（蓝牙连接）或 VTube Studio（Wi-Fi 连接）断开连接。

解决方法：在 Android 系统设置中，确保 mocopi 应用的所有省电选项均已关闭，允许其在后台不受限制地使用电量。

![mocopi_battery](img/img/mocopi_battery.jpg)