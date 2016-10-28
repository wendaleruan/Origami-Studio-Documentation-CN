# Animations动画

动画在 Origami 里是被设计用来流畅转换的，例如: 他们使任何数字的改变之间变得平滑。

## 动画模块

* **Pop Animation** `A` 自然的有活力的动画通常在 Facebook 应用里发现。 你可以很简单的传递数值到你的开发中，用iOS的 Pop 框架，Android的 Rebound , 和web的 Rebound JS 。

* **Classic Animation** `C` 传统的缓动曲线, 如 linear, ease-in, 和 ease-out.

* **Repeating Motion** 重复, 缓动曲线来回的动画


## 动画数值

在组合中  [Interaction](http://origami.design/documentation/patches/builtin.layer.interaction.html) 或者  [Switch](http://origami.design/documentation/patches/builtin.switch.html) 模块,  输出 0 或 1, 一个动画模块能从0到1平滑地过渡数值, 反之亦然. Origami 一般渐进的转换换0到1的数值.

下面这个例子，当你点触的时候将从 0 到 1 \(或者 0% 到 100%\) 用可逆的有活力的动画缩放一个图层：

![](/assets/12.png)

## 过渡

动画从 0 到 1 很简单, 但是在其他值之间变化呢?

**Transition** `T` 模块让你的过渡从 0\/1 到任意 start\/end 值:

![](/assets/13.png)

举个例子, 如果你想要变化一个图层的宽从 100px 到 200px. 你要具体说明开始的值100, 和结束的值 200. 从组合中变化0到1的值上面讲过, 你能很轻易的变化图层的宽度。

With a Progress of 0:

![](/assets/14.png)

With a Progress of .5:

![](/assets/15.png)

With a Progress of 1:

![](/assets/16.png)

In combination with an animation patch, you can now animate between any two values easily:

![](/assets/17.png)

## 总结

* Pop Animation and Classic Animation automatically tween any number.
* Interaction, Switch, Animation, Transition \(ISAT\) are your bread and butter for animating layers.
* Sync multiple animations together by using one animation patch connected to multiple Transitions, which map progress of 0-1 to any start\/end values.



