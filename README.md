
```
//注册用户名与邮箱
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
//创建git版本库
git init

//将文件添加仓库
git add readme.txt

//将文件提交到仓库
git commit -m "wrote a readme file" 

//m参数为添加描述,可以add多次，统一commit一次提交
//查看当前仓库状态
git status

//查看具体的修改状态
git diff

//查看所有的提交信息
git log
git log --pretty=oneline//压缩一行显示
在一行开头位置为id号也就是Git提交的版本号
HEAD表示当前版本，可以理解成是一个指针

//回退到上一个的版本
git rest --hard HEAD^
HEAD^^ //返回上上个版本
HEAD~100 //返回前100个版本

git reset --hard 1094a //也可以通过前几位id回退或前进

//查看所有的操作记录和id
git reflog

//导出主干的文件，覆盖工作区
git checkout -- readme.txt
//加入已经add到暂存区，可以回退到工作区
git reset HEAD readme.txt

//删除文件 并提交
git rm test.txt
git commit -m "remove test.txt"



```

```
//远程仓库

//创建秘钥
ssh-keygen -t rsa -C "youremail@example.com"

//接下将公钥，复制到GitHub
//连接远程,
git remote add origin git@github.com:frontEndJiang/learngit.git
//将代码推送到远程
git push -u origin master

//从远程克隆代码
git clone git@github.com:frontEndJiang/gitskills.git

```

```
//创建于合并分支
git checkout -b dev //创建并切换到dev分支

git branch //查看当前处于哪一个分支

git checkout master //切换到主分支

git merge dev //将dev合并到主分支

git branch -d dev //删除dev分支

```

```
查看分支的合并情况
git log --graph --pretty=oneline --abbrev-commit

git merge --no-ff -m "merge with no-ff" dev //禁用fast-forward
```

```
//暂时存储当前未提交的工作内容
git stash

git stash list //查看当前存储区的信息

git stash pop //将存储区恢复到工作区，并将stash删除

git branch -D feature-vulcan//可以强制删除已经提交还未合并的分支

```

```
//查看远程仓库
git remote

//将远程的分支拉到本地
git checkout -b dev origin/dev

//指定本地dev与远程dev的链接
git branch --set-upstream-to=origin/dev dev

git rebaseb//操作可以把本地未push的分叉提交历史整理成直线
```

```
//标签管理
git tag v1.0 //在当前分支打印标签
git tag //查看所有标签
git show <tagname> //查看标签信息

git tag -a v0.1 -m "version 0.1 released" 1094adb//-a指定标签名，-m指定说明文字

git tag -d v0.1//删除标签

git push origin v1.0 //将标签推送到远程

git push origin --tags //将本地标签推送到远程


//删除远程的标签
git tag -d v0.9 //先删除本地
git push origin :refs/tags/v0.9 


```




