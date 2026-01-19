此页面包含一些如果 VTube Studio 在你的 PC 上产生延迟时可以尝试的操作。

**请先尝试以下所有方法，然后再在 VTube Studio Discord 中提问！**

## 以管理员身份启动 VTube Studio

在 Windows 上，以管理员身份启动 VTube Studio。 VTube Studio 可以将其 GPU 优先级设置为“高”，这应该可以防止其他需要 GPU 的游戏导致其滞后。但是，这仅在 VTube Studio 以管理员身份运行时有效。

有关如何以管理员身份启动 VTube Studio 的信息，请参阅 [此页面](Starting-as-Admin.md).


## 使用“GPU 优先级”按钮

**仅限英伟达！！**

如果你有 NVIDIA GPU，你可以将 VTube Studio 设置为具有 GPU 优先级。如果你同时玩游戏并且游戏占用了所有 GPU 资源，这会很有帮助。未来它将自动开启，但现在如果你希望 VTube Studio 具有 GPU 优先级，则必须在每次启动 VTube Studio 时按此按钮：:

[[img/img/nvidia_gpu_priority_mode.png]]

## 检查日志

单击 VTube Studio 主菜单中的橙色“日志”按钮。有没有错误？你还可以通过检查“Live2DModels”文件夹旁边的“Logs”文件夹中的文本来查看完整日志。

有时 VTS 中会出现某些问题，并在每一帧都向日志发送带有错误的无用信息，从而导致应用程序速度显着减慢。如果你遇到这种情况，请在 [VTube Studio Discord](https://discord.gg/VTubeStudio) 中提出。

## 关闭所有“性能改进”应用程序（MSI AfterBurner、Norton、Game Fire、BullGuard 等）

在某些情况下，像 `"MSI AfterBurner"` 这样提高游戏性能的应用实际上可能会导致性能/帧速率问题。将它们全部关闭，看看是否有帮助。如果是这样，请检查你是否可以将 VTube Studio 添加为这些应用程序的例外（它们通常以某种方式允许这样做）。

另一个可能导致延迟的应用程序是 `"RTSS Rivatuner"` ，因此也请注意该应用程序。应用 `"Game Fire"` 也可能会导致延迟或冻结。

如果你安装了 Norton/BullGuard，请确保“游戏优化器”设置已关闭。

[[img/img/norton_game_optimizer.png]]

## 检查你的安全软件

如果你正在运行防病毒软件或其他安全软件，请确保将 VTS 添加为例外。已知会导致 VTS 出现问题的一款反恶意软件应用程序是“IObit Malware Fighter”。某些反恶意软件应用程序可能会导致 VTS 运行速度非常缓慢，因此请尝试暂时停用它们，看看是否有帮助。

如果你正在运行 `"FS Protection"` 或 `"F-Secure"` ，请确保将 VTube Studio 添加为例外。事实证明，当 VTube Studio 启动时，这些防病毒应用程序会使 PC 完全崩溃。

## 检查 Windows 任务管理器是否存在性能问题（CPU/GPU 使用情况）

在任务管理器中查看CPU/GPU的实际使用情况。如果你的电脑的 CPU 或 GPU 总使用率接近 100%，请检查哪些应用程序使用率最高。如果它不是 VTube Studio，而是你同时运行的游戏，则你可能需要调整游戏的设置，以便你的 PC 可以同时运行它和 VTube Studio。

如果CPU/GPU使用率未接近100%，则可能存在一些与性能问题无关的其他问题。

## 确保 VTube Studio 中的虚拟摄像头和 NDI 已关闭

如果你不使用 NDI 或虚拟网络摄像头，请确保它们在 VTS 设置中都已关闭。同时打开它们肯定会导致性能问题和滞后。

如果你正在使用其中之一，但对性能影响太大，请尝试使用普通的 OBS `游戏窗口捕捉` 。

## 尝试关闭其他应用并检查 OBS

延迟是仅在你在 OBS 中录制（或打开 OBS）时发生，还是即使 OBS 未运行也一直发生？如果你在OBS中使用某些捕获方法，是否会出现这种情况？只有特定应用程序才会出现这种情况吗？这将是进一步故障排除的重要信息。

## 关闭 NVIDIA G-Sync

NVIDIA G-Sync 可能会导致问题，尤其是在多显示器设置上。 [尝试用这种方法关闭它](https://cn.bing.com/search?q=%E5%A6%82%E4%BD%95%E5%85%B3%E9%97%AD+NVIDIA+G-Sync&form=ANNTH1&refig=65745bbdff1148e5ac684d1b2406a285&pc=CNNDDB) 。

* 右键单击桌面，然后单击菜单中的 `Nvidia Control Panel` 。
* 点击"显示"旁边的 `+` 。
* 选择 `设置 G-SYNC` (不是所有显示器都有此选项)
* 取消选中 `Enable G-SYNC` 旁边的框。

## 降低游戏FPS

确保你使用 VTube Studio 玩的任何游戏都没有将帧速率设置为无限制。如果可能的话，尝试将游戏 FPS 限制为 60。你还可以尝试直接在 `Nvidia Control Panel` 中限制 FPS，如果游戏没有 FPS 设置，这也应该有效。

[[img/img/fps_setting_nvidia_control_panel.png]]

## 修复 GPU 驱动程序中的 FPS

由于某些原因，有时 VTube Studio 中设置的 FPS 值会被忽略，导致其运行不受限。你可以在 GPU 驱动程序中设置固定的 FPS 值。如果你有 NVIDIA GPU，请右键单击桌面，然后单击菜单中的 `Nvidia 控制面板` 。你可以在那里为应用程序设置固定的 FPS 限制（请使用搜索引擎了解如何操作）。


## 检查 VTS "电源模式" 和渲染 GPU

当在笔记本电脑上运行 VTS 时，这一点可能尤其重要。电源设置可能不适用于非笔记本电脑 GPU。

打开 `Nvidia 控制面板`, 转至 `管理3D设置`, 点击 `程序设置` 并选择 `VTube Studio.exe`。然后选择 `最佳性能`.

另外，检查 `OpenGL rendering GPU` 设置。你可以选择运行 VTube Studio 的 GPU。某些笔记本电脑具有集成 GPU 和独立 GPU，你可能需要确保 VTS 在独立 GPU 上运行。

[[img/img/nvidia_control_panel_1.png]]

## 关闭“GPU硬件加速”

同时运行游戏和 VTube Studio 时，GPU硬件加速可能会导致问题。查看搜索引擎（或例如 [此页面](https://www.tenforums.com/tutorials/150440-turn-off-hardware-accelerated-gpu-scheduling-windows-10-a.html) ）以获取有关如何执行此操作的信息。

[[img/img/gpu_scheduling_off.png]]

## 检查 VTube Studio 中的帧速率

当你在应用程序中打开日志（主菜单中的橙色“日志”按钮）时，VTube Studio 将显示实际渲染 FPS。

如果你打开了垂直同步并使用高刷新率显示器，VTube Studio 可能会以非常高的 FPS 运行，从而在同时运行游戏时导致性能问题。尝试在设置中将 VTube Studio 限制为 `1/2 刷新率` 或 `60 FPS` 。

一般来说，建议始终以 60 FPS 运行 VTS。这可能会导致应用程序出现屏幕撕裂，但不会出现在你的 OBS 捕获/推流/录制中。

## 关闭 Steam 界面

全局禁用所有游戏的 Steam 界面。这已被证明会导致某些用户出现帧速率问题。你可以像这样关闭它（参见 `"启用 Steam 叠加层"` ）:

其他软件（如 UPlay）也被证明在与 VTube Studio 同时运行时会因为游戏内覆盖从而给一些用户带来问题。

https://help.steampowered.com/zh-cn/faqs/view/3978-072C-18DF-FBF9

## 不使用 Steam 启动 VTube Studio

尝试使用 `start_without_steam.bat` 文件在 Steam 之外启动 VTube Studio。有关更多信息，请参阅此 Wiki 页面: ["不通过Steam启动应用"](Starting-without-Steam.md)

另外，尝试以管理员身份启动 VTube Studio，看看是否有帮助。你可以通过右键单击 VTube Studio `.exe` 文件，选择 `以管理员身份运行` 来完成此操作。然后，你可以使用 Steam 或使用 `start_without_steam.bat` 正常启动它，如上所述。

## 如果使用 USB 连接 iPhone，请重新启动 iTunes 并清除 iTunes 临时文件

关闭 iTunes（如果它由于某种原因正在运行）和 VTube Studio。

然后，打开资源管理器并在文件夹搜索字段中键入 %ProgramData%\Apple\Lockdown。删除该文件夹中的所有内容，然后尝试再次启动 iTunes 和 VTube Studio 并检查是否仍然出现延迟。

## 设置VTube Studio的进程优先级和GPU优先级

打开Windows任务管理器，转到 `详细信息` 选项卡，右键单击 `VTube Studio.exe` 并在 `设置优先级` 选项下选择 `高` 或 `实时` 。

如果你没有看到该选项卡，则可能需要先点击底部的 `更多详细信息` 。

## 在笔记本电脑（和某些 PC）上，为 VTS 设置“首选 GPU”

许多笔记本电脑都有一个集成 GPU（包含在 CPU 中）和一个通常速度要快得多的专用 GPU。 VTube Studio 可能在较慢的 GPU 上运行。在 Windows 10 中，你可以为每个应用程序设置“首选 GPU”。

[查看搜索引擎了解详细操作](https://cn.bing.com/search?q=%E8%AE%BE%E7%BD%AE%E2%80%9C%E9%A6%96%E9%80%89+GPU%E2%80%9D&form=ANNTH1&refig=6574640ed7d6459182a99d3a5254cba1&pc=CNNDDB) 并将 VTube Studio 设置为在专用 GPU 上运行。

## 检查“省电模式”

许多笔记本电脑和一些台式电脑都有“省电模式”。打开这些会大大降低性能。确保你没有激活任何类似的模式。如果你使用的是笔记本电脑，还要确保它正在充电而不是使用电池运行，因为这有时也会激活省电模式。

## 确保所有软件都是最新的

确保所有涉及的软件都是最新的。特别是以下内容:

* 你的显卡驱动
* OBS 或任何你使用的推流软件
* Steam 上的 VTube Studio (确保你不在测试版分支上)

## 重启

有时，这有助于解决性能问题。

## 如果你有多显示器设置

如果你有多显示器设置，请尝试拔掉一台显示器的插头，看看是否有帮助。如果是这样，这可能是在 VTube Studio Discord 中进一步排除故障的宝贵信息。

## 在 VTube Studio Discord 中提问

如果这些都没有帮助，请通过 VTube Studio Discord 进行询问。

https://discord.gg/VTubeStudio












