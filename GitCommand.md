< [Back](README.md)

## 安装git

`yum install git`

## 配置Git

Git安装完成后，还需要最后一步设置，在命令行输入：

```
# 设置提交代码时的用户信息
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。注意git config命令的--global参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。


```
# 显示当前的Git配置
git config --list

# 编辑Git配置文件
git config -e [--global]

```

## 新建代码库

```
# 在当前目录新建一个Git代码库
git init

# 新建一个目录，将其初始化为Git代码库
git init [project-name]

# 下载一个项目和它的整个代码历史
git clone [url]
```

## 查看、添加、提交、

```
git help <command> # 显示command的help
git show # 显示某次提交的内容 git show $id
git checkout -- <file> # 抛弃工作区修改
git checkout . # 抛弃工作区修改
git add <file> # 将工作文件修改提交到本地暂存区
git add . # 将所有修改过的工作文件提交暂存区
git rm <file> # 从版本库中删除文件
git rm <file> --cached # 从版本库中删除文件，但不删除文件
```

## 提交修改到分支

```
git commit  -m "提交的描述信息" ＃-m 描述
git commit -a -m "提交的描述信息" ＃-a 只将所有被修改或者已删除的且已经被git管理的文档提交倒仓库中

# 使用一次新的commit，替代上一次提交
# 如果代码没有任何新变化，则用来改写上一次commit的提交信息
git commit --amend -m [message]

```

# 恢复版本

```
git reset <file> # 从暂存区恢复到工作文件
git reset -- . # 从暂存区恢复到工作文件
git reset --hard # 恢复最近一次提交过的状态，即放弃上次提交后的所有本次修改
git reset --hard HEAD^ # 恢复到上一次提交的状态 ^代表上个版本 ^^代表上上个版本
git reset --hard <commitid> #恢复到指定的版本  commitid可配合git reflog使用
```

## 对比文件

```
git diff <file> # 比较当前文件和暂存区文件差异 git diff
git diff <id1><id2> # 比较两次提交之间的差异
git diff <branch1>..<branch2> # 在两个分支之间比较
git diff --staged # 比较暂存区和版本库差异
git diff --cached # 比较暂存区和版本库差异
git diff --stat # 仅仅比较统计信息
```

## 查看提交记录

```
git log  <file> # 查看该文件每次提交记录
git log -p <file> # 查看每次详细修改内容的diff
git log -p -2 # 查看最近两次详细修改内容的diff
git log --stat #查看提交统计信息

# 显示指定文件是什么人在什么时间修改过
git blame [file]

# 显示某个文件的版本历史，包括文件改名
git log --follow [file]
git whatchanged [file]

# 显示某个commit之后的所有变动，每个commit占据一行
git log [tag] HEAD --pretty=format:%s

# 显示某个commit之后的所有变动，其"提交说明"必须符合搜索条件
git log [tag] HEAD --grep feature
```

## 查看、切换、创建和删除分支

```
git branch -r # 查看远程分支
git branch <new_branch> # 创建新的分支
git branch -v # 查看各个分支最后提交信息
git branch --merged # 查看已经被合并到当前分支的分支
git branch --no-merged # 查看尚未被合并到当前分支的分支
git checkout <branch> # 切换到某个分支
git checkout -b <new_branch> # 创建新的分支，并且切换过去
git checkout -b <new_branch> <branch> # 基于branch创建新的new_branch
git checkout $id # 把某次历史提交记录checkout出来，但无分支信息，切换到其他分支会自动删除
git checkout $id -b <new_branch> # 把某次历史提交记录checkout出来，创建成一个分支
git branch -d <branch> # 删除某个分支
git branch -D <branch> # 强制删除某个分支 (未被合并的分支被删除的时候需要强制)

```

## 分支合并

```
git merge <branch> # 将branch分支合并到当前分支
git merge origin/master --no-ff # 不要Fast-Foward合并，这样可以生成merge提交
```


## 暂存管理

```
git stash # 暂存
git stash list # 列所有stash
git stash apply # 恢复暂存的内容
git stash drop # 删除暂存区
```
## 远程分支管理

```
git pull [remote] [branch]# 取回远程仓库的变化，并与本地分支合并
git pull --no-ff # 抓取
git fetch origin # 抓取远程仓库更新不自动合并
git merge origin/master # 将远程主分支合并到本地当前分支
git checkout --track origin/branch # 跟踪某个远程分支创建相应的本地分支
git checkout -b <local_branch> origin/<remote_branch> # 基于远程分支创建本地分支，功能同上
git push # push所有分支
git push origin master # 将本地主分支推到远程主分支
git push -u origin master # 将本地主分支推到远程(如无远程主分支则创建，用于初始化远程仓库)
git push origin <local_branch> # 创建远程分支， origin是远程仓库名
git push origin <local_branch>:<remote_branch> # 创建远程分支
git push origin :<remote_branch> #先删除本地分支(git branch -d <branch>)，然后再push删除远程分支

# 强行推送当前分支到远程仓库，即使有冲突
$ git push [remote] --force

# 推送所有分支到远程仓库
$ git push [remote] --all
```

## 远程仓库管理

```
git remote -v # 查看远程服务器地址和仓库名称
git remote show origin # 查看远程服务器仓库状态
git remote add origin git@ github:robbin/robbin_site.git # 添加远程仓库地址
git remote set-url origin git@ github.com:robbin/robbin_site.git # 设置远程仓库地址(用于修改远程仓库地址)
git remote rm <repository> # 删除远程仓库
git branch --set-upstream master origin/master #设置跟踪远程库和本地库
```

## 标签说明

git标签分为两种类型：轻量标签和附注标签。轻量标签是指向提交对象的引用，附注标签则是仓库中的一个独立对象。建议使用附注标签。

```
git tag #打印出当前仓库所有的标签
git tag -l 'v0.1.*'  #搜索副歌模式的标签
git tag v0.1.2 -light #创建轻量标签
git tag －a v1.0.1 -m '1.0.1版本'  #创建附注标签 (-a 指定标签类型，后附标签名。-m指定标签说明)
git checkout [tagname] #切换到标签
git show v1.0.0 #查看标签版本信息
git tag -d v1.0.0 #删除标签
git push --delete origin v1.0.0 #删除线上标签
git push origin v1.0.0  #将1.0.0标签提交到git服务器
git push origin --tags #将本地所有标签一次性提交到git服务器
git fetch origin tag v1.0.0 #获取远程版本

```

# 导出干净代码

```
git archive --format zip --output "./output.zip" master -0  
```
将代码导出并 zip 打包后放在当前目录下，`output.zip`就是需要的文件，`-0`的意思是不压缩。



