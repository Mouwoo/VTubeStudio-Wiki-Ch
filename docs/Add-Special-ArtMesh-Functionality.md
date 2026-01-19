**注意：** ArtMesh 是模型的组成部分，本质上对应模型基础 PSD 文件中的图层。你可以为模型的每个 ArtMesh 自定义部分设置。

## 设置图层组
无需为每个 ArtMesh/图层手动配置颜色叠加等功能，你可以先创建一个 [图层组](ArtMesh-Groups.md)，再通过该组将颜色批量应用到组内所有 ArtMesh 上。

## 为模型自定义 ArtMesh 功能
加载模型后，通过以下菜单可为单个 ArtMesh 添加功能。

![Adding functionality to ArtMeshes](img/img/add_functionality_artmeshes_1.png)

对于 Live2D 模型，可为每个 ArtMesh 自定义/添加以下功能：

* [创建图层/ArtMesh 组](ArtMesh-Groups.md)

* 禁止挂件固定到该 ArtMesh 上

* 选择可删除拖放至其上方挂件的 ArtMesh（拖放后挂件将从场景中移除）

* 自定义 [屏幕光源着色系统](Display-Light-Overlay.md) 对该 ArtMesh 的影响效果

* 为 ArtMesh 自定义 [正片叠底/滤色颜色叠加](Recoloring-Models-and-Items.md) 效果

通过此菜单，还可关闭选定 Live2D 参数在经 VNet 传输时的平滑效果，这对重复参数或仅需特定离散值的参数十分实用。

以下章节将对此进行更详细的说明。

### 禁止挂件固定到 ArtMesh
你可以将挂件（PNG、GIF 等格式）固定到 Live2D 模型上，详见 [挂件系统](Item-System.md)。有时你可能希望模型的某些部分不允许固定挂件，这类部分通常是腮红、半透明或透明叠加层等 ArtMesh。只需在列表中关闭对应 ArtMesh 的固定权限即可实现。

![Exclude ArtMeshes from item pinning](img/img/add_functionality_artmeshes_2.png)

### 选择可删除拖放挂件的 ArtMesh
你可以指定部分 ArtMesh，使其能删除任何拖放至自身上方的挂件。例如，可将此功能应用于嘴巴相关的 ArtMesh，实现模型“吃掉”挂件的效果。

### 自定义屏幕光源着色系统对 ArtMesh 的影响
借助 [屏幕光源着色系统](Display-Light-Overlay.md)，你可以将游戏、视频等内容的颜色叠加到模型上。

通过自定义设置，可调整该系统对模型各部分的影响程度。例如，可让模型的眼睛等部位“在暗处发光”，使其更加突出。

![Customize Lighting Overlay System](img/img/add_functionality_artmeshes_3.png)

### 为 ArtMesh 自定义正片叠底/滤色颜色叠加
可为每个 ArtMesh 设置静态的正片叠底/滤色颜色叠加效果，以此对模型进行整体重新着色，比如更改头发或眼睛颜色。

**请注意：** 务必先获得画师许可，再进行此类操作。有关如何使用该功能，以及如何通过热键加载着色预设，详见 [此页面](Recoloring-Models-and-Items.md)。