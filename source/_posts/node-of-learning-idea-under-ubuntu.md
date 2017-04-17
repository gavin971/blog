---
title: Ubuntu下IntelliJ IDEA使用笔记
date: 2017-04-17 18:00:00
categories: IDE
tags: [Ubuntu, IDE]
---
# Preface
> 使用IDEA


<!--more-->
# Install

博主采用***[Toolbox App](https://www.jetbrains.com/toolbox/app/)*** 方式安装，方便管理更新。
安装的时候注意**配置安装路径**：
![](http://ojoba1c98.bkt.clouddn.com/img/learning-idea-under-ubuntu/idea-setting-path.png)
至于*注册码*，嘿嘿，度娘你懂的。

# Keyboard shortcuts


# Plugin
## 热部署插件JRebel安装与激活
> 每次修改java文件都需要重启tomcat，很痛苦有木有？ 推荐给大家一个很好用的热部署插件，JRebel，目前是最好的，在使用过程中应该90%的编辑操作都是可以reload的，爽歪歪，节约我们大量的开发时间，提高开发效率。

### 安装
两种方式安装：
#### 方式一
下载安装，前往***[JRebe官网下载地址](https://zeroturnaround.com/software/jrebel/download/nightly-build/#!/intellij)***，选择对应IDE的版本下载，然后安装（下面照搬官网说的...）：
1、Open File > Settings (Preferences on macOS). Select Plugins.
2、Press Install plugin from disk…
3、Browse to the downloaded archive and press OK. Complete the installation.

#### 方式二
直接安装：
1、Open File > Settings. Select Plugins.
2、Press Browse Repositories.
3、Find JRebel. Press Install plugin.
4、Next → ***[Activation](https://zeroturnaround.com/software/jrebel/quickstart/intellij/#!/activation)***

### 激活
先戳进***[官网](https://my.jrebel.com/)***，使用Facebook或Twitter注册登录，之后就可以免费申请激活码了：
![](http://ojoba1c98.bkt.clouddn.com/img/learning-idea-under-ubuntu/myrebel-activation-code.png)

打开 `Help` > `JRebel` > `Activation`，将申请的激活码复制进去，稍等片刻完成激活。

### 工程配置
打开  `view` > `tool window` > `Jrebel`，在弹出框中勾选你要热部署的项目：
![](http://ojoba1c98.bkt.clouddn.com/img/learning-idea-under-ubuntu/jrebel-project-setting.png)
在tomcat配置中勾选图示选项：
![](http://ojoba1c98.bkt.clouddn.com/img/learning-idea-under-ubuntu/jrebel-tomcat-setting.png)
**deployment 要选择后缀为explored的工程**。

### 启动
点击 ![](http://ojoba1c98.bkt.clouddn.com/img/learning-idea-under-ubuntu/jrebel-startup.png) JRebel图标，启动项目


# Conflict of keyboard shortcuts
快捷键有冲突，创建脚本并执行：
```bash
#!/bin/bash  
gsettings set org.gnome.desktop.wm.keybindings toggle-shaded "[]" 
gsettings set org.gnome.settings-daemon.plugins.media-keys screensaver "[]"
gsettings set org.gnome.desktop.wm.keybindings switch-to-workspace-left "[]" 
gsettings set org.gnome.desktop.wm.keybindings begin-move "[]" 
```

**目前发现的快捷键冲突：**
1、`ctrl+alt+方向`，直接到系统设置里面改：
![](http://ojoba1c98.bkt.clouddn.com/img/learning-idea-under-ubuntu/idea-setting-keyboard.png)

2、安装了搜狗之后，按`ctrl+alt+b`会启动虚拟键盘，所以在输入法里面打开Fcitx设置，在附加组件里面，点击高级，再把虚拟键盘的选项去掉：
![](http://ojoba1c98.bkt.clouddn.com/img/learning-idea-under-ubuntu/idea-sougou-conflict.png)
然后注销或重启电脑。

3、`ctrl+alt+s`，同样，键盘里面找到，然后禁用掉。