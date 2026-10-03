# 获取多媒体信息 (MediaInfo) (MediaInfo)

快速查看音视频或图片文件的分辨率、播放时长和文件大小等属性

## 运行参数

* **多媒体文件路径 (`file_path`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 待读取元数据的音视频或图像文件路径。常用预设：`C:/images/sample.png`, `C:/video/clip.mp4`, `C:/audio/test.wav`。

## 输出

* 类型: `string`
* 描述: 多媒体文件元数据属性 JSON 字符串。

## 使用示例

```json
{
    "tag":  "MediaInfo",
    "file_path":  ""
}
```
