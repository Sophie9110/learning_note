## 1.words

pentest  渗透测试

vulnerabilities   漏洞

graphical interface  图形界面

robust  强大的

metasploit  元破解

  --24.19

framework  框架

spin   旋转

perspective  看法

daunting  令人生畏的

navigating   导航

GUI   图形用户界面

slash   削减

pwd -  print working directory

folder  文件夹

locate  定位

bash   Bash是一个命令处理器，通常运行于文本窗口中，并能执行用户直接输入的命令。Bash还能从文件中读取命令，这样的文件称为脚本。和其他Unix shell 一样，它支持文件名替换（通配符匹配）、[管道](https://ws.wiki.fallingwaterdesignbuild.com/baike-管道_(Unix))、[here文档](https://ws.wiki.fallingwaterdesignbuild.com/baike-Here文档)、命令替换、变量，以及条件判断和循环遍历的结构控制语句 https://ws.wiki.fallingwaterdesignbuild.com/wiki/Bash

dash   长划—

penetration  渗透

execute  执行

configuration  配置

script    脚本

overview 概述

default  默认

configuration  配置

userinfo  用户信息

hashcat  一款自称为世界上最快的密码破解工具。

crack   爆破

​    root   a user account with full and unrestricted access to a system.

make sure that these files can only be accessed by the root user

privilege  特权



## 2.commands

### 1.![image-20211220190705817](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211220190705817.png)

copy:   `cp  test.txt  Downloads/`    

delete:  `rm  Downloads/test.txt`  

move:  `mv    test.txt  Downloads/`

change password:    `passwd`



### 2.![image-20211220193248609](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211220193248609.png)

#### 1.chmod

(change mode)https://www.runoob.com/linux/linux-comm-chmod.html

r:可以查看此目录下的完整文件列表信息。

w：可以对此目录下的所有的文件及目录进行相关的更改，也就是可以更改这个目录下的结构列表（这个要重视） 具体权利如下：

   可以在此目录下创建新的文件或目录；

​    **可以在此目录下删除存在的文件或目录（不论该文件的权限是什么，这点要格外注意！！！！）**

   可以重命名及改变文件或目录的位置。

x：目录没有可执行的权限，因此目录中x的功能就是允许别的用户进入这个目录。

![image-20211220194612035](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211220194612035.png)

![img](https://img-blog.csdnimg.cn/20210111151702194.bmp?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3lhbmdxaWFuZzE5OTc=,size_16,color_FFFFFF,t_70)

“-”表示普通文件；
“l”是链接文件，相当于windows的快捷方式；
“b”是块设备，硬盘就是一个例子；
“c”是字符设备文件，鼠标，键盘算是；
“d”是目录文件，相当于windows的文件夹。
chmod 【数字】【文件名】——修改权限位

`chmod  777  test.txt`

#### 2.adduser

Linux adduser命令用于新增使用者帐号或更新预设的使用者资料。

adduser 与 useradd 指令为同一指令（经由符号连结 symbolic link）。

使用权限：系统管理员。

https://www.runoob.com/linux/linux-comm-adduser.html



#### 3./etc/passwd,/etc/shadow

​     用户名(login_name):是代表用户账号的字符串

　  口令(passwd):一些系统中，存放着加密后的用户口令字。虽然这个字段存放的只是用户口令的加密串，不是明文，但是由于/etc/passwd文件对所有用户都可读，所以这仍是一个安全隐患。因此，现在许多Linux系统（如SVR4）都使用了shadow技术，把真正的加密后的用户口令字存放到/etc/shadow文件中，而在/etc/passwd文件的口令字段中只存放一个特殊的字符，例如“x”或者“*”。

　　用户标识号(UID):是一个整数，系统内部用它来标识用户。一般情况下它与用户名是一一对应的。如果几个用户名对应的用户标识号是一样的，系统内部将把它们视为同一个用户，但是它们可以有不同的口令、不同的主目录以及不同的登录Shell等

​      主目录(home_directory):也就是用户的起始工作目录，它是用户在登录到系统之后所处的目录

​        登录Shell(Shell):用户登录后，要启动一个进程，负责将用户的操作传给内核，这个进程是用户登录到系统后运行的命令解释器或某个特定的程序，即Shell。Shell是用户与Linux系统之间的接口。Linux的Shell有许多种，每种都有不同的特点。常用的有sh(BourneShell),csh(CShell),ksh(KornShell),tcsh(TENEX/TOPS-20typeCShell),bash(BourneAgainShell)等。系统管理员可以根据系统情况和用户习惯为用户指定某个Shell。如果不指定Shell，那么系统使用sh为默认的登录Shell，即这个字段的值为/bin/sh

https://blog.csdn.net/a1154490629/article/details/52190801



## 3.network commands

![image-20211220222548173](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211220222548173.png)
