# git常用指令

## 流程理解

工作区-->暂存区-->分支-->个人仓-->公共仓

## 流程类

```shell
git config --global user.name '你的用户名'
git config --global user.email '你的邮箱'
git init #初始化git仓库
git add readme.txt #添加文件到版本库
git commit -m "wrote a readme file" #把文件提交到仓库

git clone git@github.com:ChlMr/test.git #克隆个人仓 一般默认名字问origin
git remote add upstream git@github.com:michaelliao/gitskills.git #添加公共仓
git fetch upstream #拉取公共仓代码
git merge upstream/master #将公共仓master分支合并到本地分支
git push origin master #将修改提交到个人仓

git checkout -b dev #创建并切换到dev分支
git checkout master #切换回master分支
git merge dev #将dev分支合并到当前分支
```

## 查看类

```shell
git config --list #查看配置是否成功
git status #查看仓库当前的状态
git diff readme.txt #查看add之前文件的不同
git log #查看从最近到最远的提交日志
git reflog #查看每一次命令
git remote -v #查看远程仓
git branch #查看当前分支
```

## 撤销类

```shell
git checkout -- readme.txt #改回git add之前的状态
git reset HEAD readme.txt #撤回之前的git add
git reset --hard HEAD^ #返回上一个版本的提交
git reset --hard 1094a #返回commit id为1094axxx的那个版本

git remote rm origin #删除origin仓库
git branch -d dev #删除dev分支
```

## 解决冲突

```shell
git status #查看具体是哪个文件有冲突
git add readme.txt #假设是readme.txt文件冲突，修改后add
git commit-m "conflict fixed" #修改后再提交
```

