
[[img/img/hint_top.png]]
[[img/img/bunny_point.png|alt="Important Point!!"|height=59px|width=189px]]<br/>
**_重要!!_**

**只有在获得模型画师许可的情况下才能使用此功能。许多画师不希望他们的艺术作品以任何方式被修改或重新着色，并认为这是不礼貌的，所以请在使用此功能之前询问你的画师，并始终尊重他们的意愿!!**
[[img/img/hint_bottom.png]]

## 重新着色模型

你可以重新着色主 VTube Studio 模型中的所有图形网格（模型的一部分）以及加载到场景中的任何 [Live2D挂件](Item-System.md) 你还可以使用快捷键保存/加载重新着色预设。 **在进行任何操作之前，请先获得你的画师的许可。**

要重新着色当前加载模型的图形网格，请打开模型设置选项卡并单击 **"自定义模型"** 。然后，选择 **“为ArtMeshes自定义正片叠底/滤色颜色”** 。

[[img/img/add_functionality_artmeshes_1.png|alt="Adding functionality to ArtMeshes"]]

这将让你为每个图形网格设置正片叠底和屏幕覆盖色。这些颜色更改会与你的模型一起保存，并在你下次重新加载模型时加载

[[img/img/live2d_item_recolor.png|alt="Recoloring your model ArtMeshes"]]

### 使模型的某些部分不可见

你还可以使图形网格不可见或半透明。为此，请使用 ArtMesh 的 `正片叠底` 设置上的 `A / Alpha` 滑块。

## 重新着色 Live2D 挂件

对 Live2D 挂件执行同样的操作也很容易。有关更多信息请查看 Live2D 挂件页面: https://github.com/Mouwoo/VTubeStudio/wiki/Item-System

## 保存并通过快捷键加载颜色预设

你还可以使用 **快捷键** 为场景中的任何模型或 Live2D 挂件加载这些滤色/正片叠底颜色预设。为此，请使用要注册的 ArtMesh 颜色准备模型，然后创建 **“ArtMesh 颜色预设”类型** 的新快捷键。使用快捷键 UI 上的 **“记录设置”** 按钮记录当前设置。然后可以使用该快捷键加载/卸载该滤色/正片叠底颜色预设。

你还可以使用空设置创建该类型的快捷键，以创建删除该模型当前加载的颜色预设的快捷键。

[[img/img/live2d_item_recolor_hotkey.png]]




