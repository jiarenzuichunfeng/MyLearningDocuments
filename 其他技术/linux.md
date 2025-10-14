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

## 基础命令



```
切换目录
	cd 路径
	cd - 回到切换前的目录
	cd .. 返回上一层目录
列出目录内容
	ls
	ls -a 显示隐藏文件
	ls -l 以列表展示
	ls -lt 以列表展示以时间排序（升序）
	ls -ltr 以列表展示以时间排序（降序）
	ls -a
查询所在目录
	pwd
查看小文件内容
	cat
	cat -n 显示行号
查看大文件内容
	more
查看文件的前面n行
	head -N 文件名
查看文件的后面n行
	tail -N 文件名
	tail -f 动态查看
创建一个空文件
	touch
创建目录
	mkdir
	makdr -p 创建多级目录
删除目录
	rmdir
拷贝文件
	cp 文件名 要复制到的位置/（新文件名）
	cp -a（复制文件属性） 文件名 要复制到的位置
移动或更名现有的文件或目录
	mv 文件名 新文件名 
	mv 文件名 要移动到的位置（新文件名）
删除文件或目录
	rm 有提示
	rm -rf 不需要提示 可以删除目录
对比文件差异
	diff 文件1 文件2 打印出不一样的内容
远程安全登录方式（切换主机）
	ssh ip地址 
退出命令
	exit
查看用户
	id 用户名
查新主机信息
	uname
	uname -a 查看详细主机信息
查看网络是否畅通
	ping ip地址或域名
标准输出命令
  echo "要输出的内容"
查看帮助文档
	man 命令
查看内部命令帮助
	help
清屏
	clear
当前在本地系统上的所有用户的信息
	who
	whoami 查看用户
查询系统信息
	uptime
	w
查看系统内存
	free
	free -m 以M显示
	free -g 以G显示
	free -h 
统计行
	wc -l 文件名
查找文件里符合条件的字符串
	grep
	grep -n 字符串 文件名 查看行数
	grep -w 字符串 文件名 精确匹配
	grep -v 字符串 文件名 排除
	grep -i 字符串 文件名 忽略大小写
查询文件
	find 从哪里开始查  查询标准 要查询的文件或文件夹
对排序好的内容进行统计
	uniq
对内容进行排序
	sort
```

