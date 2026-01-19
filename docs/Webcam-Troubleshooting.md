此页面包含一些如果你的网络摄像头无法在 VTube Studio 中工作时可以尝试的操作。

**请先尝试以下所有方法，然后再在 VTube Studio Discord 中提问！**

## 检查日志

打开应用程序中的网络摄像头后，单击 VTube Studio 主菜单中的橙色“日志”按钮。检查有没有错。你还可以通过检查“Live2DModels”文件夹旁边的“Logs”文件夹中的文本来查看完整日志。

## 尝试不同的 USB 端口

如果是 USB 网络摄像头，请尝试将其插入其他 USB 端口。这有时会有所帮助。


## 尝试在 VTube Studio 中重新选择网络摄像头

转到网络摄像头设置并再次选择网络摄像头。然后开始跟踪。

## 确保 VTube Studio 有权访问网络摄像头

可以在 Windows 设置中为各个应用程序打开/关闭网络摄像头访问。一些安全软件还会阻止应用程序访问网络摄像头。确保允许 VTube Studio 访问网络摄像头。

## 检查安全软件

一些安全软件或杀毒软件会阻止程序访问网络摄像头。如果你使用任何第三方安全软件，请检查它们是否有摄像头安全设置。具有此类设置的一些应用程序是 `"ESET Antivirus"` 、 `"AVAST"` 和 `"IObit Malware Fighter"` 。

特别是对于 `"ESET Antivirus"` ，请确保像这样停用 `Webcam Protection` :

[[img/img/eset_antivirus_webcam_fix.png]]

## 安装 Visual C++ 可再发行组件

当你在 Steam 上安装 VTube Studio 时，这应该会自动发生，但有时它似乎不起作用。确保你已安装它，否则网络摄像头跟踪将无法工作，并且你会在日志中收到一些类似 `"Missing DLL"` 的错误。

你可以在此处获取：（查看“Visual Studio 2015、2017、2019 和 2022”部分）

https://learn.microsoft.com/zh-cn/cpp/windows/latest-supported-vc-redist?view=msvc-170

## 检查你是否运行了“Windows N 版本”

例如“Windows 10 N 版”。这些版本缺少网络摄像头跟踪工作所需的一些库，你还会在日志中收到 `"Missing DLL"` 错误。你需要下载一些额外的库。

从此页面找到适合你的 Windows 版本的正确版本并安装: https://support.microsoft.com/zh-cn/topic/windows-10-n-%E7%89%88%E5%92%8C-windows-10-kn-%E7%89%88%E7%9A%84%E5%AA%92%E4%BD%93%E5%8A%9F%E8%83%BD%E5%8C%85-229a1ad7-7a3f-87f7-9f0b-ff92fb96b3e4

## 确保没有其他应用程序正在使用网络摄像头

通常这将在 VTS 日志中显示为 `"No data from webcam - Maybe another app is using it?"`。

VTS 通常因为另一个应用程序正在使用而无法访问网络摄像头。如果在 OBS 中的场景中使用相机，即使该场景未打开，也可能会发生这种情况。确保你的相机没有在其他地方使用。为了进行故障排除，我还建议退出电脑上运行的所有其他应用程序/程序，看看是否有帮助。

## 如果你有 VPN，请尝试将其关闭

VTube Studio (OpenSeeFace) 使用的网络摄像头跟踪器使用本地网络与 VTube Studio 进行通信。因此，VPN 可能会干扰 VTube Studio 网络摄像头跟踪。尝试关闭 VPN，然后启动 VTS，看看是否有帮助。如果这解决了你的问题，请找到一种方法将 VTube Studio 添加到 VPN 应用程序的例外列表中。

## 重启

有时，这有助于解决网络摄像头问题。

## 进行 Steam 完整性检查并检查你的安全软件

安全软件可能会从 VTS 目录中删除应用程序运行所需的一些文件。如果你正在运行防病毒软件或其他安全软件，请确保将 VTS 添加为例外。已知会导致 VTS 出现问题的一款反恶意软件应用程序是“IObit Malware Fighter”。

要检查所有文件是否都存在，请运行 Steam 完整性检查，如下所示: https://help.steampowered.com/zh-cn/faqs/view/0C48-FCBD-DA71-93EB

还要确保 VTube Studio 作为例外添加到你的防火墙中，并尝试暂时关闭防火墙（记住之后再次将其重新打开！！）

## 某些设备会导致问题，例如 Avermedia Live Gamer Portable C875

目前，将此设备连接到你的 PC 将导致 VTube Studio 在选择网络摄像头时崩溃。在VTS中选择并启动网络摄像头时，你必须暂时断开连接，否则将无法工作。

## 尝试移动文件夹

尝试将 VTube Studio 文件夹移至其他位置。如果它位于 `Program Files (x86)` 文件夹中的某个位置，请将其移动到 `Program Files` 文件夹中，看看是否有帮助。你始终可以像 [这样](Starting-without-Steam.md) 不通过 Steam 启动 VTube Studio。

## 检查 `run.bat` 文件

尝试手动启动网络摄像头跟踪器，看看它在 VTube Studio 之外是否可以正常工作。你可以通过运行 Steam 文件中 `VTube Studio_Data\StreamingAssets\OpenSeeFaceTracker_v_1_20_2\binary` 文件夹中的文件 `run.bat` 来完成此操作。这将显示你的网络摄像头视频，包括跟踪点，因此请勿在直播中执行此操作！如果这有效，但跟踪器在 VTube Studio 中不起作用，这是进一步排除故障的重要线索。

## 在 VTube Studio Discord 中提问

如果这些都没有帮助，请通过 VTube Studio Discord 进行询问。创建主题时，请发布你的日志。日志（.txt 文件）可以在 `Live2DModels` 文件夹旁边的 `Logs` 文件夹中找到。

https://discord.gg/VTubeStudio




