# linux-cenos7



## vmware虚拟机的三种网络模式

* VMnet0 虚拟机交换机：Bridged桥接模式
  * 特点：	
    * 默认使用VMnet0，不提供DHCP服务
    * 虚拟机与外部主机需要再同一个网段上，与局域网的其它机器没有区别
    * 可以与局域网内其它主机通信，可以与外部网络通信
    * 容易与局域网的其它主机引起ip地址冲突
* VMnet1 虚拟机交换机：Host-Only仅主机模式
  * 特点：
    * 默认使用VMnet1，提供DHCP服务（DHCP服务是指由服务器控制的一段ip地址范围，当客户机登录服务器时会自动获取服务器分配的IP地址与子网掩码）
    * 虚拟机可以和物理主机互相访问，但虚拟机无法访问外部网络
* Vmnet8 虚拟机交换机：NAT模式
  * 特点：
    * 默认使用VMnet0，提供DHCP服务
    * 虚拟机可以和物理主机互相访问，虚拟机可以访问外部网络
    * 局域网内其它机器访问不了

## linux CentOS7 网络命令

* 重启主机：reboot
* 重启网卡：systemctl restart network.service
* 查看Ip地址： ip addr
* 检测网络是否畅通： ping ip地址
* 结束ping 命令 ：ctrl + c
* 清屏：ctrl + l

## linux 远程链接工具

* xshull
* SecureCRT
* 使用前保证网络畅通
* 查看IP地址
* 注意：创建linux系统时，记得勾选可以使用ssh

## linux 虚拟机快速克隆与快照回复

* 克隆后的虚拟机执行重启网卡：systemctl restart network.service会报错
* 网卡路径：/etc/sysconfig/network-script/具体路径不同
* 使用vi工具进行编辑操作 按i进行编辑 按esc退出编辑模式 按wq进行保存
  * vi 要编辑的文件路径

* 快照相当于对服务器进行备份
