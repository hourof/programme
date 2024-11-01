# 1.查看远程仓库地址

git remote -v

# 2.重新设置远程仓库地址

git remote set-url origin https://gitee.com/xx/xx.git (新地址)

# 3.查看提交历史记录

```python
#查看详细历史记录
git log

#显示简介的一行提交历史
git log --oneline

#显示分支合并图，同时显示分支和标签信息
git log --graph --decorate --oneline
```

# 4.分支命令

```python
# 查看有哪些分支
git branch
#创建分支命令
git branch  <新分支名称>
#切换分支
git checkout <分支名称>
```

# 5.切换到提交的某一份历史

> 首先查看提交历史记录
>
> 用git log  --oneline 命令

![1](img\1.png)

> 黄色字体就是提交的哈希值

```python
#切换到某一次提交的历史，比如切换到first commit这次
git checkout <6c27aa6>
```

