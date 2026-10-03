# 截取指定窗口 (CaptureWindow) (CaptureWindow)

精准截取指定软件窗口的画面，即使窗口被遮挡也能清晰截取

## 运行参数

* **目标窗口句柄或标题 (`window`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 窗口句柄数值或标题模糊匹配关键字。
* **窗口索引序号 (`index`)**
  * 类型: `number`
  * 默认值: `0`
  * 描述: 匹配到多个同名窗口时的选择索引。常用预设：`0`, `1`。
* **裁剪尺寸 (w, h) (`size`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 窗口内裁剪宽高。
* **左上角偏移 (x, y) (`top_left`)**
  * 类型: `string`
  * 默认值: `"0, 0"`
  * 描述: 窗口内局部坐标偏移。常用预设：`0, 0`。
* **保存路径 (`output_path`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 保存文件路径。常用预设：``, `C:/temp/window.png`。
* **复制到剪贴板 (`to_clipboard`)**
  * 类型: `number`
  * 默认值: `0`
  * 描述: 复制到剪贴板。常用预设：`0`, `1`。
* **OCR白底优化 (`ocr_optimize`)**
  * 类型: `number`
  * 默认值: `0`
  * 描述: OCR白底优化。常用预设：`0`, `1`。

## 输出

* 类型: `string`
* 描述: 保存的目标窗口截图文件路径或内存图像对象。

## 使用示例

```json
{
    "tag":  "CaptureWindow",
    "window":  "",
    "index":  0,
    "size":  "",
    "top_left":  "0, 0",
    "output_path":  "",
    "to_clipboard":  0,
    "ocr_optimize":  0
}
```
