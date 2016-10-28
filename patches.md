# Patch 模块

Patch 是 Origami Studio 的构建模块。可以用惊人的速度演示你的想法和迭代。

Patch 允许你添加交互、动画和动作到你的原型中，每一个patch都有独有的功能可以从其他的patch接受和传递信息。

Patch 库包含了大量的patch模块, 但是一套15-20个patch模块的核心设置就已经支持大多数的原型了。它们都有单独的快捷键可以超级快的使用。

Patches 有简单的数学模块:

![](/assets/1.png)

（+模块输入两个数字在左边，然后输出综合在右边，2+3=5。）

patch 可以添加交互到图层上：

![](/assets/2.png)

（Interaction模块输出触控的信息在查看器图层上。当手指在区块上按下，它在down这个端口输出 √ 。）

patch可以管理状态：

![](/assets/3.png)

（Switch模块能打开或关闭左侧的输入，然后输出当前的状态到右边）

patch可以控制图层属性

![](/assets/4.png)

（通过在属性面板点击任意属性，添加图层属性模块。这个模块控制区块是否显示或者隐藏）

## 端口

端口允许模块接收信息，并将信息传递出去。 左边的端口是模块的输入，右边的是输出。点击端口的值编辑输入。（除非另一个模块的连线已连接到输入上）

每一个端口都能接收不同类型的信息-- 用于Origami的值的重要类型：

* **Number**: 整数或小数
* **Boolean**: 布尔的值有两个可能的结果\(比如: true\/false, yes\/no, on\/off, 0\/1\). 布尔端口的值经常是 On\/Off,  On 值相当于是一个对号。类似程序中，在模块间传递数据，布尔的值能被修改为一个数字 0 \(off\) 或者1 \(on\) 。
* **Text**: 一串字符.
* **Image**: 你可以拖拽或粘贴任何的图片.
* **Video**: 你可以拖拽或粘贴任何的视频.
* **Sound**: 你可以拖拽或粘贴任何的音频.
* **Color**: 任何 RGB 或者 HSL 颜色.
* **Index**: 任何非负的整数 \(比如: 0, 1, 2\)
* **JSON Data**: 任何数量的任何类型的JSON格式的值。JSON（JavaScript Object Notation）是用于存储和交换数据的通用格式。 
* **Point**: A value that represents numbers in 2D, 3D, or 4D. Points can represent any set of X, Y, Z values \(ex: Position X, Y, Z; Rotation X, Y, Z\).

Some patches can change the number of ports it has or the type of value it supports. Right-click any patch to see the options available.

