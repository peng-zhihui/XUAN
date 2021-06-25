![img1](/.assets/home/img1.jpg)

系统安装&配置

### 2.1 镜像烧录

200DK的系统基于Ubuntu Server 18.04，但是不能直接烧录原始镜像，需要首先进行一些系统配置包括安装NPU驱动和相关软件包等。

具体的操作流程可以参考：https://support.huaweicloud.com/dedg-A200dk_3000_c75/atlased_04_0013.html

整个过程比较漫长，需要下载一些工具并进行脚本配置，完整的制作镜像包我打包为`make_200dk_image.zip`文件了，其中主要是修改了原版文件`make_sd_card.py`中的默认板卡ip地址。

> 另外这里也提供我打包配置好的系统镜像可以直接烧录到SD卡。

### 2.2 连接网络

200DK开发板的接口比较少，不带无线网卡，且串口只能用于打印日志不能登录系统，所以只有三种方式登录板卡系统，可以参考：https://support.huaweicloud.com/dedg-A200dk_3000_c75/atlased_04_0015.html

在线文档中的连接方式都是基于Ubuntu服务器的，而其实我们可以利用200DK的USB网卡直接通过Windows共享网络，来很方便地配置开发板，同时让板子通过USB网卡接入互联网。

1. 在前面制作镜像的时候，将USB网卡的ip设置为`192.168.137.200`

   > 因为`192.168.137.1`是Windows共享网络的固定ip，设置共享网络时Windows会把接受共享的网卡的ip固定为这个，所以为了保证我们的开发板和USB网卡ip在同一网段选需要这么设置。

2. 用USB线连接开发板到电脑，按下面的链接安装好驱动：

   https://support.huaweicloud.com/dedg-A200dk_3000_c75/atlased_04_0038.html

3. 打开`网络适配器`，配置USB网卡的ip为静态地址`192.168.137.1`，DNS设置为和WLAN网卡一致，此时应该可以通过`192.168.137.200`连接到板卡的SSH了，但是还无法让开发板上网

   ![](https://pengzhihui-markdown.oss-cn-shanghai.aliyuncs.com/img/20201231165823.png)

4. 设置WLAN的属性页面共享网络到刚刚装好的USB网卡：

   ![](https://pengzhihui-markdown.oss-cn-shanghai.aliyuncs.com/img/20201231165028.png)

5. SSH进入到开发板系统，编辑如下文件：

   ```
   vi /etc/netplan/01-netcfg.yaml
   ```

   修改内容为：

   ```
   network:
     version: 2
   #  renderer: NetworkManager
     renderer: networkd
     ethernets:
       eth0:
         dhcp4: true
         addresses: []
         optional: true
   
       usb0:
         dhcp4: no
         addresses: [192.168.137.200/24]
         gateway4: 192.168.137.1
         nameservers:
               addresses: [192.168.158.140]
   ```

   其中nameservers为Windows的WLAN网卡中的DNS，执行如下命令重启网络服务：

   ```
   netplan apply
   ```

   然后就可以ping一下百度看看连接性了。

   > vim保存readonly文件方法：`:w !sudo tee %`

### 2.1 更换软件源

> 需要搞清楚的是：
>
> 1. Jetson Xavier NX 默认系统是 Ubuntu18.04LTS，对应源关键字：“bionic”
> 2. Jetson Xavier NX CPU是arm64的架构，镜像路径：xxx/ubuntu-ports/

```
sudo nano /etc/apt/sources.list
```

更换内容为（用的是清华源，也可以搜索其他的源）：

```
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports/ bionic-updates main restricted universe multiverse
deb-src http://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports/ bionic-updates main restricted universe multiverse
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports/ bionic-security main restricted universe multiverse
deb-src http://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports/ bionic-security main restricted universe multiverse
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports/ bionic-backports main restricted universe multiverse
deb-src http://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports/ bionic-backports main restricted universe multiverse
deb http://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports/ bionic main universe restricted
deb-src http://mirrors.tuna.tsinghua.edu.cn/ubuntu-ports/ bionic main universe restricted
```


