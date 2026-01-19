以下是在 Linux（特别是 Arch Linux）上使用 **OpenSeeFace** 人脸跟踪运行 **VTube Studio** 的说明。这将需要一些关于 Linux 的技术知识，不建议初学者使用，但如果你正在阅读这篇文章，我相信你已经意识到了这一点。

感谢 **Ruyi#0110** 制作本指南。

## 指南：在 Linux 上使用 OpenSeeFace 网络摄像头跟踪运行 VTube Studio

使用的发行版：**Arch Linux** 。$符号表示命令行的开头，不要包含它。

### 安装 python39

`$ sudo pacman -Sy python39` 

请注意，如果没有 `sudo` ， `pacman` 就无法运行。 `pacman` 是所使用的 Arch 安装上的包管理器，你的可能会有所不同。

`-Sy` 是 `pacman` 的参数，作用是告诉它更新镜像并安装软件包。

`python39` 是包名称本身(我认为在 Ubuntu 上它可能被称为 `python3.9`).


### 安装要求

`$ sudo pacman -Sy python-pip python-virtualenv git`


`python-pip` 是我们用来在虚拟环境中安装东西的东西。

`python-virtualenv` 是虚拟环境本身。

`git` 将帮助我们下载 `OpenSeeFace` 。同样，包名称可能不同。你可能已经安装了一些软件包。


_注意:_ Ubuntu 24.04 设置 python 环境的等效命令是:
```bash
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
sudo apt-get install python3.9-distutils
python3.9 -m pip install tomli
virtualenv -p python3.9 env
```



### 下载/安装 OpenSeeFace

`$ git clone https://github.com/emilianavt/OpenSeeFace`

然后进入其文件夹：

`$ cd OpenSeeFace`

并创建虚拟环境：

`$ virtualenv -p python39 env`

然后启动虚拟环境：

`$ source env/bin/activate`

并安装facetracker运行所需的所有东西：

`$ pip install onnxruntime opencv-python pillow numpy==1.26.1`

`numpy` 不同的原因是我们需要特定旧版本的 `numpy` 。

最后，在启动Facetracker之前，我们需要确保VTube Studio可以看到它。

右键点击Steam库中的Vtube Studio，点击属性>已安装文件>浏览。

转到Vtube Studio_Data > StreamingAssets并打开ip.txt（如果没有则创建一个）。

在这里，你需要确认两件事: 
`ip=0.0.0.0`
以及
`port=11573`

请确保在编辑/添加它们后进行保存。现在，Vtube Studio将监听Facetracker的正确IP和端口。

这就是奇迹发生的地方！返回到你的终端并输入:

`$ python facetracker.py  -W 1280 -H 720 --discard-after 0 --scan-every 0 --no-3d-adapt 1 --max-feature-updates 900 -c 0`

请注意，`-c 0` 代表你的相机。通常是 `0` 但如果你有多个摄像头（例如 Valve 索引中的摄像头），你可能需要在此处使用不同的数字(尝试 `1` , `2` , ...)

### 启动 VTube Studio

现在你应该能够打开 VTube Studio，选择 `VTubeStudioCam` 并使用（如果分辨率显示为 4x4，请不要担心，我们需要的只是其中的 `OpenSeeFace` 信息）。

请注意，每次要使用 `OpenSeeFace` 时都需要启动虚拟环境，使用以下三个命令:


*  `$ cd OpenSeeFace`

*  `$ source env/bin/activate`

*  `$ python facetracker.py -c 0 -W 1280 -H 720 --discard-after 0 --scan-every 0 --no-3d-adapt 1 --max-feature-updates 900`

请注意，`-c 0` 代表你的相机。通常是 `0` 但如果你有多个摄像头（例如 Valve 索引中的摄像头），你可能需要在此处使用不同的数字(尝试 `1` , `2` , ...)