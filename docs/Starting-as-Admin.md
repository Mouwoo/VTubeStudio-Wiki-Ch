在 Windows 上以管理员身份启动 VTube Studio 可以解决一些问题，例如当 VTube Studio 窗口未处于焦点时快捷键不起作用。

此外，VTube Studio 在以管理员身份启动时会尝试将其 GPU 优先级设置为`高`。建议始终以管理员身份启动 VTube Studio，尤其是在遇到 VTube Studio 延迟问题时。

要以管理员身份启动VTube Studio，请找到`.exe文件`，右键单击它，单击`属性`，转到`兼容性`选项卡并选中`以管理员身份运行此程序`。

然后使用 Steam 或`start_without_steam.bat`文件正常启动 VTS。

![以管理员身份运行VTube Studio设置界面](img/img/start_as_admin_1.png)