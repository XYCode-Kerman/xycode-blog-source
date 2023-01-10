---
title: 从0开始配置你的manjaro! -- i3wm的安装
abbrlink: a7cc
date: 2023-01-07 16:52:53
tags:
	- manjaro
	- linux
	- 高效
	- i3wm
categories: 从0开始配置你的manjaro
cover: https://global-image-bed-1302614822.cos.ap-nanjing.myqcloud.com/images202301071904430.png
---
# 前言

> 推荐使用**aria2c**+**torrent**的方式下载manjaro镜像，cdn77的速度太慢了。
>
> 推荐直接下载i3wm的镜像，中文渲染问题我后面会一步一步带你解决。

# 安装manjaro

![image-20230107211351234](https://global-image-bed-1302614822.cos.ap-nanjing.myqcloud.com/images202301072113650.png)

在该界面设置好相关配置，推荐从闭源驱动启动，更加稳定。

![image-20230107211529609](https://global-image-bed-1302614822.cos.ap-nanjing.myqcloud.com/images202301072115926.png)

设置好后应该如上图所示，开源/闭源驱动看个人需求选择，我这里就用闭源驱动启动了。

启动后你应该能看到manjaro hello这一程序，点击上面的**Launch installer**按钮以进行安装。

> 如果出现中文渲染问题，你应当执行如下命令：
>
> ```bash
> sudo pacman-mirrors -c China
> sudo pacman -Sy wqy-zenhei
> ```

安装时会让你选择**引导驱动器**和**交换分区**，如果你的目标磁盘大于**30GB**，请果断选择**带休眠的交换分区**，否则请选择**不带休眠的交换分区**，也可以选择**交换到文件**，但交换分区是必须的！

如果你试图将manjaro作为**第二个系统**安装，请将引导程序安装到一个**与原系统不同的磁盘**，以免manjaro引导程序（grub）覆盖掉原系统的引导程序！

> 当原系统的引导程序被覆盖，你**几乎不可能**再次恢复其的引导程序，如果是Linux系统，可以在manjaro的grub中新增一个菜单，而Windows几乎不存在恢复可能！

![image-20230107214847098](https://global-image-bed-1302614822.cos.ap-nanjing.myqcloud.com/images202301072148608.png)

推荐**为管理员(root)使用同样的密码**。OFFICE套件可以选择安装，无必要不推荐安装（大不了用网页版Office365）。

![image-20230107215050464](https://global-image-bed-1302614822.cos.ap-nanjing.myqcloud.com/images202301072151144.png)

在*摘要*界面点击安装后，manjaro将会进行安装，该过程是**不可逆**的，请谨慎操作！

![image-20230107215755848](https://global-image-bed-1302614822.cos.ap-nanjing.myqcloud.com/images202301072157996.png)

出现如上界面，即代表安装完成，你可以在命令行中输入`reboot`或点击`现在重启`，并拔出你的安装介质（如`USB`、`光盘`）。

当出现如下界面，即代表你已经进入了manjaro，输入密码并按下回车即可登录。

![image-20230107220652875](https://global-image-bed-1302614822.cos.ap-nanjing.myqcloud.com/images202301072206358.png)

> 恭喜你，你已经成功安装了manjaro和i3-wm（以及一个lightdm），在下一章中，我们将讲解如何美化你的i3-wm和shell！
>
> 如果依然有中文渲染问题，请执行前面提到的代码！

# 附件

## I3WM默认常用键位

|       **键位**       |            **操作**            |
| :------------------: | :----------------------------: |
|     Mod + Enter      |            打开终端            |
|   Mod + Shift + Q    |          关闭当前窗口          |
|  Mod + 上/下/左/右   |            移动焦点            |
|     Mod + 数字键     |           切换工作区           |
| Mod + Shift + 数字键 | 将焦点上的窗口移动到对应工作区 |
|       Mod + D        |     打开dmenu（应用菜单）      |

> Mod键一般为**Windows徽标键**，少数为**Alt**键。
