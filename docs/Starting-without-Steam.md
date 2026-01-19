VTube Studio仅通过Steam发行，所有更新也以该形式分发。然而，在下载后，**你可以不通过Steam直接启动VTube Studio**。

**注意:** 当 VTube Studio 不通过 Steam 启动时，[VNet 多人联机](Multiplayer.md) 功能将不可用。

使用 VTube Studio `.exe` 旁边的 `start_without_steam.bat` 文件。 

![非Steam启动文件位置](img/img/start_without_steam.png)

在 macOS 上，该文件位于： ~/Library/Application Support/Steam/steamapps/common/VTube Studio 。由于“Library”文件夹在 macOS 上是隐藏的，因此访问起来可能有点困难。请查看此页面，了解如何访问它的详细信息：https://forums.macrumors.com/threads/how-to-find-steam-apps-folder-location-on-mac.2303715/

### 启动多个VTube Studio

你可以使用 `start_without_steam` 文件启动多个 VTube Studio。

如果你已经启动了一个 VTube Studio（无论是否通过 Steam），你还可以使用第一个配置选项卡上的“多开 VTube Studio”按钮启动多个 VTube Studio。

![多开VTube Studio按钮位置](img/img/start_new_vts_instance_button.png)

当你启动多个 VTube Studio 时，由于网络服务器和 API 的端口已经被占用，所以它们将在下一个可用端口上启动。

你可以使用多个网络摄像头或手机（在不同端口上）控制不同的VTube Studio进程。你也可以在多个VTube Studio中使用同一个网络摄像头。
当你启动多个 VTube Studio 时，窗口将具有不同的标题（仅限 Windows，macOS 不支持），因此 OBS 可以分别捕获这些窗口。

![多开VTube Studio窗口标题示例](img/img/vts_multi_window_title.png){: height="" width="730px"}

你现在可以使用多个网络摄像头或手机（在不同端口上）控制不同的VTube Studio进程。你也可以在多个VTube Studio中使用同一个网络摄像头，这样它们就会使用相同的追踪数据。在这种情况下，摄像头只会执行一次面部追踪，所以不会有额外的CPU负荷。

要了解如何执行此操作，请查看 [使用单个网络摄像头或iPhone-Android设备控制多个模型](Controlling-multiple-models-with-one-Webcam-or-iPhone-Android-device.md)页面。

![多开VTube Studio效果演示](img/img/multi_vts.gif){: height="" width="740px"}

如果你购买了 `去除水印 DLC` ，则必须通过 Steam 启动该应用程序至少一次，之后该 DLC 也可以在该 PC 上在没有 Steam 的情况下使用（并且完全离线）。