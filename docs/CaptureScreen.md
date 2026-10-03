# 截取屏幕 (CaptureScreen) (CaptureScreen)

截取整张电脑屏幕的画面图像，支持保存为文件或复制到剪贴板

## 运行参数

* **显示器名称/编号 (`display_name`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 目标屏幕，留空为默认主屏幕或虚拟跨屏全桌面。常用预设：``, `primary`, `0`, `1`。
* **裁剪尺寸 (w, h) (`size`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 局部截取的宽高。常用预设：``, `1920, 1080`, `1280, 720`。
* **左上角偏移 (x, y) (`top_left`)**
  * 类型: `string`
  * 默认值: `"0, 0"`
  * 描述: 起始坐标偏移。常用预设：`0, 0`, `100, 100`。
* **保存路径 (`output_path`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 保存文件路径。常用预设：``, `C:/temp/screenshot.png`。
* **复制到剪贴板 (`to_clipboard`)**
  * 类型: `number`
  * 默认值: `0`
  * 描述: 复制到系统剪贴板。常用预设：`0`, `1`。
* **OCR白底优化 (`ocr_optimize`)**
  * 类型: `number`
  * 默认值: `0`
  * 描述: 透明通道白底铺平。常用预设：`0`, `1`。

## 输出

* 类型: `string`
* 描述: 保存的屏幕截图文件路径或内存图像对象。

## 使用示例

```json
{
    "tag":  "CaptureScreen",
    "display_name":  "",
    "size":  "",
    "top_left":  "0, 0",
    "output_path":  "",
    "to_clipboard":  0,
    "ocr_optimize":  0
}
```
