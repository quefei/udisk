# Myudisk

说明：

 - 仅支持一块 500G 以上的 SATA 硬盘
 - 需要一个 4G 以上的 U盘
 - 需要 CentOS 将硬盘识别为 sda，将U盘识别为 sdb
 - 需要使用 [老毛桃U盘启动盘制作工具][1]

## 制作 Myudisk

1.制作启动U盘：

使用 [老毛桃U盘启动盘制作工具][2] 将U盘制作成启动U盘，并且将其卷标命名为 **QUENONG**。

2.下载 Myudisk：

 - 下载 [Myudisk][3]，将 **QUENONG** 目录下的所有文件拷贝到U盘的 **根目录** 下；
 - 下载 [CentOS-7-x86_64-Minimal-1708.iso][4]，替换U盘里的 **CentOS-7-x86_64-Minimal-1708.txt**；
 - 下载 [CentOS-7-x86_64-NetInstall-1708.iso][5]，替换U盘里的 **CentOS-7-x86_64-NetInstall-1708.txt**；

也可以直接下载 Myudisk 的完整文件 [QUENONG.zip][6]（MD5：d1cecbcd25561c9534ab901ba0b87e16）。

## 自动安装 CentOS-7.4-x86_64

1.配置 IP 地址：

打开U盘里的 ks.cfg 文件，搜索 **######custom######**，替换 IP **192.168.1.5** 及网关 **192.168.1.1**。

2.开始安装：

 - 开机从U盘启动；
 - 选择 [10] 启动自定义ISO/IMG文件（LMT目录）
 - 选择 [02] 自动搜索并列出LMT目录下所有文件
 - 选择 [03] RUN CentOS-7-x86_64-NetInstall-1708.iso
 - 选择 Install CentOS 7
 - 等待安装完成

3.系统账户：

 - 用户：root ，密码：123456
 - 用户：admin，密码：123456

## 手动安装 CentOS-7.4-x86_64


  [1]: http://laomaotao.net/down/2016/1015/4932.html
  [2]: http://laomaotao.net/down/2016/1015/4932.html
  [3]: https://gitee.com/quefei/myudisk/repository/archive/master
  [4]: http://mirrors.aliyun.com/centos/7/isos/x86_64/CentOS-7-x86_64-Minimal-1708.iso
  [5]: https://pan.baidu.com/s/1dEQfc7v
  [6]: http://pan.baidu.com/s/1eSlHJUy