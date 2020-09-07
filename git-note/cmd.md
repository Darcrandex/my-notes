# 常用指令

1. 初始化本地仓库

```
cd my-project
git init
```

2. 克隆仓库

```
git clone <仓库地址(线上/本地)>

git clone <地址> <本地仓库新的名字>

git clone -b <指定要克隆的分支名> <地址>
```

3. 工作区->暂存区

```
// 暂存个别文件,空格隔开多个文件名
git add <文件路径>

// 暂存所有修改的文件
git add .
```

4. 暂存区->本地仓库

```
git commit -m "备注"
```

5. 拉取线上新内容(尝试合并)

```
git pull <终端名称> <分支名称>

git pull origin master

git pull gitee my-branch
```

6. 本地仓库->线上仓库

```
git push <终端名称> <分支名称>

git push origin master
```

7. 查看关联的终端

```
git remote -v
```

8. 查看修改历史

```
git log
```

9. 将 A 分支的单个`commit`的内容合并到 B 分支

> [git cherry-pick 教程](http://www.ruanyifeng.com/blog/2020/04/git-cherry-pick.html)

```
git checkout A
git commit -m 'a1 的内容'
git push origin A
git log
```

查看'a1 的内容'所对应的 id

```
git checkout B
git cherry-pick <id>
```

![git 指令](https://atts.w3cschool.cn/attachments/image/20191225/1577243564858376.png)
