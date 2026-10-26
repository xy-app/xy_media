# AudioPlayer - 音频播放与控制

聚合型音频播控动作，支持本地音频 (WAV, MP3 等) 播放、停止音频通道/流，以及发出硬件/系统蜂鸣提示音。

## 输入参数

| 参数名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `action` | `string` | `play` | 动作模式：`play` (播放), `stop` (停止), `beep` (蜂鸣提示音) |
| `file_path` | `string` | `""` | 本地音频文件路径 (WAV, MP3, OGG, FLAC) |
| `volume` | `number` | `80` | 音量大小 (0 ~ 100) |
| `repeat` | `number` | `0` | 是否循环播放 (`0` 单次, `1` 循环) |
| `wait` | `number` | `0` | 是否阻塞等待播放完毕 |
| `channel` | `string` | `""` | 停止模式下的音频通道别名 (留空停止默认) |
| `beep_type` | `string` | `tone` | 蜂鸣类型：`tone` (指定频率), `info`, `warning`, `error`, `ok` |
| `frequency` | `number` | `750` | 声音频率 Hz (仅在 tone 模式生效) |
| `duration_ms` | `number` | `300` | 蜂鸣持续毫秒数 |

## 输出

- 返回播放的文件路径或操作成功标志。
