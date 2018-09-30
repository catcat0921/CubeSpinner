# 乐高EV3魔方机器人

EV3是EDUCATION
建议固件1.07E

使用c语言对EV3进行编程的环境配置教程参考：http://bbs.cmnxt.com/thread-13374-1-1.html


在原作者基础上增加了错误显示，无论魔方是否正确，都会尝试进行还原，然后再报错。
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



使用教程：

1. 搭建

        用LDD打开release/CubeSpinner.lxf，照图搭之！这个魔方机器人的大多数零件来自EV3套件，你只需要再准备白色和黄色的圆砖（当然颜色随意，白色和黄色会比较友好）。
        第二个颜色传感器（连接到4端口）是可选的，加上它可以使扫描时间缩短4秒。
        因为LDD搞不定皮筋，所以请大家参照视频用皮筋拉紧两个手臂使棘轮结构能够正常工作

2.准备一个魔方

        你需要一个竞速魔方，色块有倒角会更顺滑，你还可以方便地取掉中心帽来调节螺丝。我使用的是淘宝购买的大雁轮回。
        你需要对魔方进行一下改造，用两个LEGO 2x2 板替换中心帽，凸点向外。要让你的魔方拥有视频里的那种魔力，你只需要把LEGO板用锉锉掉一点点边角，使它能够适合魔方块的形状。我选择把板粘上去，这样更耐用，如果你不想永久破坏原来的魔方也可以选择不粘。
        魔方的配色方案必须遵循带有贴纸/板材的标准红宝石魔方和黑色背景。

3.安装软件

        你需要在EV3主机上创建一个工程目录，一个简单的方法是利用EV3-g上传“launcher/CubeSpinner.ev3”自动建立这个目录，然后下载“release/CubeSpinner.rbf”和“spinnermain.rbf”到这个目录。
        也可以用如下步骤：
        a.将主机连接到电脑
        b.启动EV3-g
        c.新建一个新项目“CubeSpinner”，它将只包含开始模块
        d.下载到主机，主机上就有文件夹“CubeSpinner”了，里面有一个程序文件
        e.启动内存浏览器。这将显示“CubeSpinner”文件夹和内容
        f.删除CubeSpinner文件夹中的程序文件
        g.选择“CubeSpinner”文件夹，并使用“下载”功能将“release/CubeSpinner.rbf”和“spinnermain.rbf”文件下载到主机。


3.操作魔方机器人

        在启动程序之前，请确认所有的电机臂对齐。两个大型电机带动的红色3M跨接块对齐的时候，你可以用手指感觉到它跟黑色11M梁过渡地地方是光滑的。红色3M跨接块应该能顺时针和逆时针转动动相同的角度。（老妖怪注，这应该说的是大型电机内部齿轮有空隙，需要调整到顺时针和逆时针空隙一样。这里颜色以图纸为准）。同样，你可以将中型电机带动的旋转结构与离中型电机最近的红色11M梁对齐。程序运行后，就不能对齐了。
  
        从项目“CubeSpinner”启动“CubeSpinner”。主机的中心按钮已经用7M梁转到侧面，往下按7M梁即可。启动后，程序会用大概1分40秒的时间来创建一些大型数据表。完成之后颜色传感器的灯变白，就可以放魔方了。

        打乱魔方，插入正确的方向：白色中心块必须在左边，黄色中心块必须在右边（按机器人上的两个圆砖的颜色放），橙色中心块必须在上面。

        按中心按钮开始运行。

        如果你只连接了一个颜色传感器，机器人将直接还原魔方（如果没有出错）。
        如果你用了两个颜色传感器，首次运行只能校准颜色传感器，并且进行一些看似杂乱的步骤，然后魔方会回到刚放进去的状态。再次按中心按钮，机器人才还原魔方。每次启动程序后都需要进行这样的校准步骤。

        每次成功还原之后，你可以在显示屏上看到一些信息：所用的时间和解决的步数。

4.故障排除

        这个机器人的结构和程序是用9V电源开发和测试的（一些直流电源适配器或不可充电电池）。我试过7.2V（可充电电池）也似乎工作正常，就是电机转得慢一点。如果你遇到设置的问题，请联系我

        颜色传感器在昏暗的灯光下效果最佳，太亮的灯光尤其是新式LED灯会对颜色传感器造成真正的麻烦。


	
	
# 原作者的话：
# CubeSpinner
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

	