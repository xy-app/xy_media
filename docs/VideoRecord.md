# VideoRecord - 高清 MP4 视频屏录

原生硬件加速屏录，生成高帧率高清标准 MP4 视频文件，支持系统内录+麦克风双声道加权混音，以及30秒内存环形队列异常/崩溃回溯录像存盘。

## 核心特性

- **双声道加权混音**：支持系统播音 Loopback + 麦克风采样的加权衰减防爆音 PCM 混音，录屏时可同时留存系统发音与演示者解说。
- **30秒崩溃/异常回溯**：开启 `start_rolling` 内存环形队列录屏，在平时不占用磁盘空间。当流程捕获到 Error 或 Catch 节点捕获到目标应用闪退时，执行 `dump_rolling` 瞬间写盘导出报错发生前 30 秒的视频录像。

## 输入参数

| 参数名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `action` | `string` | `record_duration` | 录制动作：`record_duration` (定时), `start` (开启), `stop` (停止), `start_rolling` (常驻内存录屏), `dump_rolling` (崩溃瞬间导出) |
| `output_path` | `string` | `recording.mp4` | 导出的 MP4 视频文件路径 |
| `fps` | `number` | `30` | 录制帧率 (15, 24, 30, 60) |
| `duration` | `number` | `10` | 定时录制时长 (秒) |
| `target_window` | `wnd` | `""` | 目标窗口标题/句柄 (留空录制全屏) |
| `audio_source` | `string` | `system_and_mic` | 音频源：`system_and_mic` (双声道混音), `system_only`, `mic_only`, `none` |

## 输出

- 返回导出的 MP4 视频文件绝对路径。
