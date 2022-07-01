### 1.查询端口是否被占用：netstat -anp|grep xxxx       
### 2.查找文件命令  find / -name "*文件名*"  *通识匹配  find . -name "*ies_menu.js*" 
3.grep 文本搜索  
常用参数：
-R 搜索子文件夹
-v 从结果集中排除某些行
-l 只显示文件名，不显示具体细节
-i 忽略大小写


grep -R "This is a test message" *   查找所有子文件夹，显示文件路径、文件名和细节
grep -Rl "This is a test message" *  显示文件名，不显示文件细节
 grep -R "com.bsp.smsgateway.test.content" *|grep -v Test   先查找包含关键字的结果集，从结果集中排除包含Test的部分

双引号有没有效果是一样的，没有区别


3.在vi中搜索关键字
在非编辑模式下/keyword  向下查找，  ?keyword向上查找  按n键继续查找

4.tail命令中查找关键字命令
tail -100f root.log|grep  website *


5.su命令
su切换用户
su ossadm和 su - ossadm的区别： su ossadm起了一个子shell窗口，有些export的变量会残留遗传到字shell中；su - ossadm 起了一个全新的shell窗口，全无残留
