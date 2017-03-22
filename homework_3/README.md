# 作业报告
## 1.安装配置Docker
+ 根据讲义上的教程安装docker
![](./docker1.png)
![](./docker2.png)

## 2.查阅相关资料及docker相关文档，介绍docker基本命令(如run,images,network等)，要求至少包含镜像管理，容器管理，网络管理三部分的命令，至少介绍5个不同的命令，尽量完整的介绍命令，包括命令的含义和其用法，例子。

###  docker run : 创建一个新的容器并且运行一个命令
+ 语法： docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
+ option 说明
-a stdin: 指定标准输入输出内容类型，可选 STDIN/STDOUT/STDERR 三项；
-d: 后台运行容器，并返回容器ID；
-i: 以交互模式运行容器，通常与 -t 同时使用；
-t: 为容器重新分配一个伪输入终端，通常与 -i 同时使用；
--name="nginx-lb": 为容器指定一个名称；
--dns 8.8.8.8: 指定容器使用的DNS服务器，默认和宿主一致；
--dns-search example.com: 指定容器DNS搜索域名，默认和宿主一致；
-h "mars": 指定容器的hostname；
-e username="ritchie": 设置环境变量；
--env-file=[]: 从指定文件读入环境变量；
--cpuset="0-2" or --cpuset="0,1,2": 绑定容器到指定CPU运行；
-m :设置容器使用内存最大值；
--net="bridge": 指定容器的网络连接类型，支持 bridge/host/none/container: 四种类型；
--link=[]: 添加链接到另一个容器；
--expose=[]: 开放一个端口或一组端口；
+ 实例
docker run hello-world

### docker images: 列出本地镜像
+ 语法：docker images [OPTIONS] [REPOSITORY[:TAG]]
+ option 说明
-a :列出本地所有的镜像（含中间映像层，默认情况下，过滤掉中间映像层）；
--digests :显示镜像的摘要信息；
-f :显示满足条件的镜像；
--format :指定返回值的模板文件；
--no-trunc :显示完整的镜像信息；
-q :只显示镜像ID。
+ 实例
![](./docker-ubuntu.png)

### docker pull : 从镜像仓库中拉取或者更新指定镜像
+ 语法: docker pull [OPTIONS] NAME[:TAG|@DIGEST]
+ option　说明
-a :拉取所有 tagged 镜像
--disable-content-trust :忽略镜像的校验,默认开启
+ 实例
docker pull java

### docker start :启动一个或多少已经被停止的容器
### docker stop :停止一个运行中的容器
### docker restart :重启容器
+ 语法
docker start [OPTIONS] CONTAINER [CONTAINER...]
docker stop [OPTIONS] CONTAINER [CONTAINER...]
docker restart [OPTIONS] CONTAINER [CONTAINER...]
+ 实例
docker start myrunoob
docker stop myrunoob
docker restart myrunoob

### docker save : 将指定镜像保存成 tar 归档文件。
+ 语法：docker save [OPTIONS] IMAGE [IMAGE...]
+ option 说明
-o :输出到的文件
+ 实例
docker save -o my_ubuntu.tar ubnutu