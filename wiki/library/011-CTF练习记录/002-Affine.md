
# Affine  


>题目来源：JDCTF  


>当前版本：v1.0  
>维护人：Gu-f  
>维护时间：2019年01月27日  

题目：  
![description](/wiki/image/ctfimg/affinejdctf.jpg)  


首先我们拿到题目，看到题目是Affine，很显然是仿射加密。  
直接上脚本，或[仿射解密在线网站](http://ctf.ssleye.com/affine.html)  
脚本参考如下：  
```python
#仿射密码解密
#改进欧几里得算法求线性方程的x与y
#例：y = 17*x-8 flag{szzyfimhyzd}，，a=17,b=-8
#输出全为大写
def get(a, b):
    if b == 0:
        return 1, 0
    else:
        k = a //b
        remainder = a % b
        x1, y1 = get(b, remainder)
        x, y =y1, x1 - k * y1
    return x, y

s = input("请输入解密字符：").upper()
a = int(input("请输入a："))
b = int(input("请输入b："))

#求a关于26的乘法逆元
x, y = get(a, 26)
a1 = x % 26

l= len(s)
for i in range(l):
    cipher = a1 * (ord(s[i])- 65 - b) % 26
    res=chr(cipher + 65)
    print(res, end='')
```

运行脚本即可得到flag，或在线网站也可以。


## 历史版本

| 版本号 | 维护人 |维护时间 |维护内容|
| :- | :- | :-| :- |
| v1.0 | [Gu-f](https://Gu-f.github.io/) |2019-01-27|创建了本词条|
