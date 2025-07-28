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

![创建SSH密钥](assets/learning file/git学习/image/截图 2025-07-28 21-21-21.png)





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
- [ ] 将修改添加到暂存区：`git add a.txt`
- [ ] 将暂存区的修改添加到版本库：`git commit -m "Update a.txt"`
- [ ] 将本地版本库提交到远程仓库：`git push origin mian` 