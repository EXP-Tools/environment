## 在Windows下配置JDK环境变量

------

### 1.　找到环境变量设置入口

- 低于win7的系统版本：
<br/>　　在桌面右击【计算机/我的电脑】 -&gt; 【属性】 -&gt; 【高级系统设置】 -&gt; 【高级】 -&gt; 【环境变量】
<br/>　
- 高于win8的系统版本：
<br/>　　在开始菜单右击【此电脑/这台电脑】 -&gt; 【更多】 -&gt; 【属性】 -&gt; 【高级系统设置】 -&gt; 【环境变量】


### 2.　设置环境变量

- 2.1.　在【系统变量】区域点击【新建】按钮
- 2.2.　在【变量名】输入【JAVA_HOME】
- 2.3.　在【变量值】输入【所安装的JDK路径】，如输入【C:\Program Files\Java\jdk1.7.0_72】
<br/>　　　　但是有些程序不能识别路径中的空格，这里更建议使用特殊字符代替：【C:\Progra~1\Java\jdk1.7.0_72】
- 2.4.　点击【确定】按钮
- 2.5.　在【系统变量】区域点击【新建】按钮
- 2.6.　在【变量名】输入【CLASSPATH】
- 2.7.　在【变量值】输入【.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;】（注意不要遗漏点号和分号）
- 2.8.　点击【确定】按钮
- 2.9.　在【系统变量】区域找到名为【Path】的变量名称，选中后点击【编辑】按钮
<br/>　　　　低于win7的系统版本：在开头添加【%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;】
<br/>　　　　高于win8的系统版本：在末尾添加两行【%JAVA_HOME%\bin】和【%JAVA_HOME%\jre\bin】


### 3.　检查环境变量

- 3.1.　【win+R】打开&quot;快速运行界面&quot;
- 3.2.　输入【cmd】并点击【确认】按钮打开&quot;DOS界面&quot;
- 3.3.　输入 `java –version` ，若显示Java版本信息则配置成功

> 注：
<br/>　若同时安装了多个版本的JDK，但是发现无论怎么修改环境变量【%JAVA_HOME%】
<br/>　都无法切换版本（即 `java –version` 得到的版本号总是相同的）
<br/>　这时可以在DOS界面输入 `where java` 命令查看实际使用的jdk路径
<br/>　会发现指向了【C:\Windows\System32\java.exe】
<br/>　切到【C:\Windows\System32】目录后会发现有3个文件：java.exe、javaw.exe、javaws.exe
<br/>　这是安装某个版本的JDK时自动复制的，他们的优先级比环境变量高，删除即可

------

## 版权声明

　[![Copyright (C) 2016-2018 By EXP](https://img.shields.io/badge/Copyright%20(C)-2006~2018%20By%20EXP-blue.svg)](http://exp-blog.com)　[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

- Site: [http://exp-blog.com](http://exp-blog.com) 
- Mail: <a href="mailto:289065406@qq.com?subject=[EXP's Github]%20Your%20Question%20（请写下您的疑问）&amp;body=What%20can%20I%20help%20you?%20（需要我提供什么帮助吗？）">289065406@qq.com</a>


------