⚠️ **此功能面向Live2D建模师，如果你不是建模师可忽略此功能。** ⚠️ 

VTube Studio 通过 **Live2D Cubism 外部集成** 功能直接链接到Live2D Cubism Editor。

该功能可以实现以下效果:

* 你可以将追踪数据从VTS发送到Live2D Cubism Editor。在Live2D Cubism Editor的Live2D物理预览窗口中进行实时面捕跟踪，从而使调整物理效果变得更加容易，因为你可以不用导出模型就直接看到物理效果在面捕中的效果。这个功能也可以用于通过VTube Studio的跟踪数据直接在Live2D Cubism Editor中录制动画。

* VTube Studio可以自动检测你从Live2D Cubism Editor导出的模型，并自动将模型复制到VTube Studio模型文件夹中。

![VTube Studio与Live2D Cubism Editor联动界面](img/img/live2d_api_editor_vts_2.png)

## 如何设置

首先，你需要打开Live2D Cubism Editor API。点击`文件` => `外部应用程序的集成设置...` 然后点击播放键来开启API。

![Live2D Cubism Editor API开启界面](img/img/live2d_api_editor_1.png)

完成后，开始连接到VTube Studio中的Live2D Cubism Editor API（第一个设置选项卡）。如果VTube Studio与Live2D Cubism运行在不同的电脑上，你也可以通过本地网络连接到Live2D Cubism Editor API，方法是打开 `"编辑器在远程电脑上运行"` 并输入运行Live2D Cubism的电脑的本地IP地址，请确保防火墙设置正确。

![VTube Studio中Live2D API连接设置界面](img/img/live2d_api_editor_vts_1.png)

VTube Studio会自动在后台尝试连接/重新连接。第一次连接时，你需要在Live2D Cubism中勾选“授权”复选框。现在，VTube Studio将完全访问Live2D Cubism Editor API。VTube Studio会记住它自己的令牌，所以你只需要手动授权一次。

需要注意的是，VTube Studio会将当前加载模型的所有Live2D参数值发送到Live2D Cubism Editor。因此，只有两边同时加载具有相同Live2D参数的模型时，VTube Studio和Live2D Cubism Editor之间才能正常同步模型动作。

![Live2D Cubism Editor授权界面](img/img/live2d_api_editor_2.png)

## Live2D 编辑器动画录制

你还可以使用它在动画窗口处于活动状态时将跟踪数据发送到Live2D Cubism Editor。这样，你可以使用 VTube Studio 跟踪数据录制单帧或整个动画。

Live2D Cubism Editor动画窗口中有两个按钮。当VTube Studio未连接时，这些按钮将显示为灰色，无法按下。连接 VTube Studio 后，你可以 **按住** 这些按钮来启动接收跟踪数据。

* **快照按钮:** 按住可将当前发送的跟踪数据设置为当前选定的动画帧。按住此按钮，数据就会发送到当前选定的帧，并将覆盖其原本的参数值。

* **录制按钮:** 按住可记录跟踪数据。按住此按钮，动画窗口中的时间轴将会行进，并同时记录关键帧。

使用时要记住几个要点:

* 你始终必须在动画时间轴中选择要向其发送数据的模型。当在时间轴中加载多个模型时，需要选中其中一个模型。显然，你应该在 VTube Studio 中加载匹配的模型，来让发送与接收的参数匹配。

* 你在Live2D Cubism Editor动画窗口中的动画会具有特定的FPS设置，例如60。而VTube Studio 将始终以当前应用程序 FPS 发送数据。这意味着两者之间可能存在轻微的 FPS 不匹配，即使你将它们设置为相同的目标 FPS。在某些情况下，这可能会导致错过某些帧，即在编辑器中未收到动画的数据。不过问题不大，因为编辑器会自动在帧之间进行插值，使动作保持流畅。但是在进行覆盖现有的动画数据时，这可能会导致一些严重问题，因为在现有动画数据上进行新的录制时，新接收到的动画数据将仅填补那些“缺失的帧”，导致原有帧与新录制的帧交错出现。因此，不建议在现有动画数据上直接进行录制。相反，在开始新录制之前，请先在时间轴中删除原有的参数关键帧。

![VTube Studio向Live2D Editor发送动画数据界面](img/img/live2d_api_editor_vts_anim.png)

## 快捷键

当你在Live2D Cubism中编辑模型时，你可能希望启动/停止将参数从VTS发送到编辑器中。

要做到这一点，你可以在VTube Studio中设置一个快捷键来打开/关闭发送参数数据。快捷键类型为 `"Live2D Editor API 参数同步"` 。

## 性能

VTube Studio会在每一帧时将所有参数值发送到Live2D Cubism Editor中。对于在Live2D Cubism Editor中会以低帧率运行的庞大模型，这可能会导致编辑器卡死。

如果你的模型出现这种情况，建议仅在打开Live2D Cubism中的物理模拟窗口时使用参数同步功能，因为物理窗口运行通常比较平稳。

要确保VTube Studio仅在开启物理模拟窗口时发送参数数据，请打开 `"仅物理窗口"` 。