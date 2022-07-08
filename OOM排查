# **java.lang.OutOfMemoryError: unable to create new native thread**

 java.lang.OutOfMemoryError: unable to create new native thread是java较为常见的一种异常，通常发生在进程试图创建新的线程时，这种报错存在两种可能原因：

1. 系统内存耗尽，无法为新线程分配内存

   2. 创建线程数超过了操作系统的限制

 

**查看最大线程数**

- 查看当前系统已用的线程或进程数

  pstree -p | wc -l

- 查看当前摸进程的线程数

  pstree -p <pid> |wc -l 

- 查看当前用户的系统最大线程数

ulimit -a   （max user processes）

**修改方案**

1.在/etc/security/limits.conf 修改，只有root生效，普通用户还要修改 /etc/security/limits.d/20-nproc.conf

\* soft nproc 65535  # 打开进程数 

\* hard nproc 65535  # 打开进程数

2.修改/etc/security/limits.d/20-nproc.conf

3.修改系统总限制

查看系统限制方法：

sysctl kernel.pid_max

修改：

/etc/sysctl.conf

参考博客：

https://www.jianshu.com/p/b0df25bae79d

http://3ms.huawei.com/hi/group/2692269/wiki_4877761.html

http://3ms.huawei.com/km/blogs/details/6231377
