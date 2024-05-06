1. 打开 git-bash , 新建一个文件夹dir
2. 进入dir,输入 git init 将这个目录变成仓库，会出现一个隐藏文件 .git 
3. 添加文件: 编辑保存一个文件, 然后
    git add <filename>    将文件放入暂存区
    git commit -m ''      将文件提交到分支
可同时 add多个文件, 然后一并commit

常用命令：
git status   查看文件状态，是否被改动过
git diff     查看文件被修改的内容
rm  <filename>  删除掉工作区的文件，但分支上的文件并没有被删除
如果想删除分支上的文件:   git rm <filename>  并 git commit -m ''
如果是误删, 使用 git checkout -- <filename> 恢复, 当然只能恢复分支上保存的文件


# 一、将本地文件推送到远程仓库
1. 首先在GitHub上创建一个仓库
2. 在本地文件夹下运行：
git remote add [<name>] git@github.com:phyoung123/gitskills
    首次推送是要用add将仓库命名
    git remote -v 查看当前文件夹下面添加了哪些远程库

3. 把本地库推送到远程库上
    git push -u [<name>] master
    第一次推送时要加 -u ,将本地master分支与远程master分支关联
    后续直接git push [<name>] master


# 二、从远程库克隆
    git clone git@github.com:phyoung123/gitskills 
    这是ssh协议, 传输很快
    除此之外还可以 git clone htts://github.com/.....
    这是http协议,比较慢

# 三、创建分支
当在团队多人协同操作一个文件时, 可以先创建一个自己的分支, 然后再合并过去
首先用 git branch 查看当前有哪些分支

1. 创建分支并切换过去
    git checkout -b [<name>] 或者 git switch -c [<name>]
    单纯创建一个分支
    git switch [<name>]

2. 在分支上修改的内容不会引起master分支的变化, 需要 git merge [<name>] 将分支 merge 到master上
    合并完后就可以删除分支 git branch -d [<name>]

# 总的流程就是

git add → git commit -m '对这次修改的描述' → git remote add [<name>] git@github.com:... → git push -u [<name>] master 
