# skipfish
***
Skipfish是一个命令行模式，以C语言编写的积极的Web应用程序的安全性侦察工具，没有代理模式。 它准备了一个互动为目标的网站的站点地图进行一个递归爬网和基于字典的探头。

### 特点
+ 多路单线程
+ 全异步网络I/O
+ 启发式内容识别
+ 误报低

***

## 使用方法

+
``` skipfish -o test http:# ```

-0 为指定输出 test为文件夹名称 http为你要爬取的网页目录

+
```skipfish -o test @url.txt ```

@url.txt 为你要扫描的网站集合

+
```skipfish -o test -I /string/ http://#```

-I 为只扫描包含string字符串的网页地址

+
```skipfish -o test -X /string/ http://#```

-X 不扫描包含string字符串的网页地址
