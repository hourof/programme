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

## 1.查看分支

```
git branch
```

## 2.创建分支

```
git branch <新分支名称>
```

## 3.切换分支

```
git checkout <分支名称>
```

## 4.切换到main分支

```
git branch -M main
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

# 6.远程提交

## 1.给仓库起别名

```
#origin就是仓库别名 后面的地址是仓库地址
git remote add origin  https://github.com/hourof/programme.git
```

## 2.查看仓库的别名

```python
#查看 本地仓库关联的 远程仓库
git remote

#查看 本地仓库关联的 远程仓库信息
git remote -v
```

## 3.修改远程仓库的别名

```
git remote add     github git@github.com:toFrankie/repo-demo.git        新增 远程仓库别名
git remote rm      github                                                删除 已存在 远程仓库别名（只会移除本地仓库与远程仓库的管理，不会删除远程仓库的代码）
git remote rename  github gitlab                                     修改 远程仓库别名（也可以先删除再添加）
git remote set-url github git@github.com:toXXXX/repo-demo.git       更新 远程仓库别名 关联的 远程仓库

```

 ## 4.提交到远端仓库

```
git push -u origin main
```

## 提交历史记录出现的问题解决方案网址

[解决Git连接失败：Failed to connect to github.com port 443 after 21090 ms: Couldn‘t connect to server ‍-腾讯云开发者社区-腾讯云](https://cloud.tencent.com/developer/article/2405656)

# 5.用户信息

## 1.查看用户自己配置

```
git config --global --list
```

# 6.配置ssh

## 1.生成ssh密钥

> ssh-keygen -t rsa -C "这里换上你的邮箱"
>
> 询问得时候一路回车键就行,然后自动生成密钥
>
> 
>
> 查看邮箱命令
>
> git config --global --list

## 2.查看生成得密钥
<font color=Blue>cat ~/.ssh/id_rsa.pub</font>

把方框里面得内容复制

![1](img\ssh.png)

## 3.配置github

![1](img/4.png)

![1](img/5.png)

## 4.测试ssh连接
<font color="Blue">ssh -T git@github.com</font>

> 当返回这段英文时就代表配置成功
>
> Hi hourof! You've successfully authenticated, but GitHub does not provide shell access.
