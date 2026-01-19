VTube Studio的主要用途是使用你的手机进行面部追踪，在Mac/PC应用中渲染你的模型，然后使用OBS（或类似的录制软件）向YouTube或Twitch推流。任何Windows/Mac录制软件都应与VTube Studio兼容。 

有关如何将 OBS（或其他录制/流媒体软件）与 VTube Studio 结合使用，请查看 ["使用 OBS 录制流媒体"](Recording-Streaming-with-OBS.md)页面。

如果你使用iPhone/iPad进行追踪，你可以使用WiFi或USB向电脑端传输面部追踪数据，Android端则仅能使用WiFi传输。

![顶部提示图标](img/img/hint_top.png)
![重点提示图标](img/img/bunny_point.png){: height="59px" width="189px"}
VTube Studio使用你的本地网络（TCP/UDP）从手机向PC或Mac发送面部追踪数据。取决于你的家庭网络设置，可能会出现连接问题，原因多为防火墙设置。更多信息参见以下章节：

[连接问题&解决方案](Connection-Issues-&-Troubleshooting.md)
![底部提示图标](img/img/hint_bottom.png)

## 通过WiFi推流 - PC/Mac上的准备

将面部追踪数据从手机向PC/Mac推流十分方便。首先，确认你的手机与PC/Mac都在同一个本地网络下，否则它们将无法识别对方。

然后，启动桌面应用。在设置中，你可以在选择端口后启动服务器（优先尝试默认端口，25565）。

![服务器连接设置界面](img/img/connection_server.png)

这将在每个可用的网络设备上启动你电脑端的VTube Studio服务器。由于同一电脑可能有多个网络设备，你也许会在按下 **“显示IP列表”** 时看到多个IP。

![IP地址列表界面](img/img/ip_vx.png)

![顶部提示图标](img/img/hint_top.png)
![重点提示图标](img/img/bunny_point.png){: height="59px" width="189px"}
虽然此处显示的IPv4地址通常是无法在互联网上公开访问的本地、内部地址，但你的IPv6地址很有可能是公共地址！若想公开截图，别忘了挡住它们，注意安全！
![底部提示图标](img/img/hint_bottom.png)

首次启动服务器时，你可能会看到Windows Defender防火墙的弹窗。请确保勾上“允许访问专用网络”。否则，你的手机将因被防火墙阻止而无法连接到电脑端应用。

服务器现在已被启动，并正在检测手机应用连接。让它保持该状态。

## 通过WiFi推流 - 连接手机应用

下一步，在手机上启动应用。在设置中，你可以手动输入桌面应用的IP与端口，也可以使用 **“查找服务器”** 按钮自动搜寻服务器并使用它的IP与端口。扫描过程应该不会超过五秒。

![服务器扫描界面](img/img/server_scan.png){: height="" width="290px"}
![主设置界面](img/img/settings_main_2.jpg){: height="" width="290px"}
![手机连接成功界面](img/img/smartphone_connected_real.png){: height="" width="290px"}

现在，点击“连接到电脑”，应用现在会连接到服务器端。如果连接因某些原因丢失，应用会自动尝试重新建立连接。

**恭喜！** 你现在正在将你的面部追踪数据推流到电脑。你可以在桌面应用中打开一个VTS模型，它会使用手机上的面部追踪数据。只要你想，也可以同时在手机应用上打开任意一个模型。

![顶部提示图标](img/img/hint_top.png)
![重点提示图标](img/img/bunny_point.png){: height="59px" width="189px"}
向电脑推流时，你不必在手机上也打开模型。事实上，出于性能方面的考虑，更建议不启用模型。在使用“推流模式”时，连接电脑后，手机上加载的所有模型都会被自动移除。
![底部提示图标](img/img/hint_bottom.png)

## WiFi的替代品：通过USB向iOS或PC / Mac推流

若你使用iPhone/iPad进行追踪，你也可以使用USB有线连接来实时传输面部追踪数据。这比WiFi传输更为稳定，同时也是一个经过测试的新功能。目前，这是更为推荐的传输面部追踪数据的方式。

要开始连接，首先启用手机上的“连接USB”选项。如果原本使用WiFi将面部追踪传输至电脑，会因二者不兼容而将其停用。然后激活 PC/Mac 上应用程序中的“连接 USB”开关。

![USB连接设置界面](img/img/usb_con_pc_1.png)

如果设备没有显示或连接失败，请确保下述情况无误：

* iOS设备通过USB线与电脑连接。

* iOS设备已解锁并正在运行VTube Studio应用。

* iOS端应用显示“USB已启用。等待电脑应用连接。”

* iPhone已与电脑“配对”（手机必须“信任”该电脑）。可以通过检查iTunes上是否可以查看该iPhone文件目录来确认这点。

* **重要提醒：请确保你安装了iTunes！！** iTunes在Windows/MacOS上会启动一些与iPhone通信所需的后台服务。iTunes本身无需启动，但请务必确认已安装并至少运行过一次。如果USB连接依旧失败，请尝试在打开VTube Studio前先启动iTunes。