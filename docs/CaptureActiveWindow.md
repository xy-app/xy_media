# 截取当前活动窗口 (CaptureActiveWindow) (CaptureActiveWindow)

截取当前最前方的活动软件窗口图像，可保存为文件或复制到剪贴板

## 运行参数

* **裁剪尺寸 (w, h) (`size`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 局部截取的宽高，留空截取整个窗口。常用预设：``, `800, 600`, `1280, 720`。
* **左上角偏移 (x, y) (`top_left`)**
  * 类型: `string`
  * 默认值: `"0, 0"`
  * 描述: 相对于活动窗口客户区左上角的裁剪起始坐标。常用预设：`0, 0`, `10, 10`, `50, 50`。
* **保存路径 (`output_path`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 截图直接存盘路径，留空则返回内存 Image 对象。常用预设：``, `C:/temp/active_window.png`。
* **复制到剪贴板 (`to_clipboard`)**
  * 类型: `number`
  * 默认值: `0`
  * 描述: 是否同步复制截图至系统剪贴板 (1为是，0为否)。常用预设：`0`, `1`。
* **OCR白底优化 (`ocr_optimize`)**
  * 类型: `number`
  * 默认值: `0`
  * 描述: 是否自动将透明/半透明通道平铺为纯白背景以提升 OCR 识别率。常用预设：`0`, `1`。

## 输出

* 类型: `string`
* 描述: 保存的截图文件路径或内存图像对象。

## 使用示例

```json
{
    "tag":  "CaptureActiveWindow",
    "size":  "",
    "top_left":  "0, 0",
    "output_path":  "",
    "to_clipboard":  0,
    "ocr_optimize":  0
}
```
