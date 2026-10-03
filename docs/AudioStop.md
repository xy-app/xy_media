# 停止音频 (AudioStop) (AudioStop)

立即停止正在播放的背景音乐或提示音

## 运行参数

* **播放通道/别名 (`channel`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 待停止的音频通道别名，留空停止默认通道。常用预设：``, `xy_audio`, `bgm`。

## 输出

* 类型: `string`
* 描述: 停止音频播放的执行结果回执。

## 使用示例

```json
{
    "tag":  "AudioStop",
    "channel":  ""
}
```
