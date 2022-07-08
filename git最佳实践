### **git reset**

根据–soft –mixed –hard，会对working tree和index和HEAD进行重置:

  git reset --mixed：此为默认方式，不带任何参数的git reset，即时这种方式，它回退到某个版本，只保留源码，回退commit和index信息

  git reset --soft：回退到某个版本，只回退了commit的信息，不会恢复到index file一级。如果还要提交，直接commit即可

  git reset --hard：彻底回退到某个版本，本地的源码也会变为上一个版本的内容，此命令 慎用！

  HEAD 最近一个提交

  HEAD^ 上一次提交

  HEAD^ ^ 上一次的 上一次的提交（倒数第三次）

  HEAD^^^ 倒数 第四次的 提交

### git强制覆盖本地文件

git fetch --all

git reset --hard origin/master

git pull

### git强制推送本地代码到远程仓库

git push -u origin develop

### cherry-pick

从一个分支合并多个commits到其他分支：

[Git-用 cherry-pick](https://blog.csdn.net/qq_32452623/article/details/79449534)

### rebase 合并提交记录

1)从HEAD版本开始往过去数3个版本

git rebase -i HEAD~3

2)指定要合并的版本之前的版本号

git rebase -i 3a4226b

3）git rebase --abort 取消rebase操作 

https://blog.csdn.net/qhshiniba/article/details/44154121

https://segmentfault.com/a/1190000007748862
