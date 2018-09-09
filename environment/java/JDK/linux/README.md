linux同时安装64和86位jdk

1、创建JDK目录
   mkdir /usr/java/x64
   mkdir /usr/java/x86

2、上传JDK安装包
   /usr/java/x64/jdk-6u45-linux-x64.bin 
   /usr/java/x86/jdk-6u45-linux-i586.bin

3、授权执行
   chmod u+x jdk-6u45-linux-x64.bin 
   chmod u+x jdk-6u45-linux-i586.bin

4、安装
   ./jdk-6u45-linux-x64.bin 
   ./jdk-6u45-linux-i586.bin

5、设置系统环境变量
   vi /etc/profile

   末尾添加
   export JAVA_HOME=/usr/java/x64/jdk1.6.0_45
   #export JAVA_HOME=/usr/java/x86/jdk1.6.0_45
   export CLASSPATH=.:${JAVA_HOME}/lib:${JAVA_HOME}/jre/lib  
   export PATH=${JAVA_HOME}/bin:$PATH

6、设置软连接
   ln -s /usr/java/x64/jdk1.6.0_45/bin/java  /usr/bin/java
   ln -s /usr/java/x64/jdk1.6.0_45/bin/javac  /usr/bin/javac
   ln -s /usr/java/x86/jdk1.6.0_45/bin/java  /usr/bin/java86
   ln -s /usr/java/x86/jdk1.6.0_45/bin/javac  /usr/bin/javac86

7、查看版本
   java -version
   java86 -version
