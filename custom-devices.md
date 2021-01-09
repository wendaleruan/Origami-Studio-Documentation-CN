# Custom Devices

制作你自己的模拟设备, 添加他们到 Studio 并且分享它们给别人。

## 创建设备

1. 在 macOS 上创建文件夹
2. 重命名文件夹叫 `[yourdevice].origamidevice`
3. 这个文件夹应该包含以下:
4. 一个 `info.json` 文件用于描述设备 \(查看下面的文档\)
5. 任意数量的 .png 图片引用于 `info.json`
6. 双击 `.origamidevice` 文件来安装它

## 测试你的设备

在安装之后测试你的自定义设备:

1. 在 Origami Studio 打开设备
2. 对bundle包做任何改变
3. 双击bundle包
4. Origami Studio 将会立刻刷新到设备上

所有安装的设备都会储存在 `~/Library/Application Support/Diamond/Devices`. 如果你已经有一个同名的设备在这个文件夹里，它会被替换掉。

## info.json 例子

```text
{
  "key" : "iPhone4",
  "displayName" : "iPhone 4",
  "platform" : "iOS",
  "screenScale" : 2,
  "screenSize" : [
    320,
    480
  ],
  "handsImageScale" : 0.5649999999999999,
  "handsImageOffset" : [
    2,
    45
  ],
  "handsImages" : [
    "iPhoneHands.png",
    "iPhoneHands2.png",
    "iPhoneHands3.png"
  ],
  "deviceInsets" : [
    130,
    28,
    130,
    28
  ],
  "deviceImages" : {
    "White" : "iPhone4-White.png",
    "Black" : "iPhone4-Black.png"
  },
  "shadowOffset" : [
    20,
    -5
  ],
}
```

## info.json 文档

很多设备原型的 `info.json` 文件都是通过 [Device Info patch ](http://origami.design/documentation/patches/builtin.deviceInfo.html)显示的。

### `key`

类型: String, Required

这是 bundle 包中最重要的项目。Key 将保存到设计师的作品中，所以一旦被选中你不能改变它。Key 应该与设备的通常理解的名称有关，但如果有多个屏幕大小或分辨率，它必须是唯一的组合。你不应该在 Key 中包含设备颜色。它在设备图像里。

### `displayName`

类型: String, Required

display name 在 Studio 的设备选择菜单里显示. 它能够被改变在它没有被保存到作品中的时候。

### `screenSize`

类型: Array of 2 numbers, Required

设备用 pt\/dp 显示大小. 像素大小是 `screenSize` 乘以 `screenScale`.

作品通过设备信息端口 "Screen Size"显示。

### `screenScale`

类型: Number, Required

每个点有多少像素

举个例子, iOS 视网膜显示屏是典型的2.0倍大小. iPhone 6 Plus 是3.0倍大小. Android 设备有一系列的倍数从 0.75 到 4.0 相对应到 ldpi \(0.75\) mdpi \(1.0\), hdpi \(1.5\), xhdpi \(2.0\), xxhdpi \(3.0\) and xxxhdpi \(4.0\).

### `platform`

类型: String, Optional

例如. `iOS`, `Android`, `AndroidWear`, `WindowsPhone`, `Windows`, `OSX`, `tvOS`, or `watchOS`

### `mouseInput`

类型: Boolean, Optional

设备用鼠标还是触控板输入

### `viewerWindowNative`

类型: Boolean, Optional

设备是否用自带的mac窗口显示弹出窗口, screenSize 可以轻易地改变大小。

### `deviceInsets`

类型: Array of 4 Numbers, Required

Describes the distance around the device. Influences how the shadow is drawn and the device is positioned relative to the containing view frame.

描述设备的距离。影响阴影绘制的方式还有设置设备相对于包含视图框的位置。

### `shadowOffset`

类型: Array of 2 Numbers, Optional

如果你想创建影子，设置这个一些非零的值，你能定位影子在设备的相对位置。

### `deviceImages`

类型: Dictionary of Strings to Strings

The keys in the dictionary describe colors the device is available in, the values are the names of the .png files within the bundle that will display the correct device frame within Origami Studio.

### `deviceImageOffset`

类型: Array of 2 Numbers, Optional

从屏幕上偏移设备图像多少

### `deviceImageScale`

类型: Number, Required if deviceImages is used

相对于屏幕大小，放大或缩小图像多少

### `handsImageOffset`

类型: Array of 2 Numbers, Optional

相对于设备图形偏移手的图像多少

### `handsImageScale`

类型: Float, Optional

相对于屏幕缩放手的图像大小多少

### `handsImages`

类型: Array of Strings, Optional

这里的每个条目都应该指向设备包中提供的一个手的图像。

### `handsOnTop`

类型: Boolean, Optional

是否手在设备的顶部。有用的设备如 iPad，拇指应该在前面。

