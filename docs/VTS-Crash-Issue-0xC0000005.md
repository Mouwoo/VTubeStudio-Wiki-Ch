如果你的 VTube Studio 在使用几分钟后在 Windows 上多次随机崩溃，并且崩溃与你在 VTS 中执行某些操作（例如打开摄像头）没有关联，则崩溃可能是由硬件问题引起的。如果你刚刚升级了电脑的一部分，或者其他应用程序/游戏在一段时间后以同样的方式崩溃，这种情况会更容易发生。

导致此类崩溃的硬件问题通常与 内存、CPU 或主板有关。

首先要做的是检查崩溃日志。在资源管理器中输入 `%TMP%\Denchi\` 。找到 `Crashes` 文件夹。在该文件夹中，你将看到名称类似于  `Crash_2024-07-08_084334446` 的文件夹列表。打开最近的文件夹并找到player.log文件。该文件内容末尾将包含一些有关崩溃的信息，如下所示:

```
========== OUTPUTTING STACK TRACE ==================

0x00007FFD0A273EE2 (UnityPlayer) UnityMain
0x00007FFD0A27591A (UnityPlayer) UnityMain
0x00007FFD0A27248C (UnityPlayer) UnityMain
0x00007FFD0A3EB43D (UnityPlayer) UnityMain
0x00007FFD0A3EB6F4 (UnityPlayer) UnityMain
0x00007FFD0A2A627A (UnityPlayer) UnityMain
0x00007FFD0A2A6320 (UnityPlayer) UnityMain
0x00007FFD0A2AA5B8 (UnityPlayer) UnityMain
  ERROR: SymGetSymFromAddr64, GetLastError: 'Attempt to access invalid address.' (Address: 00007FFD0A0678AA)
0x00007FFD0A0678AA (UnityPlayer) (function-name not available)
  ERROR: SymGetSymFromAddr64, GetLastError: 'Attempt to access invalid address.' (Address: 00007FFD0A065D7B)
0x00007FFD0A065D7B (UnityPlayer) (function-name not available)
  ERROR: SymGetSymFromAddr64, GetLastError: 'Attempt to access invalid address.' (Address: 00007FFD0A06AE12)
0x00007FFD0A06AE12 (UnityPlayer) (function-name not available)
0x00007FFD0A06BFBB (UnityPlayer) UnityMain
  ERROR: SymGetSymFromAddr64, GetLastError: 'Attempt to access invalid address.' (Address: 00007FF7B3C011F2)
0x00007FF7B3C011F2 (VTube Studio) (function-name not available)
0x00007FFD6094257D (KERNEL32) BaseThreadInitThunk
0x00007FFD6234AF28 (ntdll) RtlUserThreadStart

========== END OF STACKTRACE ===========
```

有时，这将包含有关导致崩溃的确切原因的更多信息，因此请确保在 VTube Studio Discord 中共享该文件。

然而，有时没有更多信息。在这种情况下，很可能存在硬件问题。

## 可以尝试的方法

* 确保你的 GPU 驱动程序是最新的。
* 确保你的 Windows 版本是最新的。
* 运行一个内存检查工具，如下所示:
  * MemTest64: https://www.techpowerup.com/memtest64/
  * 如果此工具发现错误，则表明你的 RAM 有故障或 BIOS 中的时序设置错误。
  * 如果有的话，你可以尝试通过关闭 XMP/EXPO 来修复该问题: [Turn off XMP](https://www.quora.com/What-is-XMP-on-a-PC-motherboard-and-how-do-you-disable-it).
  * 你还可以尝试在 BIOS 中稍微降低 RAM 频率，看看是否可以修复内存错误。
* VTS 运行时监控 GPU/CPU 温度。是否产生了异常升温？如果是这样，你可能需要检查你的 CPU/GPU 冷却。
* 重新启动你的电脑。
* 检查你正在运行的其他软件。 特别是像 "游戏加速器" (MSI AfterBurner, BullGuard 等) 或第三方安全软件 (Avast等) 之类的软件，因为这些软件可能会以某种方式干扰 VTube Studio。如果这解决了问题，请尝试找出具体是哪个应用程序引起的。如果你正在使用第三方安全软件，请尝试暂时禁用它们。
* Citrix VPN 已被证明会导致许多基于 Unity 的应用程序（例如 VTS）出现此问题，因此请确保你没有同时运行该应用程序。
* 如果你使用的是笔记本电脑，请检查电源设置并确保未处于省电模式。
* 尝试 [以管理员启动 VTube Studio](Starting-as-Admin.md) 。
* 下载安装最新的 [Visual C++ Redistributable](https://learn.microsoft.com/zh-cn/cpp/windows/latest-supported-vc-redist?view=msvc-170).
* 关闭 Steam 游戏内覆盖并尝试 [不通过Steam启动 VTube Studio](Starting-without-Steam.md) 。
* 如果你有多个内存条，依次尝试单独使用其中的一个来启动电脑。如果问题发生在某一特定内存条上，则该内存条可能有故障。
* 更新你的 BIOS (UEFI)。旧的 BIOS 版本有可能是产生随机崩溃的原因。
* 在 BIOS 设置中，尝试以下操作:
  * 检查你的内存条频率并尝试降低它。例如，如果你的内存条设置为 3600 MHz，请尝试将其设置为 2133 MHz。
  * [关闭 XMP](https://www.quora.com/What-is-XMP-on-a-PC-motherboard-and-how-do-you-disable-it).
  * 关闭 Intel Turbo Boost（它位于你的 BIOS 设置中，并且默认启用）。
  * 如果你对 CPU 进行了超频，请尝试再次将其设置为出厂默认值。


