# MediaWatermark - 媒体水印与打码脱敏

为截图、图片或视频叠加动态文字水印（机器名/时间戳/防泄密标记），或对敏感区域进行像素级马赛克与高斯模糊脱敏。

## 核心特性

- **多样式处理**：支持 `watermark` (文字水印)、`mosaic` (像素级马赛克打码)、`blur` (高斯模糊)。
- **敏感信息脱敏**：指定 `mask_region` ROI 矩形区域，对身份证号、银行卡号、手机号与密码框进行安全打码，防止截图/录屏泄密。

## 输入参数

| 参数名 | 类型 | 默认值 | 说明 |
| :--- | :--- | :--- | :--- |
| `style` | `string` | `watermark` | 处理样式：`watermark` (文字水印), `mosaic` (马赛克), `blur` (高斯模糊) |
| `input_path` | `string` | `""` | 源图片或视频路径 |
| `watermark_text` | `string` | `CONFIDENTIAL` | 叠加的水印文本 (仅在 watermark 模式生效) |
| `mask_region` | `string` | `""` | 打码脱敏矩形区域 `x, y, w, h` (仅在 mosaic/blur 模式生效，留空全图打码) |
| `position` | `string` | `bottom_right` | 水印对齐位置：`bottom_right`, `bottom_left`, `top_right`, `center`, `tile` (平铺) |
| `opacity` | `number` | `0.5` | 不透明度 (`0.1` 到 `1.0`) |
| `output_path` | `string` | `watermarked.png` | 水印/打码导出保存路径 |

## 输出

- 返回处理后的图片/视频文件绝对路径。
