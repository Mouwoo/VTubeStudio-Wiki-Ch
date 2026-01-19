**注意:** ArtMesh(图形网格)是模型的一部分。它们是模型的基础 PSD 中的图层。某些设置可以根据 ArtMesh 为你的模型进行自定义。

## 为模型自定义 ArtMesh 功能

你可以通过先加载模型，然后访问以下菜单，为模型中的单个 ArtMeshs 添加功能。

[[img/img/add_functionality_artmeshes_1.png|alt="Adding functionality to ArtMeshes"]]

对于Live2D模型，可以对ArtMesh自定义/添加以下功能：

* 使ArtMeshes无法被挂件吸附
* 使ArtMeshes删除吸附与它的挂件
* 为ArtMeshes自定义 [屏幕光源着色](Display-Light-Overlay.md)
* 为ArtMeshes自定义 [正片叠底/滤色颜色](Recoloring-Models-and-Items.md)

接下来将进行详细介绍。

### 使ArtMeshes无法被挂件吸附

可将挂件（PNG、GIF等）固定到Live2D模型中，详见 "[挂件系统](Item-System.md)" 。 有时，你可能希望从中排除模型的某些部分，并确保挂件无法固定到它们。通常是腮红、半透明或不可见的叠加层等ArtMeshes。你可以通过在列表中关闭它们来执行此操作。

[[img/img/add_functionality_artmeshes_2.png|alt="Exclude ArtMeshes from item pinning"]]

### 使ArtMeshes删除吸附于它的挂件

你可以选择 ArtMesh，以删除拖放到其上的任何挂件。例如，你可以将其用于与嘴巴相关的 ArtMeshes，让你的模型“吃掉”挂件。

### 为ArtMeshes自定义屏幕光源着色

使用 [屏幕光源着色](Display-Light-Overlay.md) 系统, 你可以将模型与游戏、视频等中的颜色叠加在一起。

你可以自定义此系统对模型各部分的影响程度。例如，使用此自定义，你可以通过使模型的某些部分（如眼睛）“在黑暗中发光”来使它们更加突出。

[[img/img/add_functionality_artmeshes_3.png|alt="Customize Lighting Overlay System"]]

### 为ArtMeshes自定义正片叠底/滤色颜色

你可以为每个 ArtMesh 设置正片叠底/滤色颜色并以这种方式完全重新着色你的模型，例如更改头发或眼睛的颜色。

请在获得你的画师的许可后再这样做。有关如何使用此功能以及如何使用快捷键加载重新着色预设的更多信息，请参阅 [这一页](Recoloring-Models-and-Items.md) 。