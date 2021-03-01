# Git版本库的操作：

## 1.git版本库内容添加

git status ：版本库状态变化

git diff  文件名：查看版本库中变化文件名的区别

## 2.git版本库的版本切换

git log:查看版本库的命令行历史记录

git reset -hard HEAD^:返回文件的上一个版本

cat +文件名：查看文件内容

git reflog：查看历史命令操作，可以查找（git reset -hard +命令编号）的命令编号，便于返回编号版本

## 3.工作区和暂存区

工作区：创建的目录（例如：gitlearn文件夹）
版本库：在工作区内的# (.git文件夹)

暂存区：版本库内stage，git add +文件名：将文件放入暂存区

master（主干分支）：git为目录创建的第一个分支，有一个HEAD指针指向它。

git commit  -m "批注提交主干分支的内容"：将暂存区的内容合并提交到主干分支。

![git-repo](https://www.liaoxuefeng.com/files/attachments/919020037470528/0)

## 4.管理修改

  在我们工作中经常出现修改错误和错误操作，很容易让我们的工作进度付之东流，git为我们提供的完整的管理修改，git管理的是修改，而不是文件。

git diff HEAD -- 文件名：查看文件版本与上一版本的文件的区别

## 5.撤销修改

  git status：查看工作区变化状态

git checkout -- file ：丢弃file工作区的修改

git reset HEAD  <file>：可以把暂存区的修改撤销掉（unstage），重新放回工作区

## 6.删除文件

rm +文件名：删除工作区文件

```
git rm test.txt ：删掉暂存区文件，再用git commit -m "remove test.txt"，文件从版本库删除
git checkout -- test.txt：撤销操作，再用git reset 文件：恢复。
```