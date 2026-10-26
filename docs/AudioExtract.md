# AudioExtract - 音视频分离与音频提取

跨平台免重编码高速提取视频中的音频轨道 (MP4 -> MP3/WAV/M4A)，耗时低至毫秒级，且零音质损耗。

## 输入参数

| 参数名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `input_video` | `string` | `""` | 源视频文件路径 (MP4, MOV, MKV) |
| `output_audio` | `string` | `extracted_audio.mp3` | 导出的音频文件路径 |
| `audio_format` | `string` | `auto` | 导出格式：`auto`, `mp3`, `wav`, `m4a` |

## 输出

- 返回导出的音频文件绝对路径。
