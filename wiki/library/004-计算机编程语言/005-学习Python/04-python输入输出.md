# 输入输出
 今天就开始和大家讲python基础知识

>当前版本：v1.2  
>维护人：Gu-f  
>维护时间：2018年05月25日

## 输出  
python 中输出函数是print()，区别于C语言，比C语言少了个f，想要输出只需要把需要输出的内容写进函数里即可。  
```python
print("hello world!")
```
需要注意的是，在python中是不需要“；”的，或者  
```python
print('hello world!')
```
这段代码同样可以输出 hello world！两段代码的显示效果是一样的，可见在python中使用单引号和双引号的作用是相同的  

效果如下  
![04-01](/wiki/image/python/04/04-01.jpg)  

python中还可以分开打印一行字符串，代码如下  
```python
print("hello""world")
```
效果如下  
![04-02](/wiki/image/python/04/04-02.jpg)  

也可以通过+号将字符串进行连接  
```python
print("hello"+"world")
print("hello"+"world"+"!")
```
效果如下：  
![04-03](/wiki/image/python/04/04-03.jpg)  

在python可以直接进行数值的计算，通过print函数直接可以打印出来  
```python
print(1+1)
print(2+2)
print(1+1+1)
```
效果如下：  
![04-04](/wiki/image/python/04/04-04.jpg)  

结合字符串输出使打印出的效果更佳  
```python
print("1+1=",1+1)
print("1+2=",1+2)
```
运行结果：  
![04-05](/wiki/image/python/04/04-05.jpg)  

## 输入
首先我们要明白变量，python中的变量和C语言中的变量类似，只不过在C语言中变量需要定义，在python中变量是不需要定义的，可以直接使用。  
如下：  
```python
name=123
print(name)
```
运行的结果如下：  
![04-06](/wiki/image/python/04/04-06.jpg)  

在python中的输入其实也很简单，只需要一个input()函数即可实现  
```python
a=input()
print(a)
```
结果如下：  
![04-07](/wiki/image/python/04/04-07.jpg)  

接下来我们综合利用一下print()和input()函数  
```python
name=input()
print("hello",name)
```
运行结果如下，注意中间多了个空格哦，，注意和字符串连接的区别。  
![04-08](/wiki/image/python/04/04-08.jpg)  

当需要输出多行文本时可以用'''或"""来进行输出  
```python
print('''hello
      world
      123
      456''')
print("""hello
      world
      789""")
```
运行的结果如下：  
![04-09](/wiki/image/python/04/04-09.jpg)  


自己可以尝试多多联系，比如打印出“你好，GitHub”  
好了，今天就到这里了。  


## 历史版本

| 版本号 | 维护人 |维护时间 |维护内容|
| :- | :- | :-| :- |
| v1.0 | [Gu-f](https://Gu-f.github.io/) |2018-05-24|创建了本词条|
| v1.1 | [Jhin](https://blog.link-lin.cn/) |2018-05-24|修正了本词条的格式|
| v1.2 | [Gu-f](https://Gu-f.github.io/) |2018-05-25|补充缺失内容|
