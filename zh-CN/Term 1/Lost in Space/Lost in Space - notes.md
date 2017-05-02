---
title: 太空迷航 — 社区负责人笔记
language: cn-ZH
embeds: "*.png"
...

#简介：
在这个项目中，孩子们将学习如何通过组合代码块来创建简单的动画。

#资源
本项目需要用到Scratch 2。 Scratch 2 可以通过 [jumpto.cc/scratch-on](http://jumpto.cc/scratch-on) 在线使用，也可以通过 [jumpto.cc/scratch-off](http://jumpto.cc/scratch-off) 下载安装离线版本离线使用。

您可以在 <a href="http://scratch.mit.edu/projects/26818098/#editor">这里</a>找到该项目的完整资源，也可以点击该项目的“下载项目资料”链接下载，项目文件名：

+ LostInSpace.sb2

本项目还有一个预加载外部资源的版本。 您可以通过 [jumpto.cc/space-resources](http://jumpto.cc/space-resources), 下载，或者到下载下来的工程资源中寻找，项目文件名：

+ LostInSpaceResources.sb2 

#学习目标
+ 循环:
	+ `Repeat` {.blockcontrol} 循环;
	+ `Forever` {.blockcontrol} 循环.

#挑战
+ "改进你的动画" - 改变代码中的数字；
+ "创建你自己的动画" - 应用所学创建一个新的动画。

#常见问题
+ 你可能需要提醒孩子们在动画开始前“重置”精灵的位置、大小和其他效果。可以在动画开始前添加如下代码轻松实现“重置”工作：

```blocks
	移到 x:(0) y:(0)
```

```blocks
	将角色的大小设定为 (100)
```

```blocks
	清除所有图形特效
```

+ “太空船”精灵会横向移动，我们需要将其顺时针旋转90度。旋转太空船是本项目教程的一部分，但如果这种方法有问题，可以用别的精灵代替太空船。

	![screenshot](space-rotate.png)

