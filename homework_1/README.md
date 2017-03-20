### 1.阅读Mesos论文《Mesos: A Platform for Fine-Grained Resource Sharing in the Data Center》，并了解数据中心操作系统的概念

+ 提出Mesos论文中的内容
Mesos是支持在多种计算集群框架（frameworks）间共享服务器集群的平台，利用HADOOP，MPI。提高了集群资源占用率，避免了每 种框架的数据重复。Mesos能够镜像细粒度的资源共享，通过轮流的读取磁盘数据是的frameworks能从本地获取数据。为了满足复杂的资源调度方 法，Mesos引入了称为资源提供的（resource offer）的2层资源调度机制。Mesos决定多少资源分配给frameworks，frameworks决定接受多少资源和决定哪个任务使用多少资源。
Mesos，一个薄的资源共享层，通过对集群框架提供共有的访问集群资源的接口，使得在多样化的集群计算框架中实现细粒度共享成为可能
数据中心操作系统主要做到了将数据中心的大规模服务器集群视为了一个计算机，对其中的CPU、内存、储存装置以及其他运算资源，全部加以虚拟化，并进行管理。同时，如Spark这类并行计算框架或Hadoop这类分布存储框架等应用都可以运行于其上。
![](https://github.com/areslan1122/os-lab/blob/master/homework_1/picture01.png）