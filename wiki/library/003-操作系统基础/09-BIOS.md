# BIOS
>当前版本：v1.0  
>维护人：Jhin  
>维护时间：2017年11月10日


`BIOS`是英文”Basic Input Output System”的缩略词，直译过来后中文名称就是”基本输入输出系统”。在IBM PC兼容系统上，是一种业界标准的固件接口。BIOS这个字眼是在1975年第一次由CP/M操作系统中出现。  BIOS是个人电脑启动时加载的第一个软件。

其实，它是一组固化到计算机内主板上一个ROM芯片上的程序，它保存着计算机最重要的基本输入输出的程序、开机后自检程序和系统自启动程序，它可从CMOS中读写系统设置的具体信息。 其主要功能是为计算机提供最底层的、最直接的硬件设置和控制。此外，BIOS还向作业系统提供一些系统参数。系统硬件的变化是由BIOS隐藏，程序使用BIOS功能而不是直接控制硬件。现代作业系统会忽略BIOS提供的抽象层并直接控制硬件组件。

当今，此系统已成为一些病毒木马的目标。一旦此系统被破坏，其后果不堪设想。
## 历史
术语BIOS（基本输入/输出系统）最初是由Gary Kildall 发明，第一次出现是在1975年的CP/M操作系统。 描述CP / M的机器特定部分启动时，接口直接加载的硬件。（一个CP/M机器的ROM中通常只有一个简单的引导加载程序）。

多种版本的MS-DOS，PC-DOS或DR-DOS含有一个被称为”IO.SYS”，“IBMBIO.COM”，“IBMBIO.SYS”或“ DRBIOS.SYS”等名字的文件；这个文件就是所谓的“DOSBIOS”（也称为“DOS I / O系统”），它包含操作系统中的较低级别的硬件指定的部分。它与底层硬件特有的，但独立于操作系统的固化在ROM的“系统BIOS”，共同它代表了“CP/M BIOS”。

通过引入PS / 2的机器，IBM将系统BIOS分为真实模式和保护模式部分。真实模式部分是为了提供与现有的操作系统，如DOS的向后兼容性，因此被命名为“CBIOS”（用于兼容性BIOS），而“ABIOS”（高级BIOS）则提供适合多任务处理的新的操作系统如OS/2的接口。

BIOS技术源于IBM PC/AT机器的流行以及第一台由康柏公司研制生产的“克隆”PC。在PC引导的过程中，BIOS担负着初始化硬件，检测硬件功能，以及引导操作系统的责任。在早期，BIOS还提供一套运行时的服务程序给操作系统及应用程序使用。BIOS程序存放于一个断电后内容不会丢失的只读内存中；系统过电或被重置（reset）时，处理器第一条指令的地址会被定位到BIOS的内存中，让初始化程序开始运行。英特尔公司从2000年开始，发明了可扩展固件接口（Extensible Firmware Interface），用以规范BIOS的开发。而支持EFI规范的BIOS也被称为EFI BIOS。之后为了推广EFI，业界多家著名公司共同成立了统一可扩展固件接口论坛（UEFI Forum），英特尔公司将EFI 1.1规范贡献给业界，用以制订新的国际标准UEFI规范。目前UEFI规范的最新版本是2.1b。目前UEFI已在个人电脑上得到普及。
## 引导电脑原理

当电脑的电源打开，BIOS就会由主板上的闪存（flash memory）运行，并将芯片组和内存子系统初始化。BIOS会把自己从闪存中，解压缩到系统的主存；并且从那边开始运行。PC的BIOS代码也包含诊断功能，以保证某些重要硬件组件，像是键盘、磁盘设备、输出输入端口等等，可以正常运作且正确地初始化。几乎所有的BIOS都可以选择性地运行CMOS内存的设置程序；也就是保存BIOS会访问的用户自定义设置数据（时间、日期、硬盘细节，等等）。IBM技术参考手册中曾经包含早期PC和AT BIOS的80×86源代码。

现代的BIOS可以让用户选择由哪个设备引导电脑，如光盘驱动器、硬盘、软盘、USB U盘等等。这项功能对于安装操作系统、以LiveCD引导电脑、以及改变电脑找寻开机媒体的顺序特别有用。

有些BIOS系统允许用户可以选择要加载哪个操作系统（例如从第二颗硬盘加载其他操作系统），虽然这项功能通常是由第二阶段的开机管理程序（boot loader）来处理。
## BIOS固件

由于BIOS与硬件系统集成在一起（将BIOS程序指令刻录在IC中），所以有时候也被称为固件。在大约1990年BIOS是保存在ROM（只读内存）中而无法被修改。因为BIOS的大小和复杂程度随时间不断增加，而且硬件的更新速度加快，令BIOS也必须不断更新以支持新硬件，于是BIOS就改为存储在EEPROM或者闪存中，让用户可以轻易更新BIOS。然而，不适当的运行或是终止BIOS更新可能导致电脑或是设备无法使用。为了避免BIOS损坏，有些新的主板有备份的BIOS（“双BIOS”主板）。有些BIOS有“引导区块”（Boot Block），属于只读内存的一部分，一开始就会被运行且无法被更新。这个程序会在运行BIOS前，验证BIOS其他部分是否正确无误（经由检查码，凑杂码等等）。如果引导区块侦测到主要的BIOS已损坏，通常会自动由软盘驱动器等设备引导电脑，让用户可以修复或更新BIOS。一部分主板会在确定BIOS已损坏后自动搜索软盘驱动器等设备看看有没有完整的BIOS文件。此时用户可以放入存储BIOS文件的软盘（例如由网上下载的更新版BIOS文件，或是自行备份的BIOS文件）。引导区块会在找到软盘中存储的BIOS文件后自动尝试更新BIOS，希望以此修复已损坏的部分。硬件制造厂商经常发出BIOS升级来更新他们的产品和修正已知的问题。
## 与CMOS的联系和区别
### BIOS与CMOS的关系

CMOS是计算机上另一个重要的存储器。之所以提到它，是因为BIOS程序的设置结果就保存在CMOS中。而且，在BIOS程序引导计算机启动后，计算机需要载入CMOS中的用户信息和常规设置后才能正常使用。
### BIOS与CMOS的区别

二者的区别是，BIOS是存储在唯读记忆体（EEPROM），而CMOS为随机存储器（RAM）；BIOS中存储的是程序，而CMOS中存储的是普通信息。

EEPROM即是我们常用的U盘和各类存储卡，因此我们可以更新BIOS，其内容亦能在断电后保存。

CMOS RAM的内容在断电会消失。所以，把主板的电池拆出，便可重置其内容。另外，拆出电池也会重置时间。
## BIOS芯片简介
BIOS设置程序是储存在BIOS芯片中的，BIOS芯片是主板上一块长方形或正方形芯片，只有在开机时才可以进行设置。（一般在计算机启动时按F2或者Delete进入BIOS进行设置，一些特殊机型按F1、Esc、F12等进行设置）。BIOS设置程序主要对计算机的基本输入输出系统进行管理和设置，使系统运行在最好状态下，使用BIOS设置程序还可以排除系统故障或者诊断系统问题。有人认为既然BIOS是”程序”，那它就应该是属于软件，感觉就像自己常用的Word或Excel。但也有很多人不这么认为，因为它与一般的软件还是有一些区别，而且它与硬件的联系也是相当地紧密。形象地说，BIOS应该是连接软件程序与硬件设备的一座”桥梁”，负责解决硬件的即时要求。主板上的BIOS芯片或许是主板上唯一贴有标签的芯片，一般它是一块32针的双列直插式的集成电路，上面印有”BIOS”字样。
### ROM
在微机（微型计算机Microcomputer System）的发展初期，BIOS都存放在ROM（Read Only Memory，只读存储器）中。ROM内部的资料是在ROM的制造工序中，在工厂里用特殊的方法被烧录进去的，其中的内容只能读不能改，一旦烧录进去，用户只能验证写入的资料是否正确，不能再作任何修改。如果发现资料有任何错误，则只有舍弃不用。
### EPROM
EPROM（Erasable Programmable ROM，可擦除可编程ROM）芯片可重复擦除和写入，解决了ROM芯片只能写入一次的弊端。EPROM芯片有一个很明显的特征，在其正面的陶瓷封装上，开有一个玻璃窗口，透过该窗口，可以看到其内部的集成电路，紫外线透过该孔照射内部芯片就可以擦除其内的数据，完成芯片擦除的操作要用到EPROM擦除器。EPROM内资料的写入要用专用的编程器，并且往芯片中写内容时必须要加一定的编程电压（VPP=12—24V，随不同的芯片型号而定）。EPROM的型号是以27开头的，如27C020(8*256K）是一片2M Bits容量的EPROM芯片。EPROM芯片在写入资料后，还要以不透光的贴纸或胶布把窗口封住，以免受到周围的紫外线照射而使资料受损。
### EEPROM
由于EPROM操作的不便，586以后的主板上BIOS ROM芯片大部分都采用EEPROM（Electrically Erasable Programmable ROM，电可擦除可编程ROM）。 通过跳线开关和系统配带的驱动程序盘，可以对EEPROM进行重写，方便地实现BIOS升级。

BIOS芯片中主要存放：
+ 自诊断程序：通过读取CMOSRAM中的内容识别硬件配置，并对其进行自检和初始化；
+ CMOS设置程序：引导过程中，用特殊热键启动，进行设置后，存入CMOS RAM中；
+ 系统自举装载程序：在自检成功后将磁盘相对0道0扇区上的引导程序装入内存，让其运行以装入DOS系统；
+ 主要I/O设备的驱动程序和中断服务：由于BIOS直接和系统硬件资源打交道，因此总是针对某一类型的硬件系统，而各种硬件系统又各有不同，所以存在各种不同种类的BIOS，随着硬件技术的发展，同一种BIOS也先后出现了不同的版本，新版本的BIOS比起老版本来说，功能更强。

### NORFlash
从奔腾时代开始，现代的电脑主板都使用NORFlash来作为BIOS的存储芯片。除了容量比EEPROM更大外，主要是NORFlash具有写入功能，运行电脑通过软件的方式进行BIOS的更新，而无需额外的硬件支持（通常EEPROM的擦写需要不同的电压和条件），且写入速度快。
## 主要程序
### 中断例程
BIOS中中断例程即BIOS中断服务程序。它是微机系统软、硬件之间的一个可编程接口，用于程序软件功能与微机硬件实现的衔接。DOS/Windows操作系统对软盘、硬盘、光驱与键盘、显示器等外围设备的管理即建立在系统BIOS的基础上。程序员也可以通过 对INT 5、INT 13等中断的访问直接调用BIOS中断例程。
### 系统设置程序
微机部件配置情况是放在一块可读写的CMOS RAM芯片中的，不接市电或笔记本没有电池时，CMOS通过一块后备电池向CMOS供电以保持其中的信息。如果CMOS中关于微机的配置信息不正确，会导致不能开机、时间不准、零部件不能识别，并由此引发一系列的软硬件故障。在BIOS ROM芯片中装有一个程序称为“系统设置程序”，就是用来设置BIOS中的参数的，并将这些设置保存在COMS中。这个程序一般在开机时按下一个或一组键即可进入，它提供了良好的界面供用户使用。
### POST上电自检
微机接通电源后，系统将有一个对内部各个设备进行检查的过程，这是由一个通常称之为POST(Power On Self Test，上电自检）的程序来完成的。这也是BIOS的一个功能。完整的POST自检将包括CPU、640K基本内存、1M以上的扩展内存、ROM、主板、 CMOS存贮器、串并口、显示卡、软硬盘子系统及键盘测试。自检中若发现问题，系统将给出提示信息或鸣笛警告。
### 自检程序
在完成POST自检后，ROM BIOS将按照系统CMOS设置中的启动顺序搜寻软硬盘驱动器及CDROM、网络服务器等有效的启动驱动器 ，读入操作系统引导记录，然后将系统控制权交给引导记录，由引导记录完成系统的启动。
## BIOS功能
从功能上看，BIOS分为三个部分：
自检及初始化
这部分负责启动电脑，具体有三个部分：
1. 第一个部分是用于电脑刚接通电源时对硬件部分的检测，也叫做加电自检（Power On Self Test，简称POST），功能是检查电脑是否良好，通常完整的POST自检将包括对CPU，640K基本内存，1M以上的扩展内存，ROM，主板，CMOS存储器，串并口，显示卡，软硬盘子系统及键盘进行测试，一旦在自检中发现问题，系统将给出提示信息或鸣笛警告。自检中如发现有错误，将按两种情况处理：对于严重故障（致命性故障）则停机，此时由于各种初始化操作还没完成，不能给出任何提示或信号；对于非严重故障则给出提示或声音报警信号，等待用户处理。
2. 第二个部分是初始化，包括创建中断向量、设置寄存器、对一些外部设备进行初始化和检测等，其中很重要的一部分是BIOS设置，主要是对硬件设置的一些参数，当电脑启动时会读取这些参数，并和实际硬件设置进行比较，如果不符合，会影响系统的启动。
3. 第三个部分是引导程序，功能是引导DOS或其他操作系统。BIOS先从软盘或硬盘的开始扇区读取引导记录，如果没有找到，则会在显示器上显示没有引导设备，如果找到引导记录会把电脑的控制权转给引导记录，由引导记录把操作系统装入电脑，在电脑启动成功后，BIOS的这部分任务就完成了。

## 程序服务处理
程序服务处理程序主要是为应用程序和操作系统服务，这些服务主要与输入输出设备有关，例如读磁盘、文件输出到打印机等。为了完成这些操作，BIOS必须直接与计算机的I/O设备打交道，它通过端口发出命令，向各种外部设备传送数据以及从它们那儿接收数据，使程序能够脱离具体的硬件操作。
### 硬件中断处理
硬件中断处理则分别处理PC机硬件的需求，BIOS的服务功能是通过调用中断服务程序来实现的，这些服务分为很多组，每组有一个专门的中断。例如视频服务，中断号为10H；屏幕打印，中断号为05H；磁盘及串行口服务，中断14H等。每一组又根据具体功能细分为不同的服务号。应用程序需要使用哪些外设、进行什么操作只需要在程序中用相应的指令说明即可，无需直接控制。

（二）（三）两部分功能虽然是两个独立的内容，但在使用上密切相关。这两部分分别为软件和硬件服务，组合到一起，使计算机系统正常运行。

另外需注意：BIOS设置不当会直接损坏计算机的硬件，甚至烧毁主板，建议不熟悉者慎重修改设置。用户可以通过设置BIOS来改变各种不同的设置，比如onboard显卡的内存大小。用户手上所有的操作系统都是由BIOS转交给引导扇区，再由引导扇区转到各分区激活相应的操作系统。
### 小功能
开机出现DISK BOOT FAILURE,INSERT SYSTEM DISK AND PRESS ENTER 情况
### 从硬盘启动的设置方法：
1. 开机时按“Del”键，进入BIOS设置，(***/也可能是按F1、Esc或者是F12，依据电脑品牌的不同来具体操作/***)
2. 用上下光标键移动到第二项***Advanced BIOS Features *** 按回车，在按上下光标键移动到***First Boot drivers***，
3. 这时候把
按 “Page UP”键和“Page DOWN”选择属性为***“HDD”***或者***”DISK HARD”***
4. 按F10保存后，重启就可以了。
***（由于BIOS不同属性中的硬盘启动也不同。）***
## BIOS类别
市面上较流行的主板BIOS主要有 Award BIOS、AMI BIOS、Phoenix BIOS三种类型，此外还有台湾出的Insyde BIOS。
### Award
Award BIOS是由Award Software公司开发的BIOS产品，在目前的主板中使用最为广泛。Award BIOS功能较为齐全，支持许多新硬件，市面上多数主机板都采用了这种BIOS。
### AMI
AMI BIOS是AMI公司（全称：American Megatrends Incorporated）出品的BIOS系统软件，开发于80年代中期，早期的286、386大多采用AMI BIOS，它对各种软、硬件的适应性好，能保证系统性能的稳定，到90年代后，绿色节能电脑开始普及，AMI却没能及时推出新版本来适应市场，使得Award BIOS占领了大半壁江山。当然AMI 也有非常不错的表现，新推出的版本依然功能强劲。
### Phoenix
Phoenix BIOS是Phoenix公司产品，Phoenix意为凤凰或埃及神话中的长生鸟，有完美之物的含义。Phoenix BIOS 多用于高档的586原装品牌机和笔记本电脑上，其画面简洁，便于操作。
### Insyde
Insyde bios 是台湾的一家软件厂商的产品，是一种新兴的BIOS类型，被某些基于英特尔芯片的笔记本电脑采用，如神舟、联想。
### 百敖（BYOSOFT）
ByoCore是百敖（ByoSoft）公司出品的bios产品，广泛应用于PC、服务器、通讯、物联网、工控、消费类等领域。

## 进入方式
不同的BIOS有不同的进入方法，通常会在开机画面有提示。
### PC机进入方式
+ Award BIOS：按“Del”键
+ AMI BIOS：按“Del”或“ESC”键
+ Phoenix BIOS：按“F2”键
+ acer：按“Del”键
### 其它进入
+ ibm（冷开机按f1，部分新型号可以在重新启动时启动按f1）
+ hp（启动和重新启动时按f2）
+ sony（启动和重新启动时按f2）
+ dell（启动和重新启动时按f2）
+ acer（启动和重新启动时按f2）
+ toshiba（冷开机时按esc然后按f1）
+ hp compaq（开机到右上角出现闪动光标时按f10，或者开机时按f10）
+ fujitsu（启动和重新启动时按f2）
+ 绝大多数国产和台湾品牌（启动和重新启动时按f2）
## BIOS设置
### 标准CMOS
从主菜单选择“STANDARD CMOS SETUP”后进入“标准CMOS设置”菜单。

Date/Time:日期和时间的设置，我们可以用光标配合“Page Up”和“Page Down”依次设置成当前日期和时间。

Floppy Drive A，B: 设定软盘驱动器类型为None/720K/1.2M/1.44M/2.88M。

HDD Type（硬盘类型）： Auto（自动检测）、SCSI(SCSI HDD）、CD－ROM驱动器、Floptical(LS－120大容量软驱）或是Type 1～47等IDE设备。

LBA/Large:硬盘LBA/Large模式是否打开。540M以上的硬盘都要将此选项打开（On），但在Novell Netware 3.xx或4.xx版等网络操作系统下要视情况将它关掉（Off）。

Block Mode: 将此选项设为On，有助于硬盘存取速度加快，但有些旧硬盘不支持此模式，必须将此选项设为Off。

32 Bit Mode: 将此选项设为On，有助于在32位的操作系统（如WIN95/NT）下加快硬盘传输速度，有些旧硬盘不支持此模式，必须将此选项设为Off。
PIO Mode: 支持PIO Mode0～Mode5(DMA/33）。用BIOS程序自动检查硬盘时，会自动设置硬盘的PIO Mode。

***注意：当你在系统中接上一台IDE设备（如硬盘、光驱等）时，最好进入BIOS，让它自动检测。如果使用的是抽屉式硬盘的话，可将Type设成Auto，或将Primary以及Secondary的Type都改成Auto 即可。所谓Primary指的是第一IDE接口，对应于主板上的IDE0插口，Secondary指的是第二IDE接口，对应于主板上的IDE1插口。每个IDE接口可接Master/Slave（主/从）两台IDE设备。***
### 高级设定
1st/2rd/3rd/4th Boot Device: 开机启动设备的顺序，可选择由IDE0～3、SCSI、光驱、软驱、 Floptical (LS－120大容量软驱）或由Network（网络）开机。

S.M.A.R.TFor HardDisk: 开启（Enable）硬盘S.M.A.R.T功能。如果硬盘支持，此功能可提供硬盘自我监控的功能。

Quick Boot: 开启此功能后，可使开机速度加快。

Floppy Drive Swap: 若将此功能Enable，可使A驱与B驱互换。

PS/2 Mouse Support : 是否开启PS/2鼠标口，若设定为Enable，则开机时，将IRQ12保留给PS/2鼠标使用，若设定为Disable，则IRQ12留给系统使用。

Password Check: 设定何时检查Password（口令），若设定成Setup时，每次进入BIOS设定时将会要求输入口令，若设定成Always时，进入BIOS或系统开机时，都会要求输入口令，但先决条件是必须先设定口令（Security窗口中的User选项）。

Primary Display: 设定显示卡的种类。

Internal Cache: 是否开启CPU内部高速缓存（L1 Cache），应设为Enable。

External Cache: 是否开启主板上的高速缓存（L2 Cache），应设为Enable。

System BIOS Cacheable: 是否将系统BIOS程序复制到内存中，以加快BIOS存取速度。

C000－DC00，16K Shadow: 此8项是将主内存的UpperMemory（上位内存区）开启，将所有插卡上ROM程序映射到内存中，以加快CPU对BIOS的执行效率。Disable：不开启本功能；Enable：开启，且可提供读写区段功能；Cached：开启，但不提供读写功能。
### 属性设置

从主菜单上选择“BIOS FEATURES SETUP”即进入“BIOS属性设置”菜单。此设置中第1项“Virus Warning/病毒防范”除了在安装操作系统如DOS6?xx和Windows9x/200 0/NT等的过程中须设置为“Disabled”外，其余时间应该都设为“Enabled”。

第2、3、4和5项是涉及CPU的。其中“CPU Internal Cache/CPU内部缓存”、“External Cache/外部缓存”用来管理CPU的L1 Cache和L2 Cache。如果使用赛扬（主频为2.66Ghz和300Mhz的除外）、PentiumⅡ和PentiumⅢ可全部设为Enabled。第4项“CPU L2 Cache ECC Checking/CPU二级缓存ECC校验”一般情况下设为Enabled，但使用PentiumⅡ233 、PentiumⅢ266时可设为Disabled，因为这两种CPU的L2 Cache不具备ECC校验功能，设为Enable d时反而会降低系统启动速度。第5项“Processor number feature/处理器序列号功能”用于控制早已闹得沸沸扬扬的PentiumⅢ编号（ID），中国有关部门要求设为“Disabled”。但笔者曾试过，好像Intel出口到中国的“铜矿”PentiumⅢ已经在CPU中关闭了ID，此项设置毫无作用。

另外一些是关于系统启动时的设置，其中“快速自检/Quick power on self test”可设为“Enabled”，这样系统在启动时只对内存检验一遍，而设为“Disabled”时则在启动时将对内存检验三遍，自然要慢些；至于“CPU升级日志/CPU Update Data”则按BIOS推荐值设为“Enabled”，“优先网络启动/Boot From LAN First”项用于“网卡”等启动优先设置，除联网使用外一般都设为“Disabled”；“系统引导顺序/Boot Sequence” 就是经常提到的从C盘或A盘启动设置，其中的设置选择较多，有光驱、“D：”等优先启动设置等，比较简明。注意其中从“D”盘启动是指物理D盘（即所使用的第二块硬盘）而不是逻辑D：盘。

“软驱盘符交换/Swap Floppy Drive”用于交换两块软驱的“A：”、“B：”盘符，即如果有两块软驱可以通过此项设置将事实上的“A：”改为“B：”驱等；“引导显示卡/VGA Boot From”用于设置电脑在使用双显示卡时以PCI还是AGP显卡作为启动时（即显示）的主卡，此项设置根据用户自己使用的显卡总线类型而定，另外这项在给BIOS失效的显卡重写BIOS时也有用，例如在为BIOS失效的AGP卡重装BIOS时，可另插PCI 显卡引导系统进行操作。

“引导时检查软驱/Boot Up Floppy Seek”意义明确，用户可根据自己需要分别设为“Enabled”或“Disabled”，但设为“Enabled”时，启动时软驱“吱吱”作响挺烦的。

“启动时副键盘状态/Boot Up NumLock Stating”决定启动数字小键盘状态，设为“ON”时为数字输入有效（键盘上NumLock灯亮），反之则为无效状态；“Typematic Rate Sett ing”、“Typematic Rate（Chars/Sec）”和“Typematic Delay(Msec) ”三项用于调整键盘录入速度，意义不大。

“密码使用选择/Security Option”设置有“System”和“Setup”分别是确定密码是每次启动系统（包括热启动）时都用还是仅在进入BIOS设置时才用。

“显示校正/PCI-VGA Palette Snoop”是在ISA和PCI总线上分别使用两块显示板卡（如增加了VCD/DVD解压卡）时出现色彩不正常时可设为“Enabled”试试，一般都应设为“Disabled”。“Assign IRQ For VGA”则是设置由系统自动为显示卡配置中断（IRQ），目的是在系统中安装有I SA接口的解压卡等时使用，通常应该设为“Disabled”。

“OS Select For DRAM>64MB”这项只在电脑安装使用“OS/2”操作系统时才用，因为大多数用户的电脑中多安装Win XP/7/8之类，所以应该设为“No-OS/2”。

“HDD S.M.A.R.T capability”用于开启硬盘的“故障自监测报告”功能，如果你的硬盘具备这一保护功能请设为“Enabled”，如果不具备这一功能，打开此开关也不影响系统正常运行。

“Report No FDD For WIN95”的意思是在系统启动时报告win9x没有硬盘，用户系统一般是2X以上，强烈建议设置为Disable。

最后一项“Video BIOS Shadow”用于启动后将显示卡的BIOS程序映射在内存中（开辟保留区）中，这样从理论上可以提高电脑显示速度，所以可以设为“Enabled”。
## 芯片组功能（CHIPSET FEATURES SETUP)
从主菜单上选择“CHIPSET FEATURES SETUP”进入芯片组功能设置。此项设置中的具体内容因主板而异，但基本上都包括对系统硬件状态监测、CPU超温保护设置和对内存、显存状态设置等。本功能中的选项有助于系统效率的提升，建议使用默认值。若将某些Chipset、DRAM/SDRAM或SRAM部分的Timing值设得过快，可能会导致系统”死机”或运行不稳定，这时可试着将某些选项的速度值设定慢一点。　 “Reset Case Open Status”和“Case Opened”项用于设置电脑机箱（开启）状态监测和报警，一般设为“No”。

“Slow Down CPU Duty Cycle”用于选择CPU降速运行比例，可分别选择“Norma l”或“79%”及其它百分比。

“Shutdown Temp?（℃/?）”用于设置系统温度过高时自动关机初始值，同时用摄氏或华氏温度表示。
“***Temp? Select（℃/?）***”项为选择保护启动温度初始值，同样使用摄氏和华氏温度表示，此处仅对CPU进行设置。

“**Temperature Alarm**”用于设置CPU过温报警，应该设为“Yes”；然后就是系统对硬件监测所采集的数据，其中有“CPU”风扇、“Power/电源”和“Panel/板”风扇的运行状态，如果是使用非原装风扇，由于没有测速功能，系统将会认为CPU风扇故障而报警，所以此时应该将其设为“No”，其它风扇报警功能也应该予以设为“No”，对于系统监测显示的CPU电压和温度等状态参数用户只能看不能修改，但对于具备超频设置功能的BIOS中将包括对CPU的内核工作电压和I/O电压的微调，这部分内容须根据具体主板BIOS内容进行设置。

其次是对内存的运行速度进行设置，“SDRAM CAS latency Time”项设为“Auto”是使系统启动时自动检测内存，然后根据内存“SPD”中的参数进行设置，这样系统工作时不会因人为设置内存运行速度过高而出错。不过如果你买的是假内存（假SPD），那么系统运行时可就要给你闹别扭了。另外也可以按具体值分别设为“2”或 “3”等，视内存质量而定，数值越小时内存运行速度越快。

“DRAM Data Integrity Mode”则用于设置内存校验，由于多数用户使用的都是不具备ECC校验功能的SDRAM，所以这项自动设为“No-ECC”。注意：若系统使用SDRAM不稳时，建议将SDRAM速度调慢。

对于“System BIOS Cacheable”和“Video BIOS Cacheable”两项的设置是允许将主板BIOS和VGABIOS映射在高速缓存或内存中，理论是可以提高运行速度，但部分电脑使用时可能有问题，所以应根据试验后设置为“Enabled”，否则设为“Disabled”，使BIOS仅映射在内存中较为妥当。

“16 Bit I/O Recovery Time”项是输入/输出16位数据的器件传输复位速度，一般可分别设为“1”至“4”等，通常数值小、速度快。

“Memory Hole At15M-16M”是为ISA设备保留15～16M之间的内存而设的，一般设为 “Disabled”。如果你的Windows启动后少了1MB内存（通过控制板中系统属性查看），那么不妨检查一下是不是这项设成了“Enabled”。

“Delayed Transaction”是为解决PCI2?1总线的兼容问题而设，理论上设为“Enab led”可使用PCI21标准卡，但如设为“Enabled”可能会出现PCI2?1设备与普通PCI和ISA设备之间的兼容问题，所以一般推荐设成“Disabled”。

“Clock Spread Spectrum”项是为了抑制时钟频率辐射干扰，但需要硬件（主板）支持，所以可根据实际情况设为“Enabled”或“Disabled”。

USB Function Enabled: 此选项可开启USB接口的功能，如没有USB设备，建议将此选项设为Disable，否则会浪费一个IRQ资源。

Passive Release: 设定Passive Release（被动释放）为Enable时，可确保CPU与PCI总线主控芯片（PCI Bus Master）能随时重获对总线的控制权。
## 电源管理（POWER MANAGEMET SETUP)
在主菜单上选择“POWER MANAGEMMET SETUP”后进入“能源管理设置”菜单。

能源管理功能可使大部份周边设备在闲置时进入省电功能模示，减少耗电量，达到节约能源的目的。电脑在平常操作时，是工作在全速模式状态，而电源管理程序会监视系统的图形、串并口、硬盘的存取、键盘、鼠标及其他设备的工作状态，如果上述设备都处于停顿状态，则系统就会进入省电模式，当有任何监控事件发生，系统即刻回到全速工作模式的状态。省电模式又分为“全速模式（Normal）、打盹模式（Doze）、待命模式（Standby）、沉睡模式（Suspend)”，系统耗电量大小顺序：Normal>Doze> Standby > Suspend。

Power Management/APM: 是否开启APM省电功能。“Disabled”和“Enabled”，若开启（Enable），则可设定省电功能。“PM Control by APM”的意思是将能源管理交给系统（指WIN9x）的 APM（“高级能源管理”的英文缩写），可根据用户意愿分别设为“Yes”或“No”，但交予系统管理要更好些。

Green PC Monitor Power State/Video Power Down Mode/Hard Disk Power Down Mode : 设定显示器、显示卡以及硬盘是否开启省电模式，可设定成Standby、Suspend以及Off（即不进入省电模式）。

“Video off Method”项用于控制显示器，有“DPMS/显示能源管理系统”、“亮度关闭/B lank Screen”、“关亮度并切断同步信号/V/H SYNC+Blank Screen”等三种模式可选，但其中“DPMS”节能效果最好，为推荐设置，但需符合DPMS规范的显示器和显卡支持，如果设备不符合DPMS，可再试设置成另两项。

Video Power Down Mode: 设定显示器在省电模式下的状态 :Disable: 不设定 ；Stand By: 待命模式；Suspend: 沉睡模式。

Hard Disk Power Down Mode: 设定硬盘在省电模式下的状态。（同上）

“Suspend Mode”是休眠时间设置，可将时间设在1分至1小时之间，意思是超过所设时间后系统自动进入休眠状态。如果电脑中装有CD-R/W刻录机进行刻盘时最好将设为“Disabled”，以关闭休眠功能提高刻盘成功率。

“HDD Power Down”项设置硬盘自动停转时间，可设置在1至15分钟之间，或设为“Disabled”关闭硬盘自动停转。

Standby Timeout/Suspend Timeout: 本选项可设定系统在闲置几分钟后，依序进入Standby/Mode/Suspend Mode等省电模式。

VGA Active Monitor”项用于设置显示器亮度激活方式，可设为“Disabled”和“Enabled”两种。

“Soft-off by PWR-BTTN”项确定关机模式，设为“Instant-Off”，关机时用户按下电源开关，则立刻切断电源，设为“Delay4Secs”时，则在按下电源开关4秒钟后才切断电源，如果按下开关时间不足4秒，则自动进入休眠模式，所以一般按习惯设为“Instant-Off”。

“Power LED In Suspend”项设置机箱电源指示灯在系统休眠时的状态，可设为“闪动/Bl anking”、“亮/On”和“Off/Dual”等，通常按习惯设为“Blanking”使电脑在休眠时电源灯闪烁提醒用户注意。

“System After AC Back”项设置电脑在交流电断电后又恢复时的状态，可设为“断电/So ft-off”、“开机/Full On”、“Memory By S/W”和“Memory By H/W”三项，按国内使用情况一般都设为停电后再恢复供电时电脑不自动开机，即设为“断电/Soft-off”。

“CPUFAN off In suspend”项是设置CPU风扇在系统休眠时自动停转，可根据自己的风扇（只对原配或带测速功能的风扇有效）设为“Disabled”或“Enabled”。

“PME Event Wakeup”一项不详，先按缺省设置为“Disabled”。

“ModemRingOn/WakeOnlan”用于通过网络或Modem实现远程叫醒开机的设置，只要你不使用这些功能，就都可设为“Disabled”，如果需要再设为“Enabled”。

“Resume by Alarm”项用于定时开机，设置的时间可定在每月某日（00～31）某时某分某秒（ 00～23：00～59：00～59），但需要主板和其它硬件支持。

“能源管理设置”中还有“**Reload Global Timer Events**”项，这部分意思大致是对其中所列设备和网络设备以及部分系统资源（IRQ）对系统的激活是否对进入节能状态时间重新计时。

## 即插即用PCI
### 即插即用和PCI资源设置
从主菜单上选择“PNP/PCI CONFIGURATION”即可进入设置即插即用和PCI资源菜单。这项设置中“PnP OS Installed”意为安装即插即用的操作系统（自然是指WIN9x）可设为“Yes”，将PCI和ISA上的中断、DMA等资源交于操作系统管理，设为“No”时交BIOS管理。

“Resources Controlled By”项用于设置外设和板卡的资源管理，如果设为“AUTO” 交BIOS或操作系统自动管理时的设置内容很少；但设为“Manual”交用户自己管理时须设置的内容很多，此时要求用户必须具有较高的电脑应用水平，否则容易设置不当，造成设备资源使用冲突，所以一般都设为“AUTO”。当“Res ources Controlled By”项设为“AUTO”时，须设置的内容有：“Reset Configur ation Data”项是系统每次启动时将所检测硬件配置数据写入BIOS中，可分别设为“ESCD/外部设备配置数据”、“DMI/桌面管理界面”、“Both/同用”或“Disabled”，由于系统启动时不写ESCD并不影响正常运行，所以通常都设为“Disabled”，这样可能更安全些。

当“Resources Controlled By”设为“Manual”时须设置的内容除前面的几项外，还将列出系统所有可使用的IRQ和DMA资源由用户进行设置，设置时可使用“Legacy ISA”和“PCI/ISA PnP”两种状态，如果须要为ISA卡保留某一IRQ和DMA（如为声卡保留IRQ5和DMA6）时可将“IRQ -5 assigned to”和“DMA-6 assigned to”都设为“Legacy ISA”。

“Assign IRQ For USB”项是为了设置保留给USB（通用串行接口）的中断资源，如果不使用 USB设备，可设为“Disabled”。
## 加载预设值

第6项“LOAD BIOS DEFAULTS”和第7项“LOAD PERFORMANCE DEFAUL TS”中的内容和设置以前已经介绍过，此处不再重复。
## 端口综合
### 输入/输出端口综合设置

通过主菜单选择“INTEGRATED PERIPHERALS”进入设置菜单后（见图5），主要有：第1部分关于硬盘控制器的工作模式和状态，如果用户使用主板上IDE口联接硬盘和光驱等设备时，其中“On-Chip Pr imary PCI IDE/主板第一IDE口”和“On-Chip Secondary PCI IDE/主板PC I第二IDE口”必须设为“Enabled”，对于其中4个主、从IDE口的传输模式可根据情况设为“AUTO”、“MODE0”至“MODE4”。

第2部分“USB Keyboard support”的设置可根据是否使用USB键盘设为“Disabled”或“Enabled”。

第3部分是主板上软驱口、串、并口和PS/2等接口参数设置。其中两个串口可根据用户实际使用情况，分别对C OM1（Onboard serial port1）、COM2（Onboard serial port2）和并口（Onboard Parallel port）的具体I/O地址和IRQ参数进行设置，一般是在串口使用与其它设备出现资源冲突时进行调整。

并口的工作模式一般可分别设为“SPP”、“EPP”或“ECP”，由于“SPP”模式速度太慢，用户无法正常使用并口连接的光驱、硬盘、扫描仪等设备，所以一般不用；设为“ECP”时也可能会出现部分外设连接不正常问题，所以并口一般设为“EPP”或“ECP+EPP”模式为好。

接下来的“PS/2 Mouse Power On”和“Keyboard Power On”是用于电脑开机的，其中鼠标必须使用PS/2（即小6针圆口）。如果将“PS/2 Mouse Power On”设为“DblC lick/双击”时，即可在电脑关机后再双击鼠标左键重新开机。“Keyboard Power On”也可同样如此进行。

以下主菜单中的第9项“SUPERVISOR PASSWORD”、第10项“USER PASSWORD” 和第11项“IDE HDD AUTO DETECTION”、第12项“SAVE&EXIT SETUP”和第13 项“EXIT WITHOUT SAVING”等设置的具体内容在以前也都介绍过，所以也不再重复。由于各种主板的B IOS内容不尽相同（即使是同一公司开发的BIOS也这样），所以以上所介绍的内容仅供参考，以后在对其它主板的BI OS项目进行设置时须根据具体内容进行才可能获得比较满意的设置效果。
## 激活过程

当BIOS激活时会先去确认CMOS中的资料是否正确。如果正确，便会将之前用户存储在CMOS的资料，加上已存或找到的硬件信息，整合成一个表格，写到内存中，也就是所谓的SMBIOS。如果发现错误，则会自动以默认值取代CMOS提供的资料。所以这份写入内存的SMBIOS表格，就是用户进入BIOS选项后，可以看到或选择的所有信息。

所有会在BIOS之前发生的操作就只有Power On，也就是按下计算机上电源开关的那一瞬间。在Power On阶段一开始，会进入BIOS的激活流程，当用户一按下电源开关，CPU会先被激活去寻找BIOS，接着BIOS会先在Flash Memory中执行，再加上CMOS中用户所喜好的设置，然后BIOS将自己解压缩到计算机的主存储器中。此时，用户若按下【DEL】键，就可以进入BIOS所提供的设置选项，从而看到所有的设置值；或是当用户进入操作系统后，操作系统就可以参考内存中的BIOS资料，访问到每一个硬件地址。
## 章节来源
+ [BIOS--维基百科](https://zh.wikipedia.org/wiki/BIOS)

## 历史版本

| 版本号 | 维护人 |维护时间 |维护内容|
| :- | :- | :-| :- |
| v1.0 | [Jhin](http://blog.link-lin.cn) |2017-11-10|创建了本词条|
