# 解决下载安装配置java的困难

- [「下載java jdk」](https://www.oracle.com/technetwork/java/javase/downloads) ，
有 jdk 20\17\11\8 和 jre 8

## win
为了避免oracle设置的变量影响，需要先手动删除Path中的下列变量：

    C:\Program Files (x86)\Common Files\Oracle\Java\javapath
    
可以在高级系统设置 - 环境变量 - 系统变量 - Path 中删除

---

修改全局变量
* setx 代表设置全局变量
* /m 代表设置**系统**全局变量，默认是用户全局变量

使用 **管理员powershell** 执行下面的脚本
> 如使用 cmd，`$env:Path` 需要替换成 `%Path%`，否则会造成系统变量永久性丢失，后果很严重。
```bat
setx JAVA_HOME "C:\Program Files\Java\jdk-17" /m
setx CLASSPATH ".;%JAVA_HOME%\lib" /m
setx Path "%JAVA_HOME%\bin;$env:Path" /m
```

---

如果要修改不同版本的java，则设置javahome变量

```bat
setx JAVA_HOME "C:\Program Files\Java\jdk-20" /m
```

重新开启一个命令行并测试java

    java -version

 ## linux
1. [先安装好国内源](https://blog.csdn.net/u012308586/article/details/102953882)
2. 在命令行输入`java -version` 会有提示
3. 安装第一个(default)
  
  ## 驗證

输入`java`或者`javac`或者`java -version`确认是否已经成功安装

---
# 解决下载安装配置gcc的困難

- [mingw下載站](http://www.mingw.org/)
- ~~fan qiang~~
1. 安裝所有`mingw32-gcc-g++`以及`mingw32-gdb`开头的东西
2. 运行 `sysdm.cpl`直接打开环境变量
3. 编辑`Path`
4. 点击“新建”，并输入`C:\MinGW\bin`（如果自行更改了MinGW的安装路径请自行对照修改此处的路径）
5. 全部点“确定”关闭所有对话框。
  ## 驗證
控制台输入`gcc -v`确认是否已经成功安装
---
# Android Stdio
[android stdio 下载](https://developer.android.com/training/basics/firstapp/creating-project)
