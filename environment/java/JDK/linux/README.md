## 在Linux下同时安装64和86位JDK步骤

------

### 1.　创建JDK目录
```
mkdir /usr/java/x64
mkdir /usr/java/x86
```


### 2.　通过命令`rz`或`ftp`上传JDK安装包
> /usr/java/x64/jdk-6u45-linux-x64.bin  <br/>
> /usr/java/x86/jdk-6u45-linux-i586.bin


### 3.　授权执行
```
chmod u+x jdk-6u45-linux-x64.bin 
chmod u+x jdk-6u45-linux-i586.bin
```


### 4.　安装
```
./jdk-6u45-linux-x64.bin 
./jdk-6u45-linux-i586.bin
```


### 5.　通过命令`vi /etc/profile`设置系统环境变量

> 对于非 `*.bin` 格式的绿色解压包，直接从这一步开始执行即可

```
# 在末尾添加
export JAVA_HOME=/usr/java/x64/jdk1.6.0_45
export CLASSPATH=.:${JAVA_HOME}/lib:${JAVA_HOME}/jre/lib 
export PATH=${JAVA_HOME}/bin:$PATH 

export JAVA_HOME_X86=/usr/java/x86/jdk1.6.0_45
export CLASSPATH=.:${JAVA_HOME_X86}/lib:${JAVA_HOME_X86}/jre/lib 
export PATH=${JAVA_HOME_X86}/bin:$PATH
```


### 6.　设置软连接
```
ln -s /usr/java/x64/jdk1.6.0_45/bin/java  /usr/bin/java
ln -s /usr/java/x64/jdk1.6.0_45/bin/javac  /usr/bin/javac
ln -s /usr/java/x86/jdk1.6.0_45/bin/java  /usr/bin/java86
ln -s /usr/java/x86/jdk1.6.0_45/bin/javac  /usr/bin/javac86
```


### 7.　查看版本
```
java -version
java86 -version
```


------

## 版权声明

　[![Copyright (C) EXP,2016](https://img.shields.io/badge/Copyright%20(C)-EXP%202016-blue.svg)](http://exp-blog.com)　[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

- Site: [http://exp-blog.com](http://exp-blog.com) 
- Mail: <a href="mailto:289065406@qq.com?subject=[EXP's Github]%20Your%20Question%20（请写下您的疑问）&amp;body=What%20can%20I%20help%20you?%20（需要我提供什么帮助吗？）">289065406@qq.com</a>


------