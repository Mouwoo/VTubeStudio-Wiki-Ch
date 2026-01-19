VTube Studio 支持使用macOS上的热键激活，即使 VTube Studio窗口没有焦点。然而，这需要 VTube Studio 在后台读取键盘输入，出于安全原因，这通常不被允许。

所以，要做到这一点，你必须向 VTube Studio 授予两个权限。这两个权限都必须是启动的。

1. “辅助功能”许可。
2. “输入监控”权限。

如果未授予这些权限，则无法读取后台按键。请确保在 macOS 系统设置中激活它们。

### 1. 添加辅助功能权限

* 打开 macOS 系统设置。
* **隐私&安全**  =>  **辅助功能**  => **添加VTube Studio到列表中，并确保切换按钮打开。**
* 如果 VTube Studio 正在运行，请重新启动。

### 2. 添加输入监视权限

* 打开 macOS 系统设置。
* **隐私&安全**  =>  **输入监控**  => **添加VTube Studio到列表中，并确保切换按钮打开。**
* 如果 VTube Studio 正在运行，请重新启动。

### 如何将VTube Studio添加到这些权限列表？

您必须在Steam文件夹中找到VTube Studio的可执行文件。它通常位于这里：

``Macintosh HD > Users > _username_ > Library > Application Support > Steam > steamapps > common > VTube Studio``

如果在用户文件夹中找不到 `Library` 文件夹，请确保像这样取消隐藏它: https://zhuanlan.zhihu.com/p/344192350

⚠️ **确保VTube Studio已添加到两个列表中，并确保它们已打开。** ⚠️ 

[[img/img/macos_acc_bg_3.png]]

[[img/img/macos_acc_bg_2.png]]

[[img/img/macos_acc_bg_4.png]]