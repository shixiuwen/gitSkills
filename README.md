# gitSkills

### 获得公钥私钥

```
$ ssh-keygen -t rsa -C "shixiuwen1991@yeah.net"
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/Administrator/.ssh/id_rsa):
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /c/Users/Administrator/.ssh/id_rsa.
Your public key has been saved in /c/Users/Administrator/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:TLFdjTxp91rIOV7N9/+KIz3bwZejOmpWrevjypAf1SY shixiuwen1991@yeah.net
The key's randomart image is:
+---[RSA 2048]----+
|        .  ..+   |
|         + .* o  |
|        o .. + =.|
|       o    . = B|
|        S  E.+ =o|
|        . ..ooo o|
|       o .... ooo|
|        +oo++o.oo|
|        o==*B=o.o|
+----[SHA256]-----+

```

### Github使用指南：

1.	安装GitBash
2.	在gitBash中执行命令：cd  ~
3.	ssh-keygen -t rsa -C shixiuwen1991@yeah.net
 会在默认目录中生成：

 > /c/Users/Administrator/.ssh/id_rsa

 用记事本打开，将其中内容复制到GitHub的SSH设置中，这样你的电脑才能和GitHub中新建立的库同步

#### 现在开始使用GitHub:

1.	在本地建立一个Android工程，名字比如WeChat(或者假设你的本地已经有一个名字叫做WeChat的工程，想同步到GitHub进行代码托管)

2.	在GitHub上创建一个同名的库

3.	在gitbash中，切换到你工程所在目录，执行以下命令：

 > git init

 > PS：该步骤执行完之后不可执行以下两步： 1.git add .   ->   2.git commit -m "",如果执行了，则在本地初始化master分支，该分支会和origin/master分支冲突

4. 将本地库同GitHub上的库关联

 > git remote add origin git@github.com:shixiuwen/WeChat.git

 > PS:执行到这一步，已同远程库关联

 执行git branch 你会发现本地没有branch分支，继续执行

 > git fetch
 
 > git checkout –b master origin/master（该步骤可能提示如.gitignore等的文件冲突，如果有，删除本地的或者服务器上的文件）

 同步远程master分支到本地，本地就有了和远程库关联的master分支，接下来可以执行提交代码操作了

 > git push origin master

 > PS:执行到这一步，你的本地库已经推送到GitHub上了，同时同步了一个主分支master

5.	切换分支进行工作：

 > git checkout –b jrw

6.	进行代码修改后提交代码

 > git add .
 
 > git commit –m “在分支上提交操作”

7.	切换回主分支拉最新代码：

 > git checkout master
 
 > git pull

8.	切回jrw分支合并主分支master可能被他人修改后的代码

 > git checkout jrw
 
 > git merge master(该步骤执行完后可能会有冲突，有冲突的话执行git add . git commit )
 
 > git push origin jrw（这是在提交合并请求，执行完该步骤之后去GitHub执行push request 然后等待主分支接受合并） 

