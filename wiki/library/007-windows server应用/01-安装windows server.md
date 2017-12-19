# 通过网络安装windows
> 当前版本：v1.0  
>维护人：Jhin  
>维护时间：2017年12月19日

## 安装windows server
windows server的安装与windows的安装一样，下面为windows server2012安装时的部分截图

<div align="center">
![](/wiki/image/windows/install/windows2012-1.jpg)  
开始界面</div>

![](/wiki/image/windows/install/windows2012-2.jpg)  
<div align="center">启动安装界面</div>

![](/wiki/image/windows/install/windows2012-3.jpg)  
<div align="center">选择版本界面，一般选择datacenter版本</div>

![](/wiki/image/windows/install/windows2012-4.jpg)  
<div align="center">初始化安装，仅安装windows</div>

![](/wiki/image/windows/install/windows2012-5.jpg)  
<div align="center">格式化磁盘</div>

#### 下一步以后等待安装就可以了，稍等片刻就可以安装完成

## 设置windows server用户与密码

![](/wiki/image/windows/setting/setpassword.jpg)

## 添加windows部署服务

![](/wiki/image/windows/wds/windows2012-1.jpg)
<div align="center">添加角色</div>

![](/wiki/image/windows/wds/windows2012-2.jpg)
<div align="center">第二步，启动安装</div>

![](/wiki/image/windows/wds/windows2012-3.jpg)
<div align="center">选择服务器</div>

![](/wiki/image/windows/wds/windows2012-4.jpg)
<div align="center">添加相应的dhcp、dns和windows部署服务</div>
#### 一路下一步，等待安装完成
