# KDXF-studypad-C10
# 科大讯飞AI学习机C10破解安装第三方应用

* 本项目仅供学习安卓玩机技巧，如果你的平板还需要拿来学习上面的资源和课程等，请退出本教程

* 尽管本教程内容不涉及解锁BL和刷机等等，但还是有一定风险，所以你必须有足够的心理预期，并且独自担负一切损失，你的损失和作者无关

* 欢迎各位读者在issue提出你的建议和问题

## 思路

在编程空间开启网络ADB调试，用电脑连接平板，使用ADB安装Shizuku和MT管理器，通过MT管理器实现绕过软件包管理器的安装拦截

## 优势

* 只需要一次电脑，以后安装第三方软件全在平板完成

* 支持V1.00.8或更低版本的系统，解决“洋葱学院替换法”因系统更新阉割工程模式无法实现的问题

## 准备工具

* 平板充满电且能打开编程空间应用，如果没有编程空间，则不可以使用本方案，请使用洋葱学院替换法，去酷安，B站和GitHub搜“科大讯飞AI学习机”即可找到教程，或者看这个：https://github.com/KDXF-BOOM/studentpad-research

* 一台能连WIFI的电脑，灵活的双手和会用搜索引擎的大脑

* 一口气下载好这里的文件，之后要用的时候别问我在哪里下载：https://www.123pan.com/s/tMz8Vv-1I4sh.html

* 传文件用的OTG线和U盘（或者你用QQ微信传，但是特别麻烦）

## 开始操作

### 开启网络ADB调试

1.打开编程空间应用

2.输入以下代码运行并保存，以后开机时方便直接运行

```

import os

os.system("setprop service.adb.tcp.port 5555")

os.system("setprop ctl.restart adbd")

```

### 电脑连接手机

1.解压ADB工具箱.zip里面的所有文件，双击“启动命令行.cmd”，如果打不开，运行“64位微软常用运行库合集.exe”根据提示安装即可，如果是32位电脑自己去百度下载32位的版本的运行库合集

2.解压“SPD-Driver_R4.20.4201.zip”，根据系统选择win7/8/10的驱动文件夹，双击DriverSetup.exe根据提示安装后重启电脑

3.平板和电脑连接同一WIFI，平板点击设置，找到我的设备，状态信息，IP地址，记住数字的那一行就是IP地址，如果你没找到数字或者数字在最后一行没显示全，则断开WIFI重新连接一次再找
![aboutdev](/pic/aboutdev.png)

4.输入adb connect <IP地址>，看到connected to 192.168.1.152:5555类似的就是成功了，如果出现ADB被占用，请退出360和2345等乱七八糟的软件，并运行ADB工具箱里的ADB占用清除工具

### 安装必备应用

1.在上一步连接成功后，输入以下内容来安装链接里的shizuku，MT管理器

```

adb install <apk文件路径> 

```

* 这里的<apk文件路径>可以直接拖拽apk进窗口实现自动填写，注意前面有个空格

2.如果看到以下内容则安装成功

```

Performing Stream Install

Success

```

### 让MT管理器接管系统软件包安装程序

1.打开Shizuku，点击通过无线调试启动，如果成功了，会自动返回主页显示shizuku正在运行，如果失败了，去编程空间运行之前保存好的那个脚本再试
![shizuku](/pic/shizuku.png)

2.打开MT管理器，看到弹窗后确认Shizuku授权

3.随便弄一个apk文件安装，如果MT管理器没有调用系统安装器，而是直接在应用内安装，则接管成功

### 防止破解方法被封杀

使用Shizuku授权Scene的ADB模式，找到应用管理，把系统更新和系统升级还有应用中心都冻结掉（非常重要！）因为AI编程空间可能会被应用商店强制更新，已知更新后AI编程空间无法运行无线调试启动代码！
如果你已经发现被强制更新了，但你还安装了MT管理器，或者你有安装MT管理器的办法，你可以打开MT管理器，输入以下代码启用无线调试，并冻结上述三个应用。

```

setprop service.adb.tcp.port 5555

setprop ctl.restart adbd

```

### 重启后怎么做

1.重启后网络ADB调试会自动关闭，这时你只需要去编程空间运行你保存的脚本，再去激活Shizuku，然后就可以在MT管理器自由安装应用了

## 系统优化

### 第三方桌面

安装Lawnchair，在多任务页面长按Lawnchair的图标，点击右边的圆圈内感叹号图标，将其设置为默认主屏幕应用
!![desktop](/pic/desktop.png)


### 第三方输入法

注意，讯飞输入法更新后，重启会自动卸载，推荐使用百度输入法

### 解除部分网址访问限制

为解除限制，请进行如下操作，重启后需要重新操作
!(/net/1.jpg)
!(/net/2.jpg)
!(/net/3.jpg)
!(/net/4.jpg)
!(/net/5.jpg)
!(/net/6.jpg)
!(/net/7.jpg)
