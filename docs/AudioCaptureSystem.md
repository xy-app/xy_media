# AudioCaptureSystem - 电脑系统声音内录

基于 WASAPI / CoreAudio 扬声器端点内录，捕获电脑播放的所有声音（播放器、会议、客服电话），存为无损 WAV 文件。

## 输入参数

| 参数名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `action` | `string` | `record_duration` | 动作：`record_duration` (定时), `start` (后台启动), `stop` (停止写盘) |
| `output_path` | `string` | `system_audio.wav` | 导出的 WAV 文件路径 |
| `sample_rate` | `number` | `16000` | 采样率 Hz (推荐 `16000` 用于 ASR 识别，`44100` 用于高质量) |
| `duration` | `number` | `5` | 定时录制秒数 |

## 输出

- 返回生成的 WAV 音频文件绝对路径。
