## 1.words

pentest  渗透测试

vulnerabilities   漏洞

graphical interface  图形界面

robust  强大的

metasploit  元破解

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

home router  家用路由器

protocal   协议

button  按钮

utilize  利用

encrypted  加密

algorithm  算法

scramble   争夺

padlock  挂锁

certificate   证书

authenticate  认证

Filtering             过滤

general     一般

Authorization 授权

 Stuff  东西

Stateless   无状态的

Transactions  交易

Tweak  调整

Flip  翻动

Cache  control   缓存控制

Analogous  类似的

 Functionality  功能

Mechanism  机能

Interaction  相互作用

Route  路由器

Interpreter 口译员

Domain  name 域名

Generate 产生

append  附加

sync  同步

retrieve   取回

simultaneous      同时

dynamic    动态的

capacitor   电容器

nic  网卡

pivot  转动

load up  加载 

  boot  开机 

sequel   续集 

database  数据库

malicious   恶意的

redundant 多余的

spin up   启动

load up    加载
  boot   开机
 sequel  续集
 database  数据库
 malicious   恶意的
redundant  多余的
 spin up an ftp server  启动
Postgresql   
update  更新
upgrade  升级
repositories  存储库
abort  终止
script  脚本
bash  猛击
for loop  for循环
narrow down  缩小范围 
lingers  徘徊
pipe  |   mean  add an aditional command
bracket  括号

ampersand  &  与号
do threading  做线程
sequence  顺序
ip sweep  IP扫描







## 2.commands

### 1.basic commands![image-20211220190705817](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211220190705817.png)

copy:   `cp  test.txt  Downloads/`    

delete:  `rm  Downloads/test.txt`  

move:  `mv    test.txt  Downloads/`

change password:    `passwd`



### 2.user  commands![image-20211220193248609](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211220193248609.png)

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

### 1.ifconfig

Linux ifconfig命令用于显示或设置网络设备。

ifconfig可设置网络设备的状态，或是显示目前的设置。

https://www.runoob.com/linux/linux-comm-ifconfig.html

#### 2.iwconfig

iwconfig命令用于系统配置无线网络设备或显示无线网络设备信息

iwconfig命令类似于[ifconfig](https://ywnz.com/linux/ifconfig/)命令，但是他配置对象是无线网卡，它对网络设备进行无线操作，如设置无线通信频段。

#### 3.ping

 ping 命令用于检测主机。

执行 ping 指令会使用 ICMP 传输协议，发出要求回应的信息，若远端主机的网络功能没有问题，就会回应该信息，因而得知该主机运作正常。

https://www.runoob.com/linux/linux-comm-ping.html

#### 4.arp

Linux arpwatch命令用于监听网络上ARP的记录。

ARP(Address Resolution Protocol)是用来解析IP与网络装置硬件地址的协议。

arpwatch可监听区域网络中的ARP数据包并记录，同时将监听到的变化通过E-mail来报告。



#### 5.netstat

Linux netstat 命令用于显示网络状态。

利用 netstat 指令可让你得知整个 Linux 系统的网络情况。

#### 6.route

![image-20211221202304884](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211221202304884.png)

## 4.viewing,creating,and editing files

![image-20211223183156790](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211223183156790.png)

#### 1.echo

echo命令的功能是在显示器上显示一段文字，一般起到一个提示的作用。此外，也可以直接在文件中写入要写的内容。

echo命令常用的两个选项： -n   和   -e  

echo的重定向

##### 1.replacing

echo “想要的内容”> 文件名

 将想要的内容覆盖到对应的文件当中去，文件当中之前的内容不复存在了，实际上是修改了原文件的内容。

#####   2.appending

echo “想要的内容”>> 文件名

 将想要的内容追加到文件后，对文件之前的内容不修改，只进行增添，也叫追加重定向。             

#### 2.cat

（concatenate）命令用于连接文件并打印到标准输出设备上。

https://www.runoob.com/linux/linux-comm-cat.html

#### 3.touch

Linux touch命令用于修改文件或者目录的时间属性，包括存取时间和更改时间。若文件不存在，系统会建立一个新的文件。

ls -l 可以显示档案的时间记录。

用指令"touch"修改文件"testfile"的时间属性为当前系统时间，输入如下命令：

 `touch testfile`                #修改文件的时间属性 

#### 4.nano

nano是一个字符终端的文本编辑器，有点像DOS下的editor程序。它比vi/vim要简单得多，比较适合[Linux](https://so.csdn.net/so/search?from=pc_blog_highlight&q=Linux)初学者使用。某些Linux发行版的默认编辑器就是nano。

nano命令可以打开指定文件进行编辑，默认情况下它会自动断行，即在一行中输入过长的内容时自动拆分成几行，但用这种方式来处理某些文件可能会带来问题，比如Linux系统的配置文件，自动断行就会使本来只能写在一行上的内容折断成多行了，有可能造成系统不灵了。因此，如果想避免这种情况出现，就加上-w选项。

**语法**--nano [选项] [[+行,列] 文件名]...

#### 5.gedit

  这是 Linux 下的一个纯文本编辑器,但你也可以把它用来当成是一个集成开发环境 (IDE), 它会根据不同的语言高亮显现关键字和标识符。

命令行下输入：gedit  回车即可



## 5.service command(useful for pentesting)

#### 1.service

   `sevice  apache2 start(stop)`

   `python2 -m SimpleHTTPServer  98`

server

#### 2.systemctl

`systemctl enable postgresql`

keep something online  the entire time

allow us to run metasploit and   have the postgresql database running when we boot so it doesn't have to take the extra time to load it.(matasploit,apache) 

 Linux服务管理两种方式service和systemctl

systemd是Linux系统最新的初始化系统(init),作用是提高系统的启动速度，尽可能启动较少的进程，尽可能更多进程并发启动。

systemd对应的进程管理命令是systemctl

 the service command deals with services. It's going to allow us to start and stop services on the fly. And the systemctl Command is going to allow us to enable or disable services so that they load up on boot or do not load up on boot.  

## 6.Install and Updating Tools

#### 1.Install updates with apt-get

apt-get update &&apt-get upgrade

apt-get update --looking through packages  predifined the repositories .

apt-get upgrade --packages installed

#### 2.Install tools with apt-git

sudo apt-get install  git



#### 3.Using git(github)

task:git安装 veil-framework

 `git clone https://github.com/Veil-Framework/Veil.git` 

原github地址https://github.com/Veil-Framework/Veil

## 7.scripting  with bash

#### 1.grep

Linux grep 命令用于查找文件里符合条件的字符串。

如果发现某文件的内容符合所指定的范本样式，预设 grep 指令会把含有范本样式的那一列显示出来。若不指定任何文件名称，或是所给予的文件名为 **-**，则 grep 指令会从标准输入设备读取数据。

在当前目录中，查找后缀有 file 字样的文件中包含 test 字符串的文件，并打印出该字符串的行。此时，可以使用如下命令：

`grep test *file` 

此外还有递归查找和反向查找https://www.runoob.com/linux/linux-comm-grep.html

#### 2.cut

Linux cut命令用于显示每行从开头算起 num1 到 num2 的文字。

`cut  [-bn] [file]`
`cut [-c] [file]`
`cut [-df] [file]`

cut 命令从文件的每一行剪切字节、字符和字段并将这些字节、字符和字段写至标准输出。

如果不指定 File 参数，cut 命令将读取标准输入。必须指定 -b、-c 或 -f 标志之一。

https://www.runoob.com/linux/linux-comm-cut.html

#### 3.tr

 tr 命令用于转换或删除文件中的字符。

tr 指令从标准输入设备读取数据，经过字符串转译后，将结果输出到标准输出设备。

将文件testfile中的小写字母全部转换成大写字母，此时，可使用如下命令：

`cat testfile |tr a-z A-Z` 

#### (grep,cut,tr --narrow down some results that identifies with a positive ping)

cat ping.txt |grep "64 bytes" |cut -d " "  -f  4| tr  -d  ":"

## 8.script writing

原文链接https://leonardcucos.com/how-to-make-a-ping-sweep-linux-script/

#### 1.#!/bin/bash

Note: #!/bin/bash is a hard-coded function that tells the Linux operating system to use bash as a command interpreter. 

#### 2.for loop:

`for ip in seq 1 10 ; do`
`ping -c 1 $1.$ip | grep "64 bytes" | cut -d " " -f 4 | tr -d “:” &`
`done`
Where: 

`seq 1 254` =  sequence starting from 1 to 254 [pay attention to the backticks “]

`-c 1` = count 1 

`$1` = user input [the first 3 octets of the network in this case]

`.$ip` = the sequence starting with 1 to 254

`-d` = delimiter

`tr` = translate

`&` = allows multithreading [ping all the IPs at once]

Explanation: For every IP in sequence starting from 1 to 254, do a count one ping where the network address is the user input $1 [the first three octets of the network in this case and defined when running the script], and the .$ip is the ‘seq 1 254’. List only the lines containing the “64 bytes” pattern. The rest of the command is used to filter out the unnecessary ping information and is explained in the previous section.

#### 3.Run The Ping Sweep Linux Script

To run the Ping Sweep script, we need to make the pingsweep.sh file executable. To do that, type in the terminal:

`chmod +x pingsweep.sh`
To execute the pingsweep.sh script, type in the terminal:

`./pingsweep.sh 192.168.2 > ips.txt`
To view the content in the ips.txt file, type the following command in the terminal:

`cat ips.txt`

#### 4.a little improvement

Add the following code after #!/bin/bash:

`if [ “$1” == “” ]`
`then`
`echo “Type the IP address to scan.”`
`echo “Example: ./pingsweep.sh 192.168.2”`
`else`

To indicate the end of the inner “if” statement above, we need to add the keyword “fi” at the end of the script.

Finally, this is how your pingsweep.sh file should look like: 

`#!/bin/bash`
`if [ “$1” == “” ]`
`then`
`echo “Type the IP address to scan.”`
`echo “Example: ./pingsweep.sh 192.168.2”`
`else`
`for ip in seq 1 254 ; do`
`ping -c 1 $1.$ip | grep "64 bytes" | cut -d " " -f 4 | tr -d “:” &`
`done`
`fi`

#### 5.nmap

for ip in $(cat ips.txt); do nmap -p 80 -T4 $ip & done 

## 9.learning resources

#### 1.youtube

https://www.youtube.com/watch?v=wDQ0KXR4D7A

https://www.youtube.com/watch?v=MM7qPnJSnLQ

#### 2.hackthebox.com

#### 3.virtualhackinglabs.com

#### 4.vulnhub.com

#### 5.elearnsecurity.com

#### 6.offensive-security.com

#### 7.giac.org



