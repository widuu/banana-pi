banana pi 安装lubuntu开启vnc上传文件存储到七牛
===

>开源硬件banana pi非常不错，用来做测试和科研很爽的了，因为我的卡就8G，所以很难在这上边放很多东西，所以用了云存储

###Lubuntu

>前期先简单配置ssh服务

	#切换到root
	su root
	#修改root密码
	passwd root
	#安装vim和gcc
	apt-get install vim gcc
	#修改ssh的配置文件
	vim /etc/ssh/ssh_config
	PermitRootLogin yes
	PasswordAuthentication yes
	UsePAM no
	#重启ssh
	service ssh restart

>开启vnc服务
	
	  #安装tightvncserver
	  apt-get install tightvncserver
	  #tightvncserver之后输入密码
	  tightvncserver
	  #安装xfce4 
      apt-get install xfce4
	  #编辑vnc
	  vim ~/.vnc/xstartup
 	  startxfce4 &
 	  startlubuntu &
      #启动
	  vncserver -kill :1
      vncserver -geometry 1280x800 :1

![vnc桌面](https://raw.githubusercontent.com/widuu/banana-pi/master/images/vncserver.png)

>安装golang

	apt-get install golang
    vim ~/.bashrc
	export GOPATH=/root/golang

>上传自己的文件到七牛

 我当初测试写的源代码放在[https://gist.github.com/widuu/91446f2450cf969c586c](https://gist.github.com/widuu/91446f2450cf969c586c)

	go run fileupload.go -type file bizhi.jpg

  如下图所示上传成功
 ![上传](https://raw.githubusercontent.com/widuu/banana-pi/master/images/upload.png)