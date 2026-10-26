# 🎬 官方多媒体录屏截屏与音频套件 (Media, Screen Capture & Audio Suite)

[![Plugin Version](https://img.shields.io/badge/version-0.53.0-blue.svg)](manifest.json)
[![Group](https://img.shields.io/badge/group-Media-red.svg)](#)
[![Platform](https://img.shields.io/badge/platform-All-green.svg)](#)
[![Admin](https://img.shields.io/badge/admin-not__required-brightgreen.svg)](#)
[![License](https://img.shields.io/badge/license-Freeware-brightgreen.svg)](#)
[![Discord](https://img.shields.io/discord/832082456727257118?label=Discord&logo=discord&logoColor=white&color=5865F2)](https://discord.gg/g5Fh3FtfGx)

工业级桌面跨平台多媒体处理套件。覆盖 USB 工业相机与 RTSP 流抓拍、通用屏幕/窗口/区域/长图截屏、GIF/MP4 动态屏录与双声道混音、30秒异常崩溃回溯录像、系统内录与麦克风录音、高精度离线 Whisper 语音识别与 TTS 朗读、原生音频播控及媒体水印打码脱敏。

---

## 📖 简介 (Overview)

`xy_media` 提供了全套工业级桌面多媒体处理与视音频自动化能力：
- **工业视觉与相机抓拍**：支持 USB 工业相机、UVC 摄像头及 RTSP/HTTP 网络流单次自动抓拍或句柄常驻微秒级连拍（`CameraCapture`）。
- **通用截屏矩阵**：
  - **通用画面截图** (`CaptureImage`)：聚合全屏、前台聚焦窗口、句柄指定窗口及绝对坐标 ROI 区域裁切，内置 OCR 透明通道白底平铺预优化。
  - **滚动拼接超长图** (`CaptureScroll`)：智能模拟滚轮下翻与重叠率图像融合，截取网页与长列表视图。
- **高帧率屏录与崩溃回溯**：
  - **轻量 GIF 动图录制** (`ScreenRecord`)：轻量录制屏幕动态并导出压缩 GIF 动图。
  - **高清 MP4 视频屏录与混音** (`VideoRecord`)：原生硬件加速屏录，支持系统内录+麦克风双声道加权混音，以及 **30 秒内存环形队列异常/崩溃回溯录像存盘**。
- **音频系统与双向声音采集**：
  - **音频播控与提示音** (`AudioPlayer`)：跨平台原生播放 WAV/MP3/OGG，支持音量调节、循环与系统蜂鸣音（Beep）。
  - **麦克风无损录音** (`AudioRecord`)：高品质麦克风 WAV 定时与启停录制。
  - **电脑系统内录** (`AudioCaptureSystem`)：基于 WASAPI / CoreAudio 扬声器端点内录，捕获播放器、会议及电话通话声音。
- **AI 语音交互与脱敏安全**：
  - **高精度离线 ASR 语音识别** (`SpeechToText`)：调取设置面板激活的 Whisper 本地离线模型，基于内置高性能音频解码与硬件加速，无需配置 `model_path`，100% 本地高精度转译。
  - **文本转语音 / TTS** (`TextToSpeech`)：系统原生离线中英文语音朗读播报。
  - **音视频提取** (`AudioExtract`)：跨平台免重编码毫秒级提取视频音频轨 (MP4 -> MP3/WAV/AAC)。
  - **水印与马赛克脱敏** (`MediaWatermark`)：为截图与视频叠加动态文字水印（机器名/时间戳/脱敏标记），或对敏感区域进行像素级马赛克与高斯模糊打码。
- **多媒体属性探测** (`MediaInfo`)：毫秒级嗅探图像、音频、视频的尺寸、编码、时长与采样率元数据。

---

## 🛠️ 动作指令全景速查 (Action Catalog)

| 动作标识 (Tag) | 功能名称 | 描述 | 输出类型 |
| :--- | :--- | :--- | :--- |
| `CaptureImage` | 通用画面截图 | 聚合全屏、聚焦窗口、指定句柄窗口及 ROI 区域截图，支持 OCR 白底平铺 | `string` |
| `CaptureScroll` | 滚动截取长图 | 模拟滚轮平滑滚动并自动重叠缝合生成超长分辨率全景图 | `string` |
| `CameraCapture` | 相机与视频流抓拍 | USB 摄像头与 RTSP 视频流单次自动抓拍、常驻连拍及显式关闭 | `string` |
| `ScreenRecord` | 屏幕录制 (GIF) | 录制屏幕/窗口动态，一键导出轻量化 GIF 动图 | `string` |
| `VideoRecord` | 高清 MP4 视频屏录 | 硬件加速屏录，支持双声道混音与 30s 内存环形队列崩溃回溯存盘 | `string` |
| `AudioPlayer` | 音频播放与控制 | 原生播放本地音频，支持停止通道与系统蜂鸣提示音 (Beep) | `string` |
| `AudioRecord` | 麦克风录音 | 捕获麦克风输入并保存为无损 WAV，支持定时或手动启停 | `string` |
| `AudioCaptureSystem`| 电脑系统声音内录 | 捕获电脑播放的所有声音 (播放器/会议/客服电话)，保存为 WAV | `string` |
| `TextToSpeech` | 文本转语音 (TTS) | 系统原生离线中英文语音朗读，支持语速、音量及异步播报 | `string` |
| `SpeechToText` | 语音转文字 (ASR) | 调取设置面板 Whisper 模型转写文本 | `string` |
| `AudioExtract` | 音视频分离与提取 | 跨平台免重编码毫秒级提取视频中的音频轨道 (MP4 -> MP3/WAV/AAC) | `string` |
| `MediaWatermark` | 媒体水印与打码脱敏 | 叠加动态文字水印，或对敏感区域进行像素级马赛克与高斯模糊脱敏 | `string` |
| `MediaInfo` | 获取多媒体信息 | 高速读取音视频与图像的封装格式、分辨率、时长与声道信息 | `string` |

---

## 📦 插件清单定义 (Manifest Reference)

```json
{
  "plugin_id": "xy_media",
  "name": "屏幕截屏、录屏与多媒体 (Media & Capture)",
  "version": "0.51.1",
  "group": "Media",
  "group_icon": "🎬",
  "actions": [...]
}
```

---

## 📄 许可证 (License)

本插件遵循免费专有许可协议 (Freeware)。供 小友+ 用户免费下载与使用，未经官方书面授权，严禁对二进制文件进行逆向工程、反编译或二次打包转售。
