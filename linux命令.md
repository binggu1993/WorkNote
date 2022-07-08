# linux学习

### 1.查询端口是否被占用：netstat -anp|grep xxxx       

### 2.查找文件命令  find / -name "*文件名*"  *通识匹配  find . -name "*ies_menu.js*" 

### 3.grep 文本搜索  

常用参数：

- -R 搜索子文件夹
- -v 从结果集中排除某些行
- -l 只显示文件名，不显示具体细节
- -i 忽略大小写

grep -R "This is a test message" *   查找所有子文件夹，显示文件路径、文件名和细节
grep -Rl "This is a test message" *  显示文件名，不显示文件细节
 grep -R "com.bsp.smsgateway.test.content" *|grep -v Test   先查找包含关键字的结果集，从结果集中排除包含Test的部分

双引号有没有效果是一样的，没有区别

### 3.在vi中搜索关键字

在非编辑模式下/keyword  向下查找，  ?keyword向上查找  按n键继续查找

### 4.tail命令中查找关键字命令

tail -100f root.log|grep  website *

### 5.su命令

su切换用户
su ossadm和 su - ossadm的区别： su ossadm起了一个子shell窗口，有些export的变量会残留遗传到字shell中；su - ossadm 起了一个全新的shell窗口，全无残留

### 6.export命令   export定义的变量 本窗口和由本窗口派生出去的子窗口可见，即可继承

### 7 chmod修改文件权限  

如上图，新建的文件一般读写权限是-rw-r--r--，分别是用户权限、用户组权限、用户组以外的用户权限  r-读权限，w-写权限，x-执行权限，rwx分别是421，加起来就是7，所以chmod777就是最高权限，上图新建的文件该用户权限为644，如果想要执行权限至少应该改为 744

### 8.设置环境变量：$PATH 获取当前PATH的值，修改环境变量  PATH=/test/a:$PATH

编写设置环境变量脚本，让系统可识别该命令。
比如：设置环境变量脚本：

Set_env.sh内容：
PATH=/test/a:$PATH

aaa内容：

```shell
aa=11
echo $aa
echo this is my world
```


aaa是一个可执行文件，但是如果不执行环境变量的话只有在该目录下执行  ./aaa 或者sh  aaa才能输出东西。
先执行. Set_env.sh文件，修改了PATH后，在任何路径下都可直接执行aaa文件了

### 9  ./set_env.sh 和 . set_env.sh的区别

./是在子窗口中执行，. 是在本窗口执行
8 在本窗口执行环境变量才能生效，./set_env.sh在子窗口中执行，环境变量也只是子窗口中生效，所以aaa仍然不能执行
su - ossadm
. /opt/oss/manager/bin/engr_profile.sh
ipmc_adm -cmd restartapp -app HomePageNoticeWebsite

### 10。chown ossadm: aaa

修改用户或者用户组

### 11.echo输出，$aaa取变量的值    su创建子窗口或者全新窗口，exit退出

### 12.查看进程工作路径命令：pwdx  pid

### 13 查看进程树  pstree  pid

### 14 linux下如何抓取本机进程之间的通信报文  tcpdump -i any port {port} -w dump.cap

### 15 linux下如何查看某个进程内的环境变量？

  cat /proc/$pid/environ | tr '\0' '\n'

### 16 linux下可以通过什么命令查询进程的句柄信息？ 

您的答案:

 * lsof -p pid 

 * ls -l /proc/$pid/fd/

### 17 比较区别  diff  文件1 文件2

### 18.根据内容查询文件：find ./ -name "app_define.json"|xargs grep -i "privilege"

### 19.关键字计数

需要对log文件某个关键字计数：
zgrep "Sending smpp34 message" root_20200610164620872.log|wc -l

需要对log文件两个关键字统计：

zgrep "Begin to send a message" root_20200610164620872.log |grep "2020-06-10 13"|wc -l




	20. netstat -nltp | grep 
	查看进程号占用端口

### 21.杀掉所有进程：ps -ef | grep HomePageNoticeService | grep -v grep | awk '{print $2}' | xargs kill -9
