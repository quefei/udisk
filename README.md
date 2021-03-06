﻿# Quenong Myudisk

内容目录：

 - [重要说明][1]
 - [制作 Myudisk][2]
 - [自动安装 CentOS-7.4-x86_64][3]
 - [手动安装 CentOS-7.4-x86_64][4]
 - [相关文档][5]

## 重要说明

硬件要求：

 - 仅支持一块 500G 以上的 SATA 硬盘
 - 需要一个 4G 以上的 U盘
 - 需要 CentOS 将硬盘识别为 `sda`，将U盘识别为 `sdb`

## 制作 Myudisk

**1.1 制作启动U盘：**

使用 [老毛桃U盘启动盘制作工具][6]，先将U盘制作成启动U盘，再将U盘的卷标重命名为 `QUENONG`。

**1.2 下载 Myudisk：**

可以依次下载 [Myudisk][7]，[CentOS-7-x86_64-Minimal-1708.iso][8]，[CentOS-7-x86_64-NetInstall-1708.iso][9]。然后

 - 将 `QUENONG` 目录下的所有文件拷贝到U盘的 `根目录`
 - 用 CentOS-7-x86_64-Minimal-1708.iso 替换U盘里的 CentOS-7-x86_64-Minimal-1708.txt
 - 用 CentOS-7-x86_64-NetInstall-1708.iso 替换U盘里的 CentOS-7-x86_64-NetInstall-1708.txt

也可以下载 Myudisk 的完整打包 [QUENONG.zip][10]，然后将该目录下的所有文件拷贝到U盘的 `根目录`（MD5: d1cecbcd25561c9534ab901ba0b87e16）。

## 自动安装 CentOS-7.4-x86_64

**2.1 配置 IP：**

打开U盘里的 `ks.cfg` 文件，搜索 ######custom######，修改 IP `192.168.1.5` 及网关 `192.168.1.1`。

**2.2 开始安装：**

 - 开机从U盘启动
 - 依次执行：

    \[10] 启动自定义ISO/IMG文件（LMT目录）
    
    [02] 自动搜索并列出LMT目录下所有文件
    
    [03] RUN CentOS-7-x86_64-NetInstall-1708.iso
    
    Install CentOS 7

 - 等待安装完成

**2.3 系统账户：**

      用户：root      密码：123456
      用户：admin     密码：123456

**2.4 获得纯净的系统：**

删除 `/usr/local/bin` 目录下的文件。

## 手动安装 CentOS-7.4-x86_64

**3.1 配置 IP：**

打开U盘 manual-install 目录下的 `config-network` 文件，搜索 ######custom######，修改 IP `192.168.1.10` 及网关 `192.168.1.1`。

**3.2 开始安装：**

 - 开机从U盘启动
 - 依次执行：

    \[10] 启动自定义ISO/IMG文件（LMT目录）

    [02] 自动搜索并列出LMT目录下所有文件

    [03] RUN CentOS-7-x86_64-NetInstall-1708.iso

 - 选中 Test this media & install CentOS 7 并按下 `Tab` 键
 - 将内容修改为 `vmlinuz initrd=initrd.img inst.stage2=hd:/dev/sdb1 quiet inst.gpt`
 - 设置日期和时间，键盘，语言支持，安装位置等选项
 - 等待安装完成并重启

**3.3 配置网络：**

 - 如果网卡驱动默认已经安装
 - 挂载U盘，例如 `fdisk -l; mount -t vfat /dev/sdb1 /mnt`
 - 运行 `config-network`，例如 `cd /mnt/manual-install; ./config-network`

**3.4 获得纯净的系统：**

删除 `/usr/local/bin` 目录下的文件。


  [1]: https://github.com/quefei/myudisk#%E9%87%8D%E8%A6%81%E8%AF%B4%E6%98%8E
  [2]: https://github.com/quefei/myudisk#%E5%88%B6%E4%BD%9C-myudisk
  [3]: https://github.com/quefei/myudisk#%E8%87%AA%E5%8A%A8%E5%AE%89%E8%A3%85-centos-74-x86_64
  [4]: https://github.com/quefei/myudisk#%E6%89%8B%E5%8A%A8%E5%AE%89%E8%A3%85-centos-74-x86_64
  [5]: https://github.com/quefei/docs
  [6]: http://laomaotao.net/down/2016/1015/4932.html
  [7]: https://gitee.com/quefei/myudisk/repository/archive/master
  [8]: http://mirrors.aliyun.com/centos/7/isos/x86_64/CentOS-7-x86_64-Minimal-1708.iso
  [9]: https://pan.baidu.com/s/1dEQfc7v
  [10]: http://pan.baidu.com/s/1eSlHJUy