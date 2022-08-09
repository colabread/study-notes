## 基础

### git代码流
```
工作区（unstage、untracked）
↓ add
暂存区
↓ commit
本地仓库
↓ push ↑ fetch
远程仓库

本地仓库 →（diff）工作区
远程仓库 →（pull）工作区
```

### git配置信息
```
git config --system --list
查看本地git系统配置
git config --global --list
查看本地的账户配置
git config --local --list
查看当前分支配置
```

### git账户设置
```
git config user.name [username]
查看/设置username
git config user.email [email]
查看/设置email
```

## 进阶

### git fetch
拉取远程仓库到本地仓库

### git diff
对比本地仓库与工作区

### git reflog
查看所有head指向记录
此命令可以用于回退或取消回退

### git commit --amend
修改上一次commit的提交信息，并且重写commitId（自动）

### git reabse
```
非常强大的功能，可以同时处理多个commit
保留commit（pick p）
修改commit的提交信息（reword r）
合并commit到上一个commit（squash s）
丢弃commit（drop d）

如果rebase中出现冲突，则手动合并，结束后：
git add .
git rebase —continue

rebase后可能会出现head指针分离状态，解决方案请见：
https://blog.csdn.net/qq_32907195/article/details/109217034
```

### git log —oneline
查看当前分支的最近commit，每条commit以一行显示，可通过⬆️⬇️⬅️➡️回车键、q控制日志显示

### git restore --staged [filepath]
将指定文件从暂存区退回到工作区

### git stash
+ https://www.git-tower.com/learn/git/ebook/cn/command-line/branching-merging/stashing
1. git stash
将当前工作区的所有修改剪切到临时栈

2. git stash list
查看stash栈

3. git stash pop
将最新的stash剪切到工作区

4. git stash apply [stashname]
将指定的stash复制到工作区
  
5. git stash drop [stashname]
删除指定stash
