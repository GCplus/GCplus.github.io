# git工具基础教程
>当前版本：v0.8  
>维护人：Jhin  
>维护时间：2017年10月27日

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
####  常用命令
+ 查看、添加、提交、删除、找回，重置修改文件  
git help <command> # 显示command的help  
git show # 显示某次提交的内容 git show $id  
git co -- <file> # 抛弃工作区修改  
git co . # 抛弃工作区修改  
git add <file> # 将工作文件修改提交到本地暂存区  
git add . # 将所有修改过的工作文件提交暂存区  
git rm <file> # 从版本库中删除文件  
git rm <file> --cached # 从版本库中删除文件，但不删除文件  
git reset <file> # 从暂存区恢复到工作文件  
git reset -- . # 从暂存区恢复到工作文件  
git reset --hard # 恢复最近一次提交过的状态，即放弃上次提交后的所有本次修改  
git ci <file> git ci . git ci -a # 将git add, git rm和git ci等操作都合并在一起做  
+ git ci -am "some comments"  
git ci --amend # 修改最后一次提交记录  
git revert <$id> # 恢复某次提交的状态，恢复动作本身也创建次提交对象  
git revert HEAD # 恢复最后一次提交的状态  
+ 查看文件diff  
git diff <file> # 比较当前文件和暂存区文件差异  
git diff <id2> # 比较两次提交之间的差异  
git diff <branch1>..<branch2> # 在两个分支之间比较  
git diff --staged # 比较暂存区和版本库差异  
git diff --cached # 比较暂存区和版本库差异  
git diff --stat # 仅仅比较统计信息  
+ 查看提交记录  
git log git log <file> # 查看该文件每次提交记录  
git log -p <file> # 查看每次详细修改内容的diff  
git log -p -2 # 查看最近两次详细修改内容的diff  
git log --stat #查看提交统计信息  
+ tig  
Mac上可以使用tig代替diff和log，brew install tig  
+ Git 本地分支管理  
  + 查看、切换、创建和删除分支  
git br -r # 查看远程分支  
git br <new_branch> # 创建新的分支  
git br -v # 查看各个分支最后提交信息  
git br --merged # 查看已经被合并到当前分支的分支  
git br --no-merged # 查看尚未被合并到当前分支的分支  
git co <branch> # 切换到某个分支  
git co -b <new_branch> # 创建新的分支，并且切换过去  
git co -b <new_branch> <branch> # 基于branch创建新的new_branch  
git co $id # 把某次历史提交记录checkout出来，但无分支信息，切换到其他分支会自动删除  
git co $id -b <new_branch> # 把某次历史提交记录checkout出来，创建成一个分支  
git br -d <branch> # 删除某个分支  
git br -D <branch> # 强制删除某个分支 (未被合并的分支被删除的时候需要强制)  
  + 分支合并和rebase  
git merge <branch> # 将branch分支合并到当前分支  
git merge origin/master --no-ff # 不要Fast-Foward合并，这样可以生成merge提交  
git rebase master <branch> # 将master rebase到branch，相当于： git co <branch> && git rebase master && git co master && git merge <branch>  
  + Git补丁管理(方便在多台机器上开发同步时用)  
git diff > ../sync.patch # 生成补丁  
git apply ../sync.patch # 打补丁  
git apply --check ../sync.patch #测试补丁能否成功  
  + Git暂存管理  
git stash # 暂存  
git stash list # 列所有stash  
git stash apply # 恢复暂存的内容  
git stash drop # 删除暂存区  
+ Git远程分支管理  
git pull # 抓取远程仓库所有分支更新并合并到本地  
git pull --no-ff # 抓取远程仓库所有分支更新并合并到本地，不要快进合并  
git fetch origin # 抓取远程仓库更新   
git merge origin/master # 将远程主分支合并到本地当前分支  
git co --track origin/branch # 跟踪某个远程分支创建相应的本地分支  
git co -b <local_branch> origin/<remote_branch> # 基于远程分支创建本地分支，功能同上  
git push # push所有分支  
git push origin master # 将本地主分支推到远程主分支  
git push -u origin master # 将本地主分支推到远程(如无远程主分支则创建，用于初始化远程仓库)  
git push origin <local_branch> # 创建远程分支， origin是远程仓库名  
git push origin <local_branch>:<remote_branch> # 创建远程分支  
git push origin :<remote_branch> #先删除本地分支(git br -d <branch>)，然后再push删除远程分支  
+ Git远程仓库管理
  + GitHub
git remote -v # 查看远程服务器地址和仓库名称  
git remote show origin # 查看远程服务器仓库状态  
git remote add origin git@ github:robbin/robbin_site.git # 添加远程仓库地址  
git remote set-url origin git@ github.com:robbin/robbin_site.git # 设置远程仓库地址(用于修改远程仓库地址)   
git remote rm <repository> # 删除远程仓库  
  + 创建远程仓库  
git clone --bare robbin_site robbin_site.git # 用带版本的项目创建纯版本仓库  
scp -r my_project.git git@ git.csdn.net:~ # 将纯仓库上传到服务器上  
mkdir robbin_site.git && cd robbin_site.git && git --bare init # 在服务器创建纯仓库  
git remote add origin git@ github.com:robbin/robbin_site.git # 设置远程仓库地址  
git push -u origin master # 客户端首次提交  
git push -u origin develop # 首次将本地develop分支提交到远程develop分支，并且track  
git remote set-head origin master # 设置远程仓库的HEAD指向master分支  
+ 也可以命令设置跟踪远程库和本地库  
git branch --set-upstream master origin/master  
git branch --set-upstream develop origin/develop
## 章节来源
+ [git是什么-廖雪峰](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/001373962845513aefd77a99f4145f0a2c7a7ca057e7570000)
+ [git常用命令-思考的足迹](http://www.cnblogs.com/cspku/articles/Git_cmds.html)
## 历史版本

| 版本号 | 维护人 |维护时间 |维护内容|
| :- | :- | :-| :- |
| v0.8 | [Jhin](http://blog.link-lin.cn) |2017-10-27|创建了本词条|
