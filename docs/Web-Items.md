**Web 挂件** 是 VTube Studio 中可以使用的一种挂件类型 (仅限 Windows/macOS).

Web 挂件本质上是一个可以作为 VTube Studio 中模型挂件的完整的 Web 浏览器。它们可以像普通的挂件一样移动、旋转、固定，但是会显示一个你可以与之正常交互的网站。Web 挂件使用 [Chromium 嵌入式框架 (CEF)](https://en.wikipedia.org/wiki/Chromium_Embedded_Framework), 因此它们具有 Google Chrome 所具有的大部分功能。

Web 挂件本质上类似于 "OBS 浏览器源" (同样使用 CEF), 只是可以直接在 VTube Studio 中使用。

![VTube Studio Web Items](img/img/web_items_a.png){: width="792px"}

一些基本信息:

* 任何在 Google Chrome 中运行的网站也可以在 VTube Studio Web 挂件中运行。

* 与 OBS 浏览器源一样，Web 挂件也支持透明背景。这样，你可以轻松地直接在 VTS 中使用弹幕小部件、打赏小部件等。

* 与普通浏览器一样，你可以登录网站、使用 cookie 存储数据等。 每次重新启动 VTS 时，登录名/Cookie 和其他数据都可以被储存或清除，具体取决于你的 Web 挂件设置。

* 还支持声音（可以静音），因此你可以直接将 Twitch/YouTube/BiliBili 视频加载为 VTS 中的挂件。

* Web 挂件也适用于挂件场景，因此你可以使用热键加载具有某些预设/URL 的 Web 挂件。

* Web 挂件 **不会** 通过 [VNet 多人联机](Multiplayer.md) 同步。当你处于多人连线状态时它们仅会显示在你这边。

* 你还可以使用 **热键** 来执行诸如生成新的 Web 挂件、删除它们或将其静音/取消静音之类的操作。

## 快速访问按钮

当你将鼠标悬停在Web 挂件的右上角时（见下图），将显示几个按钮。大多数应该是不言自明的。一些特殊按钮：

* `设置按钮:` 打开完整的设置页面。这使你可以访问所有 Web 挂件设置，例如挂件裁剪、滚动敏感度等。

* `锁定按钮:` 允许你锁定/解锁此 Web 挂件。在与加载的网页交互时，你应该锁定 Web 挂件，否则你会滚动/拖动该挂件。

* `交互按钮:` 打开/关闭此 Web 挂件的网页交互。当你想要拖动/移动/缩放 Web 挂件时，你应该关闭交互，否则你也会同时与网站进行交互。

![web_items_examples](img/img/web_items_examples.png)

## 热键和挂件场景

你可以使用 `触发 Web 挂件动作` 类型的热键对Web 挂件执行各种操作，例如:

* 生成新的 Web 挂件。

* 删除所有 Web 挂件。

* 将所有 Web 挂件静音/取消静音

* ...以及更多！

此外，Web 挂件也适用于 ["挂件场景"](Item-Scenes-and-Item-Hotkeys.md). 这意味着你可以设置 Web 挂件，然后将它们保存到挂件场景中，然后使用热键加载/卸载这些 Web 挂件。

Web 挂件数据将保存在挂件场景中，包括其 URL、分辨率、位置、静音/取消静音状态等。

![web_items_item_scenes](img/img/web_items_item_scenes.gif){: width="490px"}

## 透明背景

与 OBS 浏览器源一样，VTube Studio Web 挂件支持具有透明背景的页面。你可以使用它来设置弹幕机或打赏小部件等小部件，并且更直接地放入 VTube Studio。启用/禁用特定 Web 挂件透明背景的设置可以在完整的 Web 挂件配置中找到。

![web_items_settings_a](img/img/web_items_settings_a.png){: width="613px"}

## 加载本地文件

与 Google Chrome 一样，你可以使用 Web 挂件加载本地文件（文本、图像、HTML 页面等），甚至浏览本地文件夹。

默认情况下，此功能处于关闭状态，因此你必须手动允许加载的 Web 挂件能够加载本地文件。完成此操作后，只需使用本地文件路径作为 Web 挂件的 URL，它就会加载。

格式示例:

* `C:\Downloads\my_video.mp4` 将本地视频加载到 Web 挂件上并播放。

* `C:\` 将显示该文件夹的全部内容。打开本地文件夹时请小心个人信息泄露。

* `file://C:` 同上，只是使用 `file://` 前缀显式打开本地文件。

![web_items_local](img/img/web_items_local.png)

## 默认值

你可以为某些选项设置默认值，例如是否应将新生成的 Web 挂件静音或取消静音，或者新 Web 挂件是否应能够加载本地文件。

这些默认值可以在 Web 挂件设置中设置（在设置列表中向下滚动一点）。

## 限制

Web 挂件有一些限制:

* 它们 *不会通过 [VNet 多人联机](Multiplayer.md)同步*。同步浏览器上下文将非常不安全。你的 Web 挂件只会在协作会话中显示在你身边。

* 在 Web 挂件中播放高分辨率视频时，性能不是最佳的。如果你遇到性能问题或同时播放多个网页视频时，建议将Web挂件的分辨率保持在 1024 像素或以下。

* 由于 CEF 的限制，缩放级别是按域共享的。这意味着同一域上的所有 Web 挂件将具有相同的缩放级别。

## 特殊文件支持 (.mp4、.pdf等)

Web 挂件可以直接显示某些文件，例如视频、音乐文件或文本文件。无论这些文件存储在何处（在线或在你的本地 PC 上）。

支持的格式包括: `.mp4`, `.webm`, `.mp3`, `.bmp`, `.pdf`, `.txt`, `.html`, `.json`

你也可以将该类型的文件直接拖动到 VTube Studio 窗口中。这样做会将文件加载到 VTube Studio Web 挂件中。对于拖入 VTube Studio 的 Web 挂件，将自动开启本地文件访问。即使以这种方式加载图片文件(例如 `.bmp`) ，它仍然是不会通过 VNet 共享的常规 Web 挂机。

## 安全

Web 挂件使用 [Chromium Embedded Framework (CEF)](https://en.wikipedia.org/wiki/Chromium_Embedded_Framework)。这意味着在 VTube Studio Web 挂件中打开 URL 基本上与在 Google Chrome 中打开相同的 URL 一样安全。

这意味着 Web 挂件相对安全，但你不应该访问任何可疑网站或打开聊天发送的随机链接。

在Web 挂件中打开的网站始终被阻止访问你的网络摄像头或麦克风。出于安全原因，我们不允许 Web 挂件访问你的网络摄像头/麦克风。

VTube Studio 插件无法通过 API 生成 Web 挂件。Web 挂件显示的任何网站都必须由用户手动打开（或通过先前保存的挂件场景打开）。

如果插件可以访问Web 挂件功能，它将被隐藏在附加 [许可](https://github.com/Denchisoft/VTubeStudio/tree/master/Permissions) 之后。

## Web 挂件和 Steam 创意工坊

Web 挂件无法上传到 Steam 创意工坊。

## API 访问

Web 挂件的一个有趣的地方是它们本身可以是 VTube Studio 插件:

1. 使用 URL `https://website.com/my_vts_plugin_url.html` 将 Web 挂件加载到场景中

2. 该网站使用 JavaScript 连接到 VTube Studio API。

3. 该网站现在是VTube Studio中的一个挂件，同时通过 API 连接到 VTube Studio。

4. 网站可以使用 VTube Studio API 对自己的挂件进行移动、固定、取消固定、删除等操作。

5. 删除挂件后，浏览器进程将退出，API 连接将自动断开。

*注意:* 如果插件想要移动、固定自己的挂件，它需要知道挂件实例 UUID。在 VTube Studio Web 挂件中加载的网站可以在页面加载时使用 JavaScript 接收该 ID，如下所示: ["挂件 UUID 侦听器"](Web-Item-%E2%80%90-Item-UUID-Listener.md) 。

通常，与 Web 挂件相关的 API 访问非常有限:

* VTS 插件无法生成 Web 挂件。

* 你可以使用 API 像普通挂件一样移动、固定和删除 Web 挂件。

* 将来，可能会有更高级的功能，例如让插件加载 URL。如果添加了此权限，则需要额外的授权，该 [授权](https://github.com/Mouwoo/VTubeStudio/tree/master/Permissions) 必须由插件手动请求并由用户授予。

![web_item_api_1](img/img/web_item_api_1.png){: width="587px"}