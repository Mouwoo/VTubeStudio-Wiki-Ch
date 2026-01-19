这是当前版本的 VTube Studio 中已知的问题/错误列表

## 不支持的设备: 任何版本的三星 S22

由于与所使用的跟踪库不兼容，面部跟踪将无法在 Samsung S22 设备上运行。该库已停止使用，因此我对此无能为力。如果 VTube Studio 切换到更好的跟踪库，兼容性可能会恢复。

## MacOS 崩溃问题

从 `macOS 14 Sonoma` 开始，一些用户报告 macOS 上出现间歇性崩溃。到目前为止，还无法确定这些崩溃的根本原因，也没有预计的修复时间。 M2 Mac 上的崩溃似乎更加频繁。

对于某些用户来说，删除 `Live2DModels` 文件夹旁边的 `Config` 文件夹可能会有所帮助，此外， [不通过steam启动VTS](Starting-without-Steam.md) 也能解决这个问题。

## MacOS 缺少的功能

* <s>后台热键无法工作</s> macOS 上的 VTube Studio 已经能够支持程序未处于焦点时的热键。

* 摄像头跟踪支持正处于实验阶段并拥有一定限制。不建议在 macOS 上使用网络摄像头跟踪。请改用 iPhone 跟踪。

* 不支持 NVIDIA 摄像头跟踪。

* 不支持使用“虚拟摄像头”将视频输出到其他应用程序。

* 不支持通过Spout2将视频输出到OBS。请使用 NDI 获得透明背景推流。

* [请使用 NDI](Recording-Streaming-with-OBS.md#ndi-obs) 获得透明背景推流，但可能会导致CPU占用率较高。