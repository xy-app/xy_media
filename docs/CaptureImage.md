# CaptureImage - 通用画面截图

通用聚合型图像捕获动作，支持全屏、聚焦窗口、句柄指定窗口及绝对坐标区域 (ROI) 裁切，内置 OCR 透明通道白底平铺优化。

## 输入参数

| 参数名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `capture_type` | `string` | `Screen` | 截图模式：`Screen` (屏幕), `Window` (指定窗口), `ActiveWindow` (前台聚焦窗口), `Region` (区域) |
| `window` | `wnd` | `""` | 目标窗口标题或句柄表达式（仅在 Window 模式生效） |
| `display_name` | `string` | `primary` | 显示器编号 (`primary`, `0`, `1`) |
| `top_left` | `string` | `0, 0` | 裁剪起始坐标偏移 `x, y` |
| `size` | `string` | `""` | 截取尺寸 `w, h` (留空截全屏/全窗口) |
| `output_path` | `string` | `""` | 文件保存路径 (留空存入内存变量 Image) |
| `to_clipboard` | `number` | `0` | 是否写入系统剪贴板 (`0` 否, `1` 是) |
| `ocr_optimize` | `number` | `0` | 透明 Alpha 通道平铺为纯白背景提升 OCR 识别率 |

## 输出

- 运行成功返回保存的文件绝对路径，或在内存上下文中生成 `Image` 对象。
