# JVM，JRE,JDK的区别
>当前版本：v1.1  
>维护人：Jhin  
>维护时间：2018年05月29日

## JVM
Java虚拟机（英语：Java Virtual Machine，缩写为JVM），一种能够运行Java bytecode的虚拟机，以堆栈结构机器来进行实做。最早由太阳微系统所研发并实现第一个实现版本，是Java平台的一部分，能够运行以Java语言写作的软件程序。

Java虚拟机有自己完善的硬体架构，如处理器、堆栈、寄存器等，还具有相应的指令系统。JVM屏蔽了与具体操作系统平台相关的信息，使得Java程序只需生成在Java虚拟机上运行的目标代码（字节码），就可以在多种平台上不加修改地运行。通过对中央处理器（CPU）所执行的软件实现，实现能执行编译过的Java程序码（Applet与应用程序）。

作为一种编程语言的虚拟机，实际上不只是专用于Java语言，只要生成的编译文件匹配JVM对载入编译文件格式要求，任何语言都可以由JVM编译运行。此外，除了甲骨文，也有其他开源或闭源的实现。
#### 语言实现
由于JVM并不是专为Java所实现的运行时，实际上只要有其他编程语言的编译器能生成正确Java bytecode文件，则这个语言也能实现在JVM上运行。

以下为原生就在JVM上实现运行的语言：
+ Java
+ BBj
+ BeanShell
+ Ceylon
+ Clojure
+ Fantom
+ Kotlin
+ Groovy
+ MIDletPascal
+ Scala
+ Xtend

## JRE
Java运行环境（Java Runtime Environment，简称JRE）是一个软件，由太阳微系统所研发，JRE可以让电脑系统运行Java应用程序（Java Application）。

JRE的内部有一个Java虚拟机（Java Virtual Machine，JVM）以及一些标准的类别函数库（Class Library）。

<table>
  <tr>
    <td colspan="2" align="center">Java</td>
  </tr>
  <tr>
    <td align="right">Java平台</td>
    <td>Java(Java版本历史·Java 5)、JVM(Java字节码)、Java ME、Java SE、Java EE、Java Card、Android SDK</td>
  </tr>
  <tr>
    <td align="right">Oracle技术</td>
    <td>Squawk、JDK、OpenJDK、Java虚拟机、JavaFX、Maxine VM</td>
  </tr>
  <tr>
    <td align="right">平台技术</td>
    <td>Applets、Servlets、MIDlet、JSP、Web Start(JNLP)</td>
  </tr>
  <tr>
    <td align="right">主要的第三方技术</td>
    <td>Blackdown、Eclipse、GNU Classpath、GWT、Harmony、Hibernate、IcedTea、Jazelle、Spring、Struts、TopLink、WildFly</td>
  </tr>
  <tr>
    <td align="right">历 史</td>
    <td>Java版本历史、JCP、太阳微系统、自由Java实现</td>
  </tr>
  <tr>
    <td align="right">主要JVM语言</td>
    <td>BeanShell、Clojure、Groovy、Oxygene、JRuby、Jython、Kotlin、Processing、Rhino、Scala、Tcl/Java</td>
  </tr>
  <tr>
    <td align="right">会 议</td>
    <td>JavaOne、Devoxx</td>
  </tr>
</table>

## JDK
Java Development Kit（JDK）是太阳微系统针对Java开发人员发布的免费软件开发工具包（SDK，Software development kit）。自从Java推出以来，JDK已经成为使用最广泛的Java SDK。由于JDK的一部分特性采用商业许可证，而非开源[1]。因此，2006年太阳微系统宣布将发布基于GPL的开源JDK，使JDK成为自由软件。在去掉了少量闭源特性之后，太阳微系统最终促成了GPL的OpenJDK的发布。

#### 用途
作为Java语言的SDK，普通用户并不需要安装JDK来运行Java程序，而只需要安装JRE（Java Runtime Environment）。而程序开发者必须安装JDK来编译、调试程序。

#### 包含组件
JDK包含了一批用于Java开发的组件，其中包括：
+ javac：编译器，将后缀名为.java的源代码编译成后缀名为“.class”的字节码
+ java：运行工具，运行.class的字节码
+ jar：打包工具，将相关的类文件打包成一个文件
+ javadoc：文档生成器，从源码注释中提取文档，注释需匹配规范
+ jdb debugger：调试工具
+ jps：显示当前java程序运行的进程状态
+ javap：反编译程序
+ appletviewer：运行和调试applet程序的工具，不需要使用浏览器
+ javah：从Java类生成C头文件和C源文件。这些文件提供了连接胶合，使Java和C代码可进行交互。
+ javaws：运行JNLP程序
+ extcheck：一个检测jar包冲突的工具
+ apt：注释处理工具
+ jhat：java堆分析工具
+ jstack：栈跟踪程序
+ jstat：JVM检测统计工具
+ jstatd：jstat守护进程
+ jinfo：获取正在运行或崩溃的java程序配置信息
+ jmap：获取java进程内存映射信息
+ idlj：IDL-to-Java编译器。将IDL语言转化为java文件[4]
+ policytool：一个GUI的策略文件创建和管理工具
+ jrunscript：命令行脚本运行

JDK中还包括完整的JRE（Java Runtime Environment），Java运行环境，也被称为private runtime。包括了用于产品环境的各种库类，如基础类库rt.jar，以及给开发人员使用的补充库，如国际化与本地化的类库、IDL库等等。

JDK中还包括各种样例程序，用以展示Java API中的各部分。
## 章节引用
+ [Java虚拟机-维基百科](https://zh.wikipedia.org/wiki/Java%E8%99%9A%E6%8B%9F%E6%9C%BA)
+ [JRE-维基百科](https://zh.wikipedia.org/wiki/JRE)
+ [JDK-维基百科](https://zh.wikipedia.org/wiki/JDK)

## 历史版本
| 版本号 | 维护人 |维护时间 |维护内容|
| :- | :- | :-| :- |
| v1.0 | [Jhin](https://blog.link-lin.cn) |2018-05-21|创建了本词条|
| v1.1 | [Jhin](https://blog.link-lin.cn) |2018-05-29|修改了表格的格式|
