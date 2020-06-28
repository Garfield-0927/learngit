##create  a repository
	$ mkdir learngit
	$ cd learngit
	$ pwd
	path

	$git init	//initialize the repository

##add and commit file
	$ git add xxx
	$ git commit -m "content"

##check log
	$ git log

##back version
	$ git reset --hard HEAD^	//HEAD^退回上一个版本   HEAD^^退回俩个版本   HEAD~100 往上100个版本
	$ git reset --hard 版本号	//退回指定的版本
	
##check file
	$ cat xxx

##check status
	$ git status

##recall changes
	$ git checkout --xxx		//命令git checkout -- readme.txt意思就是，把readme.txt文件在工作区的修改全部撤销,总之，就是让这个文件回到最近一次git commit或git add时的状态。

##delete files
	$ git rm xxx
	$ git commit  -m "xxx is removed"

##关联 github.com
	$ ssh-keygen -t rsa -C "youremail@example.com"
	##获取Key
	##然后登陆github.com, add SSH Key,在Key文本框里粘贴id_rsa.pub文件的内容

##添加远程库
	##先在github上建一个库
	##然后，把本地仓库的内容推送到GitHub仓库。
	##下一步，就可以把本地库的所有内容推送到远程库上
	$ git remote add origin git@github.com:你的名字/库的名字.git
	$ git push -u origin master
	##本地做修改后，通过下面的命令把最新修改更新至github的repo
	$ git push origin master

##clone repo from github.com
	$ git clone git@github.com:名字/repo的名字.git

##branch
	查看分支：$ git branch
	创建分支：$ git branch <name>
	切换分支：$ git switch <name>
	创建+切换分支：$ git switch -c <name>
	合并某分支到当前分支：$ git merge <name>
	删除分支：$ git branch -d <name>


