# 截取指定区域 (CaptureRegion) (CaptureRegion)

截取屏幕上指定矩形区域的画面图像

## 运行参数

* **区域坐标 (x, y, w, h) (`region`)**
  * 类型: `string`
  * 默认值: `"0, 0, 800, 600"`
  * 描述: 屏幕绝对坐标选区范围 (x, y, 宽, 高)。常用预设：`0, 0, 800, 600`, `100, 100, 400, 300`, `200, 200, 1280, 720`。
* **显示器 (空为主屏幕) (`display_name`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 多显示器环境下的目标显示器编号或名称。常用预设：``, `primary`, `0`, `1`。
* **保存路径 (`output_path`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 保存文件的绝对路径。常用预设：``, `C:/temp/region.png`。
* **复制到剪贴板 (`to_clipboard`)**
  * 类型: `number`
  * 默认值: `0`
  * 描述: 是否复制到系统剪贴板。常用预设：`0`, `1`。
* **OCR白底优化 (`ocr_optimize`)**
  * 类型: `number`
  * 默认值: `0`
  * 描述: OCR白底透平优化。常用预设：`0`, `1`。

## 输出

* 类型: `string`
* 描述: 保存的区域截图文件路径或内存图像对象。

## 使用示例

```json
{
    "tag":  "CaptureRegion",
    "region":  "0, 0, 800, 600",
    "display_name":  "",
    "output_path":  "",
    "to_clipboard":  0,
    "ocr_optimize":  0
}
```
