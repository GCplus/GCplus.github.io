# skipfish
>当前版本：v1.1  
>维护人：yuluo  
>维护时间：2018年05月14日  

***本文残缺，仍待补充***

***
Skipfish是一个命令行模式，以C语言编写的积极的Web应用程序的安全性侦察工具，没有代理模式。 它准备了一个互动为目标的网站的站点地图进行一个递归爬网和基于字典的探头。

## 特点
+ 多路单线程
+ 全异步网络I/O
+ 启发式内容识别
+ 误报低

***

## 使用方法

+ ``` skipfish -o test http:# ```

-0 为指定输出 test为文件夹名称 http为你要爬取的网页目录

+ ```skipfish -o test @url.txt ```

@url.txt 为你要扫描的网站集合

+ ```skipfish -o test -I /string/ http://#```

-I 为只扫描包含string字符串的网页地址

+ ```skipfish -o test -X /string/ http://#```

-X 不扫描包含string字符串的网页地址

+ ```skipfish -o test -S complete.wl http:#```

-S为加载字典 差点查找方法   ```dpkg -L skipfish | grup wl```

+ ```skipfish -o test -K http:# ```

-K 指不对url中的变量进行模糊测试（fuzz）

+ ```skipfish -O test -D url http:#```

-D 为跨站点扫描其他域 可添加别的域名进行扫描

+ ```skipfish -O test -l 10 -m 100 http:#```

-l 为每秒最大请求数 -m 每个IP最大并发数 为了躲避连接限制

***
## 基于身份认证的网络扫描

```skipfish -A user:pass -o test http://1.1.1.1```

基本http身份认证

```skipfish  -C "PHPSESSID=" -C "security=" -o test http://1.1.1.1```

#基于cookie


| 版本号 | 维护人 |维护时间 |维护内容|
| :- | :- | :-| :- |
| v1.0 | [yuluo](http://www.yuluo-zy.com) |2018-05-13|创建了本词条|
| v1.1 | [Jhin](http://blog.link-lin.cn) |2018-5-14|修正了词条格式|
