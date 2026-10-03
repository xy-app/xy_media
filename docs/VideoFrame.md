# 视频逐帧提取 (VideoFrame) (VideoFrame)

从已打开的工业相机或视频文件中极速抓取当前最新的一帧清晰画面

## 运行参数

* **相机变量/设备索引 (`camera`)**
  * 类型: `string`
  * 默认值: `"{camera}"`
  * 描述: 由 CameraOpen 产生的相机句柄变量引用 (如 {camera}) 或直接设备索引。常用预设：`{camera}`, `0`, `1`。
* **帧图像存盘路径 (`output_path`)**
  * 类型: `string`
  * 默认值: `""`
  * 描述: 将提取的单帧直接保存为图片，留空返回 Image 内存实体。常用预设：``, `C:/temp/frame.png`。
* **复制到剪贴板 (`to_clipboard`)**
  * 类型: `number`
  * 默认值: `0`
  * 描述: 是否同步复制该帧至系统剪贴板 (1为是，0为否)。常用预设：`0`, `1`。

## 输出

* 类型: `string`
* 描述: 捕获到的相机视频帧文件路径或内存图像对象。

## 使用示例

```json
{
    "tag":  "VideoFrame",
    "camera":  "{camera}",
    "output_path":  "",
    "to_clipboard":  0
}
```
