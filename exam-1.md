
# 一．安装虚拟机和centos，ubuntu的步骤：
* 1.在网上找到虚拟机的安装包，将其下载并安装在本地电脑上。
* 2.将centos和ubuntu系统的镜像在网上找到并保存到本地。
* 3.打开所下载的虚拟机，点击创建新的虚拟机选择典型进行下一步。
* 4.在本地上找到自己的镜像所在地，点击下一步进行安装。





* 5.按照提示一步一步给系统命名，保存，分配内存，最后创建成功。
* 6.创建成功后点击开启次虚拟机进行系统的安装，最后经过一段时间安装成功。（安装centos的时候要选择最小安装）

# 二．给centos系统和Ubuntu系统配置网络。
* 1.打开系统，登录超级用户root，在控制器上敲击命令 ip addr,发现网络配置文件中没有ip.

* 2.进入etc/sysconfig/network-scripts/目录查看ens33叫什么名字是在哪个文件当中。

* 3.进入文件fcfg-ens33将onboot=”NO”改为yes,将BOOTPROTO改为DHCP动态获取。 


* 4.保存文件通过service network restart重启网络服务。

* 5.再一次编辑ip addr有ip的数据了。

* 6.任意ping一个网站能接收数据。

* 7.在ubuntu系统中输入命令进入/etc/network/在interfaces中输入动态连接。

* 8./etc/init.d/networking restart 重启网络服务，实现连网。


# 三．Centose配置远程操作。
* 1.输入命令：rpm -qa|grep ssh检查是否安装了SSH，若没安装通过yum install openssh-server进行安装。

* 2.通过输入netstat -tnl查看ssh的端口是否打开监听。

* 3.进入ssh-config文件中将端口和远程登录，用密码登录等选项前面的#号去掉。

* 4.输入命令行 server sshd restart重启SSH服务
* 5.打开远程程序进行连接。

# 四．Ubuntu配置ssh.
* 1.打开终端，输入apt-get update更新一下。	

* 2.更新完毕之后通过敲击命令 apt-get install openssh-server安装ssh.
* 3.查看ssh服务是否开启，如没开启 输入service ssh start 开启。

* 4.进入etc/ssh/sshd_config修改配置文件将端口和监听打开。

* 5.通过远程进行连接。
