# 蜂鸣提示音 (SystemBeep) (SystemBeep)

发出系统提示音或警报蜂鸣声，用于流程完成或出错时的声音提醒

## 运行参数

* **提示音类型 (`beep_type`)**
  * 类型: `string`
  * 默认值: `"tone"`
  * 描述: 提示音风格：tone (纯音调频率蜂鸣)、info (系统信息音)、warning (警告音)、error (错误音)、ok (完成音)。常用预设：`tone`, `info`, `warning`, `error`, `ok`。
* **声音频率(Hz) (`frequency`)**
  * 类型: `number`
  * 默认值: `750`
  * 描述: 当 beep_type 为 tone 时的发声声调频率 (Hz)。常用预设：`500`, `750`, `1000`, `1500`。
* **持续时间(毫秒) (`duration_ms`)**
  * 类型: `number`
  * 默认值: `300`
  * 描述: 蜂鸣声发声持续时间 (毫秒)。常用预设：`200`, `300`, `500`, `1000`。

## 输出

* 类型: `number`
* 描述: 系统提示音触发结果回执。

## 使用示例

```json
{
    "tag":  "SystemBeep",
    "beep_type":  "tone",
    "frequency":  750,
    "duration_ms":  300
}
```
