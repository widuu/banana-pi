banana pi 基础之连接
===

>今天拿到了banana pro,我现在的情况是这样的，只有一颗网线，显示器是VGA接口的，无线路由器是TP mini没有网线接口的那种，现在就开始吧！


###下载系统

>系统从这里下载http://www.lemaker.org/resources/29-4/%E9%95%9C%E5%83%8F%E6%96%87%E4%BB%B6.html
>我试用了fedora、lubuntu、Raspbian、ArchLinux，感觉上是lubuntu和fedora感觉不错，尤其是fedora。

###刷入系统


>详见http://www.lemaker.org/resources/29-5/%E5%BF%AB%E9%80%9F%E5%85%A5%E9%97%A8%E6%8C%87%E5%8D%97.html

###连接bananapi

>我的无线路由器不能接入网线，怎么办呢？这样处理，打开电脑->网络->右键属性->更改适配器设置->选择WlAN右键属性->允许其它网络用户通过计算机的Internet打钩
![wlan连接](../images/wlan.png)

>然后将banana pi连接的网线口一端连接电脑，开机启动,我的电源用的是充电宝，输出最大是2.1A

![连接banana pi](../images/IMG_0078.JPG)

>这时候windows电脑->调出运行->cmd->arp -a查看我的IP地址如下

![arp -a](../images/arp.png)

>然后putty连接,OK登陆上去了,

![putty](../images/bananapi-linux.png)

	#安装vnc
	apt-get install tightvncserver

	#配置vnc
	tightvncserver #输入两次密码
	Woulid you like to enter a view-only password(y/n)输入n


>OK,现在连接VNC


![vnc](../images/vnc.png)

OK，到这里就结束了，我们手上就两样东西，一个移动电源，一个网线现在也可以用了！

技术文档来自：[http://www.widuu.com/archives/10/1112.html](http://www.widuu.com/archives/10/1112.html)

硬件提供banana pi官网：[http://www.lemaker.org/](http://www.lemaker.org/)
	





