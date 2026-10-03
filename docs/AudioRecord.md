# 录音到文件 (AudioRecord) (AudioRecord)

通过麦克风录制声音并保存为高质量音频文件

## 运行参数

* **录制模式 (`action`)**
  * 类型: `string`
  * 默认值: `"record_duration"`
  * 描述: 录制动作模式：record_duration (指定时长录制)、start (后台启动录音)、stop (停止录音并保存)。常用预设：`record_duration`, `start`, `stop`。
* **WAV保存路径 (`output_path`)**
  * 类型: `string`
  * 默认值: `"recording.wav"`
  * 描述: 录音文件保存的完整路径 (仅限 .wav 格式)。常用预设：`recording.wav`, `C:/temp/voice.wav`。
* **录音时长(秒) (`duration`)**
  * 类型: `number`
  * 默认值: `5`
  * 描述: 在 record_duration 模式下的录音持续时间 (秒)。常用预设：`3`, `5`, `10`, `30`。
* **音频采样率(Hz) (`sample_rate`)**
  * 类型: `number`
  * 默认值: `16000`
  * 描述: 音频采样率频率 (语音识别建议 16000 Hz)。常用预设：`8000`, `16000`, `44100`。

## 输出

* 类型: `string`
* 描述: 生成的录音文件绝对路径或录制状态。

## 使用示例

```json
{
    "tag":  "AudioRecord",
    "action":  "record_duration",
    "output_path":  "recording.wav",
    "duration":  5,
    "sample_rate":  16000
}
```
