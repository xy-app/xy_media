# 滚动截取长图 (CaptureScroll) (CaptureScroll)

自动模拟向下滚动并无缝拼接成超长网页或聊天记录截图

## 运行参数

* **目标窗口 (空为前台焦点) (`target_window`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 滚动的目标窗口标题或句柄。常用预设：``, `Chrome`, `Edge`, `Notepad`。
* **滚动方向 (`scroll_direction`)**
  * 类型: `string`
  * 默认值: `"down"`
  * 描述: 滚轮滚动方向 (down/up)。常用预设：`down`, `up`。
* **单次滚轮步长 (`scroll_clicks`)**
  * 类型: `number`
  * 默认值: `5`
  * 描述: 每次滚动步骤发送的滚轮刻度数。常用预设：`3`, `5`, `8`, `10`。
* **最大滚动页数 (`max_pages`)**
  * 类型: `number`
  * 默认值: `5`
  * 描述: 最大滚动采样的图片页数。常用预设：`3`, `5`, `10`, `15`。
* **滚动间歇停顿(ms) (`delay_ms`)**
  * 类型: `number`
  * 默认值: `400`
  * 描述: 单次滚动后等待网页/界面重新渲染的沉降时间。常用预设：`300`, `400`, `600`, `1000`。
* **重叠比例(%) (`overlap_pct`)**
  * 类型: `number`
  * 默认值: `20`
  * 描述: 连续帧之间的缝合重叠预估比例。常用预设：`10`, `20`, `30`。
* **保存路径 (`output_path`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 长截图存盘路径。常用预设：``, `C:/temp/scroll_long.png`。
* **复制到剪贴板 (`to_clipboard`)**
  * 类型: `number`
  * 默认值: `0`
  * 描述: 复制到系统剪贴板。常用预设：`0`, `1`。
* **OCR白底优化 (`ocr_optimize`)**
  * 类型: `number`
  * 默认值: `0`
  * 描述: OCR优化。常用预设：`0`, `1`。

## 输出

* 类型: `string`
* 描述: 拼接生成的全景长图文件路径或内存图像对象。

## 使用示例

```json
{
    "tag":  "CaptureScroll",
    "target_window":  "",
    "scroll_direction":  "down",
    "scroll_clicks":  5,
    "max_pages":  5,
    "delay_ms":  400,
    "overlap_pct":  20,
    "output_path":  "",
    "to_clipboard":  0,
    "ocr_optimize":  0
}
```
