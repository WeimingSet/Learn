# Linux系统git学习

##  1. git 安装

git各平台下载地址：https://git-scm.com/downloads；[Linux系统安葬地址](https://git-scm.com/downloads/linux)：跟着流程输入指令即可

###  git 配置

配置个人信息：

```
git config --global user.name xiewm
git config --global user.email 2325870306@qq.com
git config --list #查看配置信息
```

![创建SSH密钥](https://github.com/WeimingSet/Learn/blob/master/git学习/image/密钥创建.png)

### gitub配置

setting &longrightarrow; SSH&GPG key &longrightarrow;  New SSH key

```
cat xxxx/.ssh/id_rsa.pub
```

然后将获取的密钥粘贴上去即可

####  创建仓库

![创建新仓库](https://github.com/WeimingSet/Learn/blob/master/git学习/image/仓库创建.png)

提交需要github的用户名和创建个人token而不能使用密码

## 2. 工作区、暂存区、版本库

工作区是计算机本地目录，可以进行修改

暂存区是.git里的暂存区域

```
git add filename #将单个文件提交到暂存区
git add .. #将工作区的所有修改提交
git status #查看工作区所有文件
```

版本库包含了所有版本的快照，记录项目的全部历史

```
git commit -m "Commit message" #将暂存区所有更改提交到本地版本库
git log #查看历史记录
git diff #查看工作区与暂存区的区别
git diff --cached #查看暂存区与最后一次提交的差异
```

流程：

- [x] 工作区修改文件a.txt
- [x] 将修改添加到暂存区：`git add a.txt`
- [x] 将暂存区的修改添加到版本库：`git commit -m "Update a.txt"`
- [x] 将本地版本库提交到远程仓库：`git push origin main` 

## 3. 创建本地仓库

创建新目录，cd到新目录

初始化为git仓库：`git init`

从远程克隆到本地制定文件夹：`git clone <repo> <directory>`

当前仓库配置文件：`git config`

系统所有仓库的配置文件：`git config --global`

[git基本操作命令](https://www.runoob.com/git/git-basic-operations.html)

## 4. 分支管理

创建新分支并切换到该分支：`git checkout -b <branchname>`

切换分支：`git checkout <branchname>`

合并其他分支到现在分支：`git merge <branchname>`

删除分支：`git branch -d <branchname>`

## 5.标签

创建标签以区分版本：`git tag -a <taagname e.g. v1.0>`#带注释的

推送标签到远程仓库：`git push origion <tagname>`

推送所有标签：`git tag origin --tag`

## 6. 远程仓库与本地仓库出现冲突

远程仓库多了一个文件

`git pull origin master --no-rebase`合并本地与远程文件，告诉git冲突已解决`git add <confitfilename>`

`git commit -m '冲突解决'`，重新提交`git push origin master`