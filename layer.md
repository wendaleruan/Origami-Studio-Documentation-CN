# Layers 图层

图层在 Origami Studio 里类似于图层在 Sketch 和 Photoshop: 每个图层都具有样式属性 \(位置, 大型, 图片 或者 颜色\) 并且能够被有条理的组织的。

用⌘⇧N或者工具栏+按钮添加一个图层。

## 图层组

通过选择任意数量图层然后按下 ⌘G，图层就能被编组。图层组在 Origami Studio 有它们自己的大小和位置， 并且合上里面的图层。

## 图层属性

图层属性类似于模块的端口. 这些输入端口的值决定了图层的显示结果。

## 图层属性模块

通过模块调整图层属性 点击属性在属性面板, 然后一个名叫图层名的蓝色图层属性模块就会被创建出来，只有写着一个值的一个单独的输入端口。

![](/assets/6.png)

（点击透明端口在区块属性上将会添加这个模块到模块编辑器里）

你也可以直接拖拽一条连线从模块到属性面板的图层属性上。

如果一个属性有多个坐标（例如: 位置 X\/Y, Size W\/H），你可以点击具体的坐标，如:X

![](/assets/7.png)

或者点击全部属性，如：位置

![](/assets/8.png)

（点击多个坐标的属性，例如: 位置，大小，角度，将自动插入一个Point模块，能够表示额外的不会默认显示的坐标，如:Z）

## Masking

Layers can be masked by other layers. Pressing ⌘⌥M will turn the layer to an alpha mask, clipping the layer right above it. To add additional layers to be masked, you can select the layers and press ⌘⌥⇧M.

All masks are alpha masks, which can let you do advanced masks like gradient masks or composite masks based on a group of shapes.



