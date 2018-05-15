# git工具基础教程
>当前版本：v1.1  
>维护人：Jhin  
>维护时间：2018年05月14日

## git是什么
Git是什么？  
Git是目前世界上最先进的分布式版本控制系统（没有之一）。  
Git有什么特点？简单来说就是：高端大气上档次！  
那什么是版本控制系统？  
如果你用Microsoft Word写过长篇大论，那你一定有这样的经历：  
想删除一个段落，又怕将来想恢复找不回来怎么办？有办法，先把当前文件“另存为……”一个新的Word文件，再接着改，改到一定程度，再“另存为……”一个新文件，这样一直改下去，最后你的Word文档变成了这样：  
![word创建多个版本](/wiki/image/git-word-0.jpg "关于word创建多个版本的图片")  
过了一周，你想找回被删除的文字，但是已经记不清删除前保存在哪个文件里了，只好一个一个文件去找，真麻烦。  
看着一堆乱七八糟的文件，想保留最新的一个，然后把其他的删掉，又怕哪天会用上，还不敢删，真郁闷。  
更要命的是，有些部分需要你的财务同事帮助填写，于是你把文件Copy到U盘里给她（也可能通过Email发送一份给她），然后，你继续修改Word文件。一天后，同事再把Word文件传给你，此时，你必须想想，发给她之后到你收到她的文件期间，你作了哪些改动，得把你的改动和她的部分合并，真困难。  
于是你想，如果有一个软件，不但能自动帮我记录每次文件的改动，还可以让同事协作编辑，这样就不用自己管理一堆类似的文件了，也不需要把文件传来传去。如果想查看某次改动，只需要在软件里瞄一眼就可以，岂不是很方便？  
这个软件用起来就应该像这个样子，能记录每次文件的改动：

|版本|	用户|	说明|	日期|
|:-|:-|:-|:-|
|1|	张三|	删除了软件服务条款5|	7/12 10:38|
|2|	张三|	增加了License人数限制|	7/12 18:09|
|3|	李四|	财务部门调整了合同金额|	7/13 9:51|
|4|	张三|	延长了免费升级周期|	7/14 15:17|
## 如何使用git
#### 安装（废话，不安装怎么用）
+ windows下安装  
  下载[git-for-windows](https://git-for-windows.github.io/),然后安装，下一步就可以
+ linux下安装  
  首先执行```git```查看系统是否自带这个工具，
  如果返回```The program 'git' is currently not installed. .....```说明没有安装，需要执行一下命令进行安装
  ```
如果你是debin,ubuntu...执行
apt-get install git
如果是redhat,centos...执行
yum install git
  ```
#### 常用命令
如果是日常使用记住下图几个就可以了  
![](/wiki/image/git-cmd-use.png)

名词的翻译如下:

|名词|翻译|
|:-|:-|
|Workspace|作区|
|Index/Stage|暂存区|
|Repository|仓库区（或本地仓库）|
|Remote|远程仓库|
+ 新建代码库  
```
  # 在当前目录新建一个Git代码库
  $ git init

  # 新建一个目录，将其初始化为Git代码库
  $ git init [project-name]

  # 下载一个项目和它的整个代码历史
  $ git clone [url]
```
+ 配置
Git的设置文件为`.gitconfig`，它可以在用户主目录下（全局配置），也可以在项目目录下（项目配置）。
```
  # 显示当前的Git配置
  $ git config --list

  # 编辑Git配置文件
  $ git config -e [--global]

  # 设置提交代码时的用户信息
  $ git config [--global] user.name "[name]"
  $ git config [--global] user.email "[email address]"
```
+ 增加删除文件
```
  # 添加指定文件到暂存区
  $ git add [file1] [file2] ...

  # 添加指定目录到暂存区，包括子目录
  $ git add [dir]

  # 添加当前目录的所有文件到暂存区
  $ git add .

  # 添加每个变化前，都会要求确认
  # 对于同一个文件的多处变化，可以实现分次提交
  $ git add -p

  # 删除工作区文件，并且将这次删除放入暂存区
  $ git rm [file1] [file2] ...

  # 停止追踪指定文件，但该文件会保留在工作区
  $ git rm --cached [file]

  # 改名文件，并且将这个改名放入暂存区
  $ git mv [file-original] [file-renamed]
```
+ 代码提交
```
  # 提交暂存区到仓库区
  $ git commit -m [message]

  # 提交暂存区的指定文件到仓库区
  $ git commit [file1] [file2] ... -m [message]

  # 提交工作区自上次commit之后的变化，直接到仓库区
  $ git commit -a

  # 提交时显示所有diff信息
  $ git commit -v

  # 使用一次新的commit，替代上一次提交
  # 如果代码没有任何新变化，则用来改写上一次commit的提交信息
  $ git commit --amend -m [message]

  # 重做上一次commit，并包括指定文件的新变化
  $ git commit --amend [file1] [file2] ...
```
+ 分支
```
  # 列出所有本地分支
  $ git branch

  # 列出所有远程分支
  $ git branch -r

  # 列出所有本地分支和远程分支
  $ git branch -a

  # 新建一个分支，但依然停留在当前分支
  $ git branch [branch-name]

  # 新建一个分支，并切换到该分支
  $ git checkout -b [branch]

  # 新建一个分支，指向指定commit
  $ git branch [branch] [commit]

  # 新建一个分支，与指定的远程分支建立追踪关系
  $ git branch --track [branch] [remote-branch]

  # 切换到指定分支，并更新工作区
  $ git checkout [branch-name]

  # 切换到上一个分支
  $ git checkout -

  # 建立追踪关系，在现有分支与指定的远程分支之间
  $ git branch --set-upstream [branch] [remote-branch]

  # 合并指定分支到当前分支
  $ git merge [branch]

  # 选择一个commit，合并进当前分支
  $ git cherry-pick [commit]

  # 删除分支
  $ git branch -d [branch-name]

  # 删除远程分支
  $ git push origin --delete [branch-name]
  $ git branch -dr [remote/branch]
```
+ 标签
```
  # 列出所有tag
  $ git tag

  # 新建一个tag在当前commit
  $ git tag [tag]

  # 新建一个tag在指定commit
  $ git tag [tag] [commit]

  # 删除本地tag
  $ git tag -d [tag]

  # 删除远程tag
  $ git push origin :refs/tags/[tagName]

  # 查看tag信息
  $ git show [tag]

  # 提交指定tag
  $ git push [remote] [tag]

  # 提交所有tag
  $ git push [remote] --tags

  # 新建一个分支，指向某个tag
  $ git checkout -b [branch] [tag]
```
+ 查看信息
```
  # 显示有变更的文件
  $ git status

  # 显示当前分支的版本历史
  $ git log

  # 显示commit历史，以及每次commit发生变更的文件
  $ git log --stat

  # 搜索提交历史，根据关键词
  $ git log -S [keyword]

  # 显示某个commit之后的所有变动，每个commit占据一行
  $ git log [tag] HEAD --pretty=format:%s

  # 显示某个commit之后的所有变动，其"提交说明"必须符合搜索条件
  $ git log [tag] HEAD --grep feature

  # 显示某个文件的版本历史，包括文件改名
  $ git log --follow [file]
  $ git whatchanged [file]

  # 显示指定文件相关的每一次diff
  $ git log -p [file]

  # 显示过去5次提交
  $ git log -5 --pretty --oneline

  # 显示所有提交过的用户，按提交次数排序
  $ git shortlog -sn

  # 显示指定文件是什么人在什么时间修改过
  $ git blame [file]

  # 显示暂存区和工作区的差异
  $ git diff

  # 显示暂存区和上一个commit的差异
  $ git diff --cached [file]

  # 显示工作区与当前分支最新commit之间的差异
  $ git diff HEAD

  # 显示两次提交之间的差异
  $ git diff [first-branch]...[second-branch]

  # 显示今天你写了多少行代码
  $ git diff --shortstat "@{0 day ago}"

  # 显示某次提交的元数据和内容变化
  $ git show [commit]

  # 显示某次提交发生变化的文件
  $ git show --name-only [commit]

  # 显示某次提交时，某个文件的内容
  $ git show [commit]:[filename]

  # 显示当前分支的最近几次提交
  $ git reflog
```
+ 远程同步
```
  # 下载远程仓库的所有变动
  $ git fetch [remote]

  # 显示所有远程仓库
  $ git remote -v

  # 显示某个远程仓库的信息
  $ git remote show [remote]

  # 增加一个新的远程仓库，并命名
  $ git remote add [shortname] [url]

  # 取回远程仓库的变化，并与本地分支合并
  $ git pull [remote] [branch]

  # 上传本地指定分支到远程仓库
  $ git push [remote] [branch]

  # 强行推送当前分支到远程仓库，即使有冲突
  $ git push [remote] --force

  # 推送所有分支到远程仓库
  $ git push [remote] --all
```
+ 撤销
```
  # 恢复暂存区的指定文件到工作区
  $ git checkout [file]

  # 恢复某个commit的指定文件到暂存区和工作区
  $ git checkout [commit] [file]

  # 恢复暂存区的所有文件到工作区
  $ git checkout .

  # 重置暂存区的指定文件，与上一次commit保持一致，但工作区不变
  $ git reset [file]

  # 重置暂存区与工作区，与上一次commit保持一致
  $ git reset --hard

  # 重置当前分支的指针为指定commit，同时重置暂存区，但工作区不变
  $ git reset [commit]

  # 重置当前分支的HEAD为指定commit，同时重置暂存区和工作区，与指定commit一致
  $ git reset --hard [commit]

  # 重置当前HEAD为指定commit，但保持暂存区和工作区不变
  $ git reset --keep [commit]

  # 新建一个commit，用来撤销指定commit
  # 后者的所有变化都将被前者抵消，并且应用到当前分支
  $ git revert [commit]

  # 暂时将未提交的变化移除，稍后再移入
  $ git stash
  $ git stash pop
```
+ 其他
```
  # 生成一个可供发布的压缩包
  $ git archive
```

## 章节来源
+ [git是什么-廖雪峰](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001373962845513aefd77a99f4145f0a2c7a7ca057e7570000)
+ [常用 Git 命令清单-阮一峰的网络日志](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)

## 历史版本

| 版本号 | 维护人 |维护时间 |维护内容|
| :- | :- | :-| :- |
| v0.8 | [Jhin](http://blog.link-lin.cn) |2017-10-27|创建了本词条|
|v1.0|[Jhin](http://blog.link-lin.cn)|2017-10-27|修正了本词条，更加容易阅读|
|v1.1|[Jhin](http://blog.link-lin.cn)|2018-05-14|修改了文章标题|
