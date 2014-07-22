# BIT@Home 开发环境配置指南

标签（空格分隔）： BIT@Home

---

## 0. 安装 / 配置 Ubuntu 13.04 / 14.04
对于普通 PC，参见教程 [Ubuntu 14.04 安装基础教程(图文)][1]。

对于 Mac 机，推荐使用 rEFIt，参见安装教程 [怎么在Macbook上面安装Ubuntu？][2] 和配置教程 [MacBookAir (6,2) on Ubuntu 14.04 (Trusty Tahr)][3]。

由于上位机与底层硬件通信对 I/O 效率要求比较高，__不推荐以虚拟机的方式进行安装__。

安装完成之后，完成如下配置：

1. 修改软件源为北理开源镜像源；
2. 基础开发工具的安装，例如 build-essential / git / Vim / 翻墙工具 等，总之弄成让你自己觉得舒适的开发环境；

Linux 教程推荐 [UNIX Tutorial for Beginners][4]。

## 1. ROS 安装与配置
对于 Ubuntu 13.04 请参考 [Ubuntu install of ROS Hydro][5]。

对于 Ubuntu 14.04 请参考 [Ubuntu install of ROS Indigo][6]

安装配置完毕之后，新开一个终端，输入 rosc 并按 Tab 补全，若出现 roscd 则说明安装成功。

## 2. 官方教程
阅读 ROS 官方 Wiki 提供教程 [ROS Tutorials][7]，除此之外还可以参考中文教程 [古月居 - ROS教程][8]，后者基于一个比较早期的 ROS 版本，部分指令不同，参考即可。

## 3. IDE 项目开发
ROS 社区推荐的 IDE 有 Eclipse、CodeBlocks、NetBeans 以及 QtCreator，除了 Eclipse 配合 PyDev 插件可以跑 Python 项目之外，其余都是针对 C++ 项目，具体可参见官方 Wiki [IDEs][9]，Python 开发的话还推荐 PyCharm，参见教程 [ROS开发环境之PyCharm (python)][10]。

## 4. Git / Github 团队项目开发
Git 教程推荐 [沉浸式学 Git][11] / [Pro Git][12]，配合 [图解 Git][13] 食用味道更佳。

团队仓库使用如下：

1. 在本地新建一个工作区；
2. cd 进入工作区的 src 目录；
3. 执行命令 git clone git@github.com:ihainan/BITAtHomeSummer.git；
4. 后期的开发都是基于该仓库。

仓库使用说明：

1. 每次仅 Add 自己写的源代码；
2. 每个模块命名规律为 bitathome\_module\_name，例如对于硬件控制模块，该 Package 取名为 bitathome\_hardware\_control;
3. commit 注释必须认真填写，填写规范见：[Github上git commit 提交注释的规范][14]；
4. 本地测试通过之后再上传到仓库当中，对自己的代码负责。

## 5. 串口通信与运动控制

PC 上位机通过串口与旅行者三号底座通信。串口的基本概念参见 [串行接口 - 维基百科][15] 和 [串口通信的基本概念][16]

在 Linux 下进行串口通信编程，普通用户是没有权限读写串口设备，需要进行设置，参见 [Linux普通用户无权限使用串口设备的解决方法][17]。

Python 串口通信编程可使用 PySerial 模块，参见 [PySerial Short introduction][18]。Linux 环境下可使用 socat 虚拟串口，参见 [Virtual Serial Port for Linux][19] 中排名第二的答案。

旅行者三号串口通信协议见 [FTP 资料][20]，暑期作业见 [BIT@Home 14 年暑期集训作业(一)][21]。

## 6. BIT@Home 软件框架（v0.1）
初版框架模型 / 具体的分工参见文档 [BIT@Home 软件框架（初版）][22]

## 7. BIT@Home 开发指南（v0.1）
开发指南参见文档 [BIT@Home 开发指南（初版）][23]

---
最后编辑时间：2014/07/21 15:06


  [1]: http://forum.ubuntu.org.cn/viewtopic.php?f=77&t=458267
  [2]: http://www.zhihu.com/question/22932152
  [3]: https://help.ubuntu.com/community/MacBookAir6-2/Trusty
  [4]: http://www.ee.surrey.ac.uk/Teaching/Unix/
  [5]: http://wiki.ros.org/hydro/Installation/Ubuntu
  [6]: http://wiki.ros.org/indigo/Installation/Ubuntu
  [7]: http://wiki.ros.org/ROS/Tutorials
  [8]: http://blog.csdn.net/hcx25909/article/category/1191901
  [9]: http://wiki.ros.org/IDEs
  [10]: http://my.phirobot.com/blog/2013-12-ros_ide_for_python_pycharm.html
  [11]: http://igit.linuxtoy.org/contents.html
  [12]: http://git-scm.com/book/zh
  [13]: http://marklodato.github.io/visual-git-guide/index-zh-cn.html
  [14]: http://segmentfault.com/q/1010000000395039#a-1020000000400217
  [15]: http://zh.wikipedia.org/wiki/%E4%B8%B2%E8%A1%8C%E7%AB%AF%E5%8F%A3
  [16]: http://digital.ni.com/public.nsf/allkb/9F439B3D68D9072F4825703000383197
  [17]: http://tcthinking.diandian.com/post/2012-10-17/40039362949
  [18]: http://pyserial.sourceforge.net/shortintro.html
  [19]: http://stackoverflow.com/questions/52187/virtual-serial-port-for-linux
  [20]: ftp://ftp.bitathome.org/References/%E6%97%85%E8%A1%8C%E5%AE%B6III/%E6%97%85%E8%A1%8C%E5%AE%B6III%E9%80%9A%E4%BF%A1%E5%8D%8F%E8%AE%AE/
  [21]: http://www.bitathome.org/Assignment/14_Summer/1.pdf
  [22]: http://pan.baidu.com/s/1qWv1uVi#dir/path=/BIT@Home/Documents/Software%20Architecture
  [23]: http://pan.baidu.com/s/1qWv1uVi#dir/path=/BIT@Home/Documents/Dev%20Documentshttp://pan.baidu.com/s/1qWv1uVi#dir/path=/BIT@Home/Documents/Software%20Architecture