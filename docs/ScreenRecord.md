# 屏幕录制 (ScreenRecord) (ScreenRecord)

录制桌面屏幕或指定窗口的操作过程，一键导出为轻量级 GIF 动图

## 运行参数

* **录制动作 (`action`)**
  * 类型: `string`
  * 默认值: `"record_duration"`
  * 描述: 录制操作：record_duration (录制指定秒数)、start (后台启动录屏)、stop (停止录屏并导出)。常用预设：`record_duration`, `start`, `stop`。
* **输出路径 (.gif) (`output_path`)**
  * 类型: `string`
  * 默认值: `"record.gif"`
  * 描述: 生成的 GIF 动图保存路径。常用预设：`record.gif`, `C:/temp/audit_trace.gif`。
* **录制帧率 (FPS) (`fps`)**
  * 类型: `number`
  * 默认值: `10`
  * 描述: 录屏采样帧率 (建议 5-15 FPS 以降低文件体积)。常用预设：`5`, `10`, `15`, `20`。
* **录制定时时长(秒) (`duration`)**
  * 类型: `number`
  * 默认值: `5`
  * 描述: 在 record_duration 模式下的录制时长。常用预设：`3`, `5`, `10`, `30`。
* **目标窗口 (空为全桌面) (`target_window`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 限定录制的特定窗口标题/句柄，留空录制全桌面。常用预设：``, `Chrome`, `Edge`, `Notepad`。
* **分辨率缩放倍率 (`scale`)**
  * 类型: `number`
  * 默认值: `0.5`
  * 描述: 采样分辨率等比例缩放系数 (0.1 - 1.0)。常用预设：`0.5`, `0.75`, `1.0`。

## 输出

* 类型: `string`
* 描述: 录制生成的 GIF 动图文件路径或录制状态回执。

## 使用示例

```json
{
    "tag":  "ScreenRecord",
    "action":  "record_duration",
    "output_path":  "record.gif",
    "fps":  10,
    "duration":  5,
    "target_window":  "",
    "scale":  0
}
```
