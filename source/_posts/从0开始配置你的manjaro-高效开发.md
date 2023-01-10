---
title: 从0开始配置你的manjaro! -- 高效开发
abbrlink: 913e
date: 2023-01-09 19:38:13
tags:
	- manjaro
	- linux
	- 高效
	- i3wm
categories: 从0开始配置你的manjaro
cover: https://global-image-bed-1302614822.cos.ap-nanjing.myqcloud.com/images202301091941914.png
---
> 上文：{% post_link 从0开始配置你的manjaro-i3wm的美化 %}

# archlinuxcn

`archlinuxcn`是一个由社区维护的软件库，该库中包含许多在`aur`中的软件，免去编译的过程，**清华大学镜像站**有该软件库的镜像，可以高速下载。安装方法如下

1. 使用vim打开`/etc/pacman.conf`：`sudo vim /etc/pacman.conf`
2. 在末尾新增如下行：

```bash
[archlinuxcn]
Server = https://mirror.tuna.tsinghua.edu.cn/archlinuxcn/$arch
```

然后输入`pacman -Sy archlinuxcn-keyring`即可正常使用`archlinuxcn`。以下是archlinuxcn中的常用软件。

1. yay：aur包管理器，命令格式与`pacman`相同，无需在root下运行
2. timeshift：备份系统用的
3. microsoft-edge-stable-bin：微软的Edge浏览器

> 推荐在任何情况下都优先使用`yay`安装软件，`yay`会在无法在`aur`中找到软件包时自动调用`pacman`安装。

# zsh

manjaro自带了zsh，使用`chsh`即可切换。（输入的密码不会显示）

```bash
$ chsh
正在更改 xycode 的 shell。
密码：
新 shell [/usr/bin/bash]: /usr/bin/zsh
```

# ranger

ranger是一个Linux下的纯命令行文件管理器，在xorg环境下，ranger甚至可以在终端渲染出图片。![image-20230109195355282](https://global-image-bed-1302614822.cos.ap-nanjing.myqcloud.com/images202301091953031.png)

输入以下命令安装

```bash
sudo pacman -Sy ranger
```

我推荐你用一个短命令来代替`ranger`这一命令，你可以通过在`.zshrc`或`.bashrc`[^1]当中新增这样一段命令来实现

```bash
alias ra=ranger
```

执行该命令后，在shell中，`ra`将和`ranger`等价。（需要重新打开一个zsh终端）

# timeshift

timeshift是一个系统备份软件，其有一个命令行版本`timeshift`和GUI版本`timeshift-launche

[^1]: `.zshrc`是zsh在启动时执行的一段脚本，`.bashrc`同理，其格式与正常的终端命令相同！

