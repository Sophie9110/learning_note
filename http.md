# 1.基础知识:

Client / Server
Stateless
 Application Layer
 Client Actions
 Server Status Codes
 Headers



TCP/IP 协议族按层次分别分

为以下 4 层：应用层、传输层、网络层和数据链路层。

# 应用层

**决定了向用户提供应用服务时通信的活动**。

TCP/IP 协议族内预存了各类通用的应用服务。比如，FTP（File

Transfer Protocol，文件传输协议）和 DNS（Domain Name System，域

名系统）服务就是其中两类。

**HTTP** 协议也处于该层。

# 传输层

传输层对上层应用层

**提供处于网络连接中的两台计算机之间的数据传输。**

在传输层有两个性质不同的协议：TCP（Transmission Control

Protocol，传输控制协议）和 UDP（User Data Protocol，用户数据报

协议）。

# 网络层（又名网络互连层）

**网络层用来处理在网络上流动的数据包**。数据包是网络传输的最小数

据单位。该层规定了通过怎样的路径（所谓的传输路线）到达对方计

算机，并把数据包传送给对方。

与对方计算机之间通过多台计算机或网络设备进行传输时，网络层所

起的作用就是在众多的选项内选择一条传输路线。

# 链路层（又名数据链路层，网络接口层）

**用来处理连接网络的硬件部分**。包括控制操作系统、硬件的设备驱

动、NIC（Network Interface Card，网络适配器，即网卡），及光纤等

物理可见部分（还包括连接器等一切传输媒介）。硬件上的范畴均在

链路层的作用范围之内。

<img src="C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222160700596.png" alt="image-20211222160700596" style="zoom: 67%;" />

#### “IP”其实是一种协议的名称。

IP 协议的作用是把各种数据包传送给对方

要保证确实传送到对方那里，则需要满足各类条件。其中两个重要的条件是 IP 地址和 MAC地址（Media Access Control Address）。

IP 地址指明了节点被分配到的地址，MAC 地址是指网卡所属的固定

地址。IP 地址可以和 MAC 地址进行配对。IP 地址可变换，但 MAC

地址基本上不会更改。

使用 ARP 协议凭借 MAC 地址进行通信

IP 间的通信依赖 MAC 地址。在网络上，通信的双方在同一局域网

（LAN）内的情况是很少的，通常是经过多台计算机和网络设备中转

才能连接到对方。而在进行中转时，会利用下一站中转设备的 MAC

地址来搜索下一个中转目标。这时，会采用 ARP 协议（Address

Resolution Protocol）。ARP 是一种用以解析地址的协议，根据通信方的 IP 地址就可以反查出对应的 MAC 地址。

#### 按层次分，TCP 位于传输层，提供可靠的字节流服务。

所谓的字节流服务（Byte Stream Service）是指，为了方便传输，将大块数据分割成以报文段（segment）为单位的数据包进行管理。而可靠的传输服务是指，能够把数据准确可靠地传给对方。一言以蔽之，TCP 协议为了更容易传送大数据才把数据分割，而且 TCP 协议能够确认数据最终是否送达到对方。

##### 准确无误地将数据送达目标处，TCP 协议采用了三次握手（three-way handshaking）策略

<img src="C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222161821838.png" alt="image-20211222161821838" style="zoom:80%;" />



负责域名解析的 DNS 服务

DNS（Domain Name System）服务是和 HTTP 协议一样位于应用层的

协议。它提供域名到 IP 地址之间的解析服务。

计算机既可以被赋予 IP 地址，也可以被赋予主机名和域名。比如

www.hackr.jp。



![image-20211222161948795](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222161948795.png)



![image-20211222162230254](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222162230254.png)

**URL**（Uniform Resource Locator，统一资源定位符）

URL 正是使用 Web 浏览器等访问 Web 页面时需要输入的**网页地址**。比如 http://hackr.jp/就是 URL。

**URI** ( Uniform Resource Identifier, 统一资源标识符) 

URI 就是由**某个协议方案表示的资源的定位标识符**。协议方案是指访问资源所使用的协议类型名称。

Resource:资源的定义是“可标识的任何东西”。除了文档文件、图像或服务（例如当天的天气预报）等能够区别于其他类型的，全都可作为资源。另外，资源不仅可以是单一的，也可以是多数的集合体。

Identifier:表示可标识的对象。也称为标识符。

采用 HTTP 协议时，协议方案就是 http。除此之外，还有 ftp，25mailto、telnet、file 等...`

Resource：资源的定义是“可标识的任何东西”。除了文档文件、图像或服务（例如当天的天气预报）等能够区别于其他类型的，全都可作为资源。另外，资源不仅可以是单一的，也可以是多数的集合体。

Identifier：表示可标识的对象。也称为标识符。

**URI 用字符串标识某一互联网资源，而 URL 表示资源的地点（互联**

**网上所处的位置）**。可见URL 是 URI 的子集。

### URI examples:

ftp://ftp.is.co.za/rfc/rfc1808.txt

http://www.ietf.org/rfc/rfc2396.txt

ldap://[2001:db8::7]/c=GB?objectClass?one

mailto:John.Doe@example.com

news:comp.infosystems.www.servers.unix

tel:+1-816-555-1212

telnet://192.0.2.16:80/

urn:oasis:names:specification:docbook:dtd:xml:4.1.2

#### URI 格式

**1.相对 URL，是指从浏览器中基本 URI 处指定的 URL，**

**形如 /image/logo.gif。**

**2.绝对URI:**

![image-20211222164046061](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222164046061.png)

1.使用 http: 或 https: 等协议方案名获取访问资源时要指定协议类型。不区分字母大小写，最后附一个冒号（:）。

也可使用 data: 或 javascript: 这类指定数据或脚本程序的方案名。

2.登录信息（认证）---指定用户名和密码作为从服务器端获取资源时必要的登录信息（身份认证）。此项是可选项。

3.服务器地址---使用绝对 URI 必须指定待访问的服务器地址。地址可以是类似hackr.jp 这种 DNS 可解析的名称，或是 192.168.1.1 这类 IPv4 地址名，还可以是 [0:0:0:0:0:0:0:1] 这样用方括号括起来的 IPv6 地址名。

4.服务器端口号---指定服务器连接的网络端口号。此项也是可选项，若用户省略则自动使用默认端口号。

5.查询字符串---针对已指定的文件路径内的资源，可以使用查询字符串传入任意参数。此项可选。

6.片段标识符---使用片段标识符通常可标记出已获取资源中的子资源（文档内的某个位置）。该项也为可选项。

**RFC**(**R**equest **f**or **C**omments），又翻译作**意见征求**，**意见请求**，**请求评论**[[1\]](https://ws.wiki.fallingwaterdesignbuild.com/wiki/RFC#cite_note-1)是由[互联网工程任务组](https://ws.wiki.fallingwaterdesignbuild.com/baike-互联网工程任务组)（IETF）发布的一系列[备忘录](https://ws.wiki.fallingwaterdesignbuild.com/baike-備忘錄)。文件收集了有关[互联网](https://ws.wiki.fallingwaterdesignbuild.com/baike-網際網路)相关信息，以及[UNIX](https://ws.wiki.fallingwaterdesignbuild.com/baike-UNIX)和互联网[社群](https://ws.wiki.fallingwaterdesignbuild.com/baike-社群)的软件文件，以编号排定。

# 2.简单的HTTP协议：



#### 1.请求与访问：

仅从一条通信路线来说，服务器端和客户端的角色是确定的，而用 HTTP 协议能够明确区分哪端是客户端，哪端是服务器

端。

![image-20211222165256922](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222165256922.png)

请求访问某台 HTTP 服务器上的/index.htm 页面资源。



![image-20211222170535846](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222170535846.png)





起始行开头的GET表示请求访问服务器的类型，称为方法（method）。随后的字符串 /index.htm 指明了请求访问的资源对象，也叫做请求 URI（request-URI）

**请求报文**是由请求方法、请求 URI、协议版本、可选的请求首部字段

和内容实体构成的。



![image-20211222170352573](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222170352573.png)



**响应报文：**

![image-20211222170944685](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222170944685.png)

**stateless :HTTP是不保存状态的协议**



![image-20211222171101780](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222171101780.png)

#### 使用 URI 让客户端定位到资源

当客户端请求访问资源而发送请求时，URI 需要将作为请求报文中的

请求 URI 包含在内

![image-20211222210235535](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222210235535.png)

#### 2.方法

#### GET ：获取资源

GET 方法用来请求访问已被 URI 识别的资源。指定的资源经服务器

端解析后返回响应内容。



![image-20211222210409014](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222210409014.png)

#### POST：传输实体主体

虽然用 GET 方法也可以传输实体的主体，但一般不用 GET 方法进行

传输，而是用 POST 方法

![image-20211222210806050](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222210806050.png)

例子

POST /submit.cgi HTTP/1.1

请求Host: www.hackr.jp

Content-Length: 1560（1560字节的数据）

响应

返回 submit.cgi 接收数据的处理结果

#### PUT：传输文件

PUT 方法用来传输文件。就像 FTP 协议的文件上传一样，要求在请

求报文的主体中包含文件内容，然后保存到请求 URI 指定的位置。

![image-20211222210944703](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222210944703.png)

使用 PUT 方法的请求·响应的例子

PUT /example.html HTTP/1.1

请求Host: www.hackr.jp

Content-Type: text/html

Content-Length: 1560（1560 字节的数据）

响应1

响应返回状态码 204 No Content（比如 ：该 html 已存在于服务器上）

1 响应的意思其实是请求执行成功了，但无数据返回。

#### HEAD：获得报文首部

HEAD 方法和 GET 方法一样，只是不返回报文主体部分。用于确认URI 的有效性及资源更新的日期时间等。

和 GET 一样，但不返回报文主体

![image-20211222210932847](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222210932847.png)

HEAD /index.html HTTP/1.1

请求Host: www.hackr.jp

响应

返回index.html有关的响应首部

#### DELETE：删除文件

DELETE 方法用来删除文件，是与 PUT 相反的方法。DELETE 方法按请求 URI 删除指定的资源。

![image-20211222211724675](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222211724675.png)

OPTIONS：询问支持的方法

OPTIONS 方法用来查询针对请求 URI 指定的资源支持的方法。

![image-20211222211731387](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222211731387.png)

TRACE：追踪路径

TRACE 方法是让 Web 服务器端将之前的请求通信环回给客户端的方法。![image-20211222211931155](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222211931155.png)

#### CONNECT：要求用隧道协议连接代理

CONNECT 方法要求在与代理服务器通信时建立隧道，实现用隧道协

议进行 TCP 通信。主要使用 **SSL**（Secure Sockets Layer，安全套接

层）和 **TLS**（Transport Layer Security，传输层安全）协议把通信内容

加 密后经网络隧道传输。

![image-20211222212115557](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222212115557.png)

CONNECT proxy.hackr.jp:8080 HTTP/1.1

请求Host: proxy.hackr.jp

响应

HTTP/1.1 200 OK（之后进入网络隧道）



#### 3.持久连接，管线化

旨在建立 1 次 TCP 连接后进行多次请求和响应的交互

![image-20211222212626311](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222212626311.png)

#### 4.cookie

Cookie 技术通过在请求和响应报文中写入 Cookie 信息来控制客户端的状态。

Cookie 会根据从服务器端发送的响应报文内的一个叫做 Set-Cookie 的

首部字段信息，通知客户端保存 Cookie。当下次客户端再往该服务器

发送请求时，客户端会自动在请求报文中加入 Cookie 值后发送出

去。服务器端发现客户端发送过来的 Cookie 后，会去检查究竟是从哪一

个客户端发来的连接请求，然后对比服务器上的记录，最后得到之前

的状态信息。

没有 Cookie 信息状态下的请求

![image-20211222213845865](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222213845865.png)

##### 1.请求报文（没有 Cookie 信息的状态）

GET /reader/ HTTP/1.1

Host: hackr.jp

*首部字段内没有Cookie的相关信息

##### 2.响应报文（服务器端生成 Cookie 信息）

HTTP/1.1 200 OK

Date: Thu, 12 Jul 2012 07:12:20 GMT

Server: Apache

＜Set-Cookie: id=1342077140226724; path=/; expires=Wed, 10-Oct-12 07:12:20 GMT＞

Content-Type: text/plain; charset=UTF-8

##### 3.第二次请求报文（自动发送保存着的 Cookie 信息）

GET /image/ HTTP/1.1

Host: hackr.jp

Cookie: id=1342077140226724



![image-20211222214130894](C:\Users\zengtian\AppData\Roaming\Typora\typora-user-images\image-20211222214130894.png)

# 3.报文内的HTTP信息:

