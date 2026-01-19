### 从2023年6月开始，你可以在Steam平台（macOS和Windows系统）上恢复VTube Studio的旧版本

通常情况下，我建议你始终使用最新版本，并在[VTube Studio Discord社区](https://discord.gg/VTubeStudio)中反馈遇到的任何漏洞，以便开发者尽快修复。但在某些紧急情况下，临时回滚到对你而言运行更稳定的旧版本是合理的选择。

需要注意的是，若要让[VNet 多人联机](Multiplayer.md)功能正常工作，所有协作参与者都应使用相同版本的VTube Studio。不过，如果不同版本使用的是相同的虚拟网络编码版本，它们也可能相互兼容。

如果你切换到了VTube Studio的**旧版本分支**，Steam将**不再自动更新**该软件，且在你切回常规公开发布版本之前，**不会收到任何后续的更新和漏洞修复**。

同时，无法保证这些Steam旧版本会永久兼容**VNet 多人联机**功能以及**iOS和Android移动端应用**。因此，请仅在别无选择时才进行版本回滚，并尽快切回当前的公开发布版本。

![steam_vts_old_versions_1](img/img/steam_vts_old_versions_1.png)

## 如何恢复旧版本？

⚠️ **重要提示：** 在切换到旧版本之前，请为你所有的模型、挂件和背景制作备份副本！具体操作是将`Live2DModels`、`Items`和`Backgrounds`文件夹复制到VTube Studio的Steam安装目录之外的位置。版本切换本身不会删除任何文件，但鉴于曾有报告显示Steam更新会随机删除模型文件，最好还是做好万全准备！⚠️

旧版本以**Steam测试分支**的形式提供。

在你的Steam游戏库中，右键点击`VTube Studio`，选择`属性...` → `测试版`。在该页面中，你会看到一个下拉列表，其中包含所有可用的旧版本。

你可以随时通过在测试版选项中选择`无`，切回常规版本分支。

再次提醒，请务必在尝试切换到VTube Studio旧版本**之前**，备份好你所有的资源文件。

![steam_vts_old_versions_2](img/img/steam_vts_old_versions_2.png)