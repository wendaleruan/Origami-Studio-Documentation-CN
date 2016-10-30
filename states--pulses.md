# 状态 & 闪烁

状态帮助记忆信息在你的原型里。闪烁是告诉模块运行动作。明白了这些是怎么一起工作的将帮助你更有效的创建你的Origami原型。

## 状态

状态是在时间上持续存在的数值. 最简单的状态版本就是开关模块. 开关不是开就是关, 并且会保持状态不变直到你让他们改变。

如果你看到一个状态在时间上改变了, 它可能看起来像这样:

![](/assets/states.png)

开关关闭直到你把它打开。你可以看到在一个单独帧画面中状态马上从关闭编程打开。一帧画面通常是 1\/60 秒。

## 闪烁

场景在时间上持续存在, 然而闪烁只会在一帧上打✓. 连线发送的其他闪烁的数值都是关闭的.

闪烁在时间上看上去像这样:

![](/assets/pulses.png)

You can see that pulses are only On ✓ for a single frame.

They're used to tell patches to **perform an action**, like telling a Switch to turn on or turn off. They're also useful for passing along user interactions like tapping on the screen or pressing a key on the keyboard.

## Examples of State & Pulses

* The [Switch](http://origami.design/documentation/patches/builtin.switch.html) patch outputs the **state** of the switch \(on \/ off\) and accepts **pulses** to flip the switch, turn it on, or turn it off.
* The [Interaction](http://origami.design/documentation/patches/builtin.layer.interaction.html) patch has Down and Tap outputs. Down represents the **state** of whether the finger is currently down on the screen. The Tap port outputs a **pulse** when the finger is released from the screen.
* The [Counter](http://origami.design/documentation/patches/builtin.counter.html) patch outputs the **state** of the counter \(the number value\) and accepts **pulses** to increase it or decrease it.

## Creating Pulses from State

There are a couple ways to create a pulse from state. The more explicit way is to use the [Pulse](http://origami.design/documentation/patches/builtin.pulse.html) patch. The Pulse patch accepts a state called On\/Off and will output a pulse on the Turned On port when the state turns on and the Turned Off port when the state turns off. This is an example that flips a switch the moment the user touches the screen.

![](/assets/25.gif)

Another way is to infer a state change is to connect a state directly to a port accepting a pulse. What'll happen is the port that accepts a pulse will look to when the state changes from off to on, and at that moment infer a pulse. So if you wanted a switch to flip when the user's finger touches down on the screen, you can connect the Down port directly to the Switch's Flip port, without needing to use a Pulse patch.

## Temporary State with the Delay patch

Sometimes you need a state to turn on for a few moments and then turn off. For example, say you were making a confirmation window appear for a couple seconds after the user pressed a button. You could do this using a Switch, but then you'd need to build logic that turns the switch off after some time. A simpler way to do this is to use the [Delay](http://origami.design/documentation/patches/builtin.delay.html) D patch.

The Delay patch can take state that's changing and delay the change by an amount of time you specify. You can also tell it whether to only delay increasing \(off to on\) or decreasing \(on to off\) changes. If you give a Delay patch a pulse as input, you can delay the change from on to off, extending the pulse for any amount of time you'd like.

![](/assets/26.gif)



