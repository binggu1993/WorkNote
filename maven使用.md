# maven使用

### 1.maven下载：http://maven.apache.org/download.cgi

### 2.maven安装配置http://3ms.huawei.com/km/blogs/details/6444527

### 2.跳过test maven项目编译

### 3.打印依赖树

mvn -B -DskipTests -s pom.xml dependency:tree -Dverbose > tree.txt

 

### 4.maven打包时跳过测试：

https://blog.csdn.net/thc1987/article/details/42458895

mvn install -DskipTests

 

mvn install -Dmaven.test.skip=true

 

### 5.linux配置maven

http://3ms.huawei.com/km/groups/3042447/blogs/details/5125509

 

### 6.maven依赖策略

https://blog.csdn.net/pansanday/article/details/79554632



### 7.idea配置默认maven

Idea默认配置不包括maven，每次new project maven都需要重新配置，因此需要配置默认的全局maven：

File -> Other Settings -> maven
