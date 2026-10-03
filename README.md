# 🎬 官方多媒体录屏截屏与音频套件 (Media, Screen Capture & Audio Suite)

[![Plugin Version](https://img.shields.io/badge/version-0.50.5-blue.svg)](manifest.json)
[![Group](https://img.shields.io/badge/group-Media-red.svg)](#)
[![Platform](https://img.shields.io/badge/platform-All-green.svg)](#)
[![Admin](https://img.shields.io/badge/admin-not__required-brightgreen.svg)](#)
[![License](https://img.shields.io/badge/license-Freeware-brightgreen.svg)](#)

工业级桌面跨平台多媒体处理套件。覆盖 USB 工业相机实时连续采帧、全屏/窗口/选区/长图滚动智能截屏、高性能屏幕录制动图（GIF）导出、原生音频播放控制与无损麦克风录音、离线文本转语音（TTS）播报、硬件蜂鸣提示及音视频元数据嗅探。

---

## 📖 简介 (Overview)

`xy_media` 提供了全套工业级桌面多媒体处理与视音频自动化能力：
- **工业视觉与相机采集**：支持常驻打开 USB 工业相机、UVC 摄像头及 RTSP/HTTP 网络流（`CameraOpen`），提供微秒级极速逐帧抓拍（`VideoFrame`）与资源释放（`CameraClose`）。
- **全场景截屏矩阵**：
  - **全屏截取** (`CaptureScreen`)：支持单屏、多屏跨屏及指定显示器截取。
  - **活动窗口 / 句柄后台截图** (`CaptureActiveWindow`, `CaptureWindow`)：支持前台焦点截取或后台非置顶增强渲染截屏。
  - **精准 ROI 区域截屏** (`CaptureRegion`)：按绝对坐标自由裁切。
  - **滚动拼接超长图** (`CaptureScroll`)：智能模拟滚轮下翻与重叠率图像融合，截取网页与长列表视图。
  - **OCR 白底优化**：截屏算子统一支持将透明通道铺平为纯白背景，大幅提升下游 OCR 识别准确率。
- **高性能屏幕录制** (`ScreenRecord`)：无需依赖复杂的外部转码环境，轻量录制屏幕动态并直接导出压缩 GIF 或图像序列，适用于自动化流程审计与异常留痕。
- **音频系统与麦克风录制**：支持本地音频多格式异步/循环播放（`AudioPlay`、`AudioStop`），高品质麦克风 WAV 定时与启停录制（`AudioRecord`）。
- **人机交互反馈**：支持离线文本转语音播报（`TextToSpeech`）、系统蜂鸣提示音（`SystemBeep`）以及键鼠宏操作序列回放（`PlayRecord`）。
- **多媒体属性探测** (`MediaInfo`)：毫秒级嗅探图像、音频、视频的尺寸、编码、时长与采样率元数据。

---

## ✨ 核心特性 (Features)

- **免管理员权限 (Requires Admin: False)**：所有多媒体能力均基于标准用户态 API 实现，安全合规。
- **低延迟相机暖机模型**：通过 `CameraOpen` 维持设备常驻连接，消灭冷启动延时，实现工业相机的高频实时连拍采帧。
- **零依赖轻量录屏引擎**：内置高性能屏幕捕获与 GIF 量化压缩功能，单文件开箱即用。
- **智能长图拼接算法**：结合像素重叠率分析与滚轮步进沉降延时，稳定捕获长网页、聊天记录及数据列表。
- **内置 OCR 图像前置处理**：截屏时自动平铺透明通道至纯白底色，有效规避异形窗口与阴影导致的 OCR 漏识。

---

## 🛠️ 动作指令全景速查 (Action Catalog)

| 动作标识 (Tag) | 功能名称 | 描述 | 输出类型 |
| :--- | :--- | :--- | :--- |
| `CaptureScreen` | 截取屏幕 | 捕获主屏、指定显示器或全桌面，支持 ROI 裁剪、剪贴板及 OCR 优化 | `string` |
| `CaptureActiveWindow` | 截取当前活动窗口 | 截取前台焦点窗口图像，支持局部坐标裁切与存盘/剪贴板 | `string` |
| `CaptureWindow` | 截取指定窗口 | 按句柄或标题模糊匹配截取窗口（支持后台非置顶渲染） | `string` |
| `CaptureRegion` | 截取指定区域 | 按绝对坐标与选区 (x, y, w, h) 高速裁切桌面局部 | `string` |
| `CaptureScroll` | 滚动截取长图 | 模拟滚轮平滑滚动并自动重叠缝合生成超长分辨率全景图 | `string` |
| `ScreenRecord` | 屏幕录制 | 录制屏幕/窗口动态，一键导出轻量化 GIF 动图 | `string` |
| `CameraOpen` | 打开相机设备 | 常驻初始化 USB 工业相机、UVC 摄像头或 RTSP/HTTP 视频流 | `string` |
| `VideoFrame` | 视频逐帧提取 | 极速捕获已打开相机的最新一帧，支持存盘与剪贴板 | `string` |
| `CameraClose` | 关闭相机设备 | 显式断开相机连接并释放硬件驱动句柄 | `string` |
| `AudioPlay` | 播放音频 | 原生播放 WAV/MP3/OGG 等音频，支持音量调节、循环与同步等待 | `string` |
| `AudioStop` | 停止音频 | 立即停止正在播放的指定通道背景音或全局提示音并释放声卡 | `string` |
| `AudioRecord` | 录音到文件 | 原生捕获麦克风输入并保存为无损 WAV，支持定时或手动启停 | `string` |
| `TextToSpeech` | 文本转语音 (TTS) | 系统原生离线中英文语音朗读，支持语速、音量及异步播报 | `string` |
| `SystemBeep` | 蜂鸣提示音 | 触发系统硬件音调蜂鸣或标准提示音 (Info/Warning/Error/OK) | `number` |
| `PlayRecord` | 回放录制 | 精确回放录制的键鼠宏动作，支持倍速、随机扰动防检测与循环 | `number` |
| `MediaInfo` | 获取多媒体信息 | 高速读取音视频与图像的封装格式、分辨率、时长与声道信息 | `string` |

---

## 📚 详细参数说明与使用参考 (Detailed Reference)

### 1. 屏幕截图矩阵 (Screen & Window Capture)

#### `CaptureScreen` - 截取屏幕
- **输入参数：**
  | 参数名 (Field) | 显示名称 | 类型 | 默认值 | 预设推荐值 | 说明 |
  | :--- | :--- | :--- | :--- | :--- | :--- |
  | `display_name` | 显示器名称/编号 | `string` | `""` | `""`, `primary`, `0`, `1` | 留空为默认主屏或虚拟跨屏桌面 |
  | `size` | 裁剪尺寸 (w, h) | `string` | `""` | `""`, `1920, 1080`, `1280, 720` | 局部截取分辨率，留空截全屏 |
  | `top_left` | 左上角偏移 (x, y) | `string` | `0, 0` | `0, 0`, `100, 100` | 裁剪起始坐标 |
  | `output_path` | 保存路径 | `string` | `""` | `C:/temp/screenshot.png` | 保存文件路径，留空返回 Image 内存对象 |
  | `to_clipboard` | 复制到剪贴板 | `number` | `0` | `0` (否), `1` (是) | 是否同步写入系统剪贴板 |
  | `ocr_optimize` | OCR白底优化 | `number` | `0` | `0` (关), `1` (开) | 透明通道自动转纯白底提升 OCR 识别 |

#### `CaptureActiveWindow` 与 `CaptureWindow` - 窗口截屏
- **`CaptureActiveWindow`**：截取当前最前台聚焦窗口，参数：`size`、`top_left`、`output_path`、`to_clipboard`、`ocr_optimize`。
- **`CaptureWindow`**：截取指定窗口。参数：`window`（句柄或标题模糊匹配关键字）、`index`（同名窗口下标索引，默认 `0`）、`size`、`top_left`、`output_path`、`to_clipboard`、`ocr_optimize`。

#### `CaptureRegion` - 截取指定区域
- **输入参数：** `region` (x, y, w, h 区域字符串)、`display_name`、`output_path`、`to_clipboard`、`ocr_optimize`。

#### `CaptureScroll` - 滚动截取长图
- **输入参数：**
  | 参数名 (Field) | 显示名称 | 类型 | 默认值 | 预设推荐值 | 说明 |
  | :--- | :--- | :--- | :--- | :--- | :--- |
  | `target_window` | 目标窗口 | `string` | `""` | `""`, `Chrome`, `Edge` | 目标窗口标题/句柄，留空为当前焦点窗口 |
  | `scroll_direction`| 滚动方向 | `string` | `down` | `down`, `up` | 滚轮步进方向 |
  | `scroll_clicks` | 单次滚轮步长 | `number` | `5` | `3`, `5`, `8`, `10` | 每次滚动的刻度格数 |
  | `max_pages` | 最大滚动页数 | `number` | `5` | `3`, `5`, `10` | 最大允许拼接的屏幕页数上限 |
  | `delay_ms` | 滚动间歇停顿(ms) | `number` | `400` | `300`, `400`, `600` | 滚动后等待页面渲染完毕的沉降时间 |
  | `overlap_pct` | 重叠比例(%) | `number` | `20` | `10`, `20`, `30` | 帧间重叠融合预估比例 |
  | `output_path` | 保存路径 | `string` | `""` | `C:/temp/scroll_long.png` | 拼接后长图输出文件 |
  | `to_clipboard` | 复制到剪贴板 | `number` | `0` | `0`, `1` | 是否同步写入剪贴板 |
  | `ocr_optimize` | OCR白底优化 | `number` | `0` | `0`, `1` | 透明背景自动转白底 |

---

### 2. 高性能屏幕录制 (GIF Screen Recorder)

#### `ScreenRecord` - 屏幕录制
直接录制窗口或全桌面并生成轻量 GIF。

- **输入参数：**
  | 参数名 (Field) | 显示名称 | 类型 | 默认值 | 预设选项 | 说明 |
  | :--- | :--- | :--- | :--- | :--- | :--- |
  | `action` | 录制动作 | `string` | `record_duration` | `record_duration`, `start`, `stop` | `record_duration` (定时录制), `start` (后台启动), `stop` (停止并保存) |
  | `output_path` | 输出路径 (.gif) | `string` | `record.gif` | `record.gif`, `C:/temp/audit_trace.gif` | 导出的 GIF 文件路径 |
  | `fps` | 录制帧率 (FPS) | `number` | `10` | `5`, `10`, `15`, `20` | 采样帧率（建议 5-15 兼顾流畅与体积） |
  | `duration` | 录制定时时长(秒) | `number` | `5` | `3`, `5`, `10`, `30` | `record_duration` 模式下的录制时长 |
  | `target_window` | 目标窗口 | `string` | `""` | `""`, `Chrome`, `Notepad` | 限定录制的特定窗口，留空录制全桌面 |
  | `scale` | 分辨率缩放倍率 | `number` | `0.5` | `0.5`, `0.75`, `1.0` | 降采样比例（0.1~1.0），大幅缩减 GIF 体积 |

---

### 3. USB 工业相机与视频流 (Camera & Video Frames)

#### `CameraOpen` -> `VideoFrame` -> `CameraClose` 完整流水线
- **`CameraOpen`**：
  - `device` (*string*, 默认 `0`): 本地硬件索引 `0`, `1`, `2` 或网络 RTSP 流 `rtsp://192.168.1.100:554/live`。
  - `size` (*string*): 期望分辨率如 `1920, 1080`、`1280, 720`。
  - `output_var` (*string*, 默认 `camera`): 存储生成的句柄变量名。
- **`VideoFrame`**：
  - `camera` (*string*, 默认 `{camera}`): 引用已打开的相机对象。
  - `output_path` (*string*): 直接写入磁盘，留空直接输出为 `Image` 变量供下游直接进行模板匹配或 OCR。
  - `to_clipboard` (*number*, 默认 `0`): 是否同步拷贝到系统剪贴板。
- **`CameraClose`**：
  - `camera` (*string*): 释放对应的相机句柄并断开物理占用。

---

### 4. 音频播控与麦克风录制 (Audio System)

#### `AudioPlay` 与 `AudioStop`
- **`AudioPlay`**：
  - `file_path` (*string*): 本地 WAV、MP3、OGG 路径。
  - `volume` (*number*, 默认 `80`): 音量大小（0~100）。
  - `repeat` (*number*, 默认 `0`): 是否循环播放（`1` 开启，`0` 单次）。
  - `wait` (*number*, 默认 `0`): 是否同步阻塞直到播放结束。
- **`AudioStop`**：
  - `channel` (*string*): 指定通道别名（如 `bgm`），留空停止默认通道。

#### `AudioRecord` - 录音到文件
- **输入参数：**
  - `action`: `record_duration`（定时录制）、`start`（后台启动）、`stop`（停止并写盘）。
  - `output_path`: 仅限 `.wav` 格式保存路径。
  - `duration`: 录制秒数（默认 `5` 秒）。
  - `sample_rate`: 采样率 Hz（推荐 `16000` 用于语音识别 / ASR，`44100` 用于高质量声音）。

---

### 5. 语音通知与用户交互 (TTS, Beep & Macro Replay)

#### `TextToSpeech` - 文本转语音 (TTS)
- **输入参数：**
  - `text`: 朗读文本（如 `操作已完成`）。
  - `rate`: 语速调节（`-10` 到 `10`，`0` 为标准）。
  - `volume`: 朗读音量（`0` 到 `100`）。
  - `wait`: 是否阻塞等待朗读完毕（`1` 阻塞，`0` 异步后台朗读）。

#### `SystemBeep` - 蜂鸣提示音
- **输入参数：**
  - `beep_type`: `tone` (指定频率)、`info` (信息音)、`warning` (警告音)、`error` (错误音)、`ok` (成功音)。
  - `frequency`: 声音频率 Hz（默认 `750`，仅在 `tone` 生效）。
  - `duration_ms`: 持续毫秒数（默认 `300` ms）。

#### `PlayRecord` - 回放录制
- **输入参数：**
  - `name`: 宏持久化清单表名。
  - `radius`: 随机抖动偏移像素（模拟人工操作，防风控）。
  - `speed`: 回放倍速（`1.0` 到 `5.0`）。
  - `repeat`: 重复循环次数。
  - `interval`: 循环间隙毫秒。

#### `MediaInfo` - 获取多媒体信息
- 传入 `file_path`，高速读取音视频/图像文件的封装格式、分辨率、时长、声道数与采样率等元数据。

---

## 📦 插件清单定义 (Manifest Reference)

```json
{
  "plugin_id": "xy_media",
  "name": "屏幕截屏、录屏与多媒体 (Media & Capture)",
  "version": "0.50.5",
  "group": "Media",
  "group_icon": "🎬",
  "description": "提供屏幕截图、滚动长截图、桌面录制为 GIF 动图、音频播放与录音、提示音以及工业摄像头采图功能",
  "actions": [...]
}
```

---

## 📄 许可证 (License)

本插件遵循免费专有许可协议 (Freeware)。供 小友+ 用户免费下载与使用，未经官方书面授权，严禁对二进制文件进行逆向工程、反编译或二次打包转售。
