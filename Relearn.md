### # 0 为什么要重新学git

​		因为自己开发的时候只会老三步：add commit push，之前学的都忘记完了，作为必须的技能，还是的重新复习一遍。



### # 1 安装git

​		这步pass了，如果安装还要说一遍，那建议不要当程序猿了。



### # 2 基本操作

- git init										----初始化仓库
- git add filename                      ----将文件储存至暂存区（staging area）
- git commit                                ----将文件添加至版本库



### # 3 基础命令

- git status								   ----查看working space（工作区）的文件状态
- git log 								        ----查看提交日志
- git log --pretty=oneline           ----查看提交日志（最近一次）



### # 4 时光回退

- git reset head~						    ----回退版本（一个波浪线表示回退1个版本，想要回退10个版本用~10）
  - git reset --hard head~     	----回退版本（工作区 暂存区 版本库都回退）
  - git reset --soft head~           ----回退版本（工作区不会回退，暂存区和版本库回退）

- git reflog                                       ----显示每一次操作的版本id号

  

### # 5 版本对比（少用）

- git diff



### # 6 忽略文件(.gitignore)

```bash
*.xxx					// 忽略所有后缀为xxx的文件
/node_modules			// 忽略node_modules整个文件夹
/mtk/do.c				// 忽略某个具体文件
```



### # 7 分支

```bash
git branch branchname		// 创建分支
git checkout branchname		// 切换分支
git merge branchname		// 合并到主分支
git branch -d branchname	// 删除分支
```

分支冲突：多个分支同时进行开发最后合并到主分支上导致文件不统一而产生的冲突。

解决冲突：在主分支上决定那个分支上的文件内容正确就留哪个，再通过在主分支上add和commit。

> **每天按时拉取和提交代码是一个合格程序员应有的习惯，不要当冲突制造机器！！**



### # 8 多人合作

首先有一个共同的repo

repo通常会有以下几个分支：

- master

- release

- develop

  ​	master分支上面的代码一般都是经过测试，功能完备的代码，一般由项目经理管理。

  ​	release分支上面的代码一般是要测试的代码

  ​	develop分支上面的代码就是程序猿要操作的代码，程序猿从这个分支上拉代码，然后创建自己的分支进行开发，最后push到develop这个分支上。



### # 9 跨团队合作

