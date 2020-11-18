# springsnail

## 项目功能描述
* 是一个简单的负载均衡服务器的实现
* 配置见config.xml文件
* 将本地主机作为一个中转站，即负载均衡服务器，将客户端的连接转发给比较空闲的服务器
	
## 各个文件的内容与作用说明

### config.xml: 配置文件，指明服务器本身的地址及它所要链接的ip

### fdwrapper.h fdwrapper.cpp: 操作文件描述fd的各种函数，具体会在源码解析中放出。

### log.h log.cpp: 日志函数，在程序运行过程中打印各种信息到文件和控制台中。

### mgr.h mgr.cpp: 处理网络链接和负载均衡的框架

### conn.h conn.cpp: 客户端类与函数

### processcool.h: 进程池，是整个项目的动力。

### main.cpp: 主函数，处理服务器的主要逻辑

## 使用步骤
1. 项目源码下载，`git clone https://github.com/XMJYever/springsnail.git`
2. 编译整个项目，`make`
3. 利用nslookup命令来解析想连接的服务器，例如百度，`nslookup www.baidu.com`
4. 将得到的ip地址填入config.xml文件中，修改<logical_host>下的<name>中的名称即可,保存并退出
5. 执行服务器程序, `./springsnail -f config.xml`

