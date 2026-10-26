# CameraCapture - 相机与视频流抓拍

聚合型相机抓拍动作，支持 USB 摄像头 / RTSP 视频流单次自动抓拍、句柄常驻连拍模式及显式关闭。

## 输入参数

| 参数名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `action` | `string` | `auto_capture` | 模式：`auto_capture` (自动抓拍), `open` (常驻打开), `get_frame` (抽帧), `close` (关闭) |
| `device` | `string` | `0` | 本地硬件设备索引 (`0`, `1`) 或网络 RTSP 流 URL |
| `size` | `string` | `""` | 期望分辨率尺寸 `w, h` |
| `output_path` | `string` | `""` | 抓拍保存路径 (留空存内存 Image 对象) |
| `to_clipboard` | `number` | `0` | 是否拷贝到系统剪贴板 |
| `output_var` | `string` | `camera` | 存储相机句柄的变量名 |

## 输出

- 返回导出的文件路径、抓拍的 `Image` 对象或相机句柄变量。
