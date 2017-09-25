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

也可以直接下载 Myudisk 的完整文件 QUENONG.zip（MD5：d1cecbcd25561c9534ab901ba0b87e16）。

## 自动安装 CentOS-7.4-x86_64

## 手动安装 CentOS-7.4-x86_64


  [1]: http://laomaotao.net/down/2016/1015/4932.html
  [2]: http://laomaotao.net/down/2016/1015/4932.html
  [3]: https://gitee.com/quefei/myudisk/repository/archive/master
  [4]: http://mirrors.aliyun.com/centos/7/isos/x86_64/CentOS-7-x86_64-Minimal-1708.iso
  [5]: https://pan.baidu.com/s/1dEQfc7v