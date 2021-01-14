---

---

# git-分布式版本控制软件

## 第一个版本

初始化

```
git init 
```

检测文件夹文件状态

```
git status
```

添加想管理的文件

```
git add filename(添加过的绿色，没有添加的红色)
```

添加所有剩余文件

```
git add .
```

配置个人信息

```
git config --global user.email "123123@qq.com"
git config --global user.name "gc
```

生成一个版本

```
git commit -m '第一个版本'
```

注：文件为红色表示改变过，或者未管理

## 第二个版本（更改某个文件后）

检测文件是否改变

```
git status
```

将修改后的文收集管理

```
git add .
```

生成下一个版本

```
git commit -m '第二个版本'
```

查看所有版本的信息（不包含回滚）

```
git log
```

版本回滚

```
1.git log 获取你想要版本的commit值
2.git reset --hard commitvalue
```

查看所有版本的信息（包含回滚）

```
git reflog
```

恢复被回滚的版本

```
1. git reflog 获取你想要版本的value 
2. git reset --hard value
```

恢复被修改的但未提交的文件（红色）

```
git checkout -- filename
```

将已经提交的文件（绿色）改为未提交（红色）

```
git reset HEAD filename
#想要恢复成原始版本，再进行 git checkout -- filename 即可
```

# 提高

查看所在分支

```
git branch
```

创建新的分支

```
git branch name
```

切换分支



```
git checkout dev	
注：切换分支会保留当前分支转态，并且将代码回滚至另一分支的上个状态.
```

删除分支 

```
git branch -d name
```

将其他分支代码合并到主分支

![1](/git_pic/1.png)

```
1.切换到master分支
git checkout master
2.合并
git merge test
注：合并时的代码冲突，手动找文件修改
```

# 提交到远端仓库

给仓库起别名(origin)

```
git remote add origin https://url
```

向远端提交代码

```
git push -u 别名 分支名
```

从远端拉取代码（第一次，全部）

```
git clone url
注：拉去的时候会把所有的信息拉取下来
```

从远端拉取代码（更新本地代码）

```
git pull 别名 分支名
注：更新本地代码
```

