# Unix
>当前版本：v1.0  
>维护人：Jhin  
>维护时间：2017年11月10日

`UNIX`，一种计算机操作系统，具有多任务、多用户的特征。于1969年，在美国AT&T公司的贝尔实验室开发了UNIX。

![](/wiki/image/1200px-Unix_history-simple.png "Unix发展史")
## 简介

UNIX操作系统（尤尼斯），是一个强大的多用户、多任务操作系统，支持多种处理器架构，按照操作系统的分类，属于分时操作系统，最早由KenThompson、Dennis Ritchie和Douglas McIlroy于1969年在AT&T的贝尔实验室开发。目前它的商标权由国际开放标准组织所拥有，只有匹配单一UNIX规范的UNIX系统才能使用UNIX这个名称，否则只能称为类UNIX（UNIX-like）。

Unix的前身为1964年开始的Multics，贝尔实验室 （Bell Labs）1965年时，加入一项由通用电气（General Electric）和麻省理工学院（MIT）合作 的计划；该计划要创建一套多用户、多任务、多层次（multi－user、multi－processor、multi－level）的MULTICS操作系统。贝尔实验室参与了这个操作系统的研发，但因为开发速度太慢，1969年贝尔实验室决定退出这个计划。贝尔实验室的工程师，肯·汤普逊和丹尼斯·里奇，在此时自行开发了Unix。

此后的10年，Unix在学术机构和大型企业中得到了广泛的应用，当时的UNIX拥有者AT&T公司以低廉甚至免费的许可将Unix源码授权给学术机构做研究或教学之用，许多机构在此源码基础上加以扩充和改进，形成了所谓的“Unix变种”，这些变种反过来也促进了Unix的发展，其中最著名的变种之一是由加州大学柏克莱分校开发的柏克莱软件包(BSD)产品。

后来AT&T意识到了Unix的商业价值，不再将Unix源码授权给学术机构，并对之前的Unix及其变种声明了版权权利。BSD在Unix的历史发展中具有相当大的影响力，被很多商业厂家采用，成为很多商用Unix的基础。其不断增大的影响力终于引起了AT&T的关注，于是开始了一场持久的版权官司，这场官司一直打到AT&T将自己的Unix系统实验室卖掉，新接手的Novell采取了一种比较开明的做法，允许柏克莱分校自由发布自己的Unix变种，但是前提是必须将来自于AT&T的代码完全删除，于是诞生了4.4 BSD Lite版，由于这个版本不存在法律问题，4.4 BSD Lite成为了现代柏克莱软件包的基础版本。尽管后来，非商业版的Unix系统又经过了很多演变，但其中有不少最终都是创建在BSD版本上（Linux、Minix等系统除外）。所以从这个角度上，4.4 BSD 又是所有自由版本Unix的基础，它们和System V及Linux等共同构成Unix操作系统这片璀璨的星空。

BSD使用主版本加次版本的方法标识，如4.2、4.3BSD，在原始版本的基础上还有派生版本，这些版本通常有自己的名字，如4.3BSD-Net/1，4.3BSD-Net/2等。BSD在发展中也逐渐派生出3个主要的分支：FreeBSD、OpenBSD和NetBSD。

此后的几十年中，Unix仍在不断变化，其版权所有者不断变更，授权者的数量也在增加。Unix的版权曾经为AT&T所有，之后Novell拥有获取了Unix，再之后Novell又将版权出售给了圣克鲁兹作业，但不包括知识产权和专利权（这一事实双方尚存在争议）。有很多大公司在获取了Unix的授权之后，开发了自己的Unix产品，比如IBM的AIX、HP的HP-UX、SCO的Openserver、SUN的Solaris（被Oracle收购）和SGI的IRIX。

Unix因为其安全可靠，高效强大的特点在服务器领域得到了广泛的应用。直到GNU/Linux流行开始前，Unix也是科学计算、大型机、超级计算机等所用操作系统的主流。现在其仍然被应用于一些对稳定性要求极高的数据中心之上。
## 历史
+ 初创期

Unix最初受到Multics计划的启发。Multics是由麻省理工学院、通用电气和AT&T底下的贝尔实验室合作进行的操作系统项目，被设计运行在GE-645大型主机上。但是由于整个目标过于庞大，糅合了太多的特性，Multics虽然发布了一些产品，但是性能都很低，AT&T最终撤出了投入Multics项目的资源，退出这项合作计划。

贝尔实验室最初参与Multics计划的部门为计算器技术研发部门（Computing Techniques Research Department），部门主管为道格拉斯·麦克罗伊，其下的工程师，原有丹尼斯·里奇、布莱恩·柯林汉、道格拉斯·麦克罗伊、麦克·列斯克（Mike Lesk）与乔伊·欧桑纳（Joe Ossanna）等人，为了Multics计划，他们又召募了肯·汤普逊加入其中。肯·汤普逊进入Multics计划不久，计划就中止了，但因为机器仍然保留在贝尔实验室，他继续在GE-645上开发软件。肯·汤普逊在GE-645上，写出了一个仿真器，可以让一个文件系统与内存分页机制运作起来。他同时也写了一个程序语言Bon，编写了一个太空旅行游戏。经过实际运行后，他发现游戏速度很慢而且耗费昂贵，每次运行会花费75美元。在GE-645被搬走后，肯·汤普逊在实验室中寻找没人使用的机器，找到了几台PDP-7。丹尼斯·里奇的帮助下，汤普逊用PDP-7的汇编语言重写了这个游戏，并使其在DEC PDP-7上运行起来。这次经历加上Multics项目的经验，促使汤普逊开始在DEC PDP-7上研究如何开发操作系统。

1969年，肯·汤普逊提议在PDP-7上开发一个新的阶层式操作系统的计划。Multics的原有成员，加上Rudd Canady，都投入这个计划。肯·汤普逊发现要编写驱动程序来驱动文件系统，进行测试，并不容易，于是开发了一个壳层（shell）与一些驱动程序，做出一个操作系统的雏形。在团队合作下，Multics的许多功能都被采纳，重新实现，最终做出了一个分时多任务操作系统，成为第一版UNIX。因为Multics来自“MULTiplexed Information and Computing System”的缩写，在1970年，那部PDP-7却只能支持两个用户，彼得·纽曼（Peter G. Neumann）戏称他们的系统其实是:“UNiplexed Information and Computing System”，缩写为“UNICS”。于是这个项目被称为UnICS（Uniplexed Information and Computing System）。

因为PDP-7的性能不佳，肯·汤普逊与丹尼斯·里奇决定把第一版UNIX移植到PDP-11/20的机器上，开发第二版UNIX。在性能提升后，真正可以提供多人同时使用，布莱恩·柯林汉提议将它的名称改为UNIX。

第一版UNIX是用PDP-7汇编语言编写的，一些应用是由叫做B语言的解释型语言和汇编语言混合编写的。在进行系统编程时不够强大，所以汤普逊和里奇对其进行了改造，并于1971年共同发明了C语言。1973年汤普逊和里奇用C语言重写了Unix，形成第三版UNIX。在当时，为了实现最高效率，系统程序都是由汇编语言编写，所以汤普逊和里奇此举是极具大胆创新和革命意义的。用C语言编写的Unix代码简洁紧凑、易移植、易读、易修改，为此后Unix的发展奠定了坚实基础。
+ 发展期

1974年，汤普逊和里奇合作在ACM通信上发表了一篇关于UNIX的文章，这是UNIX第一次出现在贝尔实验室以外。此后UNIX被政府机关，研究机构，企业和大学注意到，并逐渐流行开来。

1975年，UNIX发布了4、5、6三个版本。1978年，已经有大约600台计算机在运行UNIX。1979年，版本7发布，这是最后一个广泛发布的研究型UNIX版本。20世纪80年代相继发布的8、9、10版本只授权给了少数大学。此后这个方向上的研究导致了九号计划的出现，这是一个新的分布式操作系统。

1982年，AT&T基于版本7开发了UNIX System Ⅲ的第一个版本，这是一个商业版本仅供出售。为了解决混乱的UNIX版本情况，AT&T综合了其他大学和公司开发的各种UNIX，开发了UNIX System V Release 1。

这个新的UNIX商业发布版本不再包含源代码，所以加州大学柏克莱分校继续开发BSD UNIX，作为UNIX System III和V的替代选择。BSD对UNIX最重要的贡献之一是TCP/IP。BSD有8个主要的发行版中包含了TCP/IP：4.1c、4.2、4.3、4.3-Tahoe、4.3-Reno、Net2、4.4以及4.4-lite。这些发布版中的TCP/IP代码几乎是现在所有系统中TCP/IP实现的前辈，包括AT&T System V UNIX和Microsoft Windows。

其他一些公司也开始为其自己的小型机或工作站提供商业版本的UNIX系统，有些选择System V作为基础版本，有些则选择了BSD。BSD的一名主要开发者，比尔·乔伊，在BSD基础上开发了SunOS，并最终创办了昇陽公司。

1991年，一群BSD开发者（Donn Seeley、Mike Karels、Bill Jolitz和Trent Hein）离开了加州大学，创办了Berkeley Software Design, Inc (BSDI)。BSDI是第一家在便宜常见的Intel平台上提供全功能商业BSD UNIX的厂商。后来Bill Jolitz离开了BSDI，开始了386BSD的工作。386BSD被认为是FreeBSD、OpenBSD和NetBSD、DragonFlyBSD的先辈。

AT&T继续为UNIX System V增加了文件锁定，系统管理，作业控制，流和远程文件系统。1987到1989年，AT&T决定将Xenix（微软开发的一个x86-pc上的UNIX版本），BSD，SunOS和System V融合为System V Release 4（SVR4）。这个新发布版将多种特性融为一体，结束了混乱的竞争局面。

1993年以后，大多数商业UNIX发行商都基于SVR4开发自己的UNIX变体了。
## 现况

UNIX System V Release 4发布后不久，AT&T就将其所有UNIX权利出售给了Novell。Novell期望以此来对抗微软的Windows NT，但其核心市场受到了严重伤害，1993年Novell将SVR4的商标权利出售给了X/OPEN公司，后者成为定义UNIX标准的机构。1996年，X/OPEN和OSF/1合并，创建了国际开放标准组织，由它公布的“单一UNIX规范”定义着具有什么特征的操作系统可以冠上UNIX之名，相对地，不匹配这些标准但与Unix有类似性的操作系统只能称为“类Unix”(unix-like)。

UNIX代码著作权则由Novell售给圣克鲁兹作业，2001年这家公司的商标与UNIX产品和业务都出售给了Caldera Systems，交易完成后，Caldera又被重命名为SCO Group。
## 1127部门的解散

根据一项 报导 指出，当年负责研发UNIX与后续维护工作的贝尔实验室1127部门已于2005年8月正式宣告解散。肯·汤普逊已退休，现居加州；丹尼斯·里奇调到别的部门；而Douglas McIlroy则在达特茅斯学院担任教授。
## 附录：Unix进化时间表
![](/wiki/image/Unix-history.svg)
## 章节来源
+ [Unix--维基百科](https://zh.wikipedia.org/wiki/UNIX)

## 历史版本

| 版本号 | 维护人 |维护时间 |维护内容|
| :- | :- | :-| :- |
| v1.0 | [Jhin](http://blog.link-lin.cn) |2017-11-10|创建了本词条|
