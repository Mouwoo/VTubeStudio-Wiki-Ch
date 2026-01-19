
## 我的脸会意外出现在直播中吗？

<br/>
<p align="center">
  <img src="img/img/accidental_reveal.png" />
</p>
<br/>

**不，这不可能。** VTube Studio仅使用你的手机摄像头作为面部追踪，只会传输计算完毕后的参数到电脑，而非脸部或任何面部追踪原始数据。所以不论如何，任何视频画面都不会在电脑上出现。**PC/Mac版本也没有任何显示摄像头画面的功能。**

如果你还想确保自己的脸永远不会显示在手机屏幕上，请确保将 _“相机预览”_ 设置为 _“从不显示”_ (见 [**"相机设置"**](VTube-Studio设置.md)).


[[img/img/hint_top.png]]
[[img/img/bunny_point.png|alt="Important Point!!"|height=59px|width=189px]]<br/>
不必担心别人会看到你的脸，你很好看！♥
[[img/img/hint_bottom.png]]

## 我该如何购买VTube Studio？为什么要买？可以商用吗？

购买VTube Studio有两种方式，取决于你想如何使用。
 
* **我只想使用iPhone/Android追踪。**
  * 首先，从iPhone或Android 的应用商店下载VTube Studio，应用本体免费。然后到应用设置中，有一个大按钮可供购买专业版本。
  * 专业版会让你获得免费版没有的一些功能，如可以向电脑推流超过五分钟，并能够在应用中删除VTube Studio标志。
  * 目前你不需要在Steam版本中购买任何东西，免费下载使用即可。在使用iPhone/Android追踪时，电脑端不会显示水印。

* **我只想使用网络摄像头追踪。**
  * 在Steam上免费下载并试用网络摄像头追踪。你会发现，应用界面只有在启用摄像头追踪时应才会显示水印。
  * 购买“remove watermark”DLC以去除水印。

如果你想同时使用网络摄像头与iOS/Android追踪，你需要在iPhone/Android与Steam上都购买VTS。

<br/>
<p align="center">
  <img src="img/img/watermark.jpg" width="552px"/>
</p>
<br/>


[[img/img/hint_top.png]]
[[img/img/bunny_point.png|alt="Important Point!!"|height=59px|width=189px]]<br/>
我知道水印超级可爱，但无论如何请购买VTube Studio！基于大量需求，你现在可以通过在设置中取消勾选“隐藏VTS标志”来重新启用她。 你也可以用挂件系统把她以挂件/资源的形式添加到画面中。

顺带一提，动画是由Walfie(@walfieee)制作的。

[[img/img/hint_bottom.png]]


**作为个人用途时，即使没有购买任何专业版或DLC，你也可以商用VTube Studio。** 此处包括任何形式的商业使用，包括（但不限于）收益化的YouTube频道，Twitch，直播，Superchat，Live2D模型委托等。**如果你资金充足并且喜欢VTube Studio，请通过购买来支持后续开发！<3**

这仅适用于个人创作者、小型VTuber机构与一般的小型公司。对于更大的公司，你将需要额外的许可。请参考VTube Studio EULA以了解更多信息并/或直接联系我们。

* **EULA:** https://Denchisoft.com/license/
* **联系方式:** denchi@Denchisoft.com

## 我可以在购买前试用VTube Studio吗？ 

**当然可以，你也应当这么做！**

Android与iOS上的应用本体免费，并有对应专业版。免费版包含所有功能（包括加载自己的模型），所以在购买前请先试用VTube Studio。

在Steam上，该应用也是免费且包括所有功能的。若想去除水印，你只需购买Steam DLC，否则它将会在使用网络摄像头追踪时显示。

## 我可以用网络摄像头代替手机进行面部追踪吗？

可以，Steam版本支持网络摄像头追踪。

## 我该如何与好友一起使用VTube Studio？

你可以使用`start_without_steam.bat` 文件多开VTube Studio，然后就可以使用多个网络摄像头或手机控制模型。你也可以只使用一个网络摄像头来控制多个VTube Studio进程。

<br/>
<p align="center">
  <img src="img/img/start_without_steam.png"/>
</p>
<br/>


若你想与朋友进行联动直播，可以使用Zoom/Discord/Skype等应用进行群视频聊天。

举例而言，在使用Discord时，只需让每个人都使用VTube Studio的虚拟摄像头功能，然后在Discord中选择该摄像头作为你的主要视频聊天摄像头。或者，你也可以使用OBS进行录制，接着使用OBS虚拟摄像头插件为Discord创造摄像头推流。主视角的人可以使用OBS录制他们的Discord窗口，剪下每个人的视频画面，并使用色度键删除背景。这样做效果很好，但你可能需要将Discord频道升级为高质量的1080P视频聊天，以获得更优秀的画面质量。

**备注（试验性功能）：** 也可以通过LAN-Over-Internet工具，例如 _Zero Tier One_ 或 _Hamachi_ （免费版最高支持五人参与）。你可以在主机上启动多个VTube Studio进程，然后让主播连接他们，记住让不同进程使用不同端口即可！免责声明：我没有亲自测试过该方法，但用户报告称可以正常运行。当然，这种方法可能会伴有网络延迟。

## iOS 应用程序启动，但仅显示灰色屏幕作为相机预览或显示相机图像，而我的脸上没有跟踪蒙版。我该怎么办？

首先，关闭并重新启动 VTube Studio。然后，重新启动你的 iPhone。如果这不起作用，请从 iPhone 中完全删除 VTube Studio 并重新安装。那应该解决它。如果没有，请在 VTube Studio Discord 中打开一个线程。

## 我可以用USB代替WiFi连接手机吗？

如果使用iPhone/iPad进行面部追踪，这不成问题，Android系统则不支持直接将面部追踪数据通过USB传输至电脑。USB连接非常稳定，所以推荐以这种方式来发送面部追踪数据。

在Android上，即使没有WiFi，你也可以通过USB连接你的手机，并将它们连入同一个网络中。

**注意：** 这与VTube Studio无关，但当你通过USB将iPhone连接到PC/Mac，并开启**个人热点** 时，你的电脑会自动尝试使用iPhone的移动数据来访问互联网。请参考该实例: https://apple.stackexchange.com/questions/224069/iphone-prevent-automatic-hotspot-tethering-when-connecting-to-computer

## 当我尝试通过 USB 连接 iPhone 时，我的 Windows PC 卡住或以 1-2 FPS 运行

重新启动 VTube Studio，重新启动 PC 并尝试启动 iTunes。如果这不能解决问题，请再次关闭 iTunes 和 VTube Studio。

然后，打开资源管理器并在文件夹搜索栏中输入 `%ProgramData%\Apple\Lockdown` 。删除该文件夹中的所有内容，然后尝试再次启动 iTunes 和 VTube Studio。

## “虚拟摄像头”功能是什么？

**“虚拟摄像头”**（仅适用于Windows）可以让你录下VTube Studio窗口（无UI）并直接将其作为网络摄像头源使用，这样会让它在Discord、Zoom等软件中的使用更为方便。

[[img/img/virt_webcam.png]]

首先，你需要按 **“安装”** 键来安装虚拟摄像头。此处应该会显示一个Windows控制台弹窗，并可能需要你提供管理员权限，你必须授予该权限。安装成功后，你可以选择“启用虚拟摄像头”选项来启动网络摄像头源。

你现在可以在Discord、OBS、Zoom等应用中以普通摄像头的形式选择该流媒体。该网络摄像头的名字为 **"VTubeStudioCam"** 。虚拟摄像头也支持透明背景推流。需要注意的是，虚拟摄像头的视频质量会比直接使用OBS录制窗口低。

如果安装无效，请确认以管理员模式运行VTube Studio。如果该网络摄像头仍然没有显示（例如，在OBS中），**请确认OBS也以管理员模式运行** 。

## 我的设备很烫！手机应用中的“推流模式”是什么？ 

不幸的是，这是很普遍的现象。你的设备可能会变得很烫，但在正确的设置下，它不应导致任何严重的问题，如过热或崩溃。这主要会影响支持的较旧设备，如iPhone X。

为了减少发热，在向电脑推流时，你需要做三件事：
* **在手机上移除你的Live2D模型。** 当推流到电脑时，你不需要加载模型。加载模型需要消耗大量性能，可能对于部分手机来说负荷过大。 
* **关闭摄像头预览。** 在应用中长时间渲染摄像头预览也可能会导致一些性能问题，试着把它关掉吧。
* **将屏幕亮度全部调低。** 这将大幅度减少手机产生的热量。

当使用以上设置时，**十五小时以上的推流应该不成问题**（保持手机充电的情况下）。已在iPhone X与iPad上进行测试。

连接到电脑时，**“推流模式”** 会自动移除模型、关闭摄像头预览并降低屏幕亮度。在向电脑推流时，建议始终使用推流模式。

## macOS与Windows版本有什么区别吗？

Windows支持所有功能。MacOS不支持OBS透明背景与后台快捷键。这意味着在macOS端，快捷键只有VTube Studio窗口在最前端时才会正常运作。比方说，你无法在玩游戏的同时触发快捷键。

此外，macOS的网络摄像头追踪处于高度试验阶段，并且很有可能会一直保持这种状态。在使用macOS版的VTube Studio时，请牢记这点。

## 在 Windows 上运行该应用程序时，我在耳机/录音中听到一些噼啪声......

不确定是什么原因造成的。这在过去曾发生在一些人身上。通常，更新 GPU 驱动程序可以解决该问题。

## 为什么向PC/Mac推流会有延迟？为什么它的CPU/GPU占用这么高？

这基本上都是由于网络问题引起的。首先，先尝试重新启动你的路由器/交换机，电脑与手机。如果问题依旧存在，请查阅 [“连接问题&解决方案”](Connection-Issues-&-Troubleshooting.md) 章节。

如果你的CPU/GPU占用过高：这不是正常现象。VTube Studio对CPU/GPU的要求并不高，所以可能在哪里出错了。如果你出现了性能问题，请到[VTube Studio Discord](https://discord.gg/VTubeStudio)询问。

有时，**RAZER CORTEX 雷游 游戏加速器**与**微星Afterburner**等 _“游戏性能增强工具”_ 也会导致性能问题，所以可以试着关闭他们看看是否有效。

一位用户也报告说，CPU/GPU的占用率很高，直到开启 `NVidia Reflex` 才有所缓解，所以你也可以尝试这么做。

## 我可以使用单反相机进行面部追踪吗？

通常情况下可以，但部分用户报告了一些问题。部分单反可能需要关闭 **“USB选择性挂起”**。如果相机仍无法在VTube Studio中使用，请尝试通过OBS的虚拟摄像头功能进行传输，并在VTube Studio中读取该虚拟摄像头。这可能会导致部分电脑出现性能问题，但可以运行。

## 为什么应用帧率这么荒唐（每秒400+帧）？

该问题由部分显卡驱动报告错误刷新率导致，它会使VTube Studio中启用VSync时解锁每秒帧率，并尝试以最快的速度渲染应用。

要解决该问题，在你的Nvidia GPU设置（或你GPU的对应设置）中开启G-SYNC。如果这仍不起作用，请考虑在VTube Studio中把每秒帧率设置为60，而不是VSync。

## 我在Android端购买了专业版，可以把它转移到iOS端或steam吗？

通常来讲，没有。这从技术上是不可能的，因为谷歌与苹果使用不同的应用商店。<br/>
不过，我可以给予一个月的宽限期。
 
如果你在Android上购买了VTube Studio并想把它的证书转移到iOS，你可以通过邮件或Discord联系我。若这样做，请先在iOS上进行购买并提供购买证明，随后我将对你在Android上的订单进行退款。 
Valve的DLC条款也不允许将购买的订单从Steam中转入/转出。但如果仅使用Android/iOS追踪，你并不需要Steam DLC，因为它只去除使用网络摄像头追踪时显示的水印。当使用手机追踪时，Steam版本中不会显示水印。

## VTube Studio无法在我的手机上运行，我应该做些什么？

请参考 [简介&必要环境](Introduction-&-Requirements.md) 。

## 面部追踪在我的iPhone/iPad上一团糟！发生了什么？

<br/>
<p align="center">
  <img src="img/img/magnets_o.png" width="612px"/>
</p>
<br/>

首先，请尝试重启手机。

如果这不起作用，并且摄像头预览中的追踪遮罩在到处乱飞或随机闪现，这通常是由磁干扰引起的。iPhone/iPad使用磁力计（数字罗盘）来计算设备的面向。请确保你的设备没有内含磁铁的外壳，也没有靠在电脑显示器上。将设备放置在无线充电器上也可能会导致类似问题。

在某些情况下，光线不佳也是原因之一。请确保你的追踪环境中有良好、非彩色的照明，部分颜色似乎会混淆iOS/Android的面部追踪。也可以试着换一个房间，看看是否有效。

也有反馈称，出现在摄像头视野内的镜子会混淆追踪。

## 为什么我的iPhone/iPad界面只显示后置摄像头？

这说明你的设备不被支持。你也会在应用启动时看到弹窗提醒。关于被支持的设备，详见 [简介&必要环境](Introduction-&-Requirements.md) 章节。

## 持MacOS与Linux系统吗？M1芯片的Mac呢？

* **Linux:** 不受官方支持，但可以通过使用 `Network Tracker` 模式，并手动启用OpenSeeFace来在Linux上运行VTube Studio，参见 [该Trello项目](https://trello.com/c/kbZWaoKN/26-variable-ip-for-osf-tracker) 。如果你对此有疑问，可以在Discord上询问。你可以在这里找到更多信息: [在Linux上运行VTS](Running-VTS-on-Linux.md)
* **MacOS:** 试验性支持，有部分局限性。可以通过Steam正常下载，但请注意一些功能可能无法稳定使用，比如网络摄像头追踪和唇音同步。M1芯片的Mac也应该可以运行，但可能会有更多的稳定性问题。我仅能为macOS系统提供部分支持。

## 使用虚拟网络摄像头或 NDI 时，我的音频出现卡顿/故障。

某些硬件组合可能会发生这种情况，例如使用 GoXLR 时。这可以通过将 BIOS 更新到最新的可用版本来解决。

## 我可以在公司里使用VTube Studio吗？比如电视广告？

取决于企业规模，你可能需要额外证书。请查阅 [VTube Studio EULA](https://Denchisoft.com/license/) 或 [联系开发者](mailto:denchi@denchisoft.com) 获得更多信息。

## 我无法在VTube Studio中载入我的Live2D模型，哪里出了问题？

首先，请检查日志中是否有任何报错。如果日志中有报错却没有错误弹窗，可能是应用中存在错误。请通过Discord联系我以便处理。

也有杀毒软件阻止应用读取模型的情况，请尝试禁用它们或将VTube Studio添加为例外，“IObit Malware Fighter”便是一个例子。

如果你试图在iOS/Android端加载模型，应用却瞬间崩溃了，可能是模型纹理过大导致的。16K纹理或三个及以上的纹理对于大部分移动设备而言都过大了。如此高清的纹理对于提升模型显示效果并没有任何帮助，所以请在从Live2D导出模型时缩小纹理尺寸。一般而言，一至两个4K纹理就足够了。

## 我可以同时使用网络摄像头追踪与iPhone/Android追踪吗？

我不太明白为什么你想这么做，但的确可以。如果两者都在运行，会优先使用网络摄像头，一旦它失去追踪，VTS会自动使用通过网络接收的追踪数据。

## 是否可以在 Linux 上使用带有 OpenSeeFace 跟踪的 VTube Studio

Linux 不受官方支持。但是，有些人已经设法使它起作用。

你可以在此页面上找到有关此内容的更多信息：[在Linux上运行VTS](Running-VTS-on-Linux.md) 。

## 我MacOS系统上的网络摄像头追踪坏了。

MacOS上的网络摄像头追踪是试验性的，你的设备可能根本无法运行该功能。在购买任何DLC之前，请确认你对MacOS上的追踪功能满意，因为我无法保证它能够稳定工作。在最糟糕的情况下，如果VTS或其他应用无法再访问你的网络摄像头，你可能不得不按照以下步骤重置你的SMC：

**系统管理控制器（SMC）重置指南:** https://support.apple.com/zh-cn/102605

尽管如此，有相当多的用户在MacOS上使用VTube Studio，且没有遇到任何问题。

## 尽管如此，有相当多的用户在MacOS上使用VTube Studio，且没有遇到任何问题。

你可能已在 GPU 设置中关闭 `各向异性过滤` 。它必须处于活动状态才能正确渲染模型。简而言之，此设置控制如何以极端角度/变形渲染纹理。

确保各向异性过滤设置为 `"应用程序控制"` 或 `"8x"` 或 `"16x"` 。
以下是如何针对不同 GPU 驱动程序执行此操作的示例: https://www.pcgamingwiki.com/wiki/Glossary:Anisotropic_filtering_(AF)

对于 NVIDIA GPU，这可以在“NVIDIA 控制面板”中完成。确保它 **没有** 设置为 `"Off"` 。

[[img/img/aniso_filter_on.png]]

## VTube Studio 一段时间后不断随机崩溃

这表明你的电脑存在硬件问题，通常与 内存、CPU 或主板有关。

如果你检查 Windows 事件查看器，你可能会看到崩溃原因处显示 `error 0xc0000005` 。

在某些情况下，可以通过修改 BIOS 设置来解决此问题。相关详细信息请查看 [此页面](VTS-Crash-Issue-0xC0000005.md).

## VTube Studio会存储/记录个人信息吗？

**不会。**

具体而言，VTube Studio不会在设备上储存任何个人数据，也不会将其发送到任何外部服务器。VTube Studio会在电脑上保存日志，但皆为人类可读的文本文件，且除非你手动发送，否则它们不会被传输到任何地方。你也可以随时删除它们。

关于更多信息，请在 https://denchisoft.com/privacy/ 查看隐私政策。



