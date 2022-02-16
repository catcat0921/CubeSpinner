# 乐高EV3魔方机器人

使用c语言对EV3进行编程的环境配置教程参考：[配置链接](http://bbs.cmnxt.com/thread-13374-1-1.html)

## 固件版本

建议固件1.07E，测试1.03E错误。

## 改进点

在原作者基础上增加了错误显示，无论魔方是否正确，都会尝试进行还原，然后再报错。

## 错误码说明

ERR 1: 魔方颜色识别错误，统计时发现每种颜色计数不止9个，就会报错ERR 1,解决方法是换魔方。

ERR 2: Not all 12 edges exist exactly once

ERR 3: Flip error: One edge has to be flipped

魔方错误，一个棱块需要被翻转。

ERR 4: Not all corners exist exactly once

魔方错误，不是所有的棱块都出现一次。

ERR 5: Twist error: 一个角块需要被旋转。

一样是魔方错了，不过这种情况下，魔方机器人会先去还原，一般都是就可以还原到只剩那个角块。

ERR 6: Parity error: 两个角块或者两个中间的棱块需要交换，一般不会出现这个错误。

是魔方错了，建议换个色彩准度高的魔方。

## 使用教程

大概的搭建和操作详见乐高论坛论坛另一贴： [点击访问](http://bbs.cmnxt.com/thread-22447-1-1.html)

## 原作者的话

```text
CubeSpinner

Rubik's Cube solving robot using a Lego Mindstorms EV3 kit.

My second fully iteration of the cube robot. This time, the processing power 
of the EV3 intelligent brick allowed me to use a much better solving algorithm.
Additionally the new motor that comes with the EV3 kit runs much fast than the
other mindstorms motor, allowing a faster turning mechanic.

To achieve this speed, I had to modify the interface directly with the lego 
motor axis. This could be considered cheating, but it works nicely.
The programming is done in C with a GCC tool chain that was adopted for the
EV3 by John Hansen and I had to extend the sensor functionality to support
the color sensors.

For anyone who wants to build the cube spinner, the 'release' folder
contains the necessary instructions and the building plan.

There is also a video on youtube:

https://www.youtube.com/watch?v=zQR2UfwRlkA
```

## [博客主页](https://blog.maxiang.vip/)
