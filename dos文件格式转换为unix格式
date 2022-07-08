因为在dos/window下按一次回车键实际上输入的是“回车（CR)”和“换行（LF）”，而Linux/unix下按一次回车键只输入“换行（LF）”，所以文件在每行都会多了一个CR，所以Linux下运行时就会报错找不到命令，所以，解决问题之道，就是把dos文件格式转换为unix格式。

**方法1：使用dos2unix命令转换**

   第一步：安装dos2unix命令，如果已经安装，跳过该步骤

   centos：yum install dos2unix

   ubuntu：sudo apt-get install dos2unix

   第二步：转换格式

   dos2unix /usr/apache-tomcat/bin/restart.sh

   dos2unix: converting file /usr/apache-tomcat/bin/restart.sh to Unix format ...

**方法2：使用notepad++**

   在windows系统下使用notepad++编辑该sh文件，双击文件右下角编码区域选择"转换为UNIX格式"
