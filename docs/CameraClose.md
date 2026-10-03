# 关闭相机设备 (CameraClose) (CameraClose)

关闭已连接的 USB 工业相机或视频流摄像头

## 运行参数

* **相机句柄变量 (`camera`)**
  * 类型: `string`
  * 默认值: `"{camera}"`
  * 描述: 需要关闭并释放的相机句柄变量引用。常用预设：`{camera}`, `{cam0}`。

## 输出

* 类型: `string`
* 描述: 释放相机设备的结果回执。

## 使用示例

```json
{
    "tag":  "CameraClose",
    "camera":  "{camera}"
}
```
