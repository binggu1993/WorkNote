# java常见问题定位

主要包括内存泄漏、句柄数泄漏、cpu占用率高、线程死锁等问题

## cpu占用分析

**查看cpu占用**

- 分析某个进程 cpu占用情况

​     top -p 2887

- 分析某个进程所有线程 cpu占用情况

​     top -H -p 5887

**cpu占用率分析**

Kill -3 pid 

堆栈信息打印在catalina.out下

```
ps -ef|grep xxx
top -n 1 -b -p pid >cpu_monitor.txt 
top -H -n 1 -b -p pid >thread_monitor.txt
```

Top 按一下C，按照cpu占用排序，

**报错信息**

Too many open files

```java
2019-02-25 13:58:50,078 ERROR [http-nio-auto-1-Acceptor-0][ROOT][org.apache.tomcat.util.net.NioEndpoint$Acceptor 854] Socket accept failed
java.io.IOException: Too many open files
	at sun.nio.ch.ServerSocketChannelImpl.accept0(Native Method)
	at sun.nio.ch.ServerSocketChannelImpl.accept(ServerSocketChannelImpl.java:422)
	at sun.nio.ch.ServerSocketChannelImpl.accept(ServerSocketChannelImpl.java:250)
	at org.apache.tomcat.util.net.NioEndpoint$Acceptor.run(NioEndpoint.java:827)
	at java.lang.Thread.run(Thread.java:748)

```

## heapdump分析

**打印heapdump（用户进程用户保持一致）**

./jmap -dump:live,format=b,file=xxheap.hprof 25342

**使用jvisualvm分析堆dump**

Cmd --> jvisualvm

类过滤器中输入类名，过滤类有两个实例：

[java程序性能分析之thread dump和heap dump](https://www.cnblogs.com/toSeeMyDream/p/7151635.html)



## 使用jvisualvm的jstatd方式远程监控Java程序

[使用jvisualvm的jstatd方式远程监控Java程序](https://www.cnblogs.com/liugh/p/7620336.html)

