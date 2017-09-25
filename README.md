# Quenong Myudisk

 - [重要说明][1]
 - [制作 Myudisk][2]
 - [自动安装 CentOS-7.4-x86_64][3]
 - [手动安装 CentOS-7.4-x86_64][4]

## 重要说明

 - 仅支持一块 500G 以上的 SATA 硬盘
 - 需要一个 4G 以上的 U盘
 - 需要 CentOS 将硬盘识别为 sda，将U盘识别为 sdb
 - 需要使用 [老毛桃U盘启动盘制作工具][5]

## 制作 Myudisk

1.制作启动U盘：

使用 [老毛桃U盘启动盘制作工具][6] 将U盘制作成启动U盘，并且将其卷标命名为 **QUENONG**。

2.下载 Myudisk：

 - 下载 [Myudisk][7]，将 **QUENONG** 目录下的所有文件拷贝到U盘的 **根目录** 下；
 - 下载 [CentOS-7-x86_64-Minimal-1708.iso][8]，替换U盘里的 **CentOS-7-x86_64-Minimal-1708.txt**；
 - 下载 [CentOS-7-x86_64-NetInstall-1708.iso][9]，替换U盘里的 **CentOS-7-x86_64-NetInstall-1708.txt**；

也可以直接下载 Myudisk 的完整文件 [QUENONG.zip][10]（MD5：d1cecbcd25561c9534ab901ba0b87e16）。

## 自动安装 CentOS-7.4-x86_64

1.配置 IP 地址：

打开U盘里的 ks.cfg 文件，搜索 **######custom######**，替换 IP **192.168.1.5** 及网关 **192.168.1.1**。

2.开始安装：

 - 开机从U盘启动；
 - 选择 [10] 启动自定义ISO/IMG文件（LMT目录）；
 - 选择 [02] 自动搜索并列出LMT目录下所有文件；
 - 选择 [03] RUN CentOS-7-x86_64-NetInstall-1708.iso；
 - 选择 Install CentOS 7；
 - 等待安装完成。

3.系统账户：

    用户：root      密码：123456
    用户：admin     密码：123456

4.获得纯净的系统：

删除 **/usr/local/bin** 目录下的文件即可。

## 手动安装 CentOS-7.4-x86_64

1.配置 IP 地址：

打开U盘 manual-install 目录下的 config-network 文件，搜索 ######custom######，替换 IP 192.168.1.10 及网关 192.168.1.1。

2.开始安装：

 - 开机从U盘启动；
 - 选择 [10] 启动自定义ISO/IMG文件（LMT目录）；
 - 选择 [02] 自动搜索并列出LMT目录下所有文件；
 - 选择 [03] RUN CentOS-7-x86_64-NetInstall-1708.iso；
 - 选中 Test this media & install CentOS 7 并按下 Tab 键；
 - 将内容编辑为 `vmlinuz  initrd=initrd.img  inst.stage2=hd:/dev/sdb1  quiet  inst.gpt`；
 - 设置日期和时间、键盘、语言支持、安装位置等选项；
 - 等待安装完成并重启。

3.配置网络：

 - 如果网卡驱动默认已经安装；
 - 手动挂载U盘，例如 `fdisk  -l;  mount  -t  vfat  /dev/sdb1  /mnt`
 - 运行 config-network，例如 `cd  /mnt/manual-install;  ./config-network`

4.获得纯净的系统：

删除 **/usr/local/bin** 目录下的文件即可。


  [1]: https://github.com/quefei/myudisk#%E9%87%8D%E8%A6%81%E8%AF%B4%E6%98%8E
  [2]: https://github.com/quefei/myudisk#%E5%88%B6%E4%BD%9C-myudisk
  [3]: https://github.com/quefei/myudisk#%E8%87%AA%E5%8A%A8%E5%AE%89%E8%A3%85-centos-74-x86_64
  [4]: https://github.com/quefei/myudisk#%E6%89%8B%E5%8A%A8%E5%AE%89%E8%A3%85-centos-74-x86_64
  [5]: http://laomaotao.net/down/2016/1015/4932.html
  [6]: http://laomaotao.net/down/2016/1015/4932.html
  [7]: https://gitee.com/quefei/myudisk/repository/archive/master
  [8]: http://mirrors.aliyun.com/centos/7/isos/x86_64/CentOS-7-x86_64-Minimal-1708.iso
  [9]: https://pan.baidu.com/s/1dEQfc7v
  [10]: http://pan.baidu.com/s/1eSlHJUy